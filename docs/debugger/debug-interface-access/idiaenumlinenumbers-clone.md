---
description: Crée un énumérateur qui contient le même état d’énumération que l’énumérateur de numéro de ligne actif.
title: IDiaEnumLineNumbers::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Clone method
ms.assetid: fcd2479a-8ff7-4aba-a737-06123c280d54
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: af784c89e523f1747b665e46455d5d8b6b7e63b3
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102148982"
---
# <a name="idiaenumlinenumbersclone"></a>IDiaEnumLineNumbers::Clone
Crée un énumérateur qui contient le même état d’énumération que l’énumérateur actuel.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Clone ( 
   IDiaEnumLineNumbers** ppenum
);
```

#### <a name="parameters"></a>Paramètres
 `ppenum`

à Retourne un objet [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) qui contient un doublon de l’énumérateur. Les numéros de ligne ne sont pas dupliqués, mais uniquement l’énumérateur.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="see-also"></a>Voir aussi
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
