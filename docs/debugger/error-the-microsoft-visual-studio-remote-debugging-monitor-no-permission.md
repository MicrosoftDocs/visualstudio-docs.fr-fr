---
description: Cette erreur ce produit lorsque l'utilisateur qui tente d'exécuter Visual Studio Remote Debugging Monitor (msvsmon) ne possède pas de compte sur l'ordinateur local.
title: Microsoft Visual Studio Remote Debugging Monitor sur l’ordinateur distant ne dispose pas des autorisations pour se connecter à cet ordinateur
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, Windows version error
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: f35db1d84d0f44eedbc8bf09f1e5ff9a6f49e5f2
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102146728"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Erreur : Microsoft Visual Studio Remote Debugging Monitor sur l'ordinateur distant ne dispose pas des autorisations pour se connecter à cet ordinateur

Cette erreur ce produit lorsque l'utilisateur qui tente d'exécuter Visual Studio Remote Debugging Monitor (msvsmon) ne possède pas de compte sur l'ordinateur local. Cette erreur peut se produire lors du débogage à distance à l’aide du moteur de débogage hérité.

## <a name="to-fix-this-problem"></a>Pour corriger ce problème

- Ajoutez un compte d'utilisateur à l'ordinateur hôte du débogueur Visual Studio, en utilisant les mêmes nom et mot de passe que le compte d'utilisateur qui exécute msvsmon sur l'ordinateur distant.

   \- ou -

- Exécutez msvsmon en tant qu'utilisateur autorisé à appeler l'ordinateur local. Cela signifie que l'utilisateur doit être un utilisateur de domaine et un administrateur sur l'ordinateur msvsmon. Vous pouvez spécifier le compte d'utilisateur qui doit exécuter msvsmon de deux manières différentes :

  - Cliquez avec le bouton droit sur l’icône msvsmon et choisissez **Exécuter en tant que** dans le menu contextuel

    \- ou -

  - À l'invite de commandes, tapez `runas.exe`.

## <a name="see-also"></a>Voir aussi

- [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Débogage à distance](../debugger/remote-debugging.md)
