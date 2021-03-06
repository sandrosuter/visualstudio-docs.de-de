---
title: Auswählen des Installationsverzeichnisses für ein VSPackage | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c4100c045181f32e51abcc59116a69cad6cc33b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697248"
---
# <a name="choosing-the-installation-directory-for-a-vspackage"></a>Auswählen des Installationsverzeichnisses für ein VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ein VSPackage und seine unterstützenden Dateien müssen sich im Dateisystem eines Benutzers befinden. Der Speicherort hängt davon ab, ob das VSPackage verwaltet oder nicht verwaltet ist, ob es sich um ein paralleles Versions Schema und eine Benutzer Auswahl handelt.  
  
## <a name="unmanaged-vspackages"></a>Nicht verwaltete VSPackages  
 Ein nicht verwaltetes VSPackage ist ein com-Server, der an einem beliebigen Speicherort installiert werden kann. Die Registrierungsinformationen müssen den Speicherort exakt widerspiegeln. Die Benutzeroberfläche des Installers sollte einen Standard Speicherort als Unterverzeichnis der Eigenschaft ProgramFilesFolder Windows Installer bereitstellen. Beispiel:  
  
 ProgramFilesFolder Mycompany\myvspackageproduct\v1.0\  
  
 Der Benutzer sollte das Standardverzeichnis ändern können, um Benutzer zu unterstützen, die eine kleine Start Partition aufbewahren und die Installation von Anwendungen und Tools auf einem anderen Volume bevorzugen.  
  
 Wenn das parallele Schema ein VSPackage mit Versions Angabe verwendet, können Sie Unterverzeichnisse zum Speichern verschiedener Versionen verwenden. Beispiel:  
  
 ProgramFilesFolder Mycompany\myvspackageproduct\v1.0\  
  
 ProgramFilesFolder Mycompany\myvspackageproduct\v1.0\2003\  
  
 ProgramFilesFolder Mycompany\myvspackageproduct\v1.0\2005\  
  
## <a name="managed-vspackages"></a>Verwaltete VSPackages  
 Verwaltete VSPackages können auch an einem beliebigen Speicherort installiert werden. Sie sollten jedoch die Installation im globalen Assemblycache (GAC) immer in Erwägung gezogen, um die Ladezeiten der Assembly zu verringern. Da verwaltete VSPackages immer Assemblys mit starkem Namen sind, bedeutet die Installation im GAC, dass die Signatur Überprüfung mit starkem Namen nur zur Installationszeit erfolgt. Assemblys mit starkem Namen, die an anderer Stelle im Dateisystem installiert sind, müssen bei jedem Laden überprüft werden. Wenn Sie verwaltete VSPackages im GAC installieren, verwenden Sie den **/Assembly** -Schalter des regpkg-Tools, um Registrierungseinträge zu schreiben, die auf den starken Namen der Assembly verweisen.  
  
 Wenn Sie verwaltete VSPackages an einem anderen Speicherort als dem globalen Assemblycache installieren, befolgen Sie die vorherigen Ratschläge für nicht verwaltete VSPackages zum Auswählen von Verzeichnishierarchien. Verwenden Sie den **/CodeBase** -Schalter des regpkg-Tools, um Registrierungseinträge zu schreiben, die auf den Pfad der VSPackage-Assembly verweisen.  
  
 Weitere Informationen finden Sie unter [registrieren und Aufheben der Registrierung von VSPackages](../../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="satellite-dlls"></a>Satelliten-DLLs  
 Gemäß der Konvention befinden sich VSPackage-Satelliten-DLLs – die Ressourcen für ein bestimmtes Gebiets Schema – enthalten, in Unterverzeichnissen des VSPackage-Verzeichnisses. Die Unterverzeichnisse entsprechen den LCID-Werten (Locale ID).  
  
 Die [Verwaltung von VSPackages](../../extensibility/managing-vspackages.md) gibt an, dass Registrierungseinträge steuern, wo [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tatsächlich nach der Satelliten-DLL eines VSPackages sucht. Allerdings [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] versucht, eine Satelliten-DLL in einem Unterverzeichnis mit dem Namen für einen LCID-Wert in der folgenden Reihenfolge zu laden:  
  
1. Standard-LCID (vs LCID z. b. \ 1033 für Englisch)  
  
2. Standard-LCID mit der Standard unter Sprache.  
  
3. System Standard-LCID.  
  
4. System Standard-LCID mit der Standard unter Sprache.  
  
5. US-Englisch (. \ 1033 oder .\0x409).  
  
   Wenn die VSPackage-dll Ressourcen enthält und der Registrierungs Eintrag satellitedll\dllname darauf verweist, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] versucht, Sie in der obigen Reihenfolge zu laden.  
  
## <a name="see-also"></a>Weitere Informationen  
 [Auswählen zwischen freigegebenen und versionierten VSPackages](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Verwalten von VSPackages](../../extensibility/managing-vspackages.md)   
 [Verwaltete Paket Registrierung](https://msdn.microsoft.com/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)
