---
title: "student_t_distribution クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- student_t_distribution
- std::student_t_distribution
- random/std::student_t_distribution
- random/std::student_t_distribution::result_type
- random/std::student_t_distribution::reset
- random/std::student_t_distribution::operator()
- random/std::student_t_distribution::n
- random/std::student_t_distribution::param
- random/std::student_t_distribution::min
- random/std::student_t_distribution::max
dev_langs:
- C++
helpviewer_keywords:
- student_t_distribution class
ms.assetid: 87b48127-9311-4d07-95df-833ed46bf0b1
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 61781e74ed9cc5424255b8697800000f8de5eb30
ms.lasthandoff: 02/24/2017

---
# <a name="studenttdistribution-class"></a>student_t_distribution クラス
スチューデントの *t* 分布を生成します。  
  
## <a name="syntax"></a>構文  
```  
template<class RealType = double>
class student_t_distribution {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   explicit student_t_distribution(result_type n = 1.0);
   explicit student_t_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type n() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
```  
#### <a name="parameters"></a>パラメーター  
*RealType*  
 浮動小数点の結果の型は、既定では `double` です。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、スチューデントの *t* 分布に従って分布した、ユーザー指定の整数型の値または型 `double` の値 (指定がない場合) を生成する分布を表します。 次の表は、個々のメンバーに関する記事にリンクしています。  
  
||||  
|-|-|-|  
|[student_t_distribution::student_t_distribution](#student_t_distribution__student_t_distribution)|`student_t_distribution::n`|`student_t_distribution::param`|  
|`student_t_distribution::operator()`||[student_t_distribution::param_type](#student_t_distribution__param_type)|  
  
 プロパティ関数 `n()` は、格納されている分布パラメーター `n` の値を返します。  
  
 分布クラスとそのメンバーの詳細については、「[\<random>](../standard-library/random.md)」を参照してください。  
  
 スチューデントの *t* 分布の詳細については、Wolfram MathWorld の記事「[Students t-Distribution](http://go.microsoft.com/fwlink/LinkId=401094)」(スチューデントの t 分布) を参照してください。  
  
## <a name="example"></a>例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double n, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::student_t_distribution<> distr(n);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "n() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.n() << std::endl;  
  
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
    double n_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'n' distribution parameter (must be greater than zero): ";  
    std::cin >> n_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(n_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
n() == 1.0000000000  
Distribution for 10 samples:  
    1: -1.3084956212  
    2: -1.0899518684  
    3: -0.9568771388  
    4: -0.9372088821  
    5: -0.7381334669  
    6: -0.2488074854  
    7: -0.2028714601  
    8: 1.4013074495  
    9: 5.3244792236  
    10: 92.7084335614  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<random>  
  
 **名前空間:** std  
  
##  <a name="a-namestudenttdistributionstudenttdistributiona--studenttdistributionstudenttdistribution"></a><a name="student_t_distribution__student_t_distribution"></a>  student_t_distribution::student_t_distribution  
 分布を作成します。  
  
```  
explicit student_t_distribution(RealType n = 1.0);
explicit student_t_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>パラメーター  
*n*  
 `n` 分布パラメーター。  
  
*parm*  
 分布の作成に使用されるパラメーター パッケージ。  
  
### <a name="remarks"></a>コメント  
 **前提条件:** `0.0 < n`  
  
 1 番目のコンストラクターは、格納されている `n` の値が *n* の値を保持するオブジェクトを作成します。  
  
 2 番目のコンストラクターは、格納されているパラメーターが *parm* から初期化されるオブジェクトを作成します。 `param()` メンバー関数を呼び出すと、既存の分布の現在のパラメーターを取得および設定できます。  
  
##  <a name="a-namestudenttdistributionparamtypea--studenttdistributionparamtype"></a><a name="student_t_distribution__param_type"></a>  student_t_distribution::param_type  
 分布のすべてのパラメーターを格納します。  
```cpp    
struct param_type {  
   typedef student_t_distribution<result_type> distribution_type;  
   param_type(result_type n = 1.0);
   result_type n() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>パラメーター  
*n*  
`n` 分布パラメーター。  
  
*right*  
このオブジェクトと比較する `param_type` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 **前提条件:** `0.0 < n`  
  
 この構造体は、インスタンス化時に分布のクラス コンストラクターに渡したり、`param()` メンバー関数に渡して、既存の分布の格納されているパラメーターを設定したり、`operator()` に渡して、格納されているパラメーターの代わりに使用したりすることができます。  
  
## <a name="see-also"></a>関連項目  
 [\<random>](../standard-library/random.md)



