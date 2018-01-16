---
title: "&lt;memory&gt; 列挙型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 52ccd226214da7ddbdca9c480bb2f8940203155e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 列挙型
||  
|-|  
|[pointer_safety](#pointer_safety)|  
  
##  <a name="pointer_safety"></a>  pointer_safety 列挙型  
 `get_pointer_safety` によって返される可能性がある値の列挙型です。  
  
class pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>コメント  
 スコープを持つ `enum` が、`get_pointer_safety()` によって返される以下の値を定義します。  
  
 `relaxed` -- 安全に派生していないポインター (明らかに、宣言されたオブジェクトまたは割り当てられたオブジェクトへのポインター) が、安全に派生したポインターと同じように扱われます。  
  
 `preferred` -- 上と同様ですが、安全に派生していないポインターを逆参照することはできません。  
  
 `strict` -- 安全に派生していないポインターは、安全に派生したポインターとは異なる方法で扱われる場合があります。  
  
## <a name="see-also"></a>参照  
 [\<memory>](../standard-library/memory.md)


