---
title: "ロケール名、言語、および国/地域識別文字列 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
caps.latest.revision: 13
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 6f90a6a39d2f9a729d07d25e9f80d1ea9e26e1ee
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="locale-names-languages-and-countryregion-strings"></a>ロケール名、言語、および国/地域識別文字列
`locale` 関数、および `setlocale` 関数の `_create_locale` 引数は、Windows NLS API でサポートされているロケール名、言語、国/地域コード、およびコード ページを使用して設定できます。 `locale` 引数は次の形式になります。  
  
```  
locale :: "locale_name"  
        | "language[_country_region[.code_page]]"  
        | ".code_page"  
        | "C"  
        | ""  
        | NULL  
```  
  
 たとえば、英語 (米国) の `en-US` 、またはボスニア語 (キリル、ボスニア - ヘルツェゴビナ) の `bs-Cyrl-BA` などロケール名形式が推奨されます。 ロケール名のセットは「 [ロケール名](http://msdn.microsoft.com/library/windows/desktop/dd373814.aspx)」に記述されています。 Windows オペレーティング システムのバージョンによってサポートされているロケール名の一覧については、「 **各国語サポートの (NLS) の API リファレンス** 」の [Culture Name](http://msdn.microsoft.com/goglobal/bb896001.aspx)の列を参照してください。 このリソースは、ロケール名のサポートされている言語、スクリプト、および地域の部分を示しています。 既定以外の並べ替え順序を持つ、サポートされているロケール名については、「 **並べ替え順序の識別子** 」の [Locale name](http://msdn.microsoft.com/library/windows/desktop/dd374060.aspx)の列を参照してください。  
  
 ロケールを作成するために、言語識別文字列、または言語識別文字列と国/地域識別文字列が使用される場合、*言語*[_*国_地域*[.*コード_ページ*]] 形式がカテゴリのロケール設定に格納されます。 サポートされる言語識別文字列のセットは「[言語識別文字列](../c-runtime-library/language-strings.md)」、サポートされるすべての国/地域識別文字列のリストは「[国/地域識別文字列](../c-runtime-library/country-region-strings.md)」に記述されています。 指定された言語が、指定された国または地域と関連付けられていない場合、指定された国または地域の既定の言語は、ロケール設定に格納されます。 この形式は、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列にはお勧めしません。これらの文字列は、ロケール名形式よりも、オペレーティング システムの更新によって変更される可能性が高いからです。  
  
 コード ページは、ロケールに関連付けられた ANSI/OEM コード ページです。 コード ページは、言語または言語と国/地域のみによってロケールを指定すると決定されます。 特殊な値 `.ACP` は国/地域の ANSI コード ページを指定します。 特殊な値 `.OCP` は国/地域の OEM コード ページを指定します。 たとえば、ロケールとして `"Greek_Greece.ACP"` を指定すると、ロケールは `Greek_Greece.1253` (ギリシャ語の ANSI コード ページ) として格納されます。また、ロケールとして `"Greek_Greece.OCP"` を指定すると、 `Greek_Greece.737` (ギリシャ語の OEM のコード ページ) として格納されます。 コード ページの詳細については、「[コード ページ](../c-runtime-library/code-pages.md)」を参照してください。 Windows でサポートされているコード ページの一覧については、「 [コード ページの識別子](http://msdn.microsoft.com/library/windows/desktop/dd317756.aspx)」を参照してください。  
  
 ロケールを指定するためにコード ページだけを使用する場合、システムの既定の言語と国または地域が使用されます。 たとえば、英語 (米国) に構成されたシステムのロケールとして `".1254"` (ANSI トルコ語) を指定した場合は、格納されているロケールは `English_United States.1254`です。 この形式はお勧めしません。これにより一貫性のない動作が実行される可能性があるためです。  
  
 `locale` 値 `C` は、C 翻訳のための ANSI に準拠した最小環境を指定します。 `C` ロケールは、任意の `char` データ型が 1 バイトであり、値は常に 256 未満であると推定します。 `locale` が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。  
  
 `setlocale` 関数と `_wsetlocale` 関数に `LC_ALL` カテゴリを使用して、ロケールのカテゴリのすべてを同時に指定できます。 カテゴリはすべて同じロケールに設定できますが、次の形式を持つロケール引数を使用して各カテゴリを個別に設定できます。  
  
```  
LC_ALL_specifier :: locale  
        | [LC_COLLATE=locale][;LC_CTYPE=locale][;LC_MONETARY=locale][;LC_NUMERIC=locale][;LC_TIME=locale]  
  
```  
  
 セミコロンで区切って複数のカテゴリの種類を指定できます。 指定されていないカテゴリの種類は、現在のロケール設定を使用します。 たとえば、次のコードは、すべてのカテゴリの現在のロケールを `de-DE`に設定し、カテゴリ `LC_MONETARY` を `en-GB` に、カテゴリ `LC_TIME` を `es-ES`に設定します。  
  
 `_wsetlocale(LC_ALL, L"de-DE");`  
  
 `_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");`  
  
## <a name="see-also"></a>関連項目  
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)   
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [言語識別文字列](../c-runtime-library/language-strings.md)   
 [国/地域別文字列](../c-runtime-library/country-region-strings.md)