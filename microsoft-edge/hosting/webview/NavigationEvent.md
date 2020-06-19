---
description: Webview ナビゲーションに関する情報が含まれています。
title: NavigationEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 785e9646ff400e7ad229046c7030b51420b1d9ad
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752172"
---
# NavigationEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

ナビゲーションが開始されたときに発生するイベントを表すオブジェクト。  

## プロパティ  

### uri  

ターゲットの Uniform Resource Identifier (URI)。  

このプロパティは読み取り専用です。  

```javascript
var uri = NavigationEvent.uri;
```  

#### プロパティ値  

Type: **Domstring**  
