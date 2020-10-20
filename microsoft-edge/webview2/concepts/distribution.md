---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: bf0a79d41d9eddf39a31426db79d502c09b782ad
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120348"
---
# <span data-ttu-id="abb84-104">WebView2 を使用したアプリの配布</span><span class="sxs-lookup"><span data-stu-id="abb84-104">Distribution of apps using WebView2</span></span>  

<span data-ttu-id="abb84-105">WebView2 アプリを配布するときには、アプリが起動される前に、バッキング web プラットフォーム ( [WebView2 Runtime][Webview2Installer]) が存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="abb84-105">When distributing your WebView2 app, make sure the backing web platform, the [WebView2 Runtime][Webview2Installer], is present before the app starts.</span></span>  <span data-ttu-id="abb84-106">この記事では、WebView2 Runtime をインストールして、WebView2 アプリの2つの配布モードを使用する方法について説明します。  [Evergreen](#evergreen-distribution-mode) と [Fixed Version](#fixed-version-distribution-mode)。</span><span class="sxs-lookup"><span data-stu-id="abb84-106">This article describes how you can install the WebView2 Runtime, and use the two distribution modes for your WebView2 app:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="abb84-107">Evergreen 配布モード</span><span class="sxs-lookup"><span data-stu-id="abb84-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="abb84-108">ほとんどの開発者は、Evergreen 配布モードをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abb84-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="abb84-109">Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="abb84-110">次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="abb84-111">基になる web プラットフォーム \ (WebView2 Runtime) は、追加の作業を行わなくても自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="abb84-112">Evergreen 配布モードを使うすべてのアプリは、Evergreen WebView2 ランタイムの共有コピーを使用します。これにより、ディスク領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="abb84-112">All apps that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  
    
### <span data-ttu-id="abb84-113">WebView2 ランタイムについて</span><span class="sxs-lookup"><span data-stu-id="abb84-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="abb84-114">WebView2 ランタイムは再配布可能なランタイムであり、WebView2 アプリのバッキング web プラットフォームとして機能します。</span><span class="sxs-lookup"><span data-stu-id="abb84-114">The WebView2 Runtime is a redistributable runtime and serves as the backing web platform for WebView2 apps.</span></span>  <span data-ttu-id="abb84-115">この概念は、Visual C++ や C++/.NET アプリの .NET ランタイムに似ています。</span><span class="sxs-lookup"><span data-stu-id="abb84-115">The concept is similar to Visual C++ or the .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="abb84-116">ランタイムには変更された Microsoft Edge \ (Chromium \) バイナリが含まれています。これは、アプリに対して適切に調整され、テストされています。</span><span class="sxs-lookup"><span data-stu-id="abb84-116">The Runtime contains modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for apps.</span></span>  <span data-ttu-id="abb84-117">ランタイムは、インストール時にユーザーに表示されるブラウザーとしては表示されません。</span><span class="sxs-lookup"><span data-stu-id="abb84-117">The Runtime does not appear as a user-visible browser upon installation.</span></span>  <span data-ttu-id="abb84-118">たとえば、ユーザーがブラウザーのデスクトップショートカットまたはスタートメニューエントリを持っていない場合などです。</span><span class="sxs-lookup"><span data-stu-id="abb84-118">For example, a user does not have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="abb84-119">開発およびテスト中には、いずれかの方法でバッキング web プラットフォームとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="abb84-119">During development and testing, you may use either as the backing web platform.</span></span>  

*   <span data-ttu-id="abb84-120">WebView2 ランタイム</span><span class="sxs-lookup"><span data-stu-id="abb84-120">The WebView2 Runtime</span></span>  
*   <span data-ttu-id="abb84-121">任意の Insider \ (永続的でない) Microsoft Edge \ (Chromium) ブラウザチャネル</span><span class="sxs-lookup"><span data-stu-id="abb84-121">Any Insider \(non-stable\) Microsoft Edge \(Chromium\) browser channel</span></span>  

<span data-ttu-id="abb84-122">運用環境では、アプリが起動される前に、ランタイムがユーザーデバイスに存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-122">In production environments, you must ensure the Runtime is present on user devices before the app starts.</span></span>  <span data-ttu-id="abb84-123">Microsoft Edge の厩舎チャネルは、WebView2 の使用には使用できません。</span><span class="sxs-lookup"><span data-stu-id="abb84-123">The Microsoft Edge Stable channel is unavailable for WebView2 usage.</span></span>  <span data-ttu-id="abb84-124">この決定により、アプリは、アプリが運用環境のブラウザーに依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="abb84-124">The decision prevents apps from taking a dependency on the browser in production.</span></span>

<span data-ttu-id="abb84-125">次の理由により、ブラウザーに依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="abb84-125">Do not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="abb84-126">Microsoft Edge \ (Chromium \) は、すべてのユーザーデバイスに存在することが保証されていません。</span><span class="sxs-lookup"><span data-stu-id="abb84-126">Microsoft Edge \(Chromium\) isn't guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="abb84-127">たとえば、Windows Update から切断された、または Microsoft によって直接管理されていないデバイス (Enterprise と EDU market の大部分) に、ブラウザーが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-127">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise and EDU market\) may not have the browser.</span></span>  <span data-ttu-id="abb84-128">WebView2 ランタイムの配布を許可することで、アプリの前提条件として、ブラウザーに依存することを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="abb84-128">Allowing you to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>  
*   <span data-ttu-id="abb84-129">ブラウザーやアプリにはさまざまなユースケースがあるため、ブラウザーで依存関係を取得すると、アプリに意図しない副次的な影響が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-129">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="abb84-130">たとえば、IT 管理者は、内部の web サイトとの互換性を維持するためにブラウザーをバージョン管理することができます。</span><span class="sxs-lookup"><span data-stu-id="abb84-130">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="abb84-131">WebView2 ランタイムを使うと、ブラウザーの更新がアクティブに管理されている間も、アプリは evergreen を維持できます。</span><span class="sxs-lookup"><span data-stu-id="abb84-131">The WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="abb84-132">ブラウザーとは異なり、アプリのシナリオに対してランタイムは開発およびテストされていますが、場合によっては、ブラウザーでまだ使用できないバグ修正が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="abb84-132">As opposed to the browser, the Runtime is developed and tested for app scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  
    
<span data-ttu-id="abb84-133">今後、Evergreen WebView2 ランタイムは Windows の将来のリリースで出荷される予定です。</span><span class="sxs-lookup"><span data-stu-id="abb84-133">In the future, the Evergreen WebView2 Runtime will ship in future releases of Windows.</span></span>  <span data-ttu-id="abb84-134">ランタイムがより汎用的に使用できるようになるまで、実行中のアプリでランタイムを展開します。</span><span class="sxs-lookup"><span data-stu-id="abb84-134">Deploy the Runtime with your production app until the Runtime becomes more universally available.</span></span>  

### <span data-ttu-id="abb84-135">Evergreen WebView2 ランタイムの展開</span><span class="sxs-lookup"><span data-stu-id="abb84-135">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="abb84-136">デバイス上のすべての Evergreen アプリには、1つの Evergreen WebView2 ランタイムのインストールのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="abb84-136">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="abb84-137">[WebView2 Runtime ダウンロードページ][Webview2Installer]には、多数のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="abb84-137">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer].</span></span>  <span data-ttu-id="abb84-138">Evergreen ランタイムの展開に役立つツールを次に示します。</span><span class="sxs-lookup"><span data-stu-id="abb84-138">The following tools help you deploy the Evergreen Runtime.</span></span>  

*   <span data-ttu-id="abb84-139">WebView2 Runtime ブートストラップは、ごくわずかな \ (約 2 MB \ 2 MB) インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="abb84-139">WebView2 Runtime Bootstrapper is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="abb84-140">WebView2 Runtime ブートストラップは、ユーザーのデバイスアーキテクチャと一致する Microsoft サーバーから Evergreen ランタイムをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="abb84-140">WebView2 Runtime Bootstrapper downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="abb84-141">ブートストラップをプログラムでダウンロードするためのリンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="abb84-141">Use a link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="abb84-142">WebView2 Runtime Standalone Installer は、オフライン環境で Evergreen WebView2 ランタイムをインストールできる完全なインストーラーです。</span><span class="sxs-lookup"><span data-stu-id="abb84-142">WebView2 Runtime Standalone Installer is a full installer that can install the Evergreen WebView2 Runtime in offline environments.</span></span>  
    
<span data-ttu-id="abb84-143">現時点では、ブートストラップとスタンドアロンインストーラーは両方ともコンピューターごとにインストールをサポートします。昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="abb84-143">Currently, both the bootstrapper and standalone installer only support per-machine installs, which requires elevation.</span></span>  <span data-ttu-id="abb84-144">昇格せずにインストーラーを実行すると、ユーザーにアクセス許可の昇格を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-144">If an installer is run without elevation, the user is prompted to elevate permissions.</span></span>  

<span data-ttu-id="abb84-145">アプリを起動する前にランタイムが既にインストールされていることを確認するために、次のワークフローをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abb84-145">We recommend the following workflows to ensure the Runtime is already installed before your app launches.</span></span>  <span data-ttu-id="abb84-146">シナリオによっては、ワークフローを調整できます。</span><span class="sxs-lookup"><span data-stu-id="abb84-146">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="abb84-147">サンプルの [リポジトリ][InstallerSample]にはサンプルコードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="abb84-147">Sample code is available in the [Samples repo][InstallerSample].</span></span>  

#### <span data-ttu-id="abb84-148">オンラインのみの展開</span><span class="sxs-lookup"><span data-stu-id="abb84-148">Online-only deployment</span></span>  

<span data-ttu-id="abb84-149">エンドユーザーがインターネット接続を使用することを前提としている、オンラインのみの展開シナリオがある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-149">If you have an online-only deployment scenario where end users are assumed to have internet access, complete the following steps.</span></span>  

1.  <span data-ttu-id="abb84-150">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abb84-150">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="abb84-151">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-151">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="abb84-152">レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。</span><span class="sxs-lookup"><span data-stu-id="abb84-152">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="abb84-153">`pv (REG_SZ)`次の場所で検索します。</span><span class="sxs-lookup"><span data-stu-id="abb84-153">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```
          
    *   <span data-ttu-id="abb84-154">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。</span><span class="sxs-lookup"><span data-stu-id="abb84-154">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="abb84-155">ランタイムがインストールされていない場合は、リンクを使用してブートストラップをプログラムでダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="abb84-155">If the Runtime isn't installed, use the link to programmatically download the bootstrapper.</span></span>  
1.  <span data-ttu-id="abb84-156">昇格したプロセスまたはコマンドプロンプトから、 `MicrosoftEdgeWebview2Setup.exe /silent /install` サイレントインストールのためにブートストラップを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="abb84-156">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  
    
<span data-ttu-id="abb84-157">前のワークフローには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-157">The previous workflow has the following benefits.</span></span>  

*   <span data-ttu-id="abb84-158">必要な場合、またはインストーラーをパッケージ化する必要がない場合にのみ、ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="abb84-158">Install the Runtime only when needed or when you're not required to package installers.</span></span>  
*   <span data-ttu-id="abb84-159">ブートストラップは、デバイスアーキテクチャを自動的に検出し、対応するランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="abb84-159">The bootstrapper automatically detects device architecture and installs the matching Runtime.</span></span> 
*   <span data-ttu-id="abb84-160">実行時にサイレントモードでインストールします。</span><span class="sxs-lookup"><span data-stu-id="abb84-160">Install the Runtime silently.</span></span>  
    
<span data-ttu-id="abb84-161">必要に応じてブートストラップをプログラムでダウンロードする代わりに、アプリと共にパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="abb84-161">You may also choose to package the bootstrapper with your app instead of programmatically downloading it on demand.</span></span>  

#### <span data-ttu-id="abb84-162">オフライン展開</span><span class="sxs-lookup"><span data-stu-id="abb84-162">Offline deployment</span></span>  

<span data-ttu-id="abb84-163">アプリの展開がオフラインで動作する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-163">If you have an offline deployment scenario where app deployment has to work entirely offline, complete the following steps.</span></span>  

1.  <span data-ttu-id="abb84-164">[スタンドアロンインストーラー][Webview2Installer]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="abb84-164">Download the [standalone installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="abb84-165">アプリのインストーラーまたはアップデーターにインストーラーを含めます。</span><span class="sxs-lookup"><span data-stu-id="abb84-165">Include the installer in your app installer or updater.</span></span>  
1.  <span data-ttu-id="abb84-166">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abb84-166">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="abb84-167">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-167">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="abb84-168">レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。</span><span class="sxs-lookup"><span data-stu-id="abb84-168">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="abb84-169">`pv (REG_SZ)`次の場所で検索します。</span><span class="sxs-lookup"><span data-stu-id="abb84-169">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```
          
    *   <span data-ttu-id="abb84-170">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。</span><span class="sxs-lookup"><span data-stu-id="abb84-170">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="abb84-171">ランタイムがインストールされていない場合は、スタンドアロンインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-171">If the Runtime isn't installed, run the standalone installer.</span></span>  <span data-ttu-id="abb84-172">サイレントインストールを実行する場合は、昇格したプロセスからインストーラーを実行するか、または [コピー] をクリックして、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abb84-172">If you want to run a silent installation, either run the installer from an elevated process or copy and run the following command.</span></span>  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <span data-ttu-id="abb84-173">Evergreen モードでの互換性を維持する</span><span class="sxs-lookup"><span data-stu-id="abb84-173">Stay compatible in Evergreen mode</span></span>

<span data-ttu-id="abb84-174">Web は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="abb84-174">The Web is constantly evolving.</span></span> <span data-ttu-id="abb84-175">Evergreen WebView2 Runtime は最新の機能とセキュリティ修正プログラムを提供するために最新の状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="abb84-175">The Evergreen WebView2 Runtime is kept up-to-date to provide you with the latest features and security fixes.</span></span>  <span data-ttu-id="abb84-176">アプリの web との互換性を維持するために、テストインフラストラクチャをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abb84-176">To ensure your app stays compatible with the web, we recommend you set up testing infrastructure.</span></span>

<span data-ttu-id="abb84-177">未安定の Microsoft Edge チャネル (ベータ/開発/カナリア) では、WebView2 Runtime の次の機能についてのヒントを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="abb84-177">Non-stable Microsoft Edge channels \(Beta/Dev/Canary\) provide a sneak peek into what is coming next into WebView2 Runtime.</span></span>  <span data-ttu-id="abb84-178">Microsoft Edge 用の web サイトを開発する場合と同様に、WebView2 アプリを定期的にテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="abb84-178">Just like developing websites for Microsoft Edge, we recommend that you test your WebView2 app regularly.</span></span>  <span data-ttu-id="abb84-179">WebView2 アプリを、非永続的なチャネルのいずれかに対してテストし、問題が発生した場合にアプリを更新したり、 [問題を報告][GithubMicrosoftedgeWebviewfeedback] したりします。</span><span class="sxs-lookup"><span data-stu-id="abb84-179">Test your WebView2 app against one of the non-stable channels, and update your app or [report issues][GithubMicrosoftedgeWebviewfeedback] if issues arise.</span></span> <span data-ttu-id="abb84-180">通常、開発者とベータ版が推奨されるチャネルです。</span><span class="sxs-lookup"><span data-stu-id="abb84-180">Typically Dev and Beta are the recommended channels.</span></span>  <span data-ttu-id="abb84-181">適切なチャネルを判断するには、「 [Microsoft Edge チャネルの概要」][DeployEdgeMicrosoftEdgeChannels]に移動します。</span><span class="sxs-lookup"><span data-stu-id="abb84-181">To help you decide which channel is right, navigate to [Overview of the Microsoft Edge channels][DeployEdgeMicrosoftEdgeChannels].</span></span>  <span data-ttu-id="abb84-182">テスト環境では、安定してい [ない Microsoft Edge チャネル][DownloadNonstableEdge] をダウンロードでき `regkey` ます。また、または環境変数を使用して、テストアプリのチャネルの優先順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="abb84-182">You can download the [non-stable Microsoft Edge channel][DownloadNonstableEdge] on your test environment, and use `regkey` or environment variables to indicate the channel preference for your testing app.</span></span>  <span data-ttu-id="abb84-183">詳細については、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="abb84-183">For more information, navigate to [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].</span></span>  <span data-ttu-id="abb84-184">また、 [Webdriver][HowtoWebdriver] を使って WebView2 のテストを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="abb84-184">You may also use [WebDriver][HowtoWebdriver] to automate WebView2 testing.</span></span>

## <span data-ttu-id="abb84-185">固定バージョンの配布モード</span><span class="sxs-lookup"><span data-stu-id="abb84-185">Fixed Version distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="abb84-186">修正されたバージョンの配布モードは、パブリックプレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="abb84-186">The Fixed Version distribution mode is in Public Preview.</span></span>  

<span data-ttu-id="abb84-187">修正されたバージョンの配布モードは、以前の名前として使用されていました。</span><span class="sxs-lookup"><span data-stu-id="abb84-187">The Fixed Version distribution mode was previously named bring-your-own.</span></span>  

<span data-ttu-id="abb84-188">厳密な互換性要件を持つ制約のある環境では、固定バージョンの配布モードの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="abb84-188">For constrained environments with strict compatibility requirements, consider using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="abb84-189">WebView2 ランタイムの特定のバージョンを、固定バージョンの配布モードで選択してパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="abb84-189">Select and package a specific version of the WebView2 Runtime using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="abb84-190">アプリのランタイム更新のタイミングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="abb84-190">You may specify the timing of Runtime updates for your app.</span></span>  <span data-ttu-id="abb84-191">固定バージョンの配布モードでは、自動更新は取得されません。</span><span class="sxs-lookup"><span data-stu-id="abb84-191">The Fixed Version distribution mode doesn't receive any automatic updates.</span></span> <span data-ttu-id="abb84-192">アプリとランタイムの更新を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-192">You should plan to update your app and the Runtime.</span></span>  

<span data-ttu-id="abb84-193">固定バージョンモードを使用するには、</span><span class="sxs-lookup"><span data-stu-id="abb84-193">To use the Fixed Version mode,</span></span>  

*   <span data-ttu-id="abb84-194">修正済みバージョンパッケージを[ダウンロード][Webview2Installer]して、パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="abb84-194">[Download][Webview2Installer] the Fixed Version package, and decompress the package.</span></span>  
*   <span data-ttu-id="abb84-195">プロジェクトに解凍された修正バージョンバイナリを含めます。</span><span class="sxs-lookup"><span data-stu-id="abb84-195">Include the decompressed Fixed Version binaries in your project.</span></span>  
*   <span data-ttu-id="abb84-196">WebView2 環境の作成時に、修正されたバージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="abb84-196">Indicate the path to the Fixed Version binaries when creating the WebView2 environment.</span></span>  
    *   <span data-ttu-id="abb84-197">Win32 C/c + + の場合は、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 関数を使って環境を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="abb84-197">For Win32 C/C++, you may create the environment using the [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] function.</span></span>  <span data-ttu-id="abb84-198">パラメーターを使って、修正された `browserExecutableFolder` バージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="abb84-198">Use the `browserExecutableFolder` parameter to indicate the path to the Fixed Version binaries.</span></span>  
    *   <span data-ttu-id="abb84-199">.NET の場合は、次のいずれかのオプションを使用して環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abb84-199">For .NET, you may do either of the following options to specify the environment.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="abb84-200">WebView2 プロパティを有効にするには、環境を指定する必要があり `Source` ます。</span><span class="sxs-lookup"><span data-stu-id="abb84-200">You must specify the environment before the WebView2 `Source` property takes effect.</span></span>  
        
        *   <span data-ttu-id="abb84-201">`CreationProperties`WebView2 要素で \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="abb84-201">Set the `CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) property on the WebView2 element.</span></span>  <span data-ttu-id="abb84-202">`BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) クラスのメンバーを使って、修正されたバージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="abb84-202">Use the `BrowserExecutableFolder` member in the `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) class to indicate the path to the Fixed Version binaries.</span></span>  
        *   <span data-ttu-id="abb84-203">`EnsureCoreWebView2Async`[WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / 環境を指定するには、\ (WPF[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) を使用します。</span><span class="sxs-lookup"><span data-stu-id="abb84-203">Use `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) to specify the environment.</span></span>  <span data-ttu-id="abb84-204">CoreWebView2Environment のパラメーターを使って、修正された `browserExecutableFolder` バージョンのバイナリへのパスを指定します[CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 。</span><span class="sxs-lookup"><span data-stu-id="abb84-204">Use the `browserExecutableFolder` parameter in [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] to indicate the path to the Fixed Version binaries.</span></span>  
*   <span data-ttu-id="abb84-205">アプリで、修正されたバージョンのバイナリをパッケージ化して配布します。</span><span class="sxs-lookup"><span data-stu-id="abb84-205">Package and ship the Fixed Version binaries with your app.</span></span>  <span data-ttu-id="abb84-206">必要に応じてバイナリを更新します。</span><span class="sxs-lookup"><span data-stu-id="abb84-206">Update the binaries as appropriate.</span></span>  
    
<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  

[HowtoWebdriver]: ../howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft ドキュメント"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "WebView2 クラスの CreateAsync-CoreWebView2Environment クラス |Microsoft ドキュメント"  

[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  

[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-WebView2 クラス | WebView2 クラス |Microsoft ドキュメント"  

[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  

[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "WebView2 クラス | WinForms クラス |Microsoft ドキュメント"  

[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "WebView2 クラスのプロパティの自動 WebView2 のプロパティ |Microsoft ドキュメント"  

[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス WebView2 | WinForms クラス |Microsoft ドキュメント"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  

[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  

[InstallerSample]: https://aka.ms/wv2installersample "WebView2 Installer のサンプル"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView のフィードバック |GitHub"  
