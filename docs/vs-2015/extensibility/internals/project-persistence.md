---
title: Projekt Persistenz | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- persistence, projects
- projects [Visual Studio SDK], persistance
ms.assetid: 42907bcf-4e27-46bd-a8cb-01c2ccd2bde5
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: abbcc1fc1048866ef790a4b6779ed15ef80a9be1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "62429521"
---
# <a name="project-persistence"></a>Projektpersistenz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Persistenz ist ein wichtiger Entwurfs Aspekt für Ihr Projekt. In den meisten Projekten werden Projekt Elemente verwendet, die Dateien darstellen. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] unterstützt auch Projekte, deren Daten nicht Datei basiert sind. Die Dateien, die sich im Besitz des Projekts befinden, und die Projektdatei müssen persistent gespeichert werden. Die IDE weist das Projekt an, sich selbst oder ein Projekt Element zu speichern.  
  
 Vorlagen für Projekte werden an die projektfactory übermittelt. Die Vorlagen sollten die Initialisierung aller Projekt Elemente gemäß den Anforderungen des jeweiligen Projekt Typs unterstützen. Diese Vorlagen können später als Projektdateien gespeichert und über die Lösung von der IDE verwaltet werden. Weitere Informationen finden Sie unter [Erstellen von Projekt Instanzen mithilfe von projektfactorys](../../extensibility/internals/creating-project-instances-by-using-project-factories.md) und- [Lösungen](../../extensibility/internals/solutions-overview.md).  
  
 Projekt Elemente können Datei basiert oder nicht Datei basiert sein:  
  
- Dateibasierte Elemente können lokal oder Remote sein. In Webprojekten in c# werden z. b. Verbindungen mit Dateien auf einem Remote System lokal gespeichert, während die Dateien selbst auf dem Remote System gespeichert werden.  
  
- Nicht dateibasierte Elemente können Elemente in einer Datenbank oder in einem Repository speichern.  
  
## <a name="commit-models"></a>Commit-Modelle  
 Nachdem Sie entschieden haben, wo sich die Projekt Elemente befinden, müssen Sie das entsprechende Commit-Modell auswählen. Beispielsweise kann in einem dateibasierten Modell mit lokalen Dateien jedes Projekt autonom gespeichert werden. In einem Repository-Modell können Sie mehrere Elemente in einer Transaktion speichern. Weitere Informationen finden Sie unter [Entwurfsentscheidungen für Projekttyp](../../extensibility/internals/project-type-design-decisions.md).  
  
 Zum Ermitteln von Dateinamen Erweiterungen implementieren Projekte die- <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> Schnittstelle, die Informationen bereitstellt, die es dem Client eines Objekts ermöglichen, das Dialogfeld " **Speichern** unter" zu implementieren – d. h., in die Dropdown Liste " **Dateityp** " einzuschließen und die anfängliche Dateinamenerweiterung zu verwalten.  
  
 Die IDE Ruft die- `IPersistFileFormat` Schnittstelle für das Projekt auf, um anzugeben, dass das Projekt die Projekt Elemente entsprechend beibehalten soll. Daher besitzt das Objekt alle Aspekte seiner Datei und des Formats. Dies schließt den Namen des-Objekts ein.  
  
 Wenn Elemente keine Dateien sind, wird weiterhin festgehalten, `IPersistFileFormat` wie nicht dateibasierte Elemente beibehalten werden. Projektdateien, z. b. vbp-Dateien für [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] Projekte oder VCPROJ-Dateien für [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] Projekte, müssen ebenfalls persistent gespeichert werden.  
  
 Bei Save-Aktionen prüft die IDE die ausgeführten Dokumenten Tabellen (RDT), und die Hierarchie übergibt die Befehle an die <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> -Schnittstelle und die- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> Schnittstelle. Die- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.IsItemDirty%2A> Methode wird implementiert, um zu bestimmen, ob das Element geändert wurde. Wenn das Element aufweist, wird die- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem.SaveItem%2A> Methode implementiert, um das geänderte Element zu speichern.  
  
 Die Methoden der- `IVsPersistHierarchyItem2` Schnittstelle werden verwendet, um zu bestimmen, ob ein Element erneut geladen werden kann, und ob es das Element sein kann, um es neu zu laden. Außerdem kann die- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IgnoreItemFileChanges%2A> Methode implementiert werden, um zu bewirken, dass geänderte Elemente verworfen werden, ohne gespeichert zu werden.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Prüfliste: Erstellen neuer Projekttypen](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Erstellen von Projektinstanzen mithilfe von Projektfactorys](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)
