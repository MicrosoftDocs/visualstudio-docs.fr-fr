---
title: Vue Cœurs | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bce1c1ca458b8d06af89c669a76a2a93371fad5a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501197"
---
# <a name="cores-view"></a>Affichage Cœurs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [vue cœurs](https://docs.microsoft.com/visualstudio/profiling/cores-view).  
  
La vue Cœurs montre comment l’exécution du thread a été mappée aux cœurs de processeur logiques. Si vous écrivez des applications serveur, cette vue peut vous aider à optimiser les performances du cache à l’aide de la gestion du pool de thread ou de l’affinité de thread. Elle peut également vous aider à examiner les cas où l’utilisation de l’affinité de thread peut avoir aggravé le problème de migration inter-cœurs. La vue Cœurs comporte deux parties : un graphique et une légende.  
  
 Dans le graphique, les cœurs logiques sont représentés sur l’axe des ordonnées et le temps sur l’axe des abscisses. Chaque thread du graphique a une couleur propre pour que vous puissiez suivre ses mouvements d’un cœur à l’autre dans le temps. Vous pouvez filtrer les threads du graphique en les sélectionnant dans la zone de légende.  
  
 La zone de légende comporte une entrée pour chaque couleur du graphique. Chaque entrée indique la couleur et le nom du thread, le nombre de changements de contexte inter-cœurs, le nombre total de changements de contexte et le pourcentage de changements de contexte inter-cœurs. Les lignes de la légende sont triées selon le nombre de changements de contexte inter-cœurs, dans l’ordre décroissant. La légende répertorie uniquement les threads exécutés pendant l’intervalle de temps affiché.  La liste est mise à jour quand vous effectuez un zoom ou un panoramique.  
  
## <a name="see-also"></a>Voir aussi  
 [Visualiseur concurrentiel](../profiling/concurrency-visualizer.md)   
 [Vue Utilisation](../profiling/utilization-view.md)   
 [Vue Threads](../profiling/threads-view-parallel-performance.md)


