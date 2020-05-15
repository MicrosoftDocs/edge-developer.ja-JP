---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8fba2759ce0e264dcde515ee1191ec819f26eef9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654384"
---
# <span data-ttu-id="6e103-104">インターフェイス ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6e103-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="6e103-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e103-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="6e103-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e103-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="6e103-107">ProcessFailed イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6e103-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="6e103-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6e103-108">Summary</span></span>

 <span data-ttu-id="6e103-109">Members</span><span class="sxs-lookup"><span data-stu-id="6e103-109">Members</span></span>                        | <span data-ttu-id="6e103-110">説明</span><span class="sxs-lookup"><span data-stu-id="6e103-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e103-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="6e103-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="6e103-112">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="6e103-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="6e103-113">Members</span><span class="sxs-lookup"><span data-stu-id="6e103-113">Members</span></span>

#### <span data-ttu-id="6e103-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="6e103-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="6e103-115">発生したプロセスエラーの種類。</span><span class="sxs-lookup"><span data-stu-id="6e103-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="6e103-116">パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* Processの KIND)</span><span class="sxs-lookup"><span data-stu-id="6e103-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

