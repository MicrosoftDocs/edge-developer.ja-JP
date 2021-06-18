---
description: Microsoft Edge WebView2 コントロールを使用して Win32、.NET、UWP アプリで Web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html、Windows フォーム、WinForms、WPF、.NET、WinUI、Project Reunion
ms.openlocfilehash: 9c1aa073294fc649223da19c44850dc4335f6c00
ms.sourcegitcommit: 7f7922dbb6af87ecac1378d18359125770c5b8e5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536853"
---
# <a name="introduction-to-microsoft-edge-webview2"></a><span data-ttu-id="db778-104">Microsoft Edge WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="db778-104">Introduction to Microsoft Edge WebView2</span></span>  

<span data-ttu-id="db778-105">Microsoft Edge WebView2 を使用すると、Web テクノロジ \(HTML、CSS、JavaScript\) をユーザーのネイティブ アプリに埋め込みできます。</span><span class="sxs-lookup"><span data-stu-id="db778-105">The Microsoft Edge WebView2 control allows you to embed web technologies \(HTML, CSS, and JavaScript\) in your native apps.</span></span>  <span data-ttu-id="db778-106">WebView2 コントロールは、[Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain]をレンダリング エンジンとして使用して、ネイティブ アプリに Web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="db778-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native apps.</span></span>  <span data-ttu-id="db778-107">WebView2 を使用すると、ネイティブ アプリの異なる部分に Web コードを埋め込むことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="db778-107">With WebView2, you may embed web code in different parts of your native app.</span></span>  <span data-ttu-id="db778-108">1 つの WebView インスタンスを使用して、すべてのネイティブ アプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="db778-108">Build all of the native app within a single WebView instance.</span></span>  <span data-ttu-id="db778-109">WebView2 アプリの構築を開始する方法の詳細については、「[開始する方法](#get-started)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db778-109">For information on how to start building a WebView2 app, navigate to [Get Started](#get-started).</span></span>  

:::image type="complex" source="./media/WebView2/what-webview.png" alt-text="WebView とは?" lightbox="./media/WebView2/what-webview.png":::
   <span data-ttu-id="db778-111">WebView とは?</span><span class="sxs-lookup"><span data-stu-id="db778-111">What is WebView?</span></span>  
:::image-end:::    

## <a name="hybrid-app-approach"></a><span data-ttu-id="db778-112">ハイブリッド アプリのアプローチ</span><span class="sxs-lookup"><span data-stu-id="db778-112">Hybrid app approach</span></span>  

<span data-ttu-id="db778-113">開発者はひんぱんに、Web アプリを使用するか、またはネイティブ アプリを作成するかの選択をすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="db778-113">Developers must often decide between building a web app or a native app.</span></span>  <span data-ttu-id="db778-114">意思決定は、リーチとパワーの間のトレードオフにかかっています。</span><span class="sxs-lookup"><span data-stu-id="db778-114">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="db778-115">Web アプリを使用すると、広範囲にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="db778-115">Web apps allow for a broad reach.</span></span>  <span data-ttu-id="db778-116">Web 開発者は、さまざまなプラットフォームでほとんどのコードを再利用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db778-116">As a Web developer, you may reuse most of your code across different platforms.</span></span>  <span data-ttu-id="db778-117">ネイティブ プラットフォームのすべての機能にアクセスするには、ネイティブ アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="db778-117">To access the all capabilities of a native platform, use a native app.</span></span>  

:::image type="complex" source="./media/WebView2/web-native.png" alt-text="Web ネイティブ" lightbox="./media/WebView2/web-native.png":::
   <span data-ttu-id="db778-119">Web ネイティブ</span><span class="sxs-lookup"><span data-stu-id="db778-119">Web native</span></span>  
:::image-end:::    

<span data-ttu-id="db778-120">ハイブリッド アプリを使用すると、開発者は Webアプリとネイティブ アプリの両方の最高の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="db778-120">Hybrid apps allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="db778-121">ハイブリッド アプリ開発者は、次の利点からの恩恵を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="db778-121">Hybrid app developers benefit from the following advantages.</span></span>  

*   <span data-ttu-id="db778-122">Web プラットフォームのユビキタスと強さ。</span><span class="sxs-lookup"><span data-stu-id="db778-122">The ubiquity and strength of the web platform.</span></span>  
*   <span data-ttu-id="db778-123">ネイティブ プラットフォームのパワーとフル機能。</span><span class="sxs-lookup"><span data-stu-id="db778-123">The power and full capabilities of the native platform.</span></span>  
    
## <a name="webview2-benefits"></a><span data-ttu-id="db778-124">WebView2 の利点</span><span class="sxs-lookup"><span data-stu-id="db778-124">WebView2 benefits</span></span>   

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="web-ecosystem--skillset"></a><span data-ttu-id="db778-125">Web エコシステム & スキルセット</span><span class="sxs-lookup"><span data-stu-id="db778-125">Web ecosystem & skillset</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="rapid-innovation"></a><span data-ttu-id="db778-126">急速な革新</span><span class="sxs-lookup"><span data-stu-id="db778-126">Rapid innovation</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="windows-7-8-and-10-support"></a><span data-ttu-id="db778-127">Windows 7、8、および 10 のサポート</span><span class="sxs-lookup"><span data-stu-id="db778-127">Windows 7, 8, and 10 support</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db778-128">Web エコシステム内に存在する Web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。</span><span class="sxs-lookup"><span data-stu-id="db778-128">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-129">Web 開発により、迅速な展開とイテレーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="db778-129">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-130">Windows 7、Windows 8、および Windows 10 全体での一貫したユーザー エクスペリエンへのサポート。</span><span class="sxs-lookup"><span data-stu-id="db778-130">Support for a consistent user experience across Windows 7, Windows 8, and Windows 10.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="native-capabilities"></a><span data-ttu-id="db778-131">ネイティブ機能</span><span class="sxs-lookup"><span data-stu-id="db778-131">Native capabilities</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="code-sharing"></a><span data-ttu-id="db778-132">コード共有</span><span class="sxs-lookup"><span data-stu-id="db778-132">Code-sharing</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="microsoft-support"></a><span data-ttu-id="db778-133">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="db778-133">Microsoft support</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db778-134">ネイティブ API のフル セットにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="db778-134">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-135">コードベースに Web コードを追加すると、複数のプラットフォームで再利用が増えます。</span><span class="sxs-lookup"><span data-stu-id="db778-135">Add web code to your codebase allows for increased reuse across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-136">WebView2 が全般可用性 \(GA\) でリリースされる場合、Microsoft はサポートを提供し、新しい機能要求を追加します。</span><span class="sxs-lookup"><span data-stu-id="db778-136">Microsoft provides support and adds new feature requests when WebView2 releases at Generally Availability \(GA\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed-small.msft.png":::  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption-small.msft.png":::  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ### <a name="evergreen-distribution"></a><span data-ttu-id="db778-137">Evergreen 分布</span><span class="sxs-lookup"><span data-stu-id="db778-137">Evergreen distribution</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="fixed"></a><span data-ttu-id="db778-138">固定</span><span class="sxs-lookup"><span data-stu-id="db778-138">Fixed</span></span>  
   :::column-end:::
   :::column span="1":::
      ### <a name="incremental-adoption"></a><span data-ttu-id="db778-139">段階的導入</span><span class="sxs-lookup"><span data-stu-id="db778-139">Incremental adoption</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="db778-140">最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。</span><span class="sxs-lookup"><span data-stu-id="db778-140">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-141">\( 近日公開 \) アプリ内の Chromium ビットをパッケージ化することを選択します。</span><span class="sxs-lookup"><span data-stu-id="db778-141">\(coming soon\)  Choose to package the Chromium bits in your app.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="db778-142">Web コンポーネントをアプリに 1 つずつ追加します。</span><span class="sxs-lookup"><span data-stu-id="db778-142">Add web components piece by piece to your app.</span></span>  
   :::column-end:::
:::row-end:::  

## <a name="get-started"></a><span data-ttu-id="db778-143">作業の開始</span><span class="sxs-lookup"><span data-stu-id="db778-143">Get started</span></span>  

<span data-ttu-id="db778-144">WebView2 コントロールを使用してアプリをビルドしてテストするには、以下が必要です</span><span class="sxs-lookup"><span data-stu-id="db778-144">To build and test your app using the WebView2 control, you need to have</span></span> <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  --><span data-ttu-id="db778-145">[WebView2 SDK][NugetPackagesMicrosoftWebWebView2] がインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="db778-145">the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="db778-146">開始するには、次のいずれかのオプションから １つ選択します。</span><span class="sxs-lookup"><span data-stu-id="db778-146">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="db778-147">はじめに Win32 C/C++ を使用する</span><span class="sxs-lookup"><span data-stu-id="db778-147">Get Started with Win32 C/C++</span></span>][Webview2GetStartedWin32]  
*   [<span data-ttu-id="db778-148">WPF の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="db778-148">Get Started with WPF</span></span>][Webview2GetStartedWpf]  
*   [<span data-ttu-id="db778-149">WinForms の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="db778-149">Get Started with WinForms</span></span>][Webview2GetStartedWinforms]  
*   [<span data-ttu-id="db778-150">WinUI3 の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="db778-150">Get Started with WinUI3</span></span>][Webview2GetStartedWinui]  
    
<span data-ttu-id="db778-151">[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="db778-151">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="db778-152">WebView2 SDK に追加される機能が多い場合、サンプル アプリは更新されます。</span><span class="sxs-lookup"><span data-stu-id="db778-152">As more features are added to the WebView2 SDK, the sample apps will be updated.</span></span>  

## <a name="supported-platforms"></a><span data-ttu-id="db778-153">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="db778-153">Supported platforms</span></span>  

<span data-ttu-id="db778-154">一般提供 \ (GA\) またはプレビュー版は、次のプログラミング環境で利用できます。</span><span class="sxs-lookup"><span data-stu-id="db778-154">A General Availability \(GA\) or Preview version is available on the following programming environments.</span></span>  

*   <span data-ttu-id="db778-155">Win32 C/c + + \ (GA \)</span><span class="sxs-lookup"><span data-stu-id="db778-155">Win32 C/C++ \(GA\)</span></span>  
*   <span data-ttu-id="db778-156">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="db778-156">.NET Framework 4.5 or later</span></span>  
*   <span data-ttu-id="db778-157">.NET Core 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="db778-157">.NET Core 3.1 or later</span></span>  
*   <span data-ttu-id="db778-158">.NET 5</span><span class="sxs-lookup"><span data-stu-id="db778-158">.NET 5</span></span>  
*   <span data-ttu-id="db778-159">[WinUI 3.0][UwpToolkitsWinui3] \ (プレビュー \)</span><span class="sxs-lookup"><span data-stu-id="db778-159">[WinUI 3.0][UwpToolkitsWinui3] \(Preview\)</span></span>  
    
<span data-ttu-id="db778-160">WebView2 アプリは、次のバージョンの Windowsで実行可能です。。</span><span class="sxs-lookup"><span data-stu-id="db778-160">You may run WebView2 apps on the following versions of Windows.</span></span>  

*   <span data-ttu-id="db778-161">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db778-161">Windows 10</span></span>  
*   <span data-ttu-id="db778-162">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="db778-162">Windows 8.1</span></span>  
*   <span data-ttu-id="db778-163">Windows 7 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="db778-163">Windows 7 \*\*</span></span>  
*   <span data-ttu-id="db778-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="db778-164">Windows Server 2019</span></span>  
*   <span data-ttu-id="db778-165">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="db778-165">Windows Server 2016</span></span>  
*   <span data-ttu-id="db778-166">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db778-166">Windows Server 2012</span></span>  
*   <span data-ttu-id="db778-167">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="db778-167">Windows Server 2012 R2</span></span>  
*   <span data-ttu-id="db778-168">Windows Server 2008 R2 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="db778-168">Windows Server 2008 R2 \*\*</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="db778-169">\ \* \ \* WebView2 support for Windows 7 および Windows Server 2008 R2 のサポートサイクルは、Microsoft Edge と同じです。</span><span class="sxs-lookup"><span data-stu-id="db778-169">\*\* WebView2 support for Windows 7 and Windows Server 2008 R2 has the same support cycle as Microsoft Edge.</span></span>  <span data-ttu-id="db778-170">詳細については、[Microsoft Edge でサポートされているオペレーティングシステム][DeployedgeMicrosoftEdgeSupportedOS]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db778-170">For more information, navigate to [Microsoft Edge supported Operating Systems][DeployedgeMicrosoftEdgeSupportedOS].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="db778-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="db778-171">Next steps</span></span>  

<span data-ttu-id="db778-172">WebView2 アプリをビルドおよび展開する方法の詳細については、概念ドキュメントと方法ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db778-172">For more information on how to build and deploy WebView2 apps, review the conceptual documentation and how-to guides.</span></span>  

### <a name="concepts"></a><span data-ttu-id="db778-173">概念</span><span class="sxs-lookup"><span data-stu-id="db778-173">Concepts</span></span>  

*   [<span data-ttu-id="db778-174">WebView2 SDK バージョンの概要</span><span class="sxs-lookup"><span data-stu-id="db778-174">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]  
*   [<span data-ttu-id="db778-175">WebView2 を使用したアプリの配布</span><span class="sxs-lookup"><span data-stu-id="db778-175">Distribution of apps using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="db778-176">セキュリティで保護された WebView2 アプリを開発するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="db778-176">Best practices for developing secure WebView2 apps</span></span>][Webview2ConceptsSecurity]  
*   [<span data-ttu-id="db778-177">WebView2 アプリでユーザー データ フォルダーを管理する</span><span class="sxs-lookup"><span data-stu-id="db778-177">Manage User Data Folder in WebView2 apps</span></span>][Webview2ConceptsUserDataFolder]  
 
### <a name="how-to-guides"></a><span data-ttu-id="db778-178">使い方ガイド</span><span class="sxs-lookup"><span data-stu-id="db778-178">How-To guides</span></span>  

*   [<span data-ttu-id="db778-179">WebView2 を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="db778-179">How to Debug with WebView2</span></span>][Webview2HowToDebug]  
*   [<span data-ttu-id="db778-180">Microsoft Edge Driverを使用した WebView2 の自動化とテスト</span><span class="sxs-lookup"><span data-stu-id="db778-180">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowToWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="db778-181">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="db778-181">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリの配布|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリを開発するためのベスト プラクティス |Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ./concepts/user-data-folder.md "ユーザー データ フォルダーの管理 |Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft Docs"  
[Webview2GetStartedWin32]: ./get-started/win32.md "WebView2 の使用を開始する|Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "Windows フォーム アプリ (プレビュー) でのWebView2 の使用を開始する|Microsoft Docs"  
[Webview2GetStartedWinui]: ./get-started/winui.md "WinUI3 の WebView2 の使用を開始する (プレビュー) |Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF (プレビュー) の WebView2 の概要|Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "WebView2 を使用してデバッグする方法 |Microsoft Docs"  
[Webview2HowToWebdriver]: ./how-to/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft Docs"  
[Webview2ReleaseNotes]: ./release-notes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3 プレビュー 2 (2020 年7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge でサポートされているオペレーティングシステム |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 | NuGet Gallery"  
