---
description: Microsoft Edge WebView2 control を使用して Win32、.NET、UWP アプリケーションの web コンテンツをホストする
title: Microsoft Edge WebView2 control
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html、Windows フォーム、WinForms、WPF、.NET、WinUI、Project Reunion
ms.openlocfilehash: 02d17b05364f02f26a4917b65ac497156be02b2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182368"
---
# <span data-ttu-id="a5035-104">Microsoft Edge WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="a5035-104">Introduction to Microsoft Edge WebView2</span></span>  

<span data-ttu-id="a5035-105">Microsoft Edge WebView2 controlを使うと、ネイティブ アプリケーションで web テクノロジ (HTML、CSS、そしてJavaScript \) を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a5035-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native applications.</span></span>  <span data-ttu-id="a5035-106">WebView2 controlは、[Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] をレンダリングエンジンとして使用し、ネイティブ アプリケーションで web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="a5035-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native applications.</span></span>  <span data-ttu-id="a5035-107">WebView2 を使用すると、ネイティブ アプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブ アプリケーション全体を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5035-107">With WebView2, you may embed web code in different parts of your native application, or build the entire native application within a single WebView.</span></span>  <span data-ttu-id="a5035-108">WebView2 アプリケーションの作成を始める方法については、[はじめに](#getting-started)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5035-108">For information on how to start building a WebView2 application, navigate to [Get Started](#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは" lightbox="./media/WebView2/whatwebview.png":::
   <span data-ttu-id="a5035-110">WebView とは</span><span class="sxs-lookup"><span data-stu-id="a5035-110">What is WebView</span></span>  
:::image-end:::  

## <span data-ttu-id="a5035-111">ハイブリッド アプリケーションのアプローチ</span><span class="sxs-lookup"><span data-stu-id="a5035-111">Hybrid application approach</span></span>  

<span data-ttu-id="a5035-112">開発者は多くの場合、web アプリケーションまたはネイティブ アプリケーションの構築にするかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5035-112">Developers often have to decide between building a web application or a native application.</span></span>  <span data-ttu-id="a5035-113">意思決定は、リーチとパワーの間のトレードオフにかかっています。</span><span class="sxs-lookup"><span data-stu-id="a5035-113">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="a5035-114">Web アプリケーションは広範囲に対応しています。</span><span class="sxs-lookup"><span data-stu-id="a5035-114">Web applications allow for a broad reach.</span></span>  <span data-ttu-id="a5035-115">Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="a5035-115">As a Web developer, you may reuse most, if not all of your code, across all different platforms.</span></span>  <span data-ttu-id="a5035-116">ただし、ネイティブ アプリケーションは、ネイティブプラットフォーム全体の機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="a5035-116">Native applications, however, utilize the capabilities of the entire native platform.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   <span data-ttu-id="a5035-118">Web native</span><span class="sxs-lookup"><span data-stu-id="a5035-118">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="a5035-119">ハイブリッド アプリケーションを使用すると、開発者は両方の長所を享受できます。</span><span class="sxs-lookup"><span data-stu-id="a5035-119">Hybrid applications allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="a5035-120">ハイブリッド アプリケーションの開発者は、web プラットフォームの偏在と強み、およびネイティブ プラットフォームの機能とパワーを最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="a5035-120">Hybrid application developers benefit from the ubiquity and strength of the web platform, and the power and full capabilities of the native platform.</span></span>  

## <span data-ttu-id="a5035-121">WebView2 の利点</span><span class="sxs-lookup"><span data-stu-id="a5035-121">WebView2 benefits</span></span>  

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView の理由" lightbox="./media/WebView2/webviewreasons.png":::
   <span data-ttu-id="a5035-123">WebView の理由</span><span class="sxs-lookup"><span data-stu-id="a5035-123">WebView reasons</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="a5035-124">Web エコシステム \ & のスキルセット</span><span class="sxs-lookup"><span data-stu-id="a5035-124">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="a5035-125">Web エコシステム内に存在する web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。</span><span class="sxs-lookup"><span data-stu-id="a5035-125">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="a5035-126">急速な革新</span><span class="sxs-lookup"><span data-stu-id="a5035-126">Rapid innovation</span></span>**  
      <span data-ttu-id="a5035-127">Web 開発により、迅速な展開とイテレーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a5035-127">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="a5035-128">Windows 7、8、10のサポート</span><span class="sxs-lookup"><span data-stu-id="a5035-128">Windows 7, 8, 10 support</span></span>**  
      <span data-ttu-id="a5035-129">Windows 7、8、10での一貫したユーザー エクスペリエンスのサポート。</span><span class="sxs-lookup"><span data-stu-id="a5035-129">Support for a consistent user experience across Windows 7, 8, and 10.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a5035-130">ネイティブ機能</span><span class="sxs-lookup"><span data-stu-id="a5035-130">Native capabilities</span></span>**  
      <span data-ttu-id="a5035-131">ネイティブ APIs のフル セットにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a5035-131">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="a5035-132">コード共有</span><span class="sxs-lookup"><span data-stu-id="a5035-132">Code-sharing</span></span>**  
      <span data-ttu-id="a5035-133">Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用の向上が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a5035-133">Add web code to your codebase allows for increased re-use across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="a5035-134">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="a5035-134">Microsoft support</span></span>**  
      <span data-ttu-id="a5035-135">Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能の要望を追加します。</span><span class="sxs-lookup"><span data-stu-id="a5035-135">Microsoft provides support and adds new feature requests when WebView2 is release as GA.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="a5035-136">Evergreen 分布</span><span class="sxs-lookup"><span data-stu-id="a5035-136">Evergreen distribution</span></span>**  
      <span data-ttu-id="a5035-137">最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。</span><span class="sxs-lookup"><span data-stu-id="a5035-137">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="a5035-138">**修正済み** \(近日公開\)</span><span class="sxs-lookup"><span data-stu-id="a5035-138">**Fixed** \(coming soon\)</span></span>  
      <span data-ttu-id="a5035-139">アプリケーションに Chromium ビットをパッケージ化することを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5035-139">Choose to package the Chromium bits in your application.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="a5035-140">段階的導入</span><span class="sxs-lookup"><span data-stu-id="a5035-140">Incremental adoption</span></span>**  
      <span data-ttu-id="a5035-141">アプリケーションに web コンポーネントをひとつづつ追加します。</span><span class="sxs-lookup"><span data-stu-id="a5035-141">Add web components piece by piece to your application.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="a5035-142">開始するには</span><span class="sxs-lookup"><span data-stu-id="a5035-142">Getting started</span></span>  

<span data-ttu-id="a5035-143">WebView2 コントロールを使用してアプリケーションを作成しテストするには、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] と [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] の両方をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5035-143">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="a5035-144">開始するには、次のいずれかのオプションから一つ選択します。</span><span class="sxs-lookup"><span data-stu-id="a5035-144">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="a5035-145">Win32 C/C + + の概要</span><span class="sxs-lookup"><span data-stu-id="a5035-145">Getting Started with Win32 C/C++</span></span>][Webview2GettingstartedWin32]  
*   [<span data-ttu-id="a5035-146">WPF の概要</span><span class="sxs-lookup"><span data-stu-id="a5035-146">Getting Started with WPF</span></span>][Webview2GettingstartedWpf]  
*   [<span data-ttu-id="a5035-147">WinForms の概要</span><span class="sxs-lookup"><span data-stu-id="a5035-147">Getting Started with WinForms</span></span>][Webview2GettingstartedWinforms]  
*   [<span data-ttu-id="a5035-148">WinUI3 の概要</span><span class="sxs-lookup"><span data-stu-id="a5035-148">Getting Started with WinUI3</span></span>][Webview2GettingstartedWinui]  

