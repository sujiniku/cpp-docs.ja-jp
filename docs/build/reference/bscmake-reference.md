---
title: BSCMAKE リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de8e71a448c71fd18ba9cba99cb9b7347598489c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="bscmake-reference"></a>BSCMAKE リファレンス
> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。  
  
 Microsoft Browse Information Maintenance Utility (BSCMAKE.EXE) は、コンパイル時に作成された .sbr ファイルから、ブラウザー情報ファイル (.bsc) を作成します。 特定のサード パーティ製ツールでは、コード分析は .bsc ファイルを使用します。 
  
 プログラムをビルドするときに、BSCMAKE を使用してファイルをビルドすれば、プログラムのブラウザー情報ファイルを自動的に作成できます。 Visual C++ 開発環境でブラウザー情報ファイルを作成する場合は、BSCMAKE の実行方法を知る必要はありません。 ただし、このトピックを読めば、利用可能な選択肢を理解することができます。  
  
 開発環境の外部でプログラムをビルドする場合は、その環境で確認することができるカスタム .bsc ファイルを作成できます。 コンパイル中に作成した .sbr ファイル上で BSCMAKE を実行します。  
  
> [!NOTE]
>  このツールは、Visual Studio 開発者コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 ここでは、次のトピックについて説明します。  
  
-   [ブラウザー情報ファイルのビルド : 概要](../../build/reference/building-browse-information-files-overview.md)  
  
-   [.Bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [BSCMAKE コマンドライン](../../build/reference/bscmake-command-line.md)  
  
-   [BSCMAKE コマンド ファイル](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [BSCMAKE オプション](../../build/reference/bscmake-options.md)  
  
-   [BSCMAKE 終了コード](../../build/reference/bscmake-exit-codes.md)  
  
## <a name="see-also"></a>関連項目  
 [C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)