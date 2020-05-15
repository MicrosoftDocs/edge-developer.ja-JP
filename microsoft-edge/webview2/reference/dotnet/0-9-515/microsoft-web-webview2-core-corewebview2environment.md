---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: be8f475d4c1a886a92b46144f2bffde2d49dc9d4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654479"
---
# <span data-ttu-id="4cbdd-104">WebView2 クラス (CoreWebView2Environment クラス)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="4cbdd-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="4cbdd-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="4cbdd-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="4cbdd-107">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="4cbdd-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4cbdd-108">Summary</span></span>

 <span data-ttu-id="4cbdd-109">Members</span><span class="sxs-lookup"><span data-stu-id="4cbdd-109">Members</span></span>                        | <span data-ttu-id="4cbdd-110">説明</span><span class="sxs-lookup"><span data-stu-id="4cbdd-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4cbdd-111">この文字列</span><span class="sxs-lookup"><span data-stu-id="4cbdd-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="4cbdd-112">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="4cbdd-113">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="4cbdd-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="4cbdd-114">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-114">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="4cbdd-115">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="4cbdd-115">CreateAsync</span></span>](#createasync) | <span data-ttu-id="4cbdd-116">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-116">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="4cbdd-117">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="4cbdd-117">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="4cbdd-118">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-118">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="4cbdd-119">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="4cbdd-119">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="4cbdd-120">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-120">Create a new web resource response object.</span></span>

<span data-ttu-id="4cbdd-121">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-121">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="4cbdd-122">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-122">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="4cbdd-123">Members</span><span class="sxs-lookup"><span data-stu-id="4cbdd-123">Members</span></span>

#### <span data-ttu-id="4cbdd-124">この文字列</span><span class="sxs-lookup"><span data-stu-id="4cbdd-124">BrowserVersionString</span></span> 

<span data-ttu-id="4cbdd-125">CoreWebView2Environment が安定していない場合は、チャネル名を含む現在ののブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-125">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="4cbdd-126">パブリック文字列の[文字列](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-126">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="4cbdd-127">これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-127">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="4cbdd-128">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-128">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="4cbdd-129">新機能をご利用いただけます</span><span class="sxs-lookup"><span data-stu-id="4cbdd-129">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="4cbdd-130">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-130">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="4cbdd-131">パブリックイベント EventHandler< object > [New参照サーバーの使用可能](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-131">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="4cbdd-132">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-132">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="4cbdd-133">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-133">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="4cbdd-134">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-134">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="4cbdd-135">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-135">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="4cbdd-136">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-136">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="4cbdd-137">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="4cbdd-137">CreateAsync</span></span> 

<span data-ttu-id="4cbdd-138">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-138">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

> <span data-ttu-id="4cbdd-139">パブリック async タスク< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [createasync](#createasync)(string browserexecutablefolder、文字列 userdatafolder、CoreWebView2EnvironmentOptions options)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-139">public async Task< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md) > [CreateAsync](#createasync)(string browserExecutableFolder, string userDataFolder, CoreWebView2EnvironmentOptions options)</span></span>

##### <span data-ttu-id="4cbdd-140">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cbdd-140">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="4cbdd-141">埋め込まれた端を含むフォルダーの相対パス。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-141">The relative path to the folder that contains the embedded Edge.</span></span> 

* `userDataFolder` <span data-ttu-id="4cbdd-142">userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-142">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> 

* `options` <span data-ttu-id="4cbdd-143">WebView2 環境の作成に使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-143">Options used to create WebView2 Environment.</span></span>

#### <span data-ttu-id="4cbdd-144">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="4cbdd-144">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="4cbdd-145">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-145">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="4cbdd-146">パブリック async タスク< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr parentwindow)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-146">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="4cbdd-147">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-147">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="4cbdd-148">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-148">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="4cbdd-149">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-149">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="4cbdd-150">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-150">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="4cbdd-151">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-151">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="4cbdd-152">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="4cbdd-152">CreateWebResourceResponse</span></span> 

<span data-ttu-id="4cbdd-153">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-153">Create a new web resource response object.</span></span>

> <span data-ttu-id="4cbdd-154">パブリック HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(ストリームコンテンツ、int StatusCode、文字列の理由語句、文字列ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="4cbdd-154">public HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="4cbdd-155">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-155">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="4cbdd-156">空のヘッダー文字列を使ってこのオブジェクトを作成し、CoreWebView2HttpResponseHeaders を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-156">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="4cbdd-157">その他のパラメーターについては、「CoreWebView2WebResourceResponse」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cbdd-157">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

