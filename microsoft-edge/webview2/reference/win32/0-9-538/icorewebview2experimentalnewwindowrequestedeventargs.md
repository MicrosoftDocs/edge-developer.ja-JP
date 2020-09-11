---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: 855425e5cbdd594c7a4bca12efe1827035ca2f3a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011105"
---
# <span data-ttu-id="394ec-104">0.9.579-インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="394ec-104">0.9.579 - interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="394ec-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="394ec-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="394ec-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="394ec-106">Summary</span></span>

 <span data-ttu-id="394ec-107">Members</span><span class="sxs-lookup"><span data-stu-id="394ec-107">Members</span></span>                        | <span data-ttu-id="394ec-108">説明</span><span class="sxs-lookup"><span data-stu-id="394ec-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="394ec-109">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="394ec-109">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="394ec-110">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="394ec-110">Window features specified by the window.open call.</span></span>

<span data-ttu-id="394ec-111">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="394ec-111">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="394ec-112">Members</span><span class="sxs-lookup"><span data-stu-id="394ec-112">Members</span></span>

#### <span data-ttu-id="394ec-113">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="394ec-113">get_WindowFeatures</span></span> 

<span data-ttu-id="394ec-114">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="394ec-114">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="394ec-115">パブリック HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="394ec-115">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="394ec-116">これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="394ec-116">These features can be considered for positioning and sizing of new webview windows.</span></span>

