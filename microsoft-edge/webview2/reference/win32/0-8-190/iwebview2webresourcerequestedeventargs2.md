---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: c23e6bcd18e3b0fe7d2ee9b279e65fc81fe89d3d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654222"
---
# <span data-ttu-id="14f9a-104">インターフェイス IWebView2WebResourceRequestedEventArgs2</span><span class="sxs-lookup"><span data-stu-id="14f9a-104">interface IWebView2WebResourceRequestedEventArgs2</span></span> 

> [!NOTE]
> <span data-ttu-id="14f9a-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14f9a-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="14f9a-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14f9a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

<span data-ttu-id="14f9a-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="14f9a-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="14f9a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="14f9a-108">Summary</span></span>

 <span data-ttu-id="14f9a-109">Members</span><span class="sxs-lookup"><span data-stu-id="14f9a-109">Members</span></span>                        | <span data-ttu-id="14f9a-110">説明</span><span class="sxs-lookup"><span data-stu-id="14f9a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="14f9a-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="14f9a-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="14f9a-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="14f9a-112">The web resource request contexts.</span></span>

## <span data-ttu-id="14f9a-113">Members</span><span class="sxs-lookup"><span data-stu-id="14f9a-113">Members</span></span>

#### <span data-ttu-id="14f9a-114">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="14f9a-114">get_ResourceContext</span></span> 

<span data-ttu-id="14f9a-115">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="14f9a-115">The web resource request contexts.</span></span>

> <span data-ttu-id="14f9a-116">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="14f9a-116">public HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

