---
title: 名前の変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a064527f6afcbf91be3fb4e51180be647c1f506
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="rename"></a>名前の変更
**概要:** フィールド、ローカル変数、メソッド、名前空間、プロパティ、型などのコード シンボルの識別子の名前を変更します。

**タイミング:** すべてのインスタンスを検索して新しい名前をコピー/貼り付けすることなく、安全に名前を変更したいとき。  

**理由:** プロジェクト全体で新しい名前をコピーおよび貼り付けることは、エラーにつながる可能性があるため。  このリファクタリング ツールでは、正確に名前変更操作が実行されます。

**方法:**

1. 名前を変更する項目を強調表示するか、項目の内側にテキスト カーソルを置きます。

   ![強調表示されたコード](images/rename_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + R** キーを押し、次に **Ctrl + R** キーを押します。  選ばれているプロファイルによってキーボード ショートカットが異なる場合があることに注意してください。
   * **マウス**
     * **[編集] > [リファクター] > [名前の変更]** の順に選択します。
     * コードを右クリックし **[名前の変更]** を選択します。

1. **の名前を変更**、ポップアップ ウィンドウをクリックして、選択した項目の新しい名前を入力してください、**プレビュー**ボタンをクリックします。  変更、**検索スコープ**幅や名前の変更の範囲を絞り込む必要がある場合。

   ![ダイアログの名前を変更します。](images/rename_dialog.png)

   > [!TIP]
   > プレビューをスキップするには、チェック、**加えた変更参照がすべて確認された場合のスキップ プレビュー**オプション。

1. ときに、**プレビューの変更 - 名前の変更**ウィンドウが表示されたら、要求している変更が適切に適用されていることを確認してください。  有効または無効のいずれかの項目の名前を変更するウィンドウの上半分にチェック ボックスを使用します。

   ![プレビューの名前を変更します。](images/rename_preview.png)

1. すべて見栄えの良いをクリックして、**適用**ボタンをクリックし、項目の名前が、ソース コードに変更されます。
