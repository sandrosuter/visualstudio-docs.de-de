---
title: 'Test Bereich 6: Löschen | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], deleting items
- source control plug-ins, deleting items
ms.assetid: 6f2e872c-5ba2-4303-9f50-a90cef9a6225
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3ffe786b5bc5f6d0bb0233fbb431988e0145611d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68155934"
---
# <a name="test-area-6-delete"></a>Testbereich 6: Löschen
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Dieser Testbereich des Quell Code Verwaltungs-Plug-ins deckt Lösch Aktionen ab.  
  
 Die Quell Code Verwaltung antwortet auf Lösch Aktionen in **Projektmappen-Explorer**.  
  
 Im folgenden finden Sie eine Liste von Elementen, die gelöscht werden können:  
  
- Dateien  
  
- Ordner  
  
- Project  
  
  Abhängig vom Projekttyp können Sie das Projekt **Entfernen** (die Dateien auf dem Datenträger belassen) oder das Projekt **Löschen** (entfernt die Dateien auf dem Datenträger). Mit beiden Aktionen wird das Projekt oder das Element aus **Projektmappen-Explorer**entfernt.  
  
## <a name="expected-behavior"></a>Erwartetes Verhalten  
 Das erwartete Verhalten für die Testfälle im Lösch Testbereich lautet wie folgt:  
  
- Das gelöschte Element ist in **Projektmappen-Explorer**nicht mehr sichtbar.  
  
- Das übergeordnete Element des gelöschten Projekts oder Elements wird bei Bedarf (möglicherweise mit einer Eingabeaufforderung) ausgecheckt.  
  
- Nachdem Sie ein ausgechecktes oder hinzugefügtes Element gelöscht haben, wird es nicht im Fenster **ausstehende Eincheck** Vorgänge angezeigt.  
  
- Das Element ist auch nach dem Löschvorgang im Quell Code Verwaltungs Speicher vorhanden und muss manuell gelöscht werden.  
  
|Aktion|Test Schritte|Erwartete Ergebnisse zur Überprüfung|  
|------------|----------------|--------------------------------|  
|Löschen eines Client Projekts|1. Erstellen Sie ein Client Projekt.<br />2. Fügen Sie die Projekt Mappe der Quell Code Verwaltung hinzu.<br />3. entfernen Sie das gesamte Projekt aus der Projekt Mappe.|Häufiges erwartetes Verhalten.|  
|Löschen einer leeren Datei|1. Erstellen Sie ein Client Projekt.<br />2. Fügen Sie dem Projekt eine 0-Byte-Datei hinzu.<br />3. Fügen Sie die Projekt Mappe der Quell Code Verwaltung hinzu.<br />4. Wählen Sie die Datei aus, und löschen Sie Sie.|Häufiges erwartetes Verhalten.|  
|Löschen eines Ordners mit einer Datei|1. Erstellen Sie eine einzelne Projekt Mappe.<br />2. Fügen Sie einen Ordner hinzu.<br />3. Fügen Sie dem Ordner eine Datei hinzu.<br />4. Fügen Sie die Projekt Mappe der Quell Code Verwaltung hinzu.<br />5. Überprüfen Sie das Projekt, um Aufforderungen zu vermeiden.<br />6. löschen Sie den Ordner.|Häufiges erwartetes Verhalten.|  
|Löschen eines Datei System-Webprojekts|1. Erstellen Sie ein Datei System-Webprojekt (verwenden Sie die Schaltfläche zum Durchsuchen, um einen UNC-Pfad anzugeben).<br />2. Fügen Sie die Projekt Mappe der Quell Code Verwaltung hinzu.<br />3. entfernen Sie das gesamte Projekt aus der Projekt Mappe.<br />4. Wiederholen Sie die Schritte 1 bis 3 für ein lokales Webprojekt (führt verschiedene Pfade durch den Code aus, weist jedoch die gleiche externe Schnittstelle und das gleiche Verhalten auf).|Häufiges erwartetes Verhalten.|  
|Löschen einer Datei aus einem Datei System-Webprojekt|1. Erstellen Sie ein Datei System-Webprojekt.<br />2. Fügen Sie die Projekt Mappe der Quell Code Verwaltung hinzu.<br />3. löschen Sie eine Datei aus dem Projekt.<br />4. Wiederholen Sie die Schritte 1 bis 3 für ein lokales Webprojekt (führt verschiedene Pfade durch den Code aus, weist jedoch die gleiche externe Schnittstelle und das gleiche Verhalten auf).|Häufiges erwartetes Verhalten.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Testleitfaden für Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
