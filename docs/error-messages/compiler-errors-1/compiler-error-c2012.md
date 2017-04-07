---
title: "コンパイラ エラー C2012 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2012
dev_langs:
- C++
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
caps.latest.revision: 7
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
ms.openlocfilehash: 735729958755724fd2a2bde91215f21d52d10e40
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2012"></a>コンパイラ エラー C2012
'<' の後にファイル名がありません。  
  
 `#include` ディレクティブに必要なファイル名がありません。  
  
 次の例では C2012 エラーが生成されます。  
  
```  
// C2012.cpp  
#include <   // C2012 include the filename to resolve  
```  
  
 考えられる解決策:  
  
```  
// C2012b.cpp  
// compile with: /c  
#include <stdio.h>  
```