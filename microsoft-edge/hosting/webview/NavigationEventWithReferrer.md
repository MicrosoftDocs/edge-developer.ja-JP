---
description: ナビゲーションに関する参照情報が含まれています
title: NavigationEventWithReferrer 元オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/22/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: b11f60724387d996d0a730965602b5ead6a84145
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569227"
---
# NavigationEventWithReferrer 元オブジェクト

ナビゲーションが開始され、ナビゲーションに referer が含まれているときに発生するイベントを表すオブジェクト。

## プロパティ

### referer

ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。

このプロパティは読み取り専用です。

#### プロパティ値
Type: **Domstring**


```js
var referer = NavigationEventWithReferrer.referer;
```

### uri

ナビゲーションの送信先の Uniform Resource Identifier (URI)。

このプロパティは読み取り専用です。

```js
var uri = NavigationEventWithReferrer.uri;
```

#### プロパティ値
Type: **Domstring**
