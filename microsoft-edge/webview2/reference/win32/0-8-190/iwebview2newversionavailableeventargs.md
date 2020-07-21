---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 4271cc1002de70db2803a5bd6d4be73748bf5bbb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885871"
---
# <span data-ttu-id="85fb0-104">0.8.355-インターフェイス IWebView2NewVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="85fb0-104">0.8.355 - interface IWebView2NewVersionAvailableEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="85fb0-105">NewVersionAvailable イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="85fb0-105">Event args for the NewVersionAvailable event.</span></span>

## <span data-ttu-id="85fb0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="85fb0-106">Summary</span></span>

 <span data-ttu-id="85fb0-107">Members</span><span class="sxs-lookup"><span data-stu-id="85fb0-107">Members</span></span>                        | <span data-ttu-id="85fb0-108">説明</span><span class="sxs-lookup"><span data-stu-id="85fb0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="85fb0-109">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="85fb0-109">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="85fb0-110">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="85fb0-110">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="85fb0-111">Members</span><span class="sxs-lookup"><span data-stu-id="85fb0-111">Members</span></span>

#### <span data-ttu-id="85fb0-112">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="85fb0-112">get_NewVersion</span></span> 

<span data-ttu-id="85fb0-113">現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="85fb0-113">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

> <span data-ttu-id="85fb0-114">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="85fb0-114">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

