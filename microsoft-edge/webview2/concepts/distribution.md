---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 14f252b0155beb6bfce0b01dc080900f2d3e57ee
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195167"
---
# <span data-ttu-id="08ab6-104">WebView2 を使用したアプリの配布</span><span class="sxs-lookup"><span data-stu-id="08ab6-104">Distribution of apps using WebView2</span></span>  

<span data-ttu-id="08ab6-105">WebView2 アプリを配布するときには、アプリが起動される前に、バッキング web プラットフォーム ( [WebView2 Runtime][Webview2Installer]) が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-105">When distributing your WebView2 app, ensure the backing web platform, the [WebView2 Runtime][Webview2Installer], is present before the app starts.</span></span>  <span data-ttu-id="08ab6-106">この記事では、WebView2 ランタイムをインストールする方法について説明し、WebView2 アプリ用の2つの配布モード (  [Evergreen](#evergreen-distribution-mode) と [Fixed のバージョン](#fixed-version-distribution-mode)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-106">This article describes how you \(the developer\) install the WebView2 Runtime, and use the two distribution modes for your WebView2 app:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="08ab6-107">Evergreen 配布モード</span><span class="sxs-lookup"><span data-stu-id="08ab6-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="08ab6-108">ほとんどの開発者は、Evergreen 配布モードをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="08ab6-109">Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="08ab6-110">次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="08ab6-111">基になる web プラットフォーム \ (WebView2 Runtime) は、追加の作業を行わなくても自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="08ab6-112">Evergreen 配布モードを使うすべてのアプリは、Evergreen WebView2 ランタイムの共有コピーを使用します。これにより、ディスク領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-112">All apps that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  
    
### <span data-ttu-id="08ab6-113">WebView2 ランタイムについて</span><span class="sxs-lookup"><span data-stu-id="08ab6-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="08ab6-114">WebView2 ランタイムは再配布可能なランタイムであり、WebView2 アプリのバッキング web プラットフォームとして機能します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-114">The WebView2 Runtime is a redistributable runtime and serves as the backing web platform for WebView2 apps.</span></span>  <span data-ttu-id="08ab6-115">この概念は、Visual C++ や C++/.NET アプリの .NET ランタイムに似ています。</span><span class="sxs-lookup"><span data-stu-id="08ab6-115">The concept is similar to Visual C++ or the .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="08ab6-116">ランタイムには変更された Microsoft Edge \ (Chromium \) バイナリが含まれています。これは、アプリに対して適切に調整され、テストされています。</span><span class="sxs-lookup"><span data-stu-id="08ab6-116">The Runtime contains modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for apps.</span></span>  <span data-ttu-id="08ab6-117">ランタイムは、インストール時にユーザーに表示されるブラウザーとしては表示されません。</span><span class="sxs-lookup"><span data-stu-id="08ab6-117">The Runtime does not appear as a user-visible browser upon installation.</span></span>  <span data-ttu-id="08ab6-118">たとえば、ユーザーがブラウザーのデスクトップショートカットまたはスタートメニューエントリを持っていない場合などです。</span><span class="sxs-lookup"><span data-stu-id="08ab6-118">For example, a user does not have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="08ab6-119">開発およびテスト中には、いずれかの方法でバッキング web プラットフォームとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-119">During development and testing, you may use either as the backing web platform.</span></span>  

*   <span data-ttu-id="08ab6-120">WebView2 ランタイム</span><span class="sxs-lookup"><span data-stu-id="08ab6-120">The WebView2 Runtime</span></span>  
*   <span data-ttu-id="08ab6-121">任意の Insider \ (永続的でない) Microsoft Edge \ (Chromium) ブラウザチャネル</span><span class="sxs-lookup"><span data-stu-id="08ab6-121">Any Insider \(non-stable\) Microsoft Edge \(Chromium\) browser channel</span></span>  
    
