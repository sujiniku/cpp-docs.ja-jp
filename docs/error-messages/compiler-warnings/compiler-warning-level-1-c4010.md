---
title: "コンパイラの警告 (レベル 1) C4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

単一行コメント \(\/\/\) に、行連結文字があります。  
  
 単一行コメント \(\/\/ で始まるコメント\) に行連結文字の役割を持つ円記号 \(\\\) があります。  コンパイラでは次の行は前行の続きと見なされ、コメントとして処理されます。  
  
 構文エディターの中には、このような行連結文字に続く行がコメントとして表示されないものもあります。  この警告が発生した行の構文の色指定は無視してください。  
  
 次の例では警告 C4010 が生成されます。  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```