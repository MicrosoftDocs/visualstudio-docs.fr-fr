---
description: Charge les symboles pour le module en cours.
title: 'IDebugModule3 :: LoadSymbols | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0612be8ffdde8a942331a89e08298f71414a4c76
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102164823"
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
Charge les symboles pour le module en cours.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT LoadSymbols(
   void
);
```

```csharp
int LoadSymbols();
```

## <a name="return-value"></a>Valeur de retour
 Si la méthode réussit, retourne `S_OK`. En cas d'échec, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Cette méthode charge les symboles à partir du chemin de recherche actuel (qui peut être modifié en appelant la méthode [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) ).

 Cette méthode est préférable à la méthode [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) .

## <a name="see-also"></a>Voir aussi
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)
- [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)
