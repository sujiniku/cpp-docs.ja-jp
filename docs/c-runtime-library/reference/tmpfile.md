---
title: tmpfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 05edefa97701ebd70d86ff4fc78dc6cee7f083fa
ms.lasthandoff: 02/24/2017

---
# <a name="tmpfile"></a>tmpfile
一時ファイルを作成します。 セキュリティが強化されたバージョンが提供されたため、この関数は廃止されました。「[tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`tmpfile` はストリーム ポインターを返します。 それ以外の場合は、`NULL` ポインターを返します。  
  
## <a name="remarks"></a>コメント  
 `tmpfile` 関数は一時ファイルを作成し、そのストリームへのポインターを返します。 一時ファイルはルート ディレクトリに作成されます。 ルート ディレクトリ以外のディレクトリに一時ファイルを作成するには、[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) または [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](../../c-runtime-library/reference/fopen-wfopen.md) と共に使用します。  
  
 ファイルを開くことができない場合、`tmpfile` は `NULL` ポインターを返します。 この一時ファイルは、ファイルが閉じられたとき、プログラムが正常に終了したとき、または `_rmtmp` が呼び出されたときに、自動的に削除されます。これは、現在の作業ディレクトリが変更されていないことを前提とします。 一時ファイルは `w+b` (バイナリ読み書き両用) モードで開かれます。  
  
 `tmpfile` で TMP_MAX (STDIO.H を参照) よりも多く呼び出しを試行した場合は、エラーが発生することがあります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
> [!NOTE]
>  この例では、Windows Vista を管理者権限で実行する必要があります。  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)