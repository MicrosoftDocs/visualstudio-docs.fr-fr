---
description: Cette méthode modifie l’objet représenté par le visualiseur.
title: 'IEEVisualizerDataProvider :: SetObjectForVisualizer | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: df5cfd2acef1a2214d4692a49c742c26cd420ffa
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102227227"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
Cette méthode modifie l’objet représenté par le visualiseur.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetObjectForVisualizer(
   IDebugObject*  pNewObject,
   BSTR*          error,
   IDebugObject** pException
);
```

```csharp
int SetObjectForVisualizer(
   IDebugObject     pNewObject,
   out string       error,
   out IDebugObject pException
);
```

## <a name="parameters"></a>Paramètres
`pNewObject`\
dans Objet à définir.

`error`\
à Si une erreur s’est produite lors de la définition de l’objet, cette chaîne contient le message d’erreur.

`pException`\
à En cas d’erreur, cet objet contient les informations sur l’exception.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Il revient à l’implémenteur de déterminer la façon dont les informations d’erreur sont retournées. Toutefois, il est possible que certains appelants ne cherchent pas à voir si un objet exception a été retourné pour savoir qu’une erreur s’est produite. par conséquent, cette méthode doit toujours retourner un objet exception en cas d’erreur. La chaîne d’erreur doit également être fournie au cas où l’appelant souhaite l’utiliser.

## <a name="see-also"></a>Voir aussi
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
