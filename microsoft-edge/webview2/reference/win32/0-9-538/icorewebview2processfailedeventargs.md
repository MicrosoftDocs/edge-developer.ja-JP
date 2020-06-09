---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c01d98ca997a0b4e288ecaa8ede609c93fc84ea1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698976"
---
# <span data-ttu-id="70c59-104">インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="70c59-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="70c59-105">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="70c59-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="70c59-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="70c59-106">Summary</span></span>

 <span data-ttu-id="70c59-107">Members</span><span class="sxs-lookup"><span data-stu-id="70c59-107">Members</span></span>                        | <span data-ttu-id="70c59-108">説明</span><span class="sxs-lookup"><span data-stu-id="70c59-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="70c59-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="70c59-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="70c59-110">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="70c59-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="70c59-111">Members</span><span class="sxs-lookup"><span data-stu-id="70c59-111">Members</span></span>

#### <span data-ttu-id="70c59-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="70c59-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="70c59-113">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="70c59-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="70c59-114">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="70c59-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

