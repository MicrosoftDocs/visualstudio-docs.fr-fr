---
title: 'Comment : ouvrir des fichiers texte en tant que classeurs par programmation'
description: Découvrez comment vous pouvez utiliser Visual Studio pour ouvrir par programme un fichier texte en tant que classeur Microsoft Excel.
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jmartens
ms.workload:
- office
ms.openlocfilehash: 47582718128fc9818bb42571e3f33c0190a32d9e
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99888743"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Comment : ouvrir des fichiers texte en tant que classeurs par programmation
  Vous pouvez ouvrir un fichier texte en tant que classeur. Vous devez passer le nom du fichier texte que vous souhaitez ouvrir. Vous pouvez spécifier plusieurs paramètres facultatifs, tels que le numéro de ligne sur lequel commencer l’analyse et le format de colonne des données dans le fichier.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Exemple
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Compiler le code
 Cet exemple requiert les composants suivants :

- Fichier texte délimité par des virgules nommé `Test.txt` qui contient au moins trois lignes de texte.

- Fichier texte `Test.txt` à stocker sur le lecteur C.

## <a name="see-also"></a>Voir aussi
- [Utiliser des classeurs](../vsto/working-with-workbooks.md)
- [Comment : ouvrir des classeurs par programmation](../vsto/how-to-programmatically-open-workbooks.md)
- [Comment : créer des classeurs par programmation](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Comment : enregistrer des classeurs par programmation](../vsto/how-to-programmatically-save-workbooks.md)
- [Comment : fermer des classeurs par programmation](../vsto/how-to-programmatically-close-workbooks.md)
- [Paramètres facultatifs dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)
