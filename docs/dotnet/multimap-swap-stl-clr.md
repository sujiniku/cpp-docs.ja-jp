---
title: multimap::swap (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 198018d2-7814-4237-8ec3-5f3ea950e8af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 28dda88c2c10079b622e81c1505d22fc2b5f3d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="multimapswap-stlclr"></a>multimap::swap (STL/CLR)
2 つのコンテナーのコンテンツを交換します。  
  
## <a name="syntax"></a>構文  
  
```  
void swap(multimap<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテンツを交換するコンテナー。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、`this` と `right` の間で被制御シーケンスを交換します。 定数時間では、例外をスローしません。 2 つのコンテナーの内容を交換する簡単な方法として使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_multimap_swap.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'd', 4));   
    c2.insert(Mymultimap::make_value(L'e', 5));   
    c2.insert(Mymultimap::make_value(L'f', 6));   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[d 4] [e 5] [f 6]  
[d 4] [e 5] [f 6]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::operator= (STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)