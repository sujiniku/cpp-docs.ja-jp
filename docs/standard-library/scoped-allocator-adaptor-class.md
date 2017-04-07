---
title: "scoped_allocator_adaptor クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.scoped_allocator_adaptor
- scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor
dev_langs:
- C++
helpviewer_keywords:
- scoped_allocator_adaptor Class
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: f4c343592c2c767d52a66091ecca5b1bd4ae9e88
ms.lasthandoff: 02/24/2017

---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor クラス
アロケーターの入れ子を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class Outer, class... Inner>  
class scoped_allocator_adaptor;  
```  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、1 つまたは複数のアロケーターの入れ子をカプセル化します。 このような各クラスは、`outer_allocator_type` 型の最も外側のアロケーターである `Outer` のシノニムを持ちます。これは、`scoped_allocator_adaptor` オブジェクトのパブリック ベースです。 `Outer` はコンテナーで使用されるメモリの割り当てに使用されます。 このアロケーター基本オブジェクトへの参照を取得するには、`outer_allocator` を呼び出します。  
  
 入れ子の残りの部分には `inner_allocator_type` 型が含まれます。 内部のアロケーターを使用して、コンテナー内の要素にメモリを割り当てます。 格納されているこの型のオブジェクトへの参照を取得するには、`inner_allocator` を呼び出します。 `Inner...` が空ではない場合、`inner_allocator_type` は型 `scoped_allocator_adaptor<Inner...>` を持ち、`inner_allocator` はメンバー オブジェクトを指定します。 それ以外の場合、`inner_allocator_type` は型 `scoped_allocator_adaptor<Outer>` を持ち、`inner_allocator` はオブジェクト全体を指定します。  
  
 入れ子は、必要に応じて、最も内側のカプセル化されたアロケーターをレプリケートする任意の深さがあるかのように動作します。  
  
 このテンプレート クラスの動作を説明する場合、表示されるインターフェイスの一部ではないいくつかの概念が役立ちます。 *最も外側のアロケーター*は、コンストラクトのすべての呼び出しを仲介し、メソッドを破棄します。 再帰関数 `OUTERMOST(X)` で効率的に定義されます。ここで `OUTERMOST(X)` は、次のいずれかです。  
  
-   `X.outer_allocator()` が整形式である場合、`OUTERMOST(X)` は `OUTERMOST(X.outer_allocator())` です。  
  
-   それ以外の場合、`OUTERMOST(X)` は `X` です。  
  
 説明のために&3; つの型が定義されています。  
  
|型|説明|  
|----------|-----------------|  
|`Outermost`|`OUTERMOST(*this)` の型。|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### <a name="constructors"></a>コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scoped_allocator_adaptor::scoped_allocator_adaptor コンストラクター](#scoped_allocator_adaptor__scoped_allocator_adaptor_constructor)|`scoped_allocator_adaptor` オブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedef  
  
|名前|説明|  
|----------|-----------------|  
|`const_pointer`|この型は、アロケーター `Outer` に関連付けられている `const_pointer` のシノニムです。|  
|`const_void_pointer`|この型は、アロケーター `Outer` に関連付けられている `const_void_pointer` のシノニムです。|  
|`difference_type`|この型は、アロケーター `Outer` に関連付けられている `difference_type` のシノニムです。|  
|`inner_allocator_type`|この型は、入れ子になったアダプター `scoped_allocator_adaptor<Inner...>` の型のシノニムです。|  
|`outer_allocator_type`|この型は、基本アロケーター `Outer` の型のシノニムです。|  
|`pointer`|この型は、アロケーター `Outer` に関連付けられている `pointer` のシノニムです。|  
|`propagate_on_container_copy_assignment`|`Outer_traits::propagate_on_container_copy_assignment` が true を保持するか、または `inner_allocator_type::propagate_on_container_copy_assignment` が true を保持する場合にのみ、この型は true を保持します。|  
|`propagate_on_container_move_assignment`|`Outer_traits::propagate_on_container_move_assignment` が true を保持するか、または `inner_allocator_type::propagate_on_container_move_assignment` が true を保持する場合にのみ、この型は true を保持します。|  
|`propagate_on_container_swap`|`Outer_traits::propagate_on_container_swap` が true を保持するか、または `inner_allocator_type::propagate_on_container_swap` が true を保持する場合にのみ、この型は true を保持します。|  
|`size_type`|この型は、アロケーター `Outer` に関連付けられている `size_type` のシノニムです。|  
|`value_type`|この型は、アロケーター `Outer` に関連付けられている `value_type` のシノニムです。|  
|`void_pointer`|この型は、アロケーター `Outer` に関連付けられている `void_pointer` のシノニムです。|  
  
### <a name="structs"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[scoped_allocator_adaptor::rebind 構造体](#scoped_allocator_adaptor__rebind_struct)|`scoped_allocator_adaptor\<Other, Inner...>` のシノニムとして `Outer::rebind\<Other>::other` 型を定義します。|  
  
### <a name="methods"></a>メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[scoped_allocator_adaptor::allocate メソッド](#scoped_allocator_adaptor__allocate_method)|`Outer` アロケーターを使用してメモリを割り当てます。|  
|[scoped_allocator_adaptor::construct メソッド](#scoped_allocator_adaptor__construct_method)|オブジェクトを構築します。|  
|[scoped_allocator_adaptor::deallocate メソッド](#scoped_allocator_adaptor__deallocate_method)|外側のアロケーターを使用してオブジェクトの割り当てを解除します。|  
|[scoped_allocator_adaptor::destroy メソッド](#scoped_allocator_adaptor__destroy_method)|指定したオブジェクトを破棄します。|  
|[scoped_allocator_adaptor::inner_allocator メソッド](#scoped_allocator_adaptor__inner_allocator_method)|`inner_allocator_type` 型の格納されているオブジェクトへの参照を取得します。|  
|[scoped_allocator_adaptor::max_size メソッド](#scoped_allocator_adaptor__max_size_method)|外側のアロケーターが割り当てることができるオブジェクトの最大数を指定します。|  
|[scoped_allocator_adaptor::outer_allocator メソッド](#scoped_allocator_adaptor__outer_allocator_method)|`outer_allocator_type` 型の格納されているオブジェクトへの参照を取得します。|  
|[scoped_allocator_adaptor::select_on_container_copy_construction メソッド](#scoped_allocator_adaptor__select_on_container_copy_construction_method)|対応するアロケーターごとに `select_on_container_copy_construction` を呼び出すことによって、格納されている各アロケーター オブジェクトが初期化された新しい `scoped_allocator_adaptor` オブジェクトを作成します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<scoped_allocator>  
  
 **名前空間:** std  
  
##  <a name="a-namescopedallocatoradaptorallocatemethoda--scopedallocatoradaptorallocate-method"></a><a name="scoped_allocator_adaptor__allocate_method"></a>  scoped_allocator_adaptor::allocate メソッド  
 `Outer` アロケーターを使用してメモリを割り当てます。  
  
```cpp  
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 十分な記憶域を割り当てる要素の数。  
  
 `hint`  
 要求の前に割り当てられたオブジェクトのアドレスを見つけることによって、アロケーター オブジェクトを支援できるポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は `Outer_traits::allocate(outer_allocator(), count)` を返します。 2 番目のメンバー関数は `Outer_traits::allocate(outer_allocator(), count, hint)` を返します。  
  
