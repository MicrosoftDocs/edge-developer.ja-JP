---
description: HTTP 要求が行われたときに発生するイベント。
title: WebResourceRequestedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 79cff0d8fd68e3b5747008f343b5b46fb8093013
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568756"
---
# <span data-ttu-id="b04f6-104">WebResourceRequestedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b04f6-104">WebResourceRequestedEvent object</span></span>

<span data-ttu-id="b04f6-105">HTTP 要求が行われたときに発生するイベント。</span><span class="sxs-lookup"><span data-stu-id="b04f6-105">An event that is fired when an HTTP request is made.</span></span>

## <span data-ttu-id="b04f6-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b04f6-106">Properties</span></span>

### <span data-ttu-id="b04f6-107">引数</span><span class="sxs-lookup"><span data-stu-id="b04f6-107">args</span></span>

<span data-ttu-id="b04f6-108">リソース要求に関する情報。</span><span class="sxs-lookup"><span data-stu-id="b04f6-108">Information about the resource request.</span></span> <span data-ttu-id="b04f6-109">これは[WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)のようなものです。</span><span class="sxs-lookup"><span data-stu-id="b04f6-109">This is a [Windows.Web.UI.WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs).</span></span>

<span data-ttu-id="b04f6-110">このプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="b04f6-110">This property is read-only.</span></span>

```js
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```

#### <span data-ttu-id="b04f6-111">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="b04f6-111">Property value</span></span>
<span data-ttu-id="b04f6-112">種類: **any**</span><span class="sxs-lookup"><span data-stu-id="b04f6-112">Type: **any**</span></span>

