---
title: "CUserToolsManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager class
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
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
ms.openlocfilehash: 0b82adf0f9eba5ee334ada2c169546f27894c1dd
ms.lasthandoff: 02/24/2017

---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager クラス
コレクションを保持[CUserTool クラス](../../mfc/reference/cusertool-class.md)アプリケーション内のオブジェクト。 ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 `CUserToolsManager` オブジェクトは、ユーザーまたは開発者がアプリケーションに新しいユーザー ツールを追加できるようにします。 ユーザー ツールに関連するコマンドの実行をサポートし、Windows レジストリにユーザー ツールに関する情報を保存します。  
  
## <a name="syntax"></a>構文  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|`CUserToolsManager` を構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|新しいユーザー ツールを作成します。|  
|[CUserToolsManager::FindTool](#findtool)|ポインターを返す、`CMFCUserTool`指定されたコマンド ID に関連付けられているオブジェクト|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|関連付けられているリソース ID を返します、**引数**メニューで、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。|  
|[CUserToolsManager::GetDefExt](#getdefext)|既定の拡張子を返します、**ファイルを開く** ダイアログ ボックス ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) でを使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。|  
|[CUserToolsManager::GetFilter](#getfilter)|ファイル フィルターを返します、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|関連付けられているリソース ID を返します、**初期ディレクトリ**メニューで、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|アプリケーションに割り当てることができるユーザー ツールの最大数を返します。|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|ユーザー ツールのメニュー項目のプレース ホルダーのコマンド ID を返します。|  
|[CUserToolsManager::GetUserTools](#getusertools)|ユーザー ツールの一覧への参照を返します。|  
|[CUserToolsManager::InvokeTool](#invoketool)|指定されたコマンド ID を持つユーザー ツールに関連付けられているアプリケーションを実行します。|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|コマンド ID がユーザー ツールに関連付けられているかどうかを判断します。|  
|[CUserToolsManager::LoadState](#loadstate)|Windows レジストリからユーザー ツールに関する情報を読み込みます。|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|ユーザー ツールの一覧で、下の指定されたユーザー ツールを移動します。|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|ユーザー ツールの一覧上の指定したユーザー ツールを移動します。|  
|[CUserToolsManager::RemoveTool](#removetool)|指定したユーザー ツールをアプリケーションから削除します。|  
|[CUserToolsManager::SaveState](#savestate)|Windows レジストリにユーザー ツールに関する情報を格納します。|  
|[CUserToolsManager::SetDefExt](#setdefext)|既定の拡張子を指定する、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) でを使用して、**コマンド**フィールドに、**ツール**のタブをクリック、**カスタマイズ** ダイアログ ボックス。|  
|[CUserToolsManager::SetFilter](#setfilter)|ファイル フィルターを指定、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) でを使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。|  
  
## <a name="remarks"></a>コメント  
 ユーザー ツールをアプリケーションに組み込むには、次の必要があります。  
  
 1. メニュー項目とユーザー ツールのメニュー エントリに関連付けられているコマンド ID を予約します。  
  
 2. ユーザーは、アプリケーションで定義できる各ユーザー ツールの連番のコマンド ID を予約します。  
  
 3. 呼び出す、 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)メソッドと、次のパラメーターを指定する: メニュー コマンド ID、最初のユーザー ツールのコマンド ID、およびツールのユーザーの最後のコマンド id。  
  
 のみ&1; つありますグローバル`CUserToolsManager`アプリケーションごとのオブジェクト。  
  
 ユーザー ツールの例は、VisualStudioDemo サンプル プロジェクトを参照してください。  
  
## <a name="example"></a>例  
 次の例への参照を取得する方法、`CUserToolsManager`オブジェクトと、新しいユーザー ツールを作成する方法です。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&38;](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 新しいユーザー ツールを作成します。  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成したユーザー ツールへのポインターまたは`NULL`ユーザー ツールの数が最大値を超過した場合。 戻り値の型に渡される型と同じ`CWinAppEx::EnableUserTools`として、`pToolRTC`パラメーター。  
  
### <a name="remarks"></a>コメント  
 このメソッドの呼び出しで指定されている範囲内の最初の利用可能なメニュー コマンド ID の検索[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)とユーザー ツールにこの ID を割り当てます。  
  
 メソッドは、ツールの数の上限に達した場合に失敗します。 これは、範囲内のすべてのコマンド Id がユーザー ツールに割り当てられたときに発生します。 ツールの最大数を取得するにを呼び出して[CUserToolsManager::GetMaxTools](#getmaxtools)します。 呼び出してツール リストへのアクセスを取得することができます、 [CUserToolsManager::GetUserTools](#getusertools)メソッドです。  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 `CUserToolsManager` を構築します。 各アプリケーションは、1 つのユーザー ツール マネージャー多くてが必要です。  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdToolsDummy`  
 フレームワークがユーザーの [ツール] メニューのコマンド ID のプレース ホルダーとして使用する符号なし整数。  
  
 [入力] `uiCmdFirst`  
 最初のユーザー ツールのコマンドのコマンド ID。  
  
 [入力] `uiCmdLast`  
 最後のユーザー ツールのコマンドのコマンド ID。  
  
 [入力] `pToolRTC`  
 クラスを[CUserToolsManager::CreateNewTool](#createnewtool)を作成します。 派生型を使用するこのクラスを使用すると、 [CUserTool クラス](../../mfc/reference/cusertool-class.md)既定の実装ではなく。  
  
 [入力] `uArgMenuID`  
 引数のポップアップ メニューのメニュー リソースの ID。  
  
 [入力] `uInitDirMenuID`  
 [初期ディレクトリ] ポップアップ メニューのメニュー リソースの ID。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを呼び出す必要はありません。 代わりに、 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を有効にするユーザーのツール、および呼び出し[CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager)へのポインターを取得する、`CUserToolsManager`です。 詳細については、次を参照してください。[ユーザー定義のツール](../../mfc/user-defined-tools.md)します。  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 ポインターを返す、 [CUserTool クラス](../../mfc/reference/cusertool-class.md)指定されたコマンド ID に関連付けられているオブジェクト  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 メニュー コマンドの識別子です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CUserTool クラス](../../mfc/reference/cusertool-class.md)または`CUserTool`-派生オブジェクトの場合は成功した場合。 そうしないと`NULL`です。  
  
### <a name="remarks"></a>コメント  
 `FindTool`が成功すると、戻り値の型は、の型と同じ、`pToolRTC`パラメーターを[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)します。  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 関連付けられているリソース ID を返します、**引数**メニューで、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースの識別子。  
  
### <a name="remarks"></a>コメント  
 `uArgMenuID`のパラメーター [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)リソースの ID を指定します。  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 既定の拡張子を返します、**ファイルを開く** ダイアログ ボックス ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) でを使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、`CString`拡張子を表すオブジェクト。  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 ファイル フィルターを返します、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、`CString`フィルターを格納するオブジェクト。  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 関連付けられているリソース ID を返します、**初期ディレクトリ**メニューで、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースの識別子です。  
  
### <a name="remarks"></a>コメント  
 返された ID が指定された、`uInitDirMenuID`のパラメーター [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)します。  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 アプリケーションに割り当てることができるユーザー ツールの最大数を返します。  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>戻り値  
 割り当てることができるユーザー ツールの最大数。  
  
### <a name="remarks"></a>コメント  
 アプリケーションに割り当てることができるツールの最大数を取得するには、このメソッドを呼び出します。 この数は、範囲内で Id の数、`uiCmdFirst`を通じて、`uiCmdLast`パラメーターに渡すことが[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)します。  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 ユーザー ツールのメニュー項目のプレース ホルダーのコマンド ID を返します。  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プレース ホルダーのコマンド ID。  
  
### <a name="remarks"></a>コメント  
 ユーザー ツールを有効にするのには、呼び出します[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)します。 `uiCmdToolsDummy`パラメーター ツール エントリ コマンドのコマンド ID を指定します。 このメソッドが戻るツール エントリ コマンド id。 メニューでは、その ID を使用する場所には、メニューが表示されるユーザー ツールの一覧で置き換えられます。  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 ユーザー ツールの一覧への参照を返します。  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Const 参照、 [CObList クラス](../../mfc/reference/coblist-class.md)ユーザー ツールの一覧を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ツールのユーザーの一覧を取得するには、このメソッドを呼び出し、 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)オブジェクトを保持します。 各ユーザー ツールは型のオブジェクトによって表される[CUserTool クラス](../../mfc/reference/cusertool-class.md)から派生した型または`CUserTool`です。 型が指定された、`pToolRTC`パラメーターを呼び出すと[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)ユーザー ツールを有効にします。  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 指定されたコマンド ID を持つユーザー ツールに関連付けられているアプリケーションを実行します。  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 ユーザー ツールに関連付けられているメニュー コマンド ID。  
  
### <a name="return-value"></a>戻り値  
 ユーザー ツールに関連付けられているコマンドが正常に実行された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ツールのユーザーに関連付けられているアプリケーションを実行するには、このメソッドの呼び出しで指定されたコマンド ID では`uiCmdId`です。  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 コマンド ID がユーザー ツールに関連付けられているかどうかを判断します。  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 メニュー項目のコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID がユーザー ツール; に関連付けられている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、指定されたコマンド ID がコマンド ID の範囲内かどうかを確認します。 呼び出したときに、範囲を指定する[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)ユーザー ツールを有効にします。  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
 Windows レジストリからユーザー ツールに関する情報を読み込みます。  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 Windows レジストリ キーのパス。  
  
### <a name="return-value"></a>戻り値  
 状態が正常に読み込まれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、のステートを読み込みます、 `CUserToolsManager` Windows レジストリからのオブジェクト。  
  
 通常、このメソッドを直接呼び出すことはできません。 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)はワークスペース初期化プロセスの一部としてそれを呼び出します。  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 ユーザー ツールの一覧で、下の指定されたユーザー ツールを移動します。  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTool`  
 移動するユーザー ツールを指定します。  
  
### <a name="return-value"></a>戻り値  
 ユーザー ツールが正常の下へ移動された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メソッドは失敗、ツールを`pTool`指定内部リストに含まれない場合は、このツールは、一覧の最後に、またはです。  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 ユーザー ツールの一覧上の指定したユーザー ツールを移動します。  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTool`  
 移動するユーザー ツールを指定します。  
  
### <a name="return-value"></a>戻り値  
 ユーザー ツール正常に移動された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メソッドは失敗ツールを`pTool`パラメーターの指定が内部の一覧にない場合は、このツールは、ツールの最初の項目リストまたはです。  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 指定したユーザー ツールをアプリケーションから削除します。  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pTool`  
 削除するユーザー ツールへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ツールが正常に削除します。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ツールが正常に削除された場合、削除`pTool`します。  
  
##  <a name="savestate"></a>CUserToolsManager::SaveState  
 Windows レジストリにユーザー ツールに関する情報を格納します。  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 Windows レジストリ キーへのパス。  
  
### <a name="return-value"></a>戻り値  
 状態が正常に保存されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メソッドの現在の状態を格納する、 `CUserToolsManager` Windows レジストリ内のオブジェクト。  
  
 通常は、このメソッドを直接呼び出す必要はない[CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)アプリケーションのワークスペースのシリアル化プロセスの一環として自動的にはそれを呼び出します。  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 既定の拡張子を指定する、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) でを使用して、**コマンド**フィールドに、**ツール**のタブをクリック、**カスタマイズ** ダイアログ ボックス。  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strDefExt`  
 既定のファイル名拡張子を含む文字列。  
  
### <a name="remarks"></a>コメント  
 既定のファイル名拡張子を指定するには、このメソッドを呼び出して、**ファイルを開く**ユーザー ツールに関連付けるアプリケーションを選択すると表示されるダイアログ ボックス。 既定値は、"exe"です。  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 ファイル フィルターを指定、**ファイルを開く** ダイアログ ボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) でを使用して、**コマンド**フィールドに、**ツール**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strFilter`  
 フィルターを指定します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CUserTool クラス](../../mfc/reference/cusertool-class.md)
