---
description: Cette méthode convertit un emplacement et un offset de méthode en une adresse mémoire.
title: 'IDebugExpressionEvaluator :: GetMethodLocationProperty | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f841f602064b21035ea409457c708f99ec25bf12
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102152518"
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
Cette méthode convertit un emplacement et un offset de méthode en une adresse mémoire.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMethodLocationProperty( 
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider* pSymbolProvider,
   IDebugAddress*        pAddress,
   IDebugBinder*         pBinder,
   IDebugProperty2**     ppProperty
);
```

```csharp
int GetMethodLocationProperty(
   string               upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider pSymbolProvider,
   IDebugAddress        pAddress,
   IDebugBinder         pBinder,
   out IDebugProperty2  ppProperty
);
```

## <a name="parameters"></a>Paramètres
`upstrFullyQualifiedMethodPlusOffset`\
dans Emplacement et décalage de la méthode, exprimé sous la forme d’une chaîne.

`pSymbolProvider`\
dans Fournisseur de symboles exprimé sous la forme d’un objet [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) .

`pAddress`\
dans Adresse dans la méthode, exprimée sous la forme d’un objet [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) .

`pBinder`\
dans Binder exprimé sous la forme d’un objet [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) .

`ppProperty`\
à Retourne une interface [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) qui représente l’adresse mémoire.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 L’adresse retournée peut être utilisée pour définir un point d’arrêt, par exemple.

 Malgré le nom `upstrFullyQualifiedMethodPlusOffset` , un nom de méthode partiellement qualifié peut être passé à ce paramètre. Dans ce cas, la méthode sélectionnée est celle qui est entourée `pAddress` . La façon dont ce paramètre est interprété dépend de l’implémentation de l’évaluateur d’expression et du langage qu’il prend en charge.

## <a name="see-also"></a>Voir aussi
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)
