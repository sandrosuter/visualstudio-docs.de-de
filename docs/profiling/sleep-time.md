---
title: Standbyzeit | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be2d566228367e2cdb07aecc2d73eaf82a6d961f
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "62980212"
---
# <a name="sleep-time"></a>Standbyzeit
Diese Segmente in der Zeitachse werden der Blockierungszeit zugeordnet, die als Standby kategorisiert ist. Die Standbykategorie impliziert, dass ein Thread seinen logischen Kern freiwillig aufgegeben hat und jetzt keine Funktionen ausführt. Während dieser Zeit wurde ein Thread in einer API blockiert, die die Parallelitätsschnellansicht als Standby erfasst. APIs wie `Sleep()` und `SwitchToThread()` gehören zu dieser Gruppe.

## <a name="see-also"></a>Weitere Informationen
- [Threadansicht](../profiling/threads-view-parallel-performance.md)