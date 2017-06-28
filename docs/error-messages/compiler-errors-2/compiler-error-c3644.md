---
title: "コンパイラ エラー C3644 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3644
dev_langs:
- C++
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c5609ca4dc3bd5868618f7903a99e229582aa7f1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3644"></a>コンパイラ エラー C3644
'function': マネージ コードを生成する関数をコンパイルできません。  
  
 関数内のいくつかのキーワードの存在をネイティブにコンパイルする関数となります。  
  
 次の例では、c3644 エラーが生成されます。  
  
```  
// C3644.cpp  
// compile with: /clr  
// processor: x86  
  
void __clrcall Func2(int i) {  
   __asm {}   // C3644  
}  
```