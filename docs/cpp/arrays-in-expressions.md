---
title: 式の配列 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e57a97d9be3ef6245c09c6112caf72318fe784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="arrays-in-expressions"></a>式の配列
配列型の識別子が表示される場合、式で以外の`sizeof`、アドレスの (**&**)、または初期化の参照、配列の最初の要素へのポインターに変換されます。 例えば:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 ポインター `psz` は、配列 `szError1` の最初の要素をポイントします。 配列は、ポインターとは異なり、変更できる左辺値ではないことに注意してください。 したがって、次の割り当ては正しくありません。  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>関連項目  
 [配列](../cpp/arrays-cpp.md)