##  <a name="a-namescopedallocatoradaptorconstructmethoda--scopedallocatoradaptorconstruct-method"></a><a name="scoped_allocator_adaptor__construct_method"></a>  scoped_allocator_adaptor::construct メソッド  
 オブジェクトを構築します。  
  
```cpp  
template <class Ty, class... Atypes>  
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>  
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,  
    tuple<Atypes1&&...>  
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>  
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr,  
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>  
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 オブジェクトが構築されるメモリの場所へのポインター。  
  
 `args`  
 引数リスト。  
  
 `first`  
 ペアの最初の型のオブジェクト。  
  
 `second`  
 ペアの&2; 番目の型のオブジェクト。  
  
 `right`  
 移動またはコピーされる既存のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)` を呼び出して、最初のメソッドで `ptr` にオブジェクトを構築します。ここで `xargs...` は、次のいずれかです。  
  
-   `uses_allocator<Ty, inner_allocator_type>` が false を保持する場合、`xargs...` は `args...` です。  
  
-   `uses_allocator<Ty, inner_allocator_type>` が true を保持し、`is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` が true を保持する場合、`xargs...` は `allocator_arg, inner_allocator(), args...` です。  
  
-   `uses_allocator<Ty, inner_allocator_type>` が true を保持し、`is_constructible<Ty, args..., inner_allocator()>` が true を保持する場合、`xargs...` は `args..., inner_allocator()` です。  
  
 `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)` (`xargs...` は前出のリストのように変更された `first...`) および `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)` (`xargs...` は前出のリストのように変更された `second...`) を呼び出して、2 番目のメソッドで `ptr` にペア オブジェクトを構築します。  
  
 3 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)` と同じです。  
  
 4 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))` と同じです。  
  
 5 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))` と同じです。  
  
 6 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))` と同じです。  
  
##  <a name="a-namescopedallocatoradaptordeallocatemethoda--scopedallocatoradaptordeallocate-method"></a><a name="scoped_allocator_adaptor__deallocate_method"></a>  scoped_allocator_adaptor::deallocate メソッド  
 外側のアロケーターを使用してオブジェクトの割り当てを解除します。  
  
