---
title: "texture_view クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
dev_langs:
- C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 4896b3ee55a5955c33e1c2652eb73851e4ec5a64
ms.lasthandoff: 03/17/2017

---
# <a name="textureview-class"></a>texture_view クラス
テクスチャへの読み取りアクセスおよび書き込みアクセスを提供します。 `texture_view` は、既定の 32 ビット bpse である `int`、`unsigned int`、または `float` の値型のテクスチャを読み取るためにのみ使用できます。 他のテクスチャ形式を読み取るには、`texture_view<const value_type, _Rank>` を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename value_type,int _Rank>  
class texture_view;  
 
template<typename value_type, int _Rank>  
class texture_view 
   : public details::_Texture_base<value_type, _Rank>;  
 
template<typename value_type, int _Rank>  
class texture_view<const value_type, _Rank> 
   : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value_type`  
 テクスチャ集合体の要素型です。  
  
 `_Rank`  
 `texture_view` のランクです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`value_type`|テクスチャ集合体の要素型です。|  
|`coordinates_type`|`texture_view` のテクセルを指定するために使用する座標の型。つまり、値型が `short_vector` である関連するテクスチャと同じランクの `float` です。|  
|`gather_return_type`|操作を収集するために使用される戻り値の型。つまり、サンプリングされた 4 つのテクセル値から収集された 4 つの同種の色要素を保持するランク 4 の `short_vector` です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[texture_view コンス トラクター](#ctor)|オーバーロードされます。 `texture_view` インスタンスを構築します。|  
|[~ texture_view デストラクター](#ctor)|`texture_view` インスタンスを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[gather_alpha](#gather_alpha)|オーバーロードされます。 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルのアルファ (w) 要素を返します。|  
|[gather_blue](#gather_blue)|オーバーロードされます。 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの青 (z) 要素を返します。|  
|[gather_green](#gather_green)|オーバーロードされます。 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの緑 (y) 要素を返します。|  
|[gather_red](#gather_red)|オーバーロードされます。 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの赤 (x) 要素を返します。|  
|[get](#get)|オーバーロードされます。 インデックスで要素の値を取得します。|  
|[サンプル](#sample)|オーバーロードされます。 指定されたサンプリング構成を使用して詳細な指定された座標およびレベルでテクスチャをサンプリングします。|  
|[set](#set)|インデックスで要素の値を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator()](#operator_call)|オーバーロードされます。 インデックスで要素の値を取得します。|  
|[演算子](#operator_at)|オーバーロードされます。 インデックスで要素の値を取得します。|  
|[operator=](#operator_eq)|オーバーロードされます。 代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[value_type](#value_type)|`texture_view` の要素の値型です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="dtor"></a>~ texture_view 

 `texture_view` インスタンスを破棄します。  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="ctor"></a>texture_view 

 `texture_view` インスタンスを構築します。  
  
```  
texture_view(// [1] constructor  
    texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [2] constructor  
    texture<value_type, _Rank>& _Src,  
    unsigned int _Mipmap_level = 0) restrict(cpu);

 
texture_view(// [3] constructor  
    const texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [4] constructor  
    const texture<value_type, _Rank>& _Src,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);

 
