---
title: Caractères spéciaux MSBuild │ Microsoft Docs
description: En savoir plus sur les caractères réservés MSBuild pour une utilisation spéciale dans des contextes spécifiques, et quand et comment placer ces caractères dans une séquence d’échappement.
ms.custom: SEO-VS-2020
ms.date: 06/12/2019
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c5db0b870e050a9235f719d83710747101b95c3c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99922531"
---
# <a name="msbuild-special-characters"></a>Caractères spéciaux MSBuild

MSBuild réserve certains caractères pour une utilisation spéciale dans des contextes spécifiques. Pour les utiliser littéralement dans le contexte où ils sont réservés, il vous suffit de les placer dans une séquence d’échappement. Par exemple, un astérisque n’a une signification spéciale que dans les attributs `Include` et `Exclude` d’une définition d’élément, et dans les appels à `CreateItem`. Si vous souhaitez qu’un astérisque apparaisse comme un astérisque dans l’un de ces contextes, vous devez le placer dans une séquence d’échappement. Dans tous les autres contextes, tapez simplement l’astérisque là où vous souhaitez qu’il apparaisse.

 Pour placer un caractère spécial dans une séquence d’échappement, utilisez la syntaxe% \<xx> , où \<xx> représente la valeur hexadécimale ASCII du caractère. Pour plus d’informations, consultez [Comment : échapper des caractères spéciaux dans MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).

## <a name="special-characters"></a>Caractères spéciaux

 Le tableau suivant répertorie les caractères spéciaux MSBuild :

|**Caractère**|**ASCII**|**Utilisation réservée**|
|-------------------|---------------|------------------------|
|%|%25|Référencement des métadonnées|
|$|%24|Référencement des propriétés|
|@|%40|Référencement des listes d’éléments|
|'|%27|Conditions et autres expressions|
|;|%3B|Séparateur de liste|
|?|%3F|Caractère générique pour les noms de fichiers des attributs `Include` et `Exclude`|
|*|%2A|Caractère générique pour les noms de fichiers des attributs `Include` et `Exclude`|

## <a name="see-also"></a>Voir aussi

- [Concepts avancés](../msbuild/msbuild-advanced-concepts.md)
- [Éléments](../msbuild/msbuild-items.md)
