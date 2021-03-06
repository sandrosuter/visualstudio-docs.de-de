---
title: 'Gewusst wie: Programm gesteuertes Hinzufügen von Kopf-und Fußzeilen zu Dokumenten'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- headers, adding to Office documents
- documents [Office development in Visual Studio], adding headers
- documents [Office development in Visual Studio], adding footers
- footers, adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c6a60f58a116cd01c59145de0fcd29a2f55a787e
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585417"
---
# <a name="how-to-programmatically-add-headers-and-footers-to-documents"></a>Gewusst wie: Programm gesteuertes Hinzufügen von Kopf-und Fußzeilen zu Dokumenten
  Sie können Kopf- und Fußzeilen in Ihrem Dokument Text hinzufügen, indem Sie die Eigenschaft <xref:Microsoft.Office.Interop.Word.Section.Headers%2A> und die Eigenschaft <xref:Microsoft.Office.Interop.Word.Section.Footers%2A> von der<xref:Microsoft.Office.Interop.Word.Section> verwenden. Jeder Abschnitt eines Dokuments enthält drei Kopf- und Fußzeilen:

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterPrimary>

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterEvenPages>

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterFirstPage>

  Die Verfahren unterscheiden sich für Anpassungen auf Dokumentebene und VSTO-Add-Ins.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="document-level-customizations"></a>Anpassungen auf Dokumentebene
 Wenn Sie die folgenden Codebeispiele verwenden möchten, führen Sie sie aus der Klasse `ThisDocument` in Ihrem Projekt aus.

### <a name="to-add-text-to-footers-in-the-document"></a>So fügen Sie Fußzeilen im Dokument Text hinzu

1. Im folgenden Codebeispiel wird die Schriftart des Texts festgelegt, der in die primäre Fußzeile jedes Abschnitts des Dokuments eingefügt werden soll, und anschließend Text in die Fußzeile eingefügt.

     [!code-vb[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#114)]

### <a name="to-add-text-to-headers-in-the-document"></a>So fügen Sie Kopfzeilen im Dokument Text hinzu

1. Das folgende Codebeispiel fügt ein Feld hinzu, um die Seitenzahl in jeder Kopfzeile des Dokuments anzuzeigen, und legt dann die Absatzausrichtung fest, sodass der Text rechts am Header ausgerichtet wird.

     [!code-vb[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#116)]

## <a name="vsto-add-ins"></a>VSTO-Add-Ins
 Wenn Sie die folgenden Codebeispiele verwenden möchten, führen Sie sie aus der Klasse `ThisAddIn` in Ihrem Projekt aus.

### <a name="to-add-text-to-footers-in-a-document"></a>So fügen Sie Fußzeilen in einem Dokument Text hinzu

1. Im folgenden Codebeispiel wird die Schriftart des Texts festgelegt, der in die primäre Fußzeile jedes Abschnitts des Dokuments eingefügt werden soll, und anschließend Text in die Fußzeile eingefügt. In diesem Codebeispiel wird das aktive Dokument verwendet.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#114)]

### <a name="to-add-text-to-headers-in-the-document"></a>So fügen Sie Kopfzeilen im Dokument Text hinzu

1. Das folgende Codebeispiel fügt ein Feld hinzu, um die Seitenzahl in jeder Kopfzeile des Dokuments anzuzeigen, und legt dann die Absatzausrichtung fest, sodass der Text rechts am Header ausgerichtet wird. In diesem Codebeispiel wird das aktive Dokument verwendet.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#116)]

## <a name="see-also"></a>Weitere Informationen
- [Gewusst wie: Programm gesteuertes Erstellen neuer Dokumente](../vsto/how-to-programmatically-create-new-documents.md)
- [Gewusst wie: Programm gesteuertes Erweitern von Bereichen in Dokumenten](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [Gewusst wie: Programm gesteuertes durchlaufen gefundener Elemente in Dokumenten](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
