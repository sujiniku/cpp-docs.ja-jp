---
title: CPaneContainer クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneContainer
- AFXPANECONTAINER/CPaneContainer
- AFXPANECONTAINER/CPaneContainer::CPaneContainer
- AFXPANECONTAINER/CPaneContainer::AddPane
- AFXPANECONTAINER/CPaneContainer::AddRef
- AFXPANECONTAINER/CPaneContainer::AddSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::CalcAvailablePaneSpace
- AFXPANECONTAINER/CPaneContainer::CalcAvailableSpace
- AFXPANECONTAINER/CPaneContainer::CalculateRecentSize
- AFXPANECONTAINER/CPaneContainer::CheckPaneDividerVisibility
- AFXPANECONTAINER/CPaneContainer::Copy
- AFXPANECONTAINER/CPaneContainer::DeletePane
- AFXPANECONTAINER/CPaneContainer::FindSubPaneContainer
- AFXPANECONTAINER/CPaneContainer::FindTabbedPane
- AFXPANECONTAINER/CPaneContainer::GetAssociatedSiblingPaneIDs
- AFXPANECONTAINER/CPaneContainer::GetLeftPane
- AFXPANECONTAINER/CPaneContainer::GetLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetMinSize
- AFXPANECONTAINER/CPaneContainer::GetMinSizeLeft
- AFXPANECONTAINER/CPaneContainer::GetMinSizeRight
- AFXPANECONTAINER/CPaneContainer::GetNodeCount
- AFXPANECONTAINER/CPaneContainer::GetPaneDivider
- AFXPANECONTAINER/CPaneContainer::GetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerRect
- AFXPANECONTAINER/CPaneContainer::GetRecentPaneDividerStyle
- AFXPANECONTAINER/CPaneContainer::GetRecentPercent
- AFXPANECONTAINER/CPaneContainer::GetRefCount
- AFXPANECONTAINER/CPaneContainer::GetResizeStep
- AFXPANECONTAINER/CPaneContainer::GetRightPane
- AFXPANECONTAINER/CPaneContainer::GetRightPaneContainer
- AFXPANECONTAINER/CPaneContainer::GetTotalReferenceCount
- AFXPANECONTAINER/CPaneContainer::GetWindowRect
- AFXPANECONTAINER/CPaneContainer::IsDisposed
- AFXPANECONTAINER/CPaneContainer::IsEmpty
- AFXPANECONTAINER/CPaneContainer::IsLeftPane
- AFXPANECONTAINER/CPaneContainer::IsLeftPaneContainer
- AFXPANECONTAINER/CPaneContainer::IsLeftPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsRightPartEmpty
- AFXPANECONTAINER/CPaneContainer::IsVisible
- AFXPANECONTAINER/CPaneContainer::Move
- AFXPANECONTAINER/CPaneContainer::OnDeleteHidePane
- AFXPANECONTAINER/CPaneContainer::OnMoveInternalPaneDivider
- AFXPANECONTAINER/CPaneContainer::OnShowPane
- AFXPANECONTAINER/CPaneContainer::Release
- AFXPANECONTAINER/CPaneContainer::ReleaseEmptyPaneContainer
- AFXPANECONTAINER/CPaneContainer::RemoveNonValidPanes
- AFXPANECONTAINER/CPaneContainer::RemovePane
- AFXPANECONTAINER/CPaneContainer::Resize
- AFXPANECONTAINER/CPaneContainer::ResizePane
- AFXPANECONTAINER/CPaneContainer::ResizePartOfPaneContainer
- AFXPANECONTAINER/CPaneContainer::Serialize
- AFXPANECONTAINER/CPaneContainer::SetPane
- AFXPANECONTAINER/CPaneContainer::SetPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetPaneDivider
- AFXPANECONTAINER/CPaneContainer::SetParentPaneContainer
- AFXPANECONTAINER/CPaneContainer::SetRecentPercent
- AFXPANECONTAINER/CPaneContainer::SetUpByID
- AFXPANECONTAINER/CPaneContainer::StoreRecentDockSiteInfo
- AFXPANECONTAINER/CPaneContainer::StretchPaneContainer
dev_langs:
- C++
helpviewer_keywords:
- CPaneContainer [MFC], CPaneContainer
- CPaneContainer [MFC], AddPane
- CPaneContainer [MFC], AddRef
- CPaneContainer [MFC], AddSubPaneContainer
- CPaneContainer [MFC], CalcAvailablePaneSpace
- CPaneContainer [MFC], CalcAvailableSpace
- CPaneContainer [MFC], CalculateRecentSize
- CPaneContainer [MFC], CheckPaneDividerVisibility
- CPaneContainer [MFC], Copy
- CPaneContainer [MFC], DeletePane
- CPaneContainer [MFC], FindSubPaneContainer
- CPaneContainer [MFC], FindTabbedPane
- CPaneContainer [MFC], GetAssociatedSiblingPaneIDs
- CPaneContainer [MFC], GetLeftPane
- CPaneContainer [MFC], GetLeftPaneContainer
- CPaneContainer [MFC], GetMinSize
- CPaneContainer [MFC], GetMinSizeLeft
- CPaneContainer [MFC], GetMinSizeRight
- CPaneContainer [MFC], GetNodeCount
- CPaneContainer [MFC], GetPaneDivider
- CPaneContainer [MFC], GetParentPaneContainer
- CPaneContainer [MFC], GetRecentPaneDividerRect
- CPaneContainer [MFC], GetRecentPaneDividerStyle
- CPaneContainer [MFC], GetRecentPercent
- CPaneContainer [MFC], GetRefCount
- CPaneContainer [MFC], GetResizeStep
- CPaneContainer [MFC], GetRightPane
- CPaneContainer [MFC], GetRightPaneContainer
- CPaneContainer [MFC], GetTotalReferenceCount
- CPaneContainer [MFC], GetWindowRect
- CPaneContainer [MFC], IsDisposed
- CPaneContainer [MFC], IsEmpty
- CPaneContainer [MFC], IsLeftPane
- CPaneContainer [MFC], IsLeftPaneContainer
- CPaneContainer [MFC], IsLeftPartEmpty
- CPaneContainer [MFC], IsRightPartEmpty
- CPaneContainer [MFC], IsVisible
- CPaneContainer [MFC], Move
- CPaneContainer [MFC], OnDeleteHidePane
- CPaneContainer [MFC], OnMoveInternalPaneDivider
- CPaneContainer [MFC], OnShowPane
- CPaneContainer [MFC], Release
- CPaneContainer [MFC], ReleaseEmptyPaneContainer
- CPaneContainer [MFC], RemoveNonValidPanes
- CPaneContainer [MFC], RemovePane
- CPaneContainer [MFC], Resize
- CPaneContainer [MFC], ResizePane
- CPaneContainer [MFC], ResizePartOfPaneContainer
- CPaneContainer [MFC], Serialize
- CPaneContainer [MFC], SetPane
- CPaneContainer [MFC], SetPaneContainer
- CPaneContainer [MFC], SetPaneDivider
- CPaneContainer [MFC], SetParentPaneContainer
- CPaneContainer [MFC], SetRecentPercent
- CPaneContainer [MFC], SetUpByID
- CPaneContainer [MFC], StoreRecentDockSiteInfo
- CPaneContainer [MFC], StretchPaneContainer
ms.assetid: beb79e08-f611-4d66-ba04-053baa79bf86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81f516d92777583d54f5e0071ad54012dc43bb81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpanecontainer-class"></a>CPaneContainer クラス
`CPaneContainer`クラスは、MFC によって実装されるドッキング モデルの基本的なコンポーネントです。 このクラスのオブジェクトは、2 つのドッキング ペイン、または `CPaneContainer.` の 2 つのインスタンスへのポインターを格納します。また、ペイン (またはコンテナー) を分割している区分線へのポインターも格納します。 コンテナー内にコンテナーを入れ子にすると、フレームワークは複雑なドッキング レイアウトを表すバイナリ ツリーを構築します。 バイナリ ツリーのルートが格納されている、 [CPaneContainerManager](../../mfc/reference/cpanecontainermanager-class.md)オブジェクト。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
 
