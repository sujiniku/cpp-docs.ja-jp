---
title: マルチバイト文字とワイド文字 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc259a75ab12352a7d0029241496aea22803152a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="multibyte-and-wide-characters"></a>マルチバイト文字とワイド文字
マルチバイト文字は 1 つ以上のバイトのシーケンスで構成される文字です。 各バイト シーケンスは、拡張文字セットの 1 つの文字を表します。 マルチバイト文字は、漢字などの文字セットで使用されます。  
  
 ワイド文字は、常に 16 ビットの多言語文字コードです。 文字定数の型は `char` です。ワイド文字の場合、型は `wchar_t` です。 ワイド文字は常に固定サイズであるため、ワイド文字を使用すると、各種言語の文字セットを使ったプログラミングが簡単になります。  
  
 ワイド文字の文字列リテラル `L"hello"` は型 `wchar_t` の 6 つの整数の配列になります。  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Unicode 仕様はワイド文字の仕様です。 マルチバイト文字とワイド文字の相互変換用のランタイム ライブラリ ルーチンには、`mbstowcs`、`mbtowc`、`wcstombs`、および `wctomb` があります。  
  
## <a name="see-also"></a>参照  
 [C の識別子](../c-language/c-identifiers.md)