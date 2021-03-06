---
description: Récupère un numéro de ligne au moyen d’un index.
title: IDiaEnumLineNumbers::Item | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 6eeea52f2152d1674710d7c5ee2b5970a8cd91cd
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102157979"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
Récupère un numéro de ligne au moyen d’un index.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Item ( 
   DWORD            index,
   IDiaLineNumber** lineNumber
);
```

#### <a name="parameters"></a>Paramètres
 index

dans Index de l’objet [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md) à récupérer. L’index se trouve dans la plage de 0 à `count` -1, où `count` est retourné par la méthode [IDiaEnumLineNumbers :: get_Count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) .

 lineNumber

à Retourne un objet [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md) représentant le numéro de ligne souhaité.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="see-also"></a>Voir aussi
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
