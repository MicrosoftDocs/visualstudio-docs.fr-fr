---
title: Bonnes pratiques pour MSBuild | Microsoft Docs
description: Découvrez les meilleures pratiques pour l’écriture de scripts MSBuild, tels que l’utilisation d’attributs de condition et l’utilisation de caractères génériques.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: 83527ac4b7d16d2cb06c797924c18f2567f12350
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99919188"
---
# <a name="msbuild-best-practices"></a>Bonnes pratiques pour MSBuild

Nous vous recommandons les meilleures pratiques suivantes pour l'écriture de scripts MSBuild :

- Les valeurs de propriété par défaut sont mieux gérées en utilisant l'attribut `Condition` plutôt qu'en déclarant une propriété dont la valeur par défaut peut être substituée sur la ligne de commande. Par exemple, utilisez

```xml
<MyProperty Condition="'$(MyProperty)' == ''">
   MyDefaultValue
</MyProperty>
```

- En général, évitez d’utiliser des caractères génériques lorsque vous sélectionnez des éléments. Spécifiez plutôt les fichiers de manière explicite. En effet, dans la plupart des types de projets, MSBuild développe des caractères génériques à différents moments, par exemple lors de l’ajout ou de la suppression d’éléments, ce qui peut entraîner un comportement inattendu. Une exception est dans les projets de style kit SDK .NET Core, qui traitent correctement les caractères génériques.

## <a name="see-also"></a>Voir aussi

- [Concepts avancés](../msbuild/msbuild-advanced-concepts.md)
