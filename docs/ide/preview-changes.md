---
title: Aperçu des modifications du code
description: Découvrez comment utiliser la fenêtre Aperçu des modifications pour passer en revue les modifications qui vont être apportées à votre projet avant de les accepter.
ms.custom: SEO-VS-2020
ms.date: 12/16/2016
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: jmartens
f1_keywords:
- vs.codefix.previewchanges
ms.workload:
- multiple
ms.openlocfilehash: 55a53e60ffa05892531257871ede89381e7fd4e2
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99909013"
---
# <a name="preview-changes-window"></a>Fenêtre Aperçu des modifications

Quand vous utilisez différents outils de *Refactorisation* ou *Actions rapides* dans Visual Studio, il est souvent possible d’afficher un aperçu des modifications qui vont être apportées à votre projet avant de les accepter. Cette opération s’effectue dans la fenêtre **Aperçu des modifications**.  Par exemple, voici une fenêtre **Aperçu des modifications** montrant ce qui sera modifié pendant une refactorisation de changement de nom dans un projet C# :

![Aperçu des modifications](media/previewchanges.png)

La moitié supérieure de la fenêtre affiche les lignes spécifiques qui seront modifiées, chacune avec une case à cocher. Vous pouvez cocher ou décocher chaque case si vous souhaitez appliquer de manière sélective la refactorisation uniquement à des lignes spécifiques.

La moitié inférieure de la fenêtre présente le code mis en forme du projet qui sera modifié, avec les zones affectées mises en surbrillance. Quand vous sélectionnez la ligne spécifique dans la partie supérieure de la fenêtre, la ligne correspondante dans la partie inférieure est mise en surbrillance. Cela vous permet d’accéder rapidement à la ligne appropriée et de voir le code environnant.

Après avoir vérifié les modifications, cliquez sur le bouton **Appliquer** pour valider ces modifications, ou cliquez sur le bouton **Annuler** pour laisser les choses telles qu’elles étaient.

## <a name="see-also"></a>Voir aussi

- [Refactorisation dans Visual Studio](../ide/refactoring-in-visual-studio.md)
- [Actions rapides](../ide/quick-actions.md)
