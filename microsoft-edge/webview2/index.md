---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、browser control、edge html、Windows フォーム、WinForms、WPF、.NET
ms.openlocfilehash: ea3d25d16aa9e8c182d564c68615b9643c9993b4
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888599"
---
# <span data-ttu-id="8fc69-104">Microsoft Edge WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8fc69-104">Introduction to Microsoft Edge WebView2 (Preview)</span></span>  

<span data-ttu-id="8fc69-105">Microsoft Edge WebView2 コントロールを使うと、ネイティブアプリケーションで web 技術 (HTML、CSS、JavaScript \) を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native applications.</span></span>  <span data-ttu-id="8fc69-106">WebView2 コントロールは、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain]をレンダリングエンジンとして使用して、ネイティブアプリケーションで web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native applications.</span></span>  <span data-ttu-id="8fc69-107">WebView2 を使用すると、ネイティブアプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブアプリケーション全体をビルドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-107">With WebView2, you may embed web code in different parts of your native application, or build the entire native application within a single WebView.</span></span>  <span data-ttu-id="8fc69-108">WebView2 アプリケーションの作成を開始する方法については、「使用[を開始する」を参照し](#getting-started)てください。</span><span class="sxs-lookup"><span data-stu-id="8fc69-108">For information on how to start building a WebView2 application, see [Get Started](#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは" lightbox="./media/WebView2/whatwebview.png":::
   <span data-ttu-id="8fc69-110">WebView とは</span><span class="sxs-lookup"><span data-stu-id="8fc69-110">What is WebView</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="8fc69-111">WebView2 Preview は、早期にプロトタイプを形成し、API の形成に役立つフィードバックを収集することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="8fc69-111">The WebView2 Preview is intended for early prototyping and to gather feedback to help shape the API.</span></span>  <span data-ttu-id="8fc69-112">変更内容が壊れる可能性があるため、実稼働アプリではプレビューを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8fc69-112">You should not use the preview in your production apps because there may be breaking changes.</span></span>  <span data-ttu-id="8fc69-113">詳細については、「 [Webview2Releasenotes]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc69-113">For more information, see [Webview2Releasenotes].</span></span>  

## <span data-ttu-id="8fc69-114">ハイブリッドアプリケーションのアプローチ</span><span class="sxs-lookup"><span data-stu-id="8fc69-114">Hybrid application approach</span></span>  

<span data-ttu-id="8fc69-115">開発者は、多くの場合、web アプリケーションまたはネイティブアプリケーションの構築を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc69-115">Developers often have to decide between building a web application or a native application.</span></span>  <span data-ttu-id="8fc69-116">意思決定は、リーチとパワーの間のトレードオフに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-116">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="8fc69-117">Web アプリケーションを使用すると広範なアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8fc69-117">Web applications allow for a broad reach.</span></span>  <span data-ttu-id="8fc69-118">Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-118">As a Web developer, you may reuse most, if not all of your code, across all different platforms.</span></span>  <span data-ttu-id="8fc69-119">ただし、ネイティブアプリケーションは、ネイティブプラットフォーム全体の機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-119">Native applications, however, utilize the capabilities of the entire native platform.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   <span data-ttu-id="8fc69-121">Web native</span><span class="sxs-lookup"><span data-stu-id="8fc69-121">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="8fc69-122">ハイブリッドアプリケーションを使用すると、開発者は両方のメリットを享受できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-122">Hybrid applications allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="8fc69-123">ハイブリッドアプリケーションの開発者は、web プラットフォームの ubiquity と強み、およびネイティブプラットフォームの機能と機能を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-123">Hybrid application developers benefit from the ubiquity and strength of the web platform, and the power and full capabilities of the native platform.</span></span>  

