---
title: 'IEnumDebugBoundBreakpoints2:: Clone | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugBoundBreakpoints2::Clone
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Clone
ms.assetid: c6ce01a2-7da3-46ec-9837-855042fa7244
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: afb09755154227d9a3dfe81f825bbed2a514cf2e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68196119"
---
# <a name="ienumdebugboundbreakpoints2clone"></a>IEnumDebugBoundBreakpoints2::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Gibt eine Kopie der aktuellen Enumeration als ein separates Objekt zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Gibt eine Kopie dieser Enumeration als ein separates Objekt zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Kopie der-Enumeration hat denselben Zustand wie die ursprüngliche, wenn diese Methode aufgerufen wird. Allerdings sind die Status der Kopier-und ursprünglichen Zustände getrennt und können einzeln geändert werden.  
  
## <a name="see-also"></a>Weitere Informationen  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)
