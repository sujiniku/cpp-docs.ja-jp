---
title: コンパイラ エラー C2777 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2777
dev_langs:
- C++
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc3eebe5d3fe12bf102adff0cc77b6647fcf2059
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2777"></a>コンパイラ エラー C2777
プロパティごとに 1 つだけの 'put' メソッドを指定できます。  
  
 A[プロパティ](../../cpp/property-cpp.md)declspec 修飾子では、1 つ以上必要がある`put`プロパティです。  
  
 次の例では、C2777 が生成されます。  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```