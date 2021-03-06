---
title: 'Visual Studio für Mac: Überblick'
description: Visual Studio für Mac bietet eine integrierte Entwicklungsumgebung zum Erstellen von .NET-Anwendungen unter macOS. Dazu gehören ASP.NET Core-Websites und Xamarin-Projekte für iOS, Android, Mac und Xamarin.Forms.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 07/03/2020
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: 56af8f7cd30ec8e41ece2772dc63d67a2dbf3976
ms.sourcegitcommit: 703c68667261df5985a73282c1cbb0541118989c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89402612"
---
# <a name="visual-studio-2019-for-mac-tour"></a>Visual Studio 2019 für Mac: Überblick

Visual Studio für Mac ist eine _integrierte Entwicklungsumgebung_ für .NET auf dem Mac, die Sie verwenden können, um Code erst zu bearbeiten, zu debuggen und zu kompilieren und um anschließend eine App zu veröffentlichen. Zusätzlich zu Code-Editor und -Debugger enthält Visual Studio für Mac Compiler, Tools für die Codevervollständigung, grafische Designer und Features für die Quellcodeverwaltung, um die Entwicklung von Software zu vereinfachen.

Visual Studio für Mac unterstützt viele der Dateitypen, die auch vom entsprechenden Windows-Pendant unterstützt werden (z.B. `.csproj`-, `.fsproj`- oder `.sln`-Dateien), sowie Features wie EditorConfig. Sie können also die integrierte Entwicklungsumgebung verwenden, die Ihren Anforderungen am besten entspricht.
Das Erstellen, Öffnen und Entwickeln einer Anwendung ist eine vertraute Erfahrung für jeden, der schon einmal Visual Studio unter Windows verwendet hat. Zusätzlich werden auch in Visual Studio für Mac die leistungsstarken Tools eingesetzt, die sein Windows-Pendant zu einer derartig leistungsfähigen IDE machen. Die Roslyn-Compilerplattform wird für das Refactoring und IntelliSense verwendet. Das zugehörige Projektsystem und die Build-Engine verwenden MSBuild. Der Quellcode-Editor basiert auf denselben Komponenten wie Visual Studio unter Windows. Das Produkt verwendet die gleichen Debugger-Engines für Xamarin- und .NET Core-Apps und die gleichen Designer für Xamarin.iOS und Xamarin.Android.

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>Verwendungsweise von Visual Studio für Mac

Visual Studio für Mac unterstützt die folgenden Entwicklungstypen:

- ASP.NET Core-Webanwendungen mit C#, F# und Unterstützung von Razor-Seiten, JavaScript und TypeScript
- .NET Core-Konsolenanwendungen mit C# oder F#
- Plattformübergreifende Unity-Spiele und -Anwendungen mit C#
- Android-, iOS-, tvOS- und watchOS-Anwendungen in Xamarin mit C# oder F# und XAML
- Cocoa-Desktop-Apps in C# oder F#

In diesem Artikel werden verschiedene Bereiche von Visual Studio für Mac thematisiert, um einen Einblick in einige der Features zu geben, die es zu einem leistungsstarken Tool zur Erstellung dieser Anwendungen machen.

## <a name="ide-tour"></a>IDE-Überblick

Visual Studio für Mac ist in verschiedenen Abschnitten zum Verwalten von Anwendungsdateien und -einstellungen und zum Erstellen und Debuggen von Code organisiert.

## <a name="getting-started"></a>Erste Schritte

Wenn Sie Visual Studio 2019 für Mac zum ersten Mal starten, wird für neue Benutzer ein Anmeldefenster angezeigt. Melden Sie sich mit Ihrem Microsoft-Konto an, um eine kostenpflichtige Lizenz (sofern Sie eine besitzen) zu aktivieren oder eine Verknüpfung zu Azure-Abonnements herzustellen. Sie können auf **I'll do this later** (Später durchführen) klicken und sich später über das Menüelement **Visual Studio > Anmelden** anmelden:

