---
description: Cette fonction démarre une séquence de traitement par lots des opérations de contrôle de code source.
title: SccBeginBatch fonction) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: b52b82919b10e58772343aee42cb8723b10d6ca3
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102221650"
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch fonction)
Cette fonction démarre une séquence de traitement par lots des opérations de contrôle de code source. Le [SccEndBatch](../extensibility/sccendbatch-function.md) sera appelé pour terminer le traitement. Ces lots ne peuvent pas être imbriqués.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccBeginBatch(void);
```

### <a name="parameters"></a>Paramètres
 Aucun.

## <a name="return-value"></a>Valeur renvoyée
 L’implémentation du plug-in de contrôle de code source de cette fonction est supposée retourner l’une des valeurs suivantes :

|Value|Description|
|-----------|-----------------|
|SCC_OK|Le traitement des opérations a commencé.|
|SCC_E_UNKNOWNERROR|Échec non spécifique.|

## <a name="remarks"></a>Notes
 Les lots de contrôle de code source sont utilisés pour exécuter les mêmes opérations sur plusieurs projets ou plusieurs contextes. Les lots peuvent être utilisés pour éliminer les boîtes de dialogue redondantes par projet de l’expérience utilisateur pendant une opération par lot. La `SccBeginBatch` fonction et les [SccEndBatch](../extensibility/sccendbatch-function.md) sont utilisés en tant que paire de fonctions pour indiquer le début et la fin d’une opération. Ils ne peuvent pas être imbriqués. `SccBeginBatch` définit un indicateur qui spécifie qu’une opération de traitement par lot est en cours.

 Lorsqu’une opération de traitement par lot est en vigueur, le plug-in de contrôle de code source doit présenter au plus une boîte de dialogue pour toute question à l’utilisateur et appliquer la réponse de cette boîte de dialogue à toutes les opérations suivantes.

## <a name="see-also"></a>Voir aussi
- [Fonctions de l’API du plug-in de contrôle de code source](../extensibility/source-control-plug-in-api-functions.md)
- [SccEndBatch](../extensibility/sccendbatch-function.md)
