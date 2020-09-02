---
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4f155a99d28d208bc288e3175b49c221684619a0
ms.sourcegitcommit: 2fa65cca74c5214601900579c0ce9f946ad8a27e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991201"
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

# <span data-ttu-id="5ef96-103">DevTools の新機能 (Microsoft Edge 80)</span><span class="sxs-lookup"><span data-stu-id="5ef96-103">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <span data-ttu-id="5ef96-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="5ef96-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="5ef96-105">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="5ef96-106">これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="5ef96-107">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="5ef96-108">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="5ef96-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="5ef96-109">DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="5ef96-110">Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ef96-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="5ef96-111">図 1</span><span class="sxs-lookup"><span data-stu-id="5ef96-111">Figure 1</span></span>  
> <span data-ttu-id="5ef96-112">キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール</span><span class="sxs-lookup"><span data-stu-id="5ef96-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="5ef96-114">すべてのユーザーが web ページにアクセスできるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="5ef96-115">使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="5ef96-116">スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="5ef96-117">Chromium の問題 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="5ef96-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="5ef96-118">他の言語での DevTools の使用</span><span class="sxs-lookup"><span data-stu-id="5ef96-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="5ef96-119">多くの開発者は、英語だけでなく、StackOverflow や VS コードなどの他の開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="5ef96-120">ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="5ef96-121">中国語 \ (簡体字)- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="5ef96-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5ef96-122">中国語 (繁体字)- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="5ef96-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="5ef96-123">フランス語– fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="5ef96-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5ef96-124">ドイツ語-deutsch</span><span class="sxs-lookup"><span data-stu-id="5ef96-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="5ef96-125">イタリア語-italiano</span><span class="sxs-lookup"><span data-stu-id="5ef96-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5ef96-126">日本語- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="5ef96-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="5ef96-127">韓国語- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="5ef96-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5ef96-128">ポルトガル語-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="5ef96-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="5ef96-129">ロシア語–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="5ef96-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5ef96-130">スペイン語-&#241;ol</span><span class="sxs-lookup"><span data-stu-id="5ef96-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="5ef96-131">に移動 `edge://flags` して、[ローカライズされた **開発者ツールを有効** にする] フラグを [ **有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="5ef96-132">また、 **開発者ツールの実験** フラグを [ **有効**にする」に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="5ef96-133">Microsoft Edge を再起動して、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="5ef96-134">DevTools は、Microsoft Edge で使用する言語と一致し `edge://settings/languages` ます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

> ##### <span data-ttu-id="5ef96-135">図 2</span><span class="sxs-lookup"><span data-stu-id="5ef96-135">Figure 2</span></span>  
> <span data-ttu-id="5ef96-136">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="5ef96-136">The DevTools in German</span></span>  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

<span data-ttu-id="5ef96-138">用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="5ef96-139">Chromium の問題 [#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="5ef96-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="5ef96-140">webhint Microsoft Edge extension</span><span class="sxs-lookup"><span data-stu-id="5ef96-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="5ef96-141">Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="5ef96-142">詳細はこちら [https://webhint.io][Webhint] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="5ef96-143">図 3</span><span class="sxs-lookup"><span data-stu-id="5ef96-143">Figure 3</span></span>  
> <span data-ttu-id="5ef96-144">Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ</span><span class="sxs-lookup"><span data-stu-id="5ef96-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

<span data-ttu-id="5ef96-146">[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="5ef96-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="5ef96-147">拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="5ef96-148">詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="5ef96-149">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="5ef96-149">3D View</span></span>  

<span data-ttu-id="5ef96-150">**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="5ef96-151">図 4</span><span class="sxs-lookup"><span data-stu-id="5ef96-151">Figure 4</span></span>  
> <span data-ttu-id="5ef96-152">DevTools の3D ビュー</span><span class="sxs-lookup"><span data-stu-id="5ef96-152">The 3D View in the DevTools</span></span>  
> ![DevTools の3D ビュー][Image3DView]  

<span data-ttu-id="5ef96-154">3D ビューにアクセスするには、 `edge://flags` **開発者ツールの実験** フラグが [ **有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-154">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="5ef96-155">Microsoft Edge を再起動して、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-155">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="5ef96-156">`F1`DevTools または [**設定**] に移動し、[**実験**] セクションに移動して、[ **3d ビューを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-156">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="5ef96-157">を押して、 `Ctrl`  +  `Shift`  +  `P` **3d ビュー**を入力し、[ **3d ビューの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-157">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="5ef96-158">現在、UI を使って3D ビューに機能を追加しています。 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-158">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="5ef96-159">Chromium の問題 [#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="5ef96-159">Chromium issue [#987787][crbug987787]</span></span>

### <span data-ttu-id="5ef96-160">Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="5ef96-160">Visual Studio Code extensions</span></span>  

<span data-ttu-id="5ef96-161">[Visual Studio コード \ (VS コード \)][VisualStudioCode]用の一部の拡張機能がリリースされました。この機能を使って、テキストエディターから、開発者ツールの機能を直接使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-161">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="5ef96-162">以下の拡張子を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-162">Check out the extensions below:</span></span>  

#### <span data-ttu-id="5ef96-163">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="5ef96-163">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="5ef96-164">[Microsoft Edge \ (Chromium \)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] vs コード拡張の要素を追加して、vs コード内の要素ツールを使います。</span><span class="sxs-lookup"><span data-stu-id="5ef96-164">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="5ef96-165">図 5</span><span class="sxs-lookup"><span data-stu-id="5ef96-165">Figure 5</span></span>  
> <span data-ttu-id="5ef96-166">Microsoft Edge 拡張機能の要素を使用した VS コードの要素ツール</span><span class="sxs-lookup"><span data-stu-id="5ef96-166">The Elements tool in VS Code using the Elements for Microsoft Edge extension</span></span>  
> ![Microsoft Edge 拡張機能の要素を使用した VS コードの要素ツール][ImageElementsVisualStudioCode]  

<span data-ttu-id="5ef96-168">詳細については、「 [Microsoft EDGE VS コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-168">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="5ef96-169">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="5ef96-169">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="5ef96-170">[Microsoft edge vs のコード拡張用デバッガー][VisualStudioMarketplaceDebuggerEdge]を使って、microsoft edge で実行されている JAVASCRIPT を vs コードから直接デバッグします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-170">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="5ef96-171">図 6</span><span class="sxs-lookup"><span data-stu-id="5ef96-171">Figure 6</span></span>  
> <span data-ttu-id="5ef96-172">VS コードの Microsoft Edge Extension のデバッガー</span><span class="sxs-lookup"><span data-stu-id="5ef96-172">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS コードの Microsoft Edge Extension のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="5ef96-174">詳細については、「 [VS コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-174">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="5ef96-175">Webhint</span><span class="sxs-lookup"><span data-stu-id="5ef96-175">webhint</span></span>  

<span data-ttu-id="5ef96-176">Web ページを作成しているときに、web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] VS コード拡張を使います。 `webhint`</span><span class="sxs-lookup"><span data-stu-id="5ef96-176">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="5ef96-177">この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-177">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="5ef96-178">図 7</span><span class="sxs-lookup"><span data-stu-id="5ef96-178">Figure 7</span></span>  
> <span data-ttu-id="5ef96-179">VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="5ef96-179">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="5ef96-181">[詳細については、「VS コード webhint 拡張機能」を参照して][WebhintVisualStudioCodeExtension]ください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-181">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="5ef96-182">Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="5ef96-182">Visual Studio integration</span></span>
<span data-ttu-id="5ef96-183">Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-183">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="5ef96-184">この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-184">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="5ef96-185">図 8</span><span class="sxs-lookup"><span data-stu-id="5ef96-185">Figure 8</span></span>  
> <span data-ttu-id="5ef96-186">Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5ef96-186">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="5ef96-188">[Visual Studio から Microsoft Edge をデバッグする方法については、ブログの投稿を参照][MicrosoftVisualStudioBlogDebugJavascript]してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-188">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="5ef96-189">防止コンソールのメッセージを追跡する</span><span class="sxs-lookup"><span data-stu-id="5ef96-189">Tracking prevention Console messages</span></span>  

<span data-ttu-id="5ef96-190">追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="5ef96-190">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="5ef96-191">既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-191">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="5ef96-192">特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-192">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="5ef96-193">図 9</span><span class="sxs-lookup"><span data-stu-id="5ef96-193">Figure 9</span></span>  
> <span data-ttu-id="5ef96-194">予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-194">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。][ImageTrackingPrevention]  

<span data-ttu-id="5ef96-196">[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-196">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="5ef96-197">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="5ef96-197">Announcements from the Chromium project</span></span>  

<span data-ttu-id="5ef96-198">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 80 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-198">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="5ef96-199">本体での let と class の宣言のサポート</span><span class="sxs-lookup"><span data-stu-id="5ef96-199">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="5ef96-200">本体で、and ステートメントの再宣言がサポートされるようになりました `let` `class` 。</span><span class="sxs-lookup"><span data-stu-id="5ef96-200">The Console now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="5ef96-201">再宣言できないことは、本体を使って新しい JavaScript コードを試す web 開発者にとってよくある面倒な方法です。</span><span class="sxs-lookup"><span data-stu-id="5ef96-201">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="5ef96-202">`let` `class` コンソールの外部にあるスクリプト、または1つの本体に含まれていないスクリプトの Redeclaring a またはステートメントは、引き続き発生 `SyntaxError` します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-202">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="5ef96-203">たとえば、前の例のように、ローカル変数を redeclaring すると `let` 、本体からエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-203">For example, previously, when redeclaring a local variable with `let`, the Console threw an error:</span></span>  

> ##### <span data-ttu-id="5ef96-204">図 10</span><span class="sxs-lookup"><span data-stu-id="5ef96-204">Figure 10</span></span>  
> <span data-ttu-id="5ef96-205">再宣言が失敗することを示す Microsoft Edge 79 のコンソール</span><span class="sxs-lookup"><span data-stu-id="5ef96-205">The Console in Microsoft Edge 79 showing that the let redeclaration fails</span></span>  
> ![再宣言が失敗することを示す Microsoft Edge 79 のコンソール][ImageConsoleRedeclarationFails]  

<span data-ttu-id="5ef96-207">これで、コンソールは再宣言を許可します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-207">Now, the Console allows the redeclaration:</span></span>  

> ##### <span data-ttu-id="5ef96-208">図 11</span><span class="sxs-lookup"><span data-stu-id="5ef96-208">Figure 11</span></span>  
> <span data-ttu-id="5ef96-209">再宣言が正常に完了したことを示す Microsoft Edge 80 のコンソール</span><span class="sxs-lookup"><span data-stu-id="5ef96-209">The Console in Microsoft Edge 80 showing that the let redeclaration succeeds</span></span>  
> ![再宣言が正常に完了したことを示す Microsoft Edge 80 のコンソール][ImageConsoleRedeclarationSucceeds]  

<span data-ttu-id="5ef96-211">Chromium の問題 [#1004193][crbug1004193]</span><span class="sxs-lookup"><span data-stu-id="5ef96-211">Chromium issue [#1004193][crbug1004193]</span></span>  

### <span data-ttu-id="5ef96-212">優れたデバッグ</span><span class="sxs-lookup"><span data-stu-id="5ef96-212">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="5ef96-213">DevTools は、 [DWARF のデバッグ標準][DwarfHome]をサポートするために開始されています。これは、コードのステップオーバーのサポートが強化され、ブレークポイントを設定して、devtools 内のソース言語でスタックトレースを解決することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-213">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### <span data-ttu-id="5ef96-214">ネットワークパネルの更新</span><span class="sxs-lookup"><span data-stu-id="5ef96-214">Network panel updates</span></span>  

#### <span data-ttu-id="5ef96-215">[イニシエーター] タブでイニシエーターチェーンを要求する</span><span class="sxs-lookup"><span data-stu-id="5ef96-215">Request Initiator Chains in the Initiator tab</span></span>  

<span data-ttu-id="5ef96-216">これで、ネットワーク要求のイニシエーターと依存関係を入れ子になったリストとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5ef96-216">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="5ef96-217">これは、リソースが要求された理由や、特定のリソース (たとえば、スクリプト \ など) が原因で発生したネットワークアクティビティを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-217">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

> ##### <span data-ttu-id="5ef96-218">図 12</span><span class="sxs-lookup"><span data-stu-id="5ef96-218">Figure 12</span></span>  
> <span data-ttu-id="5ef96-219">[イニシエーター] タブの要求イニシエーターチェーン</span><span class="sxs-lookup"><span data-stu-id="5ef96-219">A Request Initiator Chain in the Initiator tab</span></span>  
> ![[イニシエーター] タブの要求イニシエーターチェーン][ImageRequestInitiatorChain]  

<span data-ttu-id="5ef96-221">[ [ネットワーク] パネルでネットワークアクティビティを記録][DevToolsNetworkIndex]したら、リソースをクリックし、[ **イニシエーター** ] タブに移動して **要求イニシエーターチェーン**を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-221">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="5ef96-222">検査された **リソース** は太字です。</span><span class="sxs-lookup"><span data-stu-id="5ef96-222">The **inspected resource** is bold.</span></span>  <span data-ttu-id="5ef96-223">上のスクリーンショットは、 `ai.2.min.js` 検査されたリソースを示しています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-223">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="5ef96-224">検査されたリソースの上にあるリソースが **イニシエーター**になります。</span><span class="sxs-lookup"><span data-stu-id="5ef96-224">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="5ef96-225">上のスクリーンショットは、 `https://www.microsoftedgeinsider.com` のイニシエーターを示して `ai.2.min.js` います。</span><span class="sxs-lookup"><span data-stu-id="5ef96-225">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="5ef96-226">つまり、という `https://www.microsoftedgeinsider.com` ネットワーク要求が発生しました `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="5ef96-226">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="5ef96-227">検査されたリソースの下にあるリソースは、 **依存関係**です。</span><span class="sxs-lookup"><span data-stu-id="5ef96-227">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="5ef96-228">上のスクリーンショットは、 `https://dc.services.visualstudio.com/v2/track` の依存関係を示してい `ai.2.min.js` ます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-228">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="5ef96-229">つまり、という `ai.2.min.js` ネットワーク要求が発生しました `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="5ef96-229">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="5ef96-230">また、イニシエーターと依存関係の情報にアクセスするには、ネットワークリソースを保持するか、 `Shift` マウスでポイントします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-230">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="5ef96-231">「 [イニシエーターと依存関係の表示」を][DevToolsNetworkReferenceViewInitiatorsDependencies]ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-231">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="5ef96-232">Chromium の問題 [#842488][crbug842488]</span><span class="sxs-lookup"><span data-stu-id="5ef96-232">Chromium issue [#842488][crbug842488]</span></span>  

#### <span data-ttu-id="5ef96-233">概要で選択されたネットワーク要求を強調表示する</span><span class="sxs-lookup"><span data-stu-id="5ef96-233">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="5ef96-234">ネットワークリソースを調べるためにクリックした後、[ネットワーク] パネル **では、** そのリソースの周囲に青色の境界線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-234">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="5ef96-235">これにより、ネットワーク要求が予期したより前または後に発生しているかどうかを検出することができます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-235">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

> ##### <span data-ttu-id="5ef96-236">図 13</span><span class="sxs-lookup"><span data-stu-id="5ef96-236">Figure 13</span></span>  
> <span data-ttu-id="5ef96-237">調査したリソースを強調表示した [概要] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5ef96-237">The Overview pane highlighting the inspected resource</span></span>  
> ![調査したリソースを強調表示した [概要] ウィンドウ][ImageOverviewPaneInspectedResource]  

<span data-ttu-id="5ef96-239">Chromium の問題 [#988253][crbug988253]</span><span class="sxs-lookup"><span data-stu-id="5ef96-239">Chromium issue [#988253][crbug988253]</span></span>  

#### <span data-ttu-id="5ef96-240">[ネットワーク] パネルの [URL] と [path] 列</span><span class="sxs-lookup"><span data-stu-id="5ef96-240">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="5ef96-241">[**ネットワーク**] パネルの [新しい**パス**] 列と [ **url** ] 列を使用して、各ネットワークリソースの絶対パスまたは完全な url を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-241">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

> ##### <span data-ttu-id="5ef96-242">図 14</span><span class="sxs-lookup"><span data-stu-id="5ef96-242">Figure 14</span></span>  
> <span data-ttu-id="5ef96-243">ネットワークパネルの新しいパスと URL 列</span><span class="sxs-lookup"><span data-stu-id="5ef96-243">The new Path and URL columns in the Network panel</span></span>  
> ![ネットワークパネルの新しいパスと URL 列][ImagePathNetworkPanel]  

<span data-ttu-id="5ef96-245">**ウォーターフォール**テーブルのヘッダーを右クリックし、[**パス**] または [ **URL** ] を選択して新しい列を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-245">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="5ef96-246">Chromium の問題 [#993366][crbug993366]</span><span class="sxs-lookup"><span data-stu-id="5ef96-246">Chromium issue [#993366][crbug993366]</span></span>  

#### <span data-ttu-id="5ef96-247">更新されたユーザーエージェント文字列</span><span class="sxs-lookup"><span data-stu-id="5ef96-247">Updated User-Agent strings</span></span>  

<span data-ttu-id="5ef96-248">DevTools は、[ **ネットワークの条件** ] タブを使用したカスタムユーザーエージェント文字列の設定をサポートしています。 ユーザーエージェントの文字列は、 `User-Agent` ネットワークリソースに接続される HTTP ヘッダーと、の値に影響し `navigator.userAgent` ます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-248">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="5ef96-249">定義済みのユーザーエージェント文字列は、最新のブラウザーバージョンを反映するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-249">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

> ##### <span data-ttu-id="5ef96-250">図 15</span><span class="sxs-lookup"><span data-stu-id="5ef96-250">Figure 15</span></span>  
> <span data-ttu-id="5ef96-251">[ネットワークの条件] タブの [ユーザーエージェント] メニュー</span><span class="sxs-lookup"><span data-stu-id="5ef96-251">The User Agent menu in the Network Conditions tab</span></span>  
> ![[ネットワークの条件] タブの [ユーザーエージェント] メニュー][ImageUserAgentNetworkConditionsTab]  

<span data-ttu-id="5ef96-253">ネットワークの **状態**にアクセスするには、 [コマンドメニューを開い][DevToolsCommandMenuIndex] てコマンドを実行し `Show Network Conditions` ます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-253">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="5ef96-254">[デバイスモードでは、ユーザーエージェント文字列を設定][DevToolsDeviceModeIndex]することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-254">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="5ef96-255">Chromium の問題 [#1029031][crbug1029031]</span><span class="sxs-lookup"><span data-stu-id="5ef96-255">Chromium issue [#1029031][crbug1029031]</span></span>  

### <span data-ttu-id="5ef96-256">監査パネルの更新</span><span class="sxs-lookup"><span data-stu-id="5ef96-256">Audits panel updates</span></span>  

#### <span data-ttu-id="5ef96-257">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="5ef96-257">New configuration UI</span></span>  

<span data-ttu-id="5ef96-258">構成 UI には、応答性の高い新しいデザインがあり、調整構成オプションが簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-258">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="5ef96-259">調整 UI の変更について詳しくは、「 [監査パネルの調整][GitHubGoogleChromeDevToolsAuditsPanelThrottling] 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-259">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

> ##### <span data-ttu-id="5ef96-260">図 16</span><span class="sxs-lookup"><span data-stu-id="5ef96-260">Figure 16</span></span>  
> <span data-ttu-id="5ef96-261">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="5ef96-261">The new configuration UI</span></span>  
> ![新しい構成 UI][ImageConfigurationUI]  

### <span data-ttu-id="5ef96-263">[カバレッジ] タブの更新</span><span class="sxs-lookup"><span data-stu-id="5ef96-263">Coverage tab updates</span></span>  

#### <span data-ttu-id="5ef96-264">関数単位またはブロック単位のカバレッジモード</span><span class="sxs-lookup"><span data-stu-id="5ef96-264">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="5ef96-265">[ [カバレッジ] タブ][DevToolsCoverageIndex] には、1つの **関数** または **ブロック**ごとにコードカバレッジデータを収集するかどうかを指定できる新しいドロップダウンメニューがあります。</span><span class="sxs-lookup"><span data-stu-id="5ef96-265">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="5ef96-266">**ブロック範囲ごと** に、さらに詳しい情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-266">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="5ef96-267">DevTools では、既定で **機能ごとに機能** を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ef96-267">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="5ef96-268">**各機能**と**ブロック**モードのどちらを使用するかによって、HTML ファイルに大きなコードカバレッジの違いが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5ef96-268">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="5ef96-269">**関数単位**モードを使う場合、HTML ファイル内のインラインスクリプトは関数として扱われます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-269">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="5ef96-270">スクリプトがすべて実行された場合は、DevTools はスクリプト全体を使用コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-270">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="5ef96-271">スクリプトがまったく実行されない場合のみ、DevTools はスクリプトを未使用コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="5ef96-271">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

> ##### <span data-ttu-id="5ef96-272">図 17</span><span class="sxs-lookup"><span data-stu-id="5ef96-272">Figure 17</span></span>  
> <span data-ttu-id="5ef96-273">[カバレッジモード] ドロップダウンメニュー</span><span class="sxs-lookup"><span data-stu-id="5ef96-273">The coverage mode dropdown menu</span></span>  
> ![[カバレッジモード] ドロップダウンメニュー][ImageCoverageMode]  

#### <span data-ttu-id="5ef96-275">ページの再読み込みによってカバーが開始されるようになりました</span><span class="sxs-lookup"><span data-stu-id="5ef96-275">Coverage must now be initiated by a page reload</span></span>  

<span data-ttu-id="5ef96-276">カバレッジデータの信頼性が低いため、ページの再読み込みを行わずにコードカバレッジを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="5ef96-276">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="5ef96-277">たとえば、ランタイムが長時間前であり、V8 ガベージコレクターによってクリーンアップされている場合、関数は未使用として報告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5ef96-277">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="5ef96-278">Chromium の問題 [#1004203][crbug1004203]</span><span class="sxs-lookup"><span data-stu-id="5ef96-278">Chromium issue [#1004203][crbug1004203]</span></span>  

## <span data-ttu-id="5ef96-279">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="5ef96-279">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="5ef96-280">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5ef96-280">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="5ef96-281">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-281">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="5ef96-282">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="5ef96-282">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "図 1: キーボードナビゲーションとスクリーンリーダーの機能強化による DevTools のパフォーマンスツール"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "図 3: webhint ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "図 4: Microsoft Edge DevTools の3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "図 5: Microsoft Edge Extension の要素を使用した VS コードの要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "図 6: VS コードの Microsoft Edge Extension 用デバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "図 7: web ヒント VS コード拡張機能 (VS コードでの tsx ファイルの分析)"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "図 8: Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "図 9: 予防を追跡するときに本体に表示されるメッセージによって、トラッカーの記憶域へのアクセスがブロックされる"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "図 10: 再宣言に失敗したことを示す Microsoft Edge 79 の本体"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "図 11: 再宣言が成功したことを示す Microsoft Edge 80 の本体"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "図 12: [イニシエーター] タブの要求イニシエーターチェーン"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "図 13: 調査したリソースを強調表示した [概要] ウィンドウ"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "図 14: ネットワークパネルの新しいパスと URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "図 15: [ネットワーク条件] タブの [ユーザーエージェント] メニュー"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "図 16: 新しい構成 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "図 17: [カバレッジモード] ドロップダウンメニュー"  

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "モバイルビューポートをシミュレートする Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする"  
[DevToolsNetworkIndex]: ../../../network/index.md "Microsoft Edge DevTools でネットワークアクティビティを検査する"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "イニシエーターと依存関係の表示-ネットワーク分析リファレンス"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML の新機能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張用デバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張の要素"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488-[ヘッダー] タブに [イニシエーター] フィールドを追加する (Monorail"  
[crbug988253]: https://crbug.com/988253 "988253-バグ開発ツール-ネットワーク要求とタイムライングラフ間の関係なし (Monorail"  
[crbug993366]: https://crbug.com/993366 "993366-ネットワークパネル要求リストの URL のパス部分を表示してください (Monorail"  
[crbug1004193]: https://crbug.com/1004193 "1004193-V8 の REPL モード"  
[crbug1004203]: https://crbug.com/1004203 "1004203-monorail アウト"  
[crbug1029031]: https://crbug.com/1029031 "1029031-UA 文字列が期限切れになっている" 
[crbug963183]: https://crbug.com/963183 "963183-DevTools は WCAG に準拠していません"
[crbug941561]: https://crbug.com/941561 "941561-DevTools のローカライズ可能性"
[crbug987787]: https://crbug.com/987787 "987787-Dom 3D ビュー"

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
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |webhint に関するドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"

> [!NOTE]
> <span data-ttu-id="5ef96-339">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ef96-339">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5ef96-340">元のページは [ここ](https://developers.google.com/web/updates/2019/12/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-340">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5ef96-342">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5ef96-342">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
