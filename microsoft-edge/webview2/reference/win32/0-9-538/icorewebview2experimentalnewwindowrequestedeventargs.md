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
ms.openlocfilehash: 1d91bb767045179a5d8de3700f86ff6d92a9ef36
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699115"
---
# <span data-ttu-id="e926b-104">インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e926b-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="e926b-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="e926b-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="e926b-106">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e926b-106">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="e926b-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="e926b-107">Summary</span></span>

 <span data-ttu-id="e926b-108">Members</span><span class="sxs-lookup"><span data-stu-id="e926b-108">Members</span></span>                        | <span data-ttu-id="e926b-109">説明</span><span class="sxs-lookup"><span data-stu-id="e926b-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e926b-110">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="e926b-110">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="e926b-111">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="e926b-111">Window features specified by the window.open call.</span></span>

<span data-ttu-id="e926b-112">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="e926b-112">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="e926b-113">Members</span><span class="sxs-lookup"><span data-stu-id="e926b-113">Members</span></span>

#### <span data-ttu-id="e926b-114">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="e926b-114">get_WindowFeatures</span></span> 

<span data-ttu-id="e926b-115">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="e926b-115">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="e926b-116">パブリック HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="e926b-116">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="e926b-117">これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="e926b-117">These features can be considered for positioning and sizing of new webview windows.</span></span>

