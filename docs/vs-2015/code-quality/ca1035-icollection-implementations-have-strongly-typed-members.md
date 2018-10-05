---
title: 'CA1035 : Les implémentations ICollection ont des membres fortement typés | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f6b88390f91ecf6c673e00024e0c371a09de48a2
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588146"
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035 : Les implémentations ICollection possèdent des membres fortement typés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA1035 : les implémentations ICollection ont des membres fortement typés](https://docs.microsoft.com/visualstudio/code-quality/ca1035-icollection-implementations-have-strongly-typed-members).

|||
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|CheckId|CA1035|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type public ou protégé implémente <xref:System.Collections.ICollection?displayProperty=fullName> mais ne fournit ne pas de méthode fortement typée pour <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>. La version fortement typée de <xref:System.Collections.ICollection.CopyTo%2A> doit accepter deux paramètres et ne peut pas avoir un <xref:System.Array?displayProperty=fullName> ou un tableau de <xref:System.Object?displayProperty=fullName> en tant que son premier paramètre.

## <a name="rule-description"></a>Description de la règle
 Cette règle requiert <xref:System.Collections.ICollection> implémentations fournissent fortement des membres typés afin que les utilisateurs ne doivent pas effectuer un cast des arguments à la <xref:System.Object> tapez lorsqu’ils utilisent les fonctionnalités fournies par l’interface. Cette règle suppose que le type qui implémente <xref:System.Collections.ICollection> effectue donc à gérer une collection d’instances d’un type plus fort que <xref:System.Object>.

 <xref:System.Collections.ICollection> implémente l'interface <xref:System.Collections.IEnumerable?displayProperty=fullName>. Si les objets dans la collection étendent <xref:System.ValueType?displayProperty=fullName>, vous devez fournir un membre fortement typé pour <xref:System.Collections.IEnumerable.GetEnumerator%2A> afin d’éviter la baisse de performances est provoquée par le boxing. Cela n’est pas nécessaire lorsque les objets de la collection sont un type référence.

 Pour implémenter une version fortement typée d’un membre d’interface, implémentez explicitement les membres d’interface à l’aide de noms sous la forme `InterfaceName.InterfaceMemberName`, tel que <xref:System.Collections.ICollection.CopyTo%2A>. Les membres d’interface explicites utilisent les types de données qui sont déclarés par l’interface. Implémenter des membres fortement typés à l’aide du nom de membre d’interface, tel que <xref:System.Collections.ICollection.CopyTo%2A>. Déclarer des membres fortement typés comme publics et déclarez des paramètres et retourner des valeurs à être de type fort qui est géré par la collection. Les types forts remplacent les types plus faibles comme <xref:System.Object> et <xref:System.Array> qui sont déclarés par l’interface.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez le membre d’interface explicitement (déclarez-le en tant que <xref:System.Collections.ICollection.CopyTo%2A>). Ajouter le membre fortement typé public, déclaré comme `CopyTo`, et qu’il procède à un tableau fortement typé en tant que son premier paramètre.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si vous implémentez une nouvelle collection basée sur un objet, comme une arborescence binaire, où des types qui étendent la nouvelle collection déterminent le type fort. Ces types doivent être conforme à cette règle et exposer des membres fortement typés.

## <a name="example"></a>Exemple
 L’exemple suivant illustre la façon correcte d’implémenter <xref:System.Collections.ICollection>.

 [!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ICollectionStrongTypes/cs/FxCop.Design.ICollectionStrongTypes.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA1038 : Les énumérateurs doivent être fortement typés](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

 [CA1039 : Les listes sont fortement typées](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Voir aussi
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.IEnumerable?displayProperty=fullName>
 <xref:System.Collections.ICollection?displayProperty=fullName>
 <xref:System.Object?displayProperty=fullName>


