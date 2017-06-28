---
title: "gamma_distribution クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- gamma_distribution
- random/std::gamma_distribution
- random/std::gamma_distribution::reset
- random/std::gamma_distribution::alpha
- random/std::gamma_distribution::beta
- random/std::gamma_distribution::param
- random/std::gamma_distribution::min
- random/std::gamma_distribution::max
- random/std::gamma_distribution::operator()
- random/std::gamma_distribution::param_type
- random/std::gamma_distribution::param_type::alpha
- random/std::gamma_distribution::param_type::beta
- random/std::gamma_distribution::param_type::operator==
- random/std::gamma_distribution::param_type::operator!=
- random/std::gamma_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- gamma_distribution
- gamma_distribution class
ms.assetid: 2a6798ac-6152-41d7-8ef6-d684d92f1572
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 4dc6623f129a73bde85ab350777f948bce09c091
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="gammadistribution-class"></a>gamma_distribution クラス
ガンマ分布を生成します。  
  
## <a name="syntax"></a>構文  
```  
template<class RealType = double>
class gamma_distribution {
public:    
    // types 
    typedef RealType result_type;    
    struct param_type;  

    // constructors and reset functions 
    explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
    explicit gamma_distribution(const param_type& parm);
    void reset();
    
    // generating functions
    template <class URNG>  
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions
    result_type alpha() const;
    result_type beta() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
};
```    
#### <a name="parameters"></a>パラメーター  
*RealType*  
浮動小数点の結果の型は、既定では `double` です。 使用可能な型については、「[\<random>](../standard-library/random.md)」を参照してください。  
  
*URNG* Uniform Random Number Generator エンジン。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="remarks"></a>コメント  
このテンプレート クラスは、ガンマ分布に従って分布した、ユーザー指定の浮動小数点型の値または型 `double` の値 (指定がない場合) を生成する分布を表します。 次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[gamma_distribution](#gamma_distribution)|`gamma_distribution::alpha`|`gamma_distribution::param`|  
|`gamma_distribution::operator()`|`gamma_distribution::beta`|[param_type](#param_type)|  
  
プロパティ関数 `alpha()` と `beta()` はそれぞれ、格納されている分布パラメーター *alpha* と *beta* の値を返します。  
  
プロパティ メンバー `param()` は、格納されている分布パラメーター パッケージ `param_type` を設定または返します。  

メンバー関数の `min()` と `max()` はそれぞれ、考えられる結果の最小値と最大値を返します。  
  
`reset()` メンバー関数は、次回 `operator()` を呼び出したときに、その結果が、その前にエンジンから取得された値に左右されないようにするため、キャッシュされている値をすべて破棄します。  
  
`operator()` メンバー関数は、現在のパラメーター パッケージと指定したパラメーター パッケージのいずれかから、URNG エンジンに基づいて次に生成された値を返します。
  
分布クラスとそのメンバーの詳細については、「[\<random>](../standard-library/random.md)」を参照してください。  
  
ガンマ分布の詳細については、Wolfram MathWorld の記事「[ガンマ分布](http://go.microsoft.com/fwlink/LinkId=401111)」を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::gamma_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "alpha() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.alpha() << std::endl;  
    std::cout << "beta() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.beta() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
alpha() == 1.0000000000  
beta() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.0936880533  
    2: 0.1225944894  
    3: 0.6443593183  
    4: 0.6551171649  
    5: 0.7313457551  
    6: 0.7313557977  
    7: 0.7590097389  
    8: 1.4466885214  
    9: 1.6434088411  
    10: 2.1201210996  
```  
  
## <a name="requirements"></a>要件  
**ヘッダー:** \<random>  
  
**名前空間:** std  
  
##  <a name="gamma_distribution"></a>  gamma_distribution::gamma_distribution  
分布を作成します。  
  
```  
explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
explicit gamma_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>パラメーター  
*alpha*  
`alpha` 分布パラメーター。  
  
*beta*  
`beta` 分布パラメーター。  
  
*parm*  
分布の作成に使用されるパラメーターの構造体。  
  
### <a name="remarks"></a>コメント  
**前提条件:** `0.0 < alpha` および `0.0 < beta`  
  
1 つ目のコンストラクターは、格納されている値 `alpha` と `beta` にそれぞれ *alpha* と *beta* の値を保持するオブジェクトを作成します。  
  
2 つ目のコンストラクターは、格納パラメーターが *parm* から初期化されるオブジェクトを作成します。 `param()` メンバー関数を呼び出すと、既存の分布の現在のパラメーターを取得および設定できます。  
  
##  <a name="param_type"></a>  gamma_distribution::param_type  
分布のパラメーターを格納します。  
  
```cpp   
struct param_type {  
   typedef gamma_distribution<result_type> distribution_type;  
   param_type(result_type alpha = 1.0, result_type beta 1.0);
   result_type alpha() const;
   result_type beta() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
### <a name="parameters"></a>パラメーター  
*alpha*  
`alpha` 分布パラメーター。  
  
*beta*  
`beta` 分布パラメーター。  
  
*right*  
これと比較する `param_type` インスタンス。  
  
### <a name="remarks"></a>コメント  
**前提条件:** `0.0 < alpha` および `0.0 < beta`  
  
この構造体は、インスタンス化時に分布のクラス コンストラクターに渡したり、`param()` メンバー関数に渡して、既存の分布の格納されているパラメーターを設定したり、`operator()` に渡して、格納されているパラメーターの代わりに使用したりすることができます。  
  
## <a name="see-also"></a>関連項目  
[\<random>](../standard-library/random.md)



