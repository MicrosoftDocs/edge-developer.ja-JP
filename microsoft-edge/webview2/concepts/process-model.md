---
description: プロセスモデル
title: プロセスモデル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 8548308896815266fbd1e150da979b56cfb268e2
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895564"
---
# <span data-ttu-id="341e9-104">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="341e9-104">Process model</span></span>  

<span data-ttu-id="341e9-105">WebView2 は、Microsoft Edge ブラウザーと同じプロセスモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="341e9-105">WebView2 uses the same process model as the Microsoft Edge browser.</span></span>  <span data-ttu-id="341e9-106">ブラウザープロセスモデルの詳細については、「[最新の web ブラウザーを使用したブラウザーのアーキテクチャ][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="341e9-106">For more information about the browser process model, see [Browser Architecture - Inside look at modern web browser][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture].</span></span> 

<span data-ttu-id="341e9-107">1つのブラウザープロセスは、この記事で説明されているレンダラープロセスおよびその他のユーティリティプロセスと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="341e9-107">One browser process is associated with the renderer processes and other utility processes as described in that article.</span></span>  <span data-ttu-id="341e9-108">さらに、WebView2 の場合、WebView2 を使ってプロセスを要求するホストアプリもあります。</span><span class="sxs-lookup"><span data-stu-id="341e9-108">Additionally, in the case of WebView2, there are host app requesting processes using WebView2.</span></span>  

:::image type="complex" source="../media/process-model-1.png" alt-text="プロセス1" lightbox="../media/process-model-1.png":::
   <span data-ttu-id="341e9-110">プロセス1</span><span class="sxs-lookup"><span data-stu-id="341e9-110">Process 1</span></span>  
:::image-end:::  

<span data-ttu-id="341e9-111">ユーザーデータフォルダーを指定する WebView2 要求処理を行うユーザーセッションのユーザーデータフォルダーごとに、1つのブラウザープロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="341e9-111">One browser process is specified per user data folder in a user session that serve any WebView2 requesting process that specifies that user data folder.</span></span>  <span data-ttu-id="341e9-112">つまり、1つのブラウザープロセスが複数の要求プロセスを処理している可能性があり、1つのプロセスが複数のブラウザープロセスを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="341e9-112">This means one browser process may be serving multiple requesting processes and one requesting process may be using multiple browser processes.</span></span>  

:::image type="complex" source="../media/process-model-2.png" alt-text="プロセス2" lightbox="../media/process-model-2.png":::
   <span data-ttu-id="341e9-114">プロセス2</span><span class="sxs-lookup"><span data-stu-id="341e9-114">Process 2</span></span>  
:::image-end:::  

<span data-ttu-id="341e9-115">ブラウザープロセスには、いくつかの関連するレンダラープロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="341e9-115">A browser process has some number of associated renderer processes.</span></span>  <span data-ttu-id="341e9-116">WebView2 のさまざまなインスタンスで複数のフレームを処理するために、必要に応じてブラウザープロセスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="341e9-116">The browser processes are created as required to service potentially multiple frames in different instances of WebView2.</span></span>  <span data-ttu-id="341e9-117">レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebView2 のインスタンスでレンダリングされた個別の切断元の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="341e9-117">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated instances of WebView2.</span></span>  <span data-ttu-id="341e9-118">サイト分離ブラウザー機能については、前の内容を参照してください。</span><span class="sxs-lookup"><span data-stu-id="341e9-118">The site isolation browser feature is described in the previous content.</span></span>  

<span data-ttu-id="341e9-119">は、 `CoreWebView2Environment` ユーザーデータフォルダーとブラウザープロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="341e9-119">The `CoreWebView2Environment` represents a user data folder and browser process.</span></span>  <span data-ttu-id="341e9-120">このは、 `CoreWebView2` 前に説明したように、サイトの分離に応じて、WebView2 によって、さまざまなレンダラープロセスが使用されるため、いずれかのプロセスのセットに直接対応することはできません。</span><span class="sxs-lookup"><span data-stu-id="341e9-120">The `CoreWebView2` does not directly correspond to any one set of processes since various renderer processes are used by a WebView2 depending on site isolation as previously described.</span></span>  

<span data-ttu-id="341e9-121">これらのブラウザーでのクラッシュとハングに対応し、のイベントを使用してレンダラープロセスを処理することができ `ProcessFailed` `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="341e9-121">You are able to react to crashes and hangs in these browser and renderer processes using the `ProcessFailed` event of `CoreWebView2`.</span></span>  

<span data-ttu-id="341e9-122">のメソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンすることができ `Close` `CoreWebView2Controller` ます。</span><span class="sxs-lookup"><span data-stu-id="341e9-122">You are able to safely shutdown associated browser and renderer processes using the `Close` method of `CoreWebView2Controller`.</span></span>  

<span data-ttu-id="341e9-123">WebView2 インスタンスの [ **devtools** ] ウィンドウからブラウザータスクマネージャーウィンドウを開くには、 `Shift` + `Escape` devtools ウィンドウのタイトルバーを選択するか、または hover でポイントし、コンテキストメニュー \(右クリック \) を開いて、を選択し `Browser task manager` ます。</span><span class="sxs-lookup"><span data-stu-id="341e9-123">To open the Browser Task Manager window from the **DevTools** window of a WebView2 instance, you are able to select `Shift`+`Escape` or hover on the DevTools window title bar, open the contextual menu \(right-click\), and choose `Browser task manager`.</span></span>  <span data-ttu-id="341e9-124">WebView2 のブラウザープロセスに関連付けられたすべてのプロセスが、関連付けられた目的を含めて表示されます。</span><span class="sxs-lookup"><span data-stu-id="341e9-124">All processes associated with the browser process of your WebView2 are displayed including associated purposes.</span></span>  

<!-- links -->  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "ブラウザーのアーキテクチャ-最新の web ブラウザーを表示する (パート 1)"  
