---
title: Conseils pour le débogage de threads en code natif | Microsoft Docs
description: Lisez une liste de conseils pour déboguer des threads en code natif si vous déboguez des applications multithread dans Visual Studio.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.workload:
- cplusplus
ms.openlocfilehash: 85bdd804e25dfa91b649e95daacef4bfb322df64
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99940564"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Conseils pour le débogage de threads en code natif
Voici quelques conseils que vous utiles pour le débogage de threads en code natif :

- Vous pouvez consulter le contenu du bloc d’informations du thread en entrant `@TIB` dans la fenêtre **Espion** ou dans la boîte de dialogue **Espion express**.

- Vous pouvez consulter le dernier code d’erreur du thread actuel en entrant `@Err` dans la fenêtre **Espion** ou dans la boîte de dialogue **Espion express**.

- Vous pouvez utiliser les fonctions des bibliothèques Runtime C pour déboguer une application multithread. Pour plus d’informations, consultez [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg).

## <a name="see-also"></a>Voir aussi
- [Déboguer des applications multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [Débogage du code natif](../debugger/debugging-native-code.md)