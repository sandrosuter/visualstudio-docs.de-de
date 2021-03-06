---
title: Modell eines Legacy sprach Dienstanbieter | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, model
ms.assetid: d8ae1c0c-ee3d-4937-a581-ee78d0499793
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 27d51df6dd11509b86e6648d59978b87d9cd8a02
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68157656"
---
# <a name="model-of-a-legacy-language-service"></a>Modell eines Legacysprachdiensts
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ein Sprachdienst definiert die Elemente und Features für eine bestimmte Sprache und wird verwendet, um dem Editor spezifische Informationen für diese Sprache bereitzustellen. Der Editor muss z. b. die Elemente und Schlüsselwörter der Sprache kennen, um die Syntax Farbgebung zu unterstützen.  
  
 Der Sprachdienst arbeitet eng mit dem vom Editor verwalteten Text Puffer und der Ansicht, die den Editor enthält, zusammen. Die Microsoft IntelliSense **Quick Info** -Option ist ein Beispiel für eine Funktion, die von einem Sprachdienst bereitgestellt wird.  
  
## <a name="a-minimal-language-service"></a>Ein minimaler Sprachdienst  
 Der grundlegendste Sprachdienst enthält die folgenden beiden Objekte:  
  
- Der *Sprachdienst* implementiert die- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> Schnittstelle. Ein Sprachdienst enthält Informationen zur Sprache, einschließlich des Namens, der Dateinamen Erweiterungen, des Code Fenster-Managers und der Farbauswahl.  
  
- Die *Farbgebung* implementiert die- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> Schnittstelle.  
  
  Die folgende konzeptionelle Zeichnung zeigt ein Modell eines grundlegenden sprach Dienstanbieter.  
  
  ![Grafik zum Sprachdienstmodell](../../extensibility/media/vslanguageservicemodel.gif "vslanguageservicemodel")  
  Basic-Sprachdienst Modell  
  
  Das Dokument Fenster hostet die *Dokument Ansicht* des Editors, in diesem Fall der [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Kern Editor. Die Dokument Ansicht und der Text Puffer befinden sich im Besitz des Editors. Diese Objekte funktionieren mit [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] über ein spezielles Dokument Fenster, das als *Code Fenster*bezeichnet wird. Das Code Fenster ist in einem <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> Objekt enthalten, das von der IDE erstellt und gesteuert wird.  
  
  Wenn eine Datei mit einer bestimmten Erweiterung geladen wird, sucht der Editor den Sprachdienst, der dieser Erweiterung zugeordnet ist, und übergibt das Code Fenster durch Aufrufen der- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> Methode. Der Sprachdienst gibt einen *Code Fenster-Manager*zurück, der die- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> Schnittstelle implementiert.  
  
  In der folgenden Tabelle finden Sie eine Übersicht über die Objekte im Modell.  
  
|Komponente|Objekt|Funktion|  
|---------------|------------|--------------|  
|Text Puffer|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>|Ein Unicode-Lese-/Schreib-Textstream. Es ist möglich, dass Text andere Codierungen verwendet.|  
|Codefenster|<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>|Ein Dokument Fenster, das mindestens eine Textansicht enthält. Wenn [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sich im MDI-Modus (Multiple Document Interface) befindet, ist das Code Fenster ein untergeordnetes MDI-Element.|  
|Text Ansicht|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>|Ein Fenster, in dem der Benutzer mithilfe der Tastatur und der Maus navigieren und Text anzeigen kann. Dem Benutzer wird eine Textansicht als Editor angezeigt. Sie können Text Ansichten in normalen Editor Fenstern, im Ausgabefenster und im direkt Fenster verwenden. Darüber hinaus können Sie eine oder mehrere Text Ansichten innerhalb eines Code Fensters konfigurieren.|  
|Text-Manager|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>Wird vom Dienst verwaltet, von dem Sie einen Zeiger erhalten. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager>|Eine Komponente, die allgemeine Informationen verwaltet, die von allen zuvor beschriebenen Komponenten gemeinsam genutzt werden.|  
|Sprachdienst|Implementierungsabhängig; implementiert <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>|Ein Objekt, das den Editor sprachspezifische Informationen wie Syntax Hervorhebung, Anweisungs Vervollständigung und zugehörige Klammern bereitstellt.|  
  
## <a name="see-also"></a>Weitere Informationen  
 [Dokumentdaten und Dokumentansicht in benutzerdefinierten Editoren](../../extensibility/document-data-and-document-view-in-custom-editors.md)
