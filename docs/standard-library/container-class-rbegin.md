---
title: コンテナー クラス::rbegin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rbegin method
ms.assetid: c1f0d60c-93aa-4313-81b9-04e3f9c796c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d19e7016120d66ceb59b8d1c77620121fc569b1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="container-classrbegin"></a>コンテナー クラス::rbegin

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

被制御シーケンスの末尾の次の位置を指す反転反復子を返し、反転シーケンスの先頭を指定します。

## <a name="syntax"></a>構文

```cpp
const_reverse_iterator rbegin() const;


reverse_iterator rbegin();
```

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
