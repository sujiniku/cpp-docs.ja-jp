---
title: CWindowDC クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7867f35a66abf0f5a33ecd411b81111e84e3800f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cwindowdc-class"></a>CWindowDC クラス
`CDC`の派生クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` オブジェクトを構築します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|`HWND` の割り当て先である `CWindowDC`。|  
  
## <a name="remarks"></a>コメント  
 Windows の関数を呼び出す[GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)構築時と[ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx)破棄時にします。 つまり、`CWindowDC`オブジェクト アクセスの全画面領域、 [CWnd](../../mfc/reference/cwnd-class.md) (クライアントおよび非クライアント領域の両方)。  
  
 使用する方法についての`CWindowDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>要件  
 ヘッダー: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 構築、 `CWindowDC` 、画面全体 (クライアントと非クライアントの両方) の領域にアクセスするオブジェクト、`CWnd`によって指されるオブジェクト`pWnd`です。  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、Windows の関数を呼び出します。 [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947)です。  
  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows`GetWindowDC`呼び出しは失敗します。 デバイス コンテキストは、Windows が既に割り当てられているすべての利用可能なデバイス コンテキストの場合に使用できない可能性があります。 アプリケーションは、共通のディスプレイ コンテキストで、Windows の特定の時点で利用可能なの 5 つに対して競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd  
 `HWND`の`CWnd`ポインターが構築するために使用される、`CWindowDC`オブジェクト。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd` 保護された型の変数は、`HWND`です。  
  
### <a name="example"></a>例  
  例を参照して[CWindowDC::CWindowDC](#cwindowdc)です。  
  
## <a name="see-also"></a>関連項目  
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)
