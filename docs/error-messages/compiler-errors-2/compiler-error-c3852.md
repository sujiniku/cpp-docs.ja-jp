---
title: コンパイラ エラー C3852 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3852
dev_langs:
- C++
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 439e6518c1e1f94918671f2e710ccf1a86621f16
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3852"></a>コンパイラ エラー C3852
'member' は型 'type' を持つ: 集約の初期化では、このメンバーは初期化できませんでした。  
  
 集約の初期化で、既定の初期化を受け取ることができないデータ メンバーに集約の初期化の一部として、既定の初期化を代入しようとしました。  
  
 次の例では、C3852 を生成します。  
  
```  
// C3852.cpp  
struct S  
{  
   short s;  
};  
  
struct S1  
{  
   int i;  
   const S s;  
};  
  
struct S2  
{  
   int i;  
   char & rc;  
};  
  
int main()  
{  
   S1 s1 = { 1 };   // C3852 const member   
   // try the following line instead  
   // S1 s1 = { 1, 2 };  
  
   S2 s2 = { 2 };   // C3852 reference member  
   // try the following line instead  
   // char c = 'a';  
   S2 s2 = { 2, c };  
}  
```