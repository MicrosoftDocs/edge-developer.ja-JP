---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2Environment の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: a3e8a958a70820bf32bd3a76acc9ee503f568438
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877757"
---
# <span data-ttu-id="ea2a8-104">0.9.515 クラスの WebView2 クラス (CoreWebView2Environment)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

> [!NOTE]
> <span data-ttu-id="ea2a8-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="ea2a8-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="ea2a8-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="ea2a8-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="ea2a8-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="ea2a8-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="ea2a8-109">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-109">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="ea2a8-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="ea2a8-110">Summary</span></span>

 <span data-ttu-id="ea2a8-111">Members</span><span class="sxs-lookup"><span data-stu-id="ea2a8-111">Members</span></span>                        | <span data-ttu-id="ea2a8-112">説明</span><span class="sxs-lookup"><span data-stu-id="ea2a8-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ea2a8-113">この文字列</span><span class="sxs-lookup"><span data-stu-id="ea2a8-113">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="ea2a8-114">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-114">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="ea2a8-115">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="ea2a8-115">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="ea2a8-116">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-116">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="ea2a8-117">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="ea2a8-117">CreateAsync</span></span>](#createasync) | <span data-ttu-id="ea2a8-118">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-118">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="ea2a8-119">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="ea2a8-119">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="ea2a8-120">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-120">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="ea2a8-121">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="ea2a8-121">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="ea2a8-122">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-122">Create a new web resource response object.</span></span>

<span data-ttu-id="ea2a8-123">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-123">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="ea2a8-124">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-124">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="ea2a8-125">Members</span><span class="sxs-lookup"><span data-stu-id="ea2a8-125">Members</span></span>

#### <span data-ttu-id="ea2a8-126">この文字列</span><span class="sxs-lookup"><span data-stu-id="ea2a8-126">BrowserVersionString</span></span> 

<span data-ttu-id="ea2a8-127">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-127">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="ea2a8-128">パブリック文字列の[文字列](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-128">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="ea2a8-129">これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-129">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="ea2a8-130">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-130">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="ea2a8-131">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="ea2a8-131">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="ea2a8-132">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-132">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="ea2a8-133">パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-133">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="ea2a8-134">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-134">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="ea2a8-135">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-135">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="ea2a8-136">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-136">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="ea2a8-137">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-137">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="ea2a8-138">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-138">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="ea2a8-139">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="ea2a8-139">CreateAsync</span></span> 

<span data-ttu-id="ea2a8-140">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-140">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

> <span data-ttu-id="ea2a8-141">パブリック静的非同期タスク< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [createasync](#createasync)(string browserexecutablefolder、文字列 userdatafolder、CoreWebView2EnvironmentOptions options)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-141">public static async Task< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md) > [CreateAsync](#createasync)(string browserExecutableFolder, string userDataFolder, CoreWebView2EnvironmentOptions options)</span></span>

##### <span data-ttu-id="ea2a8-142">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea2a8-142">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="ea2a8-143">埋め込まれた端を含むフォルダーの相対パス。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-143">The relative path to the folder that contains the embedded Edge.</span></span> 

* `userDataFolder` <span data-ttu-id="ea2a8-144">userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-144">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> 

* `options` <span data-ttu-id="ea2a8-145">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-145">Options used to create WebView2 Environment.</span></span>

#### <span data-ttu-id="ea2a8-146">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="ea2a8-146">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="ea2a8-147">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-147">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="ea2a8-148">パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-148">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="ea2a8-149">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-149">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="ea2a8-150">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-150">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="ea2a8-151">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-151">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="ea2a8-152">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-152">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="ea2a8-153">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-153">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="ea2a8-154">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="ea2a8-154">CreateWebResourceResponse</span></span> 

<span data-ttu-id="ea2a8-155">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-155">Create a new web resource response object.</span></span>

> <span data-ttu-id="ea2a8-156">パブリック HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="ea2a8-156">public HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="ea2a8-157">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-157">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="ea2a8-158">空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-158">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="ea2a8-159">その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea2a8-159">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

