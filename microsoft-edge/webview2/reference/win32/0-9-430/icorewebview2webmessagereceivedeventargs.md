---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f3002c6e7941cea1f632e1df4ee42a8f38a468b6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654549"
---
# <span data-ttu-id="7ee5f-104">インターフェイス ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7ee5f-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="7ee5f-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="7ee5f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="7ee5f-107">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="7ee5f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7ee5f-108">Summary</span></span>

 <span data-ttu-id="7ee5f-109">Members</span><span class="sxs-lookup"><span data-stu-id="7ee5f-109">Members</span></span>                        | <span data-ttu-id="7ee5f-110">説明</span><span class="sxs-lookup"><span data-stu-id="7ee5f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7ee5f-111">get_Source</span><span class="sxs-lookup"><span data-stu-id="7ee5f-111">get_Source</span></span>](#get_source) | <span data-ttu-id="7ee5f-112">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="7ee5f-113">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="7ee5f-113">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="7ee5f-114">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="7ee5f-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="7ee5f-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="7ee5f-116">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="7ee5f-117">Members</span><span class="sxs-lookup"><span data-stu-id="7ee5f-117">Members</span></span>

#### <span data-ttu-id="7ee5f-118">get_Source</span><span class="sxs-lookup"><span data-stu-id="7ee5f-118">get_Source</span></span> 

<span data-ttu-id="7ee5f-119">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="7ee5f-120">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* Source)</span><span class="sxs-lookup"><span data-stu-id="7ee5f-120">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="7ee5f-121">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="7ee5f-121">get_WebMessageAsJson</span></span> 

<span data-ttu-id="7ee5f-122">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="7ee5f-123">パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="7ee5f-123">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="7ee5f-124">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="7ee5f-125">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="7ee5f-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="7ee5f-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="7ee5f-127">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="7ee5f-128">パブリック HRESULT [Trygetwebmessageasstring](#trygetwebmessageasstring)(LPWSTR \* webmessageasstring)</span><span class="sxs-lookup"><span data-stu-id="7ee5f-128">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="7ee5f-129">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="7ee5f-130">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="7ee5f-131">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="7ee5f-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

