---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 5ceb24d0d20f580e14e0d5af7ec09881c9ab0eb2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878247"
---
# <span data-ttu-id="e186f-104">0.8.355-インターフェイス IWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e186f-104">0.8.355 - interface IWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="e186f-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e186f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="e186f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e186f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="e186f-107">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e186f-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="e186f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e186f-108">Summary</span></span>

 <span data-ttu-id="e186f-109">Members</span><span class="sxs-lookup"><span data-stu-id="e186f-109">Members</span></span>                        | <span data-ttu-id="e186f-110">説明</span><span class="sxs-lookup"><span data-stu-id="e186f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e186f-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e186f-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="e186f-112">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="e186f-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="e186f-113">Members</span><span class="sxs-lookup"><span data-stu-id="e186f-113">Members</span></span>

#### <span data-ttu-id="e186f-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e186f-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="e186f-115">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="e186f-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="e186f-116">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(WEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="e186f-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

