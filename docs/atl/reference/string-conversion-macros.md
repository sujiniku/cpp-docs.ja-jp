---
title: "文字列変換マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 89790d1a56f64e6479ae32d72c529142ba8df1de
ms.openlocfilehash: 0dce243b0f7db087db908d603e6cd1cfc4b02db8
ms.lasthandoff: 02/24/2017

---
# <a name="string-conversion-macros"></a>文字列変換マクロ
これらのマクロは、文字列に変換機能を提供します。  
  
|||  
|-|-|  
|[ATL と MFC 文字列変換マクロ](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)|文字列型の間で変換マクロのセット。|  
|[DEVMODE と受け取る文字列変換マクロ](http://msdn.microsoft.com/library/85cebec0-2a18-48e5-9c1c-99d5b7f15425)|内で文字列変換マクロのセット`DEVMODE`と`TEXTMETRIC`構造体。|  
  
##  <a name="a-nameatlandmfcstringconversionmacrosa--atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL と MFC 文字列変換マクロ  
 ここで説明する文字列変換マクロは、ATL と MFC の両方に対して有効です。 MFC 文字列変換の詳細については、次を参照してください。 [TN059: を使用して MFC の Mbcs/unicode 変換マクロ](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md)と[MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)します。  
  
##  <a name="a-namedevmodeandtextmetricstringconversionmacrosa--devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE と受け取る文字列変換マクロ  
 これらのマクロのコピーを作成する、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)または[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体し、新しい構造内の文字列を新しい文字列型に変換します。 マクロを使用して、新しい構造のスタックにメモリを割り当て、新しい構造体へのポインターを返します。  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>コメント  
 例:  
  
 [!code-cpp[NVC_ATL_Utilities #&128;](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 および  
  
 [!code-cpp[NVC_ATL_Utilities #&129;](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 マクロ名で、ソースの構造の文字列型が左側 (たとえば、 **A**) 送信先構造に文字列型が、右側が (たとえば、 **W**)。 **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 したがって、`DEVMODEA2W`コピー、`DEVMODE`構造体**LPSTR**に文字列を`DEVMODE`構造体`LPWSTR`文字列、`TEXTMETRICOLE2T`コピー、`TEXTMETRIC`構造体`LPOLESTR`に文字列を`TEXTMETRIC`構造体`LPTSTR`文字列、およびなどです。  
  
 2 つの文字列に変換されたり、`DEVMODE`構造体は、デバイス名 ( **dmDeviceName**) と形式名 ( **dmFormName**)。 `DEVMODE`文字列変換マクロは構造体のサイズも更新 ( **dmSize**)。  
  
 4 つの文字列に変換されたり、`TEXTMETRIC`構造体は、最初の文字 ( **tmFirstChar**)、最後の文字 ( **tmLastChar**)、既定の文字 ( **tmDefaultChar**)、および改行文字 ( **tmBreakChar**)。  
  
 動作、`DEVMODE`と`TEXTMETRIC`文字列変換マクロは、存在する場合、有効なコンパイラ ディレクティブとは異なります。 します。 ソースの型とターゲットの型が同じである場合、変換は実行されません。 コンパイラ ディレクティブ**T**と**OLE**次のようにします。  
  
|有効なコンパイラ ディレクティブ|T の変更後|OLE の変更後|  
|----------------------------------|---------------|-----------------|  
|none|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE**と**は、OLE2ANSI**|**W**|**A**|  
  
 次の表に、`DEVMODE`と`TEXTMETRIC`文字列変換マクロです。  
  
### <a name="devmode-and-textmetric-string-conversion-macros"></a>DEVMODE と受け取る文字列変換マクロ  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

