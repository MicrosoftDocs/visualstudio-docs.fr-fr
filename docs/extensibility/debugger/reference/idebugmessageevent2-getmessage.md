---
description: Obtient le message à afficher.
title: 'IDebugMessageEvent2 :: GetMessage | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 26280ca238b5ffc96b0d8b29f1b2d1a424c544d0
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102172470"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
Obtient le message à afficher.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMessage( 
   MESSAGETYPE* pMessageType,
   BSTR*        pbstrMessage,
   DWORD*       pdwType,
   BSTR*        pbstrHelpFileName,
   DWORD*       pdwHelpId
);
```

```csharp
int GetMessage( 
   out enum_MESSAGETYPE pMessageType,
   out string           pbstrMessage,
   out uint             pdwType,
   out string           pbstrHelpFileName,
   out uint             dwHelpId
);
```

## <a name="parameters"></a>Paramètres
`pMessageType`\
à Retourne une valeur de l’énumération [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) qui décrit le type du message.

`pbstrMessage`\
à Retourne le message.

`pdwType`\
à Retourne le type du message, à l’aide des conventions de la `MessageBox` fonction Win32. Pour plus d’informations, consultez la fonction [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) .

`pbstrHelpFileName`\
[in, out] Retourne le nom du fichier d’aide. Peut être une valeur null (C++) ou vide (C#) s’il n’y a aucun fichier d’aide.

`pdwHelpId`\
[in, out] Retourne l’identificateur d’aide. Peut avoir la valeur 0 si aucune aide n’est associée à ce message.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="see-also"></a>Voir aussi
- [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)
- [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)
- [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)
