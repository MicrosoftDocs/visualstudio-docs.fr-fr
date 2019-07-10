---
title: Détecter un problème et créer des journaux pour les problèmes MSBuild
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- msbuild logs"
author: mikeblome
ms.author: mblome
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Generate build logs for msbuild projects to collect helpful information when troubleshooting issues.
ms.openlocfilehash: c3db56ac7ea60ce88beae6698c974ac91373ed00
ms.sourcegitcommit: 6f7a740750b2cd17ea2275c3d046caebc9782917
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518195"
---
# <a name="troubleshoot-and-create-logs-for-msbuild-problems"></a>Détecter un problème et créer des journaux pour les problèmes MSBuild

Les procédures suivantes peuvent vous aider à diagnostiquer les problèmes de build dans votre projet Visual Studio et, si nécessaire, créer un journal à envoyer à Microsoft pour examen.

## <a name="a-property-value-is-ignored"></a>Une valeur de propriété est ignorée

Si une propriété de projet semble être définie sur une valeur particulière, mais n’a aucun effet sur la build, procédez comme suit :

1. Ouvrez l’invite de commandes développeur Studio Visual qui correspond à votre version de Visual Studio.
1. Exécutez la commande suivante, après avoir remplacé les valeurs pour votre chemin d’accès vers la solution, la configuration et le nom du projet :

    ```cmd
    msbuild /p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /pp:out.xml MyProject.vcxproj
    ```

    Cette commande génère un fichier de projet msbuild « prétraité » (out.xml). Vous pouvez rechercher une propriété spécifique de ce fichier afin de voir où elle est définie.

La dernière définition d’une propriété est ce que consomme la build. Si la propriété est définie à deux reprises, la deuxième valeur remplace la première. En outre, MSBuild évalue le projet dans plusieurs passes :

- PropertyGroup et importations
- ItemDefinitionGroups
- ItemGroup
- Cibles

Par conséquent, étant donné l’ordre suivant :

```xml
<PropertyGroup>
   <MyProperty>A</MyProperty>
</PropertyGroup>
<ItemGroup>
   <MyItems Include="MyFile.txt"/>
</ItemGroup>
<ItemDefinitionGroup>
  <MyItems>
      <MyMetadata>$(MyProperty)</MyMetadata>
  </MyItems>
</ItemDefinitionGroup>
<PropertyGroup>
   <MyProperty>B</MyProperty>
</PropertyGroup>
```

La valeur de « MyMetadata » pour l’élément de « MyFile.txt » est évaluée sur « B » pendant la build (pas « A » et non vide)

## <a name="incremental-build-is-building-more-than-it-should"></a>La build incrémentielle génère plus qu’il le devrait

Si MSBuild régénère inutilement un projet ou élément de projet, créez un journal de génération détaillé ou binaire. Vous pouvez rechercher le journal du fichier qui a été généré ou compilé inutilement. La sortie ressemble à ceci :

```output
  Task "CL"

  Using cached input dependency table built from:

  F:\test\Project1\Project1\Debug\Project1.tlog\CL.read.1.tlog

  Outputs for F:\TEST\PROJECT1\PROJECT1\PROJECT1.CPP:
  F:\TEST\PROJECT1\PROJECT1\DEBUG\PROJECT1.OBJ
  Project1.cpp will be compiled because F:\TEST\PROJECT1\PROJECT1\PROJECT1.H was modified at 6/5/2019 12:37:09 PM.

  Outputs for F:\TEST\PROJECT1\PROJECT1\PROJECT1.CPP:
  F:\TEST\PROJECT1\PROJECT1\DEBUG\PROJECT1.OBJ

  Write Tracking Logs:
  Debug\Project1.tlog\CL.write.1.tlog
```

Si vous compilez dans l’IDE Visual Studio (avec commentaires relatifs à la Fenêtre Sortie détaillés), la **Fenêtre Sortie** affiche la raison pour laquelle chaque projet n'est pas à jour :

```output
1>------ Up-To-Date check: Project: Project1, Configuration: Debug Win32 ------

1>Project is not up-to-date: build input 'f:\test\project1\project1\project1.h' was modified after the last build finished.
```

## <a name="create-a-binary-msbuild-log"></a>Créer un journal binaire msbuild

1. Ouvrir l’invite de commandes développeur de votre version de Visual Studio
1. À partir de l’invite de commandes, exécutez les commandes suivantes. (N’oubliez pas d’utiliser vos valeurs de projet et de configuration réelles.) :

    ```cmd
    Msbuild /p:Configuration="MyConfiguration";Platform="x86" /bl MySolution.sln
    ```

    ou

    ```cmd
    Msbuild /p:/p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /bl MyProject.vcxproj
    ```

Un fichier Msbuild.binlog sera créé dans le répertoire à partir duquel que vous avez exécuté MSBuild. Vous pouvez l’afficher et le rechercher à l’aide de la [Visionneuse du journal Msbuild structuré](http://www.msbuildlog.com/).

## <a name="create-a-detailed-log"></a>Créer un journal détaillé

1. Dans le menu principal de Visual Studio, accédez à **Outils** > **Options** > **Projets et Solutions** >**Générer et exécuter**.
1. Définissez **Commentaires relatifs à la build du projet MSBuild** sur **Détaillé** dans les deux zones de liste déroulante. La première zone contrôle les commentaires relatifs à la build dans la **Fenêtre Sortie** et la seconde zone contrôle les commentaires relatifs à la build dans le fichier \<projectname\>.log qui est créé dans le chaque répertoire intermédiaire du projet pendant la build.
1. À partir d’une invite de commandes développeur Visual Studio, entrez une de ces commandes, en remplaçant les valeurs de chemin d’accès et de configuration courantes :

    ```cmd
    Msbuild /p:Configuration="MyConfiguration";Platform="x86" /fl MySolution.sln 
    ```

    ou

    ```cmd
    Msbuild /p:/p:SolutionDir="c:\MySolutionDir\";Configuration="MyConfiguration";Platform="Win32" /fl MyProject.vcxproj
    ```

    Un fichier Msbuild.log sera créé dans le répertoire à partir duquel que vous avez exécuté msbuild.