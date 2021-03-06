---
title: 入力ストリーム | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3dff2e0bb0ee070b8b90ca3896d7bf8114ca918
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="input-streams"></a>入力ストリーム

入力ストリーム オブジェクトは、バイトのソースです。 最も重要な 3 つの入力ストリーム クラスは、[istream](../standard-library/basic-istream-class.md)、[ifstream](../standard-library/basic-ifstream-class.md)、および [istringstream](../standard-library/basic-istringstream-class.md) です。

`istream` クラスは、順次テキスト モードの入力に対して最も効果的です。 バッファーされた操作またはバッファーされてない操作のクラス `istream` のオブジェクトを構成できます。 基本クラスのすべての機能 `ios` は、`istream` に含まれています。 `istream` クラスからオブジェクトを構築することはほとんどありません。 代わりに、実際には一般的にクラス [ostream](../standard-library/basic-ostream-class.md) のオブジェクトである定義済みの `cin` オブジェクトを使用します。 場合によっては、プログラムの起動後に `cin` を他のストリーム オブジェクトに割り当てることができます。

`ifstream` クラスは、ディスク ファイルの入力をサポートしています。 入力専用のディスク ファイルが必要な場合は、`ifstream` クラスのオブジェクトを構築します。 バイナリまたはテキスト モードのデータを指定できます。 コンストラクターでファイル名を指定すると、オブジェクトの構築時にそのファイルが自動的に開きます。 あるいは、既定のコンストラクターを起動した後に `open` 関数を使用します。 多くの書式オプションとそのメンバー関数が `ifstream` オブジェクトに適用されます。 基本クラス `ios` および `istream` のすべての機能は、`ifstream` に含まれています。

ライブラリ関数 `sscanf_s` と同様に、`istringstream` クラスはメモリ内の文字列からの入力をサポートしています。 null 終端文字がある文字配列からデータを抽出するには、文字列を割り当てて初期化し、クラス `istringstream` のオブジェクトを構築します。

## <a name="in-this-section"></a>このセクションの内容

[入力ストリーム オブジェクトの構築](../standard-library/constructing-input-stream-objects.md)

[抽出演算子の使用](../standard-library/using-extraction-operators.md)

[抽出エラーのテスト](../standard-library/testing-for-extraction-errors.md)

[入力ストリーム マニピュレーター](../standard-library/input-stream-manipulators.md)

[入力ストリームのメンバー関数](../standard-library/input-stream-member-functions.md)

[独自クラスのための >> 演算子のオーバーロード](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>関連項目

[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
