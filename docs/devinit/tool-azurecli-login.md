---
title: azurecli-login
description: devinit outil azurecli-login.
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
ms.openlocfilehash: 94f713ed972e93b761cf7dcdafcfd92e5498d982
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99944970"
---
# <a name="azurecli-login"></a>azurecli-login

L' `azurecli-login` outil est utilisé pour se connecter à Azure Active Directory via [Azure CLI](/cli/azure/authenticate-azure-cli?preserve-view=true&view=azure-cli-latest). Cet outil utilise la commande Azure CLI : `az login --use-device-code` , pour terminer la connexion, vous devez suivre les instructions affichées sur la console.

## <a name="usage"></a>Usage

Si les deux propriétés sont omises ou vides, l’outil suivra le comportement [par défaut](#default-behavior) détaillé ci-dessous.

| Nom                                             | Type   | Obligatoire | Valeur                                                                          |
|--------------------------------------------------|--------|----------|--------------------------------------------------------------------------------|
| **commentaires**                                     | string | Non       | Propriété de commentaires facultative. Non utilisé.                                          |
| [**entrée**](#input)                              | string | Non       | Non utilisé. Pour plus d’informations, consultez l' [entrée](#input) ci-dessous.                               |
| [**additionalOptions**](#additional-options)     | string | Non       | Non utilisé. Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.     |

### <a name="input"></a>Entrée

Non utilisé.

### <a name="additional-options"></a>Options supplémentaires

Non utilisé.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut de l' `azurecli-login` outil consiste à installer la dernière version de la Azure CLI et à l’ajouter au `PATH` .

## <a name="example-usage"></a>Exemple d’utilisation
Vous trouverez ci-dessous un exemple de la façon d’exécuter `azurecli-login` à l’aide d’un `.devinit.json` .

#### <a name="devinitjson-that-will-trigger-azure-login"></a>.devinit.jssur qui déclenchera la connexion à Azure :

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "tool": "azurecli-login"
        }
    ]
}
```