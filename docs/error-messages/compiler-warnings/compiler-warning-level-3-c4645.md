---
title: "コンパイラの警告 (レベル 3) C4645 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 3) C4645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(noreturn\) で宣言された関数に return ステートメントがあります。  
  
 [noreturn](../../cpp/noreturn.md) `__declspec`修飾子でマークされている関数内に [return](../Topic/return%20Statement%20in%20Program%20Termination%20\(C++\).md) ステートメントが見つかりました。`return` ステートメントは無視されました。  
  
 次の例では C4645 が生成されます。  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```