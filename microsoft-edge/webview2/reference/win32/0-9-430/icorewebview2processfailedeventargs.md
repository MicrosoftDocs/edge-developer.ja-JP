---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a19f8c445d7ff1f6bee24cdd8871c28d41eedebe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886412"
---
# <span data-ttu-id="0a45f-104">0.9.430-インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="0a45f-104">0.9.430 - interface ICoreWebView2ProcessFailedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="0a45f-105">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="0a45f-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="0a45f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="0a45f-106">Summary</span></span>

 <span data-ttu-id="0a45f-107">Members</span><span class="sxs-lookup"><span data-stu-id="0a45f-107">Members</span></span>                        | <span data-ttu-id="0a45f-108">説明</span><span class="sxs-lookup"><span data-stu-id="0a45f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0a45f-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="0a45f-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="0a45f-110">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="0a45f-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="0a45f-111">Members</span><span class="sxs-lookup"><span data-stu-id="0a45f-111">Members</span></span>

#### <span data-ttu-id="0a45f-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="0a45f-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="0a45f-113">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="0a45f-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="0a45f-114">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="0a45f-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

