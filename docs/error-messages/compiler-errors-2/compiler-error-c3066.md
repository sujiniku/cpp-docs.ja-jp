---
title: コンパイラ エラー C3066 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3066
dev_langs:
- C++
helpviewer_keywords:
- C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 603b947e0f390de5dfb13a46bbe6c66db1d4e804
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3066"></a>コンパイラ エラー C3066
この型のオブジェクトを呼び出すことがいくつかの方法でこれらの引数  
  
 サロゲートを伴うあいまいな関数呼び出しが検出されました。  
  
 次の例では、C3066 が生成されます。  
  
```  
// C3066.cpp  
template <class T, class U> void func(T*, U*){}  
  
typedef void (*PF)(const int*, const char*);  
typedef void (*PF1)(const int*, volatile char*);  
  
struct A {  
   operator PF() const {  
      return func;  
   }  
  
   operator PF1() {  
      return func;  
   }  
  
   operator PF1() const  {  
      return func;  
   }  
  
};  
  
int main() {  
   A a;  
   int i;  
   char c;  
  
   a(&i, &c);   // C3066  
   a(&i, (const char *) &c);   // OK  
}  
```

## <a name="copy-list-initialization"></a>Copy-list-initialization
Visual Studio 2015 では、コンパイラは、誤って copy-list-initialization を通常の copy-initialization と同じ方法で処理しました。これは、単なるオーバーロードの解決のためのコンストラクターの変換と見なされます。 次の例では、Visual Studio 2015 は、MyInt(23) を選択しましたが、Visual Studio 2017 は正しくエラーを発生させます。

```
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```