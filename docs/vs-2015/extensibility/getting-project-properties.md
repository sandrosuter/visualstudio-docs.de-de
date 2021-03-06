---
title: Projekteigenschaften werden erhalten | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties, displaying in tool window
- tool windows, displaying project properties
ms.assetid: 96ba07ca-0811-4013-8602-12550ac4ba79
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d0557d08c318eda47853ec69c6204739cbece560
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204322"
---
# <a name="getting-project-properties"></a>Abrufen von Projekteigenschaften
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Projekteigenschaften in einem Tool Fenster angezeigt werden.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Ab Visual Studio 2015 installieren Sie das Visual Studio SDK nicht aus dem Download Center. Sie ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das vs SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren des Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="to-create-a-vsix-project-and-add-a-tool-window"></a>So erstellen Sie ein VSIX-Projekt und fügen ein Tool Fenster hinzu  
  
1. Jede Visual Studio-Erweiterung beginnt mit einem VSIX-Bereitstellungs Projekt, das die Erweiterungs Ressourcen enthält. Erstellen Sie ein [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] VSIX-Projekt mit dem Namen `ProjectPropertiesExtension` . Sie finden die VSIX-Projektvorlage im Dialogfeld " **Neues Projekt** " unter **Visual c#/Erweiterbarkeit**.  
  
2. Fügen Sie ein Tool Fenster hinzu, indem Sie eine benutzerdefinierte Tool Fensterelement Vorlage namens hinzufügen `ProjectPropertiesToolWindow` . Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Hinzufügen/Neues Element**aus. Wechseln Sie im **Dialogfeld Neues Element hinzufügen**zu **Visual c# Elemente/Erweiterbarkeit** , und wählen Sie **benutzerdefiniertes Tool Fenster**aus. Ändern Sie im Feld **Name** am unteren Rand des Dialog Felds den Dateinamen in `ProjectPropertiesToolWindow.cs` . Weitere Informationen zum Erstellen eines benutzerdefinierten Tool Fensters finden Sie unter [Erstellen einer Erweiterung mit einem Tool Fenster](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
3. Erstellen Sie die Projektmappe, und stellen Sie sicher, dass sie fehlerfrei kompiliert wird.  
  
### <a name="to-display-project-properties-in-a-tool-window"></a>So zeigen Sie Projekteigenschaften in einem Tool Fenster an  
  
1. Fügen Sie in der Datei ProjectPropertiesToolWindowCommand.cs die folgenden using-Anweisungen hinzu.  
  
    ```csharp  
    using EnvDTE;  
    using System.Windows.Controls;  
  
    ```  
  
2. Entfernen Sie in projectpropertiestoolwindowcontrol. XAML die vorhandene Schaltfläche, und fügen Sie eine TreeView aus der Toolbox hinzu. Sie können auch den Click-Ereignishandler aus der ProjectPropertiesToolWindowControl.XAML.cs-Datei entfernen.  
  
3. Verwenden Sie in ProjectPropertiesToolWindowCommand.cs die ShowToolWindow ()-Methode, um das Projekt zu öffnen und dessen Eigenschaften zu lesen, und fügen Sie dann die Eigenschaften der TreeView hinzu. Der Code für ShowToolWindow sollte wie folgt aussehen:  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        ToolWindowPane window = this.package.FindToolWindow(typeof(ProjectPropertiesToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
            throw new NotSupportedException("Cannot create window.");  
        }  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
        // Get the tree view and populate it if there is a project open.  
        ProjectPropertiesToolWindowControl control = (ProjectPropertiesToolWindowControl)window.Content;  
        TreeView treeView = control.treeView;  
  
        // Reset the TreeView to 0 items.  
        treeView.Items.Clear();  
  
        DTE dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
        Projects projects = dte.Solution.Projects;  
        if (projects.Count == 0)   // no project is open  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.Name = "Projects";  
            item.ItemsSource = new string[]{ "no projects are open." };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
            return;  
        }  
  
        Project project = projects.Item(1);  
        TreeViewItem item1 = new TreeViewItem();  
        item1.Header = project.Name + "Properties";  
        treeView.Items.Add(item1);  
  
        foreach (Property property in project.Properties)  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.ItemsSource = new string[] { property.Name };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
        }  
    }  
    ```  
  
4. Erstellen Sie das Projekt, und starten Sie das Debugging. Die experimentelle Instanz sollte angezeigt werden.  
  
5. Öffnen Sie in der experimentellen Instanz ein Projekt.  
  
6. Klicken Sie in der **Ansicht bzw. in anderen Fenstern** auf **projectpropertiestoolwindow**.  
  
     Das Struktur Steuerelement sollte im Tool Fenster mit dem Namen des ersten Projekts und aller zugehörigen Projekteigenschaften angezeigt werden.
