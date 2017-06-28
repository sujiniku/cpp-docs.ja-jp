---
title: "入れ子にされたクラス宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 宣言"
  - "宣言, class"
  - "宣言, 入れ子になったクラス"
  - "宣言 (クラスの)"
  - "入れ子になったクラス"
  - "入れ子になったクラス, 宣言"
ms.assetid: c02e471d-b7f9-41b8-8ef6-2323f006dbd5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 入れ子にされたクラス宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスのスコープ内で別のクラスを宣言できます。  このようなクラスを "入れ子のクラス" といいます。 入れ子のクラスには外側のクラスのスコープが適用され、そのスコープ内で使用できます。  すぐ外側のスコープ以外のスコープから入れ子のクラスを参照するには、完全修飾名を使用する必要があります。  
  
 次に、入れ子のクラスを宣言する方法を示します。  
  
```  
// nested_class_declarations.cpp  
class BufferedIO  
{  
public:  
   enum IOError { None, Access, General };  
  
   // Declare nested class BufferedInput.  
   class BufferedInput  
   {  
   public:  
      int read();  
      int good()  
      {  
         return _inputerror == None;  
      }  
   private:  
       IOError _inputerror;  
   };  
  
   // Declare nested class BufferedOutput.  
   class BufferedOutput  
   {  
      // Member list  
   };  
};  
  
int main()  
{  
}  
```  
  
 `BufferedIO::BufferedInput` と `BufferedIO::BufferedOutput` は `BufferedIO` 内で宣言されています。  `BufferedIO` クラスのスコープ外ではこれらのクラス名が表示されません。  ただし、`BufferedIO` 型のオブジェクトには、`BufferedInput` 型または `BufferedOutput` 型のオブジェクトが含まれません。  
  
 入れ子になったクラスは、外側のクラスからのみ、名前、型名、静的メンバー名、および列挙子を直接使用できます。  他のクラス メンバーの名前を使用するには、ポインター、参照、またはオブジェクト名を使用する必要があります。  
  
 前の `BufferedIO` 例では、列挙体 `IOError` には、入れ子になったクラス `BufferedIO::BufferedInput` または `BufferedIO::BufferedOutput` のメンバー関数によって直接アクセスできます \(`good` 関数を参照\)。  
  
> [!NOTE]
>  入れ子のクラスは、クラス スコープ内の型のみ宣言します。  入れ子のクラスに含まれるオブジェクトは作成されません。  前の例では、入れ子になった 2 つのクラスを宣言していますが、これらのクラス型のオブジェクトは宣言していません。  
  
 入れ子になったクラス宣言のスコープの参照可能範囲の例外は、型名が事前宣言と共に宣言されている場合です。  この場合、事前宣言によって宣言されたクラス名は、それを囲んでいるクラス \(そのスコープは、最も小さく囲んでいる非クラス スコープと定義される\) の外部から参照可能です。  例:  
  
```  
// nested_class_declarations_2.cpp  
class C  
{  
public:  
    typedef class U u_t; // class U visible outside class C scope  
    typedef class V {} v_t; // class V not visible outside class C  
};  
  
int main()  
{  
    // okay, forward declaration used above so file scope is used  
    U* pu;  
  
    // error, type name only exists in class C scope  
    u_t* pu2; // C2065  
  
    // error, class defined above so class C scope  
    V* pv; // C2065  
  
    // okay, fully qualified name  
    C::V* pv2;  
}  
```  
  
## 入れ子にされたクラスのアクセス特権  
 別のクラス内でクラスを入れ子にしても、入れ子になったクラスのメンバー関数への特別なアクセス特権は与えられません。  同様に、外側のクラスのメンバー関数にも、入れ子になったクラスのメンバーへの特別なアクセス特権は与えられません。  
  
## 入れ子にされたクラスのメンバー関数  
 入れ子のクラスで宣言されたメンバー関数はファイル スコープで定義できます。  前の例は、次のように記述することができます。  
  
```  
// member_functions_in_nested_classes.cpp  
class BufferedIO  
{  
public:  
    enum IOError { None, Access, General };  
    class BufferedInput  
    {  
    public:  
        int read(); // Declare but do not define member  
        int good(); //  functions read and good.  
    private:  
        IOError _inputerror;  
    };  
  
    class BufferedOutput  
    {  
        // Member list.  
    };  
};  
// Define member functions read and good in  
//  file scope.  
int BufferedIO::BufferedInput::read()  
{  
   return(1);  
}  
  
int BufferedIO::BufferedInput::good()  
{  
    return _inputerror == None;  
}  
int main()  
{  
}  
```  
  
 前の例では、関数名の宣言に、*qualified\-type\-name* 構文が使用されます。  宣言:  
  
```  
BufferedIO::BufferedInput::read()  
```  
  
 "`read` クラスのスコープ内の `BufferedInput` クラスのメンバーである `BufferedIO` 関数" という意味です。 この宣言は *qualified\-type\-name* 構文を使用するため、次の形式の構造が可能です。  
  
```  
typedef BufferedIO::BufferedInput BIO_INPUT;  
  
int BIO_INPUT::read()  
```  
  
 前の宣言は、前の例と等価ですが、クラス名の代わりに `typedef` 名を使用します。  
  
## 入れ子にされたクラスのフレンド関数  
 入れ子になったクラスで宣言された friend 関数は、それを囲んでいるクラスではなく、入れ子になったクラスのスコープ内にあると見なされます。  したがって、フレンド関数は、外側のクラスのメンバー関数に対する特別なアクセス特権を取得しません。  フレンド関数がファイルのスコープで定義されている場合に、そのフレンド関数の入れ子になったクラスで宣言されている名前を使用するには、次のように修飾型名を使用します。  
  
```  
// friend_functions_and_nested_classes.cpp  
  
#include <string.h>  
  
enum  
{  
    sizeOfMessage = 255  
};  
  
char *rgszMessage[sizeOfMessage];  
  
class BufferedIO  
{  
public:  
    class BufferedInput  
    {  
    public:  
        friend int GetExtendedErrorStatus();  
        static char *message;  
        static int  messageSize;  
        int iMsgNo;  
   };  
};  
  
char *BufferedIO::BufferedInput::message;  
int BufferedIO::BufferedInput::messageSize;  
  
int GetExtendedErrorStatus()  
{  
    int iMsgNo = 1; // assign arbitrary value as message number  
  
    strcpy_s( BufferedIO::BufferedInput::message,  
              BufferedIO::BufferedInput::messageSize,  
              rgszMessage[iMsgNo] );  
  
    return iMsgNo;  
}  
  
int main()  
{  
}  
```  
  
 次のコードは、フレンド関数として宣言された `GetExtendedErrorStatus` 関数を示します。  この関数はファイル スコープで定義されており、メッセージは、静的配列からクラス メンバーにコピーされます。  より適した `GetExtendedErrorStatus` の実装では次のように宣言します。  
  
```  
int GetExtendedErrorStatus( char *message )  
```  
  
 前のインターフェイスを使用すると、いくつかのクラスは、エラー メッセージのコピー先のメモリ位置を渡すことによって、この関数のサービスを使用できます。  
  
## 参照  
 [クラスと構造体](../Topic/Classes%20and%20Structs%20\(C++\).md)