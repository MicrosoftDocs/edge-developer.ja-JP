---
description: 3D ビュー、Visual Studio と Microsoft Edge の統合など。
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3081ebb256a9ede637aaaddc3c3cdf7a70a201bb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015476"
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

# <span data-ttu-id="14253-104">DevTools の新機能 (Microsoft Edge 81)</span><span class="sxs-lookup"><span data-stu-id="14253-104">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <span data-ttu-id="14253-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="14253-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="14253-106">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="14253-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="14253-107">それらを確認して、DevTools、Visual Studio コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="14253-107">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="14253-108">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="14253-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="14253-109">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="14253-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="14253-110">DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="14253-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="14253-111">Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14253-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="14253-113">キーボードナビゲーションとスクリーンリーダーの改良による DevTools の **パフォーマンス** ツール</span><span class="sxs-lookup"><span data-stu-id="14253-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="14253-114">すべてのユーザーが web ページにアクセスできるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14253-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="14253-115">使用を開始するには、Microsoft Edge のアクセシビリティに関する [洞察][AccessibilityInsights] と [webhint][WebhintBrowserExtension] の拡張機能をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="14253-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="14253-116">スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="14253-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="14253-117">Chromium の問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="14253-117">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="14253-118">他の言語での DevTools の使用</span><span class="sxs-lookup"><span data-stu-id="14253-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="14253-119">多くの開発者は、英語だけでなく、StackOverflow や Visual Studio コードなどの開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="14253-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="14253-120">ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="14253-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="14253-121">中国語 \ (簡体字)- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="14253-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="14253-122">中国語 (繁体字)- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="14253-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="14253-123">フランス語– fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="14253-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="14253-124">ドイツ語-deutsch</span><span class="sxs-lookup"><span data-stu-id="14253-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="14253-125">イタリア語-italiano</span><span class="sxs-lookup"><span data-stu-id="14253-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="14253-126">日本語- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="14253-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="14253-127">韓国語- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="14253-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="14253-128">ポルトガル語-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="14253-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="14253-129">ロシア語–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="14253-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="14253-130">スペイン語-&#241;ol</span><span class="sxs-lookup"><span data-stu-id="14253-130">Spanish - espa&#241;ol</span></span>
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文(简体)（简体）| Chinese (Traditional) - 中文(繁體)（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

<span data-ttu-id="14253-131">DevTools は、Microsoft Edge で使用する言語と自動的に一致し `edge://settings/languages` ます。</span><span class="sxs-lookup"><span data-stu-id="14253-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="14253-132">Microsoft Edge を1つの言語で使用し、DevTools を英語のままにしておく場合は、 `F1` DevTools を押して [ [設定][Settings] ] を開き、[ **ブラウザー言語の一致**] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="14253-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   <span data-ttu-id="14253-134">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="14253-134">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="14253-135">**コンソール** メッセージはローカライズされません。</span><span class="sxs-lookup"><span data-stu-id="14253-135">**Console** messages are not localized.</span></span>  <span data-ttu-id="14253-136">DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="14253-136">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="14253-137">用意されているものとは異なる言語で DevTools を使う場合は、 [ツイート][PostTweetEdgeDevTools] にサインインするか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="14253-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="14253-138">Chromium の問題 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="14253-138">Chromium issue [#941561][CR941561]</span></span>  

### <span data-ttu-id="14253-139">webhint Microsoft Edge extension</span><span class="sxs-lookup"><span data-stu-id="14253-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="14253-140">Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="14253-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="14253-141">詳細はこちら [https://webhint.io][Webhint] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14253-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   <span data-ttu-id="14253-143">Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ **ヒント** ] タブ</span><span class="sxs-lookup"><span data-stu-id="14253-143">The **Hints** tab in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="14253-144">[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="14253-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="14253-145">拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="14253-145">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="14253-146">詳細については、 [webhint.io][WebhintBrowserExtension] にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="14253-146">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="14253-147">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="14253-147">3D View</span></span>  

