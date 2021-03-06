---
description: Récupère le nom de fichier de la dernière erreur de chargement.
title: IDiaDataSource::get_lastError | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 7edce9a2af6c849371360526d617d20738973cba
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102158314"
---
# <a name="idiadatasourceget_lasterror"></a>IDiaDataSource::get_lastError
Récupère le nom de fichier de la dernière erreur de chargement.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_lastError (
   BSTR* pRetVal
);
```

#### <a name="parameters"></a>Paramètres
 pRetVal

à Retourne une chaîne qui contient le nom de fichier. pdb associé à la dernière erreur de chargement.

## <a name="return-value"></a>Valeur renvoyée
 Retourne le dernier code d’erreur provoqué par une opération de chargement. Retourne `E_INVALIDARG` si le `pRetVal` paramètre a la valeur `NULL` .

## <a name="example"></a>Exemple

```C++
BSTR    fileName;
HRESULT errorCode = pSource->get_lastError( &fileName );
```

## <a name="see-also"></a>Voir aussi
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
