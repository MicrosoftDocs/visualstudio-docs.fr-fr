---
title: Visual Studio Tools pour Docker avec ASP.NET Core
author: ghogen
description: Découvrez comment utiliser les outils Visual Studio 2019 et Docker pour Windows
ms.author: ghogen
ms.date: 02/01/2019
ms.prod: visual-studio-dev16
ms.technology: vs-azure
ms.topic: include
ms.openlocfilehash: 124f60a4a632115625524b4e30ab28f795d41660
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70312177"
---
Avec Visual Studio, vous pouvez facilement générer, déboguer et exécuter des applications de ASP.NET Core en conteneur et les publier sur Azure Container Registry (ACR), un hub d’ancrage, Azure App Service ou votre propre registre de conteneurs. Dans cet article, nous allons effectuer la publication sur ACR.

## <a name="prerequisites"></a>Prérequis

* [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) avec la charge de travail **Développement web**, **Outils Azure** et/ou la charge de travail **Développement multiplateforme .NET Core** installée
* [Outils de développement .NET core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) pour le développement avec .NET Core 2.2
* Pour publier sur Azure Container Registry, un abonnement Azure. [Inscrivez-vous pour obtenir un essai gratuit](https://azure.microsoft.com/offers/ms-azr-0044p/).

## <a name="installation-and-setup"></a>Installation et configuration

Pour l’installation de Docker, consultez d’abord les informations disponibles sur [Docker Desktop for Windows: What to know before you install](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install). Installez ensuite [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows).

## <a name="add-a-project-to-a-docker-container"></a>Ajouter un projet à un conteneur Docker

1. Créez un nouveau projet à l’aide du modèle **Application web ASP.NET Core**.
1. Sélectionnez **application Web**et assurez-vous que la case **activer la prise en charge** de l’ancrage est cochée.

   ![Case Activer la prise en charge de Docker](../../media/container-tools/vs-2019/create-new-web-application.PNG)

1. Sélectionnez le type de conteneur souhaité (Windows ou Linux) et cliquez sur **Créer**.

## <a name="dockerfile-overview"></a>Vue d’ensemble du fichier Dockerfile

Un *fichier Docker*, la recette permettant de créer une image Docker finale, est créé dans le projet. Consultez les [Informations de référence sur Dockerfile](https://docs.docker.com/engine/reference/builder/) pour comprendre les commandes qu’il contient.

```
FROM microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM microsoft/dotnet:2.2-sdk-stretch AS build
WORKDIR /src
COPY ["HelloDockerTools/HelloDockerTools.csproj", "HelloDockerTools/"]
RUN dotnet restore "HelloDockerTools/HelloDockerTools.csproj"
COPY . .
WORKDIR "/src/HelloDockerTools"
RUN dotnet build "HelloDockerTools.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "HelloDockerTools.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "HelloDockerTools.dll"]
```

Le *Dockerfile* précédent est basé sur l’image [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/). Il comprend des instructions pour modifier l’image de base en générant votre projet et en l’ajoutant au conteneur.

Quand la case **Configurer pour HTTPS** de la boîte de dialogue du nouveau projet est cochée, le fichier *Dockerfile* expose deux ports. Un port est utilisé pour le trafic HTTP tandis que l’autre est utilisé pour HTTPS. Si la case n’est pas cochée, un seul port (80) est exposé pour le trafic HTTP.

## <a name="debug"></a>Débogage

Sélectionnez **Docker** dans la liste déroulante de débogage dans la barre d’outils et démarrez le débogage de l’application. Vous pouvez être amené à voir s’afficher un message vous invitant à approuver un certificat. Choisissez d’approuver le certificat pour continuer.

L’option **Outil conteneur** dans la fenêtre **Sortie** indique les actions en cours.

Ouvrez la **Console du Gestionnaire de package** à partir du menu **Outils**> Gestionnaire de package NuGet, **Console du Gestionnaire de package**.

L’image Docker obtenue de l’application est marquée avec la balise *dev*. L’image est basée sur la balise *2.2-aspnetcore-runtime* de l’image de base *microsoft/dotnet*. Exécutez la commande `docker images` dans la fenêtre **Console du Gestionnaire de package**. Les images sur la machine s’affichent :

```console
REPOSITORY        TAG                     IMAGE ID      CREATED         SIZE
hellodockertools  dev                     d72ce0f1dfe7  30 seconds ago  255MB
microsoft/dotnet  2.2-aspnetcore-runtime  fcc3887985bb  6 days ago      255MB
```

> [!NOTE]
> L’image **dev** ne contient pas les fichiers binaires de l’application ni aucun autre contenu. En effet, les configurations **Debug** utilisent le montage de volume pour fournir l’expérience de modification et de débogage itérative. Pour créer une image de production incluant tout le contenu, utilisez la configuration **Release**.

Exécutez la commande `docker ps` dans la console du Gestionnaire de package. Notez que l’application s’exécute à l’aide du conteneur :

```console
CONTAINER ID        IMAGE                  COMMAND               CREATED             STATUS              PORTS                                           NAMES
cf5d2ef5f19a        hellodockertools:dev   "tail -f /dev/null"   2 minutes ago       Up 2 minutes        0.0.0.0:52036->80/tcp, 0.0.0.0:44342->443/tcp   priceless_cartwright
```

## <a name="publish-docker-images"></a>Publier des images Docker

Une fois le cycle de développement et de débogage de l’application effectué, vous pouvez créer une image de production de l’application.

1. Changez la liste déroulante de configuration en **Release** et générez l’application.
1. Cliquez avec le bouton droit sur votre projet dans l’**Explorateur de solutions** et choisissez **Publier**.
1. Dans la boîte de dialogue de la cible de publication, sélectionnez l’onglet **Registre de conteneurs**.
1. Choisissez **Créer un registre de conteneurs Azure**, puis cliquez sur **Publier**.
1. Renseignez les valeurs souhaitées dans **Créer un registre de conteneurs Azure**.

    | Paramètre      | Valeur suggérée  | Description                                |
    | ------------ |  ------- | -------------------------------------------------- |
    | **Préfixe DNS** | Nom globalement unique | Nom qui identifie uniquement votre registre de conteneurs. |
    | **Abonnement** | Choisissez votre abonnement | Sélectionnez l’abonnement Azure à utiliser. |
    | **[Groupe de ressources](/azure/azure-resource-manager/resource-group-overview)** | myResourceGroup |  Nom du groupe de ressources où créer votre registre de conteneurs. Choisissez **Nouveau** pour créer un groupe de ressources.|
    | **[SKU](https://docs.microsoft.com/azure/container-registry/container-registry-skus)** | Standard | Niveau de service du registre de conteneurs  |
    | **Emplacement du registre** | Un emplacement proche de vous | Choisissez un emplacement dans une [région](https://azure.microsoft.com/regions/) près de chez vous ou près d’autres services que votre registre de conteneurs va utiliser. |

    ![Boîte de dialogue de création d’un registre de conteneurs Azure dans Visual Studio][0]

1. Cliquez sur **Créer**

   ![Capture d’écran affichant la réussite de la publication](../../media/container-tools/publish-succeeded.png)

## <a name="next-steps"></a>Étapes suivantes

Vous pouvez désormais extraire le conteneur à partir du registre sur tout hôte en mesure d’exécuter des images Docker, par exemple [Azure Container Instances](/azure/container-instances/container-instances-tutorial-deploy-app).

[0]:../../media/hosting-web-apps-in-docker/vs-acr-provisioning-dialog-2019.png