---
title: 'Vorgehensweise: Ändern des Pivotpunkts eines 3D-Modells'
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c9f79f8f5a39a8721e433207f2fbb17fd85a1150
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "85768832"
---
# <a name="how-to-modify-the-pivot-point-of-a-3d-model"></a>Vorgehensweise: Ändern des Pivotpunkts eines 3D-Modells

In diesem Artikel wird erläutert, wie der Modell-Editor zum Ändern des *Pivotpunkts* eines 3D-Modells verwendet wird. Der Pivotpunkt ist der Punkt im Raum, der das mathematische Zentrum des Objektes für Rotation und Skalierung definiert.

## <a name="modify-the-pivot-point-of-a-3d-model"></a>Ändern des Pivotpunkts eines 3D-Modells

Sie können den Ursprung eines 3D-Modells durch Ändern seines Pivotpunkts neu definieren.

Stellen Sie sicher, dass das Fenster **Eigenschaften** und die **Toolbox** angezeigt werden.

1. Beginnen Sie mit einem vorhandenen 3D-Modell wie dem, das unter [Vorgehensweise: Erstellen eines einfachen 3D-Modells](../designers/how-to-create-a-basic-3-d-model.md) beschrieben wird.

2. Gehen Sie in den Pivot-Modus. Klicken Sie zum Aktivieren des Pivot-Modus auf der Symbolleiste **Model-Editor-Modus** auf **Pivot-Modus**. Es erscheint ein Feld um die Schaltfläche **Pivot-Modus**, der angibt, dass der Modell-Editor sich nun im Pivot-Modus befindet. Vorgänge wie die Verschiebung beeinflussen im Pivot-Modus den Pivotpunkt des Objektes anstatt der Struktur des Objektes im Raum.

3. Ändern Sie den Pivotpunkt des Objekts. Klicken Sie im Modus **Auswählen** auf das Objekt und anschließend auf der Symbolleiste des **Modell-Viewers** auf das Tool **Verschieben**. Ein Feld, das den Pivotpunkt darstellt, wird auf der Entwurfsoberfläche angezeigt. Verschieben Sie das Feld, um den Pivotpunkt des Objekts zu ändern.

     Durch das Verschieben des Felds können Sie den Pivopunkt in alle drei Dimensionen verschieben. Zum Verschieben des Pivotpunkts entlang einer Achse, verschieben Sie den Pfeil, der dieser Ache entspricht Das Feld und die Pfeile wechseln in eine gelbe Farbe, um die Achse anzugeben, die von der Verschiebung betroffen sind.

     Sie können auch den Pivotpunkt angeben, indem Sie die Eigenschaft **Pivot-Bewegung** im Fenster **Eigenschaften** verwenden.

    > [!TIP]
    > Sie können den Effekt des neuen Pivotpunkts durch Rotieren des Objekts betrachten. Verwenden Sie zum Drehen des Objekts das Tool **Drehen**, oder ändern Sie die Eigenschaft **Drehung**.

Hier finden Sie ein Modell, dass einen geänderten Pivotpunkt hat:

![Modell eines Hauses mit einem geänderten Pivotpunkt](../designers/media/digit-modified-model.png)

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Erstellen eines einfachen 3D-Modells](../designers/how-to-create-a-basic-3-d-model.md)
- [Modell-Editor](../designers/model-editor.md)