texture_view(// [5] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [6] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [7] copy constructor  
    const texture_view<const value_type, _Rank>& _Other,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
 [1、2] コンストラクター  
 書き込み可能な `texture` が作成される `texture_view`。  
  
 [3, 4]コンス トラクター  
 書き込み可能でない `texture` が作成される `texture_view`。  
  
 `_Other`  
 [5] コピー コンストラクター  
 ソースの書き込みが可能な `texture_view`。  
  
 [6, 7]コピー コンス トラクター  
 ソースの書き込みが可能でない `texture_view`。  
  
 `_Mipmap_level`  
 この書き込み可能な `texture` がバインドするソース `texture_view` の特定の MIPMAP レベル。 既定値は 0 で、トップ レベル (最も詳細な) MIPMAP レベルを表します。  
  
 `_Most_detailed_mip`  
 指定された `texture_view` オブジェクトに関連する、ビューのトップ レベルの (最も詳細な) MIPMAP レベル。  
  
 `_Mip_levels`  
 `texture_view` を使用してアクセスできる MIPMAP レベルの数。  
  
##  <a name="gather_red"></a>gather_red 

 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの赤 (x) 要素を返します。  
  
```  
const gather_return_type gather_red(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Address_mode`  
 `texture_view` をサンプリングするために使用するアドレス モード。 アドレス モードはすべての次元に対して同じです。  
  
 `_Sampler`  
 `texture_view` をサンプリングするために使用するサンプラー構成。  
  
 `_Coord`  
 サンプルが取得される座標です。 サンプルのテクセルを補間するには、小数の座標値が使用されます。  
  
### <a name="return-value"></a>戻り値  
 4 つのサンプリングされたテクセル値の赤 (x) 要素を含むランク 4 の短いベクター。  
  
##  <a name="gather_green"></a>gather_green 

 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの緑 (y) 要素を返します。  
  
```  
const gather_return_type gather_green(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Address_mode`  
 `texture_view` をサンプリングするために使用するアドレス モード。 アドレス モードはすべての次元に対して同じです。  
  
 `_Sampler`  
 `texture_view` をサンプリングするために使用するサンプラー構成。  
  
 `_Coord`  
 サンプルが取得される座標です。 サンプルのテクセルを補間するには、小数の座標値が使用されます。  
  
### <a name="return-value"></a>戻り値  
 4 つのサンプリングされたテクセル値の緑 (y) 要素を含むランク 4 の短いベクター。  
  
##  <a name="gather_blue"></a>gather_blue 

 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの青 (z) 要素を返します。  
  
```  
const gather_return_type gather_blue(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Address_mode`  
 `texture_view` をサンプリングするために使用するアドレス モード。 アドレス モードはすべての次元に対して同じです。  
  
 `_Sampler`  
 `texture_view` をサンプリングするために使用するサンプラー構成。  
  
 `_Coord`  
 サンプルが取得される座標です。 サンプルのテクセルを補間するには、小数の座標値が使用されます。  
  
### <a name="return-value"></a>戻り値  
 4 つのサンプリングされたテクセル値の赤 (x) 要素を含むランク 4 の短いベクター。  
  
##  <a name="gather_alpha"></a>gather_alpha 

 指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルのアルファ (w) 要素を返します。  
  
```  
const gather_return_type gather_alpha(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Address_mode`  
 `texture_view` をサンプリングするために使用するアドレス モード。 アドレス モードはすべての次元に対して同じです。  
  
 `_Sampler`  
 `texture_view` をサンプリングするために使用するサンプラー構成。  
  
 `_Coord`  
 サンプルが取得される座標です。 サンプルのテクセルを補間するには、小数の座標値が使用されます。  
  
### <a name="return-value"></a>戻り値  
 4 つのサンプリングされたテクセル値のアルファ (w) 要素を含むランク 4 の短いベクター。  
  
##  <a name="get"></a>取得 

 指定したインデックス位置にある要素の値を取得します。  
  
```  
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

 
value_type get(
    const index<_Rank>& _Index,  
    unsigned int _Mip_level = 0) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 場合によっては多次元配列である、取得する要素のインデックス。  
  
 `_Mip_level`  
 値を取得する必要のある MIPMAP レベル。 既定値 0 は最も詳細な MIPMAP レベルを表します。  
  
### <a name="return-value"></a>戻り値  
 要素の値。  
  
##  <a name="operator_eq"></a>演算子 = 

 指定された `texture_view` と同じテクスチャのビューをこの `texture_view` インスタンスに割り当てます。  
  
```  
texture_view<value_type, _Rank>& operator= (// [1] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view<const value_type, _Rank>& operator= (// [2] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

 
texture_view<const value_type, _Rank>& operator= (// [3] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 [1、2] コピー コンストラクター  
 書き込み可能な `texture_view` オブジェクト。  
  
 [3] コピー コンス トラクター  
 書き込み可能でない `texture_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `texture_view` インスタンスへの参照。  
  
##  <a name="operator_at"></a>演算子 

 インデックスごとの要素の値を返します。  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);

 
value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 場合によっては多次元の、インデックス。  
  
 `_I0`  
 1 次元インデックス。  
  
### <a name="return-value"></a>戻り値  
 `_Index` でインデックス付けされている要素の値。  
  
##  <a name="operator_call"></a>operator() 

 インデックスごとの要素の値を返します。  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);

 
value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
value_type operator() (
    int _I0) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 場合によっては多次元の、インデックス。  
  
 `_I0`  
 インデックスの最上位のコンポーネント。  
  
 `_I1`  
 インデックスの最上位の次のコンポーネント。  
  
 `_I2`  
 インデックスの最下位のコンポーネント。  
  
### <a name="return-value"></a>戻り値  
 `_Index` でインデックス付けされている要素の値。  
  
##  <a name="sample"></a>サンプル 

 指定されたサンプリング構成を使用して詳細な指定された座標およびレベルでテクスチャをサンプリングします。  
  
```  
value_type sample(
    const sampler& _Sampler,  
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);

 
template<
    filter_mode _Filter_mode = filter_linear,  
    address_mode _Address_mode = address_clamp  
>  
value_type sample(
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter_mode`  
 texture_view をサンプリングするために使用するフィルター モード。 フィルター モードは最小化、最大化、および MIPMAP フィルターで同じです。  
  
 `_Address_mode`  
 texture_view をサンプリングするために使用するアドレス モード。 アドレス モードはすべての次元に対して同じです。  
  
 `_Sampler`  
 texture_view をサンプリングするために使用するサンプラー構成。  
  
 `_Coord`  
 サンプルが取得される座標です。 テクセル値の補間には小数の座標値が使用されます。  
  
 `_Level_of_detail`  
 値は、サンプリング元の MIPMAP レベルを指定します。 2 つの MIPMAP レベル間の補間には、小数の値が使用されます。 詳細の既定のレベルは 0 で、これは最も詳細な MIPMAP レベルを表します。  
  
### <a name="return-value"></a>戻り値  
 補間されたサンプル値。  
  
##  <a name="set"></a>設定 

 指定したインデックス位置にある要素の値を指定した値に設定します。  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 場合によっては多次元配列である、設定する要素のインデックス。  
  
 `value`  
 要素を設定する値。  
  
##  <a name="value_type"></a>value_type 

 texture_view の要素の値型です。  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
