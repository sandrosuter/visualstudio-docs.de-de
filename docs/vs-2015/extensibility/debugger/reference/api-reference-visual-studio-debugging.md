---
title: API-Referenz (Visual Studio-Debuggen) | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f3e95200cf29c8561798c858635c3864d635fb40
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840957"
---
# <a name="api-reference-visual-studio-debugging"></a>API-Referenz (Visual Studio-Debugging)
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Der Referenz Abschnitt enthält eine konzeptionelle Übersicht über die API, eine Anleitung, die die Syntax und Verwendung für alle API-Elemente sowie eine Reihe von Codebeispielen zeigt. Alle Verweise sind alphabetisch nach Kategorie aufgelistet.  
  
 In der folgenden Tabelle werden die `HRESULT` von-Methoden zurückgegebenen allgemeinen Werte angezeigt.  
  
|name|BESCHREIBUNG|Wert|  
|----------|-----------------|-----------|  
|S_OK|Erfolg.|0x00000000|  
|E_UNEXPECTED|Unerwarteter Fehler.|0x8000FFFF|  
|E_NOTIMPL|Nicht implementiert.|0x80004001|  
|E_OUTOFMEMORY|Der Arbeitsspeicher reicht nicht aus, um den Vorgang abzuschließen.|0x8007000E|  
|E_INVALIDARG|Mindestens ein Argument ist ungültig.|0x80070057|  
|E_NOINTERFACE|Diese Schnittstelle wird nicht unterstützt.|0x80004002|  
|E_POINTER|Ungültiger Zeiger.|0x80004003|  
|E_HANDLE|Ungültiges Handle.|0x80070006|  
|E_ABORT|Der Vorgang wurde abgebrochen.|0x80004004|  
|E_FAIL|Unerwarteter Fehler.|0x80004005|  
|E_ACCESSDENIED|Allgemeiner Zugriffs Verweigerungs Fehler.|0x80070005|  
  
> [!NOTE]
> Wenn eine [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Debugmethode zurückgibt `S_OK` , wird davon ausgegangen, dass alle out-Parameter Zeiger gültig sind, d. h., es wird keine Validierung für Out-Parameter Zeiger durchgeführt, wenn `S_OK` zurückgegeben wird.  
  
> [!NOTE]
> Ungültige `NULL` Parameter oder [out]-Parameter verursachen möglicherweise einen Absturz der IDE.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Web](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Strukturen und Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [SDK-Hilfsprogramme zum Debuggen](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Visual Studio Debugger-Erweiterbarkeit](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)
