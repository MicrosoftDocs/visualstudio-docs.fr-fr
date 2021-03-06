---
description: Cette interface permet au gestionnaire de débogage de session (SDM) de notifier à un processus qu’il est attaché ou détaché du processus.
title: IDebugProcessEx2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: e91e61c2fc125829d3c9dacf942635021b8e3886
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102149715"
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Cette interface permet au gestionnaire de débogage de session (SDM) de notifier à un processus qu’il est attaché ou détaché du processus.

## <a name="syntax"></a>Syntaxe

```
IDebugProcessEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Un fournisseur de port personnalisé implémente cette interface sur le même objet que l’interface [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) afin de :

- Prendre en charge le suivi des sessions connectées à un processus

- Prendre en charge l’attachement automatique sur plusieurs moteurs de débogage

  Le fournisseur de port personnalisé peut implémenter cette interface s’il le souhaite.

## <a name="notes-for-callers"></a>Notes pour les appelants

- Le SDM appelle [QueryInterface](/cpp/atl/queryinterface) sur une `IDebugProcess2` interface pour obtenir cette interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
 Le tableau suivant présente les méthodes de `IDebugProcessEx2` .

|Méthode|Description|
|------------|-----------------|
|[Attacher](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|Informe le processus qu’une session est en train de déboguer le processus.|
|[Détacher](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|Informe le processus qu’une session n’est plus en train de déboguer le processus.|
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Ajoute des nœuds de programme pour une liste de moteurs de débogage.|

## <a name="remarks"></a>Notes
 Cette interface est privée entre le SDM et le processus.

## <a name="requirements"></a>Configuration requise
 En-tête : Portpriv. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
