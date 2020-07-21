---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 4dfe2296312ac3ff3e9c67667c660aafcea38211
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885759"
---
# <span data-ttu-id="f7002-104">0.8.355-インターフェイス IWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="f7002-104">0.8.355 - interface IWebView2WebMessageReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="f7002-105">WebMessageReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="f7002-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="f7002-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f7002-106">Summary</span></span>

 <span data-ttu-id="f7002-107">Members</span><span class="sxs-lookup"><span data-stu-id="f7002-107">Members</span></span>                        | <span data-ttu-id="f7002-108">説明</span><span class="sxs-lookup"><span data-stu-id="f7002-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f7002-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="f7002-109">get_Source</span></span>](#get_source) | <span data-ttu-id="f7002-110">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="f7002-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="f7002-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="f7002-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="f7002-112">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f7002-112">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="f7002-113">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="f7002-113">get_WebMessageAsString</span></span>](#get_webmessageasstring) | <span data-ttu-id="f7002-114">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f7002-114">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="f7002-115">Members</span><span class="sxs-lookup"><span data-stu-id="f7002-115">Members</span></span>

#### <span data-ttu-id="f7002-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="f7002-116">get_Source</span></span> 

<span data-ttu-id="f7002-117">この web メッセージを送信したドキュメントの URI です。</span><span class="sxs-lookup"><span data-stu-id="f7002-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="f7002-118">パブリック HRESULT [get_Source](#get_source)(LPWSTR \* Source)</span><span class="sxs-lookup"><span data-stu-id="f7002-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="f7002-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="f7002-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="f7002-120">このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f7002-120">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="f7002-121">パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span><span class="sxs-lookup"><span data-stu-id="f7002-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="f7002-122">JavaScript オブジェクトを使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f7002-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="f7002-123">たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。</span><span class="sxs-lookup"><span data-stu-id="f7002-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="f7002-124">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="f7002-124">get_WebMessageAsString</span></span> 

<span data-ttu-id="f7002-125">Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f7002-125">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="f7002-126">パブリック HRESULT [get_WebMessageAsString](#get_webmessageasstring)(LPWSTR \* webMessageAsString)</span><span class="sxs-lookup"><span data-stu-id="f7002-126">public HRESULT [get_WebMessageAsString](#get_webmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="f7002-127">投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f7002-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="f7002-128">これは、単純な文字列を使って通信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f7002-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="f7002-129">たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。</span><span class="sxs-lookup"><span data-stu-id="f7002-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

