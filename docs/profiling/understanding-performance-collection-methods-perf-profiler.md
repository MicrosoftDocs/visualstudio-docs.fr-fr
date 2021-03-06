---
title: Comprendre les méthodes de collecte des performances du profileur
description: En savoir plus sur les méthodes de collecte des données utilisées par les outils du profileur de performances de Visual Studio.
ms.date: 4/30/2020
ms.topic: conceptual
f1_keywords: ''
helpviewer_keywords:
- Performance Profiler, profiling methods
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: '>= vs-2017'
ms.workload:
- multiple
ms.openlocfilehash: f9128700f6ad54f3d92108d92e25e13b9ee4266c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99921868"
---
# <a name="understand-profiler-performance-collection-methods"></a>Comprendre les méthodes de collecte des performances du profileur

Ce document décrit les méthodes de collecte des données utilisées par les outils du profileur de performances de Visual Studio. 

## <a name="sampling"></a>échantillonnage

Les méthodes d’échantillonnage pour le profilage recueillent des données statistiques sur le travail effectué par une application pendant une exécution du profilage. La collecte de données s’effectue en collectant des informations sur l’application à intervalles réguliers ou fréquence d’échantillonnage, par exemple toutes les millisecondes, puis en analysant ces données pour créer un modèle de où le temps a été passé dans l’application. La méthode d’échantillonnage est légère et n’a que peu d’effet sur l’exécution de l’application en cours de profilage. Les outils du profileur de performances qui utilisent la méthode d’échantillonnage incluent l’outil utilisation de l' [UC](../profiling/cpu-usage.md) .

## <a name="instrumentation"></a>Instrumentation

Le profilage par instrumentation recueille des informations détaillées sur le travail effectué par une application pendant une exécution du profilage. La collecte de données est effectuée par des outils qui injectent du code dans un fichier binaire qui capture les informations de minutage ou en utilisant des raccordements de rappel pour collecter et émettre des informations de minutage et de nombre d’appels exacts pendant l’exécution d’une application. La méthode d’instrumentation a une surcharge élevée par rapport aux approches basées sur l’échantillonnage. Les outils du profileur de performances qui utilisent l’instrumentation incluent l’outil d' [allocation d’objets .net](../profiling/dotnet-alloc-tool.md) .