---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6afd1983b90b4412fd3011dc35f192809a9583b7
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881019"
---
# <span data-ttu-id="d0e03-104">0.9.430-インターフェイス ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d0e03-104">0.9.430 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d0e03-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0e03-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="d0e03-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0e03-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d0e03-107">呼び出し元は、このインターフェイスを実装して、履歴変更イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0e03-107">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="d0e03-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d0e03-108">Summary</span></span>

 <span data-ttu-id="d0e03-109">Members</span><span class="sxs-lookup"><span data-stu-id="d0e03-109">Members</span></span>                        | <span data-ttu-id="d0e03-110">説明</span><span class="sxs-lookup"><span data-stu-id="d0e03-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d0e03-111">Invoke</span><span class="sxs-lookup"><span data-stu-id="d0e03-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d0e03-112">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d0e03-112">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="d0e03-113">Members</span><span class="sxs-lookup"><span data-stu-id="d0e03-113">Members</span></span>

#### <span data-ttu-id="d0e03-114">Invoke</span><span class="sxs-lookup"><span data-stu-id="d0e03-114">Invoke</span></span> 

<span data-ttu-id="d0e03-115">イベント引数はなく、args パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="d0e03-115">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="d0e03-116">パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview、IUnknown \* args)</span><span class="sxs-lookup"><span data-stu-id="d0e03-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,IUnknown \* args)</span></span>

