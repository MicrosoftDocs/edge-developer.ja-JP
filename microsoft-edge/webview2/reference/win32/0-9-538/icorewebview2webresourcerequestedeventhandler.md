---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: 3cdafae6480a3bf6e3a5bf96f7e7fba1ae8cc77c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884520"
---
# <span data-ttu-id="7025c-104">インターフェイス ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="7025c-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="7025c-105">AddWebResourceRequestedFilter で指定されている Web リソース一致のリソースコンテキストフィルターと URL に対して、webview で URL 要求 (network、file など) を実行したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7025c-105">Fires when a URL request (through network, file etc.) is made in the webview for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>

## <span data-ttu-id="7025c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="7025c-106">Summary</span></span>

 <span data-ttu-id="7025c-107">Members</span><span class="sxs-lookup"><span data-stu-id="7025c-107">Members</span></span>                        | <span data-ttu-id="7025c-108">説明</span><span class="sxs-lookup"><span data-stu-id="7025c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7025c-109">Invoke</span><span class="sxs-lookup"><span data-stu-id="7025c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="7025c-110">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7025c-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="7025c-111">このホストでは、要求を表示して変更したり、HTTP と同様のパターンで応答を提供したりすることができます。この場合、要求はすぐに完了します。</span><span class="sxs-lookup"><span data-stu-id="7025c-111">The host can view and modify the request or provide a response in a similar pattern to HTTP, in which case the request immediately completed.</span></span> <span data-ttu-id="7025c-112">これには、承認ヘッダーなど、ネットワークスタックによって追加された要求ヘッダーが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7025c-112">This may not contain any request headers that are added by the network stack, such as Authorization headers.</span></span>

## <span data-ttu-id="7025c-113">Members</span><span class="sxs-lookup"><span data-stu-id="7025c-113">Members</span></span>

#### <span data-ttu-id="7025c-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="7025c-114">Invoke</span></span> 

<span data-ttu-id="7025c-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7025c-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="7025c-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="7025c-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

