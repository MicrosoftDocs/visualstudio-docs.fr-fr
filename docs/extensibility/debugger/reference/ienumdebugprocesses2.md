---
description: Cette interface énumère les processus en cours d’exécution sur un port de débogage.
title: IEnumDebugProcesses2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2
helpviewer_keywords:
- IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 75778ea0f02c0e7dcca1f7d2eb0ea8ace82c9b9c
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102224380"
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
Cette interface énumère les processus en cours d’exécution sur un port de débogage.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugProcesses : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Un fournisseur de port personnalisé implémente cette interface pour fournir une liste des processus en cours d’exécution sur un port.

## <a name="notes-for-callers"></a>Notes pour les appelants
 Visual Studio appelle [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) pour obtenir cette interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
 Le tableau suivant présente les méthodes de `IEnumDebugProcesses2` .

|Méthode|Description|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|Récupère un nombre spécifié de processus dans une séquence d’énumération.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|Ignore un nombre spécifié de processus dans une séquence d’énumération.|
|[Réinitialiser](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|Réinitialise une séquence d'énumération.|
|[Répliqué](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|Crée un énumérateur qui contient le même état d’énumération que l’énumérateur actuel.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|Obtient le nombre de processus dans un énumérateur.|

## <a name="remarks"></a>Notes
 Visual Studio utilise cette interface pour remplir la fenêtre **processus** .

## <a name="requirements"></a>Spécifications
 En-tête : msdbg. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)
