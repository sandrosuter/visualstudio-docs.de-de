---
title: XML-Ausschnitte
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2f2bcdd0c28d7b4b99c92d3346b32ed34aa92a0
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592320"
---
# <a name="xml-snippets"></a>XML-Ausschnitte

Der XML-Editor bietet eine als *XML-Ausschnitte* bezeichnete Funktion, mit dem Sie schneller XML-Dateien erstellen können. Sie können XML-Ausschnitte wiederverwenden, indem Sie diese in die Dateien einfügen. XML-Dateien können auch auf der Grundlage eines XSD-Schemas (XML Schema Definition Language) erstellt werden.

## <a name="reusable-xml-snippets"></a>Wiederverwendbare XML-Ausschnitte

Der XML-Editor enthält viele Ausschnitte, die einige häufig auszuführende Aufgaben beinhalten. Dadurch wird Ihnen das Erstellen von XML-Dateien erleichtert. Wenn Sie z. B. ein XML-Schema unter Verwendung der Ausschnitte "complexType Sequence-Element" und "simpleType-Element" erstellt haben, wird der folgende XML-Text in die Datei eingefügt. Entsprechend Ihren Anforderungen ändern Sie den `name`-Wert.

```xml
<xs:element name="name">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="name">
        <xs:simpleType>
          <xs:restriction base="xs:string"></xs:restriction>
        </xs:simpleType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

Es gibt zwei Möglichkeiten zum Einfügen von Ausschnitten. Mit dem Befehl **Ausschnitt einfügen** wird der XML-Ausschnitt an der Cursorposition eingefügt. Der Befehl **Umgeben mit** veranlasst, dass der XML-Ausschnitt als Wrapper für den ausgewählten Text fungiert. Beide Befehle sind entweder im Menü **Bearbeiten**, Untermenü **IntelliSense**, oder im Kontextmenü des Editors verfügbar.

Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von XML-Codeausschnitten](../xml-tools/how-to-use-xml-snippets.md).

## <a name="schema-generated-xml-snippets"></a>Schemagenerierte XML-Ausschnitte

Der XML-Editor verfügt über die Funktion, XML-Ausschnitte aus einem XML-Schema zu generieren. Mithilfe dieses Features können Sie ein Element mit XML-Elementen auffüllen, die aus den Schemainformationen für dieses Element generiert werden. Weitere Informationen finden Sie unter [Vorgehensweise: Generieren eines XML-Codeausschnitts aus einem XML-Schema](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).

## <a name="create-new-xml-snippets"></a>Erstellen neuer XML-Ausschnitte

Zusätzlich zu den standardmäßig in -Visual Studio enthaltenen Ausschnitten können Sie eigene XML-Ausschnitte erstellen und verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von XML-Codeausschnitten](../xml-tools/how-to-create-xml-snippets.md).

## <a name="see-also"></a>Siehe auch

- [Codeausschnitte in Visual Studio](../ide/code-snippets.md)
- [XML-Editor](../xml-tools/xml-editor.md)
