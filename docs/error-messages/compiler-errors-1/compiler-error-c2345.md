---
title: "コンパイラ エラー C2345 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2345"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2345"
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2345
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

align\(value\): 無効なアラインメント値です  
  
 [align](../../cpp/align-cpp.md) キーワードに渡した値が有効範囲外の値です。  
  
 次のコードでは C2345 が生成されます  
  
```  
// C2345.cpp // compile with: /c __declspec(align(0)) int a;   // C2345 __declspec(align(1)) int a;   // OK  
```