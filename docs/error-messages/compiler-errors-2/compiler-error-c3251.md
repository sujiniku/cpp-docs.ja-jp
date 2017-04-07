---
title: "コンパイラ エラー C3251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3251"
ms.assetid: 541c163e-5ee9-457c-a1e5-da860788b10d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値の型のインスタンスで基底クラス メソッドを呼び出せません。  
  
 次のエラーの原因は、`GetClass` が `Microsoft.Runtime.Object` のメンバーであり、`Microsoft.Runtime.Integer4` のメンバーでないためです。