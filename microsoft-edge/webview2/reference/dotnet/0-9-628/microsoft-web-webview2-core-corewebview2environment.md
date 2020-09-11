---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Environment。
ms.openlocfilehash: c6b1f1c62da5aa5ef64693575abb9cb46ac13851
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012286"
---
# <span data-ttu-id="528de-104">WebView2 クラス (CoreWebView2Environment クラス)</span><span class="sxs-lookup"><span data-stu-id="528de-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="528de-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="528de-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="528de-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="528de-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="528de-107">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="528de-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="528de-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="528de-108">Summary</span></span>

 <span data-ttu-id="528de-109">Members</span><span class="sxs-lookup"><span data-stu-id="528de-109">Members</span></span>                        | <span data-ttu-id="528de-110">説明</span><span class="sxs-lookup"><span data-stu-id="528de-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="528de-111">この文字列</span><span class="sxs-lookup"><span data-stu-id="528de-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="528de-112">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="528de-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="528de-113">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="528de-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="528de-114">最新バージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに呼び出される新機能。</span><span class="sxs-lookup"><span data-stu-id="528de-114">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>
[<span data-ttu-id="528de-115">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="528de-115">CreateCoreWebView2CompositionControllerAsync</span></span>](#createcorewebview2compositioncontrollerasync) | <span data-ttu-id="528de-116">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-116">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="528de-117">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="528de-117">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="528de-118">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-118">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="528de-119">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="528de-119">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="528de-120">空の CoreWebView2PointerInfo を作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-120">Create an empty CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="528de-121">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="528de-121">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="528de-122">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-122">Create a new web resource response object.</span></span>
[<span data-ttu-id="528de-123">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="528de-123">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="528de-124">指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="528de-124">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="528de-125">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-125">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="528de-126">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="528de-126">Using it in different environments are not guaranteed to be compatible and may fail.</span></span> 

<span data-ttu-id="528de-127">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-127">WebViews created from an environment run on the browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="528de-128">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="528de-128">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="528de-129">Members</span><span class="sxs-lookup"><span data-stu-id="528de-129">Members</span></span>

#### <span data-ttu-id="528de-130">この文字列</span><span class="sxs-lookup"><span data-stu-id="528de-130">BrowserVersionString</span></span> 

<span data-ttu-id="528de-131">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="528de-131">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="528de-132">パブリック文字列の [文字列](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="528de-132">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="528de-133">これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="528de-133">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="528de-134">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="528de-134">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="528de-135">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="528de-135">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="528de-136">最新バージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに呼び出される新機能。</span><span class="sxs-lookup"><span data-stu-id="528de-136">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>

> <span data-ttu-id="528de-137">パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="528de-137">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="528de-138">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-138">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="528de-139">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="528de-139">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="528de-140">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="528de-140">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="528de-141">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-141">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="528de-142">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="528de-142">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="528de-143">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="528de-143">CreateCoreWebView2CompositionControllerAsync</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="528de-144">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-144">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="528de-145">パブリック async タスク< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="528de-145">public async Task< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md) > [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="528de-146">parentWindow は、アプリが WebView のビジュアルツリーを接続する HWND です。</span><span class="sxs-lookup"><span data-stu-id="528de-146">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="528de-147">これは、WebView に対応するポインターまたはマウスの入力をアプリが受け取るようにする HWND です (そして、SendMouseInput/Sendpointer 入力を使って転送する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="528de-147">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="528de-148">アプリが WebView ビジュアルツリーを別のウィンドウの下に移動する場合、ビジュアルツリーの新しい親 HWND を更新するために CoreWebView2CompositionController ウィンドウを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-148">If the app moves the WebView visual tree to underneath a different window, then it needs to set CoreWebView2CompositionController.ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="528de-149">作成された CoreWebView2CompositionController で RootVisualTarget プロパティを設定して、ブラウザーのビジュアルツリーをホストするためのビジュアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="528de-149">Set RootVisualTarget property on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="528de-150">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="528de-150">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="528de-151">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="528de-151">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="528de-152">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="528de-152">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="528de-153">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-153">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="528de-154">パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="528de-154">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="528de-155">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="528de-155">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="528de-156">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="528de-156">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="528de-157">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="528de-157">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="528de-158">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="528de-158">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="528de-159">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="528de-159">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="528de-160">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="528de-160">CreateCoreWebView2PointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="528de-161">空の CoreWebView2PointerInfo を作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-161">Create an empty CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="528de-162">パブリック [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span><span class="sxs-lookup"><span data-stu-id="528de-162">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span></span>

<span data-ttu-id="528de-163">返された CoreWebView2PointerInfo には、Sendポインタ入力を呼び出す前に、関連するすべての情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="528de-163">The returned CoreWebView2PointerInfo needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="528de-164">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="528de-164">CreateWebResourceResponse</span></span> 

<span data-ttu-id="528de-165">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="528de-165">Create a new web resource response object.</span></span>

> <span data-ttu-id="528de-166">パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="528de-166">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="528de-167">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="528de-167">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="528de-168">空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="528de-168">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="528de-169">その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="528de-169">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

#### <span data-ttu-id="528de-170">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="528de-170">GetProviderForHwnd</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="528de-171">指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="528de-171">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="528de-172">パブリックオブジェクト [Getproviderforhwnd](#getproviderforhwnd)(IntPtr hwnd)</span><span class="sxs-lookup"><span data-stu-id="528de-172">public object [GetProviderForHwnd](#getproviderforhwnd)(IntPtr hwnd)</span></span>