<span data-ttu-id="08ab6-122">運用環境では、アプリが起動される前に、ランタイムがユーザーデバイスに存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-122">In production environments, you must ensure the Runtime is present on user devices before the app starts.</span></span>  <span data-ttu-id="08ab6-123">Microsoft Edge の厩舎チャネルは、WebView2 の使用には使用できません。</span><span class="sxs-lookup"><span data-stu-id="08ab6-123">The Microsoft Edge Stable channel is unavailable for WebView2 usage.</span></span>  <span data-ttu-id="08ab6-124">この決定により、アプリは、アプリが運用環境のブラウザーに依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-124">The decision prevents apps from taking a dependency on the browser in production.</span></span>

<span data-ttu-id="08ab6-125">次の理由により、ブラウザーに依存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-125">Do not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="08ab6-126">Microsoft Edge \ (Chromium \) は、すべてのユーザーデバイスに存在するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="08ab6-126">Microsoft Edge \(Chromium\) is not guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="08ab6-127">たとえば、Windows Update から切断された、または Microsoft によって直接管理されていないデバイス (Enterprise と EDU market の大部分) に、ブラウザーが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-127">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise and EDU market\) may not have the browser.</span></span>  <span data-ttu-id="08ab6-128">WebView2 ランタイムの配布を許可することで、アプリの前提条件として、ブラウザーに依存することを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-128">Allowing you to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>  
*   <span data-ttu-id="08ab6-129">ブラウザーやアプリにはさまざまなユースケースがあるため、ブラウザーで依存関係を取得すると、アプリに意図しない副次的な影響が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-129">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="08ab6-130">たとえば、IT 管理者は、内部の web サイトとの互換性を維持するためにブラウザーをバージョン管理することができます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-130">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="08ab6-131">WebView2 ランタイムを使うと、ブラウザーの更新がアクティブに管理されている間も、アプリは evergreen を維持できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-131">The WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="08ab6-132">ブラウザーとは異なり、アプリのシナリオに対してランタイムは開発およびテストされていますが、場合によっては、ブラウザーでまだ使用できないバグ修正が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-132">As opposed to the browser, the Runtime is developed and tested for app scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  
    
<span data-ttu-id="08ab6-133">今後、Evergreen WebView2 Runtime は、Windows の将来のリリースと共に出荷される予定です。</span><span class="sxs-lookup"><span data-stu-id="08ab6-133">In the future, the Evergreen WebView2 Runtime plans to ship with future releases of Windows.</span></span>  <span data-ttu-id="08ab6-134">ランタイムがより汎用的に使用できるようになるまで、実行中のアプリでランタイムを展開します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-134">Deploy the Runtime with your production app until the Runtime becomes more universally available.</span></span>  

### <span data-ttu-id="08ab6-135">Evergreen WebView2 ランタイムの展開</span><span class="sxs-lookup"><span data-stu-id="08ab6-135">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="08ab6-136">デバイス上のすべての Evergreen アプリには、1つの Evergreen WebView2 ランタイムのインストールのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="08ab6-136">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="08ab6-137">[WebView2 Runtime ダウンロードページ][Webview2Installer]には、多数のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="08ab6-137">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer].</span></span>  <span data-ttu-id="08ab6-138">Evergreen ランタイムの展開に役立つツールを次に示します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-138">The following tools help you deploy the Evergreen Runtime.</span></span>  

*   <span data-ttu-id="08ab6-139">WebView2 Runtime ブートストラップは、ごくわずかな \ (約 2 MB \ 2 MB) インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="08ab6-139">WebView2 Runtime Bootstrapper is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="08ab6-140">WebView2 Runtime ブートストラップは、ユーザーのデバイスアーキテクチャと一致する Microsoft サーバーから Evergreen ランタイムをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-140">WebView2 Runtime Bootstrapper downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="08ab6-141">ブートストラップをプログラムでダウンロードするためのリンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-141">Use a link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="08ab6-142">WebView2 Runtime Standalone Installer は、オフライン環境に Evergreen WebView2 ランタイムをインストールする完全なインストーラーです。</span><span class="sxs-lookup"><span data-stu-id="08ab6-142">WebView2 Runtime Standalone Installer is a full installer that installs the Evergreen WebView2 Runtime in offline environments.</span></span>  
    
