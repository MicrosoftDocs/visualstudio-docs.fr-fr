---
title: WizardExtension, élément (modèles Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardExtension
helpviewer_keywords:
- WizardExtension element [Visual Studio Templates]
- <WizardExtension> element [Visual Studio Templates]
ms.assetid: d54b01c1-50f5-4b65-828c-686e2321cc8c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7b8a9a788fb2c229791e0ca099e307e6279fd3e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47507878"
---
# <a name="wizardextension-element-visual-studio-templates"></a>WizardExtension, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [WizardExtension, élément (modèles Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/wizardextension-element-visual-studio-templates).  
  
Contient les éléments de l’inscription pour la personnalisation de l’Assistant modèle.  
  
 \<VSTemplate >  
 ...  
 \<WizardExtension >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<WizardExtension>  
    <Assembly>... </Assembly>  
    <FullClassName>... </FullClassName>  
</WizardExtension>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
  
|Élément|Description|  
|-------------|-----------------|  
|[Assembly](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|Élément requis.<br /><br /> Spécifie le nom ou le nom fort d’un assembly qui s’affiche dans le global assembly cache. Il doit y avoir au moins un `Assembly` élément dans un `WizardExtension` élément.|  
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|Élément requis.<br /><br /> Le nom qualifié complet de la classe qui implémente le `IWizard` interface. Il doit y avoir au moins un `FullClassName` élément dans un `WizardExtension` élément.|  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Contient toutes les métadonnées pour le modèle de projet, un modèle d’élément ou un starter kit.|  
  
## <a name="remarks"></a>Notes  
 `WizardExtension` est un élément enfant facultatif de `VSTemplate`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre les métadonnées pour le modèle de projet standard pour une [!INCLUDE[csprcs](../includes/csprcs-md.md)] application de Windows.  
  
```  
<VSTemplate Version="3.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyTemplate</Name>  
        <Description>Template using IWizard extension</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
    <WizardExtension>  
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>  
        <FullClassName>MyWizard.CustomWizard</FullClassName>  
    </WizardExtension>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Guide pratique pour utiliser des Assistants avec des modèles de projet](../extensibility/how-to-use-wizards-with-project-templates.md)
