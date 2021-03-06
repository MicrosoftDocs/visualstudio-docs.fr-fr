---
title: Paramètres internationaux dans la boîte de dialogue Options
description: Découvrez comment utiliser la page Paramètres internationaux de la section environnement pour modifier la langue par défaut lorsque plusieurs versions linguistiques de l’IDE sont installées.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.InternationalSettings
- VS.ToolsOptionsPages.Environment.International_Settings
- VS.Environment.International Settings
helpviewer_keywords:
- International Settings dialog box
- languages, environment settings
- Options dialog box, international settings
- languages, specifying default
ms.assetid: e3a8815c-6995-4099-8e88-34f91fad55b2
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: d9dc19c69bf99ba6f66648f396468ff36444eb3f
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99852269"
---
# <a name="options-dialog-box-environment--international-settings"></a>Options, boîte de dialogue : paramètres internationaux de l’environnement \>

La page Paramètres internationaux vous permet de changer la langue par défaut quand vous avez plusieurs versions linguistiques de l’environnement de développement intégré (IDE) installé sur votre ordinateur. Vous pouvez accéder à cette boîte de dialogue en sélectionnant **Options** dans le menu **Outils**, puis en choisissant **Paramètres internationaux** dans le dossier **Environnement**.

**Langage**

Répertorie les langues disponibles pour les versions linguistiques du produit installé. Si plusieurs versions linguistiques de produits ou si une installation mixte de versions linguistiques de produits partagent le même environnement, la langue sélectionnée est changée en **Identique à Microsoft Windows**.

> [!CAUTION]
> Dans un système où plusieurs langues sont installées, les outils de génération Visual C++ (cl.exe, link.exe, nmake.exe, bscmake.exe et les fichiers associés) ne sont pas affectés par ce paramètre. Ces outils utilisent la version pour la dernière langue installée. Les outils de génération pour la langue précédemment installée sont remplacés, car Visual C++ Build Tools n’utilise pas le modèle de DLL satellite.

### <a name="see-also"></a>Voir aussi

- [Installer des modules linguistiques](../../install/install-visual-studio.md#step-6---install-language-packs-optional)
