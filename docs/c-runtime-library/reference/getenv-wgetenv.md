---
title: "getenv、_wgetenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getenv"
  - "_wgetenv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wgetenv"
  - "getenv"
  - "_tgetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tgetenv 関数"
  - "_wgetenv 関数"
  - "環境値"
  - "環境変数"
  - "getenv 関数"
  - "tgetenv 関数"
  - "wgetenv 関数"
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# getenv、_wgetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の環境から値を取得します。  これらの関数のセキュリティを強化したバージョンについては、「[getenv\_s、\_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *getenv(   
   const char *varname   
);  
wchar_t *_wgetenv(   
   const wchar_t *varname   
);  
```  
  
#### パラメーター  
 `varname`  
 環境変数名。  
  
## 戻り値  
 `varname` を含む環境のテーブル エントリへのポインターを返します。  返されたポインターを使用して環境変数の値を変更することは安全ではありません。  環境変数の値を変更するには、`_putenv` 関数を使用します。  戻り値は `varname` が環境のテーブルにない場合は `NULL` です。  
  
## 解説  
 `getenv` 関数は、環境変数のリストから `varname` を検索します。  Windows オペレーティング システムでは、`getenv` 関数は大文字と小文字を区別しません。  `getenv` 関数と `_putenv` 関数は、`_environ` グローバル変数が指す環境のコピーを使用して環境にアクセスします。  `getenv` は、ランタイム ライブラリからアクセスできるデータ構造体だけを対象とし、プロセス用にオペレーティング システムで作成された環境 "セグメント" は参照しません。  そのため、[main](../Topic/main:%20Program%20Startup.md) または [wmain](../Topic/main:%20Program%20Startup.md) の引数 `envp` を使用するプログラムは、無効な情報を取得する可能性があります。  
  
 `varname` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数によって無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
 ワイド文字を扱う場合は、`getenv` ではなく `_wgetenv` を使用します。`_wgetenv` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  `_wenviron` グローバル変数は `_environ` と同じですが、ワイド文字を扱えるという点で異なっています。  
  
 SBCS ASCII プログラムなどの MBCS プログラムでは、環境がマルチバイト文字列で構成されているため、`_wenviron` の初期値は `NULL` です。  その後、`_wputenv` を最初に呼び出すとき、または \(MBCS\) 環境が既に存在する場合に `_wgetenv` を最初に呼び出すとき、対応するワイド文字列環境が作成され、その後は作成されたワイド文字列環境が `_wenviron` によって参照されます。  
  
 同様に、Unicode \(`_wmain`\) プログラムでは、環境がワイド文字列で構成されているため、`_environ` の初期値は `NULL` です。  その後、`_putenv` を最初に呼び出すとき、または \(Unicode\) 環境が既に存在する場合に `getenv` を最初に呼び出すときは、対応する MBCS 環境が作成され、その後は作成された MBCS 環境が `_environ` によって参照されます。  
  
 2 つの環境のコピー \(MBCS および Unicode\) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。  たとえば、`_putenv` を呼び出す場合は、2 つの環境文字列が対応するように `_wputenv` も自動的に呼び出されます。  
  
> [!CAUTION]
>  まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。  これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないためです。  詳細については、「[\_environ、\_wenviron](../../c-runtime-library/environ-wenviron.md)」を参照してください。  
  
> [!NOTE]
>  `_putenv` 系関数と `_getenv` 系関数はスレッド セーフではありません。  `_putenv` が文字列を変更している間に `_getenv` が文字列ポインターを返すことがあり、これはランダム エラーの原因になります。  これらの関数の呼び出しが同期されていることを確認する必要があります。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tgetenv`|`getenv`|`getenv`|`_wgetenv`|  
  
 `TZ` 環境変数の値を確認または変更するには、必要に応じて、`getenv`、`_putenv`、および `_tzset` を使用します。  `TZ` の詳細については、「[\_tzset](../Topic/_tzset.md)」および「[\_daylight、timezone、および \_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`getenv`|\<stdlib.h\>|  
|`_wgetenv`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_getenv.c  
// compile with: /W3  
// This program uses getenv to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *libvar;  
  
   // Get the value of the LIB environment variable.  
   libvar = getenv( "LIB" ); // C4996  
   // Note: getenv is deprecated; consider using getenv_s instead  
  
   if( libvar != NULL )  
      printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects the environment  
   // variable of the current process. The command processor's  
   // environment is not changed.  
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996  
   // Note: _putenv is deprecated; consider using putenv_s instead  
  
   // Get new value.  
   libvar = getenv( "LIB" ); // C4996  
  
   if( libvar != NULL )  
      printf( "New LIB variable is: %s\n", libvar );  
}  
```  
  
  **元の LIB 変数: C:\\progra~1\\devstu~1\\vc\\lib**  
**新しい LIB 変数: c:\\mylib;c:\\yourlib**   
## 同等の .NET Framework 関数  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [\_putenv、\_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [環境定数](../../c-runtime-library/environmental-constants.md)