---
title: Nouveautés &apos; dans MSBuild 16,0 | Microsoft Docs
description: Découvrez les fonctionnalités et les propriétés modifiées et mises à jour de MSBuild 16,0, ainsi que des liens vers les notes de publication.
ms.custom: SEO-VS-2020
ms.date: 03/11/2019
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: jmartens
ms.workload:
- multiple
monikerRange: '>=vs-2019'
ms.openlocfilehash: 24b106442456f8bfbd415c4559cba71e463418d5
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99933789"
---
# <a name="whats-new-in-msbuild-160"></a>Nouveautés de MSBuild 16.0

Cet article décrit les fonctionnalités et propriétés mises à jour dans MSBuild 16.0. Pour obtenir des notes de publication détaillées, consultez [ MSBuild 16,0](https://github.com/microsoft/msbuild/releases/tag/v16.0.461.62831).

## <a name="changed-path"></a>Chemin d’accès modifié

 MSBuild est installé dans le dossier *\Bande* sous chaque version de Visual Studio, et les exécutables se trouvent dans le sous-dossier *\Bin* . Par exemple, le chemin d’accès à *MSBuild.exe* installé avec la communauté visual studio 2019 est *C:\Program Files (x86) \Microsoft Visual Studio\2019\Community\MSBuild\Current\Bin\MSBuild.exe* vous pouvez également utiliser le module PowerShell suivant pour rechercher MSBuild : [vssetup. PowerShell](https://github.com/Microsoft/vssetup.powershell).

## <a name="changed-properties"></a>Propriétés modifiées

 Les propriétés MSBuild ci-après ont été mises à jour afin de correspondre au nouveau numéro de version.

- `MSBuildToolsVersion` pour cette version des outils présente la valeur « Current ». La version d’assembly est la même que dans Visual Studio 2017, à savoir 15.1.0.0.

- `VisualStudioVersion` pour cette version des outils présente la valeur « 16.0 »

## <a name="change-waves"></a>Vagues de changements

À compter de MSBuild 16,8, vous pouvez choisir de manière sélective de refuser certaines modifications potentiellement perturbatrices dans MSBuild. Consultez [changer les vagues](change-waves.md).

## <a name="updates"></a>Mises à jour

MSBuild et Visual Studio ciblent maintenant .NET Framework 4.7.2. Si vous souhaitez utiliser de nouvelles fonctionnalités de l’API MSBuild, vous devez également mettre à niveau votre assembly, mais le code existant continuera de fonctionner.

## <a name="see-also"></a>Voir aussi

- [MSBuild](../msbuild/msbuild.md)
