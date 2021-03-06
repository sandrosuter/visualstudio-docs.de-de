---
title: Verfügbar machen von Ereignissen im Visual Studio SDK | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- events [Visual Studio], exposing
- automation [Visual Studio SDK], exposing events
ms.assetid: 70bbc258-c221-44f8-b0d7-94087d83b8fe
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7056497c505bbb355287416e468e411b4e5a2a62
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68196683"
---
# <a name="exposing-events-in-the-visual-studio-sdk"></a>Verfügbarmachen von Ereignissen im Visual Studio SDK
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ermöglicht das Quellen Ereignis mithilfe von Automation. Es wird empfohlen, Ereignisse für Projekte und Projekt Elemente zu beziehen.  
  
 Ereignisse werden von Automation-Consumern aus dem- <xref:EnvDTE.DTEClass.Events%2A> Objekt oder <xref:EnvDTE.DTEClass.GetObject%2A> ("eventobjectname") abgerufen. Die-Umgebung ruft `IDispatch::Invoke` mithilfe der- `DISPATCH_METHOD` oder- `DISPATCH_PROPERTYGET` Flags auf, um ein Ereignis zurückzugeben.  
  
 Im folgenden Verfahren wird erläutert, wie VSPackage-spezifische Ereignisse zurückgegeben werden.  
  
1. Die Umgebung wird gestartet.  
  
2. Er liest aus der Registrierung alle Wertnamen unter den Schlüsseln Automation, AutomationEvents und AutomationProperties aller VSPackages und speichert diese Namen in einer Tabelle.  
  
3. Ein automatisierungsconsumer ruft in diesem Beispiel `DTE.Events.AutomationProjectsEvents` oder auf `DTE.Events.AutomationProjectItemsEvents` .  
  
4. Die Umgebung sucht den Zeichen folgen Parameter in der Tabelle und lädt das entsprechende VSPackage.  
  
5. Die Umgebung Ruft die <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> Methode auf, indem Sie den Namen verwendet, der im Aufruf übergeben wird. in diesem Beispiel werden automationprojectte Vents oder automationprojectitem\vents verwendet.  
  
6. Das VSPackage erstellt ein Stamm Objekt, das Methoden wie und enthält, `get_AutomationProjectsEvents` `get_AutomationProjectItemEvents` und gibt dann einen IDispatch-Zeiger auf das-Objekt zurück.  
  
7. Die Umgebung Ruft die entsprechende Methode auf Grundlage des Namens auf, der an den Automation-Aufruf weitergeleitet wird.  
  
8. Die `get_` -Methode erstellt ein weiteres IDispatch-basiertes Ereignis Objekt, das sowohl die `IConnectionPointContainer` -Schnittstelle als auch die `IConnectionPoint` -Schnittstelle implementiert und einen idispatchpointer an das-Objekt zurückgibt.  
  
   Wenn Sie ein Ereignis mithilfe von Automation verfügbar machen möchten, müssen Sie auf die Zeichen folgen reagieren, die <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> Sie der Registrierung hinzufügen. Im grundlegenden Projektbeispiel lauten die Zeichen folgen "bscprojectst Vents" und "bscprojectitem\vents".  
  
## <a name="registry-entries-from-the-basic-project-sample"></a>Registrierungseinträge aus dem grundlegenden Projektbeispiel  
 In diesem Abschnitt wird gezeigt, wo Sie der Registrierung Automatisierungs Ereignis Werte hinzufügen können.  
  
 [HKEY_LOCAL_MACHINE \software\microsoft\visualstudio\8.0\Packages \\<pkgguid \> \automationevents]  
  
 "Automationprojectevents" = "gibt das automationprojectevents-Objekt zurück"  
  
 "Automationprojectitemevents" = "gibt das automationprojectitemsevents-Objekt zurück"  
  
