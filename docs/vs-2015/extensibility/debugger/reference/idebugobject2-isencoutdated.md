---
title: 'IDebugObject2:: isencveraltet | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fa4acd0476a0df75644738840da562db97a34bf6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840962"
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Methode bestimmt, ob der Status "Bearbeiten und Fortfahren" dieses Objekts oder des übergeordneten Containers veraltet ist. Eine benutzerdefinierte Ausdrucks Auswertung implementiert diese Methode nicht und gibt immer zurück `E_NOTIMPL` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```csharp  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pfEncOutdated`  
 vorgenommen Ungleich NULL ( `TRUE` ), wenn der Zustand "Bearbeiten und Fortfahren" veraltet ist, andernfalls "Null" ( `FALSE` ).  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.  
  
> [!NOTE]
> Eine benutzerdefinierte Ausdrucks Auswertung sollte immer zurückgeben `E_NOTIMPL` .  
  
## <a name="see-also"></a>Weitere Informationen  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
