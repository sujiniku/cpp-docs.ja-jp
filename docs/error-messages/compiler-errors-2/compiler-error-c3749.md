---
title: "コンパイラ エラー C3749 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 20072ae0bdb55a6ee9cbac9d1ce0269991b839af
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3749"></a>コンパイラ エラー C3749
'attribute': 関数内で、カスタム属性を使用しない場合があります  
  
 カスタム属性は、関数内で使用できません。 カスタム属性の詳細については、トピックを参照してください。[属性](../../windows/attribute.md)します。  
  
## <a name="example"></a>例  
 次の例では、c3749 エラーが生成されます。  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