|Name|type|Range|Beschreibung|  
|----------|----------|-----------|-----------------|  
|Standard (@)|REG_SZ|Nicht verwendet|Nicht verwendet. Sie können das Datenfeld für die-Dokumentation verwenden.|  
|Automationproject\vents|REG_SZ|Der Name des Ereignis Objekts.|Nur der Schlüssel Name ist relevant. Sie können das Datenfeld für die-Dokumentation verwenden.<br /><br /> Dieses Beispiel stammt aus dem grundlegenden Projektbeispiel.|  
|Automationprojectitemevents|REG_SZ|Name des Ereignis Objekts|Nur der Schlüssel Name ist relevant. Sie können das Datenfeld für die-Dokumentation verwenden.<br /><br /> Dieses Beispiel stammt aus dem grundlegenden Projektbeispiel.|  
  
 Wenn eines der Ereignis Objekte von einem automatisierungsconsumer angefordert wird, erstellen Sie ein Stamm Objekt, das über Methoden für jedes Ereignis verfügt, das das VSPackage unterstützt. Die Umgebung Ruft die entsprechende `get_` Methode für dieses Objekt auf. Wenn beispielsweise `DTE.Events.AutomationProjectsEvents` aufgerufen wird, wird die- `get_AutomationProjectsEvents` Methode für das Root-Objekt aufgerufen.  
  
 ![Ereignisse in Visual Studio-Projekt](../../extensibility/internals/media/projectevents.gif "ProjectEvents")  
Automatisierungs Modell für Ereignisse  
  
 Die-Klasse `CProjectEventsContainer` stellt das Quell Objekt für bscprojectsevents dar, während `CProjectItemsEventsContainer` das Quell Objekt für bscprojectitemsevents darstellt.  
  
 In den meisten Fällen müssen Sie für jede Ereignis Anforderung ein neues-Objekt zurückgeben, da die meisten Ereignis Objekte ein Filter Objekt übernehmen. Wenn Sie das Ereignis auslösen, überprüfen Sie diesen Filter, um zu überprüfen, ob der Ereignishandler aufgerufen wird.  
  
 AutomationEvents. h und AutomationEvents. cpp enthalten Deklarationen und Implementierungen der Klassen in der folgenden Tabelle.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|`CAutomationEvents`|Implementiert ein Ereignis Stamm Objekt, das aus dem-Objekt abgerufen wird `DTE.Events` .|  
|`CProjectsEventsContainer` und `CProjectItemsEventsContainer`|Implementieren Sie die Ereignis Quell Objekte, die die entsprechenden Ereignisse auslösen.|  
  
 Im folgenden Codebeispiel wird gezeigt, wie auf eine Anforderung für ein Ereignis Objekt reagiert wird.  
  
```cpp#  
STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
{  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
    if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)   
        //Is the requested name our Projects object?  
    {  
        return GetAutomationProjects(ppIDispatch);  
        // Gets our Projects object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        //Is the requested name our ProjectsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectEvents object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  //Is the requested name our ProjectsItemsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectItemsEvents object.  
    }  
    return E_INVALIDARG;  
}  
```  
  
 Im obigen Code ist der `g_wszAutomationProjects` Name der Projekt Auflistung ("figprojects"), `g_wszAutomationProjectsEvents` ("figprojectsevents") und `g_wszAutomationProjectItemsEvents` ("figprojectitemevents") sind die Namen der Projekt Ereignisse und Projekt Element Ereignisse, die aus der VSPackage-Implementierung stammen.  
  
 Ereignis Objekte werden vom gleichen zentralen Speicherort, dem- `DTE.Events` Objekt, abgerufen. Auf diese Weise werden alle Ereignis Objekte gruppiert, sodass ein Endbenutzer nicht das gesamte Objektmodell durchsuchen muss, um nach einem bestimmten Ereignis zu suchen. Dadurch können Sie auch Ihre spezifischen VSPackage-Objekte bereitstellen, anstatt ihren eigenen Code für systemweite Ereignisse zu implementieren. Für Endbenutzer, die ein Ereignis für Ihre `ProjectItem` Schnittstelle finden müssen, ist es jedoch nicht sofort klar, von wo aus das Ereignis Objekt abgerufen wird.  
  
## <a name="see-also"></a>Weitere Informationen  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>   
 [VSSDK-Beispiele](../../misc/vssdk-samples.md)
