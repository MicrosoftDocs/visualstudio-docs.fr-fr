---
title: require-dotnetframeworksdk
description: l’outil devinit requiert-dotnetframeworksdk.
ms.date: 11/20/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jmartens
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: 5a4d68119ceb21553d7db1f6384904579003ce92
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99937150"
---
# <a name="require-dotnetframeworksdk"></a>require-dotnetframeworksdk

L' `require-dotnetframeworksdk` outil est utilisé pour installer le [Kit de développement logiciel (SDK) .NET Framework](https://dotnet.microsoft.com/) par le biais des [programmes d’installation fournis](https://dotnet.microsoft.com/download/visual-studio-sdks).

## <a name="usage"></a>Usage

Si les `input` Propriétés et `additionalOptions` sont omises ou vides, l’outil suivra le comportement [par défaut](#default-behavior) détaillé ci-dessous.

| Nom                                             | Type   | Obligatoire  | Valeur                                                                                    |
|--------------------------------------------------|--------|-----------|------------------------------------------------------------------------------------------|
| **commentaires**                                     | string | Non        | Propriété de commentaires facultative. Non utilisé.                                                    |
| [**entrée**](#input)                              | string | Non        | Version du kit de développement logiciel (SDK) .NET Framework à installer. Pour plus d’informations, consultez l' [entrée](#input) ci-dessous. |
| [**additionalOptions**](#additional-options)     | string | Non        | Non utilisé. Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.               |

### <a name="input"></a>Entrée

La `input` propriété est utilisée pour spécifier la version du kit de développement logiciel (SDK) .NET Framework à installer. Une liste de versions est disponible sur le [site DotNet-Framework](https://dotnet.microsoft.com/download/visual-studio-sdks).

### <a name="additional-options"></a>Options supplémentaires

Non utilisé.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut de l' `require-dotnetframeworksdk` outil consiste à installer la dernière version. Consultez les [programmes d’installation fournis](https://dotnet.microsoft.com/download/visual-studio-sdks) pour la version la plus récente.

## <a name="example-usage"></a>Exemple d’utilisation
Vous trouverez ci-dessous des exemples d’exécution à `require-dotnetframeworksdk` l’aide d’un `.devinit.json` .

#### <a name="devinitjson-that-will-install-the-latest-net-framework"></a>.devinit.jssur qui installe le dernier .NET Framework :
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "tool": "require-dotnetframeworksdk"
        }
    ]
}
```

#### <a name="devinitjson-that-will-install-a-specific-version-of-the-net-framework"></a>.devinit.jssur qui installe une version spécifique du .NET Framework :
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "tool": "require-dotnetframeworksdk",
            "input": "4.8.0"
        }
    ]
}
```