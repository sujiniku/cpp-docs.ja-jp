---
title: "unique_ptr クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unique_ptr
- std.unique_ptr
- std::unique_ptr
- memory/std::unique_ptr
dev_langs:
- C++
helpviewer_keywords:
- unique_ptr class
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
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
ms.openlocfilehash: 581766663067a026f73fc14893b52203a6c69294
ms.lasthandoff: 02/24/2017

---
# <a name="uniqueptr-class"></a>unique_ptr クラス
所有されているオブジェクトまたは配列へのポインターを格納します。 このオブジェクトと配列は、この `unique_ptr` によってのみ所有されます。 このオブジェクトと配列は、`unique_ptr` が破棄されたときに破棄されます。  
  
## <a name="syntax"></a>構文  
```  
class unique_ptr {
public:
    unique_ptr();
    unique_ptr(nullptr_t Nptr);
    explicit unique_ptr(pointer Ptr);
    unique_ptr(pointer Ptr,
        typename conditional<is_reference<Del>::value, Del,
        typename add_reference<const Del>::type>::type Deleter);
    unique_ptr(pointer Ptr,
        typename remove_reference<Del>::type&& Deleter);
    unique_ptr(unique_ptr&& Right);
    template <class T2, Class Del2>
    unique_ptr(unique_ptr<T2, Del2>&& Right);
    unique_ptr(const unique_ptr& Right) = delete;
    unique_ptr& operator=(const unique_ptr& Right) = delete;
};

//Specialization for arrays:  
template <class T, class D>
class unique_ptr<T[], D> {
public:
    typedef pointer;
    typedef T element_type;
    typedef D deleter_type;
    constexpr unique_ptr() noexcept;
    template <class U>
    explicit unique_ptr(U p) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    unique_ptr(unique_ptr&& u) noexcept;
    constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }     template <class U, class E>
        unique_ptr(unique_ptr<U, E>&& u) noexcept;
    ~unique_ptr();
    unique_ptr& operator=(unique_ptr&& u) noexcept;
    template <class U, class E>
    unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;
    unique_ptr& operator=(nullptr_t) noexcept;
    T& operator[](size_t i) const;


    pointer get() const noexcept;
    deleter_type& get_deleter() noexcept;
    const deleter_type& get_deleter() const noexcept;
    explicit operator bool() const noexcept;
    pointer release() noexcept;
    void reset(pointer p = pointer()) noexcept;
    void reset(nullptr_t = nullptr) noexcept;
    template <class U>
    void reset(U p) noexcept = delete;
    void swap(unique_ptr& u) noexcept;  // disable copy from lvalue unique_ptr(const unique_ptr&) = delete;  
    unique_ptr& operator=(const unique_ptr&) = delete;
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `Right`  
 `unique_ptr`。  
  
 `Nptr`  
 `rvalue` 型の `std::nullptr_t`。  
  
 `Ptr`  
 `pointer`。  
  
 `Deleter`  
 `deleter` にバインドされている `unique_ptr` 関数。  
  
## <a name="exceptions"></a>例外  
 例外は `unique_ptr` で生成されません。  
  
## <a name="remarks"></a>コメント  
 `unique_ptr` クラスは、`auto_ptr` に代わるものであり、C++ 標準ライブラリ コンテナーの要素として使用できます。  
  
 効率的に `unique_ptr` の新しいインスタンスを作成するには、[make_unique](../standard-library/memory-functions.md#make_unique) ヘルパー関数を使用します。  
  
 `unique_ptr` は一意にリソースを管理します。 `unique_ptr` オブジェクトは null ポインターを所有または保存するオブジェクトへのポインターを格納します。 1 つのリソースは、1 つの `unique_ptr` オブジェクトによってのみ所有されます。特定のリソースを所有する `unique_ptr` オブジェクトが破棄された時点で、リソースが解放されます。 `unique_ptr` オブジェクトを移動することはできますが、コピーすることはできません。詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
 特定の `deleter` に対するリソースの割り当てを認識する、`Del` 型の格納された `unique_ptr` オブジェクトを呼び出すことによって、リソースが解放されます。 既定の `deleter``default_delete``<T>` は、` ptr` が指すリソースが `new` で割り当てられることと、`delete _``Ptr` を呼び出すことによって解放できることを前提としています。 (部分的特殊化 `unique_ptr<T[]>` は `new[]` で割り当てられた配列オブジェクトを管理します。また、delete[] ` ptr` の呼び出しに特化した既定の `deleter``default_delete<T[]>` があります。)  
  
 所有されたリソースに対する格納されたポインター、`stored_ptr` には、`pointer` 型があります。 これは、定義されている場合は `Del::pointer`、定義されていない場合は `T *` です。 `deleter` がステートレスである場合、格納された `stored_deleter` オブジェクトである `deleter` はオブジェクト内の領域を使用しません。 `Del` が参照型である場合があることに注意してください。  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[unique_ptr::unique_ptr](#unique_ptr__unique_ptr)|`unique_ptr` には、7 種類のコンストラクターがあります。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[deleter_type](#deleter_type)|テンプレート パラメーター `Del` のシノニム。|  
|[element_type](#element_type)|テンプレート パラメーター `T``.` のシノニム。|  
|[pointer](#pointer)|定義されている場合は `Del::pointer` のシノニム、それ以外の場合は `T *` のシノニム。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[unique_ptr::get](#unique_ptr__get)|`stored_ptr` を返します。|  
|[unique_ptr::get_deleter](#unique_ptr__get_deleter)|`stored_deleter` への参照を返します。|  
|[unique_ptr::release](#unique_ptr__release)|`pointer()` を `stored_ptr` に格納し、以前の内容を返します。|  
|[unique_ptr::reset](#unique_ptr__reset)|現在所有されているリソースを解放し、新しいリソースを受け取ります。|  
|[unique_ptr::swap](#unique_ptr__swap)|指定された `deleter` を使用して、リソースと `unique_ptr` を交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|`operator bool`|この演算子は、`bool` に変換可能な型の値を返します。 `bool` への変換結果は、`true` の場合は `get() != pointer()`、それ以外の場合は `false` です。|  
|`operator->`|このメンバー関数は、`stored_ptr``.` を返します。|  
|`operator*`|このメンバー関数は、`stored_ptr``.` を返します*。|  
|[unique_ptr operator=](#unique_ptr_operator_eq)|現在の `unique_ptr` に `unique_ptr` (または `pointer-type`) の値を割り当てます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
##  <a name="a-namedeletertypea--deletertype"></a><a name="deleter_type"></a>  deleter_type  
 この型は、テンプレート パラメーター `Del` のシノニムです。  
  
```  
typedef Del deleter_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Del` のシノニムです。  
  
##  <a name="a-nameelementtypea--elementtype"></a><a name="element_type"></a>  element_type  
 この型は、テンプレート パラメーター `Type` のシノニムです。  
  
```  
typedef Type element_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Ty`のシノニムです。  
  
##  <a name="a-nameuniqueptrgeta--uniqueptrget"></a><a name="unique_ptr__get"></a>  unique_ptr::get  
 `stored_ptr` を返します。  
  
```  
pointer get() const;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`stored_ptr` を返します。  
  
