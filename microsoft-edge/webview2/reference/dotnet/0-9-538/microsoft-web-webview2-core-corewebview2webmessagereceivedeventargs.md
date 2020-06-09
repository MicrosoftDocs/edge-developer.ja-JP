---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9babcaff5b90e22ea6bac5d5703a54caef6d349d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699118"
---
# <span data-ttu-id="eb309-104">WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="eb309-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

<span data-ttu-id="eb309-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="eb309-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="eb309-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb309-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="eb309-107">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="eb309-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="eb309-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="eb309-108">Summary</span></span>

 <span data-ttu-id="eb309-109">Members</span><span class="sxs-lookup"><span data-stu-id="eb309-109">Members</span></span>                        | <span data-ttu-id="eb309-110">説明</span><span class="sxs-lookup"><span data-stu-id="eb309-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eb309-111">Source</span><span class="sxs-lookup"><span data-stu-id="eb309-111">Source</span></span>](#source) | <span data-ttu-id="eb309-112">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="eb309-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="eb309-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="eb309-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="eb309-114">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="eb309-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="eb309-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="eb309-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="eb309-116">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="eb309-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="eb309-117">Members</span><span class="sxs-lookup"><span data-stu-id="eb309-117">Members</span></span>

#### <span data-ttu-id="eb309-118">Source</span><span class="sxs-lookup"><span data-stu-id="eb309-118">Source</span></span> 

<span data-ttu-id="eb309-119">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="eb309-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="eb309-120">パブリック文字列[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="eb309-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="eb309-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="eb309-121">WebMessageAsJson</span></span> 

<span data-ttu-id="eb309-122">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="eb309-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="eb309-123">パブリック文字列[Webmessageasjson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="eb309-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="eb309-124">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="eb309-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="eb309-125">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="eb309-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="eb309-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="eb309-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="eb309-127">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="eb309-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="eb309-128">パブリック文字列[Trygetwebmessageasstring](#trygetwebmessageasstring)()</span><span class="sxs-lookup"><span data-stu-id="eb309-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="eb309-129">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="eb309-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="eb309-130">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="eb309-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="eb309-131">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="eb309-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
