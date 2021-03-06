---
title: Anzeigen verwandter Daten in WPF-Anwendungen | Microsoft-Dokumentation
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
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 3aa80194-0191-474d-9d28-5ec05654b426
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6efa79fc59ed9812cf6162096dd462100b71fbca
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "72672418"
---
# <a name="display-related-data-in-wpf-applications"></a>Anzeigen zugehöriger Daten in WPF-Anwendungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

In einigen Anwendungen können Sie mit Daten arbeiten, die aus mehreren Tabellen oder Entitäten stammen, die in einer über-/Unterordnungsbeziehung miteinander verknüpft sind. Beispielsweise können Sie ein Raster anzeigen, in dem Kunden aus einer Tabelle angezeigt werden `Customers` . Wenn der Benutzer einen bestimmten Kunden auswählt, werden in einem anderen Raster die Bestellungen für diesen Kunden aus einer verknüpften `Orders` Tabelle angezeigt.

 Sie können Daten gebundene Steuerelemente erstellen, die verwandte Daten anzeigen, indem Sie Elemente aus dem **Datenquellen** Fenster in den WPF-Designer ziehen.

## <a name="to-create-controls-that-display-related-records"></a>So erstellen Sie Steuerelemente, die verknüpfte Datensätze anzeigen

1. Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**, um das Fenster **Datenquellen** zu öffnen.

2. Klicken Sie auf **Neue Datenquelle hinzufügen**, und führen Sie den **Assistenten zum Konfigurieren von Datenquellen** aus.

3. Öffnen Sie den WPF-Designer, und stellen Sie sicher, dass der Designer einen Container enthält, bei dem es sich um ein gültiges Ablage Ziel für die Elemente im **Datenquellen** Fenster handelt.

     Weitere Informationen zu gültigen Drop-Zielen finden [Sie unterbinden von WPF-Steuerelementen an Daten in Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md).

4. Erweitern Sie im Fenster **Datenquellen** den Knoten, der die übergeordnete Tabelle oder das übergeordnete Objekt in der Beziehung darstellt. Die übergeordnete Tabelle oder das übergeordnete Objekt befindet sich auf der 1-Seite einer 1: n-Beziehung.

5. Ziehen Sie den übergeordneten Knoten (oder einzelne Elemente im übergeordneten Knoten) aus dem **Datenquellen** Fenster auf ein gültiges Ablage Ziel im Designer.

     Visual Studio generiert XAML, das neue Daten gebundene Steuerelemente für jedes Element erstellt, das Sie ziehen. Die XAML fügt den Ressourcen des Ablage Ziels auch ein neues- <xref:System.Windows.Data.CollectionViewSource> Objekt für die übergeordnete Tabelle oder das übergeordnete Objekt hinzu. Für einige Datenquellen generiert Visual Studio auch Code, um die Daten in die übergeordnete Tabelle oder das übergeordnete Objekt zu laden. Weitere Informationen finden Sie unter [Binden von WPF-Steuerelementen an Daten in Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md).

6. Suchen Sie im Fenster **Datenquellen** nach der zugehörigen untergeordneten Tabelle oder dem entsprechenden Objekt. Verknüpfte untergeordnete Tabellen und Objekte werden im unteren Bereich der Datenliste des übergeordneten Knotens als erweiterbare Knoten angezeigt.

7. Ziehen Sie den untergeordneten Knoten (oder einzelne Elemente im untergeordneten Knoten) aus dem **Datenquellen** Fenster auf ein gültiges Ablage Ziel im Designer.

     Visual Studio generiert XAML, das neue Daten gebundene Steuerelemente für jedes der Elemente erstellt, die Sie ziehen. Die XAML fügt <xref:System.Windows.Data.CollectionViewSource> den Ressourcen des Ablage Ziels auch ein neues für die untergeordnete Tabelle oder das untergeordnete Objekt hinzu. Diese neue <xref:System.Windows.Data.CollectionViewSource> ist an die-Eigenschaft der übergeordneten Tabelle oder des Objekts gebunden, das Sie soeben in den Designer gezogen haben. Für einige Datenquellen generiert Visual Studio auch Code, um die Daten in die untergeordnete Tabelle oder das untergeordnete Objekt zu laden.

     In der folgenden Abbildung wird die Tabelle mit verknüpften **Bestellungen** der **Customers** -Tabelle in einem Dataset im **Datenquellen** Fenster veranschaulicht.

     ![Relation im Datenquellenfenster](../data-tools/media/datasources2.gif "DataSources2")

## <a name="see-also"></a>Weitere Informationen
 [Binden von WPF-Steuerelementen an Daten in Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md) [Binden von WPF-Steuerelementen an Daten in Visual Studio erstellen von](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md) Nachschlage [Tabellen in WPF-Anwendungen](../data-tools/create-lookup-tables-in-wpf-applications.md) Exemplarische Vorgehensweise: Anzeigen verknüpfter [Daten in einer WPF-Anwendung](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)
