---
description: Cette interface marshale les interfaces relatives au programme à travers les limites du processus.
title: IDebugProviderProgramNode2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: a615c076fd34d7bc230efb0f36683b7167b66566
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102167852"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
Cette interface marshale les interfaces relatives au programme à travers les limites du processus.

## <a name="syntax"></a>Syntaxe

```
IDebugProviderProgramNode2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Le moteur DE débogage (DE) implémente cette interface sur le même objet qui implémente [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) pour prendre en charge les interfaces de marshaling entre les limites de processus.

## <a name="notes-for-callers"></a>Notes pour les appelants
 Appelez [QueryInterface](/cpp/atl/queryinterface) sur une `IDebugProgramNode2` interface pour obtenir cette interface. Si cette interface ne peut pas être obtenue, le DE ne prend pas en charge le marshaling des interfaces.

## <a name="methods-in-vtable-order"></a>Méthodes dans l’ordre vtable
 Cette interface implémente la méthode suivante :

|Méthode|Description|
|------------|-----------------|
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|Obtient une interface spécifiée à travers les limites du processus.|

## <a name="remarks"></a>Notes
 Cette interface est implémentée lorsque le s’exécute dans un espace de processus distinct du programme en cours de débogage : par exemple, lorsque le DE est exécuté dans l’espace de processus Visual Studio au lieu de l’espace de processus du programme en cours de débogage.

## <a name="requirements"></a>Configuration requise
 En-tête : msdbg. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
