---
title: Veröffentlichen von ClickOnce-Anwendungen | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 209aac56f4648554ce619cbe31cef19a8ab1fed7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "85531793"
---
# <a name="publishing-clickonce-applications"></a>Veröffentlichen von ClickOnce-Anwendungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Beim ersten Veröffentlichen einer [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]-Anwendung können Sie die Veröffentlichungseigenschaften mit dem Webpublishing-Assistenten festlegen. Im Assistenten stehen nur wenige Eigenschaften zur Verfügung. Alle anderen Eigenschaften sind auf die Standardwerte eingestellt.  
  
 Spätere Änderungen für die Veröffentlichung der Eigenschaften können im **Projekt-Designer** auf der Seite **Veröffentlichen** vorgenommen werden.  
  
## <a name="publish-wizard"></a>Webpublishing-Assistent  
 Sie können den Webpublishing-Assistenten verwenden, um die grundlegenden Einstellungen zum Veröffentlichen der Anwendung festzulegen. Dies sind zum Beispiel die folgenden Veröffentlichungseigenschaften:  
  
- Speicherort des Veröffentlichungsordners – In diesen Ordner kopiert Visual Studio die Dateien (lokaler Computer, Netzwerkdateifreigabe, FTP-Server oder Website)  
  
- Speicherort des Installationsordners – Aus diesem Ordner führen Endbenutzer die Installation durch (Netzwerkdateifreigabe, FTP-Server, Website, CD/DVD)  
  
- Online- oder Offlineverfügbarkeit – Ob Endbenutzer mit oder ohne Netzwerkverbindung auf die Anwendung zugreifen können  
  
