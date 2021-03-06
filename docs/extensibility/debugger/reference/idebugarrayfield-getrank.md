---
description: Obtient le rang ou le nombre de dimensions du tableau.
title: 'IDebugArrayField :: GetRank, | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d9e3d822bac6fa16314f5d2962d69adbf74d0bc3
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102143712"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
Obtient le rang ou le nombre de dimensions du tableau.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

## <a name="parameters"></a>Paramètres
`pdwRank`\
à Retourne le rang.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne S_OK ; Sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Le rang d’un tableau correspond au nombre de dimensions. En C++ et C#, les tableaux multidimensionnels sont vraiment des tableaux de tableaux et peuvent donc être considérés comme un tableau unidimensionnel (et la `GetRank` méthode retourne toujours 1). En [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] revanche, les tableaux multidimensionnels sont gérés différemment et le rang d’un tel tableau reflète le nombre de dimensions (et la `GetRank` méthode retourne toujours le nombre de dimensions).

## <a name="see-also"></a>Voir aussi
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)
