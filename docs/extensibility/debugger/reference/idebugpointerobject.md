---
title: Idebugpointerobject | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject
helpviewer_keywords:
- IDebugPointerObject interface
ms.assetid: 257fa167-b46e-4ffb-9a12-272efbf26702
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4b28189b3f0a07a27f5e4478f64963a63d634db5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80725491"
---
# <a name="idebugpointerobject"></a>IDebugPointerObject
> [!IMPORTANT]
> In Visual Studio 2015 ist diese Art der Implementierung von Ausdrucks auswergratoren veraltet. Weitere Informationen zum Implementieren von CLR-Ausdrucks Auswerters finden Sie unter [CLR-Ausdrucks](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) Auswertungen und [Beispiel für verwaltete Ausdrucks Auswertung](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Diese Schnittstelle stellt ein Zeiger Objekt dar.

## <a name="syntax"></a>Syntax

```
IDebugPointerObject : IDebugObject
```

## <a name="notes-for-implementers"></a>Hinweise für Implementierer
 Die Ausdrucks Auswertung implementiert diese Schnittstelle, um ein Zeiger Objekt darzustellen.

## <a name="notes-for-callers"></a>Hinweise für Aufrufer
 Die [idebugobject](../../../extensibility/debugger/reference/idebugobject.md) -Schnittstelle kann diese Schnittstelle mithilfe von [QueryInterface](/cpp/atl/queryinterface) abrufen, wenn der `IDebugObject` einen Zeiger darstellt.

## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge
 Zusätzlich zu den Methoden, die von [idebugobject](../../../extensibility/debugger/reference/idebugobject.md)geerbt werden, stellt die- `IDebugPointerObject` Schnittstelle die folgenden Methoden zur Verfügung.

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[Dereference](../../../extensibility/debugger/reference/idebugpointerobject-dereference.md)|Ruft das-Objekt ab, auf das die-Schnittstelle zeigt.|
|[GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)|Ruft den Wert ab, auf den die Schnittstelle als Folge von aufeinander folgenden Bytes zeigt.|
|[SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)|Legt den Wert fest, auf den die Schnittstelle aus einer Reihe von aufeinander folgenden Bytes zeigt.|

## <a name="remarks"></a>Bemerkungen
 Eine Ausdrucks Auswertung verwendet diese Schnittstelle, um einen Zeiger in einer Analyse Struktur darzustellen.

## <a name="requirements"></a>Anforderungen
 Header: EE. h

 Namespace: Microsoft. VisualStudio. Debugger. Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Weitere Informationen
- [Expression Evaluation Interfaces](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
