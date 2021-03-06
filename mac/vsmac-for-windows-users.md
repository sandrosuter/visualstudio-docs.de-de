---
title: Visual Studio für Mac für Windows-Benutzer
description: In diesem Artikel erhalten Sie eine Einführung in die Barrierefreiheitsfunktionen in Visual Studio für Mac und erfahren, wie diese aktiviert werden.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 09/25/2019
ms.assetid: 61CB6883-08CE-470F-8599-6F7570DB756E
ms.openlocfilehash: b414026ba7297dd6c93fecdf56d9a9c58c99f294
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2020
ms.locfileid: "74984271"
---
# <a name="visual-studio-for-mac-for-windows-users"></a>Visual Studio für Mac für Windows-Benutzer

Die Migration von einem Betriebssystem zu einem anderen kann eine gewaltige Herausforderung sein. Es gibt häufig sehr feine Unterschiede bei plattformübergreifenden Anwendungen – von der Benutzeroberfläche bis hin zur Kategorisierung der Menüelemente. Benutzer müssen sich auch erst an die Benutzeroberfläche des neuen Betriebssystems gewöhnen. Hier lernen Sie die gängigsten Unterschiede zwischen Visual Studio für Mac und Visual Studio für Windows kennen. Sie lernen auch einige unterschiedliche Konventionen zwischen macOS und Windows kennen.

## <a name="keyboard-shortcuts"></a>Tastenkombinationen

Als Entwickler sind Sie sicher daran gewöhnt, zur Ausführung Ihrer Aufgaben und für die Navigation die Tastatur zu verwenden. Einige der Tastaturtasten sind bei Mac- und Windows-Computern gleich. Daher könnten Sie auf den Gedanken kommen, dass für Tastaturaktionen wie z. B. Kopieren und Einfügen die gleichen Tastenkombinationen verwendet werden. Dies ist jedoch nicht immer der Fall. Glücklicherweise können Sie Ihre Tastenzuordnungen in Visual Studio für Mac ändern, um diese an Visual Studio für Windows anzupassen.

Wenn Sie Visual Studio für Mac zum ersten Mal ausführen, wird das Fenster zur Auswahl von Tastenkombinationen angezeigt: ![Fenster mit Tastenzuordnungen](media/ide-tour-2019-keyboard-shortcut.png)

Wenn Sie die Tastenzuordnungen zu einem späteren Zeitpunkt ändern möchten, finden Sie sie in den Einstellungen: ![Einstellungen für Tastenzuordnungen](media/customizing-the-ide-image10a.png)

Beachten Sie unbedingt, dass macOS andere systemweite Tastenkombinationen verwendet als Windows. Durch Ändern der Einstellungen für Tastenzuordnungen können Sie vertraute Windows-Tastenkombinationen in Visual Studio für Mac verwenden. In anderen Bereichen von macOS müssen Sie die macOS-Tastenkombinationen jedoch kennen.

Die macOS-Befehlstaste (⌘) kann im Allgemeinen genauso verwendet werden wie die STRG-Taste unter Windows. Im Folgenden finden Sie einige Beispiele sowie weitere häufig verwendete Tastenkombinationen:

|Aufgabe                   |Windows-Tastenkombination         |macOS-Tastenkombination      |
|-----------------------|-------------------------|--------------------|
|Kopieren                   |`Ctrl + C`               |`⌘ + C`             |
|Einfügen                  |`Ctrl + V`               |`⌘ + V`             |
|Ausschneiden                    |`Ctrl + X`               |`⌘ + X`             |
|undo                   |`Ctrl + Z`               |`⌘ + Z`             |
|Wiederholen                   |`Ctrl + Shift + Z`       |`⌘ + Shift + Z`     |
|Text rechts vom Cursor löschen |`Delete`                 |`fn + Backspace`    |
|Wort löschen            |`Ctrl + Delete`          |`fn + ⌥ + Backspace`|

> [!TIP]
> Eine umfassende Liste der macOS-Tastenkombinationen finden Sie auf der [Website des Apple-Supports](https://support.apple.com/en-us/HT201236).

## <a name="menus"></a>Menüs

Menüs sind in macOS anders angeordnet als unter Windows. Visual Studio für Mac bildet hierbei keine Ausnahme. Im Folgenden finden Sie einige der gängigsten Menüoptionen:

|Aufgabe                   |Visual Studio (Windows)                                              |Visual Studio für Mac                |
|-----------------------|---------------------------------------------------------------------|-------------------------------------|
|Einstellungen (Optionen)  |Tools > Optionen...                                                   |Visual Studio > Einstellungen...       |
|Erweiterungen             |Erweiterungen > Erweiterungen verwalten                                       |Visual Studio > Erweiterungen...        |
|Layouts                |Fenster > Fensterlayout anwenden > [Layout auswählen]                       |Ansicht > [Layout auswählen]               |
|Updates                |Hilfe > Nach Updates suchen                                             |Visual Studio > Nach Updates suchen... |
|NuGet-Paket-Manager  |Tools > NuGet-Paket-Manager > NuGet-Pakete oder -Projektmappe verwalten... |Projekt > NuGet-Pakete verwalten...   |
|Pads/Fenster         |Ansicht > [Pad/Fenster auswählen]                                         |Ansicht > Pads > [Pad/Fenster auswählen]  |
|Tools suchen             |Bearbeiten > Suchen und ersetzen > [Tool auswählen]                              |Suche > [Tool auswählen]               |
|Informationen zu Visual Studio    |Hilfe > Info zu Microsoft Visual Studio                                 |Visual Studio > Info zu Visual Studio  

> [!NOTE]
> Eine Übersicht über die gängigsten Features in Visual Studio für Mac finden Sie in der [IDE-Tour](ide-tour.md).