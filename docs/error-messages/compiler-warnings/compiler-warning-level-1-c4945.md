---
title: "コンパイラの警告 (レベル 1) C4945 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
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
ms.openlocfilehash: 04cd425a7e285fe3610604a76a2e61958051b101
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4945"></a>コンパイラの警告 (レベル 1) C4945
'symbol': 'assembly2' を使用してシンボルをインポートすることはできません: 'symbol' は既に別のアセンブリ 'assembly1' からインポートされると  
  
 シンボルが参照されたアセンブリからインポートされましたが、そのシンボルは、既に別の参照されたアセンブリからインポートします。 しない参照アセンブリのいずれかのか、アセンブリのいずれかで変更のシンボル名を取得します。  
  
 次の例では、C4945 を生成します。  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 それから  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 それから  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```