---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 0efc1656b8204b9775002db49e0e4a5734682cc4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654177"
---
# <span data-ttu-id="139bf-104">インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="139bf-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="139bf-105">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="139bf-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="139bf-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="139bf-106">Summary</span></span>

 <span data-ttu-id="139bf-107">Members</span><span class="sxs-lookup"><span data-stu-id="139bf-107">Members</span></span>                        | <span data-ttu-id="139bf-108">説明</span><span class="sxs-lookup"><span data-stu-id="139bf-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="139bf-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="139bf-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="139bf-110">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="139bf-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="139bf-111">Members</span><span class="sxs-lookup"><span data-stu-id="139bf-111">Members</span></span>

#### <span data-ttu-id="139bf-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="139bf-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="139bf-113">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="139bf-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="139bf-114">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="139bf-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