## <a name="syntax"></a>構文  
  
```  
class CPaneContainer : public CObject    
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneContainer::CPaneContainer](#cpanecontainer)|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneContainer::AddPane](#addpane)||  
|[CPaneContainer::AddRef](#addref)||  
|[CPaneContainer::AddSubPaneContainer](#addsubpanecontainer)||  
|[CPaneContainer::CalcAvailablePaneSpace](#calcavailablepanespace)||  
|[CPaneContainer::CalcAvailableSpace](#calcavailablespace)||  
|[CPaneContainer::CalculateRecentSize](#calculaterecentsize)||  
|[CPaneContainer::CheckPaneDividerVisibility](#checkpanedividervisibility)||  
|[CPaneContainer::Copy](#copy)||  
|[CPaneContainer::DeletePane](#deletepane)||  
|[CPaneContainer::FindSubPaneContainer](#findsubpanecontainer)||  
|[CPaneContainer::FindTabbedPane](#findtabbedpane)||  
|[CPaneContainer::GetAssociatedSiblingPaneIDs](#getassociatedsiblingpaneids)||  
|[CPaneContainer::GetLeftPane](#getleftpane)||  
|[CPaneContainer::GetLeftPaneContainer](#getleftpanecontainer)||  
|[CPaneContainer::GetMinSize](#getminsize)||  
|[CPaneContainer::GetMinSizeLeft](#getminsizeleft)||  
|[CPaneContainer::GetMinSizeRight](#getminsizeright)||  
|[CPaneContainer::GetNodeCount](#getnodecount)||  
|[CPaneContainer::GetPaneDivider](#getpanedivider)||  
|[CPaneContainer::GetParentPaneContainer](#getparentpanecontainer)||  
|[CPaneContainer::GetRecentPaneDividerRect](#getrecentpanedividerrect)||  
|[CPaneContainer::GetRecentPaneDividerStyle](#getrecentpanedividerstyle)||  
|[CPaneContainer::GetRecentPercent](#getrecentpercent)||  
|[CPaneContainer::GetRefCount](#getrefcount)||  
|[CPaneContainer::GetResizeStep](#getresizestep)||  
|[CPaneContainer::GetRightPane](#getrightpane)||  
|[CPaneContainer::GetRightPaneContainer](#getrightpanecontainer)||  
|[CPaneContainer::GetTotalReferenceCount](#gettotalreferencecount)||  
|[CPaneContainer::GetWindowRect](#getwindowrect)||  
|[CPaneContainer::IsDisposed](#isdisposed)||  
|[CPaneContainer::IsEmpty](#isempty)||  
|[CPaneContainer::IsLeftPane](#isleftpane)||  
|[CPaneContainer::IsLeftPaneContainer](#isleftpanecontainer)||  
|[CPaneContainer::IsLeftPartEmpty](#isleftpartempty)||  
|[CPaneContainer::IsRightPartEmpty](#isrightpartempty)||  
|[CPaneContainer::IsVisible](#isvisible)||  
|[CPaneContainer::Move](#move)||  
|[CPaneContainer::OnDeleteHidePane](#ondeletehidepane)||  
|[CPaneContainer::OnMoveInternalPaneDivider](#onmoveinternalpanedivider)||  
|[CPaneContainer::OnShowPane](#onshowpane)||  
|[CPaneContainer::Release](#release)||  
|[CPaneContainer::ReleaseEmptyPaneContainer](#releaseemptypanecontainer)||  
|[CPaneContainer::RemoveNonValidPanes](#removenonvalidpanes)||  
|[CPaneContainer::RemovePane](#removepane)||  
|[CPaneContainer::Resize](#resize)||  
|[CPaneContainer::ResizePane](#resizepane)||  
|[CPaneContainer::ResizePartOfPaneContainer](#resizepartofpanecontainer)||  
|[CPaneContainer::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CPaneContainer::SetPane](#setpane)||  
|[CPaneContainer::SetPaneContainer](#setpanecontainer)||  
|[CPaneContainer::SetPaneDivider](#setpanedivider)||  
|[CPaneContainer::SetParentPaneContainer](#setparentpanecontainer)||  
|[CPaneContainer::SetRecentPercent](#setrecentpercent)||  
|[CPaneContainer::SetUpByID](#setupbyid)||  
|[CPaneContainer::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneContainer::StretchPaneContainer](#stretchpanecontainer)||  
  
### <a name="remarks"></a>コメント  
 `CPaneContainer` オブジェクトは、フレームワークによって自動的に作成されます。  
  
## <a name="example"></a>例  
 次の例は、のインスタンスを構築する方法を示します、`CPaneContainer`クラスです。 このコード スニペットの一部である、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#1](../../mfc/reference/codesnippet/cpp/cpanecontainer-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CPaneContainer](../../mfc/reference/cpanecontainer-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpanecontainer.h  
  
##  <a name="addpane"></a>  CPaneContainer::AddPane  

  
```  
CDockablePane* AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addref"></a>  CPaneContainer::AddRef  

  
```  
void AddRef();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addsubpanecontainer"></a>  CPaneContainer::AddSubPaneContainer  

  
```  
BOOL AddSubPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bRightNodeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pContainer`  
 [入力] `bRightNodeNew`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcavailablepanespace"></a>  CPaneContainer::CalcAvailablePaneSpace  

  
```  
virtual int CalcAvailablePaneSpace(
    int nRequiredOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRequiredOffset`  
 [入力] `pBar`  
 [入力] `pContainer`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcavailablespace"></a>  CPaneContainer::CalcAvailableSpace  

  
```  
virtual CSize CalcAvailableSpace(
    CSize sizeStretch,  
    BOOL bLeftBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `sizeStretch`  
 [入力] `bLeftBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calculaterecentsize"></a>  CPaneContainer::CalculateRecentSize  

  
```  
void CalculateRecentSize();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkpanedividervisibility"></a>  CPaneContainer::CheckPaneDividerVisibility  

  
```  
void CheckPaneDividerVisibility();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copy"></a>  CPaneContainer::Copy  

  
```  
virtual CPaneContainer* Copy(CPaneContainer* pParentContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentContainer`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cpanecontainer"></a>  CPaneContainer::CPaneContainer  

  
```  
CPaneContainer(
    CPaneContainerManager* pManager = NULL,  
    CDockablePane* pLeftBar = NULL,  
    CDockablePane* pRightBar = NULL,  
    CPaneDivider* pSlider = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pManager`  
 [入力] `pLeftBar`  
 [入力] `pRightBar`  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="deletepane"></a>  CPaneContainer::DeletePane  

  
```  
virtual void DeletePane(
    CDockablePane* pBar,  
    BC_FIND_CRITERIA barType);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `barType`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findsubpanecontainer"></a>  CPaneContainer::FindSubPaneContainer  

  
```  
CPaneContainer* FindSubPaneContainer(
    const CObject* pObject,  
    BC_FIND_CRITERIA findCriteria);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pObject`  
 [入力] `findCriteria`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findtabbedpane"></a>  CPaneContainer::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getassociatedsiblingpaneids"></a>  CPaneContainer::GetAssociatedSiblingPaneIDs  

  
```  
CList<UINT, UINT>* GetAssociatedSiblingPaneIDs(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getleftpane"></a>  CPaneContainer::GetLeftPane  

  
```  
const CDockablePane* GetLeftPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getleftpanecontainer"></a>  CPaneContainer::GetLeftPaneContainer  

  
```  
const CPaneContainer* GetLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsize"></a>  CPaneContainer::GetMinSize  

  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsizeleft"></a>  CPaneContainer::GetMinSizeLeft  

  
```  
virtual void GetMinSizeLeft(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getminsizeright"></a>  CPaneContainer::GetMinSizeRight  

  
```  
virtual void GetMinSizeRight(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `size`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getnodecount"></a>  CPaneContainer::GetNodeCount  

  
```  
int GetNodeCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanedivider"></a>  CPaneContainer::GetPaneDivider  

  
```  
const CPaneDivider* GetPaneDivider() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getparentpanecontainer"></a>  CPaneContainer::GetParentPaneContainer  

  
```  
CPaneContainer* GetParentPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpanedividerrect"></a>  CPaneContainer::GetRecentPaneDividerRect  

  
```  
CRect GetRecentPaneDividerRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpanedividerstyle"></a>  CPaneContainer::GetRecentPaneDividerStyle  

  
```  
DWORD GetRecentPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrecentpercent"></a>  CPaneContainer::GetRecentPercent  

  
```  
int GetRecentPercent();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrefcount"></a>  CPaneContainer::GetRefCount  

  
```  
LONG GetRefCount();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getresizestep"></a>  CPaneContainer::GetResizeStep  

  
```  
virtual int GetResizeStep() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrightpane"></a>  CPaneContainer::GetRightPane  

  
```  
const CDockablePane* GetRightPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrightpanecontainer"></a>  CPaneContainer::GetRightPaneContainer  

  
```  
const CPaneContainer* GetRightPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettotalreferencecount"></a>  CPaneContainer::GetTotalReferenceCount  

  
```  
int GetTotalReferenceCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getwindowrect"></a>  CPaneContainer::GetWindowRect  

  
```  
virtual void GetWindowRect(
    CRect& rect,  
    BOOL bIgnoreVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `bIgnoreVisibility`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdisposed"></a>  CPaneContainer::IsDisposed  

  
```  
BOOL IsDisposed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isempty"></a>  CPaneContainer::IsEmpty  

  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpane"></a>  CPaneContainer::IsLeftPane  

  
```  
BOOL IsLeftPane(CDockablePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpanecontainer"></a>  CPaneContainer::IsLeftPaneContainer  

  
```  
BOOL IsLeftPaneContainer() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isleftpartempty"></a>  CPaneContainer::IsLeftPartEmpty  

  
```  
BOOL IsLeftPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCheckVisibility`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrightpartempty"></a>  CPaneContainer::IsRightPartEmpty  

  
```  
BOOL IsRightPartEmpty(BOOL bCheckVisibility = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCheckVisibility`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isvisible"></a>  CPaneContainer::IsVisible  

  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="move"></a>  CPaneContainer::Move  

  
```  
virtual void Move(CPoint ptNewLeftTop);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptNewLeftTop`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondeletehidepane"></a>  CPaneContainer::OnDeleteHidePane  

  
```  
void OnDeleteHidePane(
    CDockablePane* pBar,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bHide`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onmoveinternalpanedivider"></a>  CPaneContainer::OnMoveInternalPaneDivider  

  
```  
virtual int OnMoveInternalPaneDivider(
    int nOffset,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `hdwp`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpane"></a>  CPaneContainer::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bShow`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="release"></a>  CPaneContainer::Release  

  
```  
DWORD Release();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="releaseemptypanecontainer"></a>  CPaneContainer::ReleaseEmptyPaneContainer  

  
```  
void ReleaseEmptyPaneContainer();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removenonvalidpanes"></a>  CPaneContainer::RemoveNonValidPanes  

  
```  
void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removepane"></a>  CPaneContainer::RemovePane  

  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resize"></a>  CPaneContainer::Resize  

  
```  
virtual void Resize(
    CRect rect,  
    HDWP& hdwp,  
    BOOL bRedraw = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 [入力] `hdwp`  
 [入力] `bRedraw`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizepane"></a>  CPaneContainer::ResizePane  

  
```  
virtual void ResizePane(
    int nOffset,  
    CPane* pBar,  
    CPaneContainer* pContainer,  
    BOOL bHorz,  
    BOOL bLeftBar,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `pBar`  
 [入力] `pContainer`  
 [入力] `bHorz`  
 [入力] `bLeftBar`  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resizepartofpanecontainer"></a>  CPaneContainer::ResizePartOfPaneContainer  

  
```  
virtual void ResizePartOfPaneContainer(
    int nOffset,  
    BOOL bLeftPart,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `bLeftPart`  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="serialize"></a>  CPaneContainer::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpane"></a>  CPaneContainer::SetPane  

  
```  
void SetPane(
    CDockablePane* pBar,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bLeft`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanecontainer"></a>  CPaneContainer::SetPaneContainer  

  
```  
void SetPaneContainer(
    CPaneContainer* pContainer,  
    BOOL bLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pContainer`  
 [入力] `bLeft`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanedivider"></a>  CPaneContainer::SetPaneDivider  

  
```  
void SetPaneDivider(CPaneDivider* pSlider);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSlider`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setparentpanecontainer"></a>  CPaneContainer::SetParentPaneContainer  

  
```  
void SetParentPaneContainer(CPaneContainer* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `p`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setrecentpercent"></a>  CPaneContainer::SetRecentPercent  

  
```  
void SetRecentPercent(int nRecentPercent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRecentPercent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setupbyid"></a>  CPaneContainer::SetUpByID  

  
```  
BOOL SetUpByID(
    UINT nID,  
    CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 [入力] `pBar`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneContainer::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="stretchpanecontainer"></a>  CPaneContainer::StretchPaneContainer  

  
```  
virtual int StretchPaneContainer(
    int nOffset,  
    BOOL bStretchHorz,  
    BOOL bLeftBar,  
    BOOL bMoveSlider,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 [入力] `bStretchHorz`  
 [入力] `bLeftBar`  
 [入力] `bMoveSlider`  
 [入力] `hdwp`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CPaneContainerManager クラス](../../mfc/reference/cpanecontainermanager-class.md)
