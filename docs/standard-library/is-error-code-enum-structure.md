---
title: "is_error_code_enum 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::is_error_code_enum"
dev_langs: 
  - "C++"
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# is_error_code_enum 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[future\_errc](../Topic/future_errc%20Enumeration.md) は [error\_code](../standard-library/error-code-class.md)を格納するのに適していることを示す特化したクラスです。  
  
## 構文  
  
```  
template<>  
struct is_error_code_enum<Future_errc> : public true_type;  
```  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)