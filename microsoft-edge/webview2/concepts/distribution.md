---
description: Microsoft Edge WebView2 を使用してアプリをリリースする場合の配布オプション
title: Microsoft Edge WebView2 アプリの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 14f252b0155beb6bfce0b01dc080900f2d3e57ee
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195167"
---
# <span data-ttu-id="8ed58-104">WebView2 を使用したアプリの配布</span><span class="sxs-lookup"><span data-stu-id="8ed58-104">Distribution of apps using WebView2</span></span>  

<span data-ttu-id="8ed58-105">WebView2 アプリを配布する場合は、アプリを起動する前に、バッキング Web プラットフォームである [WebView2 ランタイム][Webview2Installer]が存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-105">When distributing your WebView2 app, ensure the backing web platform, the [WebView2 Runtime][Webview2Installer], is present before the app starts.</span></span>  <span data-ttu-id="8ed58-106">この記事では、ユーザー \(開発者\) が WebView2 ランタイムをインストールし、WebView2 アプリの 2 つの配布モードである[エバーグリーン](#evergreen-distribution-mode)と[固定バージョン](#fixed-version-distribution-mode)を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-106">This article describes how you \(the developer\) install the WebView2 Runtime, and use the two distribution modes for your WebView2 app:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="8ed58-107">エバーグリーンの配布モード</span><span class="sxs-lookup"><span data-stu-id="8ed58-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="8ed58-108">ほとんどの開発者には、エバーグリーンの配布モードをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="8ed58-109">エバーグリーンの配布モードでは、アプリで最新の機能とセキュリティ更新プログラムを利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="8ed58-110">次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="8ed58-111">基礎となる Web プラットフォーム \(WebView2 Runtime\) は、追加の作業を行わずに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="8ed58-112">エバーグリーン配布モードを使用するすべてのアプリは、ディスク領域を節約するエバーグリーン WebView2 ランタイムの共有コピーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-112">All apps that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  
    
### <span data-ttu-id="8ed58-113">WebView2 ランタイムについて</span><span class="sxs-lookup"><span data-stu-id="8ed58-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="8ed58-114">WebView2 ランタイムは再頒布可能なランタイムであり、WebView2 アプリのバッキング Web プラットフォームとして機能します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-114">The WebView2 Runtime is a redistributable runtime and serves as the backing web platform for WebView2 apps.</span></span>  <span data-ttu-id="8ed58-115">概念は、Visual C++ または C++/.NET アプリ用の .NET ランタイムに似ています。</span><span class="sxs-lookup"><span data-stu-id="8ed58-115">The concept is similar to Visual C++ or the .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="8ed58-116">ランタイムには、アプリ用に微調整されテストされた、変更された Microsoft Edge \(Chromium\) バイナリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ed58-116">The Runtime contains modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for apps.</span></span>  <span data-ttu-id="8ed58-117">ランタイムは、インストール時にユーザーに表示されるブラウザーとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-117">The Runtime does not appear as a user-visible browser upon installation.</span></span>  <span data-ttu-id="8ed58-118">たとえば、ユーザーにはブラウザーのデスクトップ ショートカットやスタート メニューのエントリがありません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-118">For example, a user does not have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="8ed58-119">開発およびテスト中は、どちらかをバッキング Web プラットフォームとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-119">During development and testing, you may use either as the backing web platform.</span></span>  

*   <span data-ttu-id="8ed58-120">WebView2 ランタイム</span><span class="sxs-lookup"><span data-stu-id="8ed58-120">The WebView2 Runtime</span></span>  
*   <span data-ttu-id="8ed58-121">任意の Insider \(非安定版\) Microsoft Edge \(Chromium\) ブラウザー チャネル</span><span class="sxs-lookup"><span data-stu-id="8ed58-121">Any Insider \(non-stable\) Microsoft Edge \(Chromium\) browser channel</span></span>  
    
