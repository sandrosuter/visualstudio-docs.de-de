---
title: Einstieg in die Quellcodeverwaltungs-Plug-ins | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 85aa5727f252ad75c45064d7b885e3d282da36a4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "62538160"
---
# <a name="getting-started-with-source-control-plug-ins"></a>Erste Schritte mit Quellcodeverwaltungs-Plug-Ins
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zum Erstellen eines Quellcodeverwaltungs-Plug-Ins müssen Sie eine DLL erstellen, die die in der Quellcodeverwaltungs-Plug-in-API definierten Funktionen implementiert, und dann die dll bei registrieren, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] um Sie für die Verwendung in der Quell Code Versionskontrolle verfügbar zu machen.  
  
 Für Quellcodeverwaltungs-Plug-ins sind drei Versionen der Quellcodeverwaltungs-Plug-in-API (Versionen 1,1, 1,2 und 1,3) verfügbar. Die hier dokumentierte API für das Quellcodeverwaltungs-Plug-in ist Version 1,3. Es wurde für die vollständige Kompatibilität mit Quellcodeverwaltungs-Plug-ins entwickelt, die die Versionen 1,1 und 1,2 unterstützen. Im Abschnitt Neuigkeiten im Abschnitt " [Quellcodeverwaltungs-Plug-in-API Version 1,3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) " werden die neuen Features erläutert, die in der neuesten Version der API für Quellcodeverwaltungs-Plug-Ins unterstützt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Installieren eines Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 Beschreibt, wie Sie die Registrierungseinträge erstellen, die erforderlich sind, um eine Quellcodeverwaltungs-dll zu binden.  
  
 [Neuigkeiten in API-Version 1.3 des Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 Bietet eine kurze Übersicht über die Änderungen, die an der Quellcodeverwaltungs-Plug-in-API in Version 1,3 vorgenommen wurden.  
  
 [Neuigkeiten in API-Version 1.2 des Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 Bietet eine kurze Übersicht über die Änderungen, die an der Quellcodeverwaltungs-Plug-in-API in Version 1,2 vorgenommen wurden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Quellcodeverwaltungs-Plug-Ins](../../extensibility/source-control-plug-ins.md)  
 Stellt eine vollständige Auflistung aller Elemente in der Quellcodeverwaltungs-Plug-in-API bereit.  
  
 [Erstellen eines Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definiert das Quellcodeverwaltungs-Plug-in-SDK und beschreibt die enthaltenen Ressourcen.