- Aktualisierungsrate – Wie häufig die Anwendung eine Prüfung auf neue Updates durchführt  
  
  Weitere Informationen finden Sie unter Gewusst [wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>Seite "Veröffentlichen"  
 Die Seite **Veröffentlichen** des **Projekt-Designers** wird zur Konfiguration von Eigenschaften für die ClickOnce-Bereitstellung verwendet. In der folgenden Tabelle sind Themen aufgeführt.  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Gewusst wie: Angeben des Orts, an dem Visual Studio die Dateien kopiert](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Beschreibt, wie Sie festlegen, wo Visual Studio die Anwendungsdateien und -manifeste ablegt.|  
|[Vorgehensweise: Angeben des Speicher Orts für die Installation durch Endbenutzer](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Beschreibt, wie Sie den Speicherort festlegen, auf den Benutzer zugreifen, um die Anwendung herunterzuladen und zu installieren.|  
|[Gewusst wie: Angeben des Offline-oder Online Installationsmodus von ClickOnce](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Beschreibt, wie Sie festlegen, ob die Anwendung offline oder online verfügbar sein soll.|  
|[Gewusst wie: Festlegen der ClickOnce-Veröffentlichungs Version](../deployment/how-to-set-the-clickonce-publish-version.md)|Beschreibt, wie Sie die ClickOnce-Eigenschaft **Veröffentlichungsversion** festlegen, die bestimmt, ob die veröffentlichte Anwendung als Update behandelt wird.|  
|[Gewusst wie: Automatisches Erhöhen der ClickOnce-Veröffentlichungsversion](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Beschreibt, wie Sie erreichen, dass die Revisionsnummer von **PublishVersion** jedes Mal automatisch inkrementiert wird, wenn Sie die Anwendung veröffentlichen.|  
  
 Weitere Informationen finden Sie unter [Seite "veröffentlichen", Projekt-Designer](../ide/reference/publish-page-project-designer.md)  
  
### <a name="application-files-dialog-box"></a>Dialogfeld "Anwendungsdateien"  
 In diesem Dialogfeld können Sie angeben, wie die Dateien im Projekt zur Veröffentlichung, Aktualisierung und zum dynamischen Download kategorisiert werden. Es enthält ein Raster der Projektdateien, die standardmäßig nicht ausgeschlossen sind bzw. die über eine Downloadgruppe verfügen.  
  
 Informationen zum Ausschließen von Dateien, zum Markieren von Dateien als Datendateien oder erforderliche Komponenten und zum Erstellen von Dateigruppen für die bedingte Installation in der Benutzeroberfläche von Visual Studio finden Sie unter Gewusst [wie: Angeben der von ClickOnce veröffentlichten Dateien](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Sie können Datendateien auch mit Mage.exe kennzeichnen. Weitere Informationen finden Sie unter [Vorgehensweise: Einschließen einer Datendatei in eine ClickOnce-Anwendung](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
### <a name="prerequisites-dialog-box"></a>Dialogfeld "Erforderliche Komponenten"  
 In diesem Dialogfeld wird festgelegt, welche erforderlichen Komponenten installiert werden und wie die Installation ausgeführt wird. Weitere Informationen finden Sie unter Gewusst [wie: Installieren von erforderlichen Komponenten mit einer ClickOnce-Anwendung](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) und [Voraussetzungen (Dialog Feld](../ide/reference/prerequisites-dialog-box.md)).  
  
### <a name="application-updates-dialog-box"></a>Dialogfeld "Anwendungsupdates"  
 In diesem Dialogfeld wird angegeben, wie bei der Anwendungsinstallation nach Updates gesucht werden soll. Weitere Informationen finden Sie unter Gewusst [wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](../deployment/how-to-manage-updates-for-a-clickonce-application.md).  
  
### <a name="publish-options-dialog-box"></a>Dialogfeld "Veröffentlichungsoptionen"  
 Im Dialogfeld Veröffentlichungsoptionen werden die Bereitstellungsoptionen einer Anwendung angegeben.  
  
|Titel|Beschreibung|
|-|-|  
|[Vorgehensweise: Ändern der Veröffentlichungs Sprache für eine ClickOnce-Anwendung](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Beschreibt, wie Sie eine Sprache und eine Kultur angeben, die mit der lokalisierten Version übereinstimmen.|  
|[Gewusst wie: Angeben eines Startmenü namens für eine ClickOnce-Anwendung](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|Beschreibt, wie Sie den Anzeigenamen für eine ClickOnce-Anwendung ändern.|  
|[Vorgehensweise: Angeben eines Links für technischen Support](../deployment/how-to-specify-a-link-for-technical-support.md)|Beschreibt, wie Sie die **Support-URL**-Eigenschaft festlegen, die eine Webseite oder Dateifreigabe angibt, von der Benutzer Informationen zur Anwendung abrufen können.|  
|[Gewusst wie: Angeben einer Support-URL für einzelne erforderliche Komponenten in einer ClickOnce-Bereitstellung](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Veranschaulicht, wie ein Anwendungsmanifest manuell geändert wird, um für die jeweilige erforderliche Komponente einzelne Support-URLs aufzunehmen.|  
|[Gewusst wie: Angeben einer Veröffentlichungs Seite für eine ClickOnce-Anwendung](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Beschreibt, wie Sie zusammen mit der Anwendung eine Standardwebseite (publish.htm) generieren und veröffentlichen.|  
|[Vorgehensweise: Anpassen der ClickOnce-Standardwebseite](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Beschreibt, wie Sie die Webseite anpassen, die zusammen mit der Anwendung automatisch generiert und veröffentlicht wird.|  
|[Gewusst wie: Aktivieren von AutoStart für Installationen von CD](../deployment/how-to-enable-autostart-for-cd-installations.md)|Beschreibt, wie Sie AutoStart aktivieren, damit die ClickOnce-Anwendung beim Einlegen des Datenträgers automatisch gestartet wird.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Gewusst wie: Erstellen von Dateizuordnungen für eine ClickOnce-Anwendung](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|Beschreibt, wie Sie einer ClickOnce-Anwendung die Unterstützung für Dateierweiterungen hinzufügen.|  
|[Gewusst wie: Abrufen von Abfrage Zeichenfolgen-Informationen in einer Online-ClickOnce-Anwendung](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|Veranschaulicht, wie die Parameter aus der URL abgerufen werden, mit denen eine ClickOnce-Anwendung ausgeführt wird.|  
|[Gewusst wie: Deaktivieren der URL-Aktivierung von ClickOnce-Anwendungen mithilfe des Designers](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Beschreibt, wie Sie mit dem Designer vorgeben können, dass Benutzer die Anwendung über das Menü **Start** starten müssen.|  
|[Gewusst wie: Deaktivieren der URL-Aktivierung von ClickOnce-Anwendungen](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Beschreibt, wie Sie vorgeben können, dass Benutzer die Anwendung über das Menü **Start** starten müssen.|  
|[Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der ClickOnce-Bereitstellungs-API mit](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Erklärt, wie Anwendungsassemblys erst bei der ersten Verwendung durch die Anwendung mit dem Designer heruntergeladen werden.|  
|[Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Erklärt, wie Anwendungsassemblys erst bei der ersten Verwendung durch die Anwendung heruntergeladen werden.|  
|[Exemplarische Vorgehensweise: Herunterladen von Satellitenassemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Beschreibt, wie Sie Ihre Satellitenassemblys als optional kennzeichnen und nur die Assembly herunterladen, die ein Clientcomputer für die eigenen aktuellen Kultureinstellungen benötigt.|  
|[Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|Erklärt, wie .NET Framework-Dienstprogramme verwendet werden, um ClickOnce-Anwendungen bereitzustellen.|  
|[Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung, die kein erneutes Signieren erfordert und Brandinginformationen beibehält](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required?view=vs-2015)|Erklärt, wie .NET Framework-Hilfsprogramme verwendet werden, um die ClickOnce-Anwendung bereitzustellen, ohne die Manifeste neu zu signieren.|  
|[NIB: Gewusst wie: Optimieren einer Anwendung für einen bestimmten CPU-Typ](https://msdn.microsoft.com/294a75d2-4279-4b72-8298-2bea05be907a)|Erklärt, wie Sie die Veröffentlichung für einen 64-Bit-Prozessor durchführen, indem Sie im Projekt die Eigenschaft **Ziel-CPU** oder **Plattformziel** ändern.|  
|[Exemplarische Vorgehensweise: Aktivieren einer ClickOnce-Anwendung für die Ausführung auf mehreren .NET Framework Versionen](https://msdn.microsoft.com/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Erklärt, wie Sie eine ClickOnce-Anwendung so aktivieren, dass sie auf mehreren Versionen von .NET Framework installiert und ausgeführt wird.|  
|[Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Installers für eine ClickOnce-Anwendung](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Erklärt, wie Sie ein benutzerdefiniertes Installationsprogramm erstellen, um eine ClickOnce-Anwendung zu installieren.|  
|[Gewusst wie: Veröffentlichen einer WPF-Anwendung mit aktivierten visuellen Stilen](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Stellt detaillierte Anweisungen zum Auflösen eines Fehlers bereit, der angezeigt wird, wenn Sie versuchen, eine WPF-Anwendung zu veröffentlichen, bei der visuelle Stile aktiviert sind.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [ClickOnce-Sicherheit und-Bereitstellung](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce-Referenz](../deployment/clickonce-reference.md)
