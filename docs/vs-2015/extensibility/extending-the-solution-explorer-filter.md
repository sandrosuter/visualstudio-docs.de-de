---
title: Erweitern des Projektmappen-Explorer Filters | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Solution Explorer, extending
- extensibility [Visual Studio], projects and solutions
ms.assetid: df976c76-27ec-4f00-ab6d-a26a745dc6c7
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 687663a79ea5dca75da68013519f4652fa71460c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204383"
---
# <a name="extending-the-solution-explorer-filter"></a>Erweitern des Filters für den Projektmappen-Explorer
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sie können **Projektmappen-Explorer** Filter Funktionalität erweitern, um unterschiedliche Dateien anzuzeigen oder auszublenden. Beispielsweise können Sie einen Filter erstellen, der nur c#-klassenfactorydateien im **Projektmappen-Explorer**anzeigt, wie in dieser exemplarischen Vorgehensweise veranschaulicht.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Ab Visual Studio 2015 installieren Sie das Visual Studio SDK nicht aus dem Download Center. Sie ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das vs SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren des Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="create-a-visual-studio-package-project"></a>Erstellen eines Visual Studio-Paket Projekts  
  
1. Erstellen Sie ein VSIX-Projekt mit dem Namen `FileFilter` . Fügen Sie eine benutzerdefinierte Befehls Element Vorlage mit dem Namen **FileFilter**hinzu. Weitere Informationen finden Sie unter [Erstellen einer Erweiterung mit einem Menübefehl](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2. Fügen Sie einen Verweis auf `System.ComponentModel.Composition` und hinzu `Microsoft.VisualStudio.Utilities` .  
  
3. Legen Sie den Menübefehl auf der Symbolleiste **Projektmappen-Explorer** angezeigt. Öffnen Sie die Datei "filefilterpackage. vsct".  
  
4. Ändern `<Button>` Sie den Block wie folgt:  
  
    ```xml  
    <Button guid="guidFileFilterPackageCmdSet" id="FileFilterId" priority="0x0400" type="Button">  
        <Parent guid="guidSHLMainMenu" id="IDG_VS_TOOLBAR_PROJWIN_FILTERS" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>FileNameFilter</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
### <a name="update-the-manifest-file"></a>Aktualisieren der Manifest-Datei  
  
1. Fügen Sie in der Datei "Source. Extension. vsixmanifest" ein Medienobjekt hinzu, das eine MEF-Komponente ist.  
  
2. Wählen Sie auf der Registerkarte **Objekte** die Schaltfläche **neu** aus.  
  
3. Wählen Sie im Feld **Typ** den Eintrag **Microsoft. VisualStudio. MEFComponent**aus.  
  
4. Wählen Sie im Feld **Quelle** **ein Projekt in der aktuellen Projekt Mappe aus**.  
  
5. Wählen Sie im Feld **Projekt** die Option **FileFilter**aus, und klicken Sie dann auf die Schaltfläche **OK** .  
  
### <a name="add-the-filter-code"></a>Hinzufügen des Filter Codes  
  
1. Fügen Sie der Datei FileFilterPackageGuids.cs einige GUIDs hinzu:  
  
    ```csharp  
    public const string guidFileFilterPackageCmdSetString = "00000000-0000-0000-0000-00000000"; // get your GUID from the .vsct file  
    public const int FileFilterId = 0x100;  
    ```  
  
2. Fügen Sie dem FileFilter-Projekt eine Klassendatei mit dem Namen FileNameFilter.cs hinzu.  
  
3. Ersetzen Sie den leeren Namespace und die leere Klasse durch den folgenden Code.  
  
     Die `Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem rootItems)` -Methode nimmt die Auflistung, die den Stamm der Projekt Mappe enthält ( `rootItems` ), und gibt die Auflistung von Elementen zurück, die in den Filter eingeschlossen werden sollen.  
  
     Die- `ShouldIncludeInFilter` Methode filtert die Elemente in der **Projektmappen-Explorer** Hierarchie basierend auf der von Ihnen angegebenen Bedingung.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Text.RegularExpressions;  
    using System.Threading.Tasks;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
  
    namespace FileFilter  
    {  
        // Implements ISolutionTreeFilterProvider. The SolutionTreeFilterProvider attribute declares it as a MEF component  
        [SolutionTreeFilterProvider(FileFilterPackageGuids.guidFileFilterPackageCmdSetString, (uint)(FileFilterPackageGuids.FileFilterId))]  
        public sealed class FileNameFilterProvider : HierarchyTreeFilterProvider  
        {  
            SVsServiceProvider svcProvider;  
            IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
            // Constructor required for MEF composition  
            [ImportingConstructor]  
            public FileNameFilterProvider(SVsServiceProvider serviceProvider, IVsHierarchyItemCollectionProvider hierarchyCollectionProvider)  
            {  
                this.svcProvider = serviceProvider;  
                this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
            }  
  
            // Returns an instance of Create filter class.  
            protected override HierarchyTreeFilter CreateFilter()  
            {  
                return new FileNameFilter(this.svcProvider, this.hierarchyCollectionProvider, FileNamePattern);  
            }  
  
            // Regex pattern for CSharp factory classes  
            private const string FileNamePattern = @"\w*factory\w*(.cs$)";  
  
            // Implementation of file filtering  
            private sealed class FileNameFilter : HierarchyTreeFilter  
            {  
                private readonly Regex regexp;  
                private readonly IServiceProvider svcProvider;  
                private readonly IVsHierarchyItemCollectionProvider hierarchyCollectionProvider;  
  
                public FileNameFilter(  
                    IServiceProvider serviceProvider,  
                    IVsHierarchyItemCollectionProvider hierarchyCollectionProvider,  
                    string fileNamePattern)  
                {  
                    this.svcProvider = serviceProvider;  
                    this.hierarchyCollectionProvider = hierarchyCollectionProvider;  
                    this.regexp = new Regex(fileNamePattern, RegexOptions.IgnoreCase);  
                }  
  
                // Gets the items to be included from this filter provider.   
                // rootItems is a collection that contains the root of your solution  
                // Returns a collection of items to be included as part of the filter  
                protected override async Task<IReadOnlyObservableSet> GetIncludedItemsAsync(IEnumerable<IVsHierarchyItem> rootItems)  
                {  
                    IVsHierarchyItem root = HierarchyUtilities.FindCommonAncestor(rootItems);  
                    IReadOnlyObservableSet<IVsHierarchyItem> sourceItems;  
                    sourceItems = await hierarchyCollectionProvider.GetDescendantsAsync(  
                                        root.HierarchyIdentity.NestedHierarchy,  
                                        CancellationToken);  
  
                    IFilteredHierarchyItemSet includedItems = await hierarchyCollectionProvider.GetFilteredHierarchyItemsAsync(  
                        sourceItems,  
                        ShouldIncludeInFilter,  
                        CancellationToken);  
                    return includedItems;  
                }  
  
                // Returns true if filters hierarchy item name for given filter; otherwise, false</returns>  
                private bool ShouldIncludeInFilter(IVsHierarchyItem hierarchyItem)  
                {  
                    if (hierarchyItem == null)  
                    {  
                        return false;  
                    }  
                    return this.regexp.IsMatch(hierarchyItem.Text);  
                }  
            }  
        }  
    }  
  
    ```  
  
