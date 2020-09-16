---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Environment。
ms.openlocfilehash: 05b8a10c723ae57b2c95551f4d5043f3336eba3b
ms.sourcegitcommit: 65db518273b3cd69f1b3c528809600719b9b70aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016327"
---
# <span data-ttu-id="e6560-104">WebView2 クラス (CoreWebView2Environment クラス)</span><span class="sxs-lookup"><span data-stu-id="e6560-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="e6560-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="e6560-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e6560-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e6560-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e6560-107">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="e6560-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="e6560-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e6560-108">Summary</span></span>

 <span data-ttu-id="e6560-109">Members</span><span class="sxs-lookup"><span data-stu-id="e6560-109">Members</span></span>                        | <span data-ttu-id="e6560-110">説明</span><span class="sxs-lookup"><span data-stu-id="e6560-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e6560-111">この文字列</span><span class="sxs-lookup"><span data-stu-id="e6560-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="e6560-112">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="e6560-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="e6560-113">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="e6560-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="e6560-114">最新バージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに呼び出される新機能。</span><span class="sxs-lookup"><span data-stu-id="e6560-114">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>
[<span data-ttu-id="e6560-115">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="e6560-115">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="e6560-116">ブラウザーのバージョンを比較して、一致しているか、異なるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6560-116">Compare browser versions to determine if they match or are different.</span></span>
[<span data-ttu-id="e6560-117">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-117">CreateAsync</span></span>](#createasync) | <span data-ttu-id="e6560-118">インストールされている Microsoft Edge のバージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-118">Creates an evergreen WebView2 Environment using the installed version of Microsoft Edge.</span></span>
[<span data-ttu-id="e6560-119">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-119">CreateCoreWebView2CompositionControllerAsync</span></span>](#createcorewebview2compositioncontrollerasync) | <span data-ttu-id="e6560-120">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-120">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="e6560-121">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-121">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="e6560-122">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-122">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="e6560-123">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="e6560-123">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="e6560-124">空の CoreWebView2PointerInfo を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-124">Create an empty CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="e6560-125">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="e6560-125">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="e6560-126">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-126">Create a new web resource response object.</span></span>
[<span data-ttu-id="e6560-127">Getserverした文字列</span><span class="sxs-lookup"><span data-stu-id="e6560-127">GetAvailableBrowserVersionString</span></span>](#getavailablebrowserversionstring) | <span data-ttu-id="e6560-128">ブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6560-128">Get the browser version information.</span></span>
[<span data-ttu-id="e6560-129">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="e6560-129">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="e6560-130">指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="e6560-130">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="e6560-131">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-131">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="e6560-132">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-132">Using it in different environments are not guaranteed to be compatible and may fail.</span></span> 

## <span data-ttu-id="e6560-133">Members</span><span class="sxs-lookup"><span data-stu-id="e6560-133">Members</span></span>

#### <span data-ttu-id="e6560-134">この文字列</span><span class="sxs-lookup"><span data-stu-id="e6560-134">BrowserVersionString</span></span> 

<span data-ttu-id="e6560-135">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="e6560-135">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="e6560-136">パブリック文字列の [文字列](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="e6560-136">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="e6560-137">これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="e6560-137">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="e6560-138">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="e6560-138">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="e6560-139">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="e6560-139">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="e6560-140">最新バージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに呼び出される新機能。</span><span class="sxs-lookup"><span data-stu-id="e6560-140">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>

> <span data-ttu-id="e6560-141">パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="e6560-141">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="e6560-142">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-142">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="e6560-143">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="e6560-143">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="e6560-144">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="e6560-144">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="e6560-145">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-145">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="e6560-146">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="e6560-146">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="e6560-147">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="e6560-147">CompareBrowserVersions</span></span> 

<span data-ttu-id="e6560-148">ブラウザーのバージョンを比較して、一致しているか、異なるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6560-148">Compare browser versions to determine if they match or are different.</span></span>

> <span data-ttu-id="e6560-149">パブリック静的な int [CompareBrowserVersions](#comparebrowserversions)(文字列 version1、文字列 version2)</span><span class="sxs-lookup"><span data-stu-id="e6560-149">public static int [CompareBrowserVersions](#comparebrowserversions)(string version1, string version2)</span></span>

<span data-ttu-id="e6560-150">最初のバージョンが比較されている2番目のバージョンより小さいか、等しいか、それよりも大きいかに応じて、-1、0、または1を返します。</span><span class="sxs-lookup"><span data-stu-id="e6560-150">Returns -1, 0 or 1 depending on whether the first version is less than, equal to or greater than the second version being compared.</span></span>

<span data-ttu-id="e6560-151">入力では、GetAvailableCoreWebView2BrowserVersionString から取得した versionInfo を直接使うことができます。チャネル情報は無視されます。</span><span class="sxs-lookup"><span data-stu-id="e6560-151">Input can directly use the versionInfo obtained from GetAvailableCoreWebView2BrowserVersionString, channel info will be ignored.</span></span>

##### <span data-ttu-id="e6560-152">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6560-152">Parameters</span></span>
* `version1` <span data-ttu-id="e6560-153">比較する最初のバージョン。</span><span class="sxs-lookup"><span data-stu-id="e6560-153">The first version to compare.</span></span> 

* `version2` <span data-ttu-id="e6560-154">比較する2つ目のバージョン。</span><span class="sxs-lookup"><span data-stu-id="e6560-154">The second version to compare.</span></span>

#### <span data-ttu-id="e6560-155">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-155">CreateAsync</span></span> 

<span data-ttu-id="e6560-156">インストールされている Microsoft Edge のバージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-156">Creates an evergreen WebView2 Environment using the installed version of Microsoft Edge.</span></span>

> <span data-ttu-id="e6560-157">パブリック静的非同期タスク< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [createasync](#createasync)(string browserexecutablefolder、文字列 userdatafolder、CoreWebView2EnvironmentOptions options)</span><span class="sxs-lookup"><span data-stu-id="e6560-157">public static async Task< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md) > [CreateAsync](#createasync)(string browserExecutableFolder, string userDataFolder, CoreWebView2EnvironmentOptions options)</span></span>

##### <span data-ttu-id="e6560-158">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6560-158">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="e6560-159">WebView2 ランタイムの修正されたバージョンを含むフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="e6560-159">The relative path to the folder that contains the fixed version of the WebView2 Runtime.</span></span> 

* `userDataFolder` <span data-ttu-id="e6560-160">userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e6560-160">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> 

* `options` <span data-ttu-id="e6560-161">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="e6560-161">Options used to create WebView2 Environment.</span></span>

#### <span data-ttu-id="e6560-162">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-162">CreateCoreWebView2CompositionControllerAsync</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="e6560-163">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-163">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="e6560-164">パブリック async タスク< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="e6560-164">public async Task< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md) > [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="e6560-165">parentWindow は、アプリが WebView のビジュアルツリーを接続する HWND です。</span><span class="sxs-lookup"><span data-stu-id="e6560-165">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="e6560-166">これは、WebView に対応するポインターまたはマウスの入力をアプリが受け取るようにする HWND です (そして、SendMouseInput/Sendpointer 入力を使って転送する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e6560-166">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="e6560-167">アプリが WebView ビジュアルツリーを別のウィンドウの下に移動する場合、ビジュアルツリーの新しい親 HWND を更新するために CoreWebView2CompositionController ウィンドウを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-167">If the app moves the WebView visual tree to underneath a different window, then it needs to set CoreWebView2CompositionController.ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="e6560-168">作成された CoreWebView2CompositionController で RootVisualTarget プロパティを設定して、ブラウザーのビジュアルツリーをホストするためのビジュアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e6560-168">Set RootVisualTarget property on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="e6560-169">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6560-169">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="e6560-170">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e6560-170">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="e6560-171">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="e6560-171">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="e6560-172">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-172">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="e6560-173">パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="e6560-173">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="e6560-174">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="e6560-174">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="e6560-175">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6560-175">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="e6560-176">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="e6560-176">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="e6560-177">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6560-177">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="e6560-178">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e6560-178">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="e6560-179">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="e6560-179">CreateCoreWebView2PointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="e6560-180">空の CoreWebView2PointerInfo を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-180">Create an empty CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="e6560-181">パブリック [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span><span class="sxs-lookup"><span data-stu-id="e6560-181">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span></span>

<span data-ttu-id="e6560-182">返された CoreWebView2PointerInfo には、Sendポインタ入力を呼び出す前に、関連するすべての情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6560-182">The returned CoreWebView2PointerInfo needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="e6560-183">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="e6560-183">CreateWebResourceResponse</span></span> 

<span data-ttu-id="e6560-184">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6560-184">Create a new web resource response object.</span></span>

> <span data-ttu-id="e6560-185">パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="e6560-185">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="e6560-186">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="e6560-186">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="e6560-187">空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6560-187">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="e6560-188">その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6560-188">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

#### <span data-ttu-id="e6560-189">Getserverした文字列</span><span class="sxs-lookup"><span data-stu-id="e6560-189">GetAvailableBrowserVersionString</span></span> 

<span data-ttu-id="e6560-190">ブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e6560-190">Get the browser version information.</span></span>

> <span data-ttu-id="e6560-191">パブリック静的な文字列 [Getserverの](#getavailablebrowserversionstring)文字列 (String browserExecutableFolder)</span><span class="sxs-lookup"><span data-stu-id="e6560-191">public static string [GetAvailableBrowserVersionString](#getavailablebrowserversionstring)(string browserExecutableFolder)</span></span>

<span data-ttu-id="e6560-192">チャネルが安定していない場合は、チャネル名も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6560-192">You also get the channel name if the channel is not a stable channel.</span></span> <span data-ttu-id="e6560-193">WebView2 ランタイムを使っている場合、チャネル名は返されません。</span><span class="sxs-lookup"><span data-stu-id="e6560-193">If you use the WebView2 Runtime, no channel name is returned.</span></span>

##### <span data-ttu-id="e6560-194">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6560-194">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="e6560-195">WebView2 ランタイムの修正されたバージョンを含むフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="e6560-195">The relative path to the folder that contains the fixed version of the WebView2 Runtime.</span></span>

#### <span data-ttu-id="e6560-196">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="e6560-196">GetProviderForHwnd</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="e6560-197">指定された HWND に対応する CoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="e6560-197">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="e6560-198">パブリックオブジェクト [Getproviderforhwnd](#getproviderforhwnd)(IntPtr hwnd)</span><span class="sxs-lookup"><span data-stu-id="e6560-198">public object [GetProviderForHwnd](#getproviderforhwnd)(IntPtr hwnd)</span></span>
