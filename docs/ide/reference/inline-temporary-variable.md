---
title: Remplacer une variable temporaire par sa valeur
description: Découvrez comment utiliser le menu actions rapides et refactorisations pour supprimer une variable temporaire et la remplacer par sa valeur à la place.
ms.custom: SEO-VS-2020
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jmartens
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ebe062d5dd569ae1d2162ea7334f91d8b82decdb
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99852373"
---
# <a name="inline-a-temporary-variable-refactoring"></a>Inclure une variable temporaire (refactorisation)

Cette refactorisation s’applique à :

- C#

- Visual Basic

**Quoi :** vous permet de supprimer une variable temporaire et de la remplacer par sa valeur.

**Quand :** l’utilisation de la variable temporaire complique la lecture du code.

**Pourquoi :** la suppression d’une variable temporaire peut faciliter la lecture du code.

## <a name="how-to"></a>Procédures

1. Mettez en surbrillance ou placez le curseur dans la variable temporaire à inclure :

   - C# :

       ![Code mis en surbrillance (C#)](media/inline-highlight-cs.png)

   - Visual Basic :

       ![Code mis en surbrillance (Visual Basic)](media/inline-highlight-vb.png)

2. Effectuez ensuite l'une des opérations suivantes :

   - **Clavier**
      - Appuyez sur **CTRL** + **.** pour afficher le menu **Actions rapides et refactorisations**.
   - **Souris**
      - Cliquez avec le bouton droit sur le code et sélectionnez le menu **Actions rapides et refactorisations**.

3. Sélectionnez **Inclure une variable temporaire** dans la fenêtre contextuelle d’aperçu.

   La variable est supprimée et ses utilisations sont remplacées par la valeur de la variable.

   - C# :

      ![Résultat de l’action Inclure (C#)](media/inline-result-cs.png)

   - Visual Basic :

      ![Résultat de l’action Inclure (Visual Basic)](media/inline-result-vb.png)

## <a name="see-also"></a>Voir aussi

- [Refactorisation](../refactoring-in-visual-studio.md)
