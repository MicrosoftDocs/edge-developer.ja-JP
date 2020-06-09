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
ms.openlocfilehash: 4183f3a1c60bd9e2bdcff5227426db1f07c313cf
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697519"
---
# <span data-ttu-id="546c8-104">インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="546c8-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="546c8-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="546c8-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="546c8-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="546c8-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="546c8-107">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="546c8-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="546c8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="546c8-108">Summary</span></span>

 <span data-ttu-id="546c8-109">Members</span><span class="sxs-lookup"><span data-stu-id="546c8-109">Members</span></span>                        | <span data-ttu-id="546c8-110">説明</span><span class="sxs-lookup"><span data-stu-id="546c8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="546c8-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="546c8-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="546c8-112">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="546c8-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="546c8-113">Members</span><span class="sxs-lookup"><span data-stu-id="546c8-113">Members</span></span>

#### <span data-ttu-id="546c8-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="546c8-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="546c8-115">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="546c8-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="546c8-116">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="546c8-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

