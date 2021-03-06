---
title: Output | Microsoft Docs
description: Découvrez comment l’option de sortie spécifie le nom du fichier de données de profilage pour la session de performance. Output doit être utilisé avec l’option Start.
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: jmartens
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: de3edb5e9b9c04b53d6b669828020c0999d218e5
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99922395"
---
# <a name="output"></a>Output
L’option **Output** spécifie le nom du fichier de données de profilage pour la session de performances. **Output** doit être utilisé avec l’option **Start**.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName [Options]
```

#### <a name="parameters"></a>Paramètres
 `FileName` Nom du fichier de données. Les chemins complets et partiels sont acceptés. Si un chemin n’est pas spécifié, le fichier est créé dans le répertoire actif.

## <a name="required-options"></a>Options obligatoires
 L’option **Output** doit être utilisée avec l’option **Start**.

 **Démarrer :** `Method` Spécifie le nom du fichier de sortie.

## <a name="example"></a>Exemple
 Dans l’exemple suivant, le fichier de données de profilage est créé dans le répertoire actif.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
```

## <a name="see-also"></a>Voir aussi
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)
