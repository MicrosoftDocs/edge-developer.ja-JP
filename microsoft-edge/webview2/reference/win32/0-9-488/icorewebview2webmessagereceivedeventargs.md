---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c57c0df57915361e2d32024a5512616dea96a923
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654505"
---
# <span data-ttu-id="dc1e2-104">インターフェイス ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="dc1e2-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="dc1e2-105">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="dc1e2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="dc1e2-106">Summary</span></span>

 <span data-ttu-id="dc1e2-107">Members</span><span class="sxs-lookup"><span data-stu-id="dc1e2-107">Members</span></span>                        | <span data-ttu-id="dc1e2-108">説明</span><span class="sxs-lookup"><span data-stu-id="dc1e2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dc1e2-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="dc1e2-109">get_Source</span></span>](#get_source) | <span data-ttu-id="dc1e2-110">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="dc1e2-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="dc1e2-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="dc1e2-112">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-112">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="dc1e2-113">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="dc1e2-113">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="dc1e2-114">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-114">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="dc1e2-115">Members</span><span class="sxs-lookup"><span data-stu-id="dc1e2-115">Members</span></span>

#### <span data-ttu-id="dc1e2-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="dc1e2-116">get_Source</span></span> 

<span data-ttu-id="dc1e2-117">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="dc1e2-118">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* Source)</span><span class="sxs-lookup"><span data-stu-id="dc1e2-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="dc1e2-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="dc1e2-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="dc1e2-120">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-120">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="dc1e2-121">パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="dc1e2-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="dc1e2-122">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="dc1e2-123">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="dc1e2-124">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="dc1e2-124">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="dc1e2-125">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-125">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="dc1e2-126">パブリック HRESULT [Trygetwebmessageasstring](#trygetwebmessageasstring)(LPWSTR \* webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="dc1e2-126">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="dc1e2-127">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="dc1e2-128">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="dc1e2-129">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="dc1e2-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

