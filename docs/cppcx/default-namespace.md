---
title: 既定の名前空間 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f4386d3636744a673a10dd9530fd3836fdb78e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="default-namespace"></a>既定の名前空間
`default`名前空間のスコープとは、組み込みの型がサポートする C + + CX です。  
  
## <a name="syntax"></a>構文  
  
```  
namespace default;  
```  
  
### <a name="members"></a>メンバー  
 組み込み型はすべて、次のメンバーを継承します。  
  
|||  
|-|-|  
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。|  
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|このインスタンスのハッシュ コードを返します。|  
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|現在の型を表す文字列を返します。|  
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|現在の型を表す文字列を返します。|  
  
### <a name="built-in-types"></a>組み込み型  
  
|名前|説明|  
|----------|-----------------|  
|`char16`|Unicode (UTF-16) コード ポイントを表す 16 ビットの数字以外の値。|  
|`float32`|32 ビットの IEEE 754 浮動小数点数。|  
|`float64`|64 ビットの IEEE 754 浮動小数点数。|  
|`int16`|16 ビット符号付き整数。|  
|`int32`|32 ビット符号付き整数。|  
|`int64`|64 ビット符号付き整数。|  
|`int8`|8 ビット符号付き数値。|  
|`uint16`|16 ビット符号なし整数。|  
|`uint32`|32 ビット符号なし整数|  
|`uint64`|64 ビット符号なし整数。|  
|`uint8`|8 ビット符号なし数値。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** vccorlib.h  
  
## <a name="see-also"></a>関連項目  
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)