---
title: 'Idebugcomplussymbolprovider:: GetAssemblyName | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugComPlusSymbolProvider::GetAssemblyName
- GetAssemblyName
ms.assetid: a08cd609-b9b9-47bd-bf73-cbf851285907
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ad546e3cde5106a966ce4533ee059f0ba1e2565d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "80733974"
---
# <a name="idebugcomplussymbolprovidergetassemblyname"></a>IDebugComPlusSymbolProvider::GetAssemblyName
Ruft den Namen der Assembly ab, bei der das Modul und die Anwendungsdomäne angegeben sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetAssemblyName(
    ULONG32 ulAppDomainID,
    GUID    guidModule,
    BSTR*   pbstrName
);
```

```csharp
int GetAssemblyName(
    uint   ulAppDomainID,
    Guid   guidModule,
    string pbstrName
);
```

## <a name="parameters"></a>Parameter
`ulAppDomainID`\
in Der Bezeichner für die Anwendungsdomäne.

`guidModule`\
in Eindeutiger Bezeichner für das Modul.

`pbstrName`\
vorgenommen Gibt den Namen der Assembly zurück.

## <a name="return-value"></a>Rückgabewert
Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.

## <a name="example"></a>Beispiel
Im folgenden Beispiel wird gezeigt, wie diese Methode für ein **cdebugsymbolprovider** -Objekt implementiert wird, das die [idebugcomplussymbolprovider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) -Schnittstelle verfügbar macht.

```cpp
HRESULT CDebugSymbolProvider::GetAssemblyName(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    BSTR* pbstrName
)
{
    HRESULT hr = S_OK;
    Module_ID idModule(ulAppDomainID, guidModule);
    CComPtr<IMetaDataImport> pMetadata;

    METHOD_ENTRY( CDebugSymbolProvider::GetMetadataForModule );

    IfFalseGo( pbstrName, E_INVALIDARG );
    *pbstrName = NULL;

    IfFailGo( GetMetadata( idModule, &pMetadata ) );
    IfFailGo( GetAssemblyName( pMetadata, 0, pbstrName ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::GetMetadataForModule, hr );
    return hr;
}
```

## <a name="see-also"></a>Weitere Informationen
- [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
