---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Microsoft Edge WebView2 コントロール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、browser control、edge html、Windows フォーム、WinForms、WPF、.NET
ms.openlocfilehash: 9356da17f2db9456a9a309bc9ef06c74fbb50779
ms.sourcegitcommit: e49b86082da884299fdd485d3311d63a7688c0d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2020
ms.locfileid: "10754546"
---
# <span data-ttu-id="30399-104">Microsoft Edge WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="30399-104">Introduction to Microsoft Edge WebView2 (Preview)</span></span>  

<span data-ttu-id="30399-105">Microsoft Edge WebView2 コントロールを使うと、ネイティブアプリケーションで web 技術 (HTML、CSS、JavaScript \) を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="30399-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native applications.</span></span>  <span data-ttu-id="30399-106">WebView2 コントロールは、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com)をレンダリングエンジンとして使用して、ネイティブアプリケーションで web コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="30399-106">The WebView2 control uses [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com) as the rendering engine to display the web content in native applications.</span></span>  <span data-ttu-id="30399-107">WebView2 を使用すると、ネイティブアプリケーションのさまざまな場所に web コードを埋め込むことができます。または、1つの WebView 内でネイティブアプリケーション全体をビルドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="30399-107">With WebView2, you may embed web code in different parts of your native application, or build the entire native application within a single WebView.</span></span>  <span data-ttu-id="30399-108">WebView2 アプリケーションの作成を開始する方法については、「使用[を開始する」を参照し](./index.md#getting-started)てください。</span><span class="sxs-lookup"><span data-stu-id="30399-108">For information on how to start building a WebView2 application, see [Get Started](./index.md#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="WebView とは":::
   <span data-ttu-id="30399-110">WebView とは</span><span class="sxs-lookup"><span data-stu-id="30399-110">What is WebView</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="30399-111">WebView2 Preview は、早期にプロトタイプを形成し、API の形成に役立つフィードバックを収集することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="30399-111">The WebView2 Preview is intended for early prototyping and to gather feedback to help to shape the API.</span></span>  <span data-ttu-id="30399-112">Microsoft Edge WebView チームでは、運用アプリでプレビューを使用することはお勧めしません。[変更が中断](./releasenotes.md)される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30399-112">The Microsoft Edge WebView team does not recommend that you use the preview in your production apps because there may be [breaking changes](./releasenotes.md).</span></span>  

## <span data-ttu-id="30399-113">ハイブリッドアプリケーションのアプローチ</span><span class="sxs-lookup"><span data-stu-id="30399-113">Hybrid application approach</span></span>  

<span data-ttu-id="30399-114">通常、開発者は、web アプリケーションまたはネイティブアプリケーションのビルドのどちらかを選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="30399-114">Developers often have to choose between building a web application or a native application.</span></span>  <span data-ttu-id="30399-115">意思決定は、リーチとパワーの間のトレードオフに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="30399-115">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="30399-116">Web アプリケーションを使用すると広範なアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="30399-116">Web applications allow for a broad reach.</span></span>  <span data-ttu-id="30399-117">Web 開発者は、すべての異なるプラットフォームで、ほとんどのコードを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="30399-117">As a Web developer, you may reuse most, if not all of your code, across all different platforms.</span></span>  <span data-ttu-id="30399-118">ただし、ネイティブアプリケーションは、ネイティブプラットフォーム全体の機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="30399-118">Native applications, however, utilize the capabilities of the entire native platform.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native":::
   <span data-ttu-id="30399-120">Web native</span><span class="sxs-lookup"><span data-stu-id="30399-120">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="30399-121">ハイブリッドアプリケーションを使用すると、開発者は両方のメリットを享受できます。</span><span class="sxs-lookup"><span data-stu-id="30399-121">Hybrid applications allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="30399-122">ハイブリッドアプリケーションの開発者は、web プラットフォームの ubiquity と強み、およびネイティブプラットフォームの機能と機能を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="30399-122">Hybrid application developers benefit from the ubiquity and strength of the web platform, and the power and full capabilities of the native platform.</span></span>  

