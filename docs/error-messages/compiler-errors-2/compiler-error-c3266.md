---
title: "コンパイラ エラー C3266 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3266
dev_langs:
- C++
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 3144021b946165e367a1981e8bf123c8f7514a45
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3266"></a>コンパイラ エラー C3266
'class' : クラス コンストラクターは 'void' パラメーター リストを必要とします  
  
/clr プログラミングを使用するクラスのクラス コンストラクターは、パラメーターを受け取ることはできません。  
  
次の例では C3266 が生成されます。  
  
```  
// C3266.cpp  
// compile with: /clr  
  
ref class X {  
   static X(int i) { // C3266  
   // try the following line instead  
   // static X() {  
   }  
};  
  
int main() {  
}  
```  
