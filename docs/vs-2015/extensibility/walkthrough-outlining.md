---
title: 'Exemplarische Vorgehensweise: Gliederung | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - outlining
ms.assetid: d75a44aa-265a-44d4-9c28-457f59c4ff9f
caps.latest.revision: 31
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7c1dd3d28b9978b52c95b5ff905d57720ed10f5d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68201954"
---
# <a name="walkthrough-outlining"></a>Exemplarische Vorgehensweise: Gliedern
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sie können sprachbasierte Funktionen wie Gliederung implementieren, indem Sie die Arten von Textbereichen definieren, die Sie erweitern oder reduzieren möchten. Sie können Bereiche im Kontext eines sprach Dienstanbieter definieren, oder Sie können eine eigene Dateinamenerweiterung und einen Inhaltstyp definieren und die Regions Definition nur auf diesen Typ anwenden, oder Sie können die Regions Definitionen auf einen vorhandenen Inhaltstyp (z. b. "Text") anwenden. Diese exemplarische Vorgehensweise zeigt, wie Gliederungs Bereiche definiert und angezeigt werden.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Ab Visual Studio 2015 installieren Sie das Visual Studio SDK nicht aus dem Download Center. Sie ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das vs SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren des Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Erstellen eines MEF-Projekts (Managed Extensibility Framework)  
  
#### <a name="to-create-a-mef-project"></a>So erstellen Sie ein MEF-Projekt  
  
1. Erstellen Sie ein VSIX-Projekt. Nennen Sie die Projektmappe `OutlineRegionTest`.  
  
