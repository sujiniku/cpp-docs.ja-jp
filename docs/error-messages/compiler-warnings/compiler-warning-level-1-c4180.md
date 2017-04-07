---
title: "コンパイラの警告 (レベル 1) C4180 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4180"
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数型へ適用された修飾子は無効なため、無視されます。  
  
 **const** などの修飾子が、`typedef` で定義された関数型に適用されています。  
  
## 使用例  
  
```  
// C4180.cpp // compile with: /W1 /c typedef int FuncType(void); // the const qualifier cannot be applied to the // function type FuncType const FuncType f;   // C4180  
```