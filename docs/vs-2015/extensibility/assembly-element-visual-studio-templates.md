---
title: Assembly-Element (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio templates]
- <Assembly> element [Visual Studio templates]
ms.assetid: 9242f76a-1273-4b8a-8f26-6606f91829ef
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 10c894f3507ae760624b6ae18f785aae6016cd5e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184709"
---
# <a name="assembly-element-visual-studio-templates"></a>Assembly-Element (Visual Studio-Vorlagen)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Gibt Informationen zu einer Assembly an, die von der Vorlage zum Hinzufügen eines Verweises auf diese Assembly zu Projekten verwendet wird.  
  
 \<VSTemplate>  
 \<TemplateContent>  
 \<References>  
 \<Reference>  
 \<Assembly>  
  
## <a name="syntax"></a>Syntax  
  
```  
<Assembly> AssemblyName </Assembly>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[Referenz](../extensibility/reference-element-visual-studio-templates.md)|Gibt den Assemblyverweis an, der hinzugefügt wird, wenn das Element einem Projekt hinzugefügt wird.|  
  
## <a name="text-value"></a>Textwert  
 Ein Textwert ist erforderlich.  
  
 Dieser Text gibt die Assembly an, die einem Projekt hinzugefügt werden soll, wenn die Element Vorlage instanziiert wird. Dieser Assemblyname muss auf eine der folgenden Arten angegeben werden:  
  
- Als vollständiger AssemblyName. Beispiel:  
  
    ```  
    <Assembly>  
        MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom = null.  
    </Assembly>  
    ```  
  
- Als einfache Textreferenz. Beispiel:  
  
    ```  
    <Assembly> System </Assembly>  
    ```  
  
## <a name="remarks"></a>Bemerkungen  
 `Assembly` ist ein erforderliches untergeordnetes Element von `Reference`.  
  
 Die `Reference` `References,` Elemente, und `Assembly` können nur in. VSTEMPLATE-Dateien mit dem- `Type` Attribut Wert verwendet werden `Item` .  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das-Element einer Element `TemplateContent` Vorlage. Dieses XML fügt Verweise auf die System.dll und System.Data.dll Assemblys hinzu.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Schema Referenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt-und Element Vorlagen](../ide/creating-project-and-item-templates.md)
