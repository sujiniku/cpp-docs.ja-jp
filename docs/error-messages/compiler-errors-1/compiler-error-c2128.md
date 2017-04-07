---
title: "コンパイラ エラー C2128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c2128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2128"
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : alloc\_text\/same\_seg は C リンケージが指定された関数のみ有効です。  
  
 `pragma` `alloc_text`  を使用できるのは、C リンケージを持つように宣言された関数だけです。  
  
 次の例では警告 C2128 が生成されます。  
  
```  
// C2128.cpp  
// compile with: /c  
  
// Delete the following line to resolve.  
void func();  
// #pragma alloc_text("my segment", func)   // C2128  
  
extern "C" {  
void func();  
}  
  
#pragma alloc_text("my segment", func)  
void func() {}  
```