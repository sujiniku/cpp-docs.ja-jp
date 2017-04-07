---
title: "コンパイラ エラー C2589 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6470a86eec00f0e1913e9947f2767af3d9e85298
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2589"></a>コンパイラ エラー C2589
'identifier': の右側に無効なトークン ':: '  
  
 クラス、構造体または共用体の名前が、スコープ解決演算子 (2 つのコロン) の左側に表示された場合、右側のトークンがありますクラス、構造体または共用体のメンバー。 それ以外の場合、任意のグローバル識別子は、右側に表示できます。  
  
 スコープ解決演算子はオーバー ロードすることはできません。  
  
 次の例では、c2589 エラーが生成されます。  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```