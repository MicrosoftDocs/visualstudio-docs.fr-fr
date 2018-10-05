---
title: À l’aide de l’attribut DebuggerDisplay | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerDisplay attribute
- DebuggerDisplayAttribute class
ms.assetid: f4eb7c76-af4e-493b-9ab6-9cb05949d9b3
caps.latest.revision: 50
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb5e47cbaea7c7a39201f25adf6955a2e22c9b9b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47507144"
---
# <a name="using-the-debuggerdisplay-attribute"></a>Utilisation de l’attribut DebuggerDisplay
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [à l’aide de l’attribut DebuggerDisplay](https://docs.microsoft.com/visualstudio/debugger/using-the-debuggerdisplay-attribute).  
  
La <xref:System.Diagnostics.DebuggerDisplayAttribute> contrôle la façon dont un objet, une propriété ou un champ s’affiche dans les fenêtres de variables du débogueur. Cet attribut peut être appliqué aux éléments suivants : types, délégués, propriétés, champs et assemblys.  
  
 L'attribut `DebuggerDisplay` possède un seul argument, qui est une chaîne à afficher dans la colonne valeur des instances du type. Cette chaîne peut contenir des accolades (`{` et `}`). Le texte entre deux accolades est évalué comme un champ, une propriété ou une méthode.  
  
 Si une classe possède une méthode `ToString()` substituée, le débogueur utilise la méthode substituée à la place du `{<typeName>}`par défaut. Si vous avez substitué la méthode `ToString()` , le débogueur utilise la méthode substituée à la place du`{<typeName>}`par défaut. Il est donc inutile d’utiliser `DebuggerDisplay`. Si vous utilisez les deux, l’attribut `DebuggerDisplay` est prioritaire sur la méthode `ToString()` substituée.  
  
 L’évaluation par le débogueur de cet appel `ToString()` implicite dépend d’un paramètre utilisateur dans la boîte de dialogue **Outils / Options / Débogage** . Visual Basic n’implémente pas cette évaluation `ToString()` implicite.  
  
> [!IMPORTANT]
>  Si la case **Afficher la structure brute des objets dans des fenêtres de variables** est cochée dans la boîte de dialogue **Outils / Options / Débogage** , l’attribut `DebuggerDisplay` est ignoré.  
  
 Le tableau suivant montre quelques-unes des utilisations possibles de l'attribut `DebuggerDisplay` et quelques exemples de sorties.  
  
|Attribut|Sortie (affichée dans la colonne **Valeur** )|  
|---------------|------------------------------------------------|  
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Utilisé sur un type avec champs `x` et `y`.|`x = 5 y = 18`|  
|`[DebuggerDisplay("String value is {getString()}")]`La syntaxe des paramètres peut varier d'un langage à l'autre. Par conséquent, soyez vigilant dans son emploi.|`String value is [5, 6, 6]`|  
  
 `DebuggerDisplay` peut également accepter des paramètres nommés.  
  
|Paramètres|Objectif|  
|----------------|-------------|  
|`Name`, `Type`|Ces paramètres affectent les colonnes **Nom** et **Type** des fenêtres de variables. (Ils peuvent être appliqués aux chaînes à l'aide de la même syntaxe que le constructeur). Une utilisation excessive ou inappropriée de ces paramètres peut générer un résultat confus.|  
|`Target`, `TargetTypeName`|Spécifie le type cible lorsque l'attribut est utilisé au niveau de l'assembly.|  
  
 Le fichier autoexp.cs utilise l’attribut DebuggerDisplay au niveau de l’assembly. Le fichier autoexp.cs détermine les expansions par défaut utilisées par Visual Studio pour les objets .NET. Vous pouvez examiner le fichier autoexp.cs pour obtenir des exemples d’utilisation de l’attribut DebuggerDisplay, ou modifier et compiler le fichier autoexp.cs pour changer les expansions par défaut. Assurez-vous d'avoir sauvegardé le fichier autoexp.cs avant de le modifier.  
  
 Pour générer autoexp.cs, ouvrez une Invite de commandes développeur pour VS2015, puis exécutez les commandes suivantes :  
  
```  
cd <directory containing autoexp.cs>  
csc /t:library autoexp.cs  
```  
  
 Les modifications apportées à autoexp.dll seront récupérées lors de la prochaine session de débogage.  
  
## <a name="using-expressions-in-debuggerdisplay"></a>Utilisation d'expressions dans DebuggerDisplay  
 Bien que vous puissiez utiliser une expression générale à l'intérieur de l'accolade dans un attribut DebuggerDisplay, cette méthode n'est pas recommandée.  
  
 Une expression générale DebuggerDisplay dispose d'un accès implicite au pointeur `this` pour l'instance actuelle du type de cible uniquement. L'expression n'a accès ni aux alias, ni aux variables locales, ni aux pointeurs. Si l'expression référence des propriétés, les attributs de ces propriétés ne sont pas traités. Par exemple, le code C# `[DebuggerDisplay("Object {count - 2}"`  afficherait `Object 6` si le champ `count` avait la valeur 8.  
  
 L'utilisation d'expressions dans DebuggerDisplay peut provoquer les problèmes suivants :  
  
-   L'évaluation des expressions est l'opération la plus coûteuse dans le débogueur et l'expression est évaluée chaque fois qu'elle est affichée. Cela peut provoquer des problèmes de performances pendant l'exécution du code pas à pas. Par exemple, une expression complexe qui est utilisée pour afficher des valeurs dans une collection ou une liste peut être très lente lorsque le nombre d'éléments est important.  
  
-   Les expressions sont évaluées par l'évaluateur d'expression du langage du cadre de pile actuel et pas par l'évaluateur du langage dans lequel l'expression a été écrite. Cela peut provoquer des résultats inattendus lorsque les langages sont différents.  
  
-   L'évaluation d'une expression peut modifier l'état de l'application. Par exemple, une expression qui définit la valeur d'une propriété transforme la valeur d'une propriété dans le code en cours de exécution.  
  
 Une façon de réduire les problèmes potentiels de l'évaluation de l'expression consiste à créer une propriété privée qui exécute l'opération et retourne une chaîne. L'attribut DebuggerDisplay peut ensuite afficher la valeur de cette propriété privée. L'exemple suivant implémente ce modèle :  
  
```csharp  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
public sealed class MyClass   
{      
    public int count { get; set; }      
    public bool flag { get; set; }      
    private string DebuggerDisplay  
   {         
        get  
        {  
             return string.Format("("Object {0}", count - 2);  
        }      
    }  
}  
```  
  
## <a name="example"></a>Exemple  
 L'exemple de code suivant explique l'utilisation de `DebuggerDisplay`, ainsi que de `DebuggerBrowseable` et `DebuggerTypeProxy`. Lorsqu'il s'affiche dans une fenêtre de variables du débogueur, comme la fenêtre **Espion** , il produit une expansion de ce genre :  
  
|**Name**|**Valeur**|**Type**|  
|--------------|---------------|--------------|  
|Touche|"trois"|objet {string}|  
|Value|3|objet {int}|  
  
```csharp  
[DebuggerDisplay("{value}", Name = "{key}")]  
internal class KeyValuePairs  
{  
    private IDictionary dictionary;  
    private object key;  
    private object value;  
    public KeyValuePairs(IDictionary dictionary, object key, object value)  
    {  
        this.value = value;  
        this.key = key;  
        this.dictionary = dictionary;  
    }  
  
    public object Key  
    {  
        get { return key; }  
        set  
        {  
            object tempValue = dictionary[key];  
            dictionary.Remove(key);  
            key = value;  
            dictionary.Add(key, tempValue);  
        }  
    }  
  
    public object Value  
    {  
        get { return this.value; }  
        set  
        {  
            this.value = value;  
            dictionary[key] = this.value;  
        }  
    }  
}  
  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable  
{  
    public Hashtable hashtable;  
  
    public MyHashtable()  
    {  
        hashtable = new Hashtable();    
    }    private string DebuggerDisplay    {        get { return "Count = " + hashtable.Count); }    }  
  
    private class HashtableDebugView  
    {  
        private MyHashtable myhashtable;  
        public HashtableDebugView(MyHashtable myhashtable)  
        {  
            this.myhashtable = myhashtable;  
        }  
  
        [DebuggerBrowsable(DebuggerBrowsableState.RootHidden)]  
        public KeyValuePairs[] Keys  
        {  
            get  
            {  
                KeyValuePairs[] keys = new KeyValuePairs[myhashtable.hashtable.Count];  
  
                int i = 0;  
                foreach (object key in myhashtable.hashtable.Keys)  
                {  
                    keys[i] = new KeyValuePairs(myhashtable.hashtable, key, myhashtable.hashtable[key]);  
                    i++;  
                }  
                return keys;  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [À l’aide de l’attribut DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md) [amélioration du débogage avec les attributs d’affichage de débogueur](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)


