---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b917f309194316b26ee94aa94dc8289ef4430007
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697540"
---
# <span data-ttu-id="fc79f-104">WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="fc79f-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="fc79f-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc79f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="fc79f-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc79f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="fc79f-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="fc79f-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="fc79f-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="fc79f-109">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="fc79f-109">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="fc79f-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="fc79f-110">Summary</span></span>

 <span data-ttu-id="fc79f-111">Members</span><span class="sxs-lookup"><span data-stu-id="fc79f-111">Members</span></span>                        | <span data-ttu-id="fc79f-112">説明</span><span class="sxs-lookup"><span data-stu-id="fc79f-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fc79f-113">Source</span><span class="sxs-lookup"><span data-stu-id="fc79f-113">Source</span></span>](#source) | <span data-ttu-id="fc79f-114">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="fc79f-114">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="fc79f-115">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fc79f-115">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="fc79f-116">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fc79f-116">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="fc79f-117">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fc79f-117">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="fc79f-118">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-118">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="fc79f-119">Members</span><span class="sxs-lookup"><span data-stu-id="fc79f-119">Members</span></span>

#### <span data-ttu-id="fc79f-120">Source</span><span class="sxs-lookup"><span data-stu-id="fc79f-120">Source</span></span> 

<span data-ttu-id="fc79f-121">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="fc79f-121">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="fc79f-122">パブリック文字列[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="fc79f-122">public string [Source](#source)</span></span>

#### <span data-ttu-id="fc79f-123">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fc79f-123">WebMessageAsJson</span></span> 

<span data-ttu-id="fc79f-124">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="fc79f-124">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="fc79f-125">パブリック文字列[Webmessageasjson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="fc79f-125">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="fc79f-126">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-126">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="fc79f-127">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="fc79f-127">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="fc79f-128">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fc79f-128">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="fc79f-129">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-129">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="fc79f-130">パブリック文字列[Trygetwebmessageasstring](#trygetwebmessageasstring)()</span><span class="sxs-lookup"><span data-stu-id="fc79f-130">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="fc79f-131">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-131">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="fc79f-132">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fc79f-132">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="fc79f-133">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="fc79f-133">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

