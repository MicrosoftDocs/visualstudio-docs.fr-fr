---
title: 'Comment : modéliser un terrain 3D | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93bce3336a4ccb8731730616d36191fdf83c5241
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47507567"
---
# <a name="how-to-model-3-d-terrain"></a>Procédure : modéliser un terrain 3D
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : modéliser un Terrain 3D](https://docs.microsoft.com/visualstudio/designers/how-to-model-3-d-terrain).  
  
Ce document montre comment utiliser l’éditeur de modèle pour créer un modèle de terrain 3D.  
  
 Ce document illustre ces activités :  
  
-   Ajout d’objets à une scène  
  
-   Sélection des faces et des points  
  
-   Translation des sélections  
  
-   Utilisation de l’outil **Subdiviser la face**  
  
-   Tramage d’un objet dans l’aire de conception  
  
## <a name="creating-a-3-d-terrain-model"></a>Création d’un modèle de terrain 3D  
 Vous pouvez créer un terrain 3D en subdivisant un plan pour obtenir des faces supplémentaires, puis en manipulant leurs sommets pour créer des caractéristiques de terrain intéressantes.  
  
 Lorsque vous avez terminé, le modèle doit se présenter comme suit :  
  
 ![Scène 3D illustrant un modèle de terrain](../designers/media/digit-terrain-model.png "Digit-Terrain-Model")  
  
 Avant de commencer, assurez-vous que la fenêtre **Propriétés** et la **Boîte à outils** sont affichées.  
  
#### <a name="to-create-a-3-d-terrain-model"></a>Pour créer un modèle de terrain 3D  
  
1.  Créez un modèle 3D à utiliser. Pour plus d’informations sur l’ajout d’un modèle à votre projet, consultez la section Getting Started (Prise en main) de l’article [Model Editor (Éditeur de modèle)](../designers/model-editor.md).  
  
2.  Ajoutez un plan à la scène. Dans la **Boîte à outils**, sous **Formes**, sélectionnez **Plan** et déplacez-le vers l’aire de conception.  
  
    > [!TIP]
    >  Pour faciliter l’utilisation de l’objet plan, vous pouvez l’encadrer dans l’aire de conception. En mode **Sélection**, sélectionnez l’objet plan, puis dans la barre d’outils de l’éditeur de modèle, choisissez le bouton **Frame Object (Encadrer l’objet)**.  
  
3.  Passez en mode de sélection de la face. Dans la barre d’outils de l’éditeur de modèle, choisissez **Sélectionner la face**.  
  
4.  Subdivisez le plan. En mode de sélection de la face, choisissez le plan une fois pour l’activer pour la sélection, puis choisissez-le à nouveau pour sélectionner uniquement sa face. Dans la barre d’outils de l’éditeur de modèle, choisissez **Subdiviser la face**. De nouveaux sommets sont ajoutés au plan qui le fractionnent en quatre partitions de même taille.  
  
5.  Créez d’autres subdivisions. Les nouvelles faces étant toujours sélectionnées, choisissez **Subdiviser la face** deux autres fois. Au total, 64 faces sont créées. En créant d’autres subdivisions, vous pouvez donner au terrain encore plus de détails.  
  
6.  Passez en mode de sélection du point. Dans la barre d’outils de l’éditeur de modèle, choisissez **Sélectionner le point**.  
  
7.  Modifiez un point pour créer une caractéristique de terrain. En mode de sélection du point, sélectionnez l’un des points, puis, dans la barre d’outils de l’éditeur de modèle, choisissez l’outil **Translater**. Une zone représentant le point s’affiche sur l’aire de conception. Utilisez la flèche verte pour déplacer la zone et ainsi modifier la hauteur du point. Répétez cette étape pour différents points afin de créer des caractéristiques intéressantes de terrain.  
  
    > [!TIP]
    >  Vous pouvez sélectionner plusieurs points à la fois pour les modifier de manière uniforme.  
  
 Le modèle de terrain est terminé. Voici à nouveau le modèle final, avec l’ombrage Phong appliqué :  
  
 ![Scène 3D illustrant un modèle de terrain](../designers/media/digit-terrain-model.png "Digit-Terrain-Model")  
  
 Vous pouvez utiliser ce modèle de terrain pour montrer l’effet du nuanceur de dégradé décrit dans l’article [Comment : créer un nuanceur de géométrie dégradé](../designers/how-to-create-a-geometry-based-gradient-shader.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de modèle](../designers/model-editor.md)


