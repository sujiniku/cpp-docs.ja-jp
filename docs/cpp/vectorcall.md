---
title: _ _vectorcall |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1c95ed59-86c6-4857-b4ed-10519193f851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29c202a888d4c741a9a9fb54a84109100038d32a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="vectorcall"></a>__vectorcall
**Microsoft 固有の仕様**  
  
 `__vectorcall` 呼び出し規約は、可能な場合に、関数への引数をレジスタに渡すことを指定します。 `__vectorcall` も引数に複数のレジスタを使用して[_ _fastcall](../cpp/fastcall.md)または既定[x64 呼び出し規約](../build/overview-of-x64-calling-conventions.md)を使用します。 `__vectorcall` の呼び出し規約は、SSE2 (Streaming SIMD Extensions 2) 以上が搭載された x86 および x64 プロセッサのネイティブ コードでのみサポートされます。 `__vectorcall` は、関数が複数の浮動小数点または SIMD ベクターの引数を渡し、レジスタに読み込んだ引数を利用して演算を実行する場合に、その関数の処理を高速化するために使用します。 次の一覧では、`__vectorcall` の x86 と x64 の実装に共通の機能を示します。 相違点については、このトピックで後ほど説明します。  
  
|要素|実装|  
|-------------|--------------------|  
|C の名前装飾規約|関数名には、2 つの "アット" マーク (@@) とそれに続くパラメーター リストのバイト数 (10 進数) がサフィックスとして付けられます。|  
|大文字と小文字の変換規約|大文字小文字は変換されません。|  
  
 使用して、 [/Gv](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションでは、各関数をモジュールとしてコンパイルする`__vectorcall`関数は、メンバー関数でない限り、競合する呼び出し規約の属性によって宣言されたを使用して、`vararg`変数引数リスト、または名前を持つ`main`します。  
  
 レジスタによって次の 3 つの種類の引数を渡すことができます`__vectorcall`関数:*整数型*値、*ベクター型*値、および*同種ベクター集計*(HVA) の値。  
  
 整数型は、2 つの条件を満たしています。まずプロセッサのネイティブなレジスタ サイズ (たとえば、x86 コンピューターでは 4 バイト、x64 コンピューターでは 8 バイト) に収まります。また、そのビット表現を変更せずにレジスタ長の整数値に変換し、再度元に戻すことができます。 たとえば、x86 の `int` (x64 では `long long`) に昇格できる型 (`char` や `short`)、または `int` (x64 では `long long`) にキャストした後、変更せずに元の型に復帰できる型はすべて整数型です。 整数型には、ポインター、参照のほか、4 バイト以下 (x64 では 8 バイト以下) の `struct` 型や `union` 型が含まれます。 それを超えるサイズの `struct` 型と `union` 型は、x64 プラットフォームでは、呼び出し元が割り当てたメモリに、参照によって渡されます。x86 プラットフォームでは、スタックの値によって渡されます。  
  
 ベクター型は、浮動小数点型 (たとえば、`float` や `double`)、または SIMD ベクター型 (たとえば、`__m128` や `__m256`) です。  
  
 HVA 型は、同一のベクター型を持つ最大 4 個のデータ メンバーから成る複合型です。 HVA 型のアラインメント要件は、そのメンバーのベクター型のアラインメント要件と同じになります。 次の例は、同一のベクター型を 3 個含み、32 バイトのアラインメントを持つ HVA `struct` 定義を示しています。  
  
```cpp  
typedef struct {  
   __m256 x;  
   __m256 y;  
   __m256 z;  
} hva3;    // 3 element HVA type on __m256  
  
```  
  
 ヘッダー ファイルで `__vectorcall` キーワードを使用して関数を明示的に宣言すると、個別にコンパイルされたコードをエラーなしでリンクできます。 関数は `__vectorcall` を使用するようにプロトタイプ宣言される必要があり、`vararg` の可変長の引数リストは使用できません。  
  
 メンバー関数は `__vectorcall` 指定子を使用して宣言される場合があります。 非表示の `this` ポインターは、最初の整数型の引数としてレジスタで渡されます。  
  
 ARM コンピューターでは、`__vectorcall` がコンパイラによって受け入れられたり、無視されたりします。  
  
 静的でないクラスのメンバー関数が行外で宣言されている場合、行外の宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの非静的なメンバーの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義があるとします。  
  
```cpp  
struct MyClass {  
   void __vectorcall mymethod();  
};  
```  
  
 ここで、  
  
```cpp  
void MyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __vectorcall MyClass::mymethod() { return; }  
```  
  
 `__vectorcall` 関数へのポインターを作成したときは、`__vectorcall` 呼び出し規約を指定する必要があります。 次の例では、4 個の `typedef` の引数を受け取り、1 個の `__vectorcall` の値を返す `double` 関数へのポインターの `__m256` を作成しています。  
  
```cpp  
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);  
```  
  
## <a name="vectorcall-convention-on-x64"></a>x64 での __vectorcall 規約  
 x64 では、`__vectorcall` 呼び出し規約によって標準の x64 呼び出し規約が拡張され、追加のレジスタを利用できます。 整数型引数とベクター型引数の両方が、引数リスト内の位置に基づいてレジスタにマップされます。 HVA 引数は、未使用のベクター レジスタに割り当てられます。  
  
 最初の 4 個の引数がすべて整数型引数の場合、それらの引数は左から順にその位置に対応するレジスタ (RCX、RDX、R8、R9) に渡されます。 非表示の `this` ポインターは、最初の整数型引数として処理されます。 最初の 4 個の引数のうちの 1 個が HVA 引数であって、使用可能なレジスタに渡すことができない場合は、その代わりに、呼び出し元が割り当てたメモリへの参照が、その引数に対応する整数型のレジスタに渡されます。 5 番目以降のパラメーター位置にある整数型引数は、スタックに渡されます。  
  
 最初の 6 個の引数がすべてベクター型引数の場合、それらの引数はその位置に従って、左から順に SSE ベクター レジスタの 0 ～ 5 に値で渡されます。 浮動小数点型と `__m128` 型は XMM レジスタに渡され、`__m256` 型は YMM レジスタに渡されます。 この点は標準の x64 呼び出し規則と異なり、ベクター型が参照渡しではなく値渡しされ、追加のレジスタが使用されます。 ベクター型引数に対して割り当てられるシャドウ スタック領域は 8 バイトに固定され、 [/homeparams](../build/reference/homeparams-copy-register-parameters-to-stack.md)オプションは適用されません。 7 番目以降のパラメーター位置にあるベクター型引数は、呼び出し元が割り当てられたメモリへの参照によってスタックに渡されます。  
  
 ベクター引数にレジスタが割り当てられた後、HVA 全体を格納できる十分なレジスタがある場合いは、HVA 引数のデータ メンバーが未使用のベクター レジスタの XMM0 ～ XMM5 (または `__m256` 型の場合は YMM0 ～ YMM5) に昇順に割り当てられます。 十分なレジスタが使用できない場合、HVA 引数は、呼び出し元が割り当てたメモリへの参照によって渡されます。 HVA 引数用のスタック シャドウ領域は 8 バイトに固定され、内容は未定義です。 HVA の引数は、パラメーター リストの左から順にレジスタに割り当てられますが、任意の位置に割り当てることもできます。 最初の 4 個の引数位置のいずれかに、ベクター レジスタに割り当てられていない HVA 引数がある場合、その位置に対応する整数レジスタに参照によって渡されます。 5 番目以降のパラメーター位置にあり、参照によって渡された HVA 引数はスタックにプッシュされます。  
  
 `__vectorcall` 関数の結果は、可能であれば、値によってレジスタに返されます。 8 バイト以下の構造体や共用体を含む整数型の結果は、値によって RAX に返されます。 ベクター型の結果は、サイズに応じて XMM0 または YMM0 に値によって返されます。 HVA の結果は、要素のサイズに応じて、各データ要素がレジスタ XMM0:XMM3 またはレジスタ YMM0:YMM3 に値によって返されます。 対応するレジスタに収まらない結果の型は、呼び出し元が割り当てたメモリへの参照によって返されます。  
  
 `__vectorcall` の x64 実装では、スタックは呼び出し元によって管理されます。 呼び出された関数のためのスタックは、呼び出し元のプロローグ コードとエピローグ コードによって割り当てられ、クリアされます。 引数はスタックで右から左へプッシュされます。レジスタに渡された引数には、シャドウ スタック領域が割り当てられます。  
  
 次に例を示します。  
  
```cpp  
// crt_vc64.c  
// Build for amd64 with: cl /arch:AVX /W3 /FAs crt_vc64.c  
// This example creates an annotated assembly listing in  
// crt_vc64.asm.  
  
#include <intrin.h>  
#include <xmmintrin.h>  
  
typedef struct {  
   __m128 array[2];  
} hva2;    // 2 element HVA type on __m128  
  
typedef struct {  
   __m256 array[4];  
} hva4;    // 4 element HVA type on __m256  
  
// Example 1: All vectors  
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.  
// Return value in XMM0.  
__m128 __vectorcall   
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {  
   return d;  
}  
  
// Example 2: Mixed int, float and vector parameters  
// Passes a in RCX, b in XMM1, c in R8, d in XMM3, e in YMM4,   
// f in XMM5, g pushed on stack.   
// Return value in YMM0.  
__m256 __vectorcall   
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {  
   return e;  
}  
  
// Example 3: Mixed int and HVA parameters  
// Passes a in RCX, c in R8, d in R9, and e pushed on stack.  
// Passes b by element in [XMM0:XMM1];   
// b's stack shadow area is 8-bytes of undefined value.   
// Return value in XMM0.  
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {  
   return b.array[0];  
}  
  
// Example 4: Discontiguous HVA   
// Passes a in RCX, b in XMM1, d in XMM3, and e is pushed on stack.  
// Passes c by element in [YMM0,YMM2,YMM4,YMM5], discontiguous because  
// vector arguments b and d were allocated first.   
// Shadow area for c is an 8-byte undefined value.  
// Return value in XMM0.  
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {  
   return b;  
}  
  
// Example 5: Multiple HVA arguments  
// Passes a in RCX, c in R8, e pushed on stack.  
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5], each with   
// stack shadow areas of an 8-byte undefined value.  
// Return value in RAX.  
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {  
   return c + e;  
}  
  
// Example 6: HVA argument passed by reference, returned by register  
// Passes a in [XMM0:XMM1], b passed by reference in RDX, c in YMM2,   
// d in [XMM3:XMM4].   
// Register space was insufficient for b, but not for d.  
// Return value in [YMM0:YMM3].  
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {  
   return b;  
}  
  
int __cdecl main( void )  
{  
   hva4 h4;  
   hva2 h2;  
   int i;  
   float f;  
   __m128 a, b, d;  
   __m256 c, e;  
  
   a = b = d = _mm_set1_ps(3.0f);  
   c = e = _mm256_set1_ps(5.0f);  
   h2.array[0] = _mm_set1_ps(6.0f);  
   h4.array[0] = _mm256_set1_ps(7.0f);  
  
   b = example1(a, b, c, d, e);  
   e = example2(1, b, 3, d, e, 6.0f, 7);  
   d = example3(1, h2, 3, 4, 5);  
   f = example4(1, 2.0f, h4, d, 5);  
   i = example5(1, h2, 3, h4, 5);  
   h4 = example6(h2, h4, c, h2);  
}  
  
```  
  
## <a name="vectorcall-convention-on-x86"></a>x86 での __vectorcall 規約  
 `__vectorcall` 呼び出し規約は、32 ビット整数型引数に関する `__fastcall` 規約に従い、ベクター型と HVA の引数に対して SSE ベクター レジスタを利用します。  
  
 パラメーター リストの最初の 2 個の整数型引数は、左から順にそれぞれ ECX と EDX に配置されます。 非表示の `this` ポインターは、最初の整数型引数として処理され、ECX に渡されます。 最初の 6 個のベクター型引数は、SSE ベクター レジスタ 0 ～ 5 を介し、引数のサイズに応じて YMM または XMM レジスタに値によって渡されます。  
  
 最初の 6 個のベクター型引数は、左から順に SSE ベクター レジスタの 0 ～ 5 に値で渡されます。 浮動小数点型と `__m128` 型は XMM レジスタに渡され、`__m256` 型は YMM レジスタに渡されます。 シャドウ スタック領域は、レジスタで渡されるベクター型引数に対して割り当てられます。 7 番目以降のベクター型引数は、呼び出し元が割り当てられたメモリへの参照によってスタックに渡されます。 コンパイラ エラーの制限事項[C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md)これらの引数には適用されません。  
  
 ベクター引数にレジスタが割り当てられた後、HVA 全体を格納できる十分なレジスタがある場合いは、HVA 引数のデータ メンバーが未使用のベクター レジスタの XMM0 ～ XMM5 (または `__m256` 型の場合は YMM0 ～ YMM5) に昇順に割り当てられます。 十分なレジスタが使用できない場合、HVA 引数は、呼び出し元が割り当てたメモリへの参照によってスタックに渡されます。 HVA 引数には、スタック シャドウ領域は割り当てられません。 HVA の引数は、パラメーター リストの左から順にレジスタに割り当てられますが、任意の位置に割り当てることもできます。  
  
 `__vectorcall` 関数の結果は、可能であれば、値によってレジスタに返されます。 4 バイト以下の構造体や共用体を含む整数型の結果は、値によって EAX に返されます。 8 バイト以下の整数型の構造体や共用体は、値によって EDX:EAX に返されます。 ベクター型の結果は、サイズに応じて XMM0 または YMM0 に値によって返されます。 HVA の結果は、要素のサイズに応じて、各データ要素がレジスタ XMM0:XMM3 またはレジスタ YMM0:YMM3 に値によって返されます。 他の結果の型は、呼び出し元が割り当てたメモリへの参照によって返されます。  
  
 `__vectorcall` の x86 の実装は、呼び出し元がスタックの右から順にプッシュする引数の規約に従います。呼び出された関数は、戻る直前にスタックをクリアします。 スタックには、レジスタに配置されていない引数のみがプッシュされます。  
  
 次に例を示します。  
  
```cpp  
// crt_vc86.c  
// Build for x86 with: cl /arch:AVX /W3 /FAs crt_vc86.c  
// This example creates an annotated assembly listing in  
// crt_vc86.asm.  
  
#include <intrin.h>  
#include <xmmintrin.h>  
  
typedef struct {  
   __m128 array[2];  
} hva2;    // 2 element HVA type on __m128  
  
typedef struct {  
   __m256 array[4];  
} hva4;    // 4 element HVA type on __m256  
  
// Example 1: All vectors  
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.  
// Return value in XMM0.  
__m128 __vectorcall   
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {  
   return d;  
}  
  
// Example 2: Mixed int, float and vector parameters  
// Passes a in ECX, b in XMM0, c in EDX, d in XMM1, e in YMM2,   
// f in XMM3, g pushed on stack.   
// Return value in YMM0.  
__m256 __vectorcall   
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {  
   return e;  
}  
  
// Example 3: Mixed int and HVA parameters  
// Passes a in ECX, c in EDX, d and e pushed on stack.  
// Passes b by element in [XMM0:XMM1].   
// Return value in XMM0.  
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {  
   return b.array[0];  
}  
  
// Example 4: HVA assigned after vector types  
// Passes a in ECX, b in XMM0, d in XMM1, and e in EDX.  
// Passes c by element in [YMM2:YMM5].   
// Return value in XMM0.  
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {  
   return b;  
}  
  
// Example 5: Multiple HVA arguments  
// Passes a in ECX, c in EDX, e pushed on stack.  
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5].  
// Return value in EAX.  
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {  
   return c + e;  
}  
  
// Example 6: HVA argument passed by reference, returned by register  
// Passes a in [XMM1:XMM2], b passed by reference in ECX, c in YMM0,   
// d in [XMM3:XMM4].   
// Register space was insufficient for b, but not for d.  
// Return value in [YMM0:YMM3].  
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {  
   return b;  
}  
  
int __cdecl main( void )  
{  
   hva4 h4;  
   hva2 h2;  
   int i;  
   float f;  
   __m128 a, b, d;  
   __m256 c, e;  
  
   a = b = d = _mm_set1_ps(3.0f);  
   c = e = _mm256_set1_ps(5.0f);  
   h2.array[0] = _mm_set1_ps(6.0f);  
   h4.array[0] = _mm256_set1_ps(7.0f);  
  
   b = example1(a, b, c, d, e);  
   e = example2(1, b, 3, d, e, 6.0f, 7);  
   d = example3(1, h2, 3, 4, 5);  
   f = example4(1, 2.0f, h4, d, 5);  
   i = example5(1, h2, 3, h4, 5);  
   h4 = example6(h2, h4, c, h2);  
}  
  
```  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)   
 [キーワード](../cpp/keywords-cpp.md)