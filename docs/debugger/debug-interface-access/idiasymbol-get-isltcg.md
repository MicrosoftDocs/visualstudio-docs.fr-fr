---
description: Récupère un indicateur qui spécifie si le module (compiland) a été lié au commutateur de l’éditeur de liens/LTCG (génération de code durant l’édition de liens) (/CPP/Build/Reference/LTCG-Link-Time-Code-Generation), qui facilite l’optimisation de l’ensemble du programme.
title: IDiaSymbol::get_isLTCG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 1b8306dabe6533287d7d28841ea76f2d6478e4a3
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102160812"
---
# <a name="idiasymbolget_isltcg"></a>IDiaSymbol::get_isLTCG
Récupère un indicateur qui spécifie si le [compiland](../../debugger/debug-interface-access/compiland.md) a été lié au commutateur de l’éditeur de liens [/LTCG (génération de code durant l’édition de liens)](/cpp/build/reference/ltcg-link-time-code-generation), qui facilite l’optimisation de l’ensemble du programme. Ce commutateur s’applique uniquement au code managé.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_iSLTCG(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Paramètres
 pFlag

à Retourne `TRUE` si le `compiland` a été lié avec le commutateur de l’éditeur de liens/LTCG ; sinon, retourne `FALSE` .

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` ; sinon, retourne `S_FALSE` ou un code d’erreur.

> [!NOTE]
> Une valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.

## <a name="requirements"></a>Configuration requise

|Condition requise|Description|
|-----------------|-----------------|
|En-tête :|dia2.h|
|Version :|DIA SDK v 8.0|

## <a name="see-also"></a>Voir aussi
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
