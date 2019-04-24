---
title: 'CA3004 : Passez en revue le code pour détecter les vulnérabilités sur la divulgation d’informations'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 82f763d9a6b1ec27975aa80054456a6bbbaeaa2b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069026"
---
# <a name="ca3004-review-code-for-information-disclosure-vulnerabilities"></a>CA3004 : Passez en revue le code pour détecter les vulnérabilités sur la divulgation d’informations

|||
|-|-|
|TypeName|ReviewCodeForInformationDisclosureVulnerabilities|
|CheckId|CA3004|
|Category|Microsoft.Security|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause

Message, trace de pile ou représentation sous forme de chaîne d’une exception atteint la sortie du web.

## <a name="rule-description"></a>Description de la règle

Divulgation d’informations sur les exceptions donne les attaquants insight dans les profondeurs de votre application, ce qui peut aider des personnes malveillantes trouver d’autres vulnérabilités à exploiter.

Cette règle tente de trouver un message d’exception, la trace de la pile ou la représentation sous forme de chaîne en cours de la sortie vers une réponse HTTP.

> [!NOTE]
> Cette règle ne peut pas suivre les données entre les assemblys. Par exemple, si un seul assembly intercepte une exception et transmet ensuite à un autre assembly qui génère l’exception, cette règle ne génère un avertissement.

> [!NOTE]
> Il existe une limite configurable pour la profondeur cette règle permet d’analyser les flux de données entre les appels de méthode. Consultez [Configuration de l’analyseur](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) pour savoir comment configurer la limite dans `.editorconfig` fichiers.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

Ne générer des informations d’exception aux réponses HTTP. Au lieu de cela, fournissez un message d’erreur générique. Consultez [page de gestion des erreurs de OWASP](https://www.owasp.org/index.php/Error_Handling) pour obtenir des instructions.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Si vous connaissez votre sortie web est dans les limites d’approbation de votre application et jamais à l’extérieur, il est exposé OK pour supprimer cet avertissement. Cela est rare. Prendre en considération limite d’approbation de votre application et de flux de données susceptible de changer au fil du temps.

## <a name="pseudo-code-examples"></a>Exemples de pseudo-code

### <a name="violation"></a>Violation

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write(e.ToString());
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write(e.ToString())
        End Try
    End Sub
End Class
```

### <a name="solution"></a>Solution

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs eventArgs)
    {
        try
        {
            object o = null;
            o.ToString();
        }
        catch (Exception e)
        {
            this.Response.Write("An error occurred. Please try again later.");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Try
            Dim o As Object = Nothing
            o.ToString()
        Catch e As Exception
            Me.Response.Write("An error occurred. Please try again later.")
        End Try
    End Sub
End Class
```