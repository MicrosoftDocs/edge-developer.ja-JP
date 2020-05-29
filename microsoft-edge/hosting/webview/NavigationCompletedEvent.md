---
description: 完成した webview ナビゲーションに関する情報が含まれています。
title: NavigationCompletedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/26/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 11974f0c66d48569ee63c592bdd3b0153db075b1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569233"
---
# NavigationCompletedEvent オブジェクト

[Webview](../webview.md)が現在のコンテンツの読み込みを完了したとき、またはナビゲーションに失敗した場合に発生するイベントを表すオブジェクト。

## プロパティ
    
### uri

ナビゲーションの Uniform Resource Identifier (URI)。

このプロパティは読み取り専用です。

```js
var uri = NavigationCompletedEvent.uri;
```

#### プロパティ値
Type: **Domstring**

### isSuccess

ナビゲーションが正常に完了したかどうかを示す値を取得します。

このプロパティは読み取り専用です。

```js
var isSuccess = NavigationCompletedEvent.isSuccess;
```

#### プロパティ値
種類:**ブール**型

### webErrorStatus

ナビゲーションに失敗した場合は、理由を示す値を取得します。

このプロパティは読み取り専用です。

```js
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```

#### プロパティ値
種類:**符号なし長**
