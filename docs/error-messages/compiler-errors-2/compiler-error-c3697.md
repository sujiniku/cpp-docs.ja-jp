---
title: "コンパイラ エラー C3697 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3697"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3697"
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3697
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'修飾子' : この修飾子を '^' で使用できません  
  
 トラッキング ハンドル \(^\) が、意図していない修飾子に適用されました。  
  
 次の例では警告 C3697 が生成されます。  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```