---
title: _CrtMemDifference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDifference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CrtMemDifference
- CrtMemDifference
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 16
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2d8cba0ada845e7e75bfe15945700a1385c8bcbb
ms.lasthandoff: 02/24/2017

---
# <a name="crtmemdifference"></a>_CrtMemDifference
2 つのメモリ状態を比較し、その違いを返します (デバッグ バージョンのみ)。  
  
## <a name="syntax"></a>構文  
  
```  
int _CrtMemDifference(   
   _CrtMemState *stateDiff,  
   const _CrtMemState *oldState,  
   const _CrtMemState *newState   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stateDiff`  
 (返された)&2; つのメモリ状態の違いを格納する `_CrtMemState` 構造体へのポインター。  
  
 `oldState`  
 古い方のメモリ状態 (`_CrtMemState` 構造体) へのポインター。  
  
 `newState`  
 新しい方のメモリ状態 (`_CrtMemState` 構造体) へのポインター。  
  
## <a name="return-value"></a>戻り値  
 メモリ状態が大きく異なる場合、 `_CrtMemDifference` は TRUE を返します。 それ以外の場合、関数は FALSE を返します。  
  
## <a name="remarks"></a>コメント  
 `_CrtMemDifference` 関数は、 `oldState` と `newState` を比較し、その違いを `stateDiff`に格納します。アプリケーションはこの情報を使用して、メモリ リークなどのメモリの問題を検出できます。 [_DEBUG](../../c-runtime-library/debug.md) が定義されていない場合、`_CrtMemDifference` の呼び出しは前処理で削除されます。  
  
 `newState` と `oldState` にはそれぞれ、`_CrtMemDifference` を呼び出す前に [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) によってデータが格納された、Crtdbg.h で定義されている `_CrtMemState` 構造体への正しいポインターを指定する必要があります。 `stateDiff` には、`_CrtMemState` 構造体の以前に割り当てられたインスタンスへのポインターを指定する必要があります。 `stateDiff`、`newState` または `oldState` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を `EINVAL` に設定し、FALSE を返します。  
  
 `_CrtMemDifference` は、`_CrtMemState` のブロックの `oldState` フィールド値と `newState` のブロックのそのフィールド値を比較し、結果を `stateDiff` に格納します。 割り当てられているブロックの型の数または各型に割り当てられているブロックの合計数が&2; つのメモリ状態で異なる場合、この&2; つの状態は、大きく異なると言えます。 2 つの状態間の、一度に割り当てられた量の最大値の差、および&2; つの状態間の割り当ての合計の差も `stateDiff`に格納されます。  
  
 既定では、内部 C ランタイム ブロック (`_CRT_BLOCK`) は、メモリ状態操作に含まれません。 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して `_CRTDBG_CHECK_CRT_DF` ビットの `_crtDbgFlag` をオンにすることで、このブロックをリーク検出などのメモリ状態操作に含めることができます。 解放されたメモリ ブロック (`_FREE_BLOCK`) に関して、 `_CrtMemDifference` は TRUE を返しません。  
  
 ヒープ状態関数と `_CrtMemState` 構造体の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_CrtMemDifference`|\<crtdbg.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)