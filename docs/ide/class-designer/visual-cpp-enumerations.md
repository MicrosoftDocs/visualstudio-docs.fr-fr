---
title: Énumérations C++ dans Concepteur de classes
description: Découvrez comment Concepteur de classes prend en charge les types ENUM C++ et classes enum délimitées.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: TerryGLee
ms.author: tglee
manager: jmartens
ms.workload:
- cplusplus
ms.openlocfilehash: 88675bb7593a901805cc156bbb36a2f49d69ec29
ms.sourcegitcommit: ae6d47b09a439cd0e13180f5e89510e3e347fd47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "99852555"
---
# <a name="c-enumerations-in-class-designer"></a>Énumérations C++ dans Concepteur de classes

**Concepteur de classes** prend en charge C++ `enum` et les types délimités `enum class` . Vous trouverez ci-dessous un exemple :

```cpp
enum CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};

// or...
enum class CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};
```

Une forme d’énumération C++ dans un diagramme de classes se présente et fonctionne comme une forme de structure, hormis le fait que l’étiquette indique **Enum** ou **Enum class**, elle est rose plutôt que bleu, et elle comporte une bordure colorée sur les marges gauche et supérieure. Les formes d’énumération et les formes de structure ont des angles carrés.

Pour plus d’informations sur l’utilisation du type `enum`, consultez [Énumérations](/cpp/cpp/enumerations-cpp).

## <a name="see-also"></a>Voir aussi

- [Utilisation du code C++](working-with-visual-cpp-code.md)
- [Énumérations](/cpp/cpp/enumerations-cpp)
