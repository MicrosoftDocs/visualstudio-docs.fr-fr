---
description: Cette structure est utilisée pour définir les informations de JustMyCode d’un module.
title: JMC_CODE_SPEC | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6c862a2897b45d89f95963ce7adfe2da8d4d350f
ms.sourcegitcommit: f33ca1fc99f5d9372166431cefd0e0e639d20719
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102225563"
---
# <a name="jmc_code_spec"></a>JMC_CODE_SPEC
Cette structure est utilisée pour définir les informations de JustMyCode d’un module.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _JMC_CODE_SPEC {
    BOOL fIsUserCode;
    BSTR bstrModuleName;
} JMC_CODE_SPEC;
```

```csharp
public struct JMC_CODE_SPEC {
    public int    fIsUserCode;
    public string bstrModuleName;
};
```

## <a name="members"></a>Membres
`fIsUserCode`\
Différent de zéro ( `TRUE` ) si le module doit être considéré comme du code utilisateur ; sinon, zéro ( `FALSE` ) si le module doit être traité comme du code externe et ne doit pas être débogué.

`bstrModuleName`\
Nom du module en question.

## <a name="remarks"></a>Notes
Cette structure est transmise comme une liste de ces structures à la méthode [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md) .

## <a name="requirements"></a>Spécifications
En-tête : msdbg. h

Espace de noms : Microsoft. VisualStudio. Debugger. Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Structures et unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)
