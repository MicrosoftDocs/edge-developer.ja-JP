---
description: ナビゲーションに関する参照情報が含まれています
title: NavigationEventWithReferrer 元オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 72c8a213f632e9e74145de9c34b949adf074cd22
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752129"
---
# NavigationEventWithReferrer 元オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

ナビゲーションが開始され、ナビゲーションに referer が含まれているときに発生するイベントを表すオブジェクト。  

## プロパティ  

### referer

ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。  

このプロパティは読み取り専用です。  

#### プロパティ値  

Type: **Domstring**  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

### uri  

ナビゲーションの送信先の Uniform Resource Identifier (URI)。  

このプロパティは読み取り専用です。  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### プロパティ値  

Type: **Domstring**  
