---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ProcessFailedEventArgs
ms.openlocfilehash: 0f4ce5d4922b7a721ce2652fadfa5169a52cb458
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012333"
---
# <span data-ttu-id="3e3e7-104">インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="3e3e7-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="3e3e7-105">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="3e3e7-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3e3e7-106">Summary</span></span>

 <span data-ttu-id="3e3e7-107">Members</span><span class="sxs-lookup"><span data-stu-id="3e3e7-107">Members</span></span>                        | <span data-ttu-id="3e3e7-108">説明</span><span class="sxs-lookup"><span data-stu-id="3e3e7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e3e7-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="3e3e7-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="3e3e7-110">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="3e3e7-111">Members</span><span class="sxs-lookup"><span data-stu-id="3e3e7-111">Members</span></span>

#### <span data-ttu-id="3e3e7-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="3e3e7-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="3e3e7-113">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="3e3e7-114">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="3e3e7-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

