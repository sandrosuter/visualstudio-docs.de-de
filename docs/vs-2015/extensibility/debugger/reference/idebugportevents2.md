---
title: IDebugPortEvents2 | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5e0f6455e6df8db88b1aae1a7b7f6965c0ee524b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68188528"
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Schnittstelle benachrichtigt einen Listener (in der Regel der Sitzungs-Debug-Manager [SDM] oder eine Debug-Engine) über Prozess-und Programm Erstellung und Zerstörung an einem bestimmten Port. Diese Informationen können verwendet werden, um eine Echtzeitansicht der Prozesse und Programme anzuzeigen, die auf dem Port ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Diese Schnittstelle wird von Visual Studio normalerweise implementiert, um Benachrichtigungen über Programm Erstellung und-Löschung zu erhalten. Eine Debug-Engine kann diese Schnittstelle auch implementieren, um auf solche Port Ereignisse zu lauschen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Alle [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) -Schnittstellen können für eine Schnittstelle abgefragt werden <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> . Anschließend wird die- <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> Methode für `IDebugPortEvents2` in der- <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> Schnittstelle aufgerufen, um eine <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> Schnittstelle zu erhalten. Zum Schluss wird die- <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> Methode in der- <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> Schnittstelle aufgerufen, um die Ereignisse über die- [Ereignis](../../../extensibility/debugger/reference/idebugportevents2-event.md) Methode zu senden.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 In der folgenden Tabelle wird die-Methode von gezeigt `IDebugPortEvents2` .  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Sendet Ereignisse, die die Erstellung und Zerstörung von Prozessen und Programmen auf dem Port beschreiben.|  
  
## <a name="remarks"></a>Bemerkungen  
 `IDebugPortEvents2` wird auch von SDM zum Debuggen von Programmen verwendet, die in einem Prozess ausgeführt werden, der bereits debuggt wird.  
  
 Port Ereignisse werden von dieser Schnittstelle an SDM übermittelt.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg. h  
  
 Namespace: Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Weitere Informationen  
 [Kern Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
