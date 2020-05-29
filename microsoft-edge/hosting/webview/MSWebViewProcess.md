---
description: Webview プロセスを表します。
title: MSWebViewProcess オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 7581f6da3a23295180c50f6d41cc282ce998b64e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569236"
---
# MSWebViewProcess オブジェクト

[Webview](../webview.md)プロセスを表します。

```js
var wvprocess = new MSWebViewProcess();
```

## プロパティ

### enterpriseId

プロセスのエンタープライズ ID です。

```js
var enterpriseId = wvprocess.enterpriseId;
```

このプロパティは読み取り専用です。

#### プロパティ値
Type: **Domstring**

### isPrivateNetworkClientServerCapabilityEnabled

[Webview](../webview.md)プロセスの*プライベートネットワーク (クライアント & Server)* ユニバーサル Windows[アプリ機能の宣言](/windows/uwp/packaging/app-capability-declarations)がアプリマニフェストで有効になっているかどうかを示す値を取得します。

```js
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```

このプロパティは読み取り専用です。

#### プロパティ値
種類:**ブール**型

## メソッド

### CreateWebViewAsync

特定のプロセスで[webview](../webview.md)を作成します。

```js
wvprocess.createWebviewAsync();
```

#### 戻り値

種類**`Promise<MSHTMLWebViewElement>`**

### GetWebViews

プロセス内でホストされている**Mswebviewprocess**オブジェクトのシーケンスを返します。

#### 戻り値

種類**`sequence<MSHTMLWebViewElement>`**

### Terminate

プロセスを終了します。

```js
wvprocess.terminate();
```

#### 戻り値

このメソッドに戻り値はありません。