## <span data-ttu-id="8fc69-124">WebView2 の利点</span><span class="sxs-lookup"><span data-stu-id="8fc69-124">WebView2 benefits</span></span>   

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView の理由" lightbox="./media/WebView2/webviewreasons.png":::
   <span data-ttu-id="8fc69-126">WebView の理由</span><span class="sxs-lookup"><span data-stu-id="8fc69-126">WebView reasons</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-127">Web エコシステム \ & のスキルセット</span><span class="sxs-lookup"><span data-stu-id="8fc69-127">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="8fc69-128">Web エコシステム内に存在する web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-128">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-129">急速な革新</span><span class="sxs-lookup"><span data-stu-id="8fc69-129">Rapid innovation</span></span>**  
      <span data-ttu-id="8fc69-130">Web 開発により、迅速な展開とイテレーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8fc69-130">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-131">Windows 7、8、10のサポート</span><span class="sxs-lookup"><span data-stu-id="8fc69-131">Windows 7, 8, 10 support</span></span>**  
      <span data-ttu-id="8fc69-132">Windows 7、8、10での一貫したユーザーエクスペリエンスのサポート。</span><span class="sxs-lookup"><span data-stu-id="8fc69-132">Support for a consistent user experience across Windows 7, 8, and 10.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-133">ネイティブ機能</span><span class="sxs-lookup"><span data-stu-id="8fc69-133">Native capabilities</span></span>**  
      <span data-ttu-id="8fc69-134">ネイティブ Api の完全なセットにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8fc69-134">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-135">コード共有</span><span class="sxs-lookup"><span data-stu-id="8fc69-135">Code-sharing</span></span>**  
      <span data-ttu-id="8fc69-136">Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用を高速化できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-136">Add web code to your codebase allows for increased re-use across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-137">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="8fc69-137">Microsoft support</span></span>**  
      <span data-ttu-id="8fc69-138">Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能要求を追加します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-138">Microsoft provides support and adds new feature requests when WebView2 is release as GA.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-139">Evergreen 分布</span><span class="sxs-lookup"><span data-stu-id="8fc69-139">Evergreen distribution</span></span>**  
      <span data-ttu-id="8fc69-140">最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-140">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="8fc69-141">**固定**\ (近日公開)</span><span class="sxs-lookup"><span data-stu-id="8fc69-141">**Fixed** \(coming soon\)</span></span>  
      <span data-ttu-id="8fc69-142">アプリケーションに Chromium ビットをパッケージ化することを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-142">Choose to package the Chromium bits in your application.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="8fc69-143">段階的導入</span><span class="sxs-lookup"><span data-stu-id="8fc69-143">Incremental adoption</span></span>**  
      <span data-ttu-id="8fc69-144">アプリケーションに web コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-144">Add web components piece by piece to your application.</span></span>  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="8fc69-145">開始するには</span><span class="sxs-lookup"><span data-stu-id="8fc69-145">Getting started</span></span>  

<span data-ttu-id="8fc69-146">WebView2 コントロールを使用してアプリケーションをビルドしてテストするには、 [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]と[WebView2 SDK][NugetPackagesMicrosoftWebWebView2]の両方をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc69-146">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="8fc69-147">開始するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fc69-147">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="8fc69-148">Win32 C/C + + の概要</span><span class="sxs-lookup"><span data-stu-id="8fc69-148">Getting Started with Win32 C/C++</span></span>][Webview2GettingstartedWin32]  
*   [<span data-ttu-id="8fc69-149">WPF の概要</span><span class="sxs-lookup"><span data-stu-id="8fc69-149">Getting Started with WPF</span></span>][Webview2GettingstartedWpf]  
*   [<span data-ttu-id="8fc69-150">WinForms の概要</span><span class="sxs-lookup"><span data-stu-id="8fc69-150">Getting Started with WinForms</span></span>][Webview2GettingstartedWinforms]  
*   [<span data-ttu-id="8fc69-151">WinUI3 の概要</span><span class="sxs-lookup"><span data-stu-id="8fc69-151">Getting Started with WinUI3</span></span>][Webview2GettingstartedWinui]  

<span data-ttu-id="8fc69-152">[WebView2 サンプル][GithubMicrosoftedgeWebview2samples]リポジトリには、すべての WebView2 SDK 機能と API の使用パターンを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fc69-152">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="8fc69-153">WebView2 SDK に追加された機能により、サンプルアプリケーションが更新されます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-153">As more features are added to the WebView2 SDK, the sample applications will be updated.</span></span>  

## <span data-ttu-id="8fc69-154">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="8fc69-154">Supported platforms</span></span>  

<span data-ttu-id="8fc69-155">開発者プレビューは、次のプログラミング環境で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-155">A developer preview is available on the following programming environments.</span></span>  

*   <span data-ttu-id="8fc69-156">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="8fc69-156">Win32 C/C++</span></span>  
*   <span data-ttu-id="8fc69-157">.NET Framework 4.6.2 以降</span><span class="sxs-lookup"><span data-stu-id="8fc69-157">.NET Framework 4.6.2 or later</span></span>  
*   <span data-ttu-id="8fc69-158">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="8fc69-158">.NET Core 3.0 or later</span></span>  
*   [<span data-ttu-id="8fc69-159">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="8fc69-159">WinUI 3.0</span></span>][UwpToolkitsWinui3]  

<span data-ttu-id="8fc69-160">WebView2 アプリケーションは、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-160">You are able to run WebView2 applications on the following versions of Windows.</span></span>  

