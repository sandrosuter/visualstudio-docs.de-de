---
title: Generieren von Code für eine domänenspezifische Sprache
ms.date: 11/04/2016
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 34b834957dfe18e3fc03a86130a95071dda0badf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "75596579"
---
# <a name="generating-code-from-a-domain-specific-language"></a>Generieren von Code für eine domänenspezifische Sprache

Microsoft [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] bietet eine leistungsstarke Möglichkeit, Code, Dokumente, Konfigurationsdateien und andere Artefakte aus Daten zu generieren, die in Modellen dargestellt werden. Mithilfe von [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] können Sie einen Satz von Klassen erstellen, die Ihre Daten darstellen, und Sie können Ihre Textvorlagen in Klassen schreiben, deren Namen und Eigenschaften diese Daten widerspiegeln.

Fabrikam hat z. b. eine XML-Datei mit Kundennamen und e-Mail-Adressen. Ihre Entwickler erstellen ein Modell, in dem Customer eine Klasse mit den Eigenschaften Name und e-Mail-Adresse ist. Sie schreiben mehrere Textvorlagen, um die Daten zu verarbeiten, einschließlich dieses Fragments, das eine Tabelle aller Kunden als Teil einer HTML-Seite erzeugt:

```
<table>
<# foreach (Customer c in ContactList) {  #>
  <tr><td> <#= c.FullName #> </td>
      <td> <#= c.EmailAddress #> </td> </tr>
<# } #>  </table>
```

Wenn die Kundendatenbank verarbeitet wird, wird die XML-Datei in den Modell Speicher gelesen. Ein *Direktivenprozessor*, der mithilfe von erstellt wurde, [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] macht die Customer-Klasse für den Code in der Textvorlage verfügbar. Viele Textvorlagen können für denselben Speicher ausgeführt werden.

Text Vorlagen sind für erforderlich [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] . Sie werden zum Generieren des Quellcodes für die Elemente des Domänen Modells sowie für das VSPackage und die Steuerelemente verwendet, die zur Integration der Tools in Visual Studio verwendet werden.

In diesem Abschnitt werden einige Methoden zum Erstellen, ändern und Debuggen von Textvorlagen erläutert, die in verwendet werden [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] .

## <a name="in-this-section"></a>In diesem Abschnitt

[Zugreifen auf Modelle aus Text Vorlagen](../modeling/accessing-models-from-text-templates.md)\
Stellt grundlegende Informationen über das verweisen auf die domänenspezifische Sprache in Textvorlagen bereit.

[Exemplarische Vorgehensweise: Debuggen einer Text Vorlage zum Zugreifen auf ein Modell](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)\
Beschreibt, wie Sie die Problembehandlung und das Debuggen für eine Textvorlage durchführen, die auf eine domänenspezifische Sprache verweist.

[Exemplarische Vorgehensweise: Verbinden eines Hosts mit einem generierten Direktivenprozessor](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)\
Beschreibt, wie ein benutzerdefinierter Host mit einem generierten Direktivenprozessor verbunden wird.

[Der dsltexttransform-Befehl](../modeling/the-dsltexttransform-command.md)\
Beschreibt die Befehlsdatei, die für Textvorlagen, die auf domänenspezifische Sprachen verweisen, die ausführbare textTransform-Datei in der Befehlszeile ausführt.

## <a name="reference"></a>Verweis

[Schreiben einer T4-Text Vorlage](../modeling/writing-a-t4-text-template.md)\
Stellt die Syntax von Textvorlagen Direktiven und-Kontroll Blöcken bereit.

## <a name="related-sections"></a>Verwandte Abschnitte

[Code Generierung zur Entwurfszeit mithilfe von T4-Text Vorlagen](../modeling/design-time-code-generation-by-using-t4-text-templates.md)\
Erläutert den Textvorlagen-Transformationsprozess.

[Code Generierung in einem Buildprozess](../modeling/code-generation-in-a-build-process.md)\
Lesen Sie dieses Thema, wenn Sie Dateien aus einer DSL auf einem Buildserver erstellen.
