---
description: ユーザー補助機能の改善、その他の言語の DevTools の使用などがあります。
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8f82f46cd683433a37614bcf15745e1de9f31ffb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015469"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="7904f-104">DevTools の新機能 (Microsoft Edge 80)</span><span class="sxs-lookup"><span data-stu-id="7904f-104">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <span data-ttu-id="7904f-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="7904f-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="7904f-106">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7904f-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="7904f-107">それらを確認して、DevTools、Visual Studio コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7904f-107">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="7904f-108">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="7904f-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="7904f-109">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="7904f-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="7904f-110">DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="7904f-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="7904f-111">Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7904f-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="7904f-113">キーボードナビゲーションとスクリーンリーダーの改良による DevTools の **パフォーマンス** ツール</span><span class="sxs-lookup"><span data-stu-id="7904f-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-114">すべてのユーザーが web ページにアクセスできるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7904f-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="7904f-115">使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="7904f-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="7904f-116">スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7904f-116">If you use screen readers or the keyboard to navigate around the DevTools, send your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="7904f-117">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="7904f-117">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="7904f-118">他の言語での DevTools の使用</span><span class="sxs-lookup"><span data-stu-id="7904f-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="7904f-119">多くの開発者は、英語だけでなく、StackOverflow や Visual Studio コードなどの開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="7904f-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="7904f-120">ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="7904f-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="7904f-121">中国語 \ (簡体字)- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="7904f-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7904f-122">中国語 (繁体字)- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="7904f-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="7904f-123">フランス語– fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="7904f-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7904f-124">ドイツ語-deutsch</span><span class="sxs-lookup"><span data-stu-id="7904f-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="7904f-125">イタリア語-italiano</span><span class="sxs-lookup"><span data-stu-id="7904f-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7904f-126">日本語- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="7904f-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="7904f-127">韓国語- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="7904f-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7904f-128">ポルトガル語-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="7904f-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="7904f-129">ロシア語–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="7904f-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="7904f-130">スペイン語-&#241;ol</span><span class="sxs-lookup"><span data-stu-id="7904f-130">Spanish - espa&#241;ol</span></span>
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