##  <a name="a-nameuniqueptrgetdeletera--uniqueptrgetdeleter"></a><a name="unique_ptr__get_deleter"></a>  unique_ptr::get_deleter  
 `stored_deleter` への参照を返します。  
  
```  
Del& get_deleter();

const Del& get_deleter() const;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`stored_deleter` への参照を返します。  
  
##  <a name="a-nameuniqueptroperatoreqa--uniqueptr-operator"></a><a name="unique_ptr_operator_eq"></a>  unique_ptr operator=  
 指定された `unique_ptr` のアドレスを現在のアドレスに割り当てます。  
  
```  
unique_ptr& operator=(unique_ptr&& right);
template <class U, Class Del2>  
unique_ptr& operator=(unique_ptr<Type, Del>&& right);
unique_ptr& operator=(pointer-type);
```  
  
### <a name="parameters"></a>パラメーター  
 現在の `unique_ptr` に値を割り当てるために使用される `unique_ptr` 参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `reset(`` right``.release())` を呼び出し、` right``.stored_deleter` を `stored_deleter` に移動し、`*this` を返します。  
  
##  <a name="a-namepointera--pointer"></a><a name="pointer"></a>  pointer  
 定義されている場合は `Del::pointer` のシノニム、それ以外の場合は `Type *` のシノニム。  
  
```  
typedef T1 pointer;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、定義されている場合は `Del::pointer` の同意語、それ以外の場合は `Type *` の同意語です。  
  
##  <a name="a-nameuniqueptrreleasea--uniqueptrrelease"></a><a name="unique_ptr__release"></a>  unique_ptr::release  
 返された格納されているポインターの所有権を呼び出し元に解放し、格納されているポインターの値を `nullptr` に設定します。  
  
```  
pointer release();
```  
  
### <a name="remarks"></a>コメント  
 `release` を使用して、`unique_ptr` が保存した生のポインターの所有権を引き継ぎます。 呼び出し元は、返されたポインターの削除を担当します。 `unique-ptr` は、既定で構築される空の状態に設定します。 `unique_ptr` を呼び出した後に、互換性のある型の別のポインターを `release` に割り当てることができます。  
  
### <a name="example"></a>例  
  この例は、返されたオブジェクトに release の呼び出し元が対応する方法を示しています。  
  
