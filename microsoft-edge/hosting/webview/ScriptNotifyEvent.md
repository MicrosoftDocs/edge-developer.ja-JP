---
description: Webview コンテンツからアプリケーションに渡される通知文字列を表します。
title: ScriptNotifyEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 22313f2d96ca2c5d4d3554ca40589b9a583c89cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568760"
---
# ScriptNotifyEvent オブジェクト

[Webview](../webview.md)に含まれるコンテンツが JavaScript を使って文字列をアプリケーションに渡すときに発生するイベントを表すオブジェクト。

## プロパティ
    
### callingUri

**Scriptnotifyevent**を発生させたスクリプトが含まれているページの Uniform resource IDENTIFIER (URI) を取得します。

このプロパティは読み取り専用です。

```js
var callingUri = ScriptNotifyEvent.callingUri;
```

#### プロパティ値
Type: **Domstring**

### value

アプリケーションに渡されるメソッド名。

このプロパティは読み取り専用です。

```js
var value = ScriptNotifyEvent.value;
```

#### プロパティ値
Type: **Domstring**