---
description: Récupère le numéro de version principale du serveur frontal.
title: IDiaSymbol::get_frontEndMajor | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMajor method
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: bf5bc125b00fa8194475c9f6101e697dbf66062a
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102162165"
---
# <a name="idiasymbolget_frontendmajor"></a>IDiaSymbol::get_frontEndMajor
Récupère le numéro de version principale du serveur frontal.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_frontEndMajor ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Paramètres
 `pRetVal`

à Retourne le numéro de version principale du serveur frontal. Consultez la section Notes.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` ; sinon, retourne `S_FALSE` ou un code d’erreur.

> [!NOTE]
> Une valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.

## <a name="remarks"></a>Notes
 Un compilateur se compose généralement de deux éléments principaux : le serveur frontal (l’analyseur), qui gère l’analyse du code source dans un formulaire intermédiaire et un back end (générateur de code), qui convertit le formulaire intermédiaire en assembly. Il n’est pas rare que le serveur frontal ait une version différente de celle du back end.

 Un numéro de version frontale ou de back end est composé de trois parties : \<major> . \<minor> . \<build> , où \<major> est le numéro de version principale, \<minor> est le numéro de version mineure et \<build> est le numéro de Build. Par exemple, 13.10.3077.

## <a name="requirements"></a>Configuration requise

|Condition requise|Description|
|-----------------|-----------------|
|En-tête :|dia2.h|
|Version :|DIA SDK v 7.0|

## <a name="see-also"></a>Voir aussi
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
