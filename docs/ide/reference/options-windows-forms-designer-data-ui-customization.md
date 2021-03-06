---
title: Optionen, Windows Forms-Designer, Anpassung der Datenbenutzeroberfläche
ms.date: 08/09/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.WindowsFormsDesigner.Data_UI_Customization
helpviewer_keywords:
- Data UI customization options
- Options dialog box, Windows Forms Designer, Data UI Customization
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: e48777a50ddf66a8e5493698fb401ff7201de03e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "76114689"
---
# <a name="options-dialog-box-windows-forms-designer--data-ui-customization"></a>Dialogfeld „Optionen“: Windows Forms-Designer > Anpassung der Datenbenutzeroberfläche

Dieses Dialogfeld definiert, welche Steuerelemente in der Liste der verfügbaren Steuerelemente für Elemente im Fenster „Datenquellen“ angezeigt werden. Um es zu öffnen, wählen Sie **Tools** > **Optionen** und dann **Windows Forms-Designer** > **Anpassung der Datenbenutzeroberfläche**.

Sie können ein Steuerelement aus einem Element im Fenster „Datenquellen“ auswählen, bevor Sie es in einer Windows Forms-App auf das Formular ziehen. Verfügbare Steuerelemente werden anhand des Datentyps des Elements festgelegt. Jeder Datentyp enthält eine Liste der gültigen zugehörigen Steuerelemente, wie sie in diesem Dialogfeld definiert sind, einschließlich eines Standardsteuerelements. Wenn Sie ein Element aus dem Fenster „Datenquellen“ auf ein Formular ziehen, ohne ein Steuerelement auszuwählen, wird dem Formular das Standardsteuerelement für den Datentyp des ausgewählten Elements hinzugefügt.

Sie können die Liste der zugehörigen Steuerelemente anpassen, indem Sie die Kontrollkästchen der verfügbaren Steuerelemente für jeden Datentyp aktivieren und deaktivieren. Um ein Steuerelement zur Liste hinzuzufügen, fügen Sie ein Steuerelement hinzu, das entweder das Datenbindungsattribut <xref:System.ComponentModel.DefaultBindingPropertyAttribute> oder <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> für die Toolbox implementiert. Das-Steuerelement wird dann in der Liste der Steuerelemente für den-Datentyp angezeigt. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen benutzerdefinierter Steuerelemente zum Datenquellenfenster](../..//data-tools/add-custom-controls-to-the-data-sources-window.md).

## <a name="data-type"></a>Datentyp

Zeigt eine Liste der Typen an, mit denen Steuerelemente verknüpft werden. Tabellen werden als Datentyp `[List]` dargestellt. Spalten werden als tatsächlicher Datentyp der Spalte im zugrunde liegenden Datenspeicher dargestellt.

## <a name="associated-controls"></a>Zugeordnete Steuerelemente

Zeigt eine Liste mit Steuerelementen an, die dem ausgewählten Datentyp zugeordnet sind. Aktivieren bzw. deaktivieren Sie das Kontrollkästchen neben dem Steuerelement, um es zuzuordnen oder die Zuordnung aufzuheben. Ausgewählte Steuerelemente werden im Fenster „Datenquellen“ für eine Datenbankspalte angezeigt, die an den zugehörigen Datentyp gebunden ist.

## <a name="set-default"></a>Standard festlegen

Weist den ausgewählten Steuerelementtypen als Standardwert für den ausgewählten Datentyp zu. Das Standardsteuerelement wird als erste Auswahl im Kontextmenü für eine Datenbankspalte im Fenster „Datenquellen“ angezeigt. Wenn Sie ein Element aus dem Fenster „Datenquellen“ auf ein Formular ziehen, ohne ein Steuerelement auszuwählen, wird dem Formular das Standardsteuerelement für den Datentyp des ausgewählten Elements hinzugefügt.

Es kann nur ein Steuerelement als Standardwert für einen Datentyp zugewiesen werden.

## <a name="clear-default"></a>Standardwert löschen

Entfernt die Bezeichnung eines Steuerelements als Standard für den ausgewählten Datentyp. Wenn es für den ausgewählten Datentyp keine Voreinstellung gibt, wird `[None]` als erste Auswahl im Kontextmenü für eine Datenbankspalte dieses Typs angezeigt.
