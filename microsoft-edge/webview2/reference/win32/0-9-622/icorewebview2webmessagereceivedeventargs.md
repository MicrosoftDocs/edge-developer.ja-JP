---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebMessageReceivedEventArgs
ms.openlocfilehash: 1a541bc5c735f67013464347781de5163a7c01b2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012369"
---
# <span data-ttu-id="2e452-104">インターフェイス ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="2e452-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="2e452-105">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2e452-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="2e452-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2e452-106">Summary</span></span>

 <span data-ttu-id="2e452-107">Members</span><span class="sxs-lookup"><span data-stu-id="2e452-107">Members</span></span>                        | <span data-ttu-id="2e452-108">説明</span><span class="sxs-lookup"><span data-stu-id="2e452-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2e452-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="2e452-109">get_Source</span></span>](#get_source) | <span data-ttu-id="2e452-110">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="2e452-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="2e452-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="2e452-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="2e452-112">このメッセージは、WebView コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2e452-112">The message posted from the WebView content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="2e452-113">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="2e452-113">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="2e452-114">WebView コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="2e452-114">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="2e452-115">Members</span><span class="sxs-lookup"><span data-stu-id="2e452-115">Members</span></span>

#### <span data-ttu-id="2e452-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="2e452-116">get_Source</span></span> 

<span data-ttu-id="2e452-117">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="2e452-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="2e452-118">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* Source)</span><span class="sxs-lookup"><span data-stu-id="2e452-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="2e452-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="2e452-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="2e452-120">このメッセージは、WebView コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2e452-120">The message posted from the WebView content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="2e452-121">パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="2e452-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="2e452-122">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="2e452-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="2e452-123">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="2e452-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="2e452-124">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="2e452-124">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="2e452-125">WebView コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="2e452-125">If the message posted from the WebView content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="2e452-126">パブリック HRESULT [Trygetwebmessageasstring](#trygetwebmessageasstring)(LPWSTR \* webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="2e452-126">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="2e452-127">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="2e452-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="2e452-128">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="2e452-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="2e452-129">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="2e452-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