*   <span data-ttu-id="8fc69-161">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8fc69-161">Windows 10</span></span>  
*   <span data-ttu-id="8fc69-162">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8fc69-162">Windows 8.1</span></span>  
*   <span data-ttu-id="8fc69-163">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8fc69-163">Windows 8</span></span>  
*   <span data-ttu-id="8fc69-164">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8fc69-164">Windows 7</span></span>  
*   <span data-ttu-id="8fc69-165">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8fc69-165">Windows Server 2016</span></span>  
*   <span data-ttu-id="8fc69-166">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8fc69-166">Windows Server 2012</span></span>  
*   <span data-ttu-id="8fc69-167">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="8fc69-167">Windows Server 2012R2</span></span>  
*   <span data-ttu-id="8fc69-168">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8fc69-168">Windows Server 2008 R2</span></span>  

## <span data-ttu-id="8fc69-169">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8fc69-169">Next steps</span></span>  

<span data-ttu-id="8fc69-170">WebView2 アプリケーションを作成して展開する方法の詳細については、概念的なドキュメントと使い方ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc69-170">For more information on how to build and deploy WebView2 applications, review the conceptual documentation and how-to guides.</span></span>  

#### <span data-ttu-id="8fc69-171">概念</span><span class="sxs-lookup"><span data-stu-id="8fc69-171">Concepts</span></span>  

*   [<span data-ttu-id="8fc69-172">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="8fc69-172">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]
*   [<span data-ttu-id="8fc69-173">WebView2 を使用したアプリケーションの配布</span><span class="sxs-lookup"><span data-stu-id="8fc69-173">Distribution of applications using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="8fc69-174">セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="8fc69-174">Best practices for developing secure WebView2 applications</span></span>][Webview2ConceptsSecurity]
*   [<span data-ttu-id="8fc69-175">WebView2 アプリケーションでユーザーデータフォルダーを管理する</span><span class="sxs-lookup"><span data-stu-id="8fc69-175">Manage User Data Folder in WebView2 Applications</span></span>][Webview2ConceptsUserdatafolder]
 
#### <span data-ttu-id="8fc69-176">使い方ガイド</span><span class="sxs-lookup"><span data-stu-id="8fc69-176">How-To guides</span></span>  

*   [<span data-ttu-id="8fc69-177">WebView2 を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="8fc69-177">How to Debug with WebView2</span></span>][Webview2HowtoDebug]  
*   [<span data-ttu-id="8fc69-178">Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト</span><span class="sxs-lookup"><span data-stu-id="8fc69-178">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowtoWebdriver]  

## <span data-ttu-id="8fc69-179">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="8fc69-179">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="8fc69-180">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-180">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="8fc69-181">機能のリクエストまたはバグレポートを送信するには、「 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeddback]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc69-181">To submit feature requests or bug reports, see [WebView feedback repo][GithubMicrosoftedgeWebviewfeddback] .</span></span>  <span data-ttu-id="8fc69-182">また、既知の問題を検索するのに適した場所です。</span><span class="sxs-lookup"><span data-stu-id="8fc69-182">It's also a good place to search for known issues.</span></span>  

> [!NOTE]
> <span data-ttu-id="8fc69-183">プレビューでは、より優れた製品の構築に役立つデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-183">During the preview, we collect data to help build a better product.</span></span>  <span data-ttu-id="8fc69-184">WebView2 データの収集をオフにするには、ブラウザーデータの収集に移動してオフにし `edge://settings/privacy` ます。</span><span class="sxs-lookup"><span data-stu-id="8fc69-184">To turn off WebView2 data collection, go to `edge://settings/privacy` and turn off browser data collection.</span></span>  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ConceptsSecurity]: ./concepts/security.md "セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス |Microsoft ドキュメント"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "ユーザーデータフォルダーの管理 |Microsoft ドキュメント"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "WebView2 SDK のバージョンについて理解する |Microsoft ドキュメント"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 の概要 (開発者用プレビュー) |Microsoft ドキュメント"   
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows フォームアプリでの WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 での WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2HowtoDebug]: ./howto/debug.md "WebView2 を使用してデバッグする方法 |Microsoft ドキュメント"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft ドキュメント"  
[Webview2Releasenotes]: ./releasenotes.md "Release NOTES for WebView2 SDK |Microsoft ドキュメント"  

[UwpToolkitsWinui3]: ./gettingstarted/winui.md "Windows UI ライブラリ3プレビュー 2 (2020 年7月) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider をダウンロードする"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "WebView2 |NuGet ギャラリー"  