![Anmelden bei Ihrem Azure-Konto](media/ide-tour-2019-start-signin.png)

Anschließend können Sie Ihre IDE anpassen, indem Sie Ihre bevorzugten Tastenkombinationen auswählen: Diesen Schritt können Sie für Visual Studio für Mac, Visual Studio, Visual Studio Code und Xcode durchführen:

![Auswählen der bevorzugten Tastenkombinationen](media/ide-tour-2019-keyboard-shortcut.png)

Nach der Ersteinrichtung wird bei jedem Öffnen von Visual Studio 2019 für Mac das _Startfenster_ angezeigt, das eine Liste der letzten Projekte sowie Schaltflächen zum Öffnen eines vorhandenen Projekts oder zum Erstellen eines neuen Projekts enthält:

![Wählen Sie zwischen aktuellen Projekten aus, oder erstellen Sie ein neues Element.](media/ide-tour-2019-start-projects.png)

## <a name="solutions-and-projects"></a>Projektmappen und Projekte

Das folgende Bild zeigt Visual Studio für Mac mit einer geladenen Anwendung:

![Visual Studio für Mac mit einer geladenen Anwendung](media/ide-tour-image17.png)

In den folgenden Abschnitten wird ein Überblick über die Hauptbereich von Visual Studio für Mac gegeben.

## <a name="solution-pad"></a>Projektmappenpad

Das Projektmappenpad organisiert die Projekte in einer Projektmappe:

![Im Projektmappenpad organisierte Projekte](media/ide-tour-image18.png)

Hier werden Dateien für den Quellcode, Ressourcen, Benutzeroberflächen und Abhängigkeiten in plattformspezifische Projekte organisiert.

Weitere Informationen zum Verwenden von Projekten und Projektmappen in Visual Studio für Mac finden Sie im Artikel [Projektmappen und Projekte](/visualstudio/mac/projects-and-solutions).

## <a name="assembly-references"></a>Assemblyverweise

Assemblyverweise für jedes Projekt stehen im Ordner „Verweise“ zu Verfügung:

![Ordner „Verweise“ im Projektmappenpad](media/ide-tour-image19.png)

Sie können mit dem Dialogfeld **Verweise bearbeiten** zusätzliche Verweise hinzufügen. Dieses kann durch Doppelklicken auf den Ordner „Verweise“ angezeigt werden, oder indem Sie auf **Verweise bearbeiten** in den Kontextmenüaktionen klicken:

![Dialogfeld „Verweise bearbeiten“](media/ide-tour-image20.png)

Weitere Informationen zum Verwenden von Verweisen in Visual Studio für Mac finden Sie im Artikel [Verwalten von Verweisen in einem Projekt](/visualstudio/mac/managing-references-in-a-project).

## <a name="dependencies--packages"></a>Abhängigkeiten/Pakete

Alle in Ihrer App verwendeten externen Abhängigkeiten werden im Ordner „Abhängigkeiten“ oder im Ordner „Pakete“ gespeichert, je nachdem, ob es sich um ein .NET Core- oder ein Xamarin.iOS/Xamarin.Android-Projekt handelt. Diese werden in der Regel in NuGet-Form bereitgestellt.

NuGet ist der beliebteste Paket-Manager für die .NET-Entwicklung. Mit der NuGet-Unterstützung von Visual Studio können Sie leicht nach Paketen suchen und diese in Ihrer Anwendung einem Projekt hinzufügen.

Um Ihrer Anwendung eine Abhängigkeit hinzuzufügen, klicken Sie mit der rechten Maustaste auf den Ordner Abhängigkeiten/Pakete und dann auf **Pakete hinzufügen**:

![Hinzufügen eines NuGet-Pakets](media/ide-tour-image21.png)

Informationen zum Verwenden eines NuGet-Pakets in einer Anwendung finden Sie im Artikel [Einschließen eines NuGet-Pakets in Ihr Projekt](/visualstudio/mac/nuget-walkthrough).

## <a name="source-editor"></a>Quellcode-Editor

Der Code-Editor nutzt dieselben Kernkomponenten wie Visual Studio unter Windows, stellt aber eine vollständig native Benutzeroberfläche bereit. Dabei spielt es keine Rolle, ob Sie in C#, XAML oder JavaScript programmieren.

Dadurch sind u. a. folgende Features verfügbar:

* eine native (auf Cocoa basierende) macOS-Benutzeroberfläche (QuickInfos, Editoroberfläche, Randverzierungen, Textrendering, IntelliSense)
* IntelliSense-Typfilterung und Funktion zum Anzeigen von Importelementen
* Unterstützung für native Texteingaben
* RTL-/BiDi-Sprachunterstützung (von rechts nach links und bidirektional)
* Roslyn 3
* Unterstützung mehrerer Caretzeichen
* Zeilenumbruch
* Aktualisierte IntelliSense-Benutzeroberfläche
* Verbesserte Suchen/Ersetzen-Funktion
* Unterstützung für Codeausschnitte 
* Formatieren der Auswahl
* Inline-Fehlerbehebungsmenüs

Weitere Informationen zum Verwenden des Quellcode-Editors in Visual Studio für Mac finden Sie in der Dokumentation des [Quellcode-Editors](/visualstudio/mac/source-editor).

Sie können Registerkarten anheften, damit diese jederzeit angezeigt werden. Dadurch wird sichergestellt, dass bei jedem Projektstart die gewünschte Registerkarte angezeigt wird. Zeigen Sie auf die Registerkarte, und klicken Sie auf das _Stecknadelsymbol_, um die Registerkarte anzuheften:

![Anheften einer Registerkarte](media/ide-tour-tabpin.png)

## <a name="refactoring"></a>Refactoring

Visual Studio für Mac bietet zwei praktische Möglichkeiten zum Umgestalten Ihres Codes: Kontextaktionen und Quellanalysen. Weitere Informationen finden Sie im Artikel [Umgestaltung](/visualstudio/mac/refactoring).

## <a name="debugging"></a>Debugging

Visual Studio für Mac verfügt über Debugger mit Unterstützung für .NET Core-, .NET Framework-, Unity- und Xamarin-Projekte. Visual Studio für Mac verwendet den .NET Core-Debugger und den Soft-Debugger von Mono, wodurch die IDE verwalteten Code plattformübergreifend debuggen kann. Weitere Informationen zum Debuggen finden Sie im Artikel [Debuggen mit Xamarin](/visualstudio/mac/debugging).

Der Debugger enthält umfangreiche Schnellansichten für besondere Typen wie Zeichenfolgen, Farben und URLs sowie Größen, Koordinaten und Bézierkurven.

Weitere Informationen zu den Datenschnellansichten des Debuggers finden Sie im Artikel [Datenvisualisierungen](/visualstudio/mac/data-visualizations).

## <a name="version-control"></a>Versionskontrolle

Visual Studio für Mac kann in die Quellcodeverwaltungs-Systeme Git und Subversion integriert werden. Projekte unter Quellcodeverwaltung werden mit dem Branch bezeichnet, der neben dem Namen der Projektmappe angezeigt wird:

![Branchname, der ein Projekt unter Quellcodeverwaltung angibt](media/ide-tour-image22.png)

Die Symbole von Dateien mit nicht committeten Änderungen sind im Projektmappenbereich mit einer Anmerkung versehen, wie in der folgenden Abbildung dargestellt:

![Ausgecheckte Dateien im Projektmappenpad](media/ide-tour-image23.png)

Weitere Informationen zum Verwenden der Versionskontrolle in Visual Studio finden Sie im Artikel [Versionskontrolle](/visualstudio/mac/version-control).

## <a name="next-steps"></a>Nächste Schritte

- [Installieren von Visual Studio für Mac](installation.md)
- [Überprüfen der verfügbaren Workloads](workloads.md)

## <a name="related-video"></a>Zugehörige Videos

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>Siehe auch

- [Visual Studio-IDE (unter Windows)](/visualstudio/ide/visual-studio-ide)
