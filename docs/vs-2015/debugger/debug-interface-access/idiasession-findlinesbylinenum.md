---
title: 'IDiaSession:: findLinesByLinenum | Microsoft-Dokumentation'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByLinenum method
ms.assetid: 76d5622d-9a91-4c2a-a98f-263af5d1daef
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d7ef4ab516bffbc13f47616c2f20fdd71cac38b0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "90841050"
---
# <a name="idiasessionfindlinesbylinenum"></a>IDiaSession::findLinesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bestimmt die Zeilennummern der Kompilierungen, dass die angegebene Zeilennummer in einer Quelldatei innerhalb oder in der Nähe liegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT findLinesByLinenum (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `compiland`  
 in Ein [idiasymmetribol](../../debugger/debug-interface-access/idiasymbol.md) -Objekt, das die Kompilierungen darstellt, in der nach den Zeilennummern gesucht werden soll. Dieser Parameter darf nicht `NULL` sein.  
  
 `file`  
 in Ein [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) -Objekt, das die Quelldatei darstellt, in der gesucht werden soll. Dieser Parameter darf nicht `NULL` sein.  
  
 `linenum`  
 in Gibt eine einzeilige Zeilennummer an.  
  
> [!NOTE]
> Sie können keine NULL-Werte verwenden, um alle Zeilen anzugeben (verwenden Sie die [IDiaSession:: findLines](../../debugger/debug-interface-access/idiasession-findlines.md) -Methode, um alle Zeilen zu finden).  
  
 `column`  
 in Gibt die Spaltennummer an. Verwenden Sie 0 (null), um alle Spalten anzugeben. Eine Spalte ist ein Byte Offset in eine Zeile.  
  
 `ppResult`  
 vorgenommen Gibt eine [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objta zurück, die eine Liste der abgerufenen Zeilennummern enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine Quelldatei öffnen, die von dieser Datei beigetragenen Kompilierungen auflisten und die Zeilennummern in der Quelldatei suchen, in der die einzelnen Kompilierungen kompiliert werden.  
  
```cpp#  
void ShowLinesInCompilands(IDiaSession *pSession, LPCOLESTR filename)  
{  
    IDiaEnumSourceFiles* pEnum;  
    IDiaSourceFile*      pFile;  
    DWORD                celt;  
  
    pSession->findFile ( NULL, filename, nsFNameExt, &pEnum );  
    while ( pEnum->Next ( 1, &pFile, &celt ) == S_OK ) // for each file  
    {  
        IDiaEnumSymbols* pEnumCompilands;  
        IDiaSymbol* pCompiland;  
  
        pFile->get_compilands ( &pEnumCompilands );  
        // for each compiland  
        while ( pEnumCompilands->Next ( 1, &pCompiland, &celt ) == S_OK )  
        {  
            IDiaEnumLineNumbers* pEnum;  
            // Find first compiland closest to line 1 of the file.  
            if (pSession->findLinesByLinenum( pCompiland, pFile, 1, 0, &pEnum ) == S_OK)  
            {  
                IDiaLineNumber *pLineNumber;  
                DWORD lineCount;  
                while ( pEnum->Next(1,&pLineNumber,&lineCount) == S_OK)  
                {  
                     DWORD lineNum;  
                     if (pLineNumber->get_line(&lineNum) == S_OK)  
                     {  
                          printf("compiland starts in source at line number = %lu\n",lineNum);  
                     }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession:: findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
