---
title: "コンパイラ エラー C2474 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
caps.latest.revision: 3
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5b8947e87420432801b97ac6ea05251bba38f5bb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2474"></a>コンパイラ エラー C2474
'keyword' : 隣接するセミコロンがありません。キーワードまたは識別子のどちらかである可能性があります。  
  
 コンパイラでセミコロンが検出される必要があったため、ユーザーの意図は認識されませんでした。 このエラーを解決するには、セミコロンを追加します。  
  
## <a name="example"></a>例  
 次の例では C2474 が生成されます。  
  
```  
// C2474.cpp  
// compile with: /clr /c  
  
ref class A {  
   ref class B {}  
   property int i;   // C2474 error  
};  
  
// OK  
ref class B {  
   ref class D {};  
   property int i;  
};  
  
ref class E {  
   ref class F {} property;   
   int i;  
};  
```