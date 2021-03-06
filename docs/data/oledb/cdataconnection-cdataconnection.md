---
title: Cdataconnection::cdataconnection |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 267341f88886f3ff94a6b828034e8acbaa2dc0c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
インスタンスを作成し、初期化、`CDataConnection`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ds`  
 [in]既存のデータ接続への参照。  
  
## <a name="remarks"></a>コメント  
 最初のオーバーライドが新たに作成`CDataConnection`既定の設定を持つオブジェクト。  
  
 2 番目のオーバーライドが新たに作成`CDataConnection`設定を指定するデータ接続オブジェクトと等価のオブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)