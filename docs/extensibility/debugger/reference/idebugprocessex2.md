---
title: IDebugProcessEx2 | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 743dd1aa72d9b8db6b848618c8a2ad6c8c8ecaaf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80723330"
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
Mit dieser Schnittstelle kann der Sitzungs-Debug-Manager (SDM) einen Prozess Benachrichtigen, der an den Prozess angefügt oder von diesem getrennt wird.

## <a name="syntax"></a>Syntax

```
IDebugProcessEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Hinweise für Implementierer
 Ein benutzerdefinierter Port Lieferant implementiert diese Schnittstelle für das gleiche Objekt wie die [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) -Schnittstelle, um Folgendes zu tun:

- Unterstützung der Nachverfolgung von mit einem Prozess verbundenen Sitzungen

- Unterstützung für Automatisches Anfügen über mehrere Debug-engines hinweg

  Der benutzerdefinierte portlieferant kann diese Schnittstelle implementieren, wenn er Sie auswählt.

## <a name="notes-for-callers"></a>Hinweise für Aufrufer

- Der SDM ruft [QueryInterface](/cpp/atl/queryinterface) für eine `IDebugProcess2` Schnittstelle auf, um diese Schnittstelle zu erhalten.

## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge
 In der folgenden Tabelle sind die Methoden von aufgeführt `IDebugProcessEx2` .

|Methode|BESCHREIBUNG|
|------------|-----------------|
|[Anfügen](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|Informiert den Prozess, dass eine Sitzung den Prozess jetzt debuggt.|
|[Trennen](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|Informiert den Prozess, dass eine Sitzung den Prozess nicht mehr debuggt.|
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|Fügt Programmknoten für eine Liste von Debug-engines hinzu.|

## <a name="remarks"></a>Bemerkungen
 Diese Schnittstelle ist für die SDM und den Prozess privat.

## <a name="requirements"></a>Anforderungen
 Header: portpriv. h

 Namespace: Microsoft. VisualStudio. Debugger. Interop

 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Weitere Informationen
- [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
