---
title: コンパイラ エラー C2654 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2654
dev_langs:
- C++
helpviewer_keywords:
- C2654
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b28fb3de46d9071c9ee19711344c5b41e337934
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2654"></a>コンパイラ エラー C2654
'identifier': メンバー関数の外でメンバーがアクセスしようとしました  
  
 宣言内でのメンバーにアクセスします。 メンバー データは、メンバー関数でのみアクセスできます。  
  
 宣言内で変数を初期化しようとするときは、このエラーを発生することができます。 この目的のためには、コンス トラクターを使用します。