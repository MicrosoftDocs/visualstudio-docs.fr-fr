---
title: IDebugAlias2::GetAppDomainId | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetAppDomainId
- IDebugAlias2::GetAppDomainId
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8a2c766a1ec6fce1856312756adad3c5f234866
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492785"
---
# <a name="idebugalias2getappdomainid"></a>IDebugAlias2::GetAppDomainId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDebugAlias2::GetAppDomainId](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugalias2-getappdomainid).  
  
Récupère l’identificateur pour le domaine d’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetAppDomainId (  
   ULONG32* pappDomainId  
);  
```  
  
```csharp  
int GetAppDomainId (  
   out uint pappDomainId  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pappDomainId`  
 [out] Retourne l’identificateur de domaine d’application.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Les modifications d’identificateur de domaine application chaque fois que l’application est redémarrée et un nouveau domaine d’application est créé.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)
