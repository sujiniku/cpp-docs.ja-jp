---
title: "CHeaderCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class
- Windows common controls [C++], CHeaderCtrl
- header controls, CHeaderCtrl class
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab3cef5d72bad004832cb85ca4b1b3604eb3a18c
ms.lasthandoff: 02/24/2017

---
# <a name="cheaderctrl-class"></a>CHeaderCtrl クラス
Windows コモン ヘッダー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|`CHeaderCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|ヘッダー コントロールのすべてのフィルターをクリアします。|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|ヘッダー コントロールのフィルターをクリアします。|  
|[CHeaderCtrl::Create](#create)|ヘッダー コントロールを作成し、それをアタッチ、`CHeaderCtrl`オブジェクトです。|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|ヘッダー コントロール内のアイテムの画像の透明なバージョンを作成します。|  
|[CHeaderCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してヘッダー コントロールを作成し、それにアタッチ、`CListCtrl`オブジェクトです。|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|ヘッダー コントロールから項目を削除します。|  
|[CHeaderCtrl::DrawItem](#drawitem)|ヘッダー コントロールの指定した項目を描画します。|  
|[CHeaderCtrl::EditFilter](#editfilter)|ヘッダー コントロールの指定したフィルターの編集を開始します。|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|ヘッダー コントロールのビットマップの余白の幅を取得します。|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|フォーカスがある現在のヘッダー コントロール内のアイテムの識別子を取得します。|  
|[CHeaderCtrl::GetImageList](#getimagelist)|ヘッダー コントロールの項目を描画に使用するイメージ リストのハンドルを取得します。|  
|[CHeaderCtrl::GetItem](#getitem)|ヘッダー コントロールの項目に関する情報を取得します。|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|ヘッダー コントロールの項目の数を取得します。|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|ヘッダー コントロールの指定のドロップダウン ボタンの外接する四角形の情報を取得します。|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|ヘッダー コントロールの指定した項目の外接する四角形を取得します。|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|ヘッダー コントロールのアイテムの左から右の順序を取得します。|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。|  
|[CHeaderCtrl::HitTest](#hittest)|どのヘッダー項目かどうかを指定したポイントにあります。|  
|[として](#insertitem)|ヘッダー コントロールに新しい項目を挿入します。|  
|[配置](#layout)|指定した四角形内のヘッダー コントロールの位置とサイズを取得します。|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|ヘッダー コントロール内での順序に基づいて、item のインデックス値を取得します。|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|ヘッダー コントロールのビットマップの余白の幅を設定します。|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|フィルター属性が、変更時刻の投稿の間のタイムアウト間隔を設定、`HDN_FILTERCHANGE`通知します。|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|変更を手動でのヘッダー項目の間の境界線をドラッグし、ヘッダー項目のドロップします。|  
|[CHeaderCtrl::SetImageList](#setimagelist)|ヘッダー コントロールへのイメージ リストを割り当てます。|  
|[CHeaderCtrl::SetItem](#setitem)|ヘッダー コントロールの指定した項目の属性を設定します。|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|ヘッダー コントロールのアイテムの左から右の順序を設定します。|  
  
## <a name="remarks"></a>コメント  
 ヘッダー コントロールは、通常のテキストまたは数値の列のセットの上に配置するウィンドウです。 各列のタイトルが含まれているし、部分に分けることができます。 ユーザーは、各列の幅を設定する部分を分割する区切り線をドラッグできます。 ヘッダー コントロールの図解は、次を参照してください。[ヘッダー コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775238)します。  
  
 このコントロール (つまり、`CHeaderCtrl`クラス) は以降 Windows 95/98 および Windows NT 3.51 の下で実行されるプログラムにのみ使用できます。  
  
 Windows 95/Internet Explorer 4.0 のコモン コントロールの追加機能には、次の項目が含まれます。  
  
-   ヘッダー項目の並べ替え。  
  
-   ヘッダー項目は、ドラッグ アンド ドロップによるのヘッダー項目の順序を並べ替えるためです。 使用して、`HDS_DRAGDROP`スタイルを作成するとき、`CHeaderCtrl`オブジェクトです。  
  
-   ヘッダー列のテキストが列のサイズ変更時に常に表示できます。 使用して、`HDS_FULLDRAG`スタイルを作成するとき、`CHeaderCtrl`オブジェクトです。  
  
-   ヘッダーのホット トラッキング、ポインターが上にマウスを置いたときにヘッダー項目が強調表示します。 使用して、`HDS_HOTTRACK`スタイルを作成するとき、`CHeaderCtrl`オブジェクトです。  
  
-   イメージ リストのサポート。 ヘッダー項目が含まれているイメージを含めることができます、`CImageList`オブジェクトまたはテキスト。  
  
 使用の詳細については`CHeaderCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CHeaderCtrl](../../mfc/using-cheaderctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 `CHeaderCtrl` オブジェクトを構築します。  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#1;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 ヘッダー コントロールのすべてのフィルターをクリアします。  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 メッセージの動作を実装して[HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) 」の説明に従って、–&1; の列の値を持つ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#2;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 ヘッダー コントロールのフィルターをクリアします。  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 `nColumn`  
 列の値をクリアするフィルターを示します。  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 メッセージの動作を実装して[HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>CHeaderCtrl::Create  
 ヘッダー コントロールを作成し、それをアタッチ、`CHeaderCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ヘッダー コントロールのスタイルを指定します。 ヘッダー コントロールのスタイルについては、次を参照してください。[ヘッダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb775241)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 ヘッダー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 通常、ヘッダー コントロールの親ウィンドウを指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `nID`  
 ヘッダー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CHeaderCtrl`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず**作成**、ヘッダー コントロールを作成およびそれにアタッチする、`CHeaderCtrl`オブジェクトです。  
  
 ヘッダー コントロールのスタイルに加え、ヘッダー コントロールの位置し、サイズ変更するときの方法を決定する次の一般的なコントロールのスタイルを使用することができます (を参照してください[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)の詳細)。  
  
- `CCS_BOTTOM`コントロールの親ウィンドウのクライアント領域の下部に配置し、ウィンドウの幅を親と同じ幅に設定します。  
  
- `CCS_NODIVIDER`コントロールの上部に描画される&2; ピクセルを強調表示できないようにします。  
  
- `CCS_NOMOVEY`サイズを変更してへの応答で縦方向にしないが、水平方向に移動するには、コントロール、`WM_SIZE`メッセージです。 場合、`CCS_NORESIZE`スタイルを使用すると、このスタイルが適用されません。 ヘッダー コントロールでは、既定でこのスタイルが適用されます。  
  
- `CCS_NOPARENTALIGN`コントロールが自動的に親ウィンドウの上下に移動するを防ぎます。 代わりに、コントロールは、親ウィンドウのサイズへの変更に関係なく、親ウィンドウ内の位置を保持します。 場合、`CCS_TOP`または`CCS_BOTTOM`スタイルが使用されても、高さを調整して、既定値とが、位置と幅は変更されません。  
  
- `CCS_NORESIZE`コントロールがその初期サイズまたは新しいサイズを設定するときに、既定の幅と高さを使用するを防ぎます。 代わりに、幅と高さの作成やサイズ変更要求で指定されたコントロールを使用します。  
  
- `CCS_TOP`コントロールの親ウィンドウのクライアント領域の上部に配置し、ウィンドウの幅を親と同じ幅に設定します。  
  
 ヘッダー コントロールに、次のウィンドウ スタイルを適用することもできます (を参照してください[ウィンドウ スタイル](../../mfc/reference/window-styles.md)の詳細)。  
  
- **WS_CHILD**子ウィンドウを作成します。 `WS_POPUP` スタイルと一緒に使うことはできません。  
  
- **WS_VISIBLE**が最初に表示されるウィンドウを作成します。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。  
  
- **WS_GROUP**をユーザーに移動できるコントロール&1; つのコントロールから次の矢印キーでのグループの最初のコントロールを指定します。 定義されたすべてのコントロール、 **WS_GROUP**後、同じグループに属している最初のコントロールのスタイルを設定します。 次のコントロールで、 **WS_GROUP**スタイルがスタイルのグループを終了し、次のグループ (つまり、1 つのグループの最後、次の開始位置) を開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを使用して移動できるコントロールの任意の数のいずれかを指定します。 TAB キーで指定された次のコントロールにユーザーの移動、 **WS_TABSTOP**スタイル。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="createex"></a>CHeaderCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けること、`CHeaderCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 ヘッダー コントロールのスタイル。 ヘッダー コントロールのスタイルについては、次を参照してください。[ヘッダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb775241)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 参照してください[作成](#create)追加のスタイルの一覧です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに**作成**、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 ヘッダー コントロール内のアイテムの画像の透明なバージョンを作成します。  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ヘッダー コントロール内の項目の&0; から始まるインデックス。 この項目に割り当てられているイメージは、透明の画像の基盤です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)成功以外の場合は、オブジェクト**NULL**します。 返される一覧には、1 つのみのイメージが含まれます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。  
  
 `CImageList`を返されたポインター ポイントであり、オブジェクトは一時オブジェクトが次のアイドル処理で削除します。  
  
##  <a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 ヘッダー コントロールから項目を削除します。  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 削除する項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#5;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>CHeaderCtrl::DrawItem  
 オーナー描画ヘッダー コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)描画する項目を記述する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、この関数をオーバーライド`CHeaderCtrl`オブジェクトです。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>CHeaderCtrl::EditFilter  
 ヘッダー コントロールの指定したフィルターの編集を開始します。  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>パラメーター  
 `nColumn`  
 編集する列。  
  
 `bDiscardChanges`  
 ユーザーを処理する方法を指定する値は、ユーザーがフィルターの編集中の場合、変更の編集時に、 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312)メッセージを送信します。  
  
 指定`true`、ユーザーが行った変更を破棄または`false`ユーザーによる変更を確定します。  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 メッセージの動作を実装して[HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#7;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 ヘッダー コントロールのビットマップの余白の幅を取得します。  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセルのビットマップの余白の幅。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#8;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 現在のヘッダー コントロールにフォーカスがある項目のインデックスを取得します。  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォーカスがあるヘッダー項目の&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_headerCtrl`つまり、現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`SetFocusedItem`と`GetFocusedItem`メソッドです。 コードの前のセクションでは、5 つの列を含むヘッダー コントロールを作成しました。 ただし、列を表示しないように列の区切り記号をドラッグすることができます。 次の例では、設定し、フォーカスの項目としては、最後の列ヘッダーを確認します。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 ヘッダー コントロールの項目を描画に使用するイメージ リストのハンドルを取得します。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 `CImageList`を返されたポインター ポイントであり、オブジェクトは一時オブジェクトが次のアイドル処理で削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#9;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>CHeaderCtrl::GetItem  
 ヘッダー コントロールの項目に関する情報を取得します。  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 取得する項目の&0; から始まるインデックスを指定します。  
  
 `pHeaderItem`  
 ポインター、 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)新しい項目を受け取る構造体。 この構造体を併用、`InsertItem`と`SetItem`メンバー関数。 フラグのいずれかの設定、**マスク**要素は、の対応する要素の値が戻った時点で正しく入力あることを確認します。 場合、**マスク**要素が&0; に設定されている、他の構造体の要素の値は意味がありません。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#10;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 ヘッダー コントロールの項目の数を取得します。  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、ヘッダー コントロール項目の数それ以外の場合 – 1 です。  
  
### <a name="example"></a>例  
  例を参照してください[CHeaderCtrl::DeleteItem](#deleteitem)します。  
  
##  <a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 現在のヘッダー コントロールのヘッダー項目のドロップダウン ボタンの外接する四角形を取得します。  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iItem`|スタイルがヘッダー項目の&0; から始まるインデックス`HDF_SPLITBUTTON`します。 詳細については、次を参照してください。、`fmt`のメンバー、 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)構造体。|  
|[出力] `lpRect`|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`この関数が成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_headerCtrl`つまり、現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`GetItemDropDownRect`メソッドです。 コードの前のセクションでは、5 つの列を含むヘッダー コントロールを作成しました。 次のコード例は、ヘッダーのドロップダウン ボタンに予約されている最初の列を場所の周辺の 3D の四角形を描画します。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 ヘッダー コントロールの指定した項目の外接する四角形を取得します。  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ヘッダー コントロールの項目の&0; から始まるインデックス。  
  
 `lpRect`  
 アドレスへのポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 メッセージの動作を実装して[HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getorderarray"></a>CHeaderCtrl::GetOrderArray  
 ヘッダー コントロールのアイテムの左から右の順序を取得します。  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `piArray`  
 表示される左から右へ順に、ヘッダー コントロール項目のインデックス値を受け取るバッファーのアドレスへのポインター。  
  
 `iCount`  
 ヘッダー コントロール項目の数。 非負の値にする必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ヘッダー項目の並べ替えをサポートするために提供されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#11;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpRect`|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る。|  
  
### <a name="return-value"></a>戻り値  
 `true`この関数が成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 ヘッダー コントロールに表示されるよりも同時に他のアイテムが含まれている場合、コントロールは、表示されていない項目をスクロールするオーバーフロー ボタンを表示できます。 ヘッダー コントロールする必要がありますが、`HDS_OVERFLOW`と`HDF_SPLITBUTTON`オーバーフロー ボタンを表示するスタイル。 外接する四角形は、オーバーフロー ボタンを囲むし、オーバーフロー ボタンが表示される場合にのみ存在します。 詳細については、次を参照してください。[ヘッダー コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb775241)します。  
  
 このメソッドは、送信、 [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_headerCtrl`つまり、現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`GetOverflowRect`メソッドです。 コードの前のセクションでは、5 つの列を含むヘッダー コントロールを作成しました。 ただし、列を表示しないように列の区切り記号をドラッグすることができます。 いくつかの列が表示されない場合、ヘッダー コントロールは、オーバーフロー ボタンを描画します。 次のコード例は、オーバーフロー ボタンの場所の周辺の 3D の四角形を描画します。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>CHeaderCtrl::HitTest  
 どのヘッダー項目かどうかを指定したポイントにあります。  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力、出力] `phdhti`|ポインター、 [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245)をテストする点を指定し、テストの結果を受け取る構造体。|  
  
### <a name="return-value"></a>戻り値  
 指定した位置に存在する場合、ヘッダー項目の&0; から始まるインデックスそれ以外の場合、–&1; です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_headerCtrl`つまり、現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`HitTest`メソッドです。 このコード例の前のセクションでは、5 つの列を含むヘッダー コントロールを作成しました。 ただし、列を表示しないように列の区切り記号をドラッグすることができます。 この例は、表示されている場合に、列のインデックスをレポートし、列が表示されていない場合は-1。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>として  
 指定したインデックス位置のヘッダー コントロールに新しい項目を挿入します。  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 挿入する項目の&0; から始まるインデックス。 値が&0; の場合は、アイテムがヘッダー コントロールの先頭に挿入されます。 値が最大値より大きい場合は、ヘッダー コントロールの最後に、項目が挿入されます。  
  
 *phdi*  
 ポインター、 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)挿入する項目に関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、新しい項目のインデックスそれ以外の場合 – 1 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#12;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>配置  
 指定した四角形内のヘッダー コントロールの位置とサイズを取得します。  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>パラメーター  
 *pHeaderLayout*  
 ポインター、 [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249)構造体は、ヘッダー コントロールの位置とサイズを設定するための情報が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、指定した四角形を占有するようである新しいヘッダー コントロールの適切なサイズを調べるために使用されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#13;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 ヘッダー コントロール内での順序に基づいて、item のインデックス値を取得します。  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nOrder*  
 ヘッダー コントロールに左から右へアイテムを表示する&0; から始まる順序です。  
  
### <a name="return-value"></a>戻り値  
 ヘッダー コントロール内での順序に基づいて、項目のインデックス。 インデックスの数は、左から右、0 から始まるをします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ヘッダー項目の並べ替えをサポートするために提供されます。  
  
##  <a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 ヘッダー コントロールのビットマップの余白の幅を設定します。  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWidth`  
 幅 (ピクセル単位) を既存のヘッダー コントロール内にあるビットマップを囲む余白の指定します。  
  
### <a name="return-value"></a>戻り値  
 ピクセルのビットマップの余白の幅。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#14;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 フィルター属性が、変更時刻の投稿の間のタイムアウト間隔を設定、[から](http://msdn.microsoft.com/library/windows/desktop/bb775277)通知します。  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeOut*  
 タイムアウト値 (ミリ秒)。  
  
### <a name="return-value"></a>戻り値  
 変更するフィルター コントロールのインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#15;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iItem`|ヘッダー項目の&0; から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_headerCtrl`つまり、現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`SetFocusedItem`と`GetFocusedItem`メソッドです。 コードの前のセクションでは、5 つの列を含むヘッダー コントロールを作成しました。 ただし、列を表示しないように列の区切り記号をドラッグすることができます。 次の例では、設定し、フォーカスの項目としては、最後の列ヘッダーを確認します。  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 変更を手動でのヘッダー項目の間の境界線をドラッグし、ヘッダー項目のドロップします。  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 ポインターの位置。 ヘッダー コントロールには、ポインターの位置に基づいて適切な区分線が強調表示されます。  
  
 `nIndex`  
 強調表示されている区分線のインデックス。  
  
### <a name="return-value"></a>戻り値  
 強調表示されている区分線のインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#16;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>CHeaderCtrl::SetImageList  
 ヘッダー コントロールへのイメージ リストを割り当てます。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`ヘッダー コントロールに割り当てられるイメージ リストを格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)ヘッダー コントロールに割り当てられています。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 `CImageList`を返されたポインター ポイントであり、オブジェクトは一時オブジェクトが次のアイドル処理で削除します。  
  
### <a name="example"></a>例  
  例を参照してください[CHeaderCtrl::GetImageList](#getimagelist)します。  
  
##  <a name="setitem"></a>CHeaderCtrl::SetItem  
 ヘッダー コントロールの指定した項目の属性を設定します。  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 操作する項目の&0; から始まるインデックス。  
  
 `pHeaderItem`  
 ポインター、 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)新しい項目の情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CHeaderCtrl::GetItem](#getitem)します。  
  
##  <a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 ヘッダー コントロールのアイテムの左から右の順序を設定します。  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `iCount`  
 ヘッダー コントロール項目の数。  
  
 `piArray`  
 表示される左から右へ順に、ヘッダー コントロール項目のインデックス値を受け取るバッファーのアドレスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ヘッダー項目の並べ替えをサポートするために提供されます。  
  
### <a name="example"></a>例  
  例を参照してください[CHeaderCtrl::GetOrderArray](#getorderarray)します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)   
 [CImageList クラス](../../mfc/reference/cimagelist-class.md)
