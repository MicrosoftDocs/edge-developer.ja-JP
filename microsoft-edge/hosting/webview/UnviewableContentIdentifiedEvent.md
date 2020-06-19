---
description: Webview がサポートされていないファイルをダウンロードしようとしていることを示します。
title: UnviewableContentIdentifiedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 0179522f3eaf0813531084eb996ee9d392e8249d
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752014"
---
# UnviewableContentIdentifiedEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Webview](../webview.md)が、サポートされていないコンテンツタイプのファイルに移動しようとしていることを示します。  

## プロパティ  

### メディア  

Unviewable コンテンツのコンテンツタイプを取得します。  

このプロパティは読み取り専用です。  

```javascript
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```  

#### プロパティ値  

Type: **Domstring**  

### referer  

ナビゲーションを要求している[webview](../webview.md)のページの Uniform resource IDENTIFIER (URI) です。  

このプロパティは読み取り専用です。  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

#### プロパティ値  

Type: **Domstring**  

### uri  

ナビゲーションの送信先の Uniform Resource Identifier (URI)。  

このプロパティは読み取り専用です。  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### プロパティ値  

Type: **Domstring**  
