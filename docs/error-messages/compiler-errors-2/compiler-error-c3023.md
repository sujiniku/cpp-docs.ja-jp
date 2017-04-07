---
title: "コンパイラ エラー C3023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3023"
ms.assetid: 89dcce98-3cd7-4931-a50f-87df1d2ebc9b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'value' : OpenMP 'clause' 句への引数での予期しないトークンです  
  
 句に渡された値が無効でした。  
  
 次の例では C3023 が生成されます。  
  
```  
// C3023.cpp // compile with: /openmp /link vcomps.lib #include <stdio.h> #include "omp.h" int main() { int i; #pragma omp parallel for schedule(dynamic 10)   // C3023 for (i = 0; i < 10; ++i) ; #pragma omp parallel for schedule(dynamic;10)   // C3023 for (i = 0; i < 10; ++i) ; // OK #pragma omp parallel for schedule(dynamic, 10) for (i = 0; i < 10; ++i) ; }  
```