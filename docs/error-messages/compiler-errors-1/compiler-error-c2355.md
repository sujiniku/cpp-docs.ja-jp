---
title: コンパイラ エラー C2355 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2355
dev_langs:
- C++
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b88bf1619a003faa57d1fe1d4f03219267481d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2355"></a>コンパイラ エラー C2355
'this' : 静的でないメンバー関数の内部または静的でないデータ メンバー初期化子においてのみ参照できます  
  
 `this` ポインターは、静的でないメンバー関数の内部または静的でないデータ メンバー初期化子でのみ有効です。 このエラーは、クラス宣言外のメンバー関数の定義のクラス スコープが適切に修飾されていないときに発生することがあります。 また、クラスで宣言されていない関数で `this` ポインターが使用されたときにも発生する場合があります。  
  
 この問題を解決するには、メンバー関数の定義とメンバー関数の宣言がクラス内で一致していることと、メンバー関数が静的として宣言されていないことを確認します。 データ メンバー初期化子については、データ メンバーが静的として宣言されていないことを確認します。  
  
 次の例では、C2355 を生成し、その修正方法を示しています。  
  
```  
// C2355.cpp  
// compile with: /c  
class MyClass {};  
MyClass *p = this;   // C2355  
  
// OK  
class MyClass2 {  
public:  
   void Test() {  
      MyClass2 *p = this;  
   }  
};  
```