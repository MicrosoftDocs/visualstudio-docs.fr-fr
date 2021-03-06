---
description: Utilisez le kit de développement logiciel (SDK) DIA pour accéder aux informations de débogage Microsoft.
title: Vue d’ensemble (kit de développement logiciel Debug interface Access) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- multiple
ms.openlocfilehash: c505216cd38b5321f291515794fc07ff58e8d698
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102155361"
---
# <a name="overview-debug-interface-access-sdk"></a>Vue d’ensemble (Kit de développement logiciel Debug Interface Access)
Utilisez le kit de développement logiciel (SDK) DIA pour accéder aux informations de débogage Microsoft. Le kit de développement logiciel (SDK) DIA fournit un ensemble d’API basé sur COM qui évite de devoir réécrire votre code chaque fois que Microsoft modifie le format des informations de débogage. Le kit de développement logiciel (SDK) DIA vous permet également de lire à partir d’un ensemble sélectionné de versions précédentes des informations de débogage, situées dans les fichiers. pdb et. dbg générés par les [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] versions 5,0 et ultérieures.

 Chaque interface dans le kit de développement DIA représente un objet COM différent, sauf indication contraire. Les interfaces supplémentaires, et par conséquent des objets supplémentaires, sont créées au moyen de requêtes explicites, telles que [IDiaDataSource :: OpenSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) ou [IDiaSession :: findchildren (](../../debugger/debug-interface-access/idiasession-findchildren.md), plutôt que d’appeler `QueryInterface` sur des pointeurs d’interface existants.

## <a name="see-also"></a>Voir aussi
- [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
