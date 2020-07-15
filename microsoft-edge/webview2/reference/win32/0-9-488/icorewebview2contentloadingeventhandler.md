---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6f817fd5e602582c47c2785459d2a3987174a7b8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880774"
---
# <span data-ttu-id="c74b9-104">0.9.515-インターフェイス ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="c74b9-104">0.9.515 - interface ICoreWebView2ContentLoadingEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="c74b9-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c74b9-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="c74b9-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c74b9-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="c74b9-107">呼び出し元は、このインターフェイスを実装して ContentLoading イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c74b9-107">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="c74b9-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="c74b9-108">Summary</span></span>

 <span data-ttu-id="c74b9-109">Members</span><span class="sxs-lookup"><span data-stu-id="c74b9-109">Members</span></span>                        | <span data-ttu-id="c74b9-110">説明</span><span class="sxs-lookup"><span data-stu-id="c74b9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c74b9-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="c74b9-111">Invoke</span></span>](#invoke) | <span data-ttu-id="c74b9-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c74b9-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="c74b9-113">Members</span><span class="sxs-lookup"><span data-stu-id="c74b9-113">Members</span></span>

#### <span data-ttu-id="c74b9-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="c74b9-114">Invoke</span></span> 

<span data-ttu-id="c74b9-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c74b9-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c74b9-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](icorewebview2.md) \* webview、 [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="c74b9-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

