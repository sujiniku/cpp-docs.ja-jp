---
title: priority_queue::top (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue::top
dev_langs:
- C++
helpviewer_keywords:
- top member [STL/CLR]
ms.assetid: e45211d5-e6df-4c03-97fd-57afb87af58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7cf02100bf08ad78452368f633443b8d738730a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="priorityqueuetop-stlclr"></a>priority_queue::top (STL/CLR)
最も高い優先順位の要素にアクセスします。  
  
## <a name="syntax"></a>構文  
  
```  
reference top();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、空でない必要があります、被制御シーケンスのトップ (最高優先度) の要素への参照を返します。 要素にアクセスする、最も高い優先度、存在することがわかっている場合に使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top() = c  
 x a b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)