```cpp  
// stl_release_unique.cpp  
// Compile by using: cl /W4 /EHsc stl_release_unique.cpp  
#include <iostream>  
#include <memory>  
  
struct Sample {  
   int content_;  
   Sample(int content) : content_(content) {  
      std::cout << "Constructing Sample(" << content_ << ")" << std::endl;  
   }  
   ~Sample() {  
      std::cout << "Deleting Sample(" << content_ << ")" << std::endl;  
   }  
};  
  
void ReleaseUniquePointer() {  
   // Use make_unique function when possible.    
   auto up1 = std::make_unique<Sample>(3);  
   auto up2 = std::make_unique<Sample>(42);  
  
   // Take over ownership from the unique_ptr up2 by using release  
   auto ptr = up2.release();  
   if (up2) {  
      // This statement does not execute, because up2 is empty.  
      std::cout << "up2 is not empty." << std::endl;  
   }  
   // We are now responsible for deletion of ptr.  
   delete ptr;  
   // up1 deletes its stored pointer when it goes out of scope.     
}  
  
int main() {  
   ReleaseUniquePointer();  
}  
```  
  
  コンピューターの出力:  
  
```Output  
Constructing Sample(3)  
Constructing Sample(42)  
Deleting Sample(42)  
Deleting Sample(3)  
  
```  
  
##  <a name="a-nameuniqueptrreseta--uniqueptrreset"></a><a name="unique_ptr__reset"></a>  unique_ptr::reset  
 ポインター パラメーターの所有権を取得してから、格納されている元のポインターを削除します。 新しいポインターが元の格納されているポインターの場合と同じ場合には、`reset` でポインターを削除して、格納されているポインターを `nullptr` に設定します。  
  
```  
void reset(pointer ptr = pointer());
void reset(nullptr_t ptr);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|所有権を取得するリソースへのポインター。|  
  
### <a name="remarks"></a>コメント  
 `reset` を使用して、`unique_ptr` が保有する格納されている[ポインター](#pointer)を `ptr` へ変更してから、元の格納されているポインターを削除します。 `unique_ptr` が空でなかった場合、`reset` は元の格納されているポインターについて [get_deleter](#unique_ptr__get_deleter) が返すデリーター関数を呼び出します。  
  
 `reset` は、まず新しいポインター `ptr` を格納してから、格納されている元のポインターを削除するため、新しいポインターと格納されている元のポインターが同じ場合には、`reset` は直ちに `ptr` を削除することがあります。  
  
##  <a name="a-nameuniqueptrswapa--uniqueptrswap"></a><a name="unique_ptr__swap"></a>  unique_ptr::swap  
 2 つの `unique_ptr` オブジェクト間でポインターを交換します。  
  
```  
void swap(unique_ptr& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 ポインターを交換するために使用される `unique_ptr`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`stored_ptr` を `right.stored_ptr` と交換し、`stored_deleter` を `right.stored_deleter` と交換します。  
  
##  <a name="a-nameuniqueptruniqueptra--uniqueptruniqueptr"></a><a name="unique_ptr__unique_ptr"></a>  unique_ptr::unique_ptr  
 `unique_ptr` には、7 種類のコンストラクターがあります。  
  
```  
unique_ptr();

unique_ptr(nullptr_t);
explicit unique_ptr(pointer ptr);

unique_ptr(
    Type* ptr,  
    typename conditional<
    is_reference<Del>::value, 
    Del, 
    typename add_reference<const Del>::type>::type _Deleter);

unique_ptr(pointer ptr, typename remove_reference<Del>::type&& _Deleter);
unique_ptr(unique_ptr&& right);
template <class Ty2, Class Del2>  
unique_ptr(unique_ptr<Ty2, Del2>&& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|` ptr`|`unique_ptr.` に割り当てられるリソースへのポインター。|  
|`_Deleter`|`unique_ptr` に割り当てられる `deleter`。|  
|` right`|新しく構築された `unique_ptr` に対する `unique_ptr` フィールドの割り当て元となる `unique_ptr` への `rvalue reference`。|  
  
### <a name="remarks"></a>コメント  
 最初の&2; つのコンストラクターはリソースを管理しないオブジェクトを構築します。 3 番目のコンストラクターは `stored_ptr` に `ptr` を格納します。 4 番目のコンストラクターは `stored_ptr` に `ptr` を、`stored_deleter` に `deleter` を格納します。  
  
 5 番目のコンストラクターは `stored_ptr` に `ptr` を格納し、`stored_deleter` に `deleter` を移動します。 6 番目と&7; 番目のコンストラクターは `stored_ptr` に `right.reset()` を格納し、`stored_deleter` に `right.get_deleter()` を移動します。  
  
##  <a name="a-nameuniqueptrdtoruniqueptra--uniqueptr-uniqueptr"></a><a name="unique_ptr__dtorunique_ptr"></a>  unique_ptr ~unique_ptr  
 `unique_ptr` のデストラクターで、`unique_ptr` オブジェクトを破棄します。  
  
```  
~unique_ptr();
```  
  
### <a name="remarks"></a>コメント  
 このデストラクターは `get_deleter()(stored_ptr)` を呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [\<memory>](../standard-library/memory.md)


