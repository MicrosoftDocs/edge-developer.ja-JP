---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 715af5cbf2bbaf8301e39dce1516019102b61ab1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877330"
---
# <span data-ttu-id="97560-104">0.9.515-インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="97560-104">0.9.515 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="97560-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97560-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="97560-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97560-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="97560-107">Webview で HTTP 要求が行われたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="97560-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="97560-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="97560-108">Summary</span></span>

 <span data-ttu-id="97560-109">Members</span><span class="sxs-lookup"><span data-stu-id="97560-109">Members</span></span>                        | <span data-ttu-id="97560-110">説明</span><span class="sxs-lookup"><span data-stu-id="97560-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="97560-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="97560-111">Invoke</span></span>](#invoke) | <span data-ttu-id="97560-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97560-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="97560-113">ホストは、要求、応答ヘッダー、応答コンテンツを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="97560-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="97560-114">Members</span><span class="sxs-lookup"><span data-stu-id="97560-114">Members</span></span>

#### <span data-ttu-id="97560-115">Invoke</span><span class="sxs-lookup"><span data-stu-id="97560-115">Invoke</span></span> 

<span data-ttu-id="97560-116">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97560-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="97560-117">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="97560-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