<span data-ttu-id="08ab6-143">現時点では、ブートストラップとスタンドアロンインストーラーは両方ともコンピューターごとにインストールをサポートします。昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="08ab6-143">Currently, both the bootstrapper and standalone installer only support per-machine installs, which requires elevation.</span></span>  <span data-ttu-id="08ab6-144">昇格せずにインストーラーを実行すると、ユーザーにアクセス許可の昇格を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-144">If an installer is run without elevation, the user is prompted to elevate permissions.</span></span>  

<span data-ttu-id="08ab6-145">次のワークフローを使用して、アプリを起動する前にランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-145">Use following workflows to ensure the Runtime is already installed before your app launches.</span></span>  <span data-ttu-id="08ab6-146">シナリオによっては、ワークフローを調整できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-146">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="08ab6-147">サンプルの [リポジトリ][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]にはサンプルコードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="08ab6-147">Sample code is available in the [Samples repo][GitHubMicrosoftedgeWebView2samplesWebview2Deployment].</span></span>  

#### <span data-ttu-id="08ab6-148">オンラインのみの展開</span><span class="sxs-lookup"><span data-stu-id="08ab6-148">Online-only deployment</span></span>  

<span data-ttu-id="08ab6-149">ユーザーがインターネットにアクセスできると見なされるオンラインのみの展開シナリオがある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-149">If you have an online-only deployment scenario where users are assumed to have internet access, complete the following steps.</span></span>  

1.  <span data-ttu-id="08ab6-150">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-150">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="08ab6-151">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-151">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="08ab6-152">レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-152">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="08ab6-153">`pv (REG_SZ)`次の場所で検索します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-153">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="08ab6-154">64ビット版の Windows の場合</span><span class="sxs-lookup"><span data-stu-id="08ab6-154">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="08ab6-155">32ビット版の Windows の場合</span><span class="sxs-lookup"><span data-stu-id="08ab6-155">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="08ab6-156">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-156">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="08ab6-157">ランタイムがインストールされていない場合は、リンクを使用してブートストラップをプログラムでダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-157">If the Runtime is not installed, use the link to programmatically download the bootstrapper.</span></span>  
1.  <span data-ttu-id="08ab6-158">昇格したプロセスまたはコマンドプロンプトから、 `MicrosoftEdgeWebview2Setup.exe /silent /install` サイレントインストールのためにブートストラップを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-158">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  
    
<span data-ttu-id="08ab6-159">前のワークフローには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-159">The previous workflow has the following benefits.</span></span>  

*   <span data-ttu-id="08ab6-160">必要な場合、またはインストーラーをパッケージ化する必要がない場合にのみ、ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-160">Install the Runtime only when needed or when you are not required to package installers.</span></span>  
*   <span data-ttu-id="08ab6-161">ブートストラップは、デバイスアーキテクチャを自動的に検出し、対応するランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-161">The bootstrapper automatically detects device architecture and installs the matching Runtime.</span></span>  
*   <span data-ttu-id="08ab6-162">実行時にサイレントモードでインストールします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-162">Install the Runtime silently.</span></span>  
    
<span data-ttu-id="08ab6-163">必要に応じてブートストラップをプログラムでダウンロードする代わりに、アプリと共にパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-163">You may also choose to package the bootstrapper with your app instead of programmatically downloading it on demand.</span></span>  

#### <span data-ttu-id="08ab6-164">オフライン展開</span><span class="sxs-lookup"><span data-stu-id="08ab6-164">Offline deployment</span></span>  

<span data-ttu-id="08ab6-165">アプリの展開がオフラインで動作する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-165">If you have an offline deployment scenario where app deployment has to work entirely offline, complete the following steps.</span></span>  

