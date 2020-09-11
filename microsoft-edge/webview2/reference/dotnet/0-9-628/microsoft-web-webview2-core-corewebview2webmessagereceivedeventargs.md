---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebMessageReceivedEventArgs。
ms.openlocfilehash: ab273337307eeef6e8842d337296756877939aff
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012240"
---
# <span data-ttu-id="33fb8-104">WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="33fb8-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

<span data-ttu-id="33fb8-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="33fb8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="33fb8-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="33fb8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="33fb8-107">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="33fb8-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="33fb8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="33fb8-108">Summary</span></span>

 <span data-ttu-id="33fb8-109">Members</span><span class="sxs-lookup"><span data-stu-id="33fb8-109">Members</span></span>                        | <span data-ttu-id="33fb8-110">説明</span><span class="sxs-lookup"><span data-stu-id="33fb8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="33fb8-111">Source</span><span class="sxs-lookup"><span data-stu-id="33fb8-111">Source</span></span>](#source) | <span data-ttu-id="33fb8-112">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="33fb8-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="33fb8-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="33fb8-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="33fb8-114">このメッセージは、WebView コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-114">The message posted from the WebView content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="33fb8-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="33fb8-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="33fb8-116">WebView コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-116">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="33fb8-117">Members</span><span class="sxs-lookup"><span data-stu-id="33fb8-117">Members</span></span>

#### <span data-ttu-id="33fb8-118">Source</span><span class="sxs-lookup"><span data-stu-id="33fb8-118">Source</span></span> 

<span data-ttu-id="33fb8-119">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="33fb8-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="33fb8-120">パブリック文字列 [ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="33fb8-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="33fb8-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="33fb8-121">WebMessageAsJson</span></span> 

<span data-ttu-id="33fb8-122">このメッセージは、WebView コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-122">The message posted from the WebView content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="33fb8-123">パブリック文字列 [Webmessageasjson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="33fb8-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="33fb8-124">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="33fb8-125">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="33fb8-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="33fb8-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="33fb8-127">WebView コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-127">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="33fb8-128">パブリック文字列 [Trygetwebmessageasstring](#trygetwebmessageasstring)()</span><span class="sxs-lookup"><span data-stu-id="33fb8-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="33fb8-129">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="33fb8-130">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="33fb8-131">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