<span data-ttu-id="8ed58-122">運用環境では、アプリを起動する前に、ユーザー のデバイスにランタイムが存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-122">In production environments, you must ensure the Runtime is present on user devices before the app starts.</span></span>  <span data-ttu-id="8ed58-123">Microsoft Edge Stable チャネルは、WebView2 の使用には利用できません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-123">The Microsoft Edge Stable channel is unavailable for WebView2 usage.</span></span>  <span data-ttu-id="8ed58-124">この決定により、アプリが運用環境でブラウザーに依存することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-124">The decision prevents apps from taking a dependency on the browser in production.</span></span>

<span data-ttu-id="8ed58-125">次の理由により、ブラウザーに依存しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-125">Do not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="8ed58-126">Microsoft Edge \(Chromium\) は、すべてのユーザー デバイスに存在することが保証されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-126">Microsoft Edge \(Chromium\) is not guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="8ed58-127">たとえば、Windows Update から切断されたデバイスや、Microsoft によって直接管理されていないデバイス \(Enterprise および EDU 市場の大部分\) にはブラウザーが存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-127">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise and EDU market\) may not have the browser.</span></span>  <span data-ttu-id="8ed58-128">WebView2 ランタイムを配布できるようにすることで、アプリの前提条件としてブラウザーに依存することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-128">Allowing you to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>  
*   <span data-ttu-id="8ed58-129">ブラウザーとアプリの使用例は異なっています。そのため、ブラウザーに依存すると、アプリに意図しない副作用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-129">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="8ed58-130">たとえば、IT 管理者は、内部 Web サイトの互換性を確保するためにブラウザーのバージョン管理を行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-130">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="8ed58-131">WebView2 ランタイムを使うと、ブラウザーの更新プログラムがアクティブに管理されている間、アプリを常にエバーグリーンに保つことができます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-131">The WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="8ed58-132">ブラウザーとは対照的に、ランタイムはアプリのシナリオ用に開発およびテストされ、場合によっては、ブラウザーでまだ利用できないバグ修正が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-132">As opposed to the browser, the Runtime is developed and tested for app scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  
    
<span data-ttu-id="8ed58-133">今後、エバーグリーン WebView2 ランタイムは Windows の将来のリリースとともに配付される予定です。</span><span class="sxs-lookup"><span data-stu-id="8ed58-133">In the future, the Evergreen WebView2 Runtime plans to ship with future releases of Windows.</span></span>  <span data-ttu-id="8ed58-134">ランタイムがより一般に利用可能になるまで、運用アプリでランタイムを展開します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-134">Deploy the Runtime with your production app until the Runtime becomes more universally available.</span></span>  

### <span data-ttu-id="8ed58-135">エバーグリーン WebView2 ランタイムの展開</span><span class="sxs-lookup"><span data-stu-id="8ed58-135">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="8ed58-136">デバイス上のすべてのエバーグリーン アプリに必要なエバーグリーン WebView2 ランタイムのインストールは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="8ed58-136">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="8ed58-137">[ WebView2 ランタイムのダウンロード ページ][Webview2Installer]には、多数のツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8ed58-137">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer].</span></span>  <span data-ttu-id="8ed58-138">次のツールは、エバーグリーン ランタイムの展開に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-138">The following tools help you deploy the Evergreen Runtime.</span></span>  

*   <span data-ttu-id="8ed58-139">WebView2 ランタイム ブートストラップは、小さな \(約 2 MB\) インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="8ed58-139">WebView2 Runtime Bootstrapper is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="8ed58-140">WebView2 ランタイム ブートストラップは、ユーザーのデバイス アーキテクチャに一致する Microsoft サーバーからエバーグリーン ランタイムをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-140">WebView2 Runtime Bootstrapper downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="8ed58-141">リンクを使用して、プログラムでブートストラップをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-141">Use a link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="8ed58-142">WebView2 ランタイム スタンドアロン インストーラーは、オフライン環境にエバーグリーン WebView2 ランタイムをインストールする完全なインストーラーです。</span><span class="sxs-lookup"><span data-stu-id="8ed58-142">WebView2 Runtime Standalone Installer is a full installer that installs the Evergreen WebView2 Runtime in offline environments.</span></span>  
    