1.  <span data-ttu-id="08ab6-166">[スタンドアロンインストーラー][Webview2Installer]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-166">Download the [standalone installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="08ab6-167">アプリのインストーラーまたはアップデーターにインストーラーを含めます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-167">Include the installer in your app installer or updater.</span></span>  
1.  <span data-ttu-id="08ab6-168">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-168">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="08ab6-169">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-169">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="08ab6-170">レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-170">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="08ab6-171">`pv (REG_SZ)`次の場所で検索します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-171">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="08ab6-172">64ビット版の Windows の場合</span><span class="sxs-lookup"><span data-stu-id="08ab6-172">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="08ab6-173">32ビット版の Windows の場合</span><span class="sxs-lookup"><span data-stu-id="08ab6-173">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="08ab6-174">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-174">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="08ab6-175">ランタイムがインストールされていない場合は、スタンドアロンインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-175">If the Runtime is not installed, run the standalone installer.</span></span>  <span data-ttu-id="08ab6-176">サイレントインストールを実行する場合は、昇格したプロセスからインストーラーを実行するか、または [コピー] をクリックして、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-176">If you want to run a silent installation, either run the installer from an elevated process or copy and run the following command.</span></span>  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <span data-ttu-id="08ab6-177">Evergreen モードでの互換性を維持する</span><span class="sxs-lookup"><span data-stu-id="08ab6-177">Stay compatible in Evergreen mode</span></span>  

<span data-ttu-id="08ab6-178">Web は絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="08ab6-178">The Web is constantly evolving.</span></span>  <span data-ttu-id="08ab6-179">Evergreen WebView2 Runtime は最新の機能とセキュリティ修正プログラムを提供するために最新の状態に維持されます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-179">The Evergreen WebView2 Runtime is kept up to date to provide you with the latest features and security fixes.</span></span>  <span data-ttu-id="08ab6-180">アプリの web との互換性を維持するために、テストインフラストラクチャを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-180">To ensure your app stays compatible with the web, you should set up testing infrastructure.</span></span>  

<span data-ttu-id="08ab6-181">未安定の Microsoft Edge チャネル (ベータ/開発/カナリア) では、WebView2 Runtime の次の機能についてのヒントを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-181">Non-stable Microsoft Edge channels \(Beta/Dev/Canary\) provide a sneak peek into what is coming next into WebView2 Runtime.</span></span>  <span data-ttu-id="08ab6-182">Microsoft Edge 用の web サイトを開発する場合と同様に、WebView2 アプリを定期的にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-182">Just like developing websites for Microsoft Edge, you should test your WebView2 app regularly.</span></span>  <span data-ttu-id="08ab6-183">WebView2 アプリを、非永続的なチャネルのいずれかに対してテストし、問題が発生した場合にアプリを更新したり、 [問題を報告][GithubMicrosoftedgeWebviewfeedback] したりします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-183">Test your WebView2 app against one of the non-stable channels, and update your app or [report issues][GithubMicrosoftedgeWebviewfeedback] if issues arise.</span></span> <span data-ttu-id="08ab6-184">通常、開発者とベータ版が推奨されるチャネルです。</span><span class="sxs-lookup"><span data-stu-id="08ab6-184">Typically Dev and Beta are the recommended channels.</span></span>  <span data-ttu-id="08ab6-185">適切なチャネルを判断するには、「 [Microsoft Edge チャネルの概要」][DeployEdgeMicrosoftEdgeChannels]に移動します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-185">To help you decide which channel is right, navigate to [Overview of the Microsoft Edge channels][DeployEdgeMicrosoftEdgeChannels].</span></span>  <span data-ttu-id="08ab6-186">テスト環境では、安定してい [ない Microsoft Edge チャネル][DownloadNonstableEdge] をダウンロードでき `regkey` ます。また、または環境変数を使用して、テストアプリのチャネルの優先順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-186">You may download the [non-stable Microsoft Edge channel][DownloadNonstableEdge] on your test environment, and use `regkey` or environment variables to indicate the channel preference for your testing app.</span></span>  <span data-ttu-id="08ab6-187">詳細については、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="08ab6-187">For more information, navigate to [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].</span></span>  <span data-ttu-id="08ab6-188">また、 [Webdriver][HowtoWebdriver] を使って WebView2 のテストを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-188">You may also use [WebDriver][HowtoWebdriver] to automate WebView2 testing.</span></span>

