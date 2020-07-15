---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 7f227e3b2c45b1088b1ac678477cf1dac5ffed5f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881131"
---
# <span data-ttu-id="ea595-104">0.9.430-インターフェイス ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="ea595-104">0.9.430 - interface ICoreWebView2ContentLoadingEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="ea595-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea595-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="ea595-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea595-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="ea595-107">呼び出し元は、このインターフェイスを実装して ContentLoading イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea595-107">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="ea595-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ea595-108">Summary</span></span>

 <span data-ttu-id="ea595-109">Members</span><span class="sxs-lookup"><span data-stu-id="ea595-109">Members</span></span>                        | <span data-ttu-id="ea595-110">説明</span><span class="sxs-lookup"><span data-stu-id="ea595-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ea595-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="ea595-111">Invoke</span></span>](#invoke) | <span data-ttu-id="ea595-112">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ea595-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="ea595-113">Members</span><span class="sxs-lookup"><span data-stu-id="ea595-113">Members</span></span>

#### <span data-ttu-id="ea595-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="ea595-114">Invoke</span></span> 

<span data-ttu-id="ea595-115">対応するイベントのイベント引数を実装側に提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ea595-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="ea595-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview、[ICoreWebView2ContentLoadingEventArgs](ICoreWebView2ContentLoadingEventArgs.md) \* args)</span><span class="sxs-lookup"><span data-stu-id="ea595-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,[ICoreWebView2ContentLoadingEventArgs](ICoreWebView2ContentLoadingEventArgs.md) \* args)</span></span>

