---
title: "CMFCPropertyGridColorProperty クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty class
- CMFCPropertyGridColorProperty::OnClickButton method
- CMFCPropertyGridColorProperty::FormatProperty method
- CMFCPropertyGridColorProperty::OnDrawValue method
- CMFCPropertyGridColorProperty::OnUpdateValue method
- CMFCPropertyGridColorProperty::OnEdit method
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
caps.latest.revision: 33
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
ms.openlocfilehash: 7069e35a44dbb0dbd4ad8d5d2b9156ccfbc15c76
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty クラス
`CMFCPropertyGridColorProperty` クラスは、色の選択用のダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|`CMFCPropertyGridColorProperty` オブジェクトを構築します。|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|により、*自動*ボタンの色の選択 ダイアログ ボックスをクリックします。 (標準的な自動ボタンのラベルは**自動**)。|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|により、*他の*ボタンの色の選択 ダイアログ ボックスをクリックします。 (標準の他のボタンのラベルは**他の色**.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  (上書き[CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty))。|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|プロパティの現在の色を取得します。|  
|`CMFCPropertyGridColorProperty::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCPropertyGridColorProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  (上書き[CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton))。|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|プロパティ値を表示するためにフレームワークによって呼び出されます  (上書き[CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue))。|  
|`CMFCPropertyGridColorProperty::OnEdit`|ユーザーがプロパティ値を変更しようとすると、フレームワークによって呼び出されます  (上書き[CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit))。|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|編集可能なプロパティの値が変更されると、フレームワークによって呼び出されます  (上書き[CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue))。|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|プロパティの新しい色を設定します。|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|現在のカラー プロパティ グリッド内の列の数を指定します。|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|編集可能なプロパティの元の値を設定します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCPropertyGridColorProperty` クラスは、プロパティ リスト コントロールに追加できるカラー プロパティをサポートします。 詳細については、次を参照してください。、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)します。  
  
## <a name="example"></a>例  
 `CMFCPropertyGridColorProperty` クラスのオブジェクトを構築する方法、および `CMFCPropertyGridColorProperty` クラスの各種メソッドを使用してこのオブジェクトを構成する方法を次の例に示します。 このコードでは、自動ボタンとその他ボタンを有効にする方法、および色と列番号を設定する方法を示しています。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&#13;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 `CMFCPropertyGridColorProperty` オブジェクトを構築します。  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strName`  
 プロパティの名前。  
  
 [入力] `color`  
 プロパティの色の値。  
  
 [入力] `pPalette`  
 カラー パレットへのポインター。 既定値は `NULL` です。  
  
 [入力] `lpszDescr`  
 プロパティの説明。 既定値は `NULL` です。  
  
 [入力] `dwData`  
 整数値またはプロパティに関連付けられているその他のデータへのポインターなどのアプリケーションに固有のデータです。 既定値は 0 です。  
  
##  <a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton  
 により、*自動*ボタンの色の選択 ダイアログ ボックスをクリックします。 (標準的な自動ボタンのラベルは**自動**)。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 自動のボタンのラベル テキスト。  
  
 [入力] `colorAutomatic`  
 自動 (既定値) の色の RGB 色の値。  
  
 [入力] `bEnable`  
 `TRUE`自動ボタンを有効にするにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton  
 により、*他の*ボタンの色の選択 ダイアログ ボックスをクリックします。 (標準の他のボタンのラベルは**他の色**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 その他のボタンのラベル テキスト。  
  
 [入力] `bAltColorDlg`  
 `TRUE`表示する、 `CMFCColorDialog`  ダイアログ ボックス`FALSE`標準色の選択 ダイアログ ボックスを表示します。 既定値は `TRUE` です。  
  
 [入力] `bEnable`  
 `TRUE`その他のボタンを表示するにはそれ以外の場合、`FALSE`です。  既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor  
 プロパティの現在の色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor  
 プロパティの新しい色を設定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber  
 現在のカラー プロパティ グリッド内の列の数を指定します。  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nColumnsNumber`  
 推奨される色のプロパティ グリッドで列数。  
  
### <a name="remarks"></a>コメント  
 このメソッドの値を設定、`m_nColumnsNumber`データ メンバーを保護します。  
  
##  <a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue  
 編集可能なプロパティの元の値を設定します。  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `varValue`  
 値。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue)編集されたプロパティの元の値を再設定する方法です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)
