---
title: MODULE_INFO | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 04a8756fd7eb2a4b938ebcd2d5f4754509b704e3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68205219"
---
# <a name="module_info"></a>MODULE_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Beschreibt ein bestimmtes Modul (dll, exe oder Assembly).  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```csharp  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## <a name="members"></a>Member  
 dwvalidfields  
 Eine Kombination von Flags aus der [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md) Enumeration, die angibt, welche Felder ausgefüllt werden.  
  
 m_bstrName  
 Der Modulname.  
  
 m_bstrUrl  
 Die Modul-URL.  
  
 m_bstrVersion  
 Die Modulversion.  
  
 m_bstrDebugMessage  
 Eine optionale Meldung zum Modul, z. b. "Symbole können nicht geladen werden."  
  
 m_addrLoadAddress  
 Die Lade Adresse des Moduls.  
  
 m_addrPreferredLoadAddress  
 Die bevorzugte Lade Adresse des Moduls.  
  
 m_dwSize  
 Die Modulgröße.  
  
 m_dwLoadOrder  
 Die Lade Reihenfolge des Moduls.  
  
 m_TimeStamp  
 Der Zeitpunkt, zu dem die Symbol Datei zuletzt geändert wurde.  
  
 m_bstrUrlSymbolLocation  
 Der Speicherort der Symbol Datei (z. b. ". \\ "), die im Modul angegeben ist. Wird als Ausgangs Speicherort zum Suchen von Symbolen für ein Modul verwendet.  
  
 m_dwModuleFlags  
 Eine Kombination von Flags aus der [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md) Enumeration, die das Modul beschreibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Struktur wird an die [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) -Methode, in der Sie ausgefüllt ist, übermittelt.  
  
 Diese Struktur entspricht den im Fenster **Module aufgeführten Modulen** .  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg. h  
  
 Namespace: Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Weitere Informationen  
 [Strukturen und Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
