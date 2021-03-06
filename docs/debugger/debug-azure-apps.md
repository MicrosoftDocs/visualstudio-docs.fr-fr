---
title: Déboguer les services Azure | Microsoft Docs
description: Vous pouvez déboguer les services Azure avec Visual Studio. Utilisez les liens de cet article pour en savoir plus sur les différentes façons de procéder.
ms.custom: SEO-VS-2020
ms.date: 09/14/2018
ms.topic: how-to
helpviewer_keywords:
- debugger
ms.assetid: 3d434de3-ee5f-419d-9a94-ac4ac02d635b
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- azure
ms.openlocfilehash: a77f1291621e84eb2e13075a791e9c6735447137
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99857620"
---
# <a name="debug-azure-services-in-visual-studio"></a>Déboguer les services Azure dans Visual Studio

Vous pouvez utiliser Visual Studio pour déboguer les services Azure dans différents scénarios :

Pour déboguer une application de production hébergée dans :

- Azure App Service, à l’aide de Visual Studio Enterprise, consultez [Déboguer des applications ASP.net en direct à l’aide du débogueur de capture instantanée](../debugger/debug-live-azure-applications.md).

- Azure App Service ou Service Fabric, à l’aide d’Application Insights, consultez [captures instantanées de débogage sur les exceptions dans les applications .net](/azure/application-insights/app-insights-snapshot-debugger).

- Machine virtuelle Azure ou groupe de machines virtuelles identiques Azure, consultez [Déboguer des machines virtuelles azure ASP.net et des groupes de machines virtuelles identiques Azure à l’aide du débogueur de capture instantanée](../debugger/debug-live-azure-virtual-machines.md).

- Service Azure Kubernetes, consultez [Déboguer des services Azure Kubernetes en direct ASP.net à l’aide de l’débogueur de capture instantanée](../debugger/debug-live-azure-kubernetes.md).

Pour déboguer à distance :

- ASP.NET sur IIS (Azure App Service ou sur une machine virtuelle Azure), consultez [débogage distant ASP.net sur Azure](remote-debugging-azure.md).

- ASP.NET sur Azure Service Fabric, consultez [déboguer une application de service fabric à distance](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)

## <a name="see-also"></a>Voir aussi

- [Débogage dans Visual Studio](../debugger/index.yml)
