---
description: Retourne une copie de l’énumération des processus en cours sous la forme d’un objet distinct.
title: 'IEnumDebugProcesses2 :: Clone | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Clone
helpviewer_keywords:
- IEnumDebugProcesses2::Clone
ms.assetid: 3d4196d3-5a80-4f76-b8b2-f72e80c8d406
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2189f0b48317ac6dc6459cbd3cde1785e02b25c5
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102226174"
---
# <a name="ienumdebugprocesses2clone"></a>IEnumDebugProcesses2::Clone
Retourne une copie de l'énumération actuelle comme un objet distinct.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone(
   IEnumDebugProcesses2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugProcesses2 ppEnum
);
```

## <a name="parameters"></a>Paramètres
`ppEnum`\
[out] Retourne une copie de cette énumération en tant qu'objet distinct.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 La copie de l’énumération a le même État que l’original au moment où cette méthode est appelée. Toutefois, le de la copie et les États de l’original sont séparés et peuvent être modifiés individuellement.

## <a name="see-also"></a>Voir aussi
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)
