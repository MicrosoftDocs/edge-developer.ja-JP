---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 15f3a16f352df90779ac4cb9e91026d8f4fb6767
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880327"
---
# <span data-ttu-id="a1504-104">0.9.515-インターフェイス ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a1504-104">0.9.515 - interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a1504-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1504-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a1504-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1504-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="a1504-107">呼び出し元は、このインターフェイスを実装して WebMessageReceived イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1504-107">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="a1504-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a1504-108">Summary</span></span>

 <span data-ttu-id="a1504-109">Members</span><span class="sxs-lookup"><span data-stu-id="a1504-109">Members</span></span>                        | <span data-ttu-id="a1504-110">説明</span><span class="sxs-lookup"><span data-stu-id="a1504-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a1504-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="a1504-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a1504-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a1504-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="a1504-113">Members</span><span class="sxs-lookup"><span data-stu-id="a1504-113">Members</span></span>

#### <span data-ttu-id="a1504-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="a1504-114">Invoke</span></span> 

<span data-ttu-id="a1504-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a1504-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a1504-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="a1504-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

