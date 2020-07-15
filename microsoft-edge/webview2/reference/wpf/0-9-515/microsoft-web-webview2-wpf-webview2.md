---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 を WebView2 します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft のように指定します。
ms.openlocfilehash: 2dd7bf1035cf5254f4668070d56d2bd2405f1276
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880263"
---
# <span data-ttu-id="8f5ce-104">WebView2 クラスを WebView2 します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="8f5ce-105">名前空間: Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="8f5ce-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="8f5ce-106">アセンブリ: Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="8f5ce-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="8f5ce-107">WPF アプリケーションに web コンテンツを埋め込むためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="8f5ce-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8f5ce-108">Summary</span></span>

 <span data-ttu-id="8f5ce-109">Members</span><span class="sxs-lookup"><span data-stu-id="8f5ce-109">Members</span></span>                        | <span data-ttu-id="8f5ce-110">説明</span><span class="sxs-lookup"><span data-stu-id="8f5ce-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8f5ce-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="8f5ce-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="8f5ce-112">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="8f5ce-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="8f5ce-114">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="8f5ce-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="8f5ce-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="8f5ce-116">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="8f5ce-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="8f5ce-118">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="8f5ce-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="8f5ce-120">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="8f5ce-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="8f5ce-122">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-123">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="8f5ce-123">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="8f5ce-124">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-124">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="8f5ce-125">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="8f5ce-125">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="8f5ce-126">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-126">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="8f5ce-127">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-127">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="8f5ce-128">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-128">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="8f5ce-129">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8f5ce-129">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="8f5ce-130">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-130">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-131">Source</span><span class="sxs-lookup"><span data-stu-id="8f5ce-131">Source</span></span>](#source) | <span data-ttu-id="8f5ce-132">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-132">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="8f5ce-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="8f5ce-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="8f5ce-134">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-134">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="8f5ce-135">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="8f5ce-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="8f5ce-136">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-136">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="8f5ce-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="8f5ce-137">GoBack</span></span>](#goback) | <span data-ttu-id="8f5ce-138">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-138">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="8f5ce-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="8f5ce-139">GoForward</span></span>](#goforward) | <span data-ttu-id="8f5ce-140">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-140">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="8f5ce-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="8f5ce-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="8f5ce-142">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-142">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="8f5ce-143">再</span><span class="sxs-lookup"><span data-stu-id="8f5ce-143">Reload</span></span>](#reload) | <span data-ttu-id="8f5ce-144">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-144">Reloads the current page.</span></span>
[<span data-ttu-id="8f5ce-145">Stop</span><span class="sxs-lookup"><span data-stu-id="8f5ce-145">Stop</span></span>](#stop) | <span data-ttu-id="8f5ce-146">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-146">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="8f5ce-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-147">WebView2</span></span>](#webview2) | <span data-ttu-id="8f5ce-148">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-148">Creates a new instance of a WebView2 control.</span></span>

<span data-ttu-id="8f5ce-149">このコントロールは、実質的には WebView2 COM API を囲むラッパーであり、次のようなドキュメントを見つけることができます。 [https://aka.ms/webview2](https://aka.ms/webview2) CoreWebView2 プロパティにアクセスすると、基になる ICoreWebView2 インターフェイスとそのすべての機能に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-149">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="8f5ce-150">最も一般的な COM 機能の一部は、ラッパーメソッド、コントロールのプロパティ、イベントを使って直接アクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-150">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="8f5ce-151">作成時には、コントロールの CoreWebView2 プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-151">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="8f5ce-152">これは、CoreWebView2 を作成することが、エッジブラウザープロセスの起動などの負荷の高い操作であるためです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-152">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="8f5ce-153">CoreWebView2 を作成するには2つの方法があります。 1) EnsureCoreWebView2Async メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-153">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="8f5ce-154">これは、明示的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-154">This is referred to as explicit initialization.</span></span> <span data-ttu-id="8f5ce-155">2) Source プロパティを設定します (たとえば、マークアップから行うことができます)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-155">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="8f5ce-156">これは暗黙的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-156">This is referred to as implicit initialization.</span></span> <span data-ttu-id="8f5ce-157">どちらのオプションを選択しても、バックグラウンドで初期化が開始され、終了するのを待たずに呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-157">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="8f5ce-158">初期化プロセスに関するオプションを指定するには、独自の CoreWebView2Environment を EnsureCoreWebView2Async に渡すか、または初期化の前にコントロールの "作成用プロパティ" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-158">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="8f5ce-159">(トリガーされた方法に関係なく) 初期化が完了すると、次の処理が行われます。 1) コントロールの CoreWebView2Ready イベントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-159">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="8f5ce-160">CoreWebView2 を使用する前に1回限りのセットアップ操作を実行する必要がある場合は、そのイベントのハンドラーで操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-160">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="8f5ce-161">2) ソースプロパティに Uri が設定されている場合、コントロールはバックグラウンドでその Uri への移動を開始します (つまり、ナビゲーションが完了するのを待たずに、これらの手順は続行します)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-161">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="8f5ce-162">3) EnsureCoreWebView2Async から返されたタスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-162">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="8f5ce-163">初期化プロセスに関係するメソッド、プロパティ、イベントの詳細については、その固有のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-163">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="8f5ce-164">コントロールの CoreWebView2 は非常に重いオブジェクトであるため (実行されている複数のプロセスとディスク領域を使用する可能性があります)、コントロールは IDisposable を実装して、解放する明示的な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-164">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="8f5ce-165">Dispose を呼び出すと、CoreWebView2 とその基になっているリソース (他の WebViews でも使用されているものを除く) が解放され、CoreWebView2 が null にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-165">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="8f5ce-166">Dispose が呼び出された後は、CoreWebView2 を再初期化することはできません。必要な機能を使おうとすると、ObjectDisposedException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-166">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="8f5ce-167">このコントロールは、WPF エコシステムの外部に存在するウィンドウを埋め込むために、HwndHost を拡張します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-167">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="8f5ce-168">これには、コントロールの入出力動作、および UIElement と FrameworkElement から "継承" する機能について、いくつかの意味があります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-168">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="8f5ce-169">詳しい情報については、HwndHost と WPF/Win32 の相互運用機能に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-169">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="8f5ce-170">Members</span><span class="sxs-lookup"><span data-stu-id="8f5ce-170">Members</span></span>

#### <span data-ttu-id="8f5ce-171">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="8f5ce-171">ContentLoading</span></span> 

<span data-ttu-id="8f5ce-172">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-172">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-173">パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-173">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="8f5ce-174">このイベントと CoreWebView2 読み込みの唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-174">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="8f5ce-175">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-175">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="8f5ce-176">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="8f5ce-176">CoreWebView2Ready</span></span> 

<span data-ttu-id="8f5ce-177">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-177">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="8f5ce-178">パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-178">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="8f5ce-179">このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-179">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="8f5ce-180">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-180">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="8f5ce-181">このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-181">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="8f5ce-182">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="8f5ce-182">NavigationCompleted</span></span> 

<span data-ttu-id="8f5ce-183">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-183">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-184">パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-184">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="8f5ce-185">このイベントと CoreWebView2 が完了する唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-185">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="8f5ce-186">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-186">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="8f5ce-187">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="8f5ce-187">NavigationStarting</span></span> 

<span data-ttu-id="8f5ce-188">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-188">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-189">パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-189">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="8f5ce-190">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-190">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="8f5ce-191">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-191">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="8f5ce-192">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="8f5ce-192">SourceChanged</span></span> 

<span data-ttu-id="8f5ce-193">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-193">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-194">パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-194">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="8f5ce-195">このイベントと CoreWebView2 Echanged の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-195">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="8f5ce-196">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-196">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="8f5ce-197">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="8f5ce-197">WebMessageReceived</span></span> 

<span data-ttu-id="8f5ce-198">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-198">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-199">パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-199">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="8f5ce-200">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-200">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="8f5ce-201">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-201">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="8f5ce-202">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="8f5ce-202">CanGoBack</span></span> 

<span data-ttu-id="8f5ce-203">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-203">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="8f5ce-204">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-204">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="8f5ce-205">CoreWebView2 の CanGoBack プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-205">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="8f5ce-206">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-206">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="8f5ce-207">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="8f5ce-207">CanGoForward</span></span> 

<span data-ttu-id="8f5ce-208">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-208">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="8f5ce-209">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-209">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="8f5ce-210">CoreWebView2 の CanGoForward プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-210">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="8f5ce-211">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-211">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="8f5ce-212">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-212">CoreWebView2</span></span> 

<span data-ttu-id="8f5ce-213">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-213">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="8f5ce-214">パブリック CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-214">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="8f5ce-215">初期化が完了するまで null を返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-215">Returns null until initialization has completed.</span></span> <span data-ttu-id="8f5ce-216">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-216">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="8f5ce-217">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-217">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-218">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-218">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="8f5ce-219">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-219">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="8f5ce-220">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-220">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-221">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8f5ce-221">CreationProperties</span></span> 

<span data-ttu-id="8f5ce-222">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-222">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-223">パブリック CoreWebView2CreationProperties の[プロパティ](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-223">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="8f5ce-224">このプロパティを設定しても、コントロールの CoreWebView2 の初期化が開始された後は機能しません (古い値は保持されます)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-224">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="8f5ce-225">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-225">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="8f5ce-226">Source</span><span class="sxs-lookup"><span data-stu-id="8f5ce-226">Source</span></span> 

<span data-ttu-id="8f5ce-227">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-227">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="8f5ce-228">パブリック Uri[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-228">public Uri [Source](#source)</span></span>

<span data-ttu-id="8f5ce-229">一般的に、このプロパティを取得することは、CoreWebView2 の CoreWebView2 プロパティを取得して、このプロパティを設定することと同じです。 CoreWebView2 で CoreWebView2 を呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-229">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="8f5ce-230">CoreWebView2 が初期化される前にこのプロパティを取得すると、それに設定された最後の Uri が取得されます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-230">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it.</span></span> <span data-ttu-id="8f5ce-231">CoreWebView2 を初期化する前にこのプロパティを設定すると、初期化はバックグラウンドで開始されます (まだ進行中ではない場合)。その後、WebView2 は指定した Uri に移動します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-231">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="8f5ce-232">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-232">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="8f5ce-233">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-233">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="8f5ce-234">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-234">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-235">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="8f5ce-235">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="8f5ce-236">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-236">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="8f5ce-237">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-237">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="8f5ce-238">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-238">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="8f5ce-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f5ce-239">Parameters</span></span>
* `environment` <span data-ttu-id="8f5ce-240">CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-240">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="8f5ce-241">独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-241">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="8f5ce-242">このメソッドに環境を渡すと、"メッセージの送信" プロパティで指定した設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-242">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="8f5ce-243">Null (既定値) を渡すと、"作成中" プロパティに値が設定されていない場合は、既定の環境が自動的に作成されて使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-243">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="8f5ce-244">返し</span><span class="sxs-lookup"><span data-stu-id="8f5ce-244">Returns</span></span>
<span data-ttu-id="8f5ce-245">バックグラウンドの初期化プロセスを表すタスク。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-245">A Task that represents the background initialization process.</span></span> <span data-ttu-id="8f5ce-246">タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-246">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="8f5ce-247">コントロールの CoreWebView2Ready イベントは、タスクが完了する前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-247">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="8f5ce-248">このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-248">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="8f5ce-249">初期化後にこのメソッドを呼び出す場合は、Source プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-249">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="8f5ce-250">このメソッドは非同期であり、タスクを返すため、ほとんどの UI コントロールのほとんどのパブリック機能と同様に、UI スレッドでも呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-250">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="8f5ce-251">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-251">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-252">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-252">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="8f5ce-253">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-253">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="8f5ce-254">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-254">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-255">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="8f5ce-255">ExecuteScriptAsync</span></span> 

<span data-ttu-id="8f5ce-256">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-256">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="8f5ce-257">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-257">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="8f5ce-258">CoreWebView2 の CoreWebView2.ExecuteScriptAsync の呼び出しに相当します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-258">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="8f5ce-259">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-259">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-260">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-260">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="8f5ce-261">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-261">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="8f5ce-262">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-262">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="8f5ce-263">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-263">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-264">GoBack</span><span class="sxs-lookup"><span data-stu-id="8f5ce-264">GoBack</span></span> 

<span data-ttu-id="8f5ce-265">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-265">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="8f5ce-266">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="8f5ce-266">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="8f5ce-267">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出しても、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-267">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="8f5ce-268">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-268">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-269">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-269">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="8f5ce-270">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-270">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="8f5ce-271">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-271">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-272">GoForward</span><span class="sxs-lookup"><span data-stu-id="8f5ce-272">GoForward</span></span> 

<span data-ttu-id="8f5ce-273">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-273">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="8f5ce-274">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="8f5ce-274">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="8f5ce-275">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出す場合と同等です。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-275">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="8f5ce-276">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-276">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-277">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-277">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="8f5ce-278">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-278">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="8f5ce-279">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-279">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-280">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="8f5ce-280">NavigateToString</span></span> 

<span data-ttu-id="8f5ce-281">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-281">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="8f5ce-282">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="8f5ce-282">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="8f5ce-283">CoreWebView2 で CoreWebView2 を呼び出すのと同じ NavigateToString</span><span class="sxs-lookup"><span data-stu-id="8f5ce-283">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="8f5ce-284">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-284">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-285">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-285">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="8f5ce-286">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-286">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="8f5ce-287">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-287">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-288">再</span><span class="sxs-lookup"><span data-stu-id="8f5ce-288">Reload</span></span> 

<span data-ttu-id="8f5ce-289">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-289">Reloads the current page.</span></span>

> <span data-ttu-id="8f5ce-290">パブリックの void[再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="8f5ce-290">public void [Reload](#reload)()</span></span>

<span data-ttu-id="8f5ce-291">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-291">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="8f5ce-292">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-292">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-293">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-293">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="8f5ce-294">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-294">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="8f5ce-295">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-295">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-296">Stop</span><span class="sxs-lookup"><span data-stu-id="8f5ce-296">Stop</span></span> 

<span data-ttu-id="8f5ce-297">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-297">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="8f5ce-298">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="8f5ce-298">public void [Stop](#stop)()</span></span>

<span data-ttu-id="8f5ce-299">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-299">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="8f5ce-300">例外</span><span class="sxs-lookup"><span data-stu-id="8f5ce-300">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="8f5ce-301">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-301">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="8f5ce-302">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-302">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="8f5ce-303">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-303">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="8f5ce-304">WebView2</span><span class="sxs-lookup"><span data-stu-id="8f5ce-304">WebView2</span></span> 

<span data-ttu-id="8f5ce-305">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-305">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="8f5ce-306">パブリック[WebView2](#webview2)()</span><span class="sxs-lookup"><span data-stu-id="8f5ce-306">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="8f5ce-307">コントロールの CoreWebView2 は、初期化されるまで null になります。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-307">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="8f5ce-308">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f5ce-308">See the WebView2 class documentation for an initialization overview.</span></span>

