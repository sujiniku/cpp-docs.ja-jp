---
title: typeid (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db1efac0a38aaa11238452e418277f78dbcd6d9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="typeid--c-component-extensions"></a>typeid (C++ コンポーネント拡張)
オブジェクトの型を示す値を取得します。  
  
> [!WARNING]
>  このトピックでは、typeid の C++ コンポーネント拡張バージョンを示します。 このキーワードの ISO C のバージョンを参照してください。 [typeid 演算子](../cpp/typeid-operator.md)です。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
  
### <a name="syntax"></a>構文  
  
```cpp  
T::typeid  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 型の名前。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 型の名前。  
  
### <a name="remarks"></a>コメント  
 C + + CX、typeid を返します、 [platform::type](../cppcx/platform-type-class.md)ランタイム型情報から構築します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **構文**  
  
```  
  
type::typeid  
```  
  
 **パラメーター**  
  
 *type*  
 System::Type オブジェクトに適用する型 (抽象宣言子) の名前。  
  
 **解説**  
  
 `typeid` を使用して、コンパイル時に型の <xref:System.Type> を取得します。  
  
 `typeid` の機能は、実行時に <xref:System.Type.GetType%2A> または <xref:System.Object.GetType%2A> を使用して型の System::Type を取得することに似ています。 ただし、typeid には型名をパラメーターとしてのみ指定できます。  型のインスタンスを使用して、その System::Type 名を取得するには、GetType を使用します。  
  
 `typeid` はコンパイル時に型名 (型) を評価できる必要がありますが、GetType は実行時に返す型を評価します。  
  
 `typeid` ネイティブ型の名前またはネイティブ型の名前です。 共通言語ランタイムの別名がかかることができます。参照してください[C++ ネイティブ型と等価な .NET Framework (C + + CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)詳細についてはします。  
  
 `typeid` ではネイティブ型も扱えますが、その場合でも System::Type を返します。  Type_info 構造体を取得する[typeid 演算子](../cpp/typeid-operator.md)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、typeid のキーワードと GetType() メンバーを比較します。  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **出力**  
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
  
```  
  
 **例**  
  
 次の例では、System::Type 型の変数を使用して型の属性を取得できることを示しています。  この例を見るとわかるように、一部の型では、`typeid` を使用するために typedef を作成する必要があります。  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **出力**  
  
```Output  
True  
  
in AtClass2 constructor  
  
in AtClass Type ^ constructor  
  
AtClass2  
  
System.AttributeUsageAttribute  
  
AtClass  
  
int::typeid != pointer_to_int::typeid, as expected  
  
int::typeid == handle_to_int::typeid, as expected  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)