<span data-ttu-id="8ed58-143">現在、ブートストラップとスタンドアロンの両方のインストーラーは、昇格が必要なコンピューターごとのインストールのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8ed58-143">Currently, both the bootstrapper and standalone installer only support per-machine installs, which requires elevation.</span></span>  <span data-ttu-id="8ed58-144">昇格せずにインストーラーを実行すると、アクセス許可を昇格するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-144">If an installer is run without elevation, the user is prompted to elevate permissions.</span></span>  

<span data-ttu-id="8ed58-145">アプリを起動する前にランタイムが既にインストールされていることを確認するには、次のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-145">Use following workflows to ensure the Runtime is already installed before your app launches.</span></span>  <span data-ttu-id="8ed58-146">自分のシナリオに応じてワークフローを調整できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-146">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="8ed58-147">サンプル コードは、[サンプルのリポジトリ][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]で利用可能です。</span><span class="sxs-lookup"><span data-stu-id="8ed58-147">Sample code is available in the [Samples repo][GitHubMicrosoftedgeWebView2samplesWebview2Deployment].</span></span>  

#### <span data-ttu-id="8ed58-148">オンラインのみの展開</span><span class="sxs-lookup"><span data-stu-id="8ed58-148">Online-only deployment</span></span>  

<span data-ttu-id="8ed58-149">ユーザーがインターネットにアクセスできると想定されるオンラインのみの展開シナリオがある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-149">If you have an online-only deployment scenario where users are assumed to have internet access, complete the following steps.</span></span>  

1.  <span data-ttu-id="8ed58-150">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-150">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="8ed58-151">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-151">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="8ed58-152">`pv (REG_SZ)` レジストリ キーが存在し、`null` または空でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-152">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="8ed58-153">次の場所で、`pv (REG_SZ)` を探します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-153">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="8ed58-154">64 ビット Windows の場合</span><span class="sxs-lookup"><span data-stu-id="8ed58-154">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="8ed58-155">32 ビット Windows の場合</span><span class="sxs-lookup"><span data-stu-id="8ed58-155">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="8ed58-156">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、`versionInfo` が `NULL` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-156">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="8ed58-157">ランタイムがインストールされていない場合は、リンクを使用してプログラムでブートストラップをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-157">If the Runtime is not installed, use the link to programmatically download the bootstrapper.</span></span>  
1.  <span data-ttu-id="8ed58-158">サイレント インストールの場合は、昇格したプロセスまたはコマンドプロンプトから `MicrosoftEdgeWebview2Setup.exe /silent /install` を使用してブートストラップを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-158">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  
    
<span data-ttu-id="8ed58-159">前のワークフローには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-159">The previous workflow has the following benefits.</span></span>  

*   <span data-ttu-id="8ed58-160">必要な場合、またはインストーラーをパッケージ化する必要がない場合にのみ、ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-160">Install the Runtime only when needed or when you are not required to package installers.</span></span>  
*   <span data-ttu-id="8ed58-161">ブートストラップは自動的にデバイス アーキテクチャを検出し、一致するランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-161">The bootstrapper automatically detects device architecture and installs the matching Runtime.</span></span>  
*   <span data-ttu-id="8ed58-162">ランタイムをサイレント インストールします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-162">Install the Runtime silently.</span></span>  
    
<span data-ttu-id="8ed58-163">プログラムでオンデマンドでダウンロードする代わりに、ブートストラップをアプリにパッケージ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-163">You may also choose to package the bootstrapper with your app instead of programmatically downloading it on demand.</span></span>  

#### <span data-ttu-id="8ed58-164">オフラインの展開</span><span class="sxs-lookup"><span data-stu-id="8ed58-164">Offline deployment</span></span>  

<span data-ttu-id="8ed58-165">アプリの展開を完全にオフラインで行う必要があるオフライン展開シナリオがある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-165">If you have an offline deployment scenario where app deployment has to work entirely offline, complete the following steps.</span></span>  

