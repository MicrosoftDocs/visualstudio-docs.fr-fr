---
title: Règles de performances de la surveillance des ressources | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2bd11b8b18e5dd4e3f6625b1b269d104a6fd5a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47505627"
---
# <a name="resource-monitoring-performance-rules"></a>Règles de performance de l'analyse de ressource
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [ressource Surveillance des règles de performances](https://docs.microsoft.com/visualstudio/profiling/resource-monitoring-performance-rules).  
  
Les messages liés aux performances de la catégorie Surveillance des ressources fournissent des données supplémentaires sur les performances de votre application. Vous pouvez utiliser ces données pour analyser les problèmes de performances. Ces règles fournissent des informations et sont signalées pour chaque exécution du profilage.  
  
|||  
|-|-|  
|[DA0501 : Consommation d’UC moyenne par le processus en cours de profilage.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Ce message indique le temps, en pourcentage, pendant lequel un processeur a exécuté des instructions à partir de l’application. La valeur signalée correspond à la moyenne de tous les intervalles de mesure pendant lesquels le processus profilé était actif.|  
|[DA0502 : consommation d’UC maximale par le processus à profiler](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Ce message indique le temps maximal, en pourcentage, pendant lequel un processeur a exécuté des instructions à partir de l’application. La valeur signalée correspond à la valeur maximale de tous les intervalles de mesure pendant lesquels le processus profilé était actif.|  
|[DA0503 : Jeu de travail moyen, en octets, pour le processus à profiler](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Ce message indique la quantité moyenne de mémoire physique, en octets, utilisée par le processus pendant que profilage était actif. Cette mesure de la mémoire physique est appelée la plage de travail.|  
|[DA0504 : Jeu de travail maximal, en octets, pour le processus à profiler](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Ce message indique la quantité maximale de mémoire physique, en octets, utilisée par le processus pendant que profilage était actif.|  
|[DA0505 : Nombre moyen d’octets privés alloués pour le processus à profiler](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Ce message indique la quantité moyenne de mémoire virtuelle, en octets, allouée par le processus pendant que profilage était actif. Cette mesure de la mémoire virtuelle est appelée *octets privés*. Les octets privés représentent les emplacements de mémoire virtuelle alloués par le processus et qui ne sont accessibles qu’aux threads actuellement exécutés dans le processus.|  
|[DA0506 : nombre maximal d’octets privés alloués pour le processus en cours de profilage](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Ce message indique la quantité maximale de mémoire virtuelle, en octets privés, allouée par le processus pendant que profilage était actif.|


