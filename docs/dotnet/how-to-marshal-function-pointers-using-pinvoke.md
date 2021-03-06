---
title: '方法: PInvoke を使用して関数ポインターをマーシャ リング |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1aa8da5e5b6931fb46ff283a5be15da5b2c7325d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>方法: PInvoke を使用して関数ポインターをマーシャリングする
このトピックには、マネージ デリゲートがについて説明しますと相互運用するアンマネージ関数を .NET Framework P/invoke 機能を使用するときに関数ポインターの代わりに使用できます。 ただし、Visual C (可能な場合)、代わりに、C++ Interop 機能を使用することをお勧め、ために、プログラマ P/invoke ほとんどのコンパイル時エラーを報告がタイプ セーフではありませんし、実装に時間がかかることができます。 アンマネージ API が DLL としてパッケージ化されたソース コードを使用できない場合は、P/invoke、唯一のオプションです。 それ以外の場合、次のトピックを参照してください。  
  
-   [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 引数は、ネイティブ関数ポインターの代わりにマネージ デリゲートを使用してマネージ コードから呼び出すことができます、関数ポインターを受け取るアンマネージ Api です。 コンパイラは自動的に関数ポインターとしてアンマネージ関数にデリゲートをマーシャ リングし、必要なマネージ/アンマネージ遷移コードを挿入します。  
  
## <a name="example"></a>例  
 次のコードはアンマネージとマネージ モジュールで構成されます。 アンマネージ モジュールは、関数ポインターを受け付ける TakesCallback に呼び出される関数を定義する DLL です。 このアドレスは、関数の実行に使用されます。  
  
 マネージ モジュールは、関数ポインターとしてネイティブ コードにマーシャ リングを使用してデリゲートを定義、<xref:System.Runtime.InteropServices.DllImportAttribute>マネージ コードにネイティブ TakesCallback 関数を公開する属性。 メインの関数では、デリゲートのインスタンスが作成され、TakesCallback 関数に渡されます。 プログラムの出力は、この関数がネイティブ TakesCallback 関数によって実行されることを示します。  
  
 マネージ関数では、.NET Framework のガベージ コレクション ネイティブ関数の実行中に、デリゲートを再配置することを防ぐために、マネージ デリゲートのガベージ コレクションを抑制します。  
  
```cpp  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```cpp  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 従来を使用してマネージ コードに、DLL の一部は公開されていませんことに注意してください #include ディレクティブです。 実際には、DLL は実行時にのみでの機能に問題が取り込まれるように<xref:System.Runtime.InteropServices.DllImportAttribute>はコンパイル時に、検出されません。  
  
## <a name="see-also"></a>関連項目  
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)