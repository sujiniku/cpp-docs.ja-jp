---
title: 型チェック (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959dd52847e6140667671b9992471155d68e9646
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="type-checking-crt"></a>型チェック (CRT)
コンパイラは、制限付きの型チェックを行います。次のように、状況によって異なる数の引数をチェックします。  
  
|関数呼び出し|型がチェックされる引数|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|最初の引数 (書式設定文字列)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|最初の 2 つの引数 (ファイルまたはバッファー、書式設定文字列)|  
|`_snprintf_s`|最初の 3 つの引数 (ファイルまたはバッファー、カウント、書式設定文字列)|  
|`_open`|最初の 2 つの引数 (パス、`_open` フラグ)|  
|`_sopen_s`|最初の 3 つの引数 (パス、`_open` フラグ、共有モード)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|最初の 2 つの引数 (パス、最初の引数のポインター)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|最初の 3 つの引数 (モード フラグ、パス、最初の引数のポインター)|  
  
 コンパイラでは、ワイド文字版のこれらの関数についても同じ制限付きの型チェックを行います。  
  
## <a name="see-also"></a>参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)