<span data-ttu-id="a5035-149">[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5035-149">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="a5035-150">WebView2 SDK に追加された機能により、サンプル アプリケーションが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a5035-150">As more features are added to the WebView2 SDK, the sample applications will be updated.</span></span>  

## <span data-ttu-id="a5035-151">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a5035-151">Supported platforms</span></span>  

<span data-ttu-id="a5035-152">一般提供 \(GA\) またはプレビュー版は、次のプログラミング環境で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a5035-152">A General Availability \(GA\) or Preview version is available on the following programming environments.</span></span>  

*   <span data-ttu-id="a5035-153">Win32 C/c + + \(GA \)</span><span class="sxs-lookup"><span data-stu-id="a5035-153">Win32 C/C++ \(GA\)</span></span>
*   <span data-ttu-id="a5035-154">.NET Framework 4.6.2 以降</span><span class="sxs-lookup"><span data-stu-id="a5035-154">.NET Framework 4.6.2 or later</span></span>
*   <span data-ttu-id="a5035-155">.NET Core 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="a5035-155">.NET Core 3.1 or later</span></span>
*   <span data-ttu-id="a5035-156">.NET 5</span><span class="sxs-lookup"><span data-stu-id="a5035-156">.NET 5</span></span>
*   <span data-ttu-id="a5035-157">[WinUI 3.0][UwpToolkitsWinui3] \(プレビュー \)</span><span class="sxs-lookup"><span data-stu-id="a5035-157">[WinUI 3.0][UwpToolkitsWinui3] \(Preview\)</span></span>

<span data-ttu-id="a5035-158">WebView2 アプリケーションは、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5035-158">You are able to run WebView2 applications on the following versions of Windows.</span></span>  

*   <span data-ttu-id="a5035-159">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a5035-159">Windows 10</span></span>  
*   <span data-ttu-id="a5035-160">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a5035-160">Windows 8.1</span></span>  
*   <span data-ttu-id="a5035-161">Windows 7 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="a5035-161">Windows 7 </span></span>  
*   <span data-ttu-id="a5035-162">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5035-162">Windows Server 2019</span></span>  
*   <span data-ttu-id="a5035-163">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a5035-163">Windows Server 2016</span></span>  
*   <span data-ttu-id="a5035-164">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a5035-164">Windows Server 2012</span></span>  
*   <span data-ttu-id="a5035-165">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a5035-165">Windows Server 2012 R2</span></span>  
*   <span data-ttu-id="a5035-166">Windows Server 2008 R2 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="a5035-166">Windows Server 2008 R2 </span></span>  

> [!IMPORTANT]
> <span data-ttu-id="a5035-167">\ \* \ \* WebView2 support for Windows 7 および Windows Server 2008 R2 のサポートサイクルは、Microsoft Edge と同じです。</span><span class="sxs-lookup"><span data-stu-id="a5035-167"> WebView2 support for Windows 7 and Windows Server 2008 R2 has the same support cycle as Microsoft Edge.</span></span>  <span data-ttu-id="a5035-168">詳細については、[Microsoft Edge でサポートされているオペレーティングシステム][DeployedgeMicrosoftEdgeSupportedOS]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5035-168">For more information, navigate to [Microsoft Edge supported Operating Systems][DeployedgeMicrosoftEdgeSupportedOS].</span></span>  

## <span data-ttu-id="a5035-169">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a5035-169">Next steps</span></span>  

<span data-ttu-id="a5035-170">WebView2 アプリケーションを作成して展開する方法の詳細については、概念のドキュメントと使い方ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5035-170">For more information on how to build and deploy WebView2 applications, review the conceptual documentation and how-to guides.</span></span>  

#### <span data-ttu-id="a5035-171">概念</span><span class="sxs-lookup"><span data-stu-id="a5035-171">Concepts</span></span>  

*   [<span data-ttu-id="a5035-172">WebView2 SDK バージョンの概要</span><span class="sxs-lookup"><span data-stu-id="a5035-172">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]
*   [<span data-ttu-id="a5035-173">WebView2 を使用したアプリケーションの配布</span><span class="sxs-lookup"><span data-stu-id="a5035-173">Distribution of applications using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="a5035-174">安全な WebView2 アプリケーションを開発するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a5035-174">Best practices for developing secure WebView2 applications</span></span>][Webview2ConceptsSecurity]
*   [<span data-ttu-id="a5035-175">WebView2 アプリケーションでユーザー データ フォルダーを管理する</span><span class="sxs-lookup"><span data-stu-id="a5035-175">Manage User Data Folder in WebView2 Applications</span></span>][Webview2ConceptsUserdatafolder]
 
#### <span data-ttu-id="a5035-176">使い方ガイド</span><span class="sxs-lookup"><span data-stu-id="a5035-176">How-To guides</span></span>  

*   [<span data-ttu-id="a5035-177">WebView2 を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="a5035-177">How to Debug with WebView2</span></span>][Webview2HowtoDebug]  
*   [<span data-ttu-id="a5035-178">Microsoft Edge Driverを使用した WebView2 の自動化とテスト</span><span class="sxs-lookup"><span data-stu-id="a5035-178">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowtoWebdriver]


## <span data-ttu-id="a5035-179">Microsoft Edge WebView チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a5035-179">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス |Microsoft Docs"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "ユーザーデータフォルダーの管理 |Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft Docs"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 の概要 |Microsoft Docs"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows フォームアプリでの WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 での WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2HowtoDebug]: ./howto/debug.md "WebView2 を使用してデバッグする方法 |Microsoft Docs"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft Docs"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3 プレビュー 2 (2020 年7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge でサポートされているオペレーティングシステム |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 | NuGet Gallery"  
