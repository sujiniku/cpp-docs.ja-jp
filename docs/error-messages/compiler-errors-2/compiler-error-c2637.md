---
title: "コンパイラ エラー C2637 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2637
dev_langs:
- C++
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: 8
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
ms.openlocfilehash: 44377a49d9c29f6f00c6fc850595b8000c25c0a3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2637"></a>コンパイラ エラー C2637
'identifier': データ メンバーへのポインターを変更することはできません  
  
 データ メンバーへのポインターは、呼び出し規約を持つことはできません。 を解決するのには、呼び出し規約を削除するか、メンバー関数へのポインターを宣言します。  
  
 次の例では、c2637 エラーが生成されます。  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```