## <span data-ttu-id="30399-123">WebView2 の利点</span><span class="sxs-lookup"><span data-stu-id="30399-123">WebView2 benefits</span></span>   

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView の理由":::
   <span data-ttu-id="30399-125">WebView の理由</span><span class="sxs-lookup"><span data-stu-id="30399-125">WebView reasons</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="30399-126">Web エコシステム \ & のスキルセット</span><span class="sxs-lookup"><span data-stu-id="30399-126">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="30399-127">Web エコシステム内に存在する web プラットフォーム、ライブラリ、ツール、人材をすべて活用できます。</span><span class="sxs-lookup"><span data-stu-id="30399-127">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30399-128">急速な革新</span><span class="sxs-lookup"><span data-stu-id="30399-128">Rapid innovation</span></span>**  
      <span data-ttu-id="30399-129">Web 開発により、迅速な展開とイテレーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="30399-129">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30399-130">Windows 7、8、10のサポート</span><span class="sxs-lookup"><span data-stu-id="30399-130">Windows 7, 8, 10 support</span></span>**  
      <span data-ttu-id="30399-131">Windows 7、8、10での一貫したユーザーエクスペリエンスのサポート。</span><span class="sxs-lookup"><span data-stu-id="30399-131">Support for a consistent user experience across Windows 7, 8, and 10.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="30399-132">ネイティブ機能</span><span class="sxs-lookup"><span data-stu-id="30399-132">Native capabilities</span></span>**  
      <span data-ttu-id="30399-133">ネイティブ Api の完全なセットにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="30399-133">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30399-134">コード共有</span><span class="sxs-lookup"><span data-stu-id="30399-134">Code-sharing</span></span>**  
      <span data-ttu-id="30399-135">Web コードをコードベースに追加することで、複数のプラットフォーム間での再利用を高速化できます。</span><span class="sxs-lookup"><span data-stu-id="30399-135">Add web code to your codebase allows for increased re-use across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30399-136">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="30399-136">Microsoft support</span></span>**  
      <span data-ttu-id="30399-137">Microsoft は、WebView2 が GA としてリリースされたときにサポートを提供し、新しい機能要求を追加します。</span><span class="sxs-lookup"><span data-stu-id="30399-137">Microsoft provides support and adds new feature requests when WebView2 is release as GA.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="30399-138">Evergreen 分布</span><span class="sxs-lookup"><span data-stu-id="30399-138">Evergreen distribution</span></span>**  
      <span data-ttu-id="30399-139">最新バージョンの Chromium を使用して、定期的なプラットフォームの更新とセキュリティ更新プログラムを利用します。</span><span class="sxs-lookup"><span data-stu-id="30399-139">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="30399-140">**固定**\ (近日公開)</span><span class="sxs-lookup"><span data-stu-id="30399-140">**Fixed** \(coming soon\)</span></span>  
      <span data-ttu-id="30399-141">アプリケーションに Chromium ビットをパッケージ化することを選択します。</span><span class="sxs-lookup"><span data-stu-id="30399-141">Choose to package the Chromium bits in your application.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30399-142">段階的導入</span><span class="sxs-lookup"><span data-stu-id="30399-142">Incremental adoption</span></span>**  
      <span data-ttu-id="30399-143">アプリケーションに web コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="30399-143">Add web components piece by piece to your application.</span></span>  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="30399-144">開始するには</span><span class="sxs-lookup"><span data-stu-id="30399-144">Getting started</span></span>  

