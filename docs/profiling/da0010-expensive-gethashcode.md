---
title: 'DA0010: Speicherintensive GetHashCode-Funktionen | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 8f94277822d1fcd4210f0f8d79591fc4e2ed3d9e
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "85520678"
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Speicherintensive GetHashCode-Funktionen

|Element|Wert|
|-|-|
|Regel-ID|DA0010|
|Kategorie|.NET Framework-Verwendung|
|Profilerstellungsmethoden|Sampling<br /><br /> .NET-Arbeitsspeicher|
|Meldung|GetHashCode-Funktionen dürfen nicht speicherintensiv sein und keinen Speicher belegen. Reduzieren Sie daher, wenn möglich, die Komplexität der Hashcodefunktionen.|
|Nachrichtentyp|Warnung|

## <a name="cause"></a>Ursache
 Aufrufe der GetHashCode-Methode des Typs machen einen großen Teil der Profilerstellungsdaten aus, oder die Methode belegt Arbeitsspeicher.

## <a name="rule-description"></a>Regelbeschreibung
 Hashing ist eine Technik, mit deren Hilfe Sie ein bestimmtes Element in einer Auflistung mit vielen Elementen schnell finden können. Da Hashtabellen groß sein können und hohe Zugriffsraten unterstützen müssen, sollten sie auch effizient konzipiert sein. Folglich sollten GetHashCode-Methoden in .NET Framework keinen Speicherplatz belegen. Wenn Speicherplatz belegt wird, wird die Belastung des Garbage Collectors größer, wodurch die Methode unter Umständen nur mit einer Verzögerung ausgeführt werden kann, wenn es nötig sein sollte, die Garbage Collection aufgrund der Reservierungsanforderung auszuführen.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Verringern Sie die Komplexität der Methode.
