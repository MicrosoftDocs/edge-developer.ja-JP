---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2SourceChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 1e3e9d3f661a6e0643d7094c9127fdf33501624a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880179"
---
# <span data-ttu-id="a4f41-104">0.9.430-インターフェイス ICoreWebView2SourceChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a4f41-104">0.9.430 - interface ICoreWebView2SourceChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a4f41-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4f41-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="a4f41-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4f41-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a4f41-107">呼び出し元は、このインターフェイスを実装して、SourceChanged イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4f41-107">The caller implements this interface to receive the SourceChanged event.</span></span>

## <span data-ttu-id="a4f41-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a4f41-108">Summary</span></span>

 <span data-ttu-id="a4f41-109">Members</span><span class="sxs-lookup"><span data-stu-id="a4f41-109">Members</span></span>                        | <span data-ttu-id="a4f41-110">説明</span><span class="sxs-lookup"><span data-stu-id="a4f41-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a4f41-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="a4f41-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a4f41-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a4f41-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="a4f41-113">Members</span><span class="sxs-lookup"><span data-stu-id="a4f41-113">Members</span></span>

#### <span data-ttu-id="a4f41-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="a4f41-114">Invoke</span></span> 

<span data-ttu-id="a4f41-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a4f41-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a4f41-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview、[ICoreWebView2SourceChangedEventArgs](ICoreWebView2SourceChangedEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="a4f41-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,[ICoreWebView2SourceChangedEventArgs](ICoreWebView2SourceChangedEventArgs.md) \* args)</span></span>

