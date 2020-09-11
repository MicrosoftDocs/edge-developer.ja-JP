---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ProcessFailedEventArgs
ms.openlocfilehash: af27c39b2ed9ba197ab1c567bcf18a43c3dee932
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010020"
---
# <span data-ttu-id="e6c1a-104">0.9.579-インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e6c1a-104">0.9.579 - interface ICoreWebView2ProcessFailedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="e6c1a-105">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e6c1a-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="e6c1a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e6c1a-106">Summary</span></span>

 <span data-ttu-id="e6c1a-107">Members</span><span class="sxs-lookup"><span data-stu-id="e6c1a-107">Members</span></span>                        | <span data-ttu-id="e6c1a-108">説明</span><span class="sxs-lookup"><span data-stu-id="e6c1a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e6c1a-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e6c1a-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="e6c1a-110">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="e6c1a-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="e6c1a-111">Members</span><span class="sxs-lookup"><span data-stu-id="e6c1a-111">Members</span></span>

#### <span data-ttu-id="e6c1a-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e6c1a-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="e6c1a-113">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="e6c1a-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="e6c1a-114">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="e6c1a-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

