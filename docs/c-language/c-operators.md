---
title: "C 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
caps.latest.revision: 7
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1e4b047307bb1153c136b0485b0d141086907525
ms.lasthandoff: 02/24/2017

---
# <a name="c-operators"></a>C 演算子
C 演算子は、[C++ 組み込み演算子](../cpp/cpp-built-in-operators-precedence-and-associativity.md)のサブセットです。  
  
 演算子には&3; 種類あります。 単項式は、単項演算子とその後に続くオペランド、または、`sizeof` キーワードとその後に続く式から構成されます。 式は、変数の名前またはキャスト式です。 式がキャスト式の場合、式をかっこで囲む必要があります。 二項式は、二項演算子で結合された&2; つのオペランドで構成されます。 三項式は、条件式演算子で結合された&3; つのオペランドで構成されます。  
  
 C には、次の単項演算子が用意されています。  
  
|シンボル|名前|  
|------------|----------|  
|**– ~ !**|否定演算子と補数演算子|  
|**\* &**|間接演算子とアドレス演算子|  
|`sizeof`|サイズ演算子|  
|**+**|単項プラス演算子|  
|**++ ––**|単項インクリメント演算子と単項デクリメント演算子|  
  
 二項演算子は、左から右へ結合されます。 C には、次の二項演算子が用意されています。  
  
|シンボル|名前|  
|------------|----------|  
|**\* / %**|乗算演算子|  
|**+ –**|加法演算子|  
|**<\< >>**|シフト演算子|  
|**\<   >   \<=   >=   ==   !=**|関係演算子|  
|**&   &#124; ^**|ビット処理演算子|  
|**&&   &#124;&#124;**|論理演算子|  
|**、**|順次評価演算子|  
  
 以前のバージョンの Microsoft 16 ビット C コンパイラでサポートされていたベース演算子 (**:>**) については、「[C 言語の構文の概要](../c-language/c-language-syntax-summary.md)」を参照してください。  
  
 条件式演算子は二項式よりも優先順位が低く、結合規則が右から左であるという点で二項式とは異なります。  
  
 演算子を含む式には代入式が含まれ、単項代入演算子または二項代入演算子が使用されます。 単項代入演算子は、インクリメント (`++`) およびデクリメント (**––**) 演算子です。二項代入演算子は、単純代入演算子 (**=**) と複合代入演算子です。 複合代入演算子はそれぞれ、単純代入演算子と他の二項演算子の組み合わせです。  
  
## <a name="see-also"></a>関連項目  
 [式と代入](../c-language/expressions-and-assignments.md)