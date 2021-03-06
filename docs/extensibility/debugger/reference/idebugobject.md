---
title: Idebugobject | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject
helpviewer_keywords:
- IDebugObject interface
ms.assetid: 05cd8bf4-c9ee-4b49-b782-2263c33067d6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6801176964a47646f03091131e1be89cf63c97f8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726310"
---
# <a name="idebugobject"></a>IDebugObject
> [!IMPORTANT]
> In Visual Studio 2015 ist diese Art der Implementierung von Ausdrucks auswergratoren veraltet. Weitere Informationen zum Implementieren von CLR-Ausdrucks Auswerters finden Sie unter [CLR-Ausdrucks](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) Auswertungen und [Beispiel für verwaltete Ausdrucks Auswertung](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Diese Schnittstelle stellt ein Objekt dar, das der Binder erstellt, um die Werte von Symbolen und Ausdrücken zu kapseln.

## <a name="syntax"></a>Syntax

```
IDebugObject : IUnknown
```

## <a name="notes-for-implementers"></a>Hinweise für Implementierer
 Eine Ausdrucks Auswertung implementiert diese Schnittstelle, um ein Objekt darzustellen.

## <a name="notes-for-callers"></a>Hinweise für Aufrufer
 Diese Schnittstelle ist die Basisklasse für alle Objekte, die von der Ausdrucks Auswertung in analysierten Ausdrücken verwendet werden. Sie wird durch einen-Rückruf der [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md) -Methode zurückgegeben. [QueryInterface](/cpp/atl/queryinterface) Ruft die spezielleren Schnittstellen von dieser Schnittstelle ab.

## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge
 In der folgenden Tabelle sind die Methoden von aufgeführt `IDebugObject` .

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)|Ruft die Größe des-Objekts ab.|
|[GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)|Ruft den Wert des-Objekts als aufeinander folgende Reihe von Bytes ab.|
|[SetValue](../../../extensibility/debugger/reference/idebugobject-setvalue.md)|Legt den Wert des-Objekts aus einer aufeinanderfolgenden Reihe von Bytes fest.|
|[SetReferenceValue](../../../extensibility/debugger/reference/idebugobject-setreferencevalue.md)|Legt den Verweis Wert dieses-Objekts fest.|
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugobject-getmemorycontext.md)|Ruft den Arbeitsspeicher Kontext ab, der die Adresse des Werts des-Objekts darstellt.|
|[GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md)|Erstellt eine Kopie des verwalteten Objekts im Adressraum der Debug-Engine.|
|[IsNullReference](../../../extensibility/debugger/reference/idebugobject-isnullreference.md)|Testet, ob dieses Objekt ein NULL-Verweis ist.|
|[IsEqual](../../../extensibility/debugger/reference/idebugobject-isequal.md)|Vergleicht ein-Objekt mit diesem-Objekt.|
|[IsReadOnly](../../../extensibility/debugger/reference/idebugobject-isreadonly.md)|Bestimmt, ob dieses-Objekt schreibgeschützt ist.|
|[IsProxy](../../../extensibility/debugger/reference/idebugobject-isproxy.md)|Bestimmt, ob es sich bei dem Objekt um einen transparenten Proxy handelt.|

## <a name="remarks"></a>Bemerkungen
 Die Ausdrucks Auswertung verwendet diese Schnittstelle als Basisklasse, um Objekte in einer Analyse Struktur darzustellen.

## <a name="requirements"></a>Anforderungen
 Header: EE. h

 Namespace: Microsoft. VisualStudio. Debugger. Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Weitere Informationen
- [Expression Evaluation Interfaces](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)
- [Zwick](../../../extensibility/debugger/reference/idebugbinder-bind.md)
