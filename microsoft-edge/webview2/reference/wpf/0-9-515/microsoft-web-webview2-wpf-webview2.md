---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f2c3bcb5334abc907a838971ebc1773b6485194f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654241"
---
# <span data-ttu-id="caff9-104">WebView2 クラスを WebView2 します。</span><span class="sxs-lookup"><span data-stu-id="caff9-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="caff9-105">名前空間: Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="caff9-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="caff9-106">"WebView2" というアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="caff9-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="caff9-107">WPF アプリケーションに web コンテンツを埋め込むためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="caff9-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="caff9-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="caff9-108">Summary</span></span>

 <span data-ttu-id="caff9-109">Members</span><span class="sxs-lookup"><span data-stu-id="caff9-109">Members</span></span>                        | <span data-ttu-id="caff9-110">説明</span><span class="sxs-lookup"><span data-stu-id="caff9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="caff9-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="caff9-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="caff9-112">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="caff9-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="caff9-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="caff9-114">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="caff9-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="caff9-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="caff9-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="caff9-116">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="caff9-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="caff9-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="caff9-118">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="caff9-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="caff9-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="caff9-120">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="caff9-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="caff9-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="caff9-122">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="caff9-123">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="caff9-123">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="caff9-124">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-124">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="caff9-125">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="caff9-125">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="caff9-126">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-126">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="caff9-127">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-127">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="caff9-128">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="caff9-128">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="caff9-129">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="caff9-129">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="caff9-130">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="caff9-130">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="caff9-131">Source</span><span class="sxs-lookup"><span data-stu-id="caff9-131">Source</span></span>](#source) | <span data-ttu-id="caff9-132">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="caff9-132">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="caff9-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="caff9-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="caff9-134">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="caff9-134">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="caff9-135">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="caff9-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="caff9-136">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="caff9-136">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="caff9-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="caff9-137">GoBack</span></span>](#goback) | <span data-ttu-id="caff9-138">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="caff9-138">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="caff9-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="caff9-139">GoForward</span></span>](#goforward) | <span data-ttu-id="caff9-140">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="caff9-140">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="caff9-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="caff9-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="caff9-142">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="caff9-142">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="caff9-143">再</span><span class="sxs-lookup"><span data-stu-id="caff9-143">Reload</span></span>](#reload) | <span data-ttu-id="caff9-144">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="caff9-144">Reloads the current page.</span></span>
[<span data-ttu-id="caff9-145">Stop</span><span class="sxs-lookup"><span data-stu-id="caff9-145">Stop</span></span>](#stop) | <span data-ttu-id="caff9-146">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="caff9-146">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="caff9-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-147">WebView2</span></span>](#webview2) | <span data-ttu-id="caff9-148">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="caff9-148">Creates a new instance of a WebView2 control.</span></span>
[<span data-ttu-id="caff9-149">BuildWindowCore</span><span class="sxs-lookup"><span data-stu-id="caff9-149">BuildWindowCore</span></span>](#buildwindowcore) | <span data-ttu-id="caff9-150">これは HwndHost からオーバーライドされ、HWND の作成を指示するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-150">This is overridden from HwndHost and is called to instruct us to create our HWND.</span></span>
[<span data-ttu-id="caff9-151">DestroyWindowCore</span><span class="sxs-lookup"><span data-stu-id="caff9-151">DestroyWindowCore</span></span>](#destroywindowcore) | <span data-ttu-id="caff9-152">これは HwndHost からオーバーライドされ、HWND の破棄を指示するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-152">This is overridden from HwndHost and is called to instruct us to destroy our HWND.</span></span>
[<span data-ttu-id="caff9-153">破棄</span><span class="sxs-lookup"><span data-stu-id="caff9-153">Dispose</span></span>](#dispose) | <span data-ttu-id="caff9-154">これは、IDispose パターンの一般的な実装に従って、基本クラスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-154">This is called by our base class according to the typical implementation of the IDispose pattern.</span></span>
[<span data-ttu-id="caff9-155">HasFocusWithinCore</span><span class="sxs-lookup"><span data-stu-id="caff9-155">HasFocusWithinCore</span></span>](#hasfocuswithincore) | <span data-ttu-id="caff9-156">これは、HwndHost からオーバーライドされ、フォーカスがコントロールとウィンドウのどちらにあるかを WPF が認識する必要があるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-156">This is overridden from HwndHost and is called when WPF needs to know if the focus is in our control/window.</span></span>
[<span data-ttu-id="caff9-157">OnKeyDown</span><span class="sxs-lookup"><span data-stu-id="caff9-157">OnKeyDown</span></span>](#onkeydown) | <span data-ttu-id="caff9-158">これは UIElement から呼び出され、キー入力の入力を処理できるようにするために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-158">This is overridden from UIElement and called to allow us to handle key press input.</span></span>
[<span data-ttu-id="caff9-159">OnKeyUp</span><span class="sxs-lookup"><span data-stu-id="caff9-159">OnKeyUp</span></span>](#onkeyup) | <span data-ttu-id="caff9-160">「Control.onkeydown」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caff9-160">See OnKeyDown.</span></span>
[<span data-ttu-id="caff9-161">Onpreview Keydown</span><span class="sxs-lookup"><span data-stu-id="caff9-161">OnPreviewKeyDown</span></span>](#onpreviewkeydown) | <span data-ttu-id="caff9-162">これは "プレビュー" です (例:</span><span class="sxs-lookup"><span data-stu-id="caff9-162">This is the "Preview" (i.e.</span></span>
[<span data-ttu-id="caff9-163">Onpreview Keyup</span><span class="sxs-lookup"><span data-stu-id="caff9-163">OnPreviewKeyUp</span></span>](#onpreviewkeyup) | <span data-ttu-id="caff9-164">詳しくは、「Onpreview Keydown」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caff9-164">See OnPreviewKeyDown.</span></span>
[<span data-ttu-id="caff9-165">OnWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="caff9-165">OnWindowPositionChanged</span></span>](#onwindowpositionchanged) | <span data-ttu-id="caff9-166">これは、コントロールの位置が変わったときに HwndHost によってオーバーライドされて呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-166">This is overridden from HwndHost and called when our control's location has changed.</span></span>
[<span data-ttu-id="caff9-167">タブの基本</span><span class="sxs-lookup"><span data-stu-id="caff9-167">TabIntoCore</span></span>](#tabintocore) | <span data-ttu-id="caff9-168">これは、HwndHost によって上書きされ、tab キーを使ってコントロール/ウィンドウにフォーカスが移動したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="caff9-168">This is overridden from HwndHost and is called to inform us that tabbing has caused the focus to move into our control/window.</span></span>

<span data-ttu-id="caff9-169">このコントロールは、実質的には WebView2 COM API を囲むラッパーであり、次のようなドキュメントを見つけることができます。 [https://aka.ms/webview2](https://aka.ms/webview2) CoreWebView2 プロパティにアクセスすると、基になる ICoreWebView2 インターフェイスとそのすべての機能に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="caff9-169">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="caff9-170">最も一般的な COM 機能の一部は、ラッパーメソッド、コントロールのプロパティ、イベントを使って直接アクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="caff9-170">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="caff9-171">作成時には、コントロールの CoreWebView2 プロパティは null になります。</span><span class="sxs-lookup"><span data-stu-id="caff9-171">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="caff9-172">これは、CoreWebView2 を作成することが、エッジブラウザープロセスの起動などの負荷の高い操作であるためです。</span><span class="sxs-lookup"><span data-stu-id="caff9-172">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="caff9-173">CoreWebView2 を作成するには2つの方法があります。 1) EnsureCoreWebView2Async メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="caff9-173">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="caff9-174">これは、明示的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="caff9-174">This is referred to as explicit initialization.</span></span> <span data-ttu-id="caff9-175">2) Source プロパティを設定します (たとえば、マークアップから行うことができます)。</span><span class="sxs-lookup"><span data-stu-id="caff9-175">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="caff9-176">これは暗黙的な初期化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="caff9-176">This is referred to as implicit initialization.</span></span> <span data-ttu-id="caff9-177">どちらのオプションを選択しても、バックグラウンドで初期化が開始され、終了するのを待たずに呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-177">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="caff9-178">初期化プロセスに関するオプションを指定するには、独自の CoreWebView2Environment を EnsureCoreWebView2Async に渡すか、または初期化の前にコントロールの "作成用プロパティ" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="caff9-178">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="caff9-179">(トリガーされた方法に関係なく) 初期化が完了すると、次の処理が行われます。 1) コントロールの CoreWebView2Ready イベントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-179">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="caff9-180">CoreWebView2 を使用する前に1回限りのセットアップ操作を実行する必要がある場合は、そのイベントのハンドラーで操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="caff9-180">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="caff9-181">2) ソースプロパティに Uri が設定されている場合、コントロールはバックグラウンドでその Uri への移動を開始します (つまり、ナビゲーションが完了するのを待たずに、これらの手順は続行します)。</span><span class="sxs-lookup"><span data-stu-id="caff9-181">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="caff9-182">3) EnsureCoreWebView2Async から返されたタスクが完了します。</span><span class="sxs-lookup"><span data-stu-id="caff9-182">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="caff9-183">初期化プロセスに関係するメソッド、プロパティ、イベントの詳細については、その固有のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-183">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="caff9-184">コントロールの CoreWebView2 は非常に重いオブジェクトであるため (実行されている複数のプロセスとディスク領域を使用する可能性があります)、コントロールは IDisposable を実装して、解放する明示的な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="caff9-184">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="caff9-185">Dispose を呼び出すと、CoreWebView2 とその基になっているリソース (他の WebViews でも使用されているものを除く) が解放され、CoreWebView2 が null にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-185">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="caff9-186">Dispose が呼び出された後は、CoreWebView2 を再初期化することはできません。必要な機能を使おうとすると、ObjectDisposedException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-186">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="caff9-187">このコントロールは、WPF エコシステムの外部に存在するウィンドウを埋め込むために、HwndHost を拡張します。</span><span class="sxs-lookup"><span data-stu-id="caff9-187">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="caff9-188">これには、コントロールの入出力動作、および UIElement と FrameworkElement から "継承" する機能について、いくつかの意味があります。</span><span class="sxs-lookup"><span data-stu-id="caff9-188">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="caff9-189">詳しい情報については、HwndHost と WPF/Win32 の相互運用機能に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-189">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="caff9-190">Members</span><span class="sxs-lookup"><span data-stu-id="caff9-190">Members</span></span>

#### <span data-ttu-id="caff9-191">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="caff9-191">ContentLoading</span></span> 

<span data-ttu-id="caff9-192">CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-192">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="caff9-193">パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="caff9-193">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="caff9-194">このイベントと CoreWebView2 読み込みの唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="caff9-194">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="caff9-195">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-195">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="caff9-196">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="caff9-196">CoreWebView2Ready</span></span> 

<span data-ttu-id="caff9-197">このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="caff9-197">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="caff9-198">パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="caff9-198">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="caff9-199">このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。</span><span class="sxs-lookup"><span data-stu-id="caff9-199">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="caff9-200">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-200">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="caff9-201">このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="caff9-201">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="caff9-202">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="caff9-202">NavigationCompleted</span></span> 

<span data-ttu-id="caff9-203">CoreWebView2 の CoreWebView2 イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-203">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="caff9-204">パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="caff9-204">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="caff9-205">このイベントと CoreWebView2 が完了する唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="caff9-205">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="caff9-206">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-206">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="caff9-207">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="caff9-207">NavigationStarting</span></span> 

<span data-ttu-id="caff9-208">CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-208">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="caff9-209">パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="caff9-209">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="caff9-210">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="caff9-210">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="caff9-211">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-211">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="caff9-212">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="caff9-212">SourceChanged</span></span> 

<span data-ttu-id="caff9-213">CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-213">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="caff9-214">パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="caff9-214">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="caff9-215">このイベントと CoreWebView2 Echanged の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="caff9-215">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="caff9-216">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-216">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="caff9-217">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="caff9-217">WebMessageReceived</span></span> 

<span data-ttu-id="caff9-218">CoreWebView2 の WebMessageReceived イベントを囲むラッパー。</span><span class="sxs-lookup"><span data-stu-id="caff9-218">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="caff9-219">パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="caff9-219">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="caff9-220">このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="caff9-220">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="caff9-221">このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="caff9-221">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="caff9-222">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="caff9-222">CanGoBack</span></span> 

<span data-ttu-id="caff9-223">ナビゲーション履歴で前のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-223">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="caff9-224">public bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="caff9-224">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="caff9-225">CoreWebView2 の CanGoBack プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-225">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="caff9-226">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-226">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="caff9-227">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="caff9-227">CanGoForward</span></span> 

<span data-ttu-id="caff9-228">ナビゲーション履歴の次のページに移動できる場合は true を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-228">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="caff9-229">public bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="caff9-229">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="caff9-230">CoreWebView2 の CanGoForward プロパティを囲むラッパー。 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-230">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="caff9-231">CoreWebView2 がまだ初期化されていない場合は、false を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-231">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="caff9-232">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-232">CoreWebView2</span></span> 

<span data-ttu-id="caff9-233">CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="caff9-233">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="caff9-234">パブリック CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="caff9-234">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="caff9-235">初期化が完了するまで null を返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-235">Returns null until initialization has completed.</span></span> <span data-ttu-id="caff9-236">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-236">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="caff9-237">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-237">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-238">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-238">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="caff9-239">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-239">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="caff9-240">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-240">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-241">プロパティのプロパティ</span><span class="sxs-lookup"><span data-stu-id="caff9-241">CreationProperties</span></span> 

<span data-ttu-id="caff9-242">コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="caff9-242">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="caff9-243">パブリック CoreWebView2CreationProperties の[プロパティ](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="caff9-243">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="caff9-244">このプロパティを設定しても、コントロールの CoreWebView2 の初期化が開始された後は機能しません (古い値は保持されます)。</span><span class="sxs-lookup"><span data-stu-id="caff9-244">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="caff9-245">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-245">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="caff9-246">Source</span><span class="sxs-lookup"><span data-stu-id="caff9-246">Source</span></span> 

<span data-ttu-id="caff9-247">WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="caff9-247">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="caff9-248">パブリック Uri[ソース](#source)</span><span class="sxs-lookup"><span data-stu-id="caff9-248">public Uri [Source](#source)</span></span>

<span data-ttu-id="caff9-249">一般的に、このプロパティを取得することは、CoreWebView2 の CoreWebView2 プロパティを取得して、このプロパティを設定することと同じです。 CoreWebView2 で CoreWebView2 を呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="caff9-249">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="caff9-250">CoreWebView2 が初期化される前にこのプロパティを取得すると、それに設定された最後の Uri が取得されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-250">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it.</span></span> <span data-ttu-id="caff9-251">CoreWebView2 を初期化する前にこのプロパティを設定すると、初期化はバックグラウンドで開始されます (まだ進行中ではない場合)。その後、WebView2 は指定した Uri に移動します。</span><span class="sxs-lookup"><span data-stu-id="caff9-251">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="caff9-252">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-252">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="caff9-253">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-253">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="caff9-254">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-254">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-255">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="caff9-255">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="caff9-256">コントロールの CoreWebView2 の初期化を明示的にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="caff9-256">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="caff9-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span><span class="sxs-lookup"><span data-stu-id="caff9-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="caff9-258">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-258">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="caff9-259">パラメーター</span><span class="sxs-lookup"><span data-stu-id="caff9-259">Parameters</span></span>
* `environment` <span data-ttu-id="caff9-260">CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="caff9-260">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="caff9-261">独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="caff9-261">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="caff9-262">このメソッドに環境を渡すと、"メッセージの送信" プロパティで指定した設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-262">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="caff9-263">Null (既定値) を渡すと、"作成中" プロパティに値が設定されていない場合は、既定の環境が自動的に作成されて使用されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-263">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="caff9-264">返し</span><span class="sxs-lookup"><span data-stu-id="caff9-264">Returns</span></span>
<span data-ttu-id="caff9-265">バックグラウンドの初期化プロセスを表すタスク。</span><span class="sxs-lookup"><span data-stu-id="caff9-265">A Task that represents the background initialization process.</span></span> <span data-ttu-id="caff9-266">タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。</span><span class="sxs-lookup"><span data-stu-id="caff9-266">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="caff9-267">コントロールの CoreWebView2Ready イベントは、タスクが完了する前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-267">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="caff9-268">このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-268">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="caff9-269">初期化後にこのメソッドを呼び出す場合は、Source プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。</span><span class="sxs-lookup"><span data-stu-id="caff9-269">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="caff9-270">このメソッドは非同期であり、タスクを返すため、ほとんどの UI コントロールのほとんどのパブリック機能と同様に、UI スレッドでも呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="caff9-270">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="caff9-271">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-271">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-272">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-272">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="caff9-273">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-273">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="caff9-274">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-274">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-275">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="caff9-275">ExecuteScriptAsync</span></span> 

<span data-ttu-id="caff9-276">WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="caff9-276">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="caff9-277">パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)</span><span class="sxs-lookup"><span data-stu-id="caff9-277">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="caff9-278">CoreWebView2 で CoreWebView2 を呼び出す場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="caff9-278">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="caff9-279">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-279">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-280">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-280">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="caff9-281">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-281">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="caff9-282">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-282">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="caff9-283">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-283">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-284">GoBack</span><span class="sxs-lookup"><span data-stu-id="caff9-284">GoBack</span></span> 

<span data-ttu-id="caff9-285">ナビゲーション履歴で、WebView を前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="caff9-285">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="caff9-286">パブリック void [GoBack](#goback)()</span><span class="sxs-lookup"><span data-stu-id="caff9-286">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="caff9-287">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出しても、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="caff9-287">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="caff9-288">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-288">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-289">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-289">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="caff9-290">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-290">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="caff9-291">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-291">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-292">GoForward</span><span class="sxs-lookup"><span data-stu-id="caff9-292">GoForward</span></span> 

<span data-ttu-id="caff9-293">WebView をナビゲーション履歴の次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="caff9-293">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="caff9-294">パブリック void [Goforward](#goforward)()</span><span class="sxs-lookup"><span data-stu-id="caff9-294">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="caff9-295">CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出す場合と同等です。</span><span class="sxs-lookup"><span data-stu-id="caff9-295">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="caff9-296">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-296">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-297">呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-297">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="caff9-298">詳細については、「DispatcherObject アクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-298">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="caff9-299">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-299">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-300">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="caff9-300">NavigateToString</span></span> 

<span data-ttu-id="caff9-301">新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="caff9-301">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="caff9-302">パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)</span><span class="sxs-lookup"><span data-stu-id="caff9-302">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="caff9-303">CoreWebView2 で CoreWebView2 を呼び出すのと同じ NavigateToString</span><span class="sxs-lookup"><span data-stu-id="caff9-303">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="caff9-304">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-304">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-305">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-305">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="caff9-306">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-306">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="caff9-307">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-307">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-308">再</span><span class="sxs-lookup"><span data-stu-id="caff9-308">Reload</span></span> 

<span data-ttu-id="caff9-309">現在のページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="caff9-309">Reloads the current page.</span></span>

> <span data-ttu-id="caff9-310">パブリックの void[再読み込み](#reload)()</span><span class="sxs-lookup"><span data-stu-id="caff9-310">public void [Reload](#reload)()</span></span>

<span data-ttu-id="caff9-311">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="caff9-311">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="caff9-312">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-312">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-313">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-313">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="caff9-314">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-314">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="caff9-315">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-315">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-316">Stop</span><span class="sxs-lookup"><span data-stu-id="caff9-316">Stop</span></span> 

<span data-ttu-id="caff9-317">すべてのナビゲーションと保留中のリソースフェッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="caff9-317">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="caff9-318">パブリック void [Stop](#stop)()</span><span class="sxs-lookup"><span data-stu-id="caff9-318">public void [Stop](#stop)()</span></span>

<span data-ttu-id="caff9-319">CoreWebView2 で CoreWebView2 を呼び出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="caff9-319">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="caff9-320">例外</span><span class="sxs-lookup"><span data-stu-id="caff9-320">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="caff9-321">CoreWebView2 がまだ初期化されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-321">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="caff9-322">" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-322">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="caff9-323">詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="caff9-323">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="caff9-324">WebView2</span><span class="sxs-lookup"><span data-stu-id="caff9-324">WebView2</span></span> 

<span data-ttu-id="caff9-325">WebView2 コントロールの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="caff9-325">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="caff9-326">パブリック[WebView2](#webview2)()</span><span class="sxs-lookup"><span data-stu-id="caff9-326">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="caff9-327">コントロールの CoreWebView2 は、初期化されるまで null になります。</span><span class="sxs-lookup"><span data-stu-id="caff9-327">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="caff9-328">初期化の概要については、WebView2 クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caff9-328">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="caff9-329">BuildWindowCore</span><span class="sxs-lookup"><span data-stu-id="caff9-329">BuildWindowCore</span></span> 

<span data-ttu-id="caff9-330">これは HwndHost からオーバーライドされ、HWND の作成を指示するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-330">This is overridden from HwndHost and is called to instruct us to create our HWND.</span></span>

> <span data-ttu-id="caff9-331">protected override HandleRef [Buildwindowcore](#buildwindowcore)(HandleRef hwndParent)</span><span class="sxs-lookup"><span data-stu-id="caff9-331">protected override HandleRef [BuildWindowCore](#buildwindowcore)(HandleRef hwndParent)</span></span>

##### <span data-ttu-id="caff9-332">パラメーター</span><span class="sxs-lookup"><span data-stu-id="caff9-332">Parameters</span></span>
* `hwndParent` <span data-ttu-id="caff9-333">作成したものの親として使用する HWND。</span><span class="sxs-lookup"><span data-stu-id="caff9-333">The HWND that we should use as the parent of the one we create.</span></span>

##### <span data-ttu-id="caff9-334">返し</span><span class="sxs-lookup"><span data-stu-id="caff9-334">Returns</span></span>
<span data-ttu-id="caff9-335">作成した HWND。</span><span class="sxs-lookup"><span data-stu-id="caff9-335">The HWND that we created.</span></span>

#### <span data-ttu-id="caff9-336">DestroyWindowCore</span><span class="sxs-lookup"><span data-stu-id="caff9-336">DestroyWindowCore</span></span> 

<span data-ttu-id="caff9-337">これは HwndHost からオーバーライドされ、HWND の破棄を指示するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-337">This is overridden from HwndHost and is called to instruct us to destroy our HWND.</span></span>

> <span data-ttu-id="caff9-338">protected override void [Destroywindowcore](#destroywindowcore)(HandleRef hwnd)</span><span class="sxs-lookup"><span data-stu-id="caff9-338">protected override void [DestroyWindowCore](#destroywindowcore)(HandleRef hwnd)</span></span>

##### <span data-ttu-id="caff9-339">パラメーター</span><span class="sxs-lookup"><span data-stu-id="caff9-339">Parameters</span></span>
* `hwnd` <span data-ttu-id="caff9-340">破棄する必要がある HWND。</span><span class="sxs-lookup"><span data-stu-id="caff9-340">Our HWND that we need to destroy.</span></span>

#### <span data-ttu-id="caff9-341">破棄</span><span class="sxs-lookup"><span data-stu-id="caff9-341">Dispose</span></span> 

<span data-ttu-id="caff9-342">これは、IDispose パターンの一般的な実装に従って、基本クラスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-342">This is called by our base class according to the typical implementation of the IDispose pattern.</span></span>

> <span data-ttu-id="caff9-343">protected override void [Dispose](#dispose)(bool disposing)</span><span class="sxs-lookup"><span data-stu-id="caff9-343">protected override void [Dispose](#dispose)(bool disposing)</span></span>

<span data-ttu-id="caff9-344">これは、CoreWebView2 を含む、基盤となるすべての COM リソースを解放することで実装されています。</span><span class="sxs-lookup"><span data-stu-id="caff9-344">We implement it by releasing all of our underlying COM resources, including our CoreWebView2.</span></span>

##### <span data-ttu-id="caff9-345">パラメーター</span><span class="sxs-lookup"><span data-stu-id="caff9-345">Parameters</span></span>
* `disposing` <span data-ttu-id="caff9-346">呼び出し元が明示的に Dispose を呼び出している場合は True、完了している場合は false。</span><span class="sxs-lookup"><span data-stu-id="caff9-346">True if a caller is explicitly calling Dispose, false if we're being finalized.</span></span>

#### <span data-ttu-id="caff9-347">HasFocusWithinCore</span><span class="sxs-lookup"><span data-stu-id="caff9-347">HasFocusWithinCore</span></span> 

<span data-ttu-id="caff9-348">これは、HwndHost からオーバーライドされ、フォーカスがコントロールとウィンドウのどちらにあるかを WPF が認識する必要があるときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-348">This is overridden from HwndHost and is called when WPF needs to know if the focus is in our control/window.</span></span>

> <span data-ttu-id="caff9-349">protected override bool [HasFocusWithinCore](#hasfocuswithincore)()</span><span class="sxs-lookup"><span data-stu-id="caff9-349">protected override bool [HasFocusWithinCore](#hasfocuswithincore)()</span></span>

<span data-ttu-id="caff9-350">Wpf は非 WPF ウィンドウをホストしているため、WPF がそれ自体を認識することはできません。そのため、代わりにこれを呼び出すように求められます。</span><span class="sxs-lookup"><span data-stu-id="caff9-350">WPF can't know on its own since we're hosting a non-WPF window, so instead it asks us by calling this.</span></span> <span data-ttu-id="caff9-351">応答するには、CoreWebView2 イベントに基づいて状態を追跡します。これにより、フォーカスが獲得または切断されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="caff9-351">To answer, we just track state based on CoreWebView2 events that fire when it gains or loses focus.</span></span>

##### <span data-ttu-id="caff9-352">返し</span><span class="sxs-lookup"><span data-stu-id="caff9-352">Returns</span></span>
<span data-ttu-id="caff9-353">フォーカスがコントロール/ウィンドウにある場合は True、そうでない場合は false。</span><span class="sxs-lookup"><span data-stu-id="caff9-353">True if the focus is in our control/window, false if it isn't.</span></span>

#### <span data-ttu-id="caff9-354">OnKeyDown</span><span class="sxs-lookup"><span data-stu-id="caff9-354">OnKeyDown</span></span> 

<span data-ttu-id="caff9-355">これは UIElement から呼び出され、キー入力の入力を処理できるようにするために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-355">This is overridden from UIElement and called to allow us to handle key press input.</span></span>

> <span data-ttu-id="caff9-356">protected override void [control.onkeydown](#onkeydown)(KeyEventArgs e)</span><span class="sxs-lookup"><span data-stu-id="caff9-356">protected override void [OnKeyDown](#onkeydown)(KeyEventArgs e)</span></span>

<span data-ttu-id="caff9-357">Wpf では、WPF 以外のウィンドウをホストしているため、キーボードイベントに対して実際に呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="caff9-357">WPF should never actually call this in response to keyboard events because we're hosting a non-WPF window.</span></span> <span data-ttu-id="caff9-358">ウィンドウにフォーカスがある場合、入力は、WPF の最上位ウィンドウと入力システムではなく、Windows に直接送信されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-358">When our window has focus Windows will send the input directly to it rather than to WPF's top-level window and input system.</span></span> <span data-ttu-id="caff9-359">このオーバーライドは、CoreWebView2 から WPF へのアクセラレータキー入力の明示的な転送 (CoreWebView2Controller_AcceleratorKeyPressed) でのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="caff9-359">This override should only be called when we're explicitly forwarding accelerator key input from the CoreWebView2 to WPF (in CoreWebView2Controller_AcceleratorKeyPressed).</span></span> <span data-ttu-id="caff9-360">その場合でも、この KeyDownEvent は、PreviewKeyDownEvent の実装によって明示的にトリガーされ、WPF の通常のシステムと一致するために発生します。</span><span class="sxs-lookup"><span data-stu-id="caff9-360">Even then, this KeyDownEvent is only triggered because our PreviewKeyDownEvent implementation explicitly triggers it, matching WPF's usual system.</span></span> <span data-ttu-id="caff9-361">そのため、プロセスは次のようになります。 CoreWebView2Controller_AcceleratorKeyPressed-> は、PreviewKeyDownEvent > Onpreview Keydown-> KeyDownEvent > Control.onkeydown を発生させます。</span><span class="sxs-lookup"><span data-stu-id="caff9-361">So the process is: CoreWebView2Controller_AcceleratorKeyPressed -> raise PreviewKeyDownEvent -> OnPreviewKeyDown -> raise KeyDownEvent -> OnKeyDown</span></span>

#### <span data-ttu-id="caff9-362">OnKeyUp</span><span class="sxs-lookup"><span data-stu-id="caff9-362">OnKeyUp</span></span> 

<span data-ttu-id="caff9-363">「Control.onkeydown」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caff9-363">See OnKeyDown.</span></span>

> <span data-ttu-id="caff9-364">protected override void [OnKeyUp](#onkeyup)(KeyEventArgs e)</span><span class="sxs-lookup"><span data-stu-id="caff9-364">protected override void [OnKeyUp](#onkeyup)(KeyEventArgs e)</span></span>

#### <span data-ttu-id="caff9-365">Onpreview Keydown</span><span class="sxs-lookup"><span data-stu-id="caff9-365">OnPreviewKeyDown</span></span> 

<span data-ttu-id="caff9-366">これは "プレビュー" です (例:</span><span class="sxs-lookup"><span data-stu-id="caff9-366">This is the "Preview" (i.e.</span></span>

> <span data-ttu-id="caff9-367">protected override void [Onpreview keydown](#onpreviewkeydown)(KeyEventArgs e)</span><span class="sxs-lookup"><span data-stu-id="caff9-367">protected override void [OnPreviewKeyDown](#onpreviewkeydown)(KeyEventArgs e)</span></span>

<span data-ttu-id="caff9-368">トンネリング) バージョンの Control.onkeydown では、実際に最初に発生します。</span><span class="sxs-lookup"><span data-stu-id="caff9-368">tunneling) version of OnKeyDown, so it actually happens first.</span></span> <span data-ttu-id="caff9-369">Control.onkeydown と同じように、CoreWebView2 から明示的にキーの押下を転送している場合にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-369">Like OnKeyDown, this will only ever be called if we're explicitly forwarding key presses from the CoreWebView2.</span></span> <span data-ttu-id="caff9-370">WPF の標準の入力処理を模倣するために、これを受け取ったときに、標準のバブルの KeyDownEvent を回避して、発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="caff9-370">In order to mimic WPF's standard input handling, when we receive this we turn around and fire off the standard bubbling KeyDownEvent.</span></span> <span data-ttu-id="caff9-371">これにより、WPF ツリー内の他のユーザーは、キー入力を処理している場合に WPF 自体がトリガーする同じ標準ペアの入力イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="caff9-371">That way others in the WPF tree see the same standard pair of input events that WPF itself would have triggered if it were handling the key press.</span></span>

#### <span data-ttu-id="caff9-372">Onpreview Keyup</span><span class="sxs-lookup"><span data-stu-id="caff9-372">OnPreviewKeyUp</span></span> 

<span data-ttu-id="caff9-373">詳しくは、「Onpreview Keydown」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caff9-373">See OnPreviewKeyDown.</span></span>

> <span data-ttu-id="caff9-374">protected override void [Onpreview keyup](#onpreviewkeyup)(KeyEventArgs e)</span><span class="sxs-lookup"><span data-stu-id="caff9-374">protected override void [OnPreviewKeyUp](#onpreviewkeyup)(KeyEventArgs e)</span></span>

#### <span data-ttu-id="caff9-375">OnWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="caff9-375">OnWindowPositionChanged</span></span> 

<span data-ttu-id="caff9-376">これは、コントロールの位置が変わったときに HwndHost によってオーバーライドされて呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="caff9-376">This is overridden from HwndHost and called when our control's location has changed.</span></span>

> <span data-ttu-id="caff9-377">protected override void [Onwindowpositionchanged](#onwindowpositionchanged)(Rect rcBoundingBox)</span><span class="sxs-lookup"><span data-stu-id="caff9-377">protected override void [OnWindowPositionChanged](#onwindowpositionchanged)(Rect rcBoundingBox)</span></span>

<span data-ttu-id="caff9-378">HwndHost は、作成した HWND の更新を行います。</span><span class="sxs-lookup"><span data-stu-id="caff9-378">The HwndHost takes care of updating the HWND we created.</span></span> <span data-ttu-id="caff9-379">必要な作業は、CoreWebView2 を新しい場所に合わせて移動することです。</span><span class="sxs-lookup"><span data-stu-id="caff9-379">What we need to do is move our CoreWebView2 to match the new location.</span></span>

#### <span data-ttu-id="caff9-380">タブの基本</span><span class="sxs-lookup"><span data-stu-id="caff9-380">TabIntoCore</span></span> 

<span data-ttu-id="caff9-381">これは、HwndHost によって上書きされ、tab キーを使ってコントロール/ウィンドウにフォーカスが移動したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="caff9-381">This is overridden from HwndHost and is called to inform us that tabbing has caused the focus to move into our control/window.</span></span>

> <span data-ttu-id="caff9-382">protected [override ブール値](#tabintocore)のブール値 (TraversalRequest 要求)</span><span class="sxs-lookup"><span data-stu-id="caff9-382">protected override bool [TabIntoCore](#tabintocore)(TraversalRequest request)</span></span>

<span data-ttu-id="caff9-383">WPF では、非 WPF HWND へのフォーカスの切り替えを管理することはできないため、ここに切り替えを委任します。</span><span class="sxs-lookup"><span data-stu-id="caff9-383">Since WPF can't manage the transition of focus to a non-WPF HWND, it delegates the transition to us here.</span></span> <span data-ttu-id="caff9-384">このため、私たちの仕事は、外部の HWND にフォーカスを置くだけです。</span><span class="sxs-lookup"><span data-stu-id="caff9-384">So our job is just to place the focus in our external HWND.</span></span>

##### <span data-ttu-id="caff9-385">パラメーター</span><span class="sxs-lookup"><span data-stu-id="caff9-385">Parameters</span></span>
* `request` <span data-ttu-id="caff9-386">フォーカスの移動方法に関する情報。</span><span class="sxs-lookup"><span data-stu-id="caff9-386">Information about how the focus is moving.</span></span>

##### <span data-ttu-id="caff9-387">返し</span><span class="sxs-lookup"><span data-stu-id="caff9-387">Returns</span></span>
<span data-ttu-id="caff9-388">ナビゲーションを処理したことを示す場合は True、そうしない場合は false を指定します。</span><span class="sxs-lookup"><span data-stu-id="caff9-388">True to indicate that we handled the navigation, or false to indicate that we didn't.</span></span>

