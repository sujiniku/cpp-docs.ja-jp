---
title: "コンパイラ エラー C3623 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3623
dev_langs:
- C++
helpviewer_keywords:
- C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
caps.latest.revision: 11
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
ms.openlocfilehash: e76c363b805df93a04309a215d092e4bb56717b9
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3623"></a>コンパイラ エラー C3623
'variable': ビット フィールドは、マネージ型または WinRT 型ではサポートされていません。  
  
 マネージ クラスまたは WinRT クラスの変数に対して、ビット フィールドは使用できません。  
  
 次の例では C3623 が生成されます。  
  
```  
// C3623.cpp  
// compile with: /clr  
using namespace System;  
ref class CMyClass {  
public:  
   int i : 1;   // C3623  
};  
  
int main() {  
   CMyClass^ pMyClass = gcnew CMyClass();  
   pMyClass->i = 3;  
   Console::Out->WriteLine(pMyClass->i);  
}  
```  
