---
title: "hash_set::operator= (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= メンバー [STL/CLR]"
ms.assetid: 25ee3afd-90cd-483f-ae03-b52ce1396090
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスを置き換えます。  
  
## 構文  
  
```  
hash_set<Key>% operator=(hash_set<Key>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コピーするコンテナー。  
  
## 解説  
 このメンバー演算子は、オブジェクトに `right` を返します `*this`をコピーします。  これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーに置き換えることができます。  
  
## 使用例  
  
```  
// cliext_hash_set_operator_as.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Myhash_set::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myhash_set c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Myhash_set::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)