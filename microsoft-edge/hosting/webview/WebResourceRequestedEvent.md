---
description: HTTP 要求が行われたときに発生するイベント。
title: WebResourceRequestedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 3d2bb54cc5d60aec5391f0e3fdd427c8ba8a3dab
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751983"
---
# <span data-ttu-id="4c6be-104">WebResourceRequestedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4c6be-104">WebResourceRequestedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="4c6be-105">HTTP 要求が行われたときに発生するイベント。</span><span class="sxs-lookup"><span data-stu-id="4c6be-105">An event that is fired when an HTTP request is made.</span></span>  

## <span data-ttu-id="4c6be-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c6be-106">Properties</span></span>  

### <span data-ttu-id="4c6be-107">引数</span><span class="sxs-lookup"><span data-stu-id="4c6be-107">args</span></span>  

<span data-ttu-id="4c6be-108">リソース要求に関する情報。</span><span class="sxs-lookup"><span data-stu-id="4c6be-108">Information about the resource request.</span></span>  <span data-ttu-id="4c6be-109">これは[WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)のようなものです。</span><span class="sxs-lookup"><span data-stu-id="4c6be-109">This is a [Windows.Web.UI.WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs).</span></span>  

<span data-ttu-id="4c6be-110">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="4c6be-110">This property is read-only.</span></span>  

```javascript
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```  

#### <span data-ttu-id="4c6be-111">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="4c6be-111">Property value</span></span>  

<span data-ttu-id="4c6be-112">種類: **any**</span><span class="sxs-lookup"><span data-stu-id="4c6be-112">Type: **any**</span></span>  
