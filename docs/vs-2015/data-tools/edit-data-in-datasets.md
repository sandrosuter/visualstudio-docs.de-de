---
title: Bearbeiten von Daten in Datasets | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- datasets [Visual Basic], editing data
- data [Visual Studio], editing in datasets
ms.assetid: 50d5c580-fbf7-408f-be70-e63ac4f4d0eb
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 699ee9b6e7a68c6a79f7f7dac526127206e8aa42
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "72672404"
---
# <a name="edit-data-in-datasets"></a>Bearbeiten von Daten in Datasets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sie bearbeiten Daten in Datentabellen, ähnlich wie Sie die Daten in einer Tabelle in einer beliebigen Datenbank bearbeiten. Der Prozess kann das Einfügen, aktualisieren und Löschen von Datensätzen in der Tabelle umfassen. In einem Daten gebundenen Formular können Sie angeben, welche Felder vom Benutzer bearbeitet werden können. In diesen Fällen verarbeitet die Daten Bindungs Infrastruktur die gesamte Änderungs Nachverfolgung, sodass die Änderungen später wieder an die Datenbank gesendet werden können. Wenn Sie Programm gesteuert Änderungen an Daten vornehmen und diese Änderungen an die Datenbank zurücksenden möchten, müssen Sie die Objekte und Methoden verwenden, die die Änderungs Nachverfolgung für Sie ausführen.

 Zusätzlich zum Ändern der tatsächlichen Daten können Sie auch Abfragen, <xref:System.Data.DataTable> um bestimmte Daten Zeilen zurückzugeben. Sie können z. b. einzelne Zeilen, bestimmte Versionen von Zeilen (ursprünglich und vorgeschlagen), geänderte Zeilen oder Zeilen mit Fehlern Abfragen.

