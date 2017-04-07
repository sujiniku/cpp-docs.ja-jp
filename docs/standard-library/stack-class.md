---
title: "stack クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::stack
- std.stack
- stack
dev_langs:
- C++
helpviewer_keywords:
- stack, stack class
- stack class
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81467a48b08fab628da94b217c2925010f3118fe
ms.lasthandoff: 02/24/2017

---
# <a name="stack-class"></a>stack クラス
基になるコンテナー型に最も新しく追加された要素へのアクセスを制限することにより、機能の制限を提供するテンプレート コンテナーのアダプター クラスです。 stack クラスは、スタック操作のみがコンテナーで実行されることが明確であることが重要な場合に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Type, class Container= deque <Type>>  
class stack  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Type*  
 スタックに格納される要素のデータ型。  
  
 `Container`  
 スタックを実装するために使用する基になるコンテナーの型。 既定値は、クラス `deque`*\<Type>* です。  
  
## <a name="remarks"></a>コメント  
 stack オブジェクトの最初のテンプレート パラメーターで指定するクラス **Type** の要素は [value_type](#stack__value_type) と同義で、2 番目のテンプレート パラメーターで指定する基になるコンテナー クラス **Container** 内の要素の型と一致する必要があります。 **Type** は割り当て可能にして、対象の型のオブジェクトをコピーできるように、および対象の型の変数に値を割り当てられるようにする必要があります。  
  
 スタックに適した基になるコンテナー クラスには、[deque](../standard-library/deque-class.md)、[list クラス](../standard-library/list-class.md)、および [vector クラス](../standard-library/vector-class.md)、または **back**、`push_back`、および `pop_back` の各操作をサポートするその他すべてのシーケンス コンテナーがあります。 基になるコンテナー クラスは、コンテナー アダプター内にカプセル化されます。コンテナー アダプターは、限られた一連のシーケンス コンテナーのメンバーの関数のみをパブリック インターフェイスとして公開します。  
  
 stack オブジェクトは、クラス **Type** の要素が等価比較できる場合にのみ等価比較でき、クラス **Type** の要素が小なり比較できる場合にのみ小なり比較できます。  
  
-   stack クラスは、後入れ先出し (LIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、積み重ねられた皿です。 要素 (皿) は、積み重ねの一番上からのみ挿入、検査、または削除できます。積み重ねの一番上に相当するのは、基本のコンテナーの末尾にある最後の要素です。 一番上の要素にのみアクセスできる制限があることが、stack クラスを使用する理由です。  
  
-   [queue クラス](../standard-library/queue-class.md)は、先入れ先出し (FIFO) のデータ構造をサポートしています。 思い描くのに助けとなるのは、銀行の窓口で並んでいる人です。 要素 (人々) は、列の一番後ろに追加され、列の一番前から取り除くことができます。 列の一番前と一番後ろの両方を検査できます。 このように一番前と一番後ろの要素にのみアクセスできる制限があることが、queue クラスを使用する理由です。  
  
-   [Priority_queue クラス](../standard-library/priority-queue-class.md)は、最も大きな要素が常に先頭の位置になるように、その要素を並べ替えます。 要素の挿入、および先頭の要素の検査と削除をサポートしています。 思い描くのに助けとなるのは、年齢、身長、またはその他の条件によって整列している人です。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[stack](#stack__stack)|空であるか、基本のコンテナー オブジェクトのコピーである `stack` を構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#stack__container_type)|`stack` によって適合されるように、基本のコンテナーを提供する型。|  
|[size_type](#stack__size_type)|`stack` 内の要素の数を表すことができる符号なし整数型。|  
|[value_type](#stack__value_type)|`stack` 内に要素として格納されるオブジェクトの種類を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[empty](#stack__empty)|`stack` が空かどうかをテストします。|  
|[pop](#stack__pop)|`stack` の先頭から要素を削除します。|  
|[push](#stack__push)|`stack` の先頭に要素を追加します。|  
|[size](#stack__size)|`stack` 内の要素数を返します。|  
|[top](#stack__top)|`stack` の先頭にある要素への参照を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<stack>  
  
 **名前空間:** std  
  
##  <a name="stack__container_type"></a>  stack::container_type  
 適合されるように、基本のコンテナーを提供する型。  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Container` のシノニムです。 3 つの C++ 標準ライブラリ シーケンス コンテナー クラス (vector クラス、list クラス、既定の deque クラス) はすべて、stack オブジェクトの基本のコンテナーとしての使用要件を満たしています。 こうした要件を満たすユーザー定義型を使用することもできます。  
  
 `Container`の詳細については、[stack クラス](../standard-library/stack-class.md)のトピックのコメントに関するセクションを参照してください。  
  
### <a name="example"></a>例  
  `container_type` の宣言方法や使用方法の例については、[stack::stack](#stack__stack) の例を参照してください。  
  
##  <a name="stack__empty"></a>  stack::empty  
 stack が空かどうかをテストします。  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 set が空の場合は **true**、set が空ではない場合は **false**。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_empty.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack <int> s1, s2;  
  
   s1.push( 1 );  
  
   if ( s1.empty( ) )  
      cout << "The stack s1 is empty." << endl;  
   else  
      cout << "The stack s1 is not empty." << endl;  
  
   if ( s2.empty( ) )  
      cout << "The stack s2 is empty." << endl;  
   else  
      cout << "The stack s2 is not empty." << endl;  
}  
```  
  
```Output  
The stack s1 is not empty.  
The stack s2 is empty.  
```  
  
##  <a name="stack__pop"></a>  stack::pop  
 stack の先頭から要素を削除します。  
  
```  
void pop();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用するには、stack を空にすることはできません。 stack の先頭は最も直近に追加された要素によって占有される位置であり、コンテナーの末尾にある最後の要素になります。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_pop.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
  
   s1.pop( );  
  
   i = s1.size( );  
   cout << "After a pop, the stack length is "   
        << i << "." << endl;  
  
   i = s1.top( );  
   cout << "After a pop, the element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
After a pop, the stack length is 2.  
After a pop, the element at the top of the stack is 20.  
```  
  
##  <a name="stack__push"></a>  stack::push  
 stack の先頭に要素を追加します。  
  
```  
void push(const Type& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 スタックの先頭に追加される要素。  
  
### <a name="remarks"></a>コメント  
 stack の先頭は最も直近に追加された要素によって占有される位置であり、コンテナーの末尾にある最後の要素になります。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_push.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 10 );  
   s1.push( 20 );  
   s1.push( 30 );  
  
   stack <int>::size_type i;  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   i = s1.top( );  
   cout << "The element at the top of the stack is "  
        << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 3.  
The element at the top of the stack is 30.  
```  
  
##  <a name="stack__size"></a>  stack::size  
 stack 内の要素数を返します。  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 stack の現在の長さ。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_size.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1, s2;  
   stack <int>::size_type i;  
  
   s1.push( 1 );  
   i = s1.size( );  
   cout << "The stack length is " << i << "." << endl;  
  
   s1.push( 2 );  
   i = s1.size( );  
   cout << "The stack length is now " << i << "." << endl;  
}  
```  
  
```Output  
The stack length is 1.  
The stack length is now 2.  
```  
  
##  <a name="stack__size_type"></a>  stack::size_type  
 stack 内の要素の数を表すことができる符号なし整数型。  
  
```  
typedef typename Container::size_type size_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、stack によって採用された基本コンテナーの `size_type` のシノニムです。  
  
### <a name="example"></a>例  
  `size_type` の宣言方法や使用方法の例については、[size](#stack__size) の例を参照してください。  
  
##  <a name="stack__stack"></a>  stack::stack  
 空であるか、基本のコンテナー クラスのコピーである stack を構築します。  
  
```  
stack();

explicit stack(const container_type& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 構築される container のコピー元となる container。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_stack.cpp  
// compile with: /EHsc  
#include <stack>  
#include <vector>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Declares stack with default deque base container  
   stack <char> dsc1;  
  
   //Explicitly declares a stack with deque base container  
   stack <char, deque<char> > dsc2;  
  
   // Declares a stack with vector base containers  
   stack <int, vector<int> > vsi1;  
  
   // Declares a stack with list base container  
   stack <int, list<int> > lsi;  
  
   // The second member function copies elements from a container  
   vector<int> v1;  
   v1.push_back( 1 );  
   stack <int, vector<int> > vsi2( v1 );  
   cout << "The element at the top of stack vsi2 is "  
        << vsi2.top( ) << "." << endl;  
}  
```  
  
```Output  
The element at the top of stack vsi2 is 1.  
```  
  
##  <a name="stack__top"></a>  stack::top  
 stack の先頭にある要素への参照を返します。  
  
```  
reference top();

const_reference top() const;
```  
  
### <a name="return-value"></a>戻り値  
 stack の先頭にあるコンテナーの最後の要素への参照。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を適用するには、stack を空にすることはできません。 stack の先頭は最も直近に追加された要素によって占有される位置であり、コンテナーの末尾にある最後の要素になります。  
  
 **top** の戻り値が `const_reference` に割り当てられている場合、stack オブジェクトを変更することはできません。 **top** の戻り値が **reference** に割り当てられている場合、stack オブジェクトを変更することはできません。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_top.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   stack <int> s1;  
  
   s1.push( 1 );  
   s1.push( 2 );  
  
   int& i = s1.top( );  
   const int& ii = s1.top( );  
  
   cout << "The top integer of the stack s1 is "  
        << i << "." << endl;  
   i--;  
   cout << "The next integer down is "<< ii << "." << endl;  
}  
```  
  
```Output  
The top integer of the stack s1 is 2.  
The next integer down is 1.  
```  
  
##  <a name="stack__value_type"></a>  stack::value_type  
 stack 内に要素として格納されるオブジェクトの種類を表す型。  
  
```  
typedef typename Container::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、stack によって採用された基本コンテナーの `value_type` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// stack_value_type.cpp  
// compile with: /EHsc  
#include <stack>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declares stacks with default deque base container  
   stack<int>::value_type AnInt;  
  
   AnInt = 69;  
   cout << "The value_type is AnInt = " << AnInt << endl;  
  
   stack<int> s1;  
   s1.push( AnInt );  
   cout << "The element at the top of the stack is "  
        << s1.top( ) << "." << endl;  
}  
```  
  
```Output  
The value_type is AnInt = 69  
The element at the top of the stack is 69.  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)

