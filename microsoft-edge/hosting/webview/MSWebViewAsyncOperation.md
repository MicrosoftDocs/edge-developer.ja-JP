---
description: 操作が正常に完了したか失敗したかを公開します
title: MSWebViewAsyncOperation オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: d6e03af2a0205938f19120076aa0ad622539d7e5
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752126"
---
# MSWebViewAsyncOperation オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

操作が正常に完了したか失敗したかを公開します。  

## イベント  

### 完了  

操作が完了したことを示します。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```  

#### イベント情報  

|  |  |  
|:--- |:--- |  
| **インターフェイス** | **イベント** |  
| **同期** |はい |  
| **バブル** |なし |   
| **取り消し可能な** |なし |  

### error (エラー)  

操作でエラーがあったことを示します。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```  

#### イベント情報  

|  |  |  
|:--- |:--- |  
| **インターフェイス** | **イベント** |  
| **同期** | はい |  
| **バブル** | なし |  
| **取り消し可能な** | なし |  

## メソッド  

### start  

非同期タスクを開始するために呼び出されます。  

```javascript
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

```javascript
var error = MSWebViewAsyncOperation.error;
```  

#### プロパティ値  

種類: **Domerror**  

### oncomplete  

**Complete**イベントハンドラー。  

```javascript
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```  

#### プロパティ値  

種類: **EventHandler**  

### 時  

**エラー**イベントハンドラー。  

```javascript
var onerror = MSWebViewAsyncOperation.onerror;
```  

#### プロパティ値  

種類: **EventHandler**  

### readyState  

オブジェクトのレディ状態を記述します。  

このプロパティは読み取り専用です。  

```javascript
var readyState = MSWebViewAsyncOperation.readyState;
```  

#### プロパティ値  

種類:**符号なし短い**  

### より  

操作の結果。  

このプロパティは読み取り専用です。  

```javascript
var result = MSWebViewAsyncOperation.result;
```  

#### プロパティ値  

種類: any  

### ターゲット  

操作のターゲット。  

このプロパティは読み取り専用です。  

```javascript
var target = MSWebViewAsyncOperation.target;
```  

#### プロパティ値  

Type: [ **MSHTMLWebViewElement**](../webview.md)  

### 型  

操作の型。  

このプロパティは読み取り専用です。  

```javascript
var type = MSWebViewAsyncOperation.type;
```  

#### プロパティ値  

種類:**符号なし短い**  
