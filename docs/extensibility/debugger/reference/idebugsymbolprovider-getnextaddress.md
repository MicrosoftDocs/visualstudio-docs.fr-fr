---
description: Obtient l’adresse de débogage qui suit une adresse de débogage donnée dans une méthode.
title: 'IDebugSymbolProvider :: GetNextAddress | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetNextAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetNextAddress method
ms.assetid: 704eeb94-cb13-49d1-82b6-7d83ed0f19c0
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d177d03daef4f8d3344941658b85f71551af126b
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102168411"
---
# <a name="idebugsymbolprovidergetnextaddress"></a>IDebugSymbolProvider::GetNextAddress
Obtient l’adresse de débogage qui suit une adresse de débogage donnée dans une méthode.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetNextAddress( 
   IDebugAddress*  pAddress,
   BOOL            fStatementOnly,
   IDebugAddress** ppAddress
);
```

```csharp
int GetNextAddress( 
   IDebugAddress     pAddress,
   bool              fStatementOnly,
   out IDebugAddress ppAddress
);
```

## <a name="parameters"></a>Paramètres
`pAddress`\
dans Adresse de débogage donnée.

`fStatementOnly`\
dans Si la valeur est TRUE, limite les adresses de débogage à une seule instruction.

`ppAddress`\
à Retourne l’adresse de débogage suivante.

## <a name="return-value"></a>Valeur renvoyée
 Retourne un valide `HRESULT` , généralement S_OK.

## <a name="see-also"></a>Voir aussi
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
