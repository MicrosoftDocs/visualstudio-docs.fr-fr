---
description: Énumère les attributs personnalisés.
title: IEnumDebugCustomAttributes | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCustomAttributes
helpviewer_keywords:
- IEnumDebugCustomAttributes interface
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: bffa799ba14738daea480a1677f1b1a820e98767
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102226837"
---
# <a name="ienumdebugcustomattributes"></a>IEnumDebugCustomAttributes
Énumère les attributs personnalisés.

## <a name="syntax"></a>Syntaxe

```
IEnumCustomAttributes : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Un fournisseur de symboles implémente cette interface pour prendre en charge des attributs personnalisés (par le biais de l’interface [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) ).

## <a name="notes-for-callers"></a>Notes pour les appelants
- [EnumCustomAttributes (](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) retourne cette interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
 Le tableau suivant présente les méthodes de `IEnumDebugCustomAttributes` .

|Méthode|Description|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|Récupère un nombre spécifié d’attributs personnalisés dans une séquence d’énumération.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|Ignore un nombre spécifié d’attributs personnalisés dans une séquence d’énumération.|
|[Réinitialiser](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|Réinitialise une séquence d'énumération.|
|[Répliqué](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|Crée un énumérateur qui contient le même état d’énumération que l’énumérateur actuel.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|Obtient le nombre d’attributs personnalisés dans un énumérateur.|

## <a name="requirements"></a>Spécifications
 En-tête : SH. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces des fournisseurs de symboles](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)