<span data-ttu-id="14253-148">**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="14253-148">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools の3D ビュー" lightbox="../../images/2020/01/3dview.msft.png":::
   <span data-ttu-id="14253-150">DevTools の3D ビュー</span><span class="sxs-lookup"><span data-stu-id="14253-150">The 3D View in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="14253-151">3d ビューにアクセスするには、キーを押して `Ctrl`  +  `Shift`  +  `P` **3d ビュー**で入力し、[ **3d ビューの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="14253-151">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="14253-152">現在、UI を使って3D ビューに機能を追加していますので、 [フィードバック](#getting-in-touch-with-microsoft-edge-devtools-team)をお送りください。</span><span class="sxs-lookup"><span data-stu-id="14253-152">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="14253-153">Chromium の問題 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="14253-153">Chromium issue [#987787][CR987787]</span></span>  

### <span data-ttu-id="14253-154">Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="14253-154">Visual Studio Code extensions</span></span>  

<span data-ttu-id="14253-155">開発者ツールチームは、テキストエディターから、開発者ツールのパワーを直接使うことができる [Visual Studio コード][VisualStudioCode] の拡張機能もリリースされました。</span><span class="sxs-lookup"><span data-stu-id="14253-155">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="14253-156">以下の拡張子を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14253-156">Check out the extensions below:</span></span>  

#### <span data-ttu-id="14253-157">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="14253-157">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="14253-158">Visual Studio のコード拡張 [の要素][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] を追加することによって、Visual studio コード内から要素ツールを使います。</span><span class="sxs-lookup"><span data-stu-id="14253-158">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素を使った Visual Studio コードの要素ツール" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   <span data-ttu-id="14253-160">Microsoft Edge 拡張機能の要素を使った Visual Studio コードの **要素** ツール</span><span class="sxs-lookup"><span data-stu-id="14253-160">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="14253-161">詳細については、「 [Microsoft Edge Visual Studio コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14253-161">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="14253-162">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="14253-162">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="14253-163">Microsoft Edge visual Studio コード拡張 [用デバッガー][VisualStudioMarketplaceDebuggerEdge] を使って、microsoft edge で実行されている JavaScript を Visual Studio コードから直接デバッグします。</span><span class="sxs-lookup"><span data-stu-id="14253-163">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="Visual Studio コードの Microsoft Edge 拡張機能のデバッガー" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   <span data-ttu-id="14253-165">Visual Studio コードの Microsoft Edge 拡張機能のデバッガー</span><span class="sxs-lookup"><span data-stu-id="14253-165">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="14253-166">詳細については、「 [Visual Studio コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14253-166">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="14253-167">Webhint</span><span class="sxs-lookup"><span data-stu-id="14253-167">webhint</span></span>  

<span data-ttu-id="14253-168">作成中の web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio のコードの拡張機能が使用されています。 `webhint`</span><span class="sxs-lookup"><span data-stu-id="14253-168">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="14253-169">この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。</span><span class="sxs-lookup"><span data-stu-id="14253-169">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="Visual Studio コードでの tsx ファイルの分析に関する webhint Visual Studio のコード拡張" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="14253-171">`.tsx`Visual Studio コードでのファイルの分析に関する webhint Visual Studio コードの拡張機能</span><span class="sxs-lookup"><span data-stu-id="14253-171">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="14253-172">[Visual Studio コード web ヒントの拡張機能について、詳細はこちらをご覧][WebhintVisualStudioCodeExtension]ください。</span><span class="sxs-lookup"><span data-stu-id="14253-172">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="14253-173">Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="14253-173">Visual Studio integration</span></span>  

<span data-ttu-id="14253-174">Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="14253-174">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="14253-175">この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。</span><span class="sxs-lookup"><span data-stu-id="14253-175">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio" lightbox="../../images/2020/01/vs.msft.png":::
   <span data-ttu-id="14253-177">Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14253-177">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="14253-178">[詳細については、「Visual Studio からの Microsoft Edge のデバッグ」を参照して][MicrosoftVisualStudio]ください。</span><span class="sxs-lookup"><span data-stu-id="14253-178">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="14253-179">防止コンソールのメッセージを追跡する</span><span class="sxs-lookup"><span data-stu-id="14253-179">Tracking prevention Console messages</span></span>  

<span data-ttu-id="14253-180">追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="14253-180">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="14253-181">既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14253-181">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="14253-182">特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。</span><span class="sxs-lookup"><span data-stu-id="14253-182">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   <span data-ttu-id="14253-184">予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="14253-184">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="14253-185">[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。</span><span class="sxs-lookup"><span data-stu-id="14253-185">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="14253-186">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="14253-186">Announcements from the Chromium project</span></span>  

<span data-ttu-id="14253-187">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 81 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="14253-187">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="14253-188">デバイスモードでの Moto G4 のサポート</span><span class="sxs-lookup"><span data-stu-id="14253-188">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="14253-189">[デバイスのツールバーを有効][DeviceToolbar]にした後、**デバイス**の一覧から Moto G4 のビューポートのサイズをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="14253-189">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="Moto G4 のビューポートのシミュレーション" lightbox="../../images/2020/01/motog4.msft.png":::
   <span data-ttu-id="14253-191">Moto G4 のビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="14253-191">Simulating a Moto G4 viewport</span></span>  
:::image-end:::  

<span data-ttu-id="14253-192">[ [デバイスフレームの表示][DeviceFrame] ] をクリックして、ビューポートの周りに Moto G4 のハードウェアを表示します。</span><span class="sxs-lookup"><span data-stu-id="14253-192">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="Moto G4 のハードウェアの表示" lightbox="../../images/2020/01/motog4frame.msft.png":::
   <span data-ttu-id="14253-194">Moto G4 のハードウェアの表示</span><span class="sxs-lookup"><span data-stu-id="14253-194">Showing the Moto G4 hardware</span></span>  
:::image-end:::  

<span data-ttu-id="14253-195">関連する機能:</span><span class="sxs-lookup"><span data-stu-id="14253-195">Related features:</span></span>  

*   <span data-ttu-id="14253-196">[コマンドメニュー][CommandMenu]を開き、コマンドを実行して、 `Capture screenshot` Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります ([**デバイスの表示] フレームを**有効にした後)。</span><span class="sxs-lookup"><span data-stu-id="14253-196">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="14253-197">[ネットワークと CPU を調整][ThrottleNetworkAndCpu] して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="14253-197">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="14253-198">Chromium の問題 [#924693][CR924693]</span><span class="sxs-lookup"><span data-stu-id="14253-198">Chromium issue [#924693][CR924693]</span></span>  

### <span data-ttu-id="14253-199">Cookie 関連の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="14253-199">Cookie-related updates</span></span>  

#### <span data-ttu-id="14253-200">[Cookie] ウィンドウでブロックされた cookie</span><span class="sxs-lookup"><span data-stu-id="14253-200">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="14253-201">アプリケーションパネルの [Cookie] ウィンドウに、ブロックされている cookie と黄色の背景が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14253-201">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="アプリケーションパネルの Cookie ウィンドウのブロックされた cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   <span data-ttu-id="14253-203">アプリケーションパネルの Cookie ウィンドウのブロックされた cookie</span><span class="sxs-lookup"><span data-stu-id="14253-203">Blocked cookies in the Cookies pane of the Application panel</span></span>  
:::image-end:::  

<span data-ttu-id="14253-204">Chromium の問題 [#1030258][CR1030258]</span><span class="sxs-lookup"><span data-stu-id="14253-204">Chromium issue [#1030258][CR1030258]</span></span>  <!-- inaccessible  -->  

#### <span data-ttu-id="14253-205">Cookie ウィンドウの cookie の優先度</span><span class="sxs-lookup"><span data-stu-id="14253-205">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="14253-206">[ネットワーク] および [アプリケーション] パネルの [Cookie] テーブルに、 **優先度** 列が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14253-206">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="14253-207">Chromium ベースのブラウザー (Microsoft Edge など) は、cookie の優先順位をサポートしている唯一のブラウザーです。</span><span class="sxs-lookup"><span data-stu-id="14253-207">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="14253-208">Chromium の問題 [#1026879][CR1026879]</span><span class="sxs-lookup"><span data-stu-id="14253-208">Chromium issue [#1026879][CR1026879]</span></span>  

#### <span data-ttu-id="14253-209">すべての cookie 値を編集する</span><span class="sxs-lookup"><span data-stu-id="14253-209">Edit all cookie values</span></span>  

<span data-ttu-id="14253-210">Cookie テーブル内のすべてのセルは、[ **サイズ** ] 列のセルを除いて編集できるようになりました。この列は、cookie のネットワークサイズ (バイト単位) を表しているためです。</span><span class="sxs-lookup"><span data-stu-id="14253-210">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="14253-211">各列の説明については、「 [フィールド][CookiesFields] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14253-211">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="Cookie の値を編集する" lightbox="../../images/2020/01/editcookie.msft.png":::
   <span data-ttu-id="14253-213">Cookie の値を編集する</span><span class="sxs-lookup"><span data-stu-id="14253-213">Editing a cookie value</span></span>  
:::image-end:::  

#### <span data-ttu-id="14253-214">Cookie データを含める Node.js の取得としてコピーする</span><span class="sxs-lookup"><span data-stu-id="14253-214">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="14253-215">ネットワーク要求を右クリックし、[ **Copy**  >  **コピーとして**コピー] を選択して、 `fetch` cookie データを含む式を取得 Node.js ます。</span><span class="sxs-lookup"><span data-stu-id="14253-215">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="Node.js の取り出しとしてコピーする" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   <span data-ttu-id="14253-217">Node.js の取り出しとしてコピーする</span><span class="sxs-lookup"><span data-stu-id="14253-217">Copy as Node.js fetch</span></span>  
:::image-end:::  

<span data-ttu-id="14253-218">Chromium の問題 [#1029826][CR1029826]</span><span class="sxs-lookup"><span data-stu-id="14253-218">Chromium issue [#1029826][CR1029826]</span></span>  

### <span data-ttu-id="14253-219">より正確な web アプリマニフェストアイコン</span><span class="sxs-lookup"><span data-stu-id="14253-219">More accurate web app manifest icons</span></span>  

<span data-ttu-id="14253-220">以前は、アプリケーションパネルのマニフェストウィンドウは、web アプリマニフェストのアイコンを表示するために、独自の要求を送信しました。</span><span class="sxs-lookup"><span data-stu-id="14253-220">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="14253-221">DevTools には、Microsoft Edge で使用するマニフェストアイコンとまったく同じものが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14253-221">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="[マニフェスト] ウィンドウのアイコン" lightbox="../../images/2020/01/manifesticons.msft.png":::
   <span data-ttu-id="14253-223">[マニフェスト] ウィンドウのアイコン</span><span class="sxs-lookup"><span data-stu-id="14253-223">Icons in the Manifest pane</span></span>  
:::image-end:::  

<span data-ttu-id="14253-224">Chromium の問題 [#985402][CR985402]</span><span class="sxs-lookup"><span data-stu-id="14253-224">Chromium issue [#985402][CR985402]</span></span>  

### <span data-ttu-id="14253-225">CSS コンテンツプロパティの上にマウスポインターを移動して、エスケープ解除した値を表示する</span><span class="sxs-lookup"><span data-stu-id="14253-225">Hover over CSS content properties to see unescaped values</span></span>  

<span data-ttu-id="14253-226">プロパティの値の上にマウスポインターを置くと、 `content` 値のエスケープ解除されたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14253-226">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="14253-227">たとえば、この [デモ][CSSContentDemo] では、擬似要素を調べると、 `p::after` [スタイル] ウィンドウにエスケープされた文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14253-227">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="エスケープされた文字列" lightbox="../../images/2020/01/escapedstring.msft.png":::
   <span data-ttu-id="14253-229">エスケープされた文字列</span><span class="sxs-lookup"><span data-stu-id="14253-229">The escaped string</span></span>  
:::image-end:::  

<span data-ttu-id="14253-230">値の上にマウスポインターを置くと `content` 、エスケープされていない値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14253-230">When you hover over the `content` value you see the unescaped value:</span></span>  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="エスケープされていない値" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   <span data-ttu-id="14253-232">エスケープされていない値</span><span class="sxs-lookup"><span data-stu-id="14253-232">The unescaped value</span></span>  
:::image-end:::  

### <span data-ttu-id="14253-233">本体の詳細なソースマップのエラー</span><span class="sxs-lookup"><span data-stu-id="14253-233">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="14253-234">これで、本体のマップで読み込みまたは解析に失敗した理由について、コンソールで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="14253-234">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="14253-235">以前は、問題の原因を説明せずにエラーが表示されました。</span><span class="sxs-lookup"><span data-stu-id="14253-235">Previously it just provided an error without explaining what went wrong.</span></span>  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="本体でのソースマップ読み込みエラー" lightbox="../../images/2020/01/sourcemap.msft.png":::
   <span data-ttu-id="14253-237">本体でのソースマップ読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="14253-237">A source map loading error in the Console</span></span>  
:::image-end:::  

### <span data-ttu-id="14253-238">ファイルの末尾を超えてスクロールを無効にする設定</span><span class="sxs-lookup"><span data-stu-id="14253-238">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="14253-239">[設定][Settings]を開いて、 **[設定] を無効**  >  **Sources**  >  にします。 [**ファイルの最後までスクロール**する] では、[**ソース**] パネルでファイルの末尾を超えてスクロールできる既定の UI 動作を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="14253-239">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="ファイルの最後までのスクロールを無効にする" lightbox="../../images/2020/01/settings.msft.png":::
   <span data-ttu-id="14253-241">[設定] で [ **ファイルの最後までスクロールを許可する** ] を無効にする</span><span class="sxs-lookup"><span data-stu-id="14253-241">Disabling **Allow scrolling past end of file** in Settings</span></span>  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   <span data-ttu-id="14253-243">ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました</span><span class="sxs-lookup"><span data-stu-id="14253-243">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
:::image-end:::  

## <span data-ttu-id="14253-244">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="14253-244">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="14253-245">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="14253-245">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="14253-246">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="14253-246">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="14253-247">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="14253-247">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイルビューポートをシミュレートする Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートする |Microsoft ドキュメント"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "デバイスの表示フレーム-Microsoft Edge DevTools のデバイスモードでモバイルデバイスをシミュレートします。Microsoft ドキュメント"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "Microsoft Edge DevTools でネットワークと CPU を調整し、デバイスモードでモバイルデバイスをシミュレートします。Microsoft ドキュメント"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft ドキュメント"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "フィールド-Microsoft Edge DevTools を使って cookie の表示、編集、削除を行うMicrosoft ドキュメント"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio コード拡張用デバッガー"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio コード拡張の要素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  

[CR924693]: https://crbug.com/924693 "機能の要求: Moto G4 をデバイスモードリストに追加する |Chromium のバグ"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |Chromium のバグ"  
[CR1026879]: https://crbug.com/1026879 "Dev 本体の [Cookie] タブに [優先度] が表示されなくなりました |Chromium のバグ"  
[CR1029826]: https://crbug.com/1029826 "[ネットワーク] タブ-> 右クリックしてコピーを要求-> のコピーでは、フェッチでは cookie はコピー > ません。Chromium のバグ"  
[CR985402]: https://crbug.com/985402 "web アプリマニフェストアイコンのエラー文字列がわかりにくくなります。Chromium のバグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG に準拠していません |Chromium のバグ"  
[CR941561]: https://crbug.com/941561 "DevTools のローカライズ可能性 |Chromium のバグ"  
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromium のバグ"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープ解除した CSS コンテンツのデモ"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  

[Webhint]: https://aka.ms/webhint "web ヒント"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio のコード拡張 |webhint に関するドキュメント"  

> [!NOTE]
> <span data-ttu-id="14253-284">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="14253-284">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="14253-285">元のページは [ここ](https://developers.google.com/web/updates/2020/01/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="14253-285">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="14253-287">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="14253-287">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  