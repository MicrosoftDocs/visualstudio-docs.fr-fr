---
title: Nœuds utilitaires | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff732221-b731-424c-ad5b-82ef5f21dff5
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fa242e6c2f609c8ac6214fcbd20d210f7c794b77
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502178"
---
# <a name="utility-nodes"></a>Nœuds utilitaires
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [nœuds utilitaires](https://docs.microsoft.com/visualstudio/designers/utility-nodes).  
  
Dans le concepteur de nuanceur, les nœuds utilitaires représentent des calculs de nuanceur communs et utiles qui ne s’inscrivent pas parfaitement dans les autres catégories. Certains nœuds utilitaires effectuent des opérations simples comme l’ajout de vecteurs ou le choix conditionnel de résultats, tandis que d’autres effectuent des opérations complexes telles que le calcul des contributions d’éclairage en fonction des modèles d’éclairage les plus utilisés.  
  
## <a name="utility-node-reference"></a>Informations de référence des nœuds utilitaires  
  
|Nœud|Détails|Properties|  
|----------|-------------|----------------|  
|**Ajouter un vecteur**|Crée un vecteur en ajoutant les entrées spécifiées ensemble.<br /><br /> **Entrée :**<br /><br /> `Vector` : `float`, `float2` ou `float3`<br /> Valeurs pour lesquelles procéder à des ajouts.<br /><br /> `Value to Append`: `float`<br /> Valeur à ajouter.<br /><br /> **Sortie :**<br /><br /> `Output` : `float2`, `float3` ou `float4` en fonction du type d’entrée `Vector`<br /> Nouveau vecteur.|Aucun.|  
|**Fresnel**|Calcule la courbe décroissante de Fresnel en fonction de la normale à la surface spécifiée.<br /><br /> La valeur de la courbe décroissante de Fresnel exprime le degré auquel la normale à la surface du pixel actuel coïncide avec le vecteur de la vue. Lorsque les vecteurs sont alignés, le résultat de la fonction est 0 ; le résultat augmente à mesure que les vecteurs sont moins semblables, et il atteint sa valeur maximale lorsque les vecteurs sont orthogonaux. Vous pouvez l’utiliser pour rendre un effet plus ou moins apparent en fonction de la relation existant entre l’appareil photo et l’orientation du pixel actuel.<br /><br /> **Entrée :**<br /><br /> `Surface Normal`: `float3`<br /> Normale à la surface du pixel actuel, définie dans l’espace tangent du pixel actuel. Vous pouvez l’utiliser pour compromettre la normale à la surface apparente, comme dans le mappage des normales.<br /><br /> **Sortie :**<br /><br /> `Output`: `float`<br /> Réflectivité du pixel actuel.|**Exposant**<br /> Exposant utilisé pour calculer la courbe décroissante de Fresnel.|  
|**If**|Choisit de façon conditionnelle l’un des trois résultats potentiels par composant. La condition est définie par la relation existant entre deux autres entrées spécifiées.<br /><br /> Pour chaque composant du résultat, le composant correspondant de l’un des trois résultats potentiels est choisi, en fonction de la relation existant entre les composants correspondants des deux premières entrées.<br /><br /> **Entrée :**<br /><br /> `X` : `float`, `float2`, `float3` ou `float4`<br /> Valeur de gauche à comparer.<br /><br /> `Y` : même type que l’entrée `X`<br /> Valeur de droite à comparer.<br /><br /> `X > Y` : même type que l’entrée `X`<br /> Valeurs qui sont choisies lorsque `X` est supérieur à `Y`.<br /><br /> `X = Y` : même type que l’entrée `X`<br /> Valeurs qui sont choisies lorsque `X` est égal à `Y`.<br /><br /> `X < Y` : même type que l’entrée `X`<br /> Valeurs qui sont choisies lorsque `X` est inférieur à `Y`.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Résultat choisi par composant.|Aucun.|  
|**Lambert**|Calcule la couleur du pixel actuel en fonction du modèle d’éclairage Lambert, à l’aide de la normale à la surface spécifiée.<br /><br /> Cette couleur est la somme des contributions de couleur ambiante et d’éclairage diffus dans des conditions d’éclairage direct. La couleur ambiante est proche de la contribution totale d’éclairage indirect, mais semble plate et terne sans le recours à un éclairage supplémentaire. Un éclairage diffus permet d’ajouter une forme et une profondeur à un objet.<br /><br /> **Entrée :**<br /><br /> `Surface Normal`: `float3`<br /> Normale à la surface du pixel actuel, définie dans l’espace tangent du pixel actuel. Vous pouvez l’utiliser pour compromettre la normale à la surface apparente, comme dans le mappage des normales.<br /><br /> `Diffuse Color`: `float3`<br /> Couleur diffuse du pixel actuel, en général la **Couleur du point**. Si aucune entrée n’est fournie, la valeur par défaut est le blanc.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Couleur diffuse du pixel actuel.|Aucun.|  
|**Vecteur de masque**|Masque les composants du vecteur spécifié.<br /><br /> Vous pouvez l’utiliser pour supprimer des canaux de couleur spécifiques d’une valeur de couleur ou pour éviter que des composants spécifiques n’affectent les calculs suivants.<br /><br /> **Entrée :**<br /><br /> `Vector`: `float4`<br /> Vecteur à masquer.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Vecteur masqué.|**Rouge / X**<br /> **False** pour masquer le composant rouge (x). **True** dans le cas contraire.<br /><br /> **Vert / Y**<br /> **False** pour masquer le composant vert (y). **True** dans le cas contraire.<br /><br /> **Bleu / Z**<br /> **False** pour masquer le composant bleu (z). **True** dans le cas contraire.<br /><br /> **Alpha / W**<br /> **False** pour masquer le composant alpha (w). **True** dans le cas contraire.|  
|**Vecteur de réflexion**|Calcule le vecteur de réflexion pour le pixel actuel dans l’espace tangent, en fonction de la position de l’appareil photo.<br /><br /> Vous pouvez l’utiliser pour calculer les réflexions, les coordonnées de carte cubique et les contributions d’éclairage spéculaire.<br /><br /> **Entrée :**<br /><br /> `Tangent Space Surface Normal`: `float3`<br /> Normale à la surface du pixel actuel, définie dans l’espace tangent du pixel actuel. Vous pouvez l’utiliser pour compromettre la normale à la surface apparente, comme dans le mappage des normales.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Vecteur de réflexion.|Aucun.|  
|**Spéculaire**|Calcule la contribution d’éclairage spéculaire en fonction du modèle d’éclairage Phong, à l’aide de la normale à la surface spécifiée.<br /><br /> L’éclairage spéculaire donne une apparence brillante et réfléchissante à un objet, par exemple, l’eau, le plastique ou les métaux.<br /><br /> **Entrée :**<br /><br /> `Surface Normal`: `float3`<br /> Normale à la surface du pixel actuel, définie dans l’espace tangent du pixel actuel. Vous pouvez l’utiliser pour compromettre la normale à la surface apparente, comme dans le mappage des normales.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Contribution de couleur des surbrillances spéculaires.|Aucun.|


