---
description: Spécifie les informations à récupérer sur la résolution réussie d’un point d’arrêt.
title: BPRESI_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 91fa2a8b973149cb9365d817e14ac877bfc9f617
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102171029"
---
# <a name="bpresi_fields"></a>BPRESI_FIELDS
Spécifie les informations à récupérer sur la résolution réussie d’un point d’arrêt.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
typedef DWORD BPRESI_FIELDS;
```

```csharp
public enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
```

## <a name="fields"></a>Champs
`BPRESI_BPRESLOCATION`\
Initialisez/utilisez le `bpResLocation` champ (emplacement de résolution des points d’arrêt) de la structure [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) .

`BPRESI_PROGRAM`\
Initialisez/utilisez le `pProgram` champ de la `BP_RESOLUTION_INFO` structure.

`BPRESI_THREAD`\
Initialisez/utilisez le `pThread` champ de la `BP_RESOLUTION_INFO` structure.

`BPRESI_ALLFIELDS`\
Spécifie tous les champs.

## <a name="remarks"></a>Notes
Passé à la méthode [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) pour indiquer les champs de la structure [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) qui doivent être initialisés.

Ces indicateurs sont également utilisés pour indiquer les champs de la `BP_RESOLUTION_INFO` structure qui sont utilisés et valides lorsque cette structure est retournée.

Ces valeurs peuvent être combinées avec une opération de bits `OR` .

## <a name="requirements"></a>Configuration requise
En-tête : msdbg. h

Espace de noms : Microsoft. VisualStudio. Debugger. Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
