---
description: Webview コンテンツからアプリケーションに渡される通知文字列を表します。
title: ScriptNotifyEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 164bfa7228b1f4ccf9817e4b7231361d090f1394
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752025"
---
# ScriptNotifyEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Webview](../webview.md)に含まれるコンテンツが JavaScript を使って文字列をアプリケーションに渡すときに発生するイベントを表すオブジェクト。  

## プロパティ  

### callingUri  

**Scriptnotifyevent**を発生させたスクリプトが含まれているページの Uniform resource IDENTIFIER (URI) を取得します。  

このプロパティは読み取り専用です。  

```javascript
var callingUri = ScriptNotifyEvent.callingUri;
```  

#### プロパティ値  

Type: **Domstring**  

### value  

アプリケーションに渡されるメソッド名。  

このプロパティは読み取り専用です。  

```javascript
var value = ScriptNotifyEvent.value;
```  

#### プロパティ値  

Type: **Domstring**  
