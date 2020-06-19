---
description: 完成した webview ナビゲーションに関する情報が含まれています。
title: NavigationCompletedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: eb5727ab59dbaf056f05ab4b19450c70f85d595f
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752140"
---
# NavigationCompletedEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Webview](../webview.md)が現在のコンテンツの読み込みを完了したとき、またはナビゲーションに失敗した場合に発生するイベントを表すオブジェクト。  

## プロパティ  

### uri  

ナビゲーションの Uniform Resource Identifier (URI)。  

このプロパティは読み取り専用です。  

```javascript
var uri = NavigationCompletedEvent.uri;
```  

#### プロパティ値  

Type: **Domstring**  

### isSuccess  

ナビゲーションが正常に完了したかどうかを示す値を取得します。  

このプロパティは読み取り専用です。  

```javascript
var isSuccess = NavigationCompletedEvent.isSuccess;
```  

#### プロパティ値  

種類:**ブール**型  

### webErrorStatus  

ナビゲーションに失敗した場合は、理由を示す値を取得します。  

このプロパティは読み取り専用です。  

```javascript
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```  

#### プロパティ値  

種類:**符号なし長**  
