---
title: ParameterGroup, élément | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ParameterGroup> element [MSBuild]
- ParameterGroup element [MSBuild]
ms.assetid: c3275e69-a427-4889-bc1d-51bff2c285fa
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d3b72a524e9c68d46db4d032ab7ce243a3ea14e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47504347"
---
# <a name="parametergroup-element"></a>ParameterGroup, élément
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [ParameterGroup élément](https://docs.microsoft.com/visualstudio/msbuild/parametergroup-element).  
  
  
Contient une liste facultative de paramètres qui seront présents sur la tâche générée par un `UsingTask``TaskFactory`. Pour plus d’informations, consultez [UsingTask, élément (MSBuild)](../msbuild/usingtask-element-msbuild.md).  
  
 \<Project>  
 \<UsingTask>  
 \<ParameterGroup>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ParameterGroup />  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
  
|Élément|Description|  
|-------------|-----------------|  
|[Paramètre](../msbuild/parameter-element.md)|Contient des informations sur un paramètre spécifique pour une tâche générée par un `UsingTask``TaskFactory`. Le nom de l’élément est le nom du paramètre.|  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|Permet d’inscrire des tâches dans [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]. Un projet peut ne contenir aucun élément `UsingTask` ou en contenir plusieurs.|  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser l'élément `ParameterGroup`.  
  
```  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
             ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)   
 [Référence du schéma de fichier projet](../msbuild/msbuild-project-file-schema-reference.md)


