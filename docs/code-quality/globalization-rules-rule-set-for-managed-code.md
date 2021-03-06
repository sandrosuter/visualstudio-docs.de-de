---
title: Regelsatz für Globalisierungsregeln für verwalteten Code
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2af6126c751d03968dc7ecd87693e3546376c12a
ms.sourcegitcommit: 5caad925ca0b5d136416144a279e984836d8f28c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2020
ms.locfileid: "89509860"
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>Regelsatz für Globalisierungsregeln für verwalteten Code

Verwenden Sie den Regelsatz Microsoft-Globalisierungsregeln, um sich auf Probleme zu konzentrieren, die möglicherweise verhindern, dass Daten in Ihrer Anwendung in verschiedenen Sprachen, Gebiets Schemata und Kulturen ordnungsgemäß angezeigt werden. Sie sollten diesen Regelsatz einschließen, wenn Ihre Anwendung lokalisiert, globalisiert oder beides ist.

|Regel|Beschreibung|
|----------|-----------------|
|[CA1303](../code-quality/ca1303.md)|Literale nicht als lokalisierte Parameter übergeben.|
|[CA1304](../code-quality/ca1304.md)|CultureInfo angeben.|
|[CA1305](../code-quality/ca1305.md)|IFormatProvider angeben.|
|[CA1307](../code-quality/ca1307.md)|StringComparison zur Übersichtlichkeit angeben|
|[CA1308](../code-quality/ca1308.md)|Zeichenfolgen in Großbuchstaben normalisieren.|
|[CA1309](../code-quality/ca1309.md)|Ordinal-StringComparison verwenden.|
|[CA1310](../code-quality/ca1310.md)|StringComparison für Richtigkeit angeben|
|[CA2101](../code-quality/ca2101.md)|Marshalling für P/Invoke-Zeichenfolgenargumente festlegen.|
