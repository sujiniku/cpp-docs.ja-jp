---
title: __p__commode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e91c03f619be1d0f1d8ad23f3b8d60e1be30cfb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="pcommode"></a>__p__commode
ファイルの入出力操作に対して既定の*ファイル コミット モード*を指定する `_commode` グローバル変数を指し示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 `_commode` グローバル変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 `__p__commode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。  
  
 ファイル コミット モードは重要なデータがディスクに書き込まれるタイミングを指定します。 詳細については、「[fflush](../c-runtime-library/reference/fflush.md)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|__p\__commode|internal.h|