4. Entfernen Sie in FileFilter.cs den Befehls Platzierungs-und-Verarbeitungs Code aus dem FileFilter-Konstruktor. Das Ergebnis sollte wie folgt aussehen:  
  
    ```csharp  
    private FileFilter(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException("package");  
        }  
  
        this.package = package;  
    }  
    ```  
  
     Entfernen Sie auch die Methode "ShowMessageBox ()".  
  
5. Ersetzen Sie in filefilterpackage, cs den Code in der Initialize ()-Methode durch Folgendes:  
  
    ```csharp  
    protected override void Initialize()  
    {  
        Debug.WriteLine (string.Format(CultureInfo.CurrentCulture, "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
    }  
    ```  
  
### <a name="test-your-code"></a>Testen des Codes  
  
1. Erstellen Sie das Projekt, und führen Sie es aus. Eine zweite Instanz von Visual Studio wird geöffnet. Dies wird als experimentelle Instanz bezeichnet.  
  
2. Öffnen Sie in der experimentellen Instanz von Visual Studio ein c#-Projekt.  
  
3. Suchen Sie nach der Schaltfläche, die Sie auf der Symbolleiste Projektmappen-Explorer Dies sollte die vierte Schaltfläche von Links sein.  
  
4. Wenn Sie auf die Schaltfläche klicken, sollten alle Dateien herausgefiltert werden, und Sie sollten sehen, dass alle Elemente aus der Ansicht gefiltert wurden. in der Projektmappen-Explorer.
