---
description: 操作が正常に完了したか失敗したかを公開します
title: MSWebViewAsyncOperation オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: ebb89c0fc645ebcd97357af10af2be650d8218b9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569237"
---
# MSWebViewAsyncOperation オブジェクト

操作が正常に完了したか失敗したかを公開します。 

## イベント

### 完了

操作が完了したことを示します。 

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | **イベント**
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |        


### error (エラー)

操作でエラーがあったことを示します。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```

#### イベント情報

|            |      |
|------------|------|
|**インターフェイス** | **イベント**
|**同期** |はい |    
|**バブル**     |なし |   
|**取り消し可能な**  |なし |            


## メソッド

### start

非同期タスクを開始するために呼び出されます。 

```js
MSWebViewAsyncOperation.start();
```

### パラメーター

このメソッドにはパラメーターはありません。

### 戻り値

このメソッドに戻り値はありません。

## プロパティ

### error (エラー)

発生したエラー。

このプロパティは読み取り専用です。

```js
var error = MSWebViewAsyncOperation.error;
```

#### プロパティ値
種類: **Domerror**

### oncomplete

**Complete**イベントハンドラー。 

```js
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```

#### プロパティ値
種類: **EventHandler**

### 時

**エラー**イベントハンドラー。 

```js
var onerror = MSWebViewAsyncOperation.onerror;
```

#### プロパティ値
種類: **EventHandler**

### readyState

オブジェクトのレディ状態を記述します。

このプロパティは読み取り専用です。

```js
var readyState = MSWebViewAsyncOperation.readyState;
```

#### プロパティ値
種類:**符号なし短い**

### より

操作の結果。

このプロパティは読み取り専用です。

```js
var result = MSWebViewAsyncOperation.result;
```

#### プロパティ値
種類: any

### ターゲット

操作のターゲット。 

このプロパティは読み取り専用です。

```js
var target = MSWebViewAsyncOperation.target;
```

#### プロパティ値
Type: [ **MSHTMLWebViewElement**](../webview.md)

### 型

操作の型。

このプロパティは読み取り専用です。

```js
var type = MSWebViewAsyncOperation.type;
```

#### プロパティ値
種類:**符号なし短い**
