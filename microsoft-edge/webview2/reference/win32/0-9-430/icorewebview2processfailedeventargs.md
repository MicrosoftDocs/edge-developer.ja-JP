---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f4238f0d75f39727260296703e84740ca77b30d4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877738"
---
# <span data-ttu-id="6b19c-104">0.9.430-インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6b19c-104">0.9.430 - interface ICoreWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="6b19c-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b19c-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="6b19c-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b19c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="6b19c-107">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6b19c-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="6b19c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6b19c-108">Summary</span></span>

 <span data-ttu-id="6b19c-109">Members</span><span class="sxs-lookup"><span data-stu-id="6b19c-109">Members</span></span>                        | <span data-ttu-id="6b19c-110">説明</span><span class="sxs-lookup"><span data-stu-id="6b19c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6b19c-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="6b19c-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="6b19c-112">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="6b19c-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="6b19c-113">Members</span><span class="sxs-lookup"><span data-stu-id="6b19c-113">Members</span></span>

#### <span data-ttu-id="6b19c-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="6b19c-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="6b19c-115">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="6b19c-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="6b19c-116">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="6b19c-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

