---
title: -NoSplash (devenv.exe)
description: Découvrez comment utiliser le commutateur de ligne de commande nosplash devenv pour empêcher l’affichage de l’écran de démarrage.
ms.custom: SEO-VS-2020
ms.date: 12/10/2018
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /NoSplash switch
- /NoSplash Devenv switch
- NoSplash Devenv switch
author: DennisLee-DennisLee
ms.author: v-dele
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c88d75c0658c861c4631daeeb736ed7cfdb0a487
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99967226"
---
# <a name="nosplash-devenvexe"></a>/NoSplash (devenv.exe)

Empêche l’écran de démarrage de s’afficher.

## <a name="syntax"></a>Syntaxe

```shell
devenv /NoSplash [File1[ FileN]...]
```

## <a name="arguments"></a>Arguments

- *File1*

  Facultatif. Fichier à ouvrir dans une instance existante de Visual Studio. S’il n’en existe pas, une instance est créée avec une disposition de fenêtre simplifiée ; l’outil ouvre *File1* dans cette nouvelle instance.

- *FileN*

  Facultatif. Un ou plusieurs fichiers supplémentaires à ouvrir dans l’instance existante de Visual Studio.

## <a name="remarks"></a>Notes

Ce commutateur masque l’écran de démarrage. S’il est omis, l’écran de démarrage s’affiche. Si vous voulez examiner en détail l’écran de démarrage (par exemple, pour vérifier l’icône de produit VSPackage), utilisez le commutateur [/Splash](../../extensibility/devenv-command-line-switches-for-vspackage-development.md).

Le commutateur `/NoSplash` peut être combiné avec d’autres commutateurs, par exemple, [/Run](run-devenv-exe.md) ou [/DebugExe](debugexe-devenv-exe.md).

## <a name="example"></a>Exemple

Les trois exemples ouvrent l’environnement IDE sans afficher l’écran de démarrage. Le deuxième compile également la solution spécifiée et exécute l’exécutable généré. Le troisième ouvre l’exécutable spécifié pour permettre son débogage dans l’environnement IDE.

```shell
devenv /nosplash

devenv /nosplash /run MySolution.sln

devenv /nosplash /debugexe MySolution.exe
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Commutateurs de ligne de commande devenv pour le développement VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
