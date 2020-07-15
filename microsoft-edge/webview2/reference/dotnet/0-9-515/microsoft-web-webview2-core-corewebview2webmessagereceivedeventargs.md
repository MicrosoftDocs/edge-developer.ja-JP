---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2WebMessageReceivedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ff4ebd8dc3a1c78424d57f6c7b5e6f7fc8e99049
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879318"
---
# <span data-ttu-id="aec92-104">0.9.515 クラスの WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="aec92-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="aec92-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aec92-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="aec92-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aec92-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="aec92-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="aec92-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="aec92-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="aec92-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="aec92-109">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="aec92-109">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="aec92-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="aec92-110">Summary</span></span>

 <span data-ttu-id="aec92-111">Members</span><span class="sxs-lookup"><span data-stu-id="aec92-111">Members</span></span>                        | <span data-ttu-id="aec92-112">説明</span><span class="sxs-lookup"><span data-stu-id="aec92-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aec92-113">Source</span><span class="sxs-lookup"><span data-stu-id="aec92-113">Source</span></span>](#source) | <span data-ttu-id="aec92-114">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="aec92-114">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="aec92-115">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="aec92-115">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="aec92-116">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="aec92-116">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="aec92-117">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="aec92-117">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="aec92-118">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="aec92-118">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="aec92-119">Members</span><span class="sxs-lookup"><span data-stu-id="aec92-119">Members</span></span>

#### <span data-ttu-id="aec92-120">Source</span><span class="sxs-lookup"><span data-stu-id="aec92-120">Source</span></span> 

<span data-ttu-id="aec92-121">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="aec92-121">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="aec92-122">パブリック文字列[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="aec92-122">public string [Source](#source)</span></span>

#### <span data-ttu-id="aec92-123">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="aec92-123">WebMessageAsJson</span></span> 

<span data-ttu-id="aec92-124">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="aec92-124">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="aec92-125">パブリック文字列[Webmessageasjson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="aec92-125">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="aec92-126">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="aec92-126">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="aec92-127">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="aec92-127">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="aec92-128">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="aec92-128">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="aec92-129">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="aec92-129">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="aec92-130">パブリック文字列[Trygetwebmessageasstring](#trygetwebmessageasstring)()</span><span class="sxs-lookup"><span data-stu-id="aec92-130">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="aec92-131">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="aec92-131">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="aec92-132">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="aec92-132">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="aec92-133">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="aec92-133">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

