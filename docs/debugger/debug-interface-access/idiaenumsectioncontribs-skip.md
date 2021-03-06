---
description: Ignore un nombre spécifié de contributions de section dans une séquence d’énumération.
title: IDiaEnumSectionContribs::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 345aa9219071a64fdd497a9e5409ee7dab3068ad
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102159299"
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
Ignore un nombre spécifié de contributions de section dans une séquence d’énumération.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Skip( 
   ULONG celt
);
```

#### <a name="parameters"></a>Paramètres
 `celt`

dans Nombre de contributions de section dans la séquence d’énumération à ignorer.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` ; sinon, retourne `S_FALSE` s’il n’y a plus de contribution de section à ignorer.

## <a name="see-also"></a>Voir aussi
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
