---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ グローバル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1134aa10717dfc5be8ef1a4de5805a3fc319aeb8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883799"
---
# <span data-ttu-id="efe9b-104">0.9.515-グローバル</span><span class="sxs-lookup"><span data-stu-id="efe9b-104">0.9.515 - Globals</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

## <span data-ttu-id="efe9b-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="efe9b-105">Summary</span></span>

 <span data-ttu-id="efe9b-106">Members</span><span class="sxs-lookup"><span data-stu-id="efe9b-106">Members</span></span>                        | <span data-ttu-id="efe9b-107">説明</span><span class="sxs-lookup"><span data-stu-id="efe9b-107">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="efe9b-108">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="efe9b-108">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="efe9b-109">このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="efe9b-109">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>
[<span data-ttu-id="efe9b-110">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="efe9b-110">CreateCoreWebView2Environment</span></span>](#createcorewebview2environment) | <span data-ttu-id="efe9b-111">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-111">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="efe9b-112">CreateCoreWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="efe9b-112">CreateCoreWebView2EnvironmentWithDetails</span></span>](#createcorewebview2environmentwithdetails) | <span data-ttu-id="efe9b-113">この API は、次の SDK リリースでは削除される予定です。</span><span class="sxs-lookup"><span data-stu-id="efe9b-113">This API is going to be removed in next SDK release.</span></span>
[<span data-ttu-id="efe9b-114">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="efe9b-114">CreateCoreWebView2EnvironmentWithOptions</span></span>](#createcorewebview2environmentwithoptions) | <span data-ttu-id="efe9b-115">[DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、または追加オプションを使って WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-115">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>
[<span data-ttu-id="efe9b-116">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="efe9b-116">GetAvailableCoreWebView2BrowserVersionString</span></span>](#getavailablecorewebview2browserversionstring) | <span data-ttu-id="efe9b-117">安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-117">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

## <span data-ttu-id="efe9b-118">Members</span><span class="sxs-lookup"><span data-stu-id="efe9b-118">Members</span></span>

#### <span data-ttu-id="efe9b-119">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="efe9b-119">CompareBrowserVersions</span></span> 

> <span data-ttu-id="efe9b-120">パブリック STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR VERSION1、PCWSTR version2、int \* result)</span><span class="sxs-lookup"><span data-stu-id="efe9b-120">public STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR version1, PCWSTR version2, int \* result)</span></span>

<span data-ttu-id="efe9b-121">このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="efe9b-121">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

<span data-ttu-id="efe9b-122">Webview2 または特定の機能ベースをバージョンで使うかどうかを決定するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-122">It can be used to determine whether to use webview2 or certain feature base on version.</span></span> <span data-ttu-id="efe9b-123">結果の値を-1、0、または1に設定します (version1 が version2 より小さいか、等しいか、等しい場合)。</span><span class="sxs-lookup"><span data-stu-id="efe9b-123">Sets the value of result to -1, 0 or 1 if version1 is less than, equal or greater than version2 respectively.</span></span> <span data-ttu-id="efe9b-124">いずれかのバージョン文字列が解析できなかった場合、または入力パラメーターが null である場合に E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-124">Returns E_INVALIDARG if it fails to parse any of the version strings or any input parameter is null.</span></span> <span data-ttu-id="efe9b-125">入力では、GetAvailableCoreWebView2BrowserVersionString から取得した versionInfo を直接使うことができます。チャネル情報は無視されます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-125">Input can directly use the versionInfo obtained from GetAvailableCoreWebView2BrowserVersionString, channel info will be ignored.</span></span>

#### <span data-ttu-id="efe9b-126">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="efe9b-126">CreateCoreWebView2Environment</span></span> 

> <span data-ttu-id="efe9b-127">パブリック STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span><span class="sxs-lookup"><span data-stu-id="efe9b-127">public STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="efe9b-128">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-128">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

<span data-ttu-id="efe9b-129">これは、CreateCoreWebView2EnvironmentWithOptions と browserExecutableFolder、userDataFolder、additionalBrowserArguments を使用してを呼び出すことに相当します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-129">This is equivalent to calling CreateCoreWebView2EnvironmentWithOptions with nullptr for browserExecutableFolder, userDataFolder, additionalBrowserArguments.</span></span> <span data-ttu-id="efe9b-130">詳細については、「CreateCoreWebView2EnvironmentWithOptions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efe9b-130">See CreateCoreWebView2EnvironmentWithOptions for more details.</span></span>

#### <span data-ttu-id="efe9b-131">CreateCoreWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="efe9b-131">CreateCoreWebView2EnvironmentWithDetails</span></span> 

> <span data-ttu-id="efe9b-132">パブリック STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)(PCWSTR browserExecutableFolder、PCWSTR userDataFolder、PCWSTR additionalBrowserArguments、 [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span><span class="sxs-lookup"><span data-stu-id="efe9b-132">public STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)(PCWSTR browserExecutableFolder, PCWSTR userDataFolder, PCWSTR additionalBrowserArguments, [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="efe9b-133">この API は、次の SDK リリースでは削除される予定です。</span><span class="sxs-lookup"><span data-stu-id="efe9b-133">This API is going to be removed in next SDK release.</span></span>

<span data-ttu-id="efe9b-134">CreateCoreWebView2EnvironmentWithOptions を使用してください。</span><span class="sxs-lookup"><span data-stu-id="efe9b-134">Please use CreateCoreWebView2EnvironmentWithOptions.</span></span>

#### <span data-ttu-id="efe9b-135">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="efe9b-135">CreateCoreWebView2EnvironmentWithOptions</span></span> 

> <span data-ttu-id="efe9b-136">パブリック STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)(PCWSTR browserExecutableFolder、PCWSTR userDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) \* environmentOptions、 [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span><span class="sxs-lookup"><span data-stu-id="efe9b-136">public STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)(PCWSTR browserExecutableFolder, PCWSTR userDataFolder, [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) \* environmentOptions, [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="efe9b-137">[DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、または追加オプションを使って WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-137">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>

<span data-ttu-id="efe9b-138">browserExecutableFolder は、埋め込まれた端を含むフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="efe9b-138">browserExecutableFolder is the relative path to the folder that contains the embedded Edge.</span></span> <span data-ttu-id="efe9b-139">埋め込まれたエッジを取得するには、インストールされている Edge のフォルダーという名前のバージョン (インストールされている 73.0.52.0 Edge の 73.0.52.0 sub フォルダーなど) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="efe9b-139">The embedded Edge can be obtained by copying the version named folder of an installed Edge, like 73.0.52.0 sub folder of an installed 73.0.52.0 Edge.</span></span> <span data-ttu-id="efe9b-140">フォルダーの msedge.exe、msedge.dll などを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-140">The folder should have msedge.exe, msedge.dll, and so on.</span></span> <span data-ttu-id="efe9b-141">BrowserExecutableFolder に null または空の文字列を使用してコンピューターにインストールされている Edge を使用して、コンピューターにインストールされている microsoft Edge の互換性のあるバージョンを検索します。この場合は、ユーザーごとに最初にインストールしてから、コンピューターごとにインストールします。</span><span class="sxs-lookup"><span data-stu-id="efe9b-141">Use null or empty string for browserExecutableFolder to create WebView using Edge installed on the machine, in which case the API will try to find a compatible version of Edge installed on the machine according to the channel preference trying to find first per user install and then per machine install.</span></span>

<span data-ttu-id="efe9b-142">既定のチャネル検索順序は、安定、ベータ、dev、カナリアです。</span><span class="sxs-lookup"><span data-stu-id="efe9b-142">The default channel search order is stable, beta, dev, and canary.</span></span> <span data-ttu-id="efe9b-143">WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 環境変数または該当する releaseChannelPreference レジストリ値に1を指定すると、チャネルの検索順序が逆になります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-143">When there is an override WEBVIEW2_RELEASE_CHANNEL_PREFERENCE environment variable or applicable releaseChannelPreference registry value with the value of 1, the channel search order is reversed.</span></span>

<span data-ttu-id="efe9b-144">userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-144">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> <span data-ttu-id="efe9b-145">パスには、絶対ファイルパス、または現在のプロセスの実行可能ファイルを基準として解釈される相対ファイルパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-145">The path can be an absolute file path or a relative file path that is interpreted as relative to the current process's executable.</span></span> <span data-ttu-id="efe9b-146">それ以外の場合、UWP アプリでは、既定のユーザーデータフォルダーはパッケージのアプリデータフォルダーになります。UWP 以外のアプリの場合、既定のユーザーデータフォルダーは、 `{Executable File Name}.WebView2` アプリの実行可能ファイルの横にある同じディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-146">Otherwise, for UWP apps, the default user data folder will be the app data folder for the package; for non-UWP apps, the default user data folder `{Executable File Name}.WebView2` will be created in the same directory next to the app executable.</span></span> <span data-ttu-id="efe9b-147">プロセスに新しいフォルダーを作成する権限がないディレクトリで実行可能ファイルが実行されている場合、WebView2 の作成に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-147">WebView2 creation can fail if the executable is running in a directory that the process doesn't have permission to create a new folder in.</span></span> <span data-ttu-id="efe9b-148">アプリは、完了時にユーザーデータフォルダーをクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-148">The app is responsible to clean up its user data folder when it is done.</span></span>

<span data-ttu-id="efe9b-149">ブラウザープロセスが WebViews 間で共有されている可能性があることに注意してください。指定したオプションが共有ブラウザープロセスで現在実行されている WebViews のオプションと一致しない場合、WebView の作成は HRESULT_FROM_WIN32 (ERROR_INVALID_STATE) で失敗します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-149">Note that as a browser process might be shared among WebViews, WebView creation will fail with HRESULT_FROM_WIN32(ERROR_INVALID_STATE) if the specified options does not match the options of the WebViews that are currently running in the shared browser process.</span></span>

<span data-ttu-id="efe9b-150">environment_created_handler は、作成した WebView2Environment が含まれる async 操作に対するハンドラーの結果です。</span><span class="sxs-lookup"><span data-stu-id="efe9b-150">environment_created_handler is the handler result to the async operation which will contain the WebView2Environment that got created.</span></span>

<span data-ttu-id="efe9b-151">EnvironmentOptions の browserExecutableFolder、userDataFolder、および additionalBrowserArguments は、環境変数またはレジストリで指定した値によって上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-151">The browserExecutableFolder, userDataFolder and additionalBrowserArguments of the environmentOptions may be overridden by values either specified in environment variables or in the registry.</span></span>

<span data-ttu-id="efe9b-152">WebView2Environment を作成すると、次の環境変数がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-152">When creating a WebView2Environment the following environment variables are checked:</span></span>

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

<span data-ttu-id="efe9b-153">Override 環境変数が見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments の各値を CreateCoreWebView2EnvironmentWithOptions parameters の対応する値の代わりとして使います。</span><span class="sxs-lookup"><span data-stu-id="efe9b-153">If an override environment variable is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

<span data-ttu-id="efe9b-154">厳密には上書きしませんが、次のような追加の環境変数を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-154">While not strictly overrides, there exists additional environment variables that can be set:</span></span>

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="efe9b-155">空でない値が含まれる場合は、スクリプトデバッガーの下で WebView が起動されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-155">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger.</span></span> <span data-ttu-id="efe9b-156">この場合、WebView は cdp コマンドを発行し `Page.waitForDebugger` ます。これにより、デバッガーが対応する cdp コマンドを発行して実行を再開するまで、webview 内でスクリプトの実行が一時停止し `Runtime.runIfWaitingForDebugger` ます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-156">In this case, the WebView will issue a `Page.waitForDebugger` CDP command that will cause script execution inside the WebView to pause on launch, until a debugger issues a corresponding `Runtime.runIfWaitingForDebugger` CDP command to resume execution.</span></span> <span data-ttu-id="efe9b-157">注: この環境変数に相当するレジストリキーはありません。</span><span class="sxs-lookup"><span data-stu-id="efe9b-157">Note: There is no registry key equivalent of this environment variable.</span></span>

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="efe9b-158">空でない値が含まれる場合は、複数の WebViews を使うホストアプリケーションもサポートするスクリプトデバッガーで WebView が起動されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-158">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger that also supports host applications that use multiple WebViews.</span></span> <span data-ttu-id="efe9b-159">この値は、ホストアプリケーションによって新しい WebView が作成されるときに、開かれて書き込まれる名前付きパイプの識別子として使われます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-159">The value is used as the identifier for a named pipe that will be opened and written to when a new WebView is created by the host application.</span></span> <span data-ttu-id="efe9b-160">このペイロードは、リモートデバッグポートの JSON ターゲットと一致し、外部デバッガーが特定の WebView インスタンスにアタッチするために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-160">The payload will match that of the remote-debugging-port JSON target and can be used by the external debugger to attach to a specific WebView instance.</span></span> <span data-ttu-id="efe9b-161">デバッガーによって作成されるパイプの形式は、次のようになり `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` ます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-161">The format of the pipe created by the debugger should be: `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where:</span></span>

* `{app_name}` <span data-ttu-id="efe9b-162">は、ホストアプリケーションの exe ファイル名 (WebView2Example.exe など) です。</span><span class="sxs-lookup"><span data-stu-id="efe9b-162">is the host application exe filename, e.g. WebView2Example.exe</span></span>

* `{pipe_name}` <span data-ttu-id="efe9b-163">は WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER の値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="efe9b-163">is the value set for WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER.</span></span>

<span data-ttu-id="efe9b-164">JSON によって識別されたターゲットのデバッグを有効にするには、次の場所に WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数を設定する必要があり `--remote-debugging-port={port_num}` ます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-164">To enable debugging of the targets identified by the JSON you will also need to set the WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variable to send `--remote-debugging-port={port_num}` where:</span></span>

* `{port_num}` <span data-ttu-id="efe9b-165">は、CDP サーバーがバインドするポートです。</span><span class="sxs-lookup"><span data-stu-id="efe9b-165">is the port on which the CDP server will bind.</span></span>

<span data-ttu-id="efe9b-166">WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER と WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数の両方を設定すると、アプリケーションでホストされている WebViews とその内容がデバッガーなどのサードパーティアプリケーションに公開されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="efe9b-166">Be aware that setting both the WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER and WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variables will cause the WebViews hosted in your application and their contents to be exposed to 3rd party applications such as debuggers.</span></span>

<span data-ttu-id="efe9b-167">注: この環境変数に相当するレジストリキーはありません。</span><span class="sxs-lookup"><span data-stu-id="efe9b-167">Note: There is no registry key equivalent of this environment variable.</span></span>

<span data-ttu-id="efe9b-168">これらの環境変数が存在しない場合は、次のようにレジストリが検査されます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-168">If none of those environment variables exist, then the registry is examined next.</span></span> <span data-ttu-id="efe9b-169">次のレジストリキーがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="efe9b-169">The following registry keys are checked:</span></span>

```
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

<span data-ttu-id="efe9b-170">ブラウザーの更新中に WebView の一部のインスタンスが開かれる可能性が低いシナリオでは、古い Edge ブラウザーの削除がブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-170">In the unlikely scenario where some instances of WebView are open during a browser update we could end up blocking the deletion of old Edge browsers.</span></span> <span data-ttu-id="efe9b-171">ディスク領域が不足しないようにするために、新しい WebView の作成は、多数の古いバージョンが存在することが検出された場合、次のエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-171">To avoid running out of disk space a new WebView creation will fail with the next error if it detects that there are many old versions present.</span></span>

```
ERROR_DISK_FULL
```

<span data-ttu-id="efe9b-172">使用できる Edge バージョンの既定の最大数は20です。</span><span class="sxs-lookup"><span data-stu-id="efe9b-172">The default maximum number of Edge versions allowed is 20.</span></span>

<span data-ttu-id="efe9b-173">許可されている古い Edge バージョンの最大数は、次の環境変数の値で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-173">The maximum number of old Edge versions allowed can be overwritten with the value of the following environment variable.</span></span>

```
WEBVIEW2_MAX_INSTANCES
```

<span data-ttu-id="efe9b-174">Webview がインストールされたエッジに依存していて、それがアンインストールされると、次のエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-174">If the Webview depends on an installed Edge and it is uninstalled any subsequent creation will fail with the next error</span></span>

```
ERROR_PRODUCT_UNINSTALLED
```

<span data-ttu-id="efe9b-175">まず、Root を HKLM として、次に HKCU を確認します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-175">First we check with Root as HKLM and then HKCU.</span></span> <span data-ttu-id="efe9b-176">AppId は、最初に呼び出し元のプロセスのアプリケーションユーザーモデル ID に設定され、対応するレジストリキーがない場合、AppId は呼び出し元のプロセスの実行可能ファイル名に設定されます。それ以外の場合は、この値が ' \* ' である必要があります。</span><span class="sxs-lookup"><span data-stu-id="efe9b-176">AppId is first set to the Application User Model ID of the caller's process, then if there's no corresponding registry key the AppId is set to the executable name of the caller's process, or if that isn't a registry key then '\*'.</span></span> <span data-ttu-id="efe9b-177">上書きレジストリキーが見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments レジストリ値を CreateCoreWebView2EnvironmentWithOptions parameters の対応する値の代わりとして使います。</span><span class="sxs-lookup"><span data-stu-id="efe9b-177">If an override registry key is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments registry values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

#### <span data-ttu-id="efe9b-178">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="efe9b-178">GetAvailableCoreWebView2BrowserVersionString</span></span> 

> <span data-ttu-id="efe9b-179">パブリック STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)(PCWSTR browserExecutableFolder、LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="efe9b-179">public STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)(PCWSTR browserExecutableFolder, LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="efe9b-180">安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="efe9b-180">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

<span data-ttu-id="efe9b-181">チャネル名は、β、dev、カナリアです。</span><span class="sxs-lookup"><span data-stu-id="efe9b-181">Channel names are beta, dev, and canary.</span></span> <span data-ttu-id="efe9b-182">BrowserExecutableFolder またはチャネルの優先順位に対して上書きが存在する場合、override が使用されます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-182">If an override exists for the browserExecutableFolder or the channel preference, the override will be used.</span></span> <span data-ttu-id="efe9b-183">Override がない場合は、GetAvailableCoreWebView2BrowserVersionString に渡されたパラメーターが使われます。</span><span class="sxs-lookup"><span data-stu-id="efe9b-183">If there isn't an override, then the parameter passed to GetAvailableCoreWebView2BrowserVersionString is used.</span></span>

