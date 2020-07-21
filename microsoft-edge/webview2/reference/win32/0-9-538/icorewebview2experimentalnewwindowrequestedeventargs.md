---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: d18ccc91d16213cf0a915420b406b65823b3f9d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886452"
---
# <span data-ttu-id="6e330-104">インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6e330-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="6e330-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6e330-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="6e330-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6e330-106">Summary</span></span>

 <span data-ttu-id="6e330-107">Members</span><span class="sxs-lookup"><span data-stu-id="6e330-107">Members</span></span>                        | <span data-ttu-id="6e330-108">説明</span><span class="sxs-lookup"><span data-stu-id="6e330-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e330-109">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="6e330-109">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="6e330-110">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e330-110">Window features specified by the window.open call.</span></span>

<span data-ttu-id="6e330-111">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="6e330-111">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="6e330-112">Members</span><span class="sxs-lookup"><span data-stu-id="6e330-112">Members</span></span>

#### <span data-ttu-id="6e330-113">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="6e330-113">get_WindowFeatures</span></span> 

<span data-ttu-id="6e330-114">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6e330-114">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="6e330-115">パブリック HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="6e330-115">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="6e330-116">これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="6e330-116">These features can be considered for positioning and sizing of new webview windows.</span></span>

