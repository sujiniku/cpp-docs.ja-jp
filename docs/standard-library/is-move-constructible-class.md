---
title: "is_move_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_move_constructible
- std.is_move_constructible
- std::is_move_constructible
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 91f451ef7ec496791d6a1a8d28965dbb5b684584
ms.lasthandoff: 02/24/2017

---
# <a name="ismoveconstructible-class"></a>is_move_constructible クラス
型に移動コンストラクターが存在するかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 T  
 評価される型  
  
## <a name="remarks"></a>コメント  
 型 `T` が移動操作によって構築できる場合に、true と評価される型述語です。 この述語は `is_constructible<T, T&&>` と同じです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)



