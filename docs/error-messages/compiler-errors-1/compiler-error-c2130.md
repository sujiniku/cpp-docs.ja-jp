---
title: "コンパイラ エラー C2130 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2130"
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line ディレクティブの行番号の後に続くオプションのトークンが、文字列ではありません。'token' が見つかりました  
  
 オプションのファイル名トークンの後に続く [\#line](../Topic/%23line%20Directive%20\(C-C++\).md) `linenumber` は文字列である必要があります。  
  
 次の例では C2130 が生成されます。  
  
```  
// C2130.cpp int main() { #line 1000 test   // C2130 #line 1000 "test"   // OK }  
```