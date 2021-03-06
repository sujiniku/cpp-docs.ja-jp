---
title: メソッド追加ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding using wizards
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc2ebd18640f0ab778cb45252691e63206861d53
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="add-method-wizard"></a>メソッド追加ウィザード
このウィザードを使用すると、インターフェイスにメソッドを追加します。 によっては、プロジェクトの種類またはインターフェイス型、メソッドを追加するには、さまざまなオプションが表示されます。  
  
## <a name="names"></a>名前  
 **戻り値の型**  
 メソッドによって返されるデータ型。 `HRESULT` 標準的なエラーを返す方法を提供するためのすべてのインターフェイスの種類を勧めします。  
  
|インターフェイスの型|説明|  
|--------------------|-----------------|  
|デュアル インターフェイス|`HRESULT`。 変更できません。|  
|カスタム インターフェイス|`HRESULT`。 変更できません。|  
|ローカル カスタム インターフェイス|戻り値の型を提供または一覧から選択します。|  
|ディスパッチ インターフェイス|戻り値の型を提供または一覧から選択します。|  
|MFC ActiveX コントロールのディスパッチ インターフェイス|ストック メソッドを実装する場合、戻り値の型は、適切な値に設定されているし、変更不可能なです。 メソッドを選択する場合、**メソッド名**を一覧表示し、をクリックして**カスタム****メソッドの型を選択して**、戻り値の型を一覧から選択します。|  
  
 **メソッド名**  
 メソッドの名前を設定します。  
  
|インターフェイスの型|説明|  
|--------------------|-----------------|  
|ATL デュアル インターフェイス、カスタム インターフェイス、およびローカル カスタム インターフェイス|独自のメソッド名を提供します。|  
|MFC ディスパッチ インターフェイス|独自のメソッド名を指定または推奨されるメソッドの名前を一覧から選択します。 適切な値が表示されます、リストから名前を選択した場合、**型を返す**ボックスは変更できません。|  
|MFC ActiveX コントロールのディスパッチ インターフェイス|独自の入力やストック メソッドのいずれかを選択[DoClick](../mfc/reference/colecontrol-class.md#doclick)と[更新](../mfc/reference/colecontrol-class.md#refresh)です。 参照してください[MFC ActiveX コントロール: ストック メソッドの追加](../mfc/mfc-activex-controls-adding-stock-methods.md)詳細についてはします。|  
  
 **メソッドの型**  
 MFC ActiveX コントロールに対してのみ使用できます。 メソッド名を指定する場合、**メソッド名**ボックスで、一覧からメソッドを選択するではなくこのボックスは使用できません。  
  
 内のメソッドのいずれかを選択した場合、**メソッド名**一覧で、ストックの実装では、またはカスタムの実装のいずれかを選択します。  
  
|メソッドの型|説明|  
|-----------------|-----------------|  
|**ストック**|これが既定値です。 選択したメソッドのストックの実装を挿入、**メソッド名**ボックスの一覧です。 **型を返す**を選択する場合は、変更不可能な**Stock**です。|  
|**カスタム**|選択したメソッドのスタブ実装を挿入、**メソッド名**ボックスの一覧です。 カスタム メソッドの種類では、戻り値の型を提供できます。 またはから選択することができます、**型を返す**ボックスの一覧です。|  
  
 **内部名**  
 MFC ディスパッチ インターフェイスに追加したカスタム メソッドのみで使用できます。 ディスパッチ マップ、ヘッダー (.h) ファイル、および実装 (.cpp) ファイルで使用される名前を設定します。 既定では、この名前は、同じ**メソッド名**です。 MFC ディスパッチ インターフェイスを使用している場合、または MFC ActiveX コントロールのディスパッチ インターフェイスにカスタム メソッドを追加する場合、メソッド名を変更することができます。  
  
|インターフェイスの型|説明|  
|--------------------|-----------------|  
|ATL デュアル インターフェイス、カスタム インターフェイス、およびローカル カスタム インターフェイス|使用できません|  
|MFC ディスパッチ インターフェイス|既定では、メソッド名を設定します。 内部名を編集することができます。|  
|MFC ActiveX コントロールのディスパッチ インターフェイス|のみカスタム メソッドの内部名を設定することができます。 ストック メソッドは、内部名を使用しません。|  
  
 **パラメーター属性**  
 指定されたパラメーターの追加の属性を設定**パラメーター名**です。  
  
|パラメーター属性|説明|許可されている組み合わせ|  
|-------------------------|-----------------|--------------------------|  
|**In**|呼び出されたプロシージャを呼び出し元のプロシージャからパラメーターが渡されることを示します。|**内部**のみ<br /><br /> **内部** と **アウト**|  
|**Out**|(サーバーからクライアントに) 呼び出し元のプロシージャに、ポインター パラメーターが呼び出されたプロシージャから返されたことを示します。|**out**のみ<br /><br /> **内部** と **アウト**<br /><br /> **out**と**retval**|  
|**戻り値**|パラメーターが、メンバーの戻り値を受け取ることを示します。|**retval**およびアウト|  
  
 **パラメーターの型**  
 パラメーターのデータ型を設定します。 一覧から、種類を選択します。  
  
 **パラメーター名**  
 メソッドを通過するパラメーターの名前を設定します。 クリックする必要があります、名前を入力すると、**追加**メソッドを通じて渡されるパラメーターの一覧に追加します。 ウィザードは、パラメーター属性 (ATL のみ) を無視する場合は、パラメーター名を指定しないと、または**パラメーターの型**選択します。  
  
 クリックすると**追加**、パラメーター名**パラメーター リスト**です。  
  
 **注**パラメーター名を指定し、をクリックした場合**完了**をクリックする前に**追加**メソッドにパラメーターを追加できません。 メソッドを検索し、パラメーターを手動で挿入する必要があります。  
  
 **[追加]**  
 指定したパラメーターを追加**パラメーター名**、およびその型とパラメーターの属性に**パラメーター リスト**です。 クリックする必要があります**追加**一覧にパラメーターを追加します。  
  
 **削除**  
 選択したパラメーターを削除**パラメーター リスト**一覧からです。  
  
 **パラメーター リスト**  
 すべてのパラメーターと、修飾子、現在、メソッドの追加の種類を表示します。 パラメーターを追加すると、ウィザードは更新**パラメーター リスト**修飾子の種類と、各パラメーターを表示します。  
  
## <a name="see-also"></a>関連項目  
 [メソッドの追加](../ide/adding-a-method-visual-cpp.md)   
 [[IDL 属性] (メソッド追加ウィザード)](../ide/idl-attributes-add-method-wizard.md)