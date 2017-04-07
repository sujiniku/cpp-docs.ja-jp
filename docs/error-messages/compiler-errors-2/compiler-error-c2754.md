---
title: "コンパイラ エラー C2754 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2754"
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specialization' : 部分的特殊化は、依存非型テンプレート パラメーターを含むことができません。  
  
 非型テンプレート パラメーターに依存するテンプレート クラスの部分的な特化が試行されました。  これは認められていません。  
  
 次の例では警告 C2754 が生成されます。  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```