---
description: Liste des tâches enfants inscrites avec cette tâche.
title: Champ m_children | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: 5aaf29d76a7bbd81a416c86360f315bc5c09b76c
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102158867"
---
# <a name="m_children-field"></a>Champ m_children
Liste des tâches enfants inscrites avec cette tâche.

 **Espace de noms :** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Assembly :** mscorlib (en *mscorlib.dll*)

 Étant donné que vous ne pouvez pas accéder à ce membre interne à partir de la .NET Framework, la syntaxe suivante est fournie en Common Intermediate Language (CIL).

## <a name="syntax"></a>Syntaxe

```csharp
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children
```

## <a name="remarks"></a>Notes
 Pendant que la tâche est en cours d’exécution, seul le thread qui exécute la tâche doit accéder à ce tableau.

 Si la tâche est terminée, les autres threads peuvent accéder à ce champ tant qu’ils n’y ajoutent rien ou n’en suppriment rien.

## <a name="see-also"></a>Voir aussi
- [ContingentProperties, classe](../../extensibility/debugger/contingentproperties-class-internal-members.md)