1.  <span data-ttu-id="8ed58-166">[スタンドアロン インストーラー][Webview2Installer]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8ed58-166">Download the [standalone installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="8ed58-167">インストーラーをアプリ インストーラーまたはアップデーターに含めます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-167">Include the installer in your app installer or updater.</span></span>  
1.  <span data-ttu-id="8ed58-168">アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-168">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="8ed58-169">確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-169">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="8ed58-170">`pv (REG_SZ)` レジストリ キーが存在し、`null` または空でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-170">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="8ed58-171">次の場所で、`pv (REG_SZ)` を探します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-171">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="8ed58-172">64 ビット Windows の場合</span><span class="sxs-lookup"><span data-stu-id="8ed58-172">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="8ed58-173">32 ビット Windows の場合</span><span class="sxs-lookup"><span data-stu-id="8ed58-173">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="8ed58-174">[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、`versionInfo` が `NULL` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-174">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="8ed58-175">ランタイムがインストールされていない場合は、スタンドアロン インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-175">If the Runtime is not installed, run the standalone installer.</span></span>  <span data-ttu-id="8ed58-176">サイレント インストールを実行する場合は、昇格されたプロセスからインストーラーを実行するか、次のコマンドをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-176">If you want to run a silent installation, either run the installer from an elevated process or copy and run the following command.</span></span>  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <span data-ttu-id="8ed58-177">エバーグリーン モードで互換性を保つ</span><span class="sxs-lookup"><span data-stu-id="8ed58-177">Stay compatible in Evergreen mode</span></span>  

<span data-ttu-id="8ed58-178">Web は常に進化しています。</span><span class="sxs-lookup"><span data-stu-id="8ed58-178">The Web is constantly evolving.</span></span>  <span data-ttu-id="8ed58-179">エバーグリーン WebView2 ランタイムは最新の状態に保たれ、最新の機能とセキュリティ修正プログラムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-179">The Evergreen WebView2 Runtime is kept up to date to provide you with the latest features and security fixes.</span></span>  <span data-ttu-id="8ed58-180">アプリが Web との互換性を維持できるようにするには、テスト インフラストラクチャを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-180">To ensure your app stays compatible with the web, you should set up testing infrastructure.</span></span>  

<span data-ttu-id="8ed58-181">不安定な Microsoft Edge チャネル \(Beta/Dev/Canary\) では、WebView2 ランタイムで次に予定されている機能のヒントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-181">Non-stable Microsoft Edge channels \(Beta/Dev/Canary\) provide a sneak peek into what is coming next into WebView2 Runtime.</span></span>  <span data-ttu-id="8ed58-182">Microsoft Edge 用の Web サイトを開発する場合と同様に、WebView2 アプリを定期的にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-182">Just like developing websites for Microsoft Edge, you should test your WebView2 app regularly.</span></span>  <span data-ttu-id="8ed58-183">不安定なチャネルの 1 つに対して WebView2 アプリをテストし、問題が発生した場合はアプリを更新するか、[問題を報告します][GithubMicrosoftedgeWebviewfeedback]。</span><span class="sxs-lookup"><span data-stu-id="8ed58-183">Test your WebView2 app against one of the non-stable channels, and update your app or [report issues][GithubMicrosoftedgeWebviewfeedback] if issues arise.</span></span> <span data-ttu-id="8ed58-184">通常、推奨されるチャネルは Dev と Beta です。</span><span class="sxs-lookup"><span data-stu-id="8ed58-184">Typically Dev and Beta are the recommended channels.</span></span>  <span data-ttu-id="8ed58-185">適切なチャネルを判断するには、「[Microsoft Edge チャネルの概要][DeployEdgeMicrosoftEdgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-185">To help you decide which channel is right, navigate to [Overview of the Microsoft Edge channels][DeployEdgeMicrosoftEdgeChannels].</span></span>  <span data-ttu-id="8ed58-186">安定していない [Microsoft Edge チャネル][DownloadNonstableEdge]をテスト環境にダウンロードし、`regkey` または環境変数を使用してテスト アプリのチャネルの設定を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-186">You may download the [non-stable Microsoft Edge channel][DownloadNonstableEdge] on your test environment, and use `regkey` or environment variables to indicate the channel preference for your testing app.</span></span>  <span data-ttu-id="8ed58-187">詳細については、「[CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-187">For more information, navigate to [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].</span></span>  <span data-ttu-id="8ed58-188">[WebDriver ][HowtoWebdriver] を使用して WebView2 のテストを自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-188">You may also use [WebDriver][HowtoWebdriver] to automate WebView2 testing.</span></span>

## <span data-ttu-id="8ed58-189">固定バージョンの配布モード</span><span class="sxs-lookup"><span data-stu-id="8ed58-189">Fixed Version distribution mode</span></span>   

<span data-ttu-id="8ed58-190">厳密な互換性要件がある制約のある環境では、固定バージョンの配布モードの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-190">For constrained environments with strict compatibility requirements, consider using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="8ed58-191">固定バージョンの配布モードを使用して、特定のバージョンの WebView2 ランタイムを選択してパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-191">Choose and package a specific version of the WebView2 Runtime using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="8ed58-192">アプリのランタイム更新のタイミングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-192">You may specify the timing of Runtime updates for your app.</span></span>  <span data-ttu-id="8ed58-193">固定バージョンの配布モードは自動更新を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-193">The Fixed Version distribution mode does not receive any automatic updates.</span></span> <span data-ttu-id="8ed58-194">アプリとランタイムの更新を計画します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-194">Plan to update your app and the Runtime.</span></span>  

> [!NOTE] 
> <span data-ttu-id="8ed58-195">固定バージョンの配布モードは、以前は bring-your-own (持ち込み) と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="8ed58-195">The Fixed Version distribution mode was previously called bring-your-own.</span></span>  

<span data-ttu-id="8ed58-196">固定バージョン モードを使用するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-196">To use the Fixed Version mode, complete the following actions</span></span>

1.  <span data-ttu-id="8ed58-197">固定バージョン パッケージを[ダウンロードします][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="8ed58-197">[Download][Webview2Installer] the Fixed Version package.</span></span> 
1.  <span data-ttu-id="8ed58-198">コマンド ライン `expand {path to the package} -F:* {path to the destination folder}` または WinRAR などのツールを使用してパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-198">Decompress the package using command line `expand {path to the package} -F:* {path to the destination folder}` or with tools such as WinRAR.</span></span> <span data-ttu-id="8ed58-199">フォルダー構造が正しく生成されない可能性があるため、エクスプローラーで展開するのは避けてください。</span><span class="sxs-lookup"><span data-stu-id="8ed58-199">Avoid decompressing through the File Explorer as it may not generate the correct folder structure.</span></span>  
1.  <span data-ttu-id="8ed58-200">展開された固定バージョンのバイナリをプロジェクトに含めます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-200">Include the decompressed Fixed Version binaries in your project.</span></span>  
1.  <span data-ttu-id="8ed58-201">WebView2 環境を作成するときに、固定バージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-201">Indicate the path to the Fixed Version binaries when creating the WebView2 environment.</span></span>  
    *   <span data-ttu-id="8ed58-202">Win32 C/C++ の場合は、[、CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 関数を使用して環境を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-202">For Win32 C/C++, you may create the environment using the [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] function.</span></span>  <span data-ttu-id="8ed58-203">`browserExecutableFolder` パラメーターを使用して、`msedgewebview2.exe` が含まれているフォルダーへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-203">Use the `browserExecutableFolder` parameter to indicate the path to the folder containing `msedgewebview2.exe`.</span></span>  
    *   <span data-ttu-id="8ed58-204">.NET の場合は、次のいずれかのオプションを使用して環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-204">For .NET, you may do either of the following options to specify the environment.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="8ed58-205">WebView2 の `Source` プロパティを有効にするには、環境を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-205">You must specify the environment before the WebView2 `Source` property takes effect.</span></span>  
        
        *   <span data-ttu-id="8ed58-206">`CreationProperties`WebView2 要素の \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-206">Set the `CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) property on the WebView2 element.</span></span>  <span data-ttu-id="8ed58-207">`CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) クラスの `BrowserExecutableFolder` メンバーを使用して、固定バージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-207">Use the `BrowserExecutableFolder` member in the `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) class to indicate the path to the Fixed Version binaries.</span></span>  
        *   <span data-ttu-id="8ed58-208">`EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) を使用して環境を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-208">Use `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) to specify the environment.</span></span>  <span data-ttu-id="8ed58-209">[CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] の `browserExecutableFolder` パラメーターを使用して、固定バージョンのバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-209">Use the `browserExecutableFolder` parameter in [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] to indicate the path to the Fixed Version binaries.</span></span>  
1.  <span data-ttu-id="8ed58-210">固定バージョンのバイナリをアプリにパッケージ化して配付します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-210">Package and ship the Fixed Version binaries with your app.</span></span>  <span data-ttu-id="8ed58-211">必要に応じてバイナリを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-211">Update the binaries as appropriate.</span></span>  
    
### <span data-ttu-id="8ed58-212">固定バージョンの既知の問題</span><span class="sxs-lookup"><span data-stu-id="8ed58-212">Known issues for Fixed Version</span></span>  

<span data-ttu-id="8ed58-213">エバーグリーン ランタイムと比較すると、固定バージョンにはインストール プロセスが含まれていないため、[Microsoft PlayReady][MicrosoftPlayReady] は変更をしないと動作しません。</span><span class="sxs-lookup"><span data-stu-id="8ed58-213">Compared to the Evergreen Runtime, Fixed Version does not have an installation process, which causes [Microsoft PlayReady][MicrosoftPlayReady] to not work without modification.</span></span>  <span data-ttu-id="8ed58-214">以下の操作を実行すると、問題を軽減できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-214">You may mitigate the problem by completing the following actions.</span></span>  

1.  <span data-ttu-id="8ed58-215">次の場所など、ユーザーのデバイスに固定バージョン パッケージを展開するパスを指定ます。</span><span class="sxs-lookup"><span data-stu-id="8ed58-215">Locate the path where you deploy the Fixed Version package on the user's device, such as the following location.</span></span>
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  <span data-ttu-id="8ed58-216">ユーザーのデバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed58-216">Run the following commands on the user's device.</span></span>

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  <span data-ttu-id="8ed58-217">これで PlayReady はユーザーのデバイスで動作しているはずです。</span><span class="sxs-lookup"><span data-stu-id="8ed58-217">PlayReady should be working now on the user's device.</span></span>  <span data-ttu-id="8ed58-218">**[固定バージョン]** フォルダーの **[セキュリティ]** タブには、`ALL APPLICATION PACKAGES` と `ALL RESTRICTED APPLICATION PACKAGES` のアクセス許可が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ed58-218">In the **Security** tab of the **Fixed Version** folder, it should include permissions for `ALL APPLICATION PACKAGES` and `ALL RESTRICTED APPLICATION PACKAGES`.</span></span>  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady のアクセス許可" lightbox="../media/play-ready-permission.png":::
        <span data-ttu-id="8ed58-220">PlayReady のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ed58-220">Permission for PlayReady</span></span>  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 について | Microsoft Docs"  
[HowtoWebdriver]: ../howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト | Microsoft Docs"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - グローバル | Microsoft Docs"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 | Microsoft Docs"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "CreateAsync - Microsoft.Web.WebView2.Core.CoreWebView2Environment クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async -Microsoft.Web.WebView2.Wpf.WebView2 クラス | Microsoft Docs"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async - Microsoft.Web.WebView2.WinForms.WebView2 クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties - Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties クラス | Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "CreationProperties - Microsoft.Web.WebView2.Wpf.WebView2 クラス | Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "Microsoft.Web.WebView2.WinForms.WebView2 クラス | Microsoft Docs"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー | Microsoft デベロッパー"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック |GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 の展開 - MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
