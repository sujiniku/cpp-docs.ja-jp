---
title: set::value_type (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::value_type
dev_langs:
- C++
helpviewer_keywords:
- value_type member [STL/CLR]
ms.assetid: 9af2fe12-9a8e-4919-9619-7a2f80988951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b04b883b2ebb8da714555e9af9fdef093cd62132
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="setvaluetype-stlclr"></a>set::value_type (STL/CLR)
要素の型。  
  
## <a name="syntax"></a>構文  
  
```  
  
typedef generic_value value_type;  
  
```  
  
## <a name="remarks"></a>コメント  
 この型は `generic_value` の同意語です。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_value_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using value_type   
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Myset::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)   
 [set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)   
 [set::reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)