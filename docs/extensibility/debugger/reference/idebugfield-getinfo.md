---
title: 'Idebugfield:: GetInfo | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1b3251db3426f87901ca0768800feaa36fef5373
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80728847"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
Diese Methode ruft Anzeigeinformationen über das Feld ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetInfo( 
   FIELD_INFO_FIELDS dwFields,
   FIELD_INFO* pFieldInfo
);
```

```csharp
int GetInfo(
   enum_FIELD_INFO_FIELDS dwFields,
   FIELD_INFO[] pFieldInfo
);
```

## <a name="parameters"></a>Parameter
`dwFields`\
in Eine Kombination aus [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) Konstanten, die die anzuzeigenden Informationen auswählt. Wenn das Feld ein Symbol darstellt, ist dies in der Regel der Symbol Name und-Typ.

`pFieldInfo`\
vorgenommen Gibt die Informationen in der bereitgestellten [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) -Struktur zurück.

## <a name="return-value"></a>Rückgabewert
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.

## <a name="see-also"></a>Weitere Informationen
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)
