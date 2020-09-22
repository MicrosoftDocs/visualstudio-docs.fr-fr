---
title: exiger-NuGet
description: l’outil devinit requiert-NuGet.
ms.date: 08/28/2020
ms.topic: reference
author: andster
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: c926bc146a7d85d67c49281effe88958f2031695
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90810448"
---
# <a name="require-nuget"></a>exiger-NuGet

`require-nuget`Outil permettant de télécharger l’interface CLI NuGet et de l’ajouter à la variable PATH. L’interface CLI NuGet fournit l’extension complète de la fonctionnalité NuGet pour installer, créer, publier et gérer des packages sans apporter de modifications aux fichiers projet. En savoir plus sur NuGet CLI [ici](https://docs.microsoft.com/nuget/reference/nuget-exe-cli-reference).

## <a name="usage"></a>Usage

Si les `input` Propriétés et `additionalOptions` sont omises ou vides, l’outil suivra le comportement [par défaut](#default-behavior) détaillé ci-dessous.

| Name                                             | Type   | Obligatoire | Valeur                                                                                |
|--------------------------------------------------|--------|----------|--------------------------------------------------------------------------------------|
| **commentaires**                                     | string | Non       | Propriété de commentaires facultative. Non utilisé.                                                |
| [**entrée**](#input)                              | string | Non       | Version de l’interface CLI NuGet à installer. Pour plus d’informations, consultez l' [entrée](#input) ci-dessous. |
| [**additionalOptions**](#additional-options)     | string | Non       | Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.                     |

### <a name="input"></a>Entrée

`input`Est une propriété facultative utilisée pour spécifier la version de l’interface CLI NuGet à installer. Si `input` est omis, la dernière version de l’interface CLI sera installée.

### <a name="additional-options"></a>Options supplémentaires

Non utilisé.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut de l' `require-nuget` outil consiste à installer la dernière version de l’interface CLI NuGet.

## <a name="example-usage"></a>Exemple d’utilisation

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "comments": "A sample dot-devinit file that downloads NuGet CLI and adds to PATH variable.'",
    "run": [
        {
            "tool": "require-nuget",
            "input": "5.5.1",
            "comments": "Installs NuGet for given input version. If no input given, then installs latest."
        }
    ]
}
```