2. Fügen Sie dem Projekt eine Editor-Klassifizierungs Element Vorlage hinzu. Weitere Informationen finden Sie unter [Erstellen einer Erweiterung mit einer Editor-Element Vorlage](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3. Löschen Sie die vorhandenen Klassendateien.  
  
## <a name="implementing-an-outlining-tagger"></a>Implementieren eines gliederungtaggers  
 Gliederungs Bereiche werden durch eine Art von Tag ( <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> ) markiert. Dieses Tag stellt das standardmäßige Gliederungs Verhalten bereit. Der dargestellte Bereich kann erweitert oder reduziert werden. Der dargestellte Bereich wird durch ein Plus Zeichen gekennzeichnet, wenn er reduziert ist, oder ein Minus Zeichen, wenn er erweitert wird, und der erweiterte Bereich wird durch eine vertikale Linie abgegrenzt.  
  
 In den folgenden Schritten wird gezeigt, wie ein Tagger definiert wird, der Gliederungs Bereiche für alle Regionen erstellt, die durch "[" und "]" begrenzt sind.  
  
#### <a name="to-implement-an-outlining-tagger"></a>So implementieren Sie einen Gliederungs Tagger  
  
1. Fügen Sie eine Klassendatei hinzu, und nennen Sie sie `OutliningTagger`.  
  
2. Importieren Sie die folgenden Namespaces.  
  
     [!code-csharp[VSSDKOutlineRegionTest#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#1)]
     [!code-vb[VSSDKOutlineRegionTest#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#1)]  
  
3. Erstellen Sie eine Klasse mit dem Namen `OutliningTagger` , und implementieren Sie Folgendes <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> :  
  
     [!code-csharp[VSSDKOutlineRegionTest#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#2)]
     [!code-vb[VSSDKOutlineRegionTest#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#2)]  
  
4. Fügen Sie einige Felder hinzu, um den Text Puffer und die Momentaufnahme zu verfolgen und die Zeilen Sätze zu sammeln, die als Gliederungs Bereiche markiert werden sollen. Dieser Code enthält eine Liste von Regions Objekten (die später definiert werden müssen), die die Gliederungs Bereiche darstellen.  
  
     [!code-csharp[VSSDKOutlineRegionTest#3](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#3)]
     [!code-vb[VSSDKOutlineRegionTest#3](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#3)]  
  
5. Fügen Sie einen Tagger-Konstruktor hinzu, der die Felder initialisiert, den Puffer analysiert und dem Ereignis einen Ereignishandler hinzufügt <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> .  
  
     [!code-csharp[VSSDKOutlineRegionTest#4](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#4)]
     [!code-vb[VSSDKOutlineRegionTest#4](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#4)]  
  
6. Implementieren Sie die- <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> Methode, die die tagspannen instanziiert. In diesem Beispiel wird davon ausgegangen, dass die Spannen in der, die <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> an die-Methode geleitet werden, zusammenhängend sind, obwohl dies möglicherweise nicht immer der Fall ist. Diese Methode instanziiert eine neue tagspanne für jeden der Gliederungs Bereiche.  
  
     [!code-csharp[VSSDKOutlineRegionTest#5](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#5)]
     [!code-vb[VSSDKOutlineRegionTest#5](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#5)]  
  
7. Deklarieren Sie einen- `TagsChanged` Ereignishandler.  
  
     [!code-csharp[VSSDKOutlineRegionTest#6](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#6)]
     [!code-vb[VSSDKOutlineRegionTest#6](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#6)]  
  
8. Fügen Sie einen `BufferChanged` Ereignishandler hinzu, <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> der auf Ereignisse reagiert, indem Sie den Text Puffer auswerten.  
  
     [!code-csharp[VSSDKOutlineRegionTest#7](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#7)]
     [!code-vb[VSSDKOutlineRegionTest#7](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#7)]  
  
9. Fügen Sie eine Methode hinzu, die den Puffer analysiert. Das hier angegebene Beispiel dient nur der Veranschaulichung. Sie analysiert den Puffer synchron in geschsted Gliederungs Bereiche.  
  
     [!code-csharp[VSSDKOutlineRegionTest#8](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#8)]
     [!code-vb[VSSDKOutlineRegionTest#8](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#8)]  
  
10. Die folgende Hilfsmethode Ruft eine Ganzzahl ab, die die Ebene der Gliederung darstellt, sodass 1 das äußteste linke Klammer Paar ist.  
  
     [!code-csharp[VSSDKOutlineRegionTest#9](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#9)]
     [!code-vb[VSSDKOutlineRegionTest#9](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#9)]  
  
11. Die folgende Hilfsmethode übersetzt einen (später in diesem Thema definierten) Bereich in eine snapshotspan.  
  
     [!code-csharp[VSSDKOutlineRegionTest#10](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#10)]
     [!code-vb[VSSDKOutlineRegionTest#10](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#10)]  
  
12. Der folgende Code dient nur der Veranschaulichung. Es definiert eine partialregion-Klasse, die die Zeilennummer und den Offset des Starts eines Gliederungs Bereichs sowie einen Verweis auf den übergeordneten Bereich (sofern vorhanden) enthält. Dies ermöglicht es dem Parser, eingefügte Gliederungs Bereiche einzurichten. Eine abgeleitete Regions Klasse enthält einen Verweis auf die Zeilennummer des Endes eines Gliederungs Bereichs.  
  
     [!code-csharp[VSSDKOutlineRegionTest#11](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#11)]
     [!code-vb[VSSDKOutlineRegionTest#11](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#11)]  
  
## <a name="implementing-a-tagger-provider"></a>Implementieren eines Tagger-Anbieters  
 Sie müssen einen Tagger-Anbieter für Ihr Tagger exportieren. Der Tagger-Anbieter erstellt einen `OutliningTagger` für einen Puffer mit dem Inhaltstyp "Text" oder gibt einen zurück, `OutliningTagger` Wenn der Puffer bereits einen besitzt.  
  
#### <a name="to-implement-a-tagger-provider"></a>So implementieren Sie einen Tagger-Anbieter  
  
1. Erstellen Sie eine Klasse `OutliningTaggerProvider` mit dem Namen, die implementiert <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider> , und exportieren Sie Sie mit den Attributen ContentType und TagType.  
  
     [!code-csharp[VSSDKOutlineRegionTest#12](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#12)]
     [!code-vb[VSSDKOutlineRegionTest#12](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#12)]  
  
2. Implementieren Sie die- <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> Methode `OutliningTagger` , indem Sie eine zu den Eigenschaften des Puffers hinzufügen.  
  
     [!code-csharp[VSSDKOutlineRegionTest#13](../snippets/csharp/VS_Snippets_VSSDK/vssdkoutlineregiontest/cs/outliningtagger.cs#13)]
     [!code-vb[VSSDKOutlineRegionTest#13](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkoutlineregiontest/vb/outliningtagger.vb#13)]  
  
## <a name="building-and-testing-the-code"></a>Erstellen und Testen des Codes  
 Um diesen Code zu testen, erstellen Sie die Projekt Mappe "outlineregiontest", und führen Sie Sie in der experimentellen Instanz aus.  
  
#### <a name="to-build-and-test-the-outlineregiontest-solution"></a>So erstellen und testen Sie die Projekt Mappe "outlineregiontest"  
  
1. Erstellen Sie die Projektmappe.  
  
2. Wenn Sie dieses Projekt im Debugger ausführen, wird eine zweite Instanz von Visual Studio instanziiert.  
  
3. Erstellen einer Textdatei Geben Sie Text ein, der die öffnende geschweifte Klammer und die schließende geschweifte Klammer enthält.  
  
    ```  
    [  
       Hello  
    ]  
    ```  
  
4. Es sollte ein Gliederungs Bereich vorhanden sein, der beide Klammern enthält. Sie sollten in der Lage sein, auf das Minus Zeichen links neben der öffnenden geschweifter Klammer zu klicken, um den Gliederungs Bereich zu reduzieren. Wenn der Bereich reduziert ist, sollte das Symbol mit den Auslassungs Zeichen (...) links neben dem reduzierten Bereich angezeigt werden, und es sollte ein Popup Fenster angezeigt werden, das den Text für den **Maus** Zeiger enthält, wenn Sie den Mauszeiger auf die Auslassungs Zeichen bewegen.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Exemplarische Vorgehensweise: Verknüpfen eines Inhaltstyps mit einer Dateinamenerweiterung](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)
