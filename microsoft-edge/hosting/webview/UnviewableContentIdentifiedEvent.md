---
description: Webview がサポートされていないファイルをダウンロードしようとしていることを示します。
title: UnviewableContentIdentifiedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/25/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: cec85ca2d5458a05cfd88210907523f25fb4af95
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568759"
---
# UnviewableContentIdentifiedEvent オブジェクト

[Webview](../webview.md)が、サポートされていないコンテンツタイプのファイルに移動しようとしていることを示します。 

## プロパティ

### メディア

Unviewable コンテンツのコンテンツタイプを取得します。

このプロパティは読み取り専用です。

```js
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```

#### プロパティ値
Type: **Domstring**

### referer

ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。

このプロパティは読み取り専用です。


```js
var referer = NavigationEventWithReferrer.referer;
```

#### プロパティ値
Type: **Domstring**

### uri

ナビゲーションの送信先の Uniform Resource Identifier (URI)。

このプロパティは読み取り専用です。

```js
var uri = NavigationEventWithReferrer.uri;
```

#### プロパティ値
Type: **Domstring**