<span data-ttu-id="30399-145">WebView2 コントロールを使用してアプリケーションをビルドしてテストするには、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download)と[WebView2 SDK](https://aka.ms/webviewnuget)の両方をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30399-145">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download) and the [WebView2 SDK](https://aka.ms/webviewnuget) installed.</span></span>  <span data-ttu-id="30399-146">開始するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="30399-146">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="30399-147">Win32 C/C + + の概要</span><span class="sxs-lookup"><span data-stu-id="30399-147">Getting Started with Win32 C/C++</span></span>](./gettingstarted/win32.md)  
*   [<span data-ttu-id="30399-148">WPF の概要</span><span class="sxs-lookup"><span data-stu-id="30399-148">Getting Started with WPF</span></span>](./gettingstarted/wpf.md)  
*   [<span data-ttu-id="30399-149">WinForms の概要</span><span class="sxs-lookup"><span data-stu-id="30399-149">Getting Started with WinForms</span></span>](./gettingstarted/winforms.md)  

<span data-ttu-id="30399-150">[WebView2 サンプル](https://github.com/MicrosoftEdge/WebView2Samples)リポジトリには、WebView2 sdk のすべての機能と API の使用パターンを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30399-150">The [WebView2 Samples](https://github.com/MicrosoftEdge/WebView2Samples) repository contains samples that demonstrate all of the WebView2 SDKs features and API usage patterns.</span></span> <span data-ttu-id="30399-151">WebView2 SDK に追加された機能により、サンプルアプリケーションが更新されます。</span><span class="sxs-lookup"><span data-stu-id="30399-151">As more features are added to the WebView2 SDK, the sample applications will be updated.</span></span>   

## <span data-ttu-id="30399-152">サポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="30399-152">Supported platforms</span></span>  

<span data-ttu-id="30399-153">開発者プレビューは、次のプログラミング環境で利用できます。</span><span class="sxs-lookup"><span data-stu-id="30399-153">A developer preview is available on the following programming environments.</span></span>  

*   <span data-ttu-id="30399-154">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="30399-154">Win32 C/C++</span></span>  
*   <span data-ttu-id="30399-155">.NET Framework 4.6.2 以降</span><span class="sxs-lookup"><span data-stu-id="30399-155">.NET Framework 4.6.2 or later</span></span>  
*   <span data-ttu-id="30399-156">.NET Core 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="30399-156">.NET Core 3.0 or later</span></span>  
*   [<span data-ttu-id="30399-157">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="30399-157">WinUI 3.0</span></span>](/uwp/toolkits/winui3/)  

<span data-ttu-id="30399-158">WebView2 アプリケーションは、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="30399-158">You are able to run WebView2 applications on the following versions of Windows.</span></span>  

*   <span data-ttu-id="30399-159">Windows 10</span><span class="sxs-lookup"><span data-stu-id="30399-159">Windows 10</span></span>  
*   <span data-ttu-id="30399-160">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="30399-160">Windows 8.1</span></span>  
*   <span data-ttu-id="30399-161">Windows 8</span><span class="sxs-lookup"><span data-stu-id="30399-161">Windows 8</span></span>  
*   <span data-ttu-id="30399-162">Windows 7</span><span class="sxs-lookup"><span data-stu-id="30399-162">Windows 7</span></span>  
*   <span data-ttu-id="30399-163">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="30399-163">Windows Server 2016</span></span>  
*   <span data-ttu-id="30399-164">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="30399-164">Windows Server 2012</span></span>  
*   <span data-ttu-id="30399-165">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="30399-165">Windows Server 2012R2</span></span>  
*   <span data-ttu-id="30399-166">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="30399-166">Windows Server 2008 R2</span></span>  

## <span data-ttu-id="30399-167">次のステップ</span><span class="sxs-lookup"><span data-stu-id="30399-167">Next steps</span></span>  

<span data-ttu-id="30399-168">WebView2 アプリケーションを作成して展開する方法の詳細については、概念的なドキュメントと使い方ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30399-168">For more detailed information on how to build and deploy WebView2 applications, checkout the conceptual documentation and how-to guides.</span></span>  

#### <span data-ttu-id="30399-169">概念</span><span class="sxs-lookup"><span data-stu-id="30399-169">Concepts</span></span>  

*   [<span data-ttu-id="30399-170">WebView2 SDK と Microsoft Edge のバージョン管理</span><span class="sxs-lookup"><span data-stu-id="30399-170">WebView2 SDK and Microsoft Edge Versioning</span></span>](./concepts/versioning.md)
*   [<span data-ttu-id="30399-171">WebView2 アプリケーションを配布する</span><span class="sxs-lookup"><span data-stu-id="30399-171">Distribute WebView2 Applications</span></span>](./concepts/distribution.md)  
*   [<span data-ttu-id="30399-172">WebView2 アプリケーションのセキュリティのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="30399-172">Security Best Practices for WebView2 Applications</span></span>](./concepts/security.md)
*   [<span data-ttu-id="30399-173">WebView2 アプリケーションでユーザーデータフォルダーを管理する</span><span class="sxs-lookup"><span data-stu-id="30399-173">Manage User Data Folder in WebView2 Applications</span></span>](./concepts/userdatafolder.md)
 
#### <span data-ttu-id="30399-174">使い方ガイド</span><span class="sxs-lookup"><span data-stu-id="30399-174">How-To guides</span></span>  

*   [<span data-ttu-id="30399-175">DevTools と Visual Studio スクリプトのデバッグによる WebView2 のデバッグ</span><span class="sxs-lookup"><span data-stu-id="30399-175">Debugging WebView2 with DevTools and Visual Studio script debugging</span></span>](./howto/debug.md)  
*   [<span data-ttu-id="30399-176">Microsoft EdgeDriver での WebView2 の自動化とデバッグ</span><span class="sxs-lookup"><span data-stu-id="30399-176">Automating and debugging WebView2 with Microsoft EdgeDriver</span></span>](./howto/webdriver.md)  

## <span data-ttu-id="30399-177">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="30399-177">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="30399-178">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="30399-178">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="30399-179">WebView[フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能のリクエストまたはバグレポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="30399-179">Visit the WebView [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports.</span></span>  <span data-ttu-id="30399-180">また、既知の問題を検索するのに適した場所です。</span><span class="sxs-lookup"><span data-stu-id="30399-180">It is also a good place to search for known issues.</span></span>  

> [!NOTE]
> <span data-ttu-id="30399-181">Microsoft Edge WebView チームは、開発者向けプレビューでもデータを収集して、より良い WebView を構築できるようにします。</span><span class="sxs-lookup"><span data-stu-id="30399-181">During developer preview, the Microsoft Edge WebView team also collects data to help build a better WebView.</span></span>  <span data-ttu-id="30399-182">WebView データの収集をオフにするには `edge://settings/privacy` 、Microsoft Edge ブラウザーを表示し、ブラウザーデータの収集をオフにします。</span><span class="sxs-lookup"><span data-stu-id="30399-182">Users may turn off WebView data collection by navigating to `edge://settings/privacy` in the Microsoft Edge browser and turning off browser data collection.</span></span>  
