---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventArgs2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 7f710b4da71a4a4e61869f06e5d2a4a95a2d0891
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885710"
---
# <span data-ttu-id="26389-104">0.8.355-インターフェイス IWebView2WebResourceRequestedEventArgs2</span><span class="sxs-lookup"><span data-stu-id="26389-104">0.8.355 - interface IWebView2WebResourceRequestedEventArgs2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

<span data-ttu-id="26389-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="26389-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="26389-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="26389-106">Summary</span></span>

 <span data-ttu-id="26389-107">Members</span><span class="sxs-lookup"><span data-stu-id="26389-107">Members</span></span>                        | <span data-ttu-id="26389-108">説明</span><span class="sxs-lookup"><span data-stu-id="26389-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="26389-109">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="26389-109">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="26389-110">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="26389-110">The web resource request contexts.</span></span>

## <span data-ttu-id="26389-111">Members</span><span class="sxs-lookup"><span data-stu-id="26389-111">Members</span></span>

#### <span data-ttu-id="26389-112">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="26389-112">get_ResourceContext</span></span> 

<span data-ttu-id="26389-113">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="26389-113">The web resource request contexts.</span></span>

> <span data-ttu-id="26389-114">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="26389-114">public HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

