---
description: Webview プロセスを表します。
title: MSWebViewProcess オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: bb70b0e8eb12c7a7c23d71f01ea24e9084caa156
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752157"
---
# MSWebViewProcess オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Webview](../webview.md)プロセスを表します。  

```javascript
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

```javascript
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```  

このプロパティは読み取り専用です。  

#### プロパティ値  

種類:**ブール**型  

## メソッド  

### CreateWebViewAsync  

特定のプロセスで[webview](../webview.md)を作成します。  

```javascript
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

```javascript
wvprocess.terminate();
```  

#### 戻り値  

このメソッドに戻り値はありません。  
