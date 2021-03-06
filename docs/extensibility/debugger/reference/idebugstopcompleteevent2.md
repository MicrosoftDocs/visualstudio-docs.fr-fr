---
description: Le moteur DE débogage (DE) peut envoyer cet événement facultatif au gestionnaire de débogage de session (SDM) lorsqu’un programme s’est arrêté.
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 4d96aa335c8951b9dfc80517bf797338cd590b48
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102159742"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

Le moteur DE débogage (DE) peut envoyer cet événement facultatif au gestionnaire de débogage de session (SDM) lorsqu’un programme s’est arrêté.

## <a name="syntax"></a>Syntaxe

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs

Cette interface a été introduite avec Visual Studio 2005. Les versions antérieures ne prenaient pas en charge l’arrêt asynchrone.

- L' [arrêt](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) est appelé par le SDM dans des scénarios à plusieurs processus ou à plusieurs programmes. Lorsqu’un programme envoie un événement d’arrêt au SDM, le SDM demande également l’arrêt d’autres programmes.

L’arrêt est utilisé pour informer le SDM de manière asynchrone qu’un programme s’est arrêté. L’information du SDM est utile pour un moteur de débogage de l’interpréteur, où aucun code n’est parfois exécuté à l’intérieur du programme débogué. par conséquent, l' [arrêt](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) ne peut pas être effectué de façon synchrone. Si un moteur de débogage souhaite utiliser cette notification asynchrone, il doit retourner `S_ASYNC_STOP` à partir de [Stop](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).

## <a name="requirements"></a>Configuration requise

En-tête : msdbg. h

Espace de noms : Microsoft. VisualStudio. Debugger. Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll
