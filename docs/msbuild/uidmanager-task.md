---
title: UidManager-Aufgabe| Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37692c541fb2a6e9b2ccf61083dd383e56a79766
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631522"
---
# <a name="uidmanager-task"></a>UidManager-Aufgabe

Die Aufgabe <xref:Microsoft.Build.Tasks.Windows.UidManager> überprüft, aktualisiert oder entfernt eindeutige Bezeichner (UIDs), um alle XAML-Elemente zu lokalisieren, die in den XAML-Quelldateien enthalten sind.

## <a name="task-parameters"></a>Aufgabenparameter

| Parameter | Beschreibung |
|-------------------------| - |
| `IntermediateDirectory` | Optionaler **String**-Parameter.<br /><br /> Gibt das Verzeichnis an, das zur Sicherung der XAML-Quelldateien verwendet wird, die vom **MarkupFiles**-Parameter angegeben werden. |
| `MarkupFiles` | Erforderlicher **ITaskItem[]** -Parameter.<br /><br /> Gibt die XAML-Quelldateien an, die für UID-Überprüfung, -Aktualisierung oder -Entfernung einbezogen werden. |
| `Task` | Erforderlicher **String**-Parameter.<br /><br /> Gibt die UID-Verwaltungsaufgabe an, die Sie ausführen möchten. Gültige Optionen sind **Check**, **Update** oder **Remove**. |

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird mit der <xref:Microsoft.Build.Tasks.Windows.UidManager>-Aufgabe überprüft, ob die angegebenen XAML-Quelldateien XAML-Elemente enthalten, die über geeignete UIDs verfügen.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="UidManagerTask">
    <UidManager
      Task="Check"
      MarkupFiles="Page1.xaml;Page2.xaml"
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />
  </Target>
</Project>
```

## <a name="see-also"></a>Siehe auch

- [WPF-MSBuild-Referenz](../msbuild/wpf-msbuild-reference.md)
- [Referenz zu MSBuild-Tasks](../msbuild/wpf-msbuild-task-reference.md)
- [MSBuild-Referenz](../msbuild/msbuild-reference.md)
- [Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)
- [Erstellen einer WPF-Anwendung (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)
- [How to: Lokalisieren einer Anwendung](/dotnet/framework/wpf/advanced/how-to-localize-an-application)