## <span data-ttu-id="08ab6-189">固定バージョンの配布モード</span><span class="sxs-lookup"><span data-stu-id="08ab6-189">Fixed Version distribution mode</span></span>   

<span data-ttu-id="08ab6-190">厳密な互換性要件を持つ制約のある環境では、固定バージョンの配布モードの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="08ab6-190">For constrained environments with strict compatibility requirements, consider using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="08ab6-191">WebView2 ランタイムの特定のバージョンを、固定バージョンの配布モードで選択してパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-191">Choose and package a specific version of the WebView2 Runtime using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="08ab6-192">アプリのランタイム更新のタイミングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-192">You may specify the timing of Runtime updates for your app.</span></span>  <span data-ttu-id="08ab6-193">修正済みのバージョン配布モードでは、自動更新は取得されません。</span><span class="sxs-lookup"><span data-stu-id="08ab6-193">The Fixed Version distribution mode does not receive any automatic updates.</span></span> <span data-ttu-id="08ab6-194">アプリとランタイムの更新を計画します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-194">Plan to update your app and the Runtime.</span></span>  

> [!NOTE] 
> <span data-ttu-id="08ab6-195">修正されたバージョンの配布モードは、以前は "自分で作成" と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="08ab6-195">The Fixed Version distribution mode was previously called bring-your-own.</span></span>  

<span data-ttu-id="08ab6-196">修正済みバージョンモードを使用するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-196">To use the Fixed Version mode, complete the following actions</span></span>

