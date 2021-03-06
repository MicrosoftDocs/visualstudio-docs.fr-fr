---
title: Identités pour les abonnés Visual Studio
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: 86f2856c-8adf-4085-9962-f4136679e5ed
ms.date: 02/19/2021
ms.topic: conceptual
description: Comment ajouter une identité secondaire à votre abonnement Visual Studio pour l’utiliser avec Azure DevOps et Azure
ms.openlocfilehash: 4d00e6808a71522f95d8580056556f5a502ecbde
ms.sourcegitcommit: 35fa920126b34c8d3839da53e3a4c2c6f509968f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102473307"
---
# <a name="identities-for-visual-studio-subscribers"></a>Identités pour les abonnés Visual Studio
Quand vous activez votre abonnement Visual Studio, nous lions l’identité (ou connexion) que vous avez utilisée lors de l’activation avec l’abonnement Visual Studio. Ainsi, nous pouvons vous reconnaître dans le [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), dans Azure DevOps et dans Azure.

Dans Azure DevOps, nous vérifions l’état de votre abonnement Visual Studio chaque fois que vous vous connectez, et nous vous octroyons des fonctionnalités automatiquement dans chaque organisation dont vous êtes membre.
Ces fonctionnalités étant incluses comme avantages réservés aux abonnés, il est possible de vous ajouter gratuitement comme membre de n’importe quelle organisation Azure DevOps lors de l’utilisation d’une identité qui est liée à votre abonnement Visual Studio.

Dans Azure, nous vérifions l’état de votre abonnement Visual Studio quand vous activez votre [crédit individuel Azure DevTest mensuel](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) qui est un avantage pour les abonnés.

Dans le [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), vous pouvez éventuellement ajouter une **identité secondaire**, en plus de celle que vous avez utilisée durant l’activation. Nous vous permettons d’ajouter une identité secondaire, si vous avez utilisé un compte Microsoft pour activer votre abonnement. De cette façon, vous pouvez également ajouter un compte professionnel ou scolaire (que vous utilisez pour vous connecter à Visual Studio, Microsoft 365 ou votre réseau d’entreprise ou d’établissement scolaire), ce qui vous permet d’accéder à Azure DevOps à l’aide de votre compte personnel et de votre compte professionnel ou scolaire.

## <a name="add-an-alternate-account-to-your-subscription"></a>Ajouter un compte secondaire à votre abonnement
L’ajout d’un compte secondaire à votre abonnement Visual Studio vous permet d’accéder à certains avantages de l’abonnement, comme Azure DevOps et Azure, ou de se connecter à l’IDE de Visual Studio avec une identité différente de celle à laquelle l’abonnement est affecté. Dans le passé, cette fonctionnalité était disponible uniquement si votre abonnement VS (Visual Studio) était affecté à un compte MSA (compte Microsoft). Nous avons étendu cette fonctionnalité aux comptes professionnels ou scolaires dans Azure AD (Azure Active Directory).

> [!NOTE]
> Un autre ID vous permet uniquement d’utiliser ce second ID pour activer les crédits Azure et Azure DevOps, et pour se connecter à l’IDE de Visual Studio.  Il ne peut pas être utilisé pour se connecter au portail des abonnements à l’adresse <https://my.visualstudio.com> .  Vous devez toujours utiliser l’ID auquel l’abonnement est attribué pour se connecter au portail. 

Pour tous les abonnements, vous pouvez ajouter un « compte professionnel ou scolaire », ce qui vous permet d’utiliser ce compte avec les avantages nécessitant une connexion (IDE VS, Azure DevOps et Azure).

### <a name="add-the-alternate-account"></a>Ajouter le compte secondaire
1. Connectez-vous au portail des abonnés Visual Studio à l’aide de votre compte Microsoft (https://my.visualstudio.com).
2. Sélectionnez l'onglet **Abonnements** .
3. Choisissez **Ajouter un autre compte**.
4. Ajoutez votre compte professionnel ou scolaire.
    > [!div class="mx-imgBorder"]
    > ![Ajouter un compte professionnel ou scolaire](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png "Ajout d’un compte professionnel ou scolaire en tant que compte secondaire sur votre abonnement.")

5. Utilisez votre compte professionnel ou scolaire pour vous connecter à Azure DevOps (https://{votre_compte}.visualstudio.com).

Votre compte secondaire est ajouté à l’abonnement Visual Studio. Ainsi, les deux identités peuvent utiliser les avantages de l’abonnement qui vous imposent de vous connecter avec le compte secondaire (IDE, Azure DevOps et Azure).

## <a name="faq"></a>Questions fréquentes (FAQ)

### <a name="q--why-doesnt-azure-devops-recognize-me-as-a-visual-studio-subscriber"></a>Q : Pourquoi Azure DevOps ne me reconnaît-il pas comme abonné Visual Studio ?

R : Azure DevOps doit reconnaître automatiquement votre abonnement quand vous vous connectez avec votre identité principale ou secondaire. Si ce n’est pas le cas, vous pouvez essayer les solutions suivantes :

* Vérifiez que vous disposez d’un abonnement Visual Studio actif qui comprend [Azure DevOps](vs-azure-devops.md#eligibility) en tant qu’avantage.

* Vérifiez que vous utilisez une connexion/identité qui est l’identité principale ou secondaire de votre abonnement Visual Studio.

* Visitez le [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) au moins une fois avant de vous connecter à Azure DevOps.

Si Azure DevOps ne reconnaît toujours pas votre abonnement, contactez le support [Azure DevOps](https://azure.microsoft.com/support/devops/).

## <a name="resources"></a>Ressources
[Prise en charge des abonnements Visual Studio](https://aka.ms/vssubscriberhelp)

## <a name="see-also"></a>Voir aussi
- [Documentation de Visual Studio](/visualstudio/)
- [Documentation Azure DevOps](/azure/devops/)
- [Documentation Azure](/azure/)
- [Documentation Microsoft 365](/microsoft-365/)

## <a name="next-steps"></a>Étapes suivantes 
Pour plus d’informations sur l’utilisation d’Azure, d’Azure DevOps ou de l’IDE de Visual Studio, consultez les ressources suivantes :
- [Microsoft Azure](vs-azure.md)
- [Azure DevOps](vs-azure-devops.md)
- [Visual Studio](vs-ide-benefit.md)