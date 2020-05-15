---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 58b32c1fe46183e55b8ac0bb4f4264b1f38e6eeb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654165"
---
# <span data-ttu-id="bba70-104">関数</span><span class="sxs-lookup"><span data-stu-id="bba70-104">Globals</span></span> 

> [!NOTE]
> <span data-ttu-id="bba70-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bba70-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="bba70-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba70-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

## <span data-ttu-id="bba70-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="bba70-107">Summary</span></span>

 <span data-ttu-id="bba70-108">Members</span><span class="sxs-lookup"><span data-stu-id="bba70-108">Members</span></span>                        | <span data-ttu-id="bba70-109">説明</span><span class="sxs-lookup"><span data-stu-id="bba70-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bba70-110">CreateWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="bba70-110">CreateWebView2EnvironmentWithDetails</span></span>](#createwebview2environmentwithdetails) | <span data-ttu-id="bba70-111">[DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、ブラウザーの追加スイッチを使って WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="bba70-111">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional browser switches.</span></span>
[<span data-ttu-id="bba70-112">CreateWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="bba70-112">CreateWebView2Environment</span></span>](#createwebview2environment) | <span data-ttu-id="bba70-113">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="bba70-113">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="bba70-114">GetWebView2BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="bba70-114">GetWebView2BrowserVersionInfo</span></span>](#getwebview2browserversioninfo) | <span data-ttu-id="bba70-115">安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bba70-115">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>
[<span data-ttu-id="bba70-116">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="bba70-116">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="bba70-117">このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bba70-117">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

## <span data-ttu-id="bba70-118">Members</span><span class="sxs-lookup"><span data-stu-id="bba70-118">Members</span></span>

#### <span data-ttu-id="bba70-119">CreateWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="bba70-119">CreateWebView2EnvironmentWithDetails</span></span> 

> <span data-ttu-id="bba70-120">パブリック STDAPI [CreateWebView2EnvironmentWithDetails](#createwebview2environmentwithdetails)(PCWSTR browserExecutableFolder、PCWSTR userDataFolder、PCWSTR additionalBrowserArguments、[IWebView2CreateWebView2EnvironmentCompletedHandler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span><span class="sxs-lookup"><span data-stu-id="bba70-120">public STDAPI [CreateWebView2EnvironmentWithDetails](#createwebview2environmentwithdetails)(PCWSTR browserExecutableFolder,PCWSTR userDataFolder,PCWSTR additionalBrowserArguments,[IWebView2CreateWebView2EnvironmentCompletedHandler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="bba70-121">[DLL エクスポート] を使用して、カスタムバージョンの Edge、ユーザーデータディレクトリ、ブラウザーの追加スイッチを使って WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="bba70-121">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional browser switches.</span></span>

<span data-ttu-id="bba70-122">browserExecutableFolder は、埋め込まれた端を含むフォルダーへの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="bba70-122">browserExecutableFolder is the relative path to the folder that contains the embedded Edge.</span></span> <span data-ttu-id="bba70-123">埋め込まれたエッジを取得するには、インストールされている Edge のフォルダーという名前のバージョン (インストールされている 73.0.52.0 Edge の 73.0.52.0 sub フォルダーなど) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="bba70-123">The embedded Edge can be obtained by copying the version named folder of an installed Edge, like 73.0.52.0 sub folder of an installed 73.0.52.0 Edge.</span></span> <span data-ttu-id="bba70-124">このフォルダーには、msedge、msedge などが含まれている必要があります。BrowserExecutableFolder に null または空の文字列を使用してコンピューターにインストールされている Edge を使用して、コンピューターにインストールされている microsoft Edge の互換性のあるバージョンを検索します。この場合は、ユーザーごとに最初にインストールしてから、コンピューターごとにインストールします。</span><span class="sxs-lookup"><span data-stu-id="bba70-124">The folder should have msedge.exe, msedge.dll, etc. Use null or empty string for browserExecutableFolder to create WebView using Edge installed on the machine, in which case the API will try to find a compatible version of Edge installed on the machine according to the channel preference trying to find first per user install and then per machine install.</span></span>

<span data-ttu-id="bba70-125">既定のチャネル検索順序は、安定、ベータ、dev、カナリアです。</span><span class="sxs-lookup"><span data-stu-id="bba70-125">The default channel search order is stable, beta, dev, and canary.</span></span> <span data-ttu-id="bba70-126">WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 環境変数または該当する releaseChannelPreference レジストリ値に1を指定すると、チャネルの検索順序が逆になります。</span><span class="sxs-lookup"><span data-stu-id="bba70-126">When there is an override WEBVIEW2_RELEASE_CHANNEL_PREFERENCE environment variable or applicable releaseChannelPreference registry value with the value of 1, the channel search order is reversed.</span></span>

<span data-ttu-id="bba70-127">userDataFolder を指定して、WebView2 の既定のユーザーデータフォルダーの場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bba70-127">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> <span data-ttu-id="bba70-128">パスには、絶対ファイルパス、または現在のプロセスの実行可能ファイルを基準として解釈される相対ファイルパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bba70-128">The path can be an absolute file path or a relative file path that is interpreted as relative to the current process's executable.</span></span> <span data-ttu-id="bba70-129">それ以外の場合、UWP アプリでは、既定のユーザーデータフォルダーはパッケージのアプリデータフォルダーになります。UWP 以外のアプリの場合、既定のユーザーデータフォルダーは、 `{Executable File Name}.WebView2` アプリの実行可能ファイルの横にある同じディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-129">Otherwise, for UWP apps, the default user data folder will be the app data folder for the package; for non-UWP apps, the default user data folder `{Executable File Name}.WebView2` will be created in the same directory next to the app executable.</span></span> <span data-ttu-id="bba70-130">プロセスに新しいフォルダーを作成する権限がないディレクトリで実行可能ファイルが実行されている場合、WebView2 の作成に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="bba70-130">WebView2 creation can fail if the executable is running in a directory that the process doesn't have permission to create a new folder in.</span></span> <span data-ttu-id="bba70-131">アプリは、完了時にユーザーデータフォルダーをクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba70-131">The app is responsible to clean up its user data folder when it is done.</span></span>

<span data-ttu-id="bba70-132">WebView の動作を変更するには、additionalBrowserArguments を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bba70-132">additionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> <span data-ttu-id="bba70-133">これらは、コマンドラインの一部としてブラウザープロセスに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-133">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="bba70-134">ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba70-134">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="bba70-135">コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-135">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="bba70-136">次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。</span><span class="sxs-lookup"><span data-stu-id="bba70-136">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="bba70-137">これらのスイッチは、指定した場合でも無視されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-137">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="bba70-138">同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-138">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="bba70-139">これは、などのスイッチにも適用されることに注意 `--enable-features` してください。</span><span class="sxs-lookup"><span data-stu-id="bba70-139">Note that this also applies to switches like `--enable-features`.</span></span> <span data-ttu-id="bba70-140">同じスイッチの異なる値をマージしようとすることはありません。</span><span class="sxs-lookup"><span data-stu-id="bba70-140">There is no attempt to merge the different values of the same switch.</span></span> <span data-ttu-id="bba70-141">アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-141">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="bba70-142">また、ブラウザープロセスが WebViews 間で共有されている可能性があるため、ブラウザープロセスを開始する最初の WebView を除き、スイッチは適用されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="bba70-142">Also note that as a browser process might be shared among WebViews, the switches are not guaranteed to be applied except for the first WebView that starts the browser process.</span></span> <span data-ttu-id="bba70-143">指定したスイッチの解析に失敗した場合、それらは無視されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-143">If parsing failed for the specified switches, they will be ignored.</span></span> `nullptr` <span data-ttu-id="bba70-144">フラグなしでブラウザープロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="bba70-144">will run browser process with no flags.</span></span>

<span data-ttu-id="bba70-145">environment_created_handler は、作成した WebView2Environment が含まれる async 操作に対するハンドラーの結果です。</span><span class="sxs-lookup"><span data-stu-id="bba70-145">environment_created_handler is the handler result to the async operation which will contain the WebView2Environment that got created.</span></span>

<span data-ttu-id="bba70-146">BrowserExecutableFolder、userDataFolder、または additionalBrowserArguments の各メンバーは、環境変数またはレジストリで指定した値によって上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bba70-146">The browserExecutableFolder, userDataFolder and additionalBrowserArguments members of the environmentParams may be overridden by values either specified in environment variables or in the registry.</span></span>

<span data-ttu-id="bba70-147">WebView2Environment を作成すると、次の環境変数がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="bba70-147">When creating a WebView2Environment the following environment variables are checked:</span></span>

```cpp
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

<span data-ttu-id="bba70-148">Override 環境変数が見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments の各値を CreateWebView2EnvironmentWithDetails parameters の対応する値の代わりとして使います。</span><span class="sxs-lookup"><span data-stu-id="bba70-148">If an override environment variable is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments values as replacements for the corresponding values in CreateWebView2EnvironmentWithDetails parameters.</span></span>

<span data-ttu-id="bba70-149">厳密には上書きしませんが、次のような追加の環境変数を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bba70-149">While not strictly overrides, there exists additional environment variables that can be set:</span></span>

```cpp
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="bba70-150">空でない値が含まれる場合は、スクリプトデバッガーの下で WebView が起動されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bba70-150">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger.</span></span> <span data-ttu-id="bba70-151">この場合、WebView は cdp コマンドを発行し `Page.waitForDebugger` ます。これにより、デバッガーが対応する cdp コマンドを発行して実行を再開するまで、webview 内でスクリプトの実行が一時停止し `Runtime.runIfWaitingForDebugger` ます。</span><span class="sxs-lookup"><span data-stu-id="bba70-151">In this case, the WebView will issue a `Page.waitForDebugger` CDP command that will cause script execution inside the WebView to pause on launch, until a debugger issues a corresponding `Runtime.runIfWaitingForDebugger` CDP command to resume execution.</span></span> <span data-ttu-id="bba70-152">注: この環境変数に相当するレジストリキーはありません。</span><span class="sxs-lookup"><span data-stu-id="bba70-152">Note: There is no registry key equivalent of this environment variable.</span></span>

```cpp
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="bba70-153">空でない値が含まれる場合は、複数の WebViews を使うホストアプリケーションもサポートするスクリプトデバッガーで WebView が起動されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bba70-153">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger that also supports host applications that use multiple WebViews.</span></span> <span data-ttu-id="bba70-154">この値は、ホストアプリケーションによって新しい WebView が作成されるときに、開かれて書き込まれる名前付きパイプの識別子として使われます。</span><span class="sxs-lookup"><span data-stu-id="bba70-154">The value is used as the identifier for a named pipe that will be opened and written to when a new WebView is created by the host application.</span></span> <span data-ttu-id="bba70-155">このペイロードは、リモートデバッグポートの JSON ターゲットと一致し、外部デバッガーが特定の WebView インスタンスにアタッチするために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bba70-155">The payload will match that of the remote-debugging-port JSON target and can be used by the external debugger to attach to a specific WebView instance.</span></span> <span data-ttu-id="bba70-156">デバッガーによって作成されるパイプの形式は、次のようになり `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` ます。</span><span class="sxs-lookup"><span data-stu-id="bba70-156">The format of the pipe created by the debugger should be: `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where:</span></span>

* `{app_name}` <span data-ttu-id="bba70-157">は、ホストアプリケーションの exe ファイル名です。例 WebView2Example</span><span class="sxs-lookup"><span data-stu-id="bba70-157">is the host application exe filename, e.g. WebView2Example.exe</span></span>

* `{pipe_name}` <span data-ttu-id="bba70-158">は WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER の値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="bba70-158">is the value set for WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER.</span></span>

<span data-ttu-id="bba70-159">JSON によって識別されたターゲットのデバッグを有効にするには、次の場所に WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数を設定する必要があり `--remote-debugging-port={port_num}` ます。</span><span class="sxs-lookup"><span data-stu-id="bba70-159">To enable debugging of the targets identified by the JSON you will also need to set the WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variable to send `--remote-debugging-port={port_num}` where:</span></span>

* `{port_num}` <span data-ttu-id="bba70-160">は、CDP サーバーがバインドするポートです。</span><span class="sxs-lookup"><span data-stu-id="bba70-160">is the port on which the CDP server will bind.</span></span>

<span data-ttu-id="bba70-161">WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER と WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 環境変数の両方を設定すると、アプリケーションでホストされている WebViews とその内容がデバッガーなどのサードパーティアプリケーションに公開されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bba70-161">Be aware that setting both the WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER and WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variables will cause the WebViews hosted in your application and their contents to be exposed to 3rd party applications such as debuggers.</span></span>

<span data-ttu-id="bba70-162">注: この環境変数に相当するレジストリキーはありません。</span><span class="sxs-lookup"><span data-stu-id="bba70-162">Note: There is no registry key equivalent of this environment variable.</span></span>

<span data-ttu-id="bba70-163">これらの環境変数が存在しない場合は、次のようにレジストリが検査されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-163">If none of those environment variables exist, then the registry is examined next.</span></span> <span data-ttu-id="bba70-164">次のレジストリキーがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="bba70-164">The following registry keys are checked:</span></span>

```cpp
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

<span data-ttu-id="bba70-165">ブラウザーの更新中に WebView の一部のインスタンスが開かれる可能性が低いシナリオでは、古い Edge ブラウザーの削除がブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="bba70-165">In the unlikely scenario where some instances of WebView are open during a browser update we could end up blocking the deletion of old Edge browsers.</span></span> <span data-ttu-id="bba70-166">ディスク領域が不足しないようにするために、新しい WebView の作成は、多数の古いバージョンが存在することが検出された場合、次のエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="bba70-166">To avoid running out of disk space a new WebView creation will fail with the next error if it detects that there are many old versions present.</span></span>

```cpp
ERROR_DISK_FULL
```

<span data-ttu-id="bba70-167">使用できる Edge バージョンの既定の最大数は20です。</span><span class="sxs-lookup"><span data-stu-id="bba70-167">The default maximum number of Edge versions allowed is 20.</span></span>

<span data-ttu-id="bba70-168">許可されている古い Edge バージョンの最大数は、次の環境変数の値で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="bba70-168">The maximum number of old Edge versions allowed can be overwritten with the value of the following environment variable.</span></span>

```cpp
WEBVIEW2_MAX_INSTANCES
```

<span data-ttu-id="bba70-169">Webview がインストールされたエッジに依存していて、それがアンインストールされると、次のエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="bba70-169">If the Webview depends on an installed Edge and it is uninstalled any subsequent creation will fail with the next error</span></span>

```cpp
ERROR_PRODUCT_UNINSTALLED
```

<span data-ttu-id="bba70-170">まず、Root を HKLM として、次に HKCU を確認します。</span><span class="sxs-lookup"><span data-stu-id="bba70-170">First we check with Root as HKLM and then HKCU.</span></span> <span data-ttu-id="bba70-171">AppId は、最初に呼び出し元のプロセスのアプリケーションユーザーモデル ID に設定され、対応するレジストリキーがない場合、AppId は呼び出し元のプロセスの実行可能ファイル名に設定されます。それ以外の場合は、この値が ' \* ' である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba70-171">AppId is first set to the Application User Model ID of the caller's process, then if there's no corresponding registry key the AppId is set to the executable name of the caller's process, or if that isn't a registry key then '\*'.</span></span> <span data-ttu-id="bba70-172">上書きレジストリキーが見つかった場合は、browserExecutableFolder、userDataFolder、additionalBrowserArguments レジストリ値を CreateWebView2EnvironmentWithDetails parameters の対応する値の代わりとして使います。</span><span class="sxs-lookup"><span data-stu-id="bba70-172">If an override registry key is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments registry values as replacements for the corresponding values in CreateWebView2EnvironmentWithDetails parameters.</span></span> <span data-ttu-id="bba70-173">いずれかのレジストリ値が存在しない場合は、CreateWebView2Environment に渡されたパラメーターが使われます。</span><span class="sxs-lookup"><span data-stu-id="bba70-173">If any of those registry values isn't present, then the parameter passed to CreateWebView2Environment is used.</span></span>

#### <span data-ttu-id="bba70-174">CreateWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="bba70-174">CreateWebView2Environment</span></span> 

> <span data-ttu-id="bba70-175">パブリック STDAPI [CreateWebView2Environment](#createwebview2environment)([IWebView2CreateWebView2EnvironmentCompletedHandler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span><span class="sxs-lookup"><span data-stu-id="bba70-175">public STDAPI [CreateWebView2Environment](#createwebview2environment)([IWebView2CreateWebView2EnvironmentCompletedHandler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="bba70-176">インストールされている Edge バージョンを使って、evergreen WebView2 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="bba70-176">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

<span data-ttu-id="bba70-177">これは、CreateWebView2EnvironmentWithDetails と browserExecutableFolder、userDataFolder、additionalBrowserArguments を使用してを呼び出すことに相当します。</span><span class="sxs-lookup"><span data-stu-id="bba70-177">This is equivalent to calling CreateWebView2EnvironmentWithDetails with nullptr for browserExecutableFolder, userDataFolder, additionalBrowserArguments.</span></span> <span data-ttu-id="bba70-178">詳細については、「CreateWebView2EnvironmentWithDetails」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba70-178">See CreateWebView2EnvironmentWithDetails for more details.</span></span>

#### <span data-ttu-id="bba70-179">GetWebView2BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="bba70-179">GetWebView2BrowserVersionInfo</span></span> 

> <span data-ttu-id="bba70-180">パブリック STDAPI [GetWebView2BrowserVersionInfo](#getwebview2browserversioninfo)(PCWSTR browserExecutableFolder、LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="bba70-180">public STDAPI [GetWebView2BrowserVersionInfo](#getwebview2browserversioninfo)(PCWSTR browserExecutableFolder,LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="bba70-181">安定したチャネルまたは埋め込みエッジでない場合は、チャネル名などのブラウザーのバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bba70-181">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

<span data-ttu-id="bba70-182">チャネル名は、β、dev、カナリアです。</span><span class="sxs-lookup"><span data-stu-id="bba70-182">Channel names are beta, dev, and canary.</span></span> <span data-ttu-id="bba70-183">BrowserExecutableFolder またはチャネルの優先順位に対して上書きが存在する場合、override が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-183">If an override exists for the browserExecutableFolder or the channel preference, the override will be used.</span></span> <span data-ttu-id="bba70-184">Override がない場合は、GetWebView2BrowserVersionInfo に渡されたパラメーターが使われます。</span><span class="sxs-lookup"><span data-stu-id="bba70-184">If there isn't an override, then the parameter passed to GetWebView2BrowserVersionInfo is used.</span></span>

#### <span data-ttu-id="bba70-185">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="bba70-185">CompareBrowserVersions</span></span> 

> <span data-ttu-id="bba70-186">パブリック STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR VERSION1、PCWSTR version2、int \* result)</span><span class="sxs-lookup"><span data-stu-id="bba70-186">public STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR version1,PCWSTR version2,int \* result)</span></span>

<span data-ttu-id="bba70-187">このメソッドは、すべてのバージョンが正しいかどうかを調べるために、バージョンを適切に比較することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bba70-187">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

<span data-ttu-id="bba70-188">Webview2 または特定の機能ベースをバージョンで使うかどうかを決定するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bba70-188">It can be used to determine whether to use webview2 or certain feature base on version.</span></span> <span data-ttu-id="bba70-189">結果の値を-1、0、または1に設定します (version1 が version2 より小さいか、等しいか、等しい場合)。</span><span class="sxs-lookup"><span data-stu-id="bba70-189">Sets the value of result to -1, 0 or 1 if version1 is less than, equal or greater than version2 respectively.</span></span> <span data-ttu-id="bba70-190">いずれかのバージョン文字列が解析できなかった場合、または入力パラメーターが null である場合に E_INVALIDARG を返します。</span><span class="sxs-lookup"><span data-stu-id="bba70-190">Returns E_INVALIDARG if it fails to parse any of the version strings or any input parameter is null.</span></span> <span data-ttu-id="bba70-191">入力では、GetWebView2BrowserVersionInfo から取得した versionInfo を直接使うことができます。チャネル情報は無視されます。</span><span class="sxs-lookup"><span data-stu-id="bba70-191">Input can directly use the versionInfo obtained from GetWebView2BrowserVersionInfo, channel info will be ignored.</span></span>

