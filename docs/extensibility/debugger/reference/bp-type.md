---
title: BP_TYPE | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_TYPE
helpviewer_keywords:
- BP_TYPE enumeration
ms.assetid: ef07191e-7966-43ab-96fb-1a0b1db3115d
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 02550141fb1857214d5bfd80d5dd86969bec9fba
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737790"
---
# <a name="bp_type"></a>BP_TYPE
Gibt an, ob sich der Haltepunkt an einem Code Speicherort befindet, ob es sich um einen Daten Speicherort handelt oder ob es sich um einen anderen Haltepunkt

## <a name="syntax"></a>Syntax

```cpp
enum enum_BP_TYPE {
    BPT_NONE    = 0x0000,
    BPT_CODE    = 0x0001,
    BPT_DATA    = 0x0002,
    BPT_SPECIAL = 0x0003
};
typedef DWORD BP_TYPE;
```

```csharp
public enum enum_BP_TYPE {
    BPT_NONE    = 0x0000,
    BPT_CODE    = 0x0001,
    BPT_DATA    = 0x0002,
    BPT_SPECIAL = 0x0003
};
```

## <a name="fields"></a>Felder
`BPT_NONE`\
Gibt keinen breakpointtyp an.

`BPT_CODE`\
Gibt einen Code Haltepunkt an.

`BPT_DATA`\
Gibt einen Daten Haltepunkt an.

`BPT_SPECIAL`\
Gibt einen Haltepunkt an, der weder ein Code noch ein Datentyp ist. Dieser Typ ist veraltet und sollte nicht verwendet werden.

## <a name="remarks"></a>Bemerkungen
Wird als Parameter an die [getbreakpointtype](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md) -Methode und die [getbreakpointtype](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md) -Methode übergeben.

## <a name="requirements"></a>Anforderungen
Header: msdbg. h

Namespace: Microsoft. VisualStudio. Debugger. Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Siehe auch
- [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetBreakpointType](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)
- [GetBreakpointType](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)
