---
title: Optionen, Windows Forms-Designer, Allgemein
ms.date: 08/09/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.WindowsFormsDesigner.General
helpviewer_keywords:
- Windows Forms Designer options
- Options dialog box, Windows Forms Designer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 2a72b27dc2277501d0e0957c8b89b551f4d6852d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "75568060"
---
# <a name="options-dialog-box-windows-forms-designer"></a>Dialogfeld „Optionen“: Windows Forms-Designer

Auf der Optionsseite von Windows Forms-Designer können Sie Einstellungen für die Raster und andere Funktionen des Windows Forms-Designers in Visual Studio festlegen. Öffnen Sie das Dialogfeld **Optionen** über das Menü **Extras**.

## <a name="code-generation-settings"></a>Einstellungen für Codegenerierung

**Optimierte Codegenerierung**\
Aktiviert die optimierte Codegenerierung. Einige Steuerelemente sind möglicherweise mit diesem Modus nicht kompatibel. Damit diese Änderung wirksam wird, muss Visual Studio geschlossen und erneut geöffnet werden.

## <a name="high-dpi-support"></a>Unterstützung für hohe DPI-Werte

**Benachrichtigungen zur DPI-Skalierung**\
Zeigt eine Meldung im Windows Forms-Designer zum Neustart von Visual Studio mit einer Skalierung von 100 % an. Weitere Informationen finden Sie unter [Deaktivieren von DPI-Informationen in Visual Studio](/dotnet/framework/winforms/disable-dpi-awareness-visual-studio).

## <a name="layout-settings"></a>Layouteinstellungen

**Rasterzellen-Standardgröße**\
Legt den Abstand zwischen horizontalen und vertikalen Gitternetzlinien auf dem Designer in Pixel fest. Die Standardgröße ist 8, 8. Die Maximalgröße ist 200, 200.

**Layoutmodus**\
Gibt das für das Layout zu verwendende Ausrichtungssystem an. Sie können „Am Raster ausrichten“ oder „Ausrichtungslinien“ auswählen.

**Raster anzeigen**\
Gibt an, ob Designer das Größenänderungsraster anzeigen. Standardmäßig ist das Raster aktiviert.

**Am Raster ausrichten**\
Bestimmt, ob Designer Objekte und Steuerelemente am Raster ausrichten. Mit anderen Worten, die Größenänderung und Bewegung von Elementen auf dem Designer ist beim Einschalten dieser Funktion auf die GridSize-Inkremente beschränkt. Das Aktivieren von „Am Raster ausrichten“ erleichtert die genaue Ausrichtung der verschiedenen Aspekte der Benutzeroberfläche, beschränkt aber die Flexibilität, mit der Steuerelemente platziert werden können. Standardmäßig ist „Am Raster ausrichten“ aktiviert.

## <a name="object-bound-smart-tag-settings"></a>Einstellungen für objektgebundene Smarttags

**Smarttags automatisch öffnen**\
Bestimmt, ob Steuerelemente und Komponenten Smarttags anzeigen. Nicht alle Steuerelemente und Komponenten unterstützen Smarttags.

## <a name="refactoring"></a>Umgestaltung

**Refactoring beim Umbenennen aktivieren**\
Wenn auf `true` gesetzt, wird eine Refactoringvorgang zur Umbenennung durchgeführt, wenn Sie eine Komponente aus dem Eigenschaftenfenster oder dem Fenster „Dokumentgliederung“ umbenennen.

## <a name="toolbox"></a>Werkzeugkasten

**Toolbox automatisch ausfüllen**\
Bestimmt, ob das Toolfenster automatisch mit Komponenten und Steuerelementen aufgefüllt wird, die vom Projekt erstellt werden.
