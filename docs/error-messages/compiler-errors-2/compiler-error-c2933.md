---
title: "コンパイラ エラー C2933 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2933"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2933"
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2933
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id が 'identifier' の typedef メンバーとして再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスを `typedef` メンバーとして使用することはできません。  
  
 次の例では C2933 が生成されます。  
  
```  
// C2933.cpp // compile with: /c template<class T> struct TC { }; struct MyStruct { typedef int TC<int>;   // C2933 }; struct TC2 { }; struct MyStruct2 { typedef int TC2; };  
```  
  
 C2933 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2933b.cpp // compile with: /clr /c generic<class T> ref struct GC { }; struct MyStruct { typedef int GC<int>;   // C2933 }; ref struct GC2 { }; struct MyStruct2 { typedef int GC2; };  
```