<span data-ttu-id="7904f-131">に移動 `edge://flags` して、[ローカライズされた **開発者ツールを有効** にする] フラグを [ **有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="7904f-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="7904f-132">また、 **開発者ツールの実験** フラグを [ **有効**にする」に設定します。</span><span class="sxs-lookup"><span data-stu-id="7904f-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="7904f-133">Microsoft Edge を再起動して、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="7904f-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="7904f-134">DevTools は、Microsoft Edge で使用する言語と一致し `edge://settings/languages` ます。</span><span class="sxs-lookup"><span data-stu-id="7904f-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   <span data-ttu-id="7904f-136">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="7904f-136">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-137">用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7904f-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="7904f-138">Chromium の問題 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="7904f-138">Chromium issue [#941561][CR941561]</span></span>  

### <span data-ttu-id="7904f-139">webhint Microsoft Edge extension</span><span class="sxs-lookup"><span data-stu-id="7904f-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="7904f-140">Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="7904f-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="7904f-141">詳細はこちら [https://webhint.io][Webhint] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7904f-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   <span data-ttu-id="7904f-143">Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ **ヒント** ] タブ</span><span class="sxs-lookup"><span data-stu-id="7904f-143">The **Hints** tab in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-144">[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="7904f-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="7904f-145">拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="7904f-145">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="7904f-146">詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="7904f-146">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="7904f-147">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="7904f-147">3D View</span></span>  

<span data-ttu-id="7904f-148">**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="7904f-148">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools の3D ビュー" lightbox="../../images/2019/12/3dview.msft.png":::
   <span data-ttu-id="7904f-150">DevTools の**3D ビュー**</span><span class="sxs-lookup"><span data-stu-id="7904f-150">The **3D View** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-151">3D ビューにアクセスするには、 `edge://flags` **開発者ツールの実験** フラグが [ **有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7904f-151">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="7904f-152">Microsoft Edge を再起動して、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="7904f-152">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="7904f-153">`F1`DevTools または [**設定**] に移動し、[**実験**] セクションに移動して、[ **3d ビューを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7904f-153">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="7904f-154">を押して、 `Ctrl`  +  `Shift`  +  `P` **3d ビュー**を入力し、[ **3d ビューの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7904f-154">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="7904f-155">現在、UI を使って3D ビューに機能を追加しています。 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。</span><span class="sxs-lookup"><span data-stu-id="7904f-155">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="7904f-156">Chromium の問題 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="7904f-156">Chromium issue [#987787][CR987787]</span></span>

### <span data-ttu-id="7904f-157">Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="7904f-157">Visual Studio Code extensions</span></span>  

<span data-ttu-id="7904f-158">開発者ツールチームは、テキストエディターからコードを直接使うことができる [Visual Studio コード][VisualStudioCode] の拡張機能もいくつかリリースされました。</span><span class="sxs-lookup"><span data-stu-id="7904f-158">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor.</span></span> <span data-ttu-id="7904f-159">次の拡張子を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-159">Check out the following extensions.</span></span>  

#### <span data-ttu-id="7904f-160">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="7904f-160">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="7904f-161">Visual Studio のコード拡張 [の要素][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] を追加することによって、Visual studio コード内から要素ツールを使います。</span><span class="sxs-lookup"><span data-stu-id="7904f-161">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge (Chromium)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素を使った Visual Studio コードの要素ツール" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   <span data-ttu-id="7904f-163">Microsoft Edge 拡張機能の要素を使った Visual Studio コードの **要素** ツール</span><span class="sxs-lookup"><span data-stu-id="7904f-163">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-164">詳細については、「 [Microsoft Edge Visual Studio コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-164">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="7904f-165">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="7904f-165">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="7904f-166">Microsoft Edge visual Studio コード拡張 [用デバッガー][VisualStudioMarketplaceDebuggerEdge] を使って、microsoft edge で実行されている JavaScript を Visual Studio コードから直接デバッグします。</span><span class="sxs-lookup"><span data-stu-id="7904f-166">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="Visual Studio コードの Microsoft Edge 拡張機能のデバッガー" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   <span data-ttu-id="7904f-168">Visual Studio コードの Microsoft Edge 拡張機能のデバッガー</span><span class="sxs-lookup"><span data-stu-id="7904f-168">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-169">詳細については、「 [Visual Studio コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-169">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="7904f-170">Webhint</span><span class="sxs-lookup"><span data-stu-id="7904f-170">webhint</span></span>  

<span data-ttu-id="7904f-171">作成中の web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio のコードの拡張機能が使用されています。 `webhint`</span><span class="sxs-lookup"><span data-stu-id="7904f-171">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="7904f-172">この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。</span><span class="sxs-lookup"><span data-stu-id="7904f-172">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="Visual Studio コードでの tsx ファイルの分析に関する webhint Visual Studio のコード拡張" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="7904f-174">`.tsx`Visual Studio コードでのファイルの分析に関する webhint Visual Studio コードの拡張機能</span><span class="sxs-lookup"><span data-stu-id="7904f-174">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-175">[Visual Studio コード web ヒントの拡張機能について、詳細はこちらをご覧][WebhintVisualStudioCodeExtension]ください。</span><span class="sxs-lookup"><span data-stu-id="7904f-175">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="7904f-176">Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="7904f-176">Visual Studio integration</span></span>
<span data-ttu-id="7904f-177">Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="7904f-177">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="7904f-178">この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-178">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio" lightbox="../../images/2019/12/vs.msft.png":::
   <span data-ttu-id="7904f-180">Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7904f-180">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-181">[Visual Studio から Microsoft Edge をデバッグする方法については、ブログの投稿を参照][MicrosoftVisualStudioBlogDebugJavascript]してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-181">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="7904f-182">防止コンソールのメッセージを追跡する</span><span class="sxs-lookup"><span data-stu-id="7904f-182">Tracking prevention Console messages</span></span>  

<span data-ttu-id="7904f-183">追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="7904f-183">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="7904f-184">既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7904f-184">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="7904f-185">特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。</span><span class="sxs-lookup"><span data-stu-id="7904f-185">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   <span data-ttu-id="7904f-187">予防を追跡するときに **本体** に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="7904f-187">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-188">[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。</span><span class="sxs-lookup"><span data-stu-id="7904f-188">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="7904f-189">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="7904f-189">Announcements from the Chromium project</span></span>  

<span data-ttu-id="7904f-190">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 80 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="7904f-190">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="7904f-191">本体での let と class の宣言のサポート</span><span class="sxs-lookup"><span data-stu-id="7904f-191">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="7904f-192">**本体**で `let` 、and ステートメントの再宣言がサポートされるようになりました `class` 。</span><span class="sxs-lookup"><span data-stu-id="7904f-192">The **Console** now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="7904f-193">再宣言できないことは、本体を使って新しい JavaScript コードを試す web 開発者にとってよくある面倒な方法です。</span><span class="sxs-lookup"><span data-stu-id="7904f-193">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="7904f-194">`let` `class` コンソールの外部にあるスクリプト、または1つの本体に含まれていないスクリプトの Redeclaring a またはステートメントは、引き続き発生 `SyntaxError` します。</span><span class="sxs-lookup"><span data-stu-id="7904f-194">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="7904f-195">たとえば、前に示したように、ローカル変数を再宣言すると `let` 、本体からエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="7904f-195">For example, previously, when re-declaring a local variable with `let`, the Console threw an error:</span></span>  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="再宣言が失敗することを示す Microsoft Edge 79 のコンソール" lightbox="../../images/2019/12/letbefore.msft.png":::
   <span data-ttu-id="7904f-197">再宣言が失敗することを示す Microsoft Edge 79 の**コンソール**</span><span class="sxs-lookup"><span data-stu-id="7904f-197">The **Console** in Microsoft Edge 79 showing that the let re-declaration fails</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-198">これで、コンソールは再宣言を許可します。</span><span class="sxs-lookup"><span data-stu-id="7904f-198">Now, the Console allows the redeclaration:</span></span>  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="再宣言が正常に完了したことを示す Microsoft Edge 80 のコンソール" lightbox="../../images/2019/12/letafter.msft.png":::
   <span data-ttu-id="7904f-200">再宣言が成功することを示す Microsoft Edge 80 の**コンソール**</span><span class="sxs-lookup"><span data-stu-id="7904f-200">The **Console** in Microsoft Edge 80 showing that the let re-declaration succeeds</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-201">Chromium の問題 [#1004193][CR1004193]</span><span class="sxs-lookup"><span data-stu-id="7904f-201">Chromium issue [#1004193][CR1004193]</span></span>  

### <span data-ttu-id="7904f-202">優れたデバッグ</span><span class="sxs-lookup"><span data-stu-id="7904f-202">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="7904f-203">DevTools は、 [DWARF のデバッグ標準][DwarfHome]をサポートするために開始されています。これは、コードのステップオーバーのサポートが強化され、ブレークポイントを設定して、devtools 内のソース言語でスタックトレースを解決することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7904f-203">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <span data-ttu-id="7904f-204">ネットワークパネルの更新</span><span class="sxs-lookup"><span data-stu-id="7904f-204">Network panel updates</span></span>  

#### <span data-ttu-id="7904f-205">[イニシエーター] タブでイニシエーターチェーンを要求する</span><span class="sxs-lookup"><span data-stu-id="7904f-205">Request Initiator Chains in the Initiator tab</span></span>  

<span data-ttu-id="7904f-206">これで、ネットワーク要求のイニシエーターと依存関係を入れ子になったリストとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7904f-206">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="7904f-207">これは、リソースが要求された理由や、特定のリソース (たとえば、スクリプト \ など) が原因で発生したネットワークアクティビティを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7904f-207">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="[イニシエーター] タブの要求イニシエーターチェーン" lightbox="../../images/2019/12/initiators.msft.png":::
   <span data-ttu-id="7904f-209">[ **イニシエーター** ] タブの要求イニシエーターチェーン</span><span class="sxs-lookup"><span data-stu-id="7904f-209">A Request Initiator Chain in the **Initiator** tab</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-210">[ [ネットワーク] パネルでネットワークアクティビティを記録][DevToolsNetworkIndex]したら、リソースをクリックし、[ **イニシエーター** ] タブに移動して **要求イニシエーターチェーン**を表示します。</span><span class="sxs-lookup"><span data-stu-id="7904f-210">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="7904f-211">検査された **リソース** は太字です。</span><span class="sxs-lookup"><span data-stu-id="7904f-211">The **inspected resource** is bold.</span></span>  <span data-ttu-id="7904f-212">上のスクリーンショットは、 `ai.2.min.js` 検査されたリソースを示しています。</span><span class="sxs-lookup"><span data-stu-id="7904f-212">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="7904f-213">検査されたリソースの上にあるリソースが **イニシエーター**になります。</span><span class="sxs-lookup"><span data-stu-id="7904f-213">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="7904f-214">上のスクリーンショットは、 `https://www.microsoftedgeinsider.com` のイニシエーターを示して `ai.2.min.js` います。</span><span class="sxs-lookup"><span data-stu-id="7904f-214">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="7904f-215">つまり、という `https://www.microsoftedgeinsider.com` ネットワーク要求が発生しました `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="7904f-215">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="7904f-216">検査されたリソースの下にあるリソースは、 **依存関係**です。</span><span class="sxs-lookup"><span data-stu-id="7904f-216">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="7904f-217">上のスクリーンショットは、 `https://dc.services.visualstudio.com/v2/track` の依存関係を示してい `ai.2.min.js` ます。</span><span class="sxs-lookup"><span data-stu-id="7904f-217">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="7904f-218">つまり、という `ai.2.min.js` ネットワーク要求が発生しました `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="7904f-218">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="7904f-219">また、イニシエーターと依存関係の情報にアクセスするには、ネットワークリソースを保持するか、 `Shift` マウスでポイントします。</span><span class="sxs-lookup"><span data-stu-id="7904f-219">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="7904f-220">「 [イニシエーターと依存関係の表示」を][DevToolsNetworkReferenceViewInitiatorsDependencies]ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7904f-220">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="7904f-221">Chromium の問題 [#842488][CR842488]</span><span class="sxs-lookup"><span data-stu-id="7904f-221">Chromium issue [#842488][CR842488]</span></span>  

#### <span data-ttu-id="7904f-222">概要で選択されたネットワーク要求を強調表示する</span><span class="sxs-lookup"><span data-stu-id="7904f-222">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="7904f-223">ネットワークリソースを調べるためにクリックした後、[ネットワーク] パネル **では、** そのリソースの周囲に青色の境界線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7904f-223">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="7904f-224">これにより、ネットワーク要求が予期したより前または後に発生しているかどうかを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="7904f-224">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="調査したリソースを強調表示した [概要] ウィンドウ" lightbox="../../images/2019/12/overview.msft.png":::
   <span data-ttu-id="7904f-226">調査したリソースを強調表示した [ **概要** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7904f-226">The **Overview** pane highlighting the inspected resource</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-227">Chromium の問題 [#988253][CR988253]</span><span class="sxs-lookup"><span data-stu-id="7904f-227">Chromium issue [#988253][CR988253]</span></span>  

#### <span data-ttu-id="7904f-228">[ネットワーク] パネルの [URL] と [path] 列</span><span class="sxs-lookup"><span data-stu-id="7904f-228">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="7904f-229">[**ネットワーク**] パネルの [新しい**パス**] 列と [ **url** ] 列を使用して、各ネットワークリソースの絶対パスまたは完全な url を確認します。</span><span class="sxs-lookup"><span data-stu-id="7904f-229">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="ネットワークパネルの新しいパスと URL 列" lightbox="../../images/2019/12/columns.msft.png":::
   <span data-ttu-id="7904f-231">**ネットワーク**パネルの新しいパスと URL 列</span><span class="sxs-lookup"><span data-stu-id="7904f-231">The new Path and URL columns in the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-232">**ウォーターフォール**テーブルのヘッダーを右クリックし、[**パス**] または [ **URL** ] を選択して新しい列を表示します。</span><span class="sxs-lookup"><span data-stu-id="7904f-232">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="7904f-233">Chromium の問題 [#993366][CR993366]</span><span class="sxs-lookup"><span data-stu-id="7904f-233">Chromium issue [#993366][CR993366]</span></span>  

#### <span data-ttu-id="7904f-234">更新されたユーザーエージェント文字列</span><span class="sxs-lookup"><span data-stu-id="7904f-234">Updated User-Agent strings</span></span>  

<span data-ttu-id="7904f-235">DevTools は、[ **ネットワークの条件** ] タブを使用したカスタムユーザーエージェント文字列の設定をサポートしています。 ユーザーエージェントの文字列は、 `User-Agent` ネットワークリソースに接続される HTTP ヘッダーと、の値に影響し `navigator.userAgent` ます。</span><span class="sxs-lookup"><span data-stu-id="7904f-235">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="7904f-236">定義済みのユーザーエージェント文字列は、最新のブラウザーバージョンを反映するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="7904f-236">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="[ネットワークの条件] タブの [ユーザーエージェント] メニュー" lightbox="../../images/2019/12/useragent.msft.png":::
   <span data-ttu-id="7904f-238">[ **ネットワークの条件** ] タブの [ユーザーエージェント] メニュー</span><span class="sxs-lookup"><span data-stu-id="7904f-238">The User Agent menu in the **Network Conditions** tab</span></span>  
:::image-end:::  

<span data-ttu-id="7904f-239">ネットワークの **状態**にアクセスするには、 [コマンドメニューを開い][DevToolsCommandMenuIndex] てコマンドを実行し `Show Network Conditions` ます。</span><span class="sxs-lookup"><span data-stu-id="7904f-239">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="7904f-240">[デバイスモードでは、ユーザーエージェント文字列を設定][DevToolsDeviceModeIndex]することもできます。</span><span class="sxs-lookup"><span data-stu-id="7904f-240">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="7904f-241">Chromium の問題 [#1029031][CR1029031]</span><span class="sxs-lookup"><span data-stu-id="7904f-241">Chromium issue [#1029031][CR1029031]</span></span>  

### <span data-ttu-id="7904f-242">監査パネルの更新</span><span class="sxs-lookup"><span data-stu-id="7904f-242">Audits panel updates</span></span>  

#### <span data-ttu-id="7904f-243">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="7904f-243">New configuration UI</span></span>  

<span data-ttu-id="7904f-244">構成 UI には、応答性の高い新しいデザインがあり、調整構成オプションが簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="7904f-244">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="7904f-245">調整 UI の変更について詳しくは、「 [監査パネルの調整][GitHubGoogleChromeDevToolsAuditsPanelThrottling] 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7904f-245">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新しい構成 UI" lightbox="../../images/2019/12/start.msft.png":::
   <span data-ttu-id="7904f-247">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="7904f-247">The new configuration UI</span></span>  
:::image-end:::  

### <span data-ttu-id="7904f-248">[カバレッジ] タブの更新</span><span class="sxs-lookup"><span data-stu-id="7904f-248">Coverage tab updates</span></span>  

#### <span data-ttu-id="7904f-249">関数単位またはブロック単位のカバレッジモード</span><span class="sxs-lookup"><span data-stu-id="7904f-249">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="7904f-250">[ [カバレッジ] タブ][DevToolsCoverageIndex] には、1つの **関数** または **ブロック**ごとにコードカバレッジデータを収集するかどうかを指定できる新しいドロップダウンメニューがあります。</span><span class="sxs-lookup"><span data-stu-id="7904f-250">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="7904f-251">**ブロック範囲ごと** に、さらに詳しい情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="7904f-251">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="7904f-252">DevTools では、既定で **機能ごとに機能** を使用します。</span><span class="sxs-lookup"><span data-stu-id="7904f-252">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="7904f-253">**各機能**と**ブロック**モードのどちらを使用するかによって、HTML ファイルに大きなコードカバレッジの違いが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7904f-253">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="7904f-254">**関数単位**モードを使う場合、HTML ファイル内のインラインスクリプトは関数として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7904f-254">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="7904f-255">スクリプトがすべて実行された場合は、DevTools はスクリプト全体を使用コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="7904f-255">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="7904f-256">スクリプトがまったく実行されない場合のみ、DevTools はスクリプトを未使用コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="7904f-256">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="[カバレッジモード] ドロップダウンメニュー" lightbox="../../images/2019/12/modes.msft.png":::
   <span data-ttu-id="7904f-258">[カバレッジモード] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="7904f-258">The coverage mode dropdown menu</span></span>  
:::image-end:::  

#### <span data-ttu-id="7904f-259">ページの再読み込みによってカバーが開始されるようになりました</span><span class="sxs-lookup"><span data-stu-id="7904f-259">Coverage must now be initiated by a page reload</span></span>  

<span data-ttu-id="7904f-260">カバレッジデータの信頼性が低いため、ページの再読み込みを行わずにコードカバレッジを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="7904f-260">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="7904f-261">たとえば、ランタイムが長時間前であり、V8 ガベージコレクターによってクリーンアップされている場合、関数は未使用として報告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7904f-261">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="7904f-262">Chromium の問題 [#1004203][CR1004203]</span><span class="sxs-lookup"><span data-stu-id="7904f-262">Chromium issue [#1004203][CR1004203]</span></span>  

## <span data-ttu-id="7904f-263">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7904f-263">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="7904f-264">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7904f-264">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="7904f-265">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7904f-265">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="7904f-266">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="7904f-266">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

<!--[../../images/2019/12/wasm.msft.png]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイルビューポートをシミュレートする Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする |Microsoft ドキュメント"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "Microsoft Edge DevTools でネットワークアクティビティを検査する |Microsoft ドキュメント"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "イニシエーターと依存関係の表示-ネットワーク分析リファレンス |Microsoft ドキュメント"  
[DevGuideEdgeHtmlWhatsNew]: /microsoft-edge/dev-guide/whats-new "EdgeHTML の新機能 |Microsoft ドキュメント"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio コード拡張機能のデバッガー |Microsoft ドキュメント"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio コード拡張の要素 |Microsoft ドキュメント"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "[ヘッダー] タブに [イニシエーター] フィールドを追加します。Chromium のバグ"  
[CR988253]: https://crbug.com/988253 "バグ DevTools-ネットワーク要求とタイムライングラフの間に関連性がありません |Chromium のバグ"  
[CR993366]: https://crbug.com/993366 "ネットワークパネル要求リストで URL のパス部分を表示してください |Chromium のバグ"  
[CR1004193]: https://crbug.com/1004193 "V8 の REPL モード |Chromium のバグ"  
[CR1004203]: https://crbug.com/1004203 "コードカバレッジをすばらしいものにする |Chromium のバグ"  
[CR1029031]: https://crbug.com/1029031 "UA 文字列が古くなります。 |Chromium のバグ" 
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"
[CR941561]: https://crbug.com/941561 "DevTools のローカライズ可能性 |Chromium のバグ"
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromium のバグ"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  

[DwarfHome]: https://dwarfstd.org "Dwarf ホーム"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools の監査パネルの調整-GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "Visual Studio からの Microsoft Edge で JavaScript をデバッグする |Visual Studio ブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "web ヒント"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio のコード拡張 |webhint に関するドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"

> [!NOTE]
> <span data-ttu-id="7904f-306">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7904f-306">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7904f-307">元のページは [ここ](https://developers.google.com/web/updates/2019/12/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="7904f-307">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7904f-309">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7904f-309">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