## <a name="to-edit-rows-in-a-dataset"></a>So bearbeiten Sie Zeilen in einem DataSet
 Wenn Sie eine vorhandene Zeile in einem bearbeiten möchten <xref:System.Data.DataTable> , müssen Sie das <xref:System.Data.DataRow> -Feld Suchen, das Sie bearbeiten möchten, und dann den gewünschten Spalten die aktualisierten Werte zuweisen.

 Wenn Sie den Index der Zeile, die Sie bearbeiten möchten, nicht kennen, verwenden Sie die- `FindBy` Methode, um nach dem Primärschlüssel zu suchen:

 [!code-csharp[VbRaddataEditing#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#3)]
 [!code-vb[VbRaddataEditing#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#3)]

 Wenn Sie den Zeilen Index kennen, können Sie wie folgt auf Zeilen zugreifen und diese bearbeiten:

 [!code-csharp[VbRaddataEditing#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#5)]
 [!code-vb[VbRaddataEditing#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#5)]

## <a name="to-insert-new-rows-into-a-dataset"></a>So fügen Sie neue Zeilen in ein Dataset ein
 Anwendungen, die Daten gebundene Steuerelemente verwenden, fügen in der Regel neue Datensätze über die Schaltfläche **Neu hinzufügen** auf einem [BindingNavigator-Steuer](https://msdn.microsoft.com/library/18c1e2a5-9834-40d3-9b2e-2b545e4e769e)Element hinzu

 Wenn Sie einem Dataset manuell neue Datensätze hinzufügen möchten, erstellen Sie eine neue Daten Zeile, indem Sie die-Methode für die Datentabelle aufrufen. Fügen Sie dann die Zeile der-Auflistung <xref:System.Data.DataRow> ( <xref:System.Data.DataTable.Rows%2A> ) von hinzu <xref:System.Data.DataTable> :

 [!code-csharp[VbRaddataEditing#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#1)]
 [!code-vb[VbRaddataEditing#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#1)]

 Um die Informationen beizubehalten, die das DataSet benötigt, um Aktualisierungen an die Datenquelle zu senden, verwenden <xref:System.Data.DataRow.Delete%2A> Sie die-Methode, um Zeilen in einer Datentabelle zu entfernen. Wenn Ihre Anwendung z. b. einen TableAdapter (oder <xref:System.Data.Common.DataAdapter> ) verwendet, löscht die-Methode des TableAdapter `Update` Zeilen in der-Datenbank, die eine <xref:System.Data.DataRow.RowState%2A> von aufweisen <xref:System.Data.DataRowState> .

 Wenn Ihre Anwendung Updates nicht an eine Datenquelle zurücksenden muss, ist es möglich, Datensätze zu entfernen, indem Sie direkt auf die Daten Zeilen Auflistung ( <xref:System.Data.DataRowCollection.Remove%2A> ) zugreifen.

#### <a name="to-delete-records-from-a-data-table"></a>So löschen Sie Datensätze aus einer Datentabelle

- Ruft die- <xref:System.Data.DataRow.Delete%2A> Methode eines auf <xref:System.Data.DataRow> .

     Diese Methode entfernt den Datensatz nicht physisch. Stattdessen wird der Datensatz zum Löschen markiert.

    > [!NOTE]
    > Wenn Sie die Count-Eigenschaft eines erhalten <xref:System.Data.DataRowCollection> , enthält die resultierende Anzahl Datensätze, die zum Löschen markiert wurden. Wenn Sie eine genaue Anzahl von Datensätzen erhalten möchten, die nicht zum Löschen markiert sind, können Sie die Sammlung durchlaufen, indem Sie die- <xref:System.Data.DataRow.RowState%2A> Eigenschaft der einzelnen Datensätze betrachten. (Datensätze, die zum Löschen markiert sind, haben die <xref:System.Data.DataRow.RowState%2A> von <xref:System.Data.DataRowState> .) Alternativ können Sie eine Datenansicht eines Datasets erstellen, das auf der Grundlage des Zeilen Zustands filtert und die Count-Eigenschaft von dort abgibt.

     Im folgenden Beispiel wird gezeigt, wie die-Methode aufgerufen wird <xref:System.Data.DataRow.Delete%2A> , um die erste Zeile in der `Customers` Tabelle als gelöscht zu markieren:

     [!code-csharp[VbRaddataEditing#8](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#8)]
     [!code-vb[VbRaddataEditing#8](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#8)]

## <a name="determine-if-there-are-changed-rows"></a>Bestimmen, ob geänderte Zeilen vorhanden sind
 Wenn Änderungen an Datensätzen in einem Dataset vorgenommen werden, werden die Informationen zu diesen Änderungen gespeichert, bis ein Commit ausgeführt wird. Sie können die Änderungen übertragen, wenn Sie die- `AcceptChanges` Methode eines Datasets oder einer Datentabelle oder die- `Update` Methode eines TableAdapter oder Daten Adapters aufzurufen.

 Änderungen werden in jeder Daten Zeile auf zwei Arten nachverfolgt:

- Jede Daten Zeile enthält Informationen, die sich auf Ihre Daten beziehen <xref:System.Data.DataRow.RowState%2A> (z. b.,, <xref:System.Data.DataRowState> <xref:System.Data.DataRowState> <xref:System.Data.DataRowState> oder <xref:System.Data.DataRowState> ).

- Jede geänderte Daten Zeile enthält mehrere Versionen dieser Zeile ( <xref:System.Data.DataRowVersion> ), die ursprüngliche Version (vor den Änderungen) und die aktuelle Version (nach Änderungen). Während des Zeitraums, in dem eine Änderung aussteht (die Zeit, zu der Sie auf das Ereignis reagieren können <xref:System.Data.DataTable.RowChanging> ), ist auch eine dritte Version – die vorgeschlagene Version – verfügbar.

  Wenn das Dataset geändert wurde, gibt die <xref:System.Data.DataSet.HasChanges%2A>-Methode eines Datasets den Wert `true` zurück. Nachdem festgestellt wurde, dass geänderte Zeilen vorhanden sind, können Sie die `GetChanges`-Methode eines <xref:System.Data.DataSet> oder einer <xref:System.Data.DataTable> aufrufen, um die Gruppe der geänderten Zeilen zurückzugeben. Weitere Informationen finden Sie unter Gewusst [wie: Abrufen geänderter Zeilen](https://msdn.microsoft.com/library/6ff0cbd0-5253-48e7-888a-144d56c2e0a9).

#### <a name="to-determine-if-changes-have-been-made-to-any-rows"></a>So bestimmen Sie, ob Änderungen an Zeilen vorgenommen wurden

- Rufen Sie die <xref:System.Data.DataSet.HasChanges%2A>-Methode eines Datasets auf, um geänderte Zeilen zu suchen.

     Im folgenden Beispiel wird veranschaulicht, wie Sie anhand des Rückgabewerts der <xref:System.Data.DataSet.HasChanges%2A>-Methode feststellen, ob ein Dataset mit dem Namen `NorthwindDataset1` geänderte Zeilen enthält:

     [!code-csharp[VbRaddataEditing#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#12)]
     [!code-vb[VbRaddataEditing#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#12)]

## <a name="determine-the-type-of-changes"></a>Bestimmen der Art der Änderungen
 Sie können auch überprüfen, welche Art von Änderungen in einem Dataset vorgenommen wurden, indem Sie einen Wert aus der- <xref:System.Data.DataRowState> Enumeration an die- <xref:System.Data.DataSet.HasChanges%2A> Methode übergeben.

#### <a name="to-determine-what-type-of-changes-have-been-made-to-a-row"></a>So stellen Sie fest, welche Art von Änderungen an einer Zeile vorgenommen wurden

- Übergeben Sie einen <xref:System.Data.DataRowState>-Wert an die <xref:System.Data.DataSet.HasChanges%2A>-Methode.

     Das folgende Beispiel zeigt, wie Sie ein DataSet mit dem Namen überprüfen `NorthwindDataset1` , um zu ermitteln, ob ihm neue Zeilen hinzugefügt wurden:

     [!code-csharp[VbRaddataEditing#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#13)]
     [!code-vb[VbRaddataEditing#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#13)]

## <a name="to-locate-rows-that-have-errors"></a>So suchen Sie Zeilen mit Fehlern
 Beim Arbeiten mit einzelnen Spalten und Daten Zeilen können Fehler auftreten. Sie können die- `HasErrors` Eigenschaft überprüfen, um festzustellen, ob Fehler in <xref:System.Data.DataSet> , oder vorhanden sind <xref:System.Data.DataTable> <xref:System.Data.DataRow> .

1. Überprüfen Sie die- `HasErrors` Eigenschaft, um festzustellen, ob das DataSet Fehler enthält.

2. Wenn die- `HasErrors` Eigenschaft ist `true` , durchlaufen Sie die Auflistungen von Tabellen und anschließend durch die Zeilen, um die Zeile mit dem Fehler zu ermitteln.

     [!code-csharp[VbRaddataEditing#23](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#23)]
     [!code-vb[VbRaddataEditing#23](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#23)]
