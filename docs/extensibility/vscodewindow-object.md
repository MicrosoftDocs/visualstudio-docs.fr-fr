---
title: Objet VSCodeWindow | Microsoft Docs
description: En savoir plus sur les fenêtres de code, qui sont des fenêtres de document spécialisées qui peuvent inclure un ou plusieurs affichages de texte, généralement l’objet VsTextView.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 6b324c0b572f025b3733233d70cf36485f90524c
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99925857"
---
# <a name="vscodewindow-object"></a>Objet VSCodeWindow
Une fenêtre de code est une fenêtre de document spécialisée qui peut inclure un ou plusieurs affichages de texte, généralement l' <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objet.

 De l’architecture, la fenêtre de code est une fenêtre de document qui se trouve dans un cadre de fenêtre. Fonctionnellement, la fenêtre de code est simplement une fenêtre de document avec des fonctionnalités supplémentaires. Dans le mode d’interface multidocument (MDI, multiple-document interface), la fenêtre de code est le frame enfant MDI. Pour plus d’informations, consultez [Personnalisation des fenêtres de code à l’aide de l’API héritée](/previous-versions/visualstudio/visual-studio-2015/extensibility/customizing-code-windows-by-using-the-legacy-api?preserve-view=true&view=vs-2015).

 Le tableau suivant répertorie les interfaces de l' <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objet.

|Méthode|Description|
|------------|-----------------|
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Fournit un mécanisme d’accès générique pour rechercher un service identifié par un identificateur global unique (GUID).|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Représente un enfant d’interface multidocument (MDI) contenant un ou plusieurs affichages de code.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Remplit un frame de fenêtre.|

## <a name="see-also"></a>Voir aussi
- <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>
- [Modifications des figures](https://www.microsoft.com/download/details.aspx?id=55984)