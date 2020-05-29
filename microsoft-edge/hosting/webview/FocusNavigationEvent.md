---
description: ナビゲーションの理由と場所を含むフォーカスイベントからのディスパッチされたオブジェクト
title: FocusNavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: b988bcd7ff252b9972bef9a31339a34b4b58d9ee
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569244"
---
# FocusNavigationEvent オブジェクト

[**NavigateFocus**](../webview.md#navigatefocus) / [**Navigationreason**](#navigationreason)と location を含む NavigateFocus[**DepartingFocus**](../webview.md#departingfocus)のディスパッチされたオブジェクト。 

## メソッド

### requestFocus

アプリから webview にフォーカスを移動するために呼び出されます。

### パラメーター

このメソッドにはパラメーターはありません。

### 戻り値

このメソッドに戻り値はありません。

## プロパティ
    
### ナビゲーションの理由

"左"、"上"、"右"、または "下" のいずれかの列挙型の**Navigationreason**。 

このプロパティは読み取り専用です。

```js
var navigationReason = FocusNavigationEvent.navigationReason;
```

#### プロパティ値
種類: **Navigationreason**

### 原点の高さ

フォーカスを与える要素の元の高さの場所。

このプロパティは読み取り専用です。

```js
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```

#### プロパティ値
種類: **float**

### 残りの原点

フォーカスを与える要素の左辺の位置。

このプロパティは読み取り専用です。

```js
var originLeft = FocusNavigationEvent.originLeft;
```

#### プロパティ値
種類: **float**

### 原点の先頭へ

フォーカスを与える要素の起点の上位の位置。

このプロパティは読み取り専用です。

```js
var originTop = FocusNavigationEvent.originTop;
```

#### プロパティ値
種類: **float**

### 原点の幅

フォーカスを与える要素の元の幅。

このプロパティは読み取り専用です。

```js
var originWidth = FocusNavigationEvent.originWidth;
```

#### プロパティ値
種類: **float**