```cpp  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 割り当て解除されるオブジェクトの開始位置へのポインター。  
  
 `count`  
 割り当て解除するオブジェクトの数。  
  
##  <a name="a-namescopedallocatoradaptordestroymethoda--scopedallocatoradaptordestroy-method"></a><a name="scoped_allocator_adaptor__destroy_method"></a>  scoped_allocator_adaptor::destroy メソッド  
 指定したオブジェクトを破棄します。  
  
```cpp  
template <class Ty>  
void destroy(Ty* ptr)  
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 破棄するオブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `Outermost_traits::destroy(OUTERMOST(*this), ptr)`  
  
##  <a name="a-namescopedallocatoradaptorinnerallocatormethoda--scopedallocatoradaptorinnerallocator-method"></a><a name="scoped_allocator_adaptor__inner_allocator_method"></a>  scoped_allocator_adaptor::inner_allocator メソッド  
 `inner_allocator_type` 型の格納されているオブジェクトへの参照を取得します。  
  
```cpp  
inner_allocator_type& inner_allocator() noexcept;  
const inner_allocator_type& inner_allocator() const noexcept;  
```  
  
### <a name="return-value"></a>戻り値  
 `inner_allocator_type` 型の格納されているオブジェクトへの参照。  
  
##  <a name="a-namescopedallocatoradaptormaxsizemethoda--scopedallocatoradaptormaxsize-method"></a><a name="scoped_allocator_adaptor__max_size_method"></a>  scoped_allocator_adaptor::max_size メソッド  
 外側のアロケーターが割り当てることができるオブジェクトの最大数を指定します。  
  
```cpp  
size_type max_size();
```  
  
### <a name="return-value"></a>戻り値  
 `Outer_traits::max_size(outer_allocator())`  
  
##  <a name="a-namescopedallocatoradaptorouterallocatormethoda--scopedallocatoradaptorouterallocator-method"></a><a name="scoped_allocator_adaptor__outer_allocator_method"></a>  scoped_allocator_adaptor::outer_allocator メソッド  
 `outer_allocator_type` 型の格納されているオブジェクトへの参照を取得します。  
  
```cpp  
outer_allocator_type& outer_allocator() noexcept;  
const outer_allocator_type& outer_allocator() const noexcept;  
```  
  
### <a name="return-value"></a>戻り値  
 `outer_allocator_type` 型の格納されているオブジェクトへの参照。  
  
##  <a name="a-namescopedallocatoradaptorrebindstructa--scopedallocatoradaptorrebind-struct"></a><a name="scoped_allocator_adaptor__rebind_struct"></a>  scoped_allocator_adaptor::rebind 構造体  
 `scoped_allocator_adaptor\<Other, Inner...>` のシノニムとして `Outer::rebind\<Other>::other` 型を定義します。  
  
struct rebind{  
   typedef Other_traits::rebind\<Other>  
   Other_alloc;  
   typedef scoped_allocator_adaptor\<Other_alloc, Inner...> other;  
   };  
  
##  <a name="a-namescopedallocatoradaptorscopedallocatoradaptorconstructora--scopedallocatoradaptorscopedallocatoradaptor-constructor"></a><a name="scoped_allocator_adaptor__scoped_allocator_adaptor_constructor"></a>  scoped_allocator_adaptor::scoped_allocator_adaptor コンストラクター  
 `scoped_allocator_adaptor` オブジェクトを構築します。  
  
```cpp  
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(
 const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(
 scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;  
template <class Outer2>  
scoped_allocator_adaptor(Outer2&& al,  
    const Inner&... rest) noexcept;  
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 既存の `scoped_allocator_adaptor`。  
  
 `al`  
 外側のアロケーターとして使用する既存のアロケーター。  
  
 `rest`  
 内側のアロケーターとして使用するアロケーターのリスト。  
  
### <a name="remarks"></a>コメント  
 1 番目のコンストラクターは、格納されているアロケーター オブジェクトを既定で構築します。 次の&3; つのコンストラクターは、それぞれ `right` 内の対応するオブジェクトから、格納されているアロケーター オブジェクトを構築します。 最後のコンストラクターは、引数リストの対応する引数から、格納されているアロケーター オブジェクトを構築します。  
  
##  <a name="a-namescopedallocatoradaptorselectoncontainercopyconstructionmethoda--scopedallocatoradaptorselectoncontainercopyconstruction-method"></a><a name="scoped_allocator_adaptor__select_on_container_copy_construction_method"></a>  scoped_allocator_adaptor::select_on_container_copy_construction メソッド  
 対応するアロケーターごとに `select_on_container_copy_construction` を呼び出すことによって、格納されている各アロケーター オブジェクトが初期化された新しい `scoped_allocator_adaptor` オブジェクトを作成します。  
  
```cpp  
scoped_allocator_adaptor select_on_container_copy_construction();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、実質的に `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())` を返します。 結果は、対応するアロケーター `al` に対して `al.select_on_container_copy_construction()` を呼び出すことによって、格納されている各アロケーター オブジェクトが初期化された新しい `scoped_allocator_adaptor` オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)



