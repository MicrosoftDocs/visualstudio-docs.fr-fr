---
title: Comment exécuter manuellement l’analyse du code hérité pour le code managé
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- code analysis, running
ms.assetid: 5086d228-f92e-4515-9708-c5b89b9e9a03
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 38c3de83dc0df39314ad236f647c69bbe614b75d
ms.sourcegitcommit: 48e93538f1e352fc1f972b642bb5fcce2f6834a2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2020
ms.locfileid: "85371818"
---
# <a name="how-to-run-legacy-code-analysis-manually-for-managed-code"></a>Comment : exécuter manuellement l’analyse du code hérité pour le code managé
L’outil d’analyse du code vous fournit des informations sur les erreurs possibles dans votre code source. Vous pouvez exécuter l’analyse du code automatiquement avec chaque génération d’un projet de code, et vous pouvez également exécuter l’analyse du code manuellement. Les règles qui sont vérifiées lors de l’exécution de l’analyse du code sont spécifiées dans la page analyse du code des pages de propriétés du projet. Pour plus d’informations, consultez [Comment : configurer l’analyse du code pour un projet de code managé](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).

## <a name="to-run-code-analysis-manually"></a>Pour exécuter l’analyse du code manuellement

1. Si vous utilisez Visual Studio 2019 version 16,5 ou ultérieure, exécutez la commande suivante sur l’invite de commandes avant de démarrer Visual Studio :

```
set EnableLegacyCodeAnalysis = true
```

2. Dans **Explorateur de solutions**, cliquez sur le projet.

3. Dans le menu **analyser** , cliquez sur **exécuter l’analyse du code sur** le nom du *projet*.
