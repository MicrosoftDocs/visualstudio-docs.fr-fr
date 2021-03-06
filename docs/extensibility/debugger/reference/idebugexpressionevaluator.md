---
description: Cette interface représente l’évaluateur d’expression.
title: IDebugExpressionEvaluator | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator
helpviewer_keywords:
- IDebugExpressionEvaluator interface
ms.assetid: 0636d8c3-625a-49fa-94b6-516f22b7e1bc
author: acangialosi
ms.author: anthc
manager: jmartens
ms.workload:
- vssdk
ms.openlocfilehash: b2e1fb465155bac2aa4be2b0d0a041715bf63bfa
ms.sourcegitcommit: 4b323a8a8bfd1a1a9e84f4b4ca88fa8da690f656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102152349"
---
# <a name="idebugexpressionevaluator"></a>IDebugExpressionEvaluator
> [!IMPORTANT]
> Dans Visual Studio 2015, cette façon d’implémenter les évaluateurs d’expression est déconseillée. Pour plus d’informations sur l’implémentation des évaluateurs d’expression CLR, consultez [évaluateur d’expression CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) et [exemple évaluateur d’expression managée](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

Cette interface représente l’évaluateur d’expression.

## <a name="syntax"></a>Syntaxe

```
IDebugExpressionEvaluator : IUnknown
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
L’évaluateur d’expression doit implémenter cette interface.

## <a name="notes-for-callers"></a>Notes pour les appelants
Pour obtenir cette interface, instanciez l’évaluateur d’expression par le biais de la `CoCreateInstance` méthode en utilisant l’ID de classe (CLSID) de l’évaluateur. Consultez l’exemple.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
Le tableau suivant présente les méthodes de `IDebugExpressionEvaluator` .

|Méthode|Description|
|------------|-----------------|
|[Analyser](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md).|Convertit une chaîne d’expression en expression analysée.|
|[GetMethodProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md)|Obtient les variables locales, les arguments et les autres propriétés d’une méthode.|
|[GetMethodLocationProperty](../../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty.md)|Convertit un emplacement et un offset de méthode en une adresse mémoire.|
|[SetLocale](../../../extensibility/debugger/reference/idebugexpressionevaluator-setlocale.md)|Détermine la langue à utiliser pour créer des résultats imprimables.|
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugexpressionevaluator-setregistryroot.md)|Définit la racine du Registre. Utilisé pour le débogage côte à côte.|

## <a name="remarks"></a>Notes
Dans une situation classique, le moteur de débogage (DE) instancie l’évaluateur d’expression (EE) à la suite d’un appel à [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md). Étant donné que le DE sait la langue et le fournisseur de l’EE qu’il souhaite utiliser, le service DE obtient le CLSID de EE à partir du Registre (le [Kit d’aide du SDK pour la fonction de débogage](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) , `GetEEMetric` , facilite cette récupération).

Après l’instanciation de l’EE, les appels DE l' [analysent](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) pour analyser l’expression et la stocker dans un objet [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) . Par la suite, un appel à [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) évalue l’expression.

## <a name="requirements"></a>Configuration requise
En-tête : EE. h

Espace de noms : Microsoft. VisualStudio. Debugger. Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="example"></a>Exemple
Cet exemple montre comment instancier l’évaluateur d’expression en fonction d’un fournisseur de symboles et d’une adresse dans le code source. Cet exemple utilise une fonction, `GetEEMetric` , à partir des [applications auxiliaires du kit de développement logiciel (SDK) pour la bibliothèque de débogage](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) , dbgmetric. lib.

```cpp
IDebugExpressionEvaluator GetExpressionEvaluator(IDebugSymbolProvider pSymbolProvider,
                                                 IDebugAddress *pSourceAddress)
{
    // This is typically defined globally but is specified here just
    // for this example.
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";

    IDebugExpressionEvaluator *pEE = NULL;
    if (pSymbolProvider != NULL && pSourceAddress != NULL) {
        HRESULT hr         = S_OK;
        GUID  languageGuid = { 0 };
        GUID  vendorGuid   = { 0 };

        hr = pSymbolProvider->GetLanguage(pSourceAddress,
                                          &languageGuid,
                                          &vendorGuid);
        if (SUCCEEDED(hr)) {
            CLSID clsidEE = { 0 };
            CComPtr<IDebugExpressionEvaluator> spExpressionEvaluator;
            // Get the expression evaluator's CLSID from the registry.
            ::GetEEMetric(languageGuid,
                          vendorGuid,
                          metricCLSID,
                          &clsidEE,
                          strRegistrationRoot);
            if (!IsEqualGUID(clsidEE,GUID_NULL)) {
                // Instantiate the expression evaluator.
                spExpressionEvaluator.CoCreateInstance(clsidEE);
            }
            if (spExpressionEvaluator != NULL) {
                pEE = spExpressionEvaluator.Detach();
            }
        }
    }
    return pEE;
}
```

## <a name="see-also"></a>Voir aussi
- [Interfaces d’évaluation des expressions](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [Programmes d’assistance SDK pour le débogage](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
