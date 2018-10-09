---
title: event_source (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 750e51264f12d1c8961ced4e8b606ea5d040d8c9
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791298"
---
# <a name="eventsource"></a>event_source

イベント ソースを作成します。

## <a name="syntax"></a>構文

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>パラメーター

*type*<br/>
次の値のいずれかの列挙です。

- アンマネージ C/C++ コード用の`native` (アンマネージ クラスの既定)。

- COM コード用の`com` 。 使用する必要があります`coclass`とき`type` =`com`します。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
ときに*型*は`native`を指定できます`optimize=size`は 4 バイトのストレージ (最小値) のすべてのイベント クラスで示すために、または`optimize=speed`(既定値) を 4 があることを示すために * (イベントの #) バイトのストレージ。

*装飾します。*<br/>
ときに*型*は`native`を指定できます`decorate=false`を結合 (.mrg) ファイルの拡張名が、外側のクラス名を含める必要がありますいないことを示しています。 [/Fx](../../build/reference/fx-merge-injected-code.md) .mrg ファイルを生成することができます。 `decorate=false`、既定値は、マージされたファイルで完全修飾型名します。

## <a name="remarks"></a>Remarks

**event_source** C++ 属性では、それが適用されているクラスまたは構造がイベント ソースとなることを指定します。

**event_source**と組み合わせて使用は、 [event_receiver](event-receiver.md)属性と[_ _event](../../cpp/event.md)キーワード。 使用`event_receiver`イベント レシーバーを作成します。 使用 **_ _event**イベントとしてこれらのメソッドを指定するイベント ソース内のメソッドにします。

> [!NOTE]
> テンプレート クラスまたは構造体にイベントを含めることはできません。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**コクラス**とき `type`=`com`|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[クラス属性](class-attributes.md)  