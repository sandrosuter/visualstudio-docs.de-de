---
title: 'Idiasymmetribol:: findChildren-exbyva | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByVA
ms.assetid: 29080009-36e4-4697-acd7-50f2e3e1bf1b
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6798f3a1dfd8979db926960a6155c5b07e255f21
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "68149969"
---
# <a name="idiasymbolfindchildrenexbyva"></a>IDiaSymbol::findChildrenExByVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ruft die untergeordneten Elemente des Symbols ab, die bei einer angegebenen virtuellen Adresse gültig sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT findChildrenExByVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `symtag`  
 in Gibt die Symbol Tags der untergeordneten Elemente an, die abgerufen werden sollen, wie in der [SymTagEnum-Enumeration](../../debugger/debug-interface-access/symtagenum.md)definiert. Legen Sie auf fest, `SymTagNull` damit alle untergeordneten Elemente abgerufen werden.  
  
 `name`  
 in Gibt den Namen der untergeordneten Elemente an, die abgerufen werden sollen. Legen Sie auf fest, `NULL` damit alle untergeordneten Elemente abgerufen werden.  
  
 `compareFlags`  
 in Gibt die Vergleichs Optionen an, die auf die namens Übereinstimmung angewendet werden. Werte aus der Enumeration-Enumeration von [NameSearchOptions](../../debugger/debug-interface-access/namesearchoptions.md) können allein oder in Kombination verwendet werden.  
  
 `address`  
 in Gibt die virtuelle Adresse an.  
  
 `ppResult`  
 vorgenommen Gibt ein [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) -Objekt zurück, das eine Liste der abgerufenen untergeordneten Symbole enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt zurück, wenn mindestens ein untergeordnetes Element `S_OK` des Symbols gefunden wurde, oder gibt zurück, wenn keine untergeordneten Elemente `S_FALSE` gefunden wurden; andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Bemerkungen  
 Zu den lokalen Symbolen, die zurückgegeben werden, gehören Informationen zum Live Bereich.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Dia2.h  
  
 Bibliothek: diaguids. lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>Weitere Informationen  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum-Enumeration](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession:: findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions-Enumeration](../../debugger/debug-interface-access/namesearchoptions.md)
