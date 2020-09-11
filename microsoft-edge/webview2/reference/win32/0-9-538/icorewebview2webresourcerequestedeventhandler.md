---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: a1bf9e05e403df10fc8e45ff5b5bc19f28558e3c
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010374"
---
# <span data-ttu-id="b11b5-104">0.9.579-インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b11b5-104">0.9.579 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="b11b5-105">AddWebResourceRequestedFilter で指定されている Web リソース一致のリソースコンテキストフィルターと URL に対して、webview で URL 要求 (network、file など) を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="b11b5-105">Fires when a URL request (through network, file etc.) is made in the webview for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>

## <span data-ttu-id="b11b5-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b11b5-106">Summary</span></span>

 <span data-ttu-id="b11b5-107">Members</span><span class="sxs-lookup"><span data-stu-id="b11b5-107">Members</span></span>                        | <span data-ttu-id="b11b5-108">説明</span><span class="sxs-lookup"><span data-stu-id="b11b5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b11b5-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="b11b5-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b11b5-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b11b5-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="b11b5-111">このホストでは、要求を表示して変更したり、HTTP と同様のパターンで応答を提供したりすることができます。この場合、要求はすぐに完了します。</span><span class="sxs-lookup"><span data-stu-id="b11b5-111">The host can view and modify the request or provide a response in a similar pattern to HTTP, in which case the request immediately completed.</span></span> <span data-ttu-id="b11b5-112">これには、承認ヘッダーなど、ネットワークスタックによって追加された要求ヘッダーが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b11b5-112">This may not contain any request headers that are added by the network stack, such as Authorization headers.</span></span>

## <span data-ttu-id="b11b5-113">Members</span><span class="sxs-lookup"><span data-stu-id="b11b5-113">Members</span></span>

#### <span data-ttu-id="b11b5-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="b11b5-114">Invoke</span></span> 

<span data-ttu-id="b11b5-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b11b5-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b11b5-116">パブリック HRESULT [呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="b11b5-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

