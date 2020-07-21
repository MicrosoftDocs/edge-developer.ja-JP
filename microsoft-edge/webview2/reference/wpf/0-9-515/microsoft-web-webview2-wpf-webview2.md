---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 を WebView2 します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/17/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft のように指定します。
ms.openlocfilehash: e7f5d11b540d1d7ad9630aa674ef5bc0073195c2
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885297"
---
# <span data-ttu-id="68650-104">WebView2 クラスを WebView2 します。</span><span class="sxs-lookup"><span data-stu-id="68650-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="68650-105">名前空間: Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="68650-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="68650-106">アセンブリ: Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="68650-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="68650-107">WPF アプリケーションに web コンテンツを埋め込むためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="68650-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="68650-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="68650-108">Summary</span></span>

 <span data-ttu-id="68650-109">Members</span><span class="sxs-lookup"><span data-stu-id="68650-109">Members</span></span>                        | <span data-ttu-id="68650-110">説明</span><span class="sxs-lookup"><span data-stu-id="68650-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="68650-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="68650-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="68650-112">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="68650-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="68650-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="68650-114">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="68650-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="68650-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="68650-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="68650-116">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="68650-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="68650-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="68650-118">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="68650-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="68650-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="68650-120">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="68650-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="68650-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="68650-122">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="68650-123">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="68650-123">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="68650-124">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="68650-124">The event fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="68650-125">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="68650-125">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="68650-126">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-126">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="68650-127">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="68650-127">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="68650-128">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-128">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="68650-129">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="68650-129">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="68650-130">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="68650-130">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="68650-131">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="68650-131">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="68650-132">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="68650-132">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="68650-133">Source</span><span class="sxs-lookup"><span data-stu-id="68650-133">Source</span></span>](#source) | <span data-ttu-id="68650-134">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="68650-134">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="68650-135">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="68650-135">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="68650-136">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="68650-136">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="68650-137">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="68650-137">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="68650-138">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="68650-138">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="68650-139">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="68650-139">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="68650-140">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="68650-140">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="68650-141">GoBack</span><span class="sxs-lookup"><span data-stu-id="68650-141">GoBack</span></span>](#goback) | <span data-ttu-id="68650-142">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="68650-142">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="68650-143">GoForward</span><span class="sxs-lookup"><span data-stu-id="68650-143">GoForward</span></span>](#goforward) | <span data-ttu-id="68650-144">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="68650-144">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="68650-145">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="68650-145">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="68650-146">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="68650-146">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="68650-147">再</span><span class="sxs-lookup"><span data-stu-id="68650-147">Reload</span></span>](#reload) | <span data-ttu-id="68650-148">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="68650-148">Reloads the current page.</span></span>
[<span data-ttu-id="68650-149">Stop</span><span class="sxs-lookup"><span data-stu-id="68650-149">Stop</span></span>](#stop) | <span data-ttu-id="68650-150">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="68650-150">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="68650-151">WebView2</span><span class="sxs-lookup"><span data-stu-id="68650-151">WebView2</span></span>](#webview2) | <span data-ttu-id="68650-152">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="68650-152">Creates a new instance of a WebView2 control.</span></span>

<span data-ttu-id="68650-153">このコントロールは、実質的には WebView2 COM API を囲むラッパーであり、次のようなドキュメントを見つけることができます。 [https://aka.ms/webview2](https://aka.ms/webview2) CoreWebView2 プロパティにアクセスすると、基になる ICoreWebView2 インターフェイスとそのすべての機能に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68650-153">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="68650-154">最も一般的な COM 機能の一部は、ラッパーメソッド、コントロールのプロパティ、イベントを使って直接アクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="68650-154">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="68650-155">作成時には、コントロールの CoreWebView2 プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="68650-155">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="68650-156">これは、CoreWebView2 を作成することが、エッジブラウザープロセスの起動などの負荷の高い操作であるためです。</span><span class="sxs-lookup"><span data-stu-id="68650-156">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="68650-157">CoreWebView2 を作成するには2つの方法があります。 1) EnsureCoreWebView2Async メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="68650-157">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="68650-158">これは、明示的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68650-158">This is referred to as explicit initialization.</span></span> <span data-ttu-id="68650-159">2) Source プロパティを設定します (たとえば、マークアップから行うことができます)。</span><span class="sxs-lookup"><span data-stu-id="68650-159">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="68650-160">これは暗黙的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="68650-160">This is referred to as implicit initialization.</span></span> <span data-ttu-id="68650-161">どちらのオプションを選択しても、バックグラウンドで初期化が開始され、終了するのを待たずに呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="68650-161">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="68650-162">初期化プロセスに関するオプションを指定するには、独自の CoreWebView2Environment を EnsureCoreWebView2Async に渡すか、または初期化の前にコントロールの "作成用プロパティ" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="68650-162">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="68650-163">(トリガーされた方法に関係なく) 初期化が完了すると、次の処理が行われます。 1) コントロールの CoreWebView2Ready イベントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68650-163">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="68650-164">CoreWebView2 を使用する前に1回限りのセットアップ操作を実行する必要がある場合は、そのイベントのハンドラーで操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="68650-164">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="68650-165">2) ソースプロパティに Uri が設定されている場合、コントロールはバックグラウンドでその Uri への移動を開始します (つまり、ナビゲーションが完了するのを待たずに、これらの手順は続行します)。</span><span class="sxs-lookup"><span data-stu-id="68650-165">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="68650-166">3) EnsureCoreWebView2Async から返されたタスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="68650-166">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="68650-167">初期化プロセスに関係するメソッド、プロパティ、イベントの詳細については、その固有のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-167">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="68650-168">コントロールの CoreWebView2 は非常に重いオブジェクトであるため (実行されている複数のプロセスとディスク領域を使用する可能性があります)、コントロールは IDisposable を実装して、解放する明示的な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="68650-168">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="68650-169">Dispose を呼び出すと、CoreWebView2 とその基になっているリソース (他の WebViews でも使用されているものを除く) が解放され、CoreWebView2 が null にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="68650-169">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="68650-170">Dispose が呼び出された後は、CoreWebView2 を再初期化することはできません。必要な機能を使おうとすると、ObjectDisposedException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-170">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="68650-171">このコントロールは、WPF エコシステムの外部に存在するウィンドウを埋め込むために、HwndHost を拡張します。</span><span class="sxs-lookup"><span data-stu-id="68650-171">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="68650-172">これには、コントロールの入出力動作、および UIElement と FrameworkElement から "継承" する機能について、いくつかの意味があります。</span><span class="sxs-lookup"><span data-stu-id="68650-172">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="68650-173">詳しい情報については、HwndHost と WPF/Win32 の相互運用機能に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-173">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="68650-174">Members</span><span class="sxs-lookup"><span data-stu-id="68650-174">Members</span></span>

#### <span data-ttu-id="68650-175">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="68650-175">ContentLoading</span></span> 

<span data-ttu-id="68650-176">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-176">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="68650-177">パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="68650-177">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="68650-178">このイベントと CoreWebView2 読み込みの唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="68650-178">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="68650-179">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68650-179">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="68650-180">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="68650-180">CoreWebView2Ready</span></span> 

<span data-ttu-id="68650-181">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="68650-181">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="68650-182">パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="68650-182">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="68650-183">このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。</span><span class="sxs-lookup"><span data-stu-id="68650-183">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="68650-184">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-184">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="68650-185">このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="68650-185">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="68650-186">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="68650-186">NavigationCompleted</span></span> 

<span data-ttu-id="68650-187">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-187">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="68650-188">パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="68650-188">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="68650-189">このイベントと CoreWebView2 が完了する唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="68650-189">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="68650-190">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68650-190">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="68650-191">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="68650-191">NavigationStarting</span></span> 

<span data-ttu-id="68650-192">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-192">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="68650-193">パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="68650-193">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="68650-194">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="68650-194">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="68650-195">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68650-195">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="68650-196">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="68650-196">SourceChanged</span></span> 

<span data-ttu-id="68650-197">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-197">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="68650-198">パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="68650-198">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="68650-199">このイベントと CoreWebView2 Echanged の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="68650-199">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="68650-200">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68650-200">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="68650-201">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="68650-201">WebMessageReceived</span></span> 

<span data-ttu-id="68650-202">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="68650-202">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="68650-203">パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="68650-203">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="68650-204">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="68650-204">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="68650-205">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="68650-205">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="68650-206">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="68650-206">ZoomFactorChanged</span></span> 

<span data-ttu-id="68650-207">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="68650-207">The event fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="68650-208">パブリックイベント EventHandler< EventArgs > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="68650-208">public event EventHandler< EventArgs > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="68650-209">このイベントは CoreWebView2Controller を直接公開します。詳細については、ZoomFactorChanged のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-209">This event directly exposes CoreWebView2Controller.ZoomFactorChanged, see its documentation for more info.</span></span>

#### <span data-ttu-id="68650-210">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="68650-210">CanGoBack</span></span> 

<span data-ttu-id="68650-211">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-211">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="68650-212">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="68650-212">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="68650-213">CoreWebView2 の CanGoBack プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="68650-213">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="68650-214">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-214">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="68650-215">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="68650-215">CanGoForward</span></span> 

<span data-ttu-id="68650-216">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-216">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="68650-217">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="68650-217">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="68650-218">CoreWebView2 の CanGoForward プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="68650-218">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="68650-219">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-219">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="68650-220">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="68650-220">CoreWebView2</span></span> 

<span data-ttu-id="68650-221">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="68650-221">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="68650-222">パブリック CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="68650-222">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="68650-223">初期化が完了するまで null を返します。</span><span class="sxs-lookup"><span data-stu-id="68650-223">Returns null until initialization has completed.</span></span> <span data-ttu-id="68650-224">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-224">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="68650-225">例外</span><span class="sxs-lookup"><span data-stu-id="68650-225">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-226">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-226">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="68650-227">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-227">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="68650-228">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-228">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-229">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="68650-229">CreationProperties</span></span> 

<span data-ttu-id="68650-230">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="68650-230">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="68650-231">パブリック CoreWebView2CreationProperties の[プロパティ](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="68650-231">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="68650-232">このプロパティを設定しても、コントロールの CoreWebView2 の初期化が開始された後は機能しません (古い値は保持されます)。</span><span class="sxs-lookup"><span data-stu-id="68650-232">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="68650-233">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-233">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="68650-234">Source</span><span class="sxs-lookup"><span data-stu-id="68650-234">Source</span></span> 

<span data-ttu-id="68650-235">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="68650-235">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="68650-236">パブリック Uri[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="68650-236">public Uri [Source](#source)</span></span>

<span data-ttu-id="68650-237">一般的に、このプロパティを取得することは、CoreWebView2 の CoreWebView2 プロパティを取得して、このプロパティを設定することと同じです (別の値)。 CoreWebView2 で CoreWebView2 の Navigate メソッドを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="68650-237">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property (to a different value) is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="68650-238">Null の値の意味は、"about: blank" と同じです (詳しくは、「解説」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="68650-238">A value of null has the same meaning as "about:blank" (see remarks for more info).</span></span> <span data-ttu-id="68650-239">CoreWebView2 が初期化される前にこのプロパティを取得すると、それに設定された最後の Uri が取得されます。存在しない場合は null (既定値) となります。</span><span class="sxs-lookup"><span data-stu-id="68650-239">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it, or null (the default) if none has been.</span></span> <span data-ttu-id="68650-240">CoreWebView2 を初期化する前にこのプロパティを設定すると、初期化はバックグラウンドで開始されます (まだ進行中ではない場合)。その後、WebView2 は指定した Uri に移動します。</span><span class="sxs-lookup"><span data-stu-id="68650-240">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="68650-241">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-241">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="68650-242">このプロパティが null の場合は、CoreWebView2 に "about: blank" と表示されます (または null に設定されている場合、CoreWebView2 は "about: blank" に移動します)。</span><span class="sxs-lookup"><span data-stu-id="68650-242">If this property is null then the CoreWebView2 will be showing "about:blank" (or if set to null then the CoreWebView2 will be navigated to "about:blank").</span></span> <span data-ttu-id="68650-243">このプロパティには、明示的な値 "about: blank" を指定することもできます。これは、CoreWebView2 に対しても同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="68650-243">It is also possible for this property to have (or be set to) the explicit value "about:blank", which has the same effect on the CoreWebView2.</span></span> <span data-ttu-id="68650-244">つまり、CoreWebView2 に "about: blank" と表示されている場合は、このプロパティの値が null または "about: blank" のいずれかである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68650-244">In other words, if the CoreWebView2 is showing "about:blank", then this property's value might be either null or "about:blank".</span></span> <span data-ttu-id="68650-245">ただし、null と "about: blank" はこのプロパティの個別の値であり、等号として扱われることはありません。</span><span class="sxs-lookup"><span data-stu-id="68650-245">However, null and "about:blank" are distinct values of this property and not treated as equal to each other.</span></span> <span data-ttu-id="68650-246">コントロールの初期化で重要なのは、null (default) から "about: blank" に値を変更しても、暗黙的な初期化が行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="68650-246">This is important for control initialization because it means that changing the value from null (its default) to "about:blank" is still a change and will still trigger implicit initialization.</span></span> 

##### <span data-ttu-id="68650-247">例外</span><span class="sxs-lookup"><span data-stu-id="68650-247">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="68650-248">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-248">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-249">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="68650-249">ZoomFactor</span></span> 

<span data-ttu-id="68650-250">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="68650-250">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="68650-251">パブリックダブル[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="68650-251">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="68650-252">このプロパティは CoreWebView2Controller を直接公開します。詳細については、ZoomFactor のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-252">This property directly exposes CoreWebView2Controller.ZoomFactor, see its documentation for more info.</span></span> <span data-ttu-id="68650-253">CoreWebView2 が初期化される前にこのプロパティを取得すると、設定されていた最後の値が取得されます。存在しない場合は、1.0 (既定値) となります。</span><span class="sxs-lookup"><span data-stu-id="68650-253">Getting this property before the CoreWebView2 has been initialized will retrieve the last value which was set to it, or 1.0 (the default) if none has been.</span></span> <span data-ttu-id="68650-254">CoreWebView2 が初期化される前にこのプロパティに設定された最新の値は、初期化後に設定されます。</span><span class="sxs-lookup"><span data-stu-id="68650-254">The most recent value set to this property before the CoreWebView2 has been initialized will be set on it after initialization.</span></span>

#### <span data-ttu-id="68650-255">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="68650-255">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="68650-256">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="68650-256">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="68650-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span><span class="sxs-lookup"><span data-stu-id="68650-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="68650-258">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-258">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="68650-259">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68650-259">Parameters</span></span>
* `environment` <span data-ttu-id="68650-260">CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="68650-260">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="68650-261">独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="68650-261">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="68650-262">このメソッドに環境を渡すと、"メッセージの送信" プロパティで指定した設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="68650-262">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="68650-263">Null (既定値) を渡すと、"作成中" プロパティに値が設定されていない場合は、既定の環境が自動的に作成されて使用されます。</span><span class="sxs-lookup"><span data-stu-id="68650-263">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="68650-264">返し</span><span class="sxs-lookup"><span data-stu-id="68650-264">Returns</span></span>
<span data-ttu-id="68650-265">バックグラウンドの初期化プロセスを表すタスク。</span><span class="sxs-lookup"><span data-stu-id="68650-265">A Task that represents the background initialization process.</span></span> <span data-ttu-id="68650-266">タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。</span><span class="sxs-lookup"><span data-stu-id="68650-266">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="68650-267">コントロールの CoreWebView2Ready イベントは、タスクが完了する前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="68650-267">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="68650-268">このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="68650-268">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="68650-269">初期化後にこのメソッドを呼び出す場合は、Source プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="68650-269">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="68650-270">このメソッドは非同期であり、タスクを返すため、ほとんどの UI コントロールのほとんどのパブリック機能と同様に、UI スレッドでも呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="68650-270">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="68650-271">例外</span><span class="sxs-lookup"><span data-stu-id="68650-271">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-272">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-272">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="68650-273">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-273">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="68650-274">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-274">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-275">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="68650-275">ExecuteScriptAsync</span></span> 

<span data-ttu-id="68650-276">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="68650-276">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="68650-277">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="68650-277">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="68650-278">CoreWebView2 の CoreWebView2.ExecuteScriptAsync の呼び出しに相当します。</span><span class="sxs-lookup"><span data-stu-id="68650-278">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="68650-279">例外</span><span class="sxs-lookup"><span data-stu-id="68650-279">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-280">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-280">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="68650-281">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-281">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="68650-282">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-282">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="68650-283">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-283">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-284">GoBack</span><span class="sxs-lookup"><span data-stu-id="68650-284">GoBack</span></span> 

<span data-ttu-id="68650-285">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="68650-285">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="68650-286">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="68650-286">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="68650-287">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出しても、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="68650-287">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="68650-288">例外</span><span class="sxs-lookup"><span data-stu-id="68650-288">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-289">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-289">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="68650-290">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-290">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="68650-291">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-291">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-292">GoForward</span><span class="sxs-lookup"><span data-stu-id="68650-292">GoForward</span></span> 

<span data-ttu-id="68650-293">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="68650-293">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="68650-294">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="68650-294">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="68650-295">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出す場合と同等です。</span><span class="sxs-lookup"><span data-stu-id="68650-295">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="68650-296">例外</span><span class="sxs-lookup"><span data-stu-id="68650-296">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-297">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-297">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="68650-298">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-298">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="68650-299">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-299">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-300">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="68650-300">NavigateToString</span></span> 

<span data-ttu-id="68650-301">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="68650-301">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="68650-302">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="68650-302">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="68650-303">CoreWebView2 で CoreWebView2 を呼び出すのと同じ NavigateToString</span><span class="sxs-lookup"><span data-stu-id="68650-303">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="68650-304">例外</span><span class="sxs-lookup"><span data-stu-id="68650-304">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-305">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-305">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="68650-306">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-306">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="68650-307">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-307">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-308">再</span><span class="sxs-lookup"><span data-stu-id="68650-308">Reload</span></span> 

<span data-ttu-id="68650-309">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="68650-309">Reloads the current page.</span></span>

> <span data-ttu-id="68650-310">パブリックの void[再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="68650-310">public void [Reload](#reload)()</span></span>

<span data-ttu-id="68650-311">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="68650-311">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="68650-312">例外</span><span class="sxs-lookup"><span data-stu-id="68650-312">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-313">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-313">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="68650-314">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-314">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="68650-315">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-315">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-316">Stop</span><span class="sxs-lookup"><span data-stu-id="68650-316">Stop</span></span> 

<span data-ttu-id="68650-317">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="68650-317">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="68650-318">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="68650-318">public void [Stop](#stop)()</span></span>

<span data-ttu-id="68650-319">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="68650-319">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="68650-320">例外</span><span class="sxs-lookup"><span data-stu-id="68650-320">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="68650-321">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-321">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="68650-322">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-322">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="68650-323">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="68650-323">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="68650-324">WebView2</span><span class="sxs-lookup"><span data-stu-id="68650-324">WebView2</span></span> 

<span data-ttu-id="68650-325">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="68650-325">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="68650-326">パブリック[WebView2](#webview2)()</span><span class="sxs-lookup"><span data-stu-id="68650-326">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="68650-327">コントロールの CoreWebView2 は、初期化されるまで null になります。</span><span class="sxs-lookup"><span data-stu-id="68650-327">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="68650-328">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68650-328">See the WebView2 class documentation for an initialization overview.</span></span>

