---
title: 'IDebugBoundBreakpoint2:: Abbild Anzahl | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 292e36878594841f200f744f2809256b05e84d94
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68156190"
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Legt die Treffer Anzahl für den gebundenen Haltepunkt fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```csharp  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwHitCount`  
 in Die festzulegende Treffer Anzahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben. Gibt zurück `E_BP_DELETED` , wenn der Zustand des gebundenen Haltepunkt Objekts auf festgelegt ist `BPS_DELETED` (Teil der [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) Enumeration).  
  
## <a name="remarks"></a>Bemerkungen  
 Die Treffer Anzahl gibt an, wie oft dieser Haltepunkt während der aktuellen Sitzung der Sitzung ausgelöst wurde.  
  
 Diese Methode wird in der Regel von der Debug-Engine aufgerufen, um die aktuelle Treffer Anzahl an diesem Breakpoint zu aktualisieren.  
  
## <a name="see-also"></a>Weitere Informationen  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)
