---
title: プロパティ (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- property_cpp
- property
dev_langs:
- C++
helpviewer_keywords:
- property keyword [C++]
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b763131fe91e2df2385f2c06bcba8bc759d695a1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="property--c-component-extensions"></a>プロパティ (C++ コンポーネント拡張)
宣言、*プロパティ*が動作し、データ メンバーや配列要素のようにアクセスできるメンバー関数。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 次のいずれかの種類のプロパティを宣言できます。  
  
 *単純なプロパティ*  
 既定では、作成、 *set アクセサー*プロパティ値を割り当てる、 *get アクセサー*プロパティ値、およびプロパティ値を含むプライベート データのコンパイラによって生成されたメンバーを取得します。  
  
 *プロパティ ブロック*  
 これを使用して、ユーザー定義の get アクセサーまたは set アクセサーを作成します。 get アクセサーおよび set アクセサーの両方が定義されている場合、プロパティの読み取りと書き込みを実行できます。get アクセサーのみが定義されている場合、プロパティは読み取り専用です。set アクセサーのみが定義されている場合、プロパティは書き込み専用です。  
  
 プロパティ値を格納するデータ メンバーを明示的に宣言する必要があります。  
  
 *インデックス付きプロパティ*  
 1 つ以上のインデックスで指定されるプロパティの値を取得し設定するために使用できるプロパティ ブロック。  
  
 いずれかのあるインデックス付きプロパティを作成すると、ユーザー定義のプロパティ名または*既定*プロパティ名。 既定のインデックス プロパティの名前は、プロパティが定義されているクラスの名前です。 既定のプロパティを宣言するには、プロパティ名ではなく `default` キーワードを指定します。  
  
 プロパティ値を格納するデータ メンバーを明示的に宣言する必要があります。 通常、インデックス プロパティの場合、データ メンバーは配列またはコレクションになります。  
  
### <a name="syntax"></a>構文  
  
```cpp  
property type property_name;

property type property_name { 
   access-modifier type get() inheritance-modifier {property_body}; 
   access-modifier void set(type value) inheritance-modifier {property_body};
} 

property type property_name[index_list] { 
   access-modifier type get(index_list) inheritance-modifier {property_body}; 
   access-modifier void set(index_list, value) inheritance-modifier {property_body};
} 

property type default[index_list] { 
   access-modifier type get(index_list) inheritance-modifier {property_body};
   access-modifier void set(index_list, value) inheritance-modifier {property_body};
}  
```  
  
### <a name="parameters"></a>パラメーター  
 `type`  
 プロパティ値のデータ型、つまりプロパティ自体です。  
  
 `property_name`  
 プロパティの名前。  
  
 `access-modifier`  
 アクセス修飾子。 有効な修飾子は `static` と `virtual`です。  
  
 get アクセサーまたは set アクセサーの `virtual` 修飾子が一致する必要はありませんが、`static` 修飾子は一致する必要があります。  
  
 `inheritance-modifier`  
 継承修飾子。 有効な修飾子は `abstract` と `sealed`です。  
  
 `index_list`  
 1 つ以上のインデックスのコンマ区切りのリスト。 各インデックスは、インデックスの型と、プロパティ メソッドの本文で使用できる識別子 (省略可能) で構成されます。  
  
 `value`  
 set 操作でプロパティに代入される値、または get 操作で取得される値。  
  
 `property_body`  
 set アクセサーまたは get アクセサーのプロパティ メソッドの本体。 `property_body` では `index_list` を、基になるプロパティ データ メンバーにアクセスするために使用するか、ユーザー定義処理のパラメーターとして使用できます。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 詳細については、次を参照してください。[プロパティ (C + + CX)](http://msdn.microsoft.com/library/windows/apps/hh755807.aspx)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **構文**  
  
```cpp  
modifier property type property_name;

modifier property type property_name {
   modifier void set(type);
   modifier type get();
}
modifier property type property_name[index-list, value] {
   modifier void set(index-list, value);
   modifier type get(index-list);

modifier property type default[index];
}  
```  
  
 **パラメーター**  
  
 *修飾子*  
 プロパティの宣言または get/set アクセサー メソッドで使用できる修飾子。 有効な値は、`static` と `virtual` です。  
  
 *type*  
 プロパティで表される値の型。  
  
 *property_name*  
 raise メソッドのパラメーター。デリゲートのシグネチャと一致する必要があります。  
  
 *index_list*  
 1 つ以上のインデックスのリスト (コンマ区切り)。角かっこ (添字演算子 []) で囲んで指定します。 各インデックスについて型を指定し、さらに必要に応じてプロパティ メソッドの本文で使用できる識別子も指定します。  
  
 **解説**  
  
 最初の構文例に示す、*単純プロパティ*、両方を暗黙的に宣言する、`set`と`get`メソッドです。 コンパイラは自動的にプロパティの値を格納するためのプライベート フィールドを作成します。  
  
 2 番目の構文例に示す、*プロパティ ブロック*、両方を明示的に宣言する、`set`と`get`メソッドです。  
  
 3 番目の構文例は、顧客定義を示しています。*インデックス プロパティ*です。 インデックス プロパティは、設定または取得する値だけでなくパラメーターも受け取ります。 プロパティに名前を指定する必要があります。 シンプル プロパティとは異なり、インデックス プロパティの `set` メソッドと `get` メソッドは明示的に定義する必要があり、さらにプロパティの名前も指定する必要があります  
  
 4 番目の構文例に示す、*既定*を型のインスタンスを配列に似たアクセスを提供するプロパティです。 `default` キーワードは、既定のプロパティを指定する場合にのみ使用されます。 既定のプロパティの名前は、プロパティが定義されている型の名前です。  
  
 `property` キーワードは、クラス、インターフェイス、または値の型で使用できます。 プロパティには get 関数 (読み取り専用)、set 関数 (書き込み専用)、またはその両方 (読み取り/書き込み) を定義できます。  
  
 プロパティ名は、それ自身が含まれるマネージ クラスの名前と同じにすることはできません。 getter 関数の戻り値の型は、対応する setter 関数の最後のパラメーターの型と一致する必要があります。  
  
 クライアント コードに対しては、プロパティは通常のデータ メンバーと同じように扱うことができ、データ メンバーと同じ構文を使用して書き込みまたは読み取りを実行できます。  
  
 get メソッドと set メソッドの `virtual` 修飾子が一致する必要はありません。  
  
 get メソッドと set メソッドのアクセシビリティが異なっていても問題ありません。  
  
 プロパティ メソッドの定義は、通常のメソッドと同様に、クラスの本文の外でも表示できます。  
  
 Get メソッドとプロパティの set メソッドが一致する必要、**静的**修飾子です。  
  
 プロパティの get メソッドと set メソッドが次の説明に適合している場合、そのプロパティはスカラーです。  
  
-   get メソッドにはパラメーターがなく、戻り値の型は `T` です。  
  
-   Set メソッドが型のパラメーターを持つ`T`、型を返すと**void**です。  
  
 同じ ID のスコープ内では、1 つのスカラー プロパティしか宣言できません。 スカラー プロパティはオーバーロードできません。  
  
 プロパティ データ メンバーを宣言すると、コンパイラはクラスにデータ メンバーを挿入します。このデータ メンバーは "バッキング ストア" とも呼ばれます。 ただし、このデータ メンバーの名前は、外側のクラスの実際のデータ メンバーであるかのように、ソース内のメンバーを参照できないような形式になっています。 型のメタデータを表示し、プロパティのバッキング ストアに対してコンパイラが生成した名前を確認するには、ildasm.exe を使用します。  
  
 プロパティ ブロック内のアクセサー メソッドについては、異なるアクセシビリティが許容されます。  つまり、set メソッドをパブリックに、get メソッドをプライベートにすることができます。  ただし、アクセサー メソッドのアクセシビリティが、プロパティ自体の宣言でのアクセシビリティよりも制限が少ない場合、エラーになります。  
  
 `property` は状況依存のキーワードです。  詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。  
  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 次の例は、プロパティのデータ メンバーとプロパティ ブロックの宣言方法と使用方法を示しています。  これにより、プロパティ アクセサーがクラスから定義できることもわかります。  
  
```  
// mcppv2_property.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   int MyInt;  
public:  
  
   // property data member  
   property String ^ Simple_Property;  
  
   // property block  
   property int Property_Block {  
  
      int get();  
  
      void set(int value) {  
         MyInt = value;  
      }  
   }  
};  
  
int C::Property_Block::get() {  
   return MyInt;  
}  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->Simple_Property = "test";  
   Console::WriteLine(MyC->Simple_Property);  
  
   MyC->Property_Block = 21;  
   Console::WriteLine(MyC->Property_Block);  
}  
```  
  
 **出力**  
  
```Output  
test  
  
21  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)