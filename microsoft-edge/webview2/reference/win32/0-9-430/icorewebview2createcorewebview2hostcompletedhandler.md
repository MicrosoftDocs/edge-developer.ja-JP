---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2CreateCoreWebView2HostCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6a707465fa08667e9915a77fdc93ee018e0f9631
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881124"
---
# <span data-ttu-id="ae78b-104">0.9.430-インターフェイス ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ae78b-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="ae78b-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae78b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="ae78b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae78b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ae78b-107">呼び出し元はこのインターフェイスを実装して、CreateCoreWebView2Host 経由で作成された CoreWebView2Host を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ae78b-107">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="ae78b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ae78b-108">Summary</span></span>

 <span data-ttu-id="ae78b-109">Members</span><span class="sxs-lookup"><span data-stu-id="ae78b-109">Members</span></span>                        | <span data-ttu-id="ae78b-110">説明</span><span class="sxs-lookup"><span data-stu-id="ae78b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ae78b-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="ae78b-111">Invoke</span></span>](#invoke) | <span data-ttu-id="ae78b-112">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ae78b-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ae78b-113">Members</span><span class="sxs-lookup"><span data-stu-id="ae78b-113">Members</span></span>

#### <span data-ttu-id="ae78b-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="ae78b-114">Invoke</span></span> 

<span data-ttu-id="ae78b-115">呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ae78b-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ae78b-116">パブリック HRESULT[呼び出し](#invoke)(hresult Result、[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span><span class="sxs-lookup"><span data-stu-id="ae78b-116">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>

