---
title: "strict_gs_check | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "strict_gs_check"
  - "strict_gs_check_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strict_gs_check プラグマ"
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# strict_gs_check
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このプラグマは、強化されたセキュリティ チェックを提供します。  
  
## 構文  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## 解説  
 コンパイラが関数スタックにランダム クッキーを挿入し、スタック ベースのバッファー オーバーランのカテゴリの検出に役立つように指示します。  既定では、\/GS \(バッファー セキュリティ チェック\) コンパイラ オプションは、すべての関数に対してクッキーを挿入しません。  詳細については、「[\/GS \(バッファーのセキュリティ チェック\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md)」を参照してください。  
  
 strict\_gs\_check を有効にするには、\/GS \(バッファー セキュリティ チェック\) でコンパイルする必要があります。  
  
 このプラグマは、有害なデータに対して公開される可能性があるコード モジュールで使用してください。  このプラグマは非常に積極的です。この防御を必要としない可能性があり、ただし生成アプリケーションのパフォーマンスに対する影響を最小化するために最適化された関数に適用されます。  
  
 このプラグマを使用した場合でも、安全なコードを記述する必要があります。  つまり、コードにバッファー オーバーランがないことを確認します。strict\_gs\_check は、コード内で残るバッファー オーバーランに対してアプリケーションを保護できます。  
  
## 使用例  
 次のコードでは、ローカル配列に配列をコピーすると、バッファー オーバーランが発生します。  \/GS でこのコードをコンパイルした場合、配列のデータ型はポインターであるため、スタックにクッキーが挿入されません。  strict\_gs\_check プラグマを追加すると、関数スタックにスタック クッキーを強制します。  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [\/GS \(バッファーのセキュリティ チェック\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md)