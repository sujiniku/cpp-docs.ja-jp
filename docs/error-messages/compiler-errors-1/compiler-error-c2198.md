---
title: "コンパイラ エラー C2198 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2198"
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 呼び出しに対する引数が少なすぎます。  
  
 コンパイラで検出された関数を呼び出すためのパラメーターが少なすぎるか、または関数宣言が正しくありません。  
  
 次の例では C2198 が生成されます。  
  
```  
// C2198.c // compile with: /c void func( int, int ); int main() { func( 1 );   // C2198 only one actual parameter func( 1, 1 );   // OK }  
```