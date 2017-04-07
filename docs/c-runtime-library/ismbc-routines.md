---
title: "_ismbc 系ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbc ルーチン"
  - "ismbc ルーチン"
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _ismbc 系ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらの各 **\_ismbc** ルーチンは、特定の条件で特定のマルチバイト文字 `c` をテストします。  
  
|||  
|-|-|  
|[\_ismbcalnum、\_ismbcalnum\_l、\_ismbcalpha、\_ismbcalpha\_l、\_ismbcdigit、\_ismbcdigit\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|[\_ismbcl0、\_ismbcl0\_l、\_ismbcl1、\_ismbcl1\_l、\_ismbcl2、\_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|  
|[\_ismbcgraph、\_ismbcgraph\_l、\_ismbcprint、\_ismbcprint\_l、\_ismbcpunct、\_ismbcpunct\_l、\_ismbcblank、\_ismbcblank\_l、\_ismbcspace、\_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[\_ismbclegal、\_ismbclegal\_l、\_ismbcsymbol、\_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|  
|[\_ismbchira、\_ismbchira\_l、\_ismbckata、\_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[\_ismbclower、\_ismbclower\_l、\_ismbcupper、\_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|  
  
## 解説  
 各 **\_ismbc** ルーチンのテスト結果は、有効なマルチバイト コード ページによって異なります。  マルチバイトのコード ページには、1 バイトの英字があります。  既定では、マルチバイト コード ページは、プログラムの開始時にオペレーティング システムから取得したシステム既定の ANSI コード ページに設定されます。  [\_getmbcp](../c-runtime-library/reference/getmbcp.md)、または [\_setmbcp](../c-runtime-library/reference/setmbcp.md) によって、使用中のマルチバイト コード ページをそれぞれ照会または変更できます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  **\_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**\_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  
  
|ルーチン|テスト条件|コード ページ 932 の例|  
|----------|-----------|--------------------|  
|[\_ismbcalnum、\_ismbcalnum\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|英数字|`c` が ASCII の英字の 1 バイト表現である場合に限り、0 以外の値を返します。`_ismbcdigit` と `_ismbcalpha` の例を参照してください。|  
|[\_ismbcalpha、\_ismbcalpha\_](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|alphabetic|`c` が ASCII の英字 \(`_ismbcupper` と `_ismbclower` の例を参照\) またはカタカナ \(0xA6\<\=`c`\<\=0xDF\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|[\_ismbcdigit、\_ismbcdigit\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|数字|`c` が ASCII 数字 \(0x30 \<\= `c`\<\= 0x39\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|[\_ismbcgraph、\_ismbcgraph\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|グラフィック|`c` が空白 \( \) を除く ASCII またはカタカナの印刷可能な文字の 1 バイト表現である場合に限り、0 以外の値を返します。  「`_ismbcdigit`」、「`_ismbcalpha`」、および「`_ismbcpunct`」の例を参照してください。|  
|[\_ismbclegal、\_ismbclegal\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|有効なマルチバイト文字|`c` の最初のバイトが範囲 0x81 ～ 0x9F か 0xE0 ～ 0xFC 内にあり、2 番目のバイトが範囲 0x40 ～ 0x7E か 0x80 ～ FC 内にある場合に限り、0 以外の値を返します。|  
|[\_ismbclower、\_ismbclower\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|小文字の英字|`c` が ASCII 小文字の英字 \(0x61 \<\= `c`\<\= 0x7A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|[\_ismbcprint、\_ismbcprint\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|印刷可能|`c` が空白 \( \) を含む ASCII またはカタカナの印刷可能な文字のバイト表現である場合に限り、0 以外の値を返します。`_ismbcspace`、`_ismbcdigit`、`_ismbcalpha` と `_ismbcpunct` の例を参照してください。|  
|[\_ismbcpunct、\_ismbcpunct\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|区切り記号|`c` が ASCII またはカタカナの区切り記号の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|[\_ismbcblank、\_ismbcblank\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|空白または水平タブ|`c` が空白文字または水平タブ文字のバイト表現である場合 \(`c`\=0x20 または `c`\=0x09\) に限り、0 以外の値を返します。|  
|[\_ismbcspace、\_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Whitespace|`c` が空白文字の場合 \(`c`\=0x20 または 0x09\<\=`c`\<\=0x0D\)、0 以外の値を返します。|  
|[\_ismbcsymbol、\_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|マルチバイトの記号|0x8141\<\=`c`\<\=0x81AC の場合にのみ、0 以外の値を返します。|  
|[\_ismbcupper、\_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|大文字の英字|`c` が ASCII 大文字の英字 \(0x41 \<\= `c`\<\= 00x5A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
  
 **コード ページ 932 固有情報**  
  
 次のルーチンは、コード ページ 932 に固有です。  
  
|ルーチン|テスト条件 \(コード ページ 932 のみ\)|  
|----------|------------------------------|  
|[\_ismbchira、\_ismbchira\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|2 バイトひらがな: 0x829F \<\= `c`\<\= 0x82F1。|  
|[\_ismbckata、\_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|2 バイト カタカナ: 0x8340 \=\<`c`\<\= 0x8396。|  
|[\_ismbcl0、\_ismbcl0\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS の非漢字: 0x8140\=\<`c`\<\=0x889E。|  
|[\_ismbcl1、\_ismbcl1\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS のレベル 1: 0x889F\=\<`c`\<\=0x9872。|  
|[\_ismbcl2、\_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS のレベル 2: 0x989F\=\<`c`\<\=0xEA9E。|  
  
 `_ismbcl0`、`_ismbcl1`、および `_ismbcl2` は、指定された値 `c` が、上の表に記載のテスト条件に一致するかどうかをチェックしますが、`c` が有効なマルチバイト文字かどうかはチェックしません。  下位バイトが範囲 0x00 – 0x3F、0x7F、または 0xFD – 0xFF にある場合、これらの関数は 0 以外の値を返し、文字がテスト条件を満たすことを示します。  マルチバイト文字が定義されているかどうかをテストするために [\_ismbbtrail、\_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) を使用します。  
  
 **コード ページ 932 固有情報終了**  
  
## 参照  
 [文字分類](../c-runtime-library/character-classification.md)   
 [is、isw 系ルーチン](../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 系ルーチン](../c-runtime-library/ismbb-routines.md)