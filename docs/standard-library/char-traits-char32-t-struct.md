---
title: "char_traits&lt;char32_t&gt; 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char_32t>"
  - "char_traits<char32_t>"
  - "std.char_traits<char_32t>"
  - "std::char_traits<char_32t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char32_t> クラス"
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# char_traits&lt;char32_t&gt; 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型 `char32_t`要素にテンプレートの構造体 **char\_traits\<CharType\>** の特殊化にする構造体。  
  
## 構文  
  
```  
template<> struct char_traits<char32_t>;  
```  
  
## 解説  
 クラスまたは構造体がこの `char32_t`型のオブジェクトを操作するライブラリ関数の利用できるようになります。  
  
## 必要条件  
 **ヘッダー:** の \<文字列\>  
  
 **名前空間:** std  
  
## 参照  
 [\<string\>](../standard-library/string.md)   
 [char\_traits 構造体](../standard-library/char-traits-struct.md)