---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2WebMessageReceivedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebMessageReceivedEventArgs。
ms.openlocfilehash: 36b5475b7af4537b640aac4bfec43f4850413b88
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010482"
---
# <span data-ttu-id="10ef3-104">0.9.579 クラスの WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="10ef3-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="10ef3-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="10ef3-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="10ef3-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="10ef3-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="10ef3-107">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="10ef3-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="10ef3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="10ef3-108">Summary</span></span>

 <span data-ttu-id="10ef3-109">Members</span><span class="sxs-lookup"><span data-stu-id="10ef3-109">Members</span></span>                        | <span data-ttu-id="10ef3-110">説明</span><span class="sxs-lookup"><span data-stu-id="10ef3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="10ef3-111">Source</span><span class="sxs-lookup"><span data-stu-id="10ef3-111">Source</span></span>](#source) | <span data-ttu-id="10ef3-112">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="10ef3-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="10ef3-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="10ef3-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="10ef3-114">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="10ef3-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="10ef3-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="10ef3-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="10ef3-116">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="10ef3-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="10ef3-117">Members</span><span class="sxs-lookup"><span data-stu-id="10ef3-117">Members</span></span>

#### <span data-ttu-id="10ef3-118">Source</span><span class="sxs-lookup"><span data-stu-id="10ef3-118">Source</span></span> 

<span data-ttu-id="10ef3-119">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="10ef3-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="10ef3-120">パブリック文字列 [ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="10ef3-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="10ef3-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="10ef3-121">WebMessageAsJson</span></span> 

<span data-ttu-id="10ef3-122">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="10ef3-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="10ef3-123">パブリック文字列 [Webmessageasjson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="10ef3-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="10ef3-124">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="10ef3-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="10ef3-125">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="10ef3-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="10ef3-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="10ef3-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="10ef3-127">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="10ef3-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="10ef3-128">パブリック文字列 [Trygetwebmessageasstring](#trygetwebmessageasstring)()</span><span class="sxs-lookup"><span data-stu-id="10ef3-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="10ef3-129">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="10ef3-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="10ef3-130">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="10ef3-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="10ef3-131">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="10ef3-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

