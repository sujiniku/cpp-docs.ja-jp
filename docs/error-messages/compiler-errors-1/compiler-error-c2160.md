---
title: "コンパイラ エラー C2160 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2160"
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マクロ定義がトークン連結演算子 \(\#\#\) で始まっています。  
  
 マクロ定義がトークン連結演算子 \(\#\#\) で始まっています。  
  
 次の例では C2160 が生成されます。  
  
```  
// C2160.cpp // compile with: /c #define mac(a,b) #a   // OK #define mac(a,b) ##a   // C2160  
```