---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 9f56ba33534c76cb1bd60c01a88eedfced45f1fb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884863"
---
# <span data-ttu-id="c9f07-104">0.9.430-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="c9f07-104">0.9.430 - interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="c9f07-105">新しい参照サーバーの available イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="c9f07-105">Event args for the NewBrowserVersionAvailable event.</span></span>

## <span data-ttu-id="c9f07-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c9f07-106">Summary</span></span>

 <span data-ttu-id="c9f07-107">Members</span><span class="sxs-lookup"><span data-stu-id="c9f07-107">Members</span></span>                        | <span data-ttu-id="c9f07-108">説明</span><span class="sxs-lookup"><span data-stu-id="c9f07-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c9f07-109">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="c9f07-109">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="c9f07-110">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="c9f07-110">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

## <span data-ttu-id="c9f07-111">Members</span><span class="sxs-lookup"><span data-stu-id="c9f07-111">Members</span></span>

#### <span data-ttu-id="c9f07-112">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="c9f07-112">get_NewVersion</span></span> 

<span data-ttu-id="c9f07-113">現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。</span><span class="sxs-lookup"><span data-stu-id="c9f07-113">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

> <span data-ttu-id="c9f07-114">パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* NewVersion)</span><span class="sxs-lookup"><span data-stu-id="c9f07-114">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

