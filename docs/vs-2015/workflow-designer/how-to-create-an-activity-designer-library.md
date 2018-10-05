---
title: 'Comment : créer une bibliothèque ActivityDesigner | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 128c36a4aca22cb2da08c3d88162fed658f27de4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47495232"
---
# <a name="how-to-create-an-activity-designer-library"></a>Procédure : créer une bibliothèque ActivityDesigner
Les concepteurs d'activités personnalisées vous permettent de créer une interface utilisateur pour une activité standard ou personnalisée. Vous contrôlez la complexité de l'interface utilisateur et avez la possibilité de créer plusieurs concepteurs d'activités pour une activité. Ce scénario vous permet de créer des concepteurs adaptés pour plusieurs audiences.  
  
### <a name="to-create-an-activity-designer-library"></a>Pour créer une bibliothèque ActivityDesigner  
  
1.  Démarrez [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2.  Sur le **fichier** menu, pointez sur **New**, puis sélectionnez **projet...** Pour ouvrir le **nouveau projet** boîte de dialogue.  
  
3.  Dans le **Types de projets** volet, sélectionnez **Workflow** à partir de le le **Visual C#** ou **Visual Basic** regroupements en fonction de votre choix langage.  
  
4.  Dans le **modèles** volet, sélectionnez **Bibliothèque ActivityDesigner**.  
  
5.  Dans le **nom** , entrez un nom descriptif pour votre projet pour faciliter l’identification.  
  
6.  Dans le **emplacement** , entrez le répertoire dans lequel vous souhaitez enregistrer votre projet, ou cliquez sur **Parcourir** pour naviguer jusqu'à lui.  
  
7.  Dans le **Solution** zone, tapez un nom descriptif pour votre solution, puis cliquez sur **OK**.  
  
    > [!NOTE]
    >  Si vous souhaitez ajouter une application de console de workflow à une solution existante, ouvrez cette solution dans [!INCLUDE[vs2010](../includes/vs2010-md.md)], cliquez avec le bouton droit sur la solution dans **l’Explorateur de solutions**, puis sélectionnez **ajouter**, puis **Nouveau projet...** Pour ouvrir le **nouveau projet** boîte de dialogue. Procédez comme décrit ci-dessus dans cette procédure.  
  
8.  Le modèle de projet crée une définition de concepteur d'activités en XAML et le fichier d'implémentation code-behind dans le code source. [!INCLUDE[wfd1](../includes/wfd1-md.md)] s'ouvre et affiche la zone de dessin pour votre concepteur d'activités.  
  
9. Faites glisser [!INCLUDE[avalon1](../includes/avalon1-md.md)] des contrôles de la **boîte à outils** vers l’aire de conception pour les utiliser dans votre concepteur d’activités personnalisées.  Pour obtenir un exemple montrant comment implémenter un concepteur d’activités personnalisées, consultez [Comment : créer un concepteur d’activités personnalisé](http://msdn.microsoft.com/library/2f3aade6-facc-44ef-9657-a407ef8b9b31).  
  
    > [!WARNING]
    >  Concepteurs d’activités personnalisées peuvent être utilisés pour les activités personnalisées ainsi par défaut [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]activités.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un projet de flux de travail](../workflow-designer/creating-a-workflow-project.md)