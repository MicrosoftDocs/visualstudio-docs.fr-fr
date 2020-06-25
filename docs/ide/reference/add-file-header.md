---
title: Ajouter un en-tête de fichier
ms.date: 06/08/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 24b0905eed167a99f8a75086c9b5ec6cbbdd8b6a
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85290346"
---
# <a name="add-debuggerdisplay-attribute"></a>Ajouter l’attribut DebuggerDisplay

Cette génération de code s’applique à :

- C#

- Visual Basic

**Ce qui suit :** Ajoutez des en-têtes de fichier aux fichiers, projets et solutions existants à l’aide d’un [EditorConfig](https://docs.microsoft.com/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).

Dans les **cas suivants :** Vous souhaitez ajouter facilement un en-tête de fichier aux fichiers, projets et solutions.

**Pourquoi :** Votre équipe vous demande d’inclure un en-tête de fichier à des fins de copyright. 

## <a name="how-to"></a>Procédures

1. Ajoutez un [EditorConfig](https://docs.microsoft.com/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project) à un projet ou à une solution si vous n’en avez pas déjà un.

2. Ajoutez la règle suivante à votre fichier EditorConfig : *file_header_template*.

3. Définissez la valeur de la règle pour qu’elle corresponde au texte d’en-tête que vous souhaitez appliquer.

    ![Règle d’en-tête de fichier EditorConfig](media/add-file-header-rule.png)

> [!NOTE]
> Vous ne pouvez pas avoir de multilignes explicites dans un EditorConfig et vous devrez utiliser le caractère de saut de ligne UNIX pour insérer de nouvelles lignes.

4. Placez le signe insertion sur la première ligne de n’importe quel fichier C# ou Visual Basic.

5. Appuyez sur **CTRL** + **.** pour afficher le menu **Actions rapides et refactorisations**.

6. Sélectionnez **Ajouter un en-tête de fichier**. 

    ![Règle d’en-tête de fichier EditorConfig](media/add-file-header.png)

7. Pour appliquer l’en-tête de fichier à la totalité d’un projet ou d’une solution, sélectionnez **projet** ou **solution** sous l’option **corriger toutes les occurrences dans :** .

8. La boîte de dialogue **corriger toutes les occurrences** s’ouvre, dans laquelle vous pouvez afficher un aperçu des modifications.

    ![Boîte de dialogue corriger toutes les occurrences](media/file-header-preview-changes.png)

8. Sélectionnez **appliquer** pour appliquer les modifications.

## <a name="see-also"></a>Voir aussi

- [Génération de code](../code-generation-in-visual-studio.md)
- [Aperçu des modifications](../../ide/preview-changes.md)