1.  <span data-ttu-id="08ab6-197">修正済みバージョンパッケージを[ダウンロード][Webview2Installer]します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-197">[Download][Webview2Installer] the Fixed Version package.</span></span> 
1.  <span data-ttu-id="08ab6-198">コマンドライン `expand {path to the package} -F:* {path to the destination folder}` または WinRAR などのツールを使用してパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-198">Decompress the package using command line `expand {path to the package} -F:* {path to the destination folder}` or with tools such as WinRAR.</span></span> <span data-ttu-id="08ab6-199">適切なフォルダー構造が生成されない可能性があるため、エクスプローラーを使用して伸長しないようにします。</span><span class="sxs-lookup"><span data-stu-id="08ab6-199">Avoid decompressing through the File Explorer as it may not generate the correct folder structure.</span></span>  
1.  <span data-ttu-id="08ab6-200">プロジェクトに解凍された修正バージョンバイナリを含めます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-200">Include the decompressed Fixed Version binaries in your project.</span></span>  
1.  <span data-ttu-id="08ab6-201">WebView2 環境の作成時に、修正されたバージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-201">Indicate the path to the Fixed Version binaries when creating the WebView2 environment.</span></span>  
    *   <span data-ttu-id="08ab6-202">Win32 C/c + + の場合は、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 関数を使って環境を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-202">For Win32 C/C++, you may create the environment using the [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] function.</span></span>  <span data-ttu-id="08ab6-203">パラメーターを使用して、が `browserExecutableFolder` 含まれているフォルダーへのパスを指定し `msedgewebview2.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-203">Use the `browserExecutableFolder` parameter to indicate the path to the folder containing `msedgewebview2.exe`.</span></span>  
    *   <span data-ttu-id="08ab6-204">.NET の場合は、次のいずれかのオプションを使用して環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-204">For .NET, you may do either of the following options to specify the environment.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="08ab6-205">WebView2 プロパティを有効にするには、環境を指定する必要があり `Source` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-205">You must specify the environment before the WebView2 `Source` property takes effect.</span></span>  
        
        *   <span data-ttu-id="08ab6-206">`CreationProperties`WebView2 要素で \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-206">Set the `CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) property on the WebView2 element.</span></span>  <span data-ttu-id="08ab6-207">`BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) クラスのメンバーを使って、修正されたバージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-207">Use the `BrowserExecutableFolder` member in the `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) class to indicate the path to the Fixed Version binaries.</span></span>  
        *   <span data-ttu-id="08ab6-208">`EnsureCoreWebView2Async`[WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / 環境を指定するには、\ (WPF[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-208">Use `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) to specify the environment.</span></span>  <span data-ttu-id="08ab6-209">CoreWebView2Environment のパラメーターを使って、修正された `browserExecutableFolder` バージョンのバイナリへのパスを指定します[CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 。</span><span class="sxs-lookup"><span data-stu-id="08ab6-209">Use the `browserExecutableFolder` parameter in [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] to indicate the path to the Fixed Version binaries.</span></span>  
1.  <span data-ttu-id="08ab6-210">アプリで、修正されたバージョンのバイナリをパッケージ化して配布します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-210">Package and ship the Fixed Version binaries with your app.</span></span>  <span data-ttu-id="08ab6-211">必要に応じてバイナリを更新します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-211">Update the binaries as appropriate.</span></span>  
    
### <span data-ttu-id="08ab6-212">修正されたバージョンの既知の問題</span><span class="sxs-lookup"><span data-stu-id="08ab6-212">Known issues for Fixed Version</span></span>  

<span data-ttu-id="08ab6-213">Evergreen ランタイムと比べると、修正されたバージョンにはインストールプロセスがないため、 [Microsoft PlayReady][MicrosoftPlayReady] は変更されずに機能しません。</span><span class="sxs-lookup"><span data-stu-id="08ab6-213">Compared to the Evergreen Runtime, Fixed Version does not have an installation process, which causes [Microsoft PlayReady][MicrosoftPlayReady] to not work without modification.</span></span>  <span data-ttu-id="08ab6-214">次の操作を実行すると、問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-214">You may mitigate the problem by completing the following actions.</span></span>  

1.  <span data-ttu-id="08ab6-215">次の場所など、ユーザーのデバイスに固定バージョンパッケージを展開するパスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-215">Locate the path where you deploy the Fixed Version package on the user's device, such as the following location.</span></span>
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  <span data-ttu-id="08ab6-216">ユーザーのデバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ab6-216">Run the following commands on the user's device.</span></span>

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  <span data-ttu-id="08ab6-217">PlayReady は、ユーザーのデバイスで現在動作している必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ab6-217">PlayReady should be working now on the user's device.</span></span>  <span data-ttu-id="08ab6-218">[**修正済みバージョン**] フォルダーの [**セキュリティ**] タブに、との権限が含まれている必要があり `ALL APPLICATION PACKAGES` `ALL RESTRICTED APPLICATION PACKAGES` ます。</span><span class="sxs-lookup"><span data-stu-id="08ab6-218">In the **Security** tab of the **Fixed Version** folder, it should include permissions for `ALL APPLICATION PACKAGES` and `ALL RESTRICTED APPLICATION PACKAGES`.</span></span>  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady のアクセス許可" lightbox="../media/play-ready-permission.png":::
        <span data-ttu-id="08ab6-220">PlayReady のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="08ab6-220">Permission for PlayReady</span></span>  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[HowtoWebdriver]: ../howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft ドキュメント"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "WebView2 クラスの CreateAsync-CoreWebView2Environment クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-WebView2 クラス | WebView2 クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "WebView2 クラス | WinForms クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "WebView2 クラスのプロパティの自動 WebView2 のプロパティ |Microsoft ドキュメント"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス WebView2 | WinForms クラス |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラ |Microsoft 開発者"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView のフィードバック |GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 展開-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
