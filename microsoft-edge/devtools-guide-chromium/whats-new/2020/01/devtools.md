---
description: 3D ビュー、Visual Studio Microsoft Edge との統合など。
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 204a596e2497415eefeeb8aa819106635ff30caa
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408361"
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
# <a name="whats-new-in-devtools-microsoft-edge-81"></a><span data-ttu-id="48a82-104">DevTools の新機能 (Microsoft Edge 81)</span><span class="sxs-lookup"><span data-stu-id="48a82-104">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="48a82-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="48a82-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="48a82-106">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="48a82-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="48a82-107">DevTools、Microsoft コード拡張機能、その他の新機能を試Visual Studioお知らせをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="48a82-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="48a82-108">開発者ツールのすべての最新および最大の機能を最新の情報に更新するには [、Microsoft Edge][MicrosoftEdgePreviewChannels] プレビュー チャネルをダウンロードし [、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。</span><span class="sxs-lookup"><span data-stu-id="48a82-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="accessibility-improvements-to-the-devtools"></a><span data-ttu-id="48a82-109">DevTools のアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="48a82-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="48a82-110">DevTools チームは、DevTools で影響の大きなカラー コントラスト、キーボード、スクリーン リーダーの問題に対処するために、クロムに対して 170 の変更を提供しました。</span><span class="sxs-lookup"><span data-stu-id="48a82-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="48a82-111">Web を構築する開発者は、すべての開発者が DevTools を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="48a82-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="キーボード ナビゲーションとスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="48a82-113">キーボード **ナビゲーション** とスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="48a82-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-114">すべてのユーザーが Web ページにアクセス可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48a82-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="48a82-115">Microsoft Edge [のアクセシビリティインサイト][AccessibilityInsights] と [webhint][WebhintBrowserExtension] 拡張機能をダウンロードして、開始します。</span><span class="sxs-lookup"><span data-stu-id="48a82-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="48a82-116">スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合は[][PostTweetEdgeDevTools]、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコンを選択してフィードバック[を送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。</span><span class="sxs-lookup"><span data-stu-id="48a82-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="48a82-117">クロムの問題 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="48a82-117">Chromium issue [#963183][CR963183]</span></span>  

### <a name="using-the-devtools-in-other-languages"></a><span data-ttu-id="48a82-118">DevTools を他の言語で使用する</span><span class="sxs-lookup"><span data-stu-id="48a82-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="48a82-119">多くの開発者は、英語ではなく、母国語で StackOverflow や Visual Studio コードなどの他の開発者ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="48a82-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="48a82-120">英語以外の 10 か国語で使用できる DevTools のローカライズをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="48a82-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="48a82-121">中国語 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="48a82-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="48a82-122">中国語 \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="48a82-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="48a82-123">フランス語 – フランス語&#231;ais</span><span class="sxs-lookup"><span data-stu-id="48a82-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="48a82-124">ドイツ語 - deutsch</span><span class="sxs-lookup"><span data-stu-id="48a82-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="48a82-125">イタリア語 - イタリア語</span><span class="sxs-lookup"><span data-stu-id="48a82-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="48a82-126">日本語 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="48a82-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="48a82-127">韓国語 - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="48a82-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="48a82-128">ポルトガル語 - portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="48a82-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="48a82-129">ロシア語 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="48a82-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="48a82-130">スペイン語 - espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="48a82-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="48a82-131">DevTools は、Microsoft Edge で使用する言語と自動的に一致します `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="48a82-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="48a82-132">Microsoft Edge を 1 つの言語で使用し、DevTools を英語のままにする場合は `F1` 、DevTools[][Settings]で [設定] を開き、ブラウザー言語の一致を**無効**にします。</span><span class="sxs-lookup"><span data-stu-id="48a82-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, select `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   <span data-ttu-id="48a82-134">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="48a82-134">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-135">**コンソール** メッセージはローカライズされません。</span><span class="sxs-lookup"><span data-stu-id="48a82-135">**Console** messages are not localized.</span></span>  <span data-ttu-id="48a82-136">DevTools UI で使用される文字列だけが、Microsoft Edge で使用する言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-136">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="48a82-137">DevTools を使用可能な言語とは異なる言語で使用する場合は、ツイートするか、[[][PostTweetEdgeDevTools]フィードバックの送信][アイコンを選択](#getting-in-touch-with-microsoft-edge-devtools-team)します。</span><span class="sxs-lookup"><span data-stu-id="48a82-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or choose the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="48a82-138">クロムの問題 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="48a82-138">Chromium issue [#941561][CR941561]</span></span>  

### <a name="webhint-microsoft-edge-extension"></a><span data-ttu-id="48a82-139">webhint Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="48a82-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="48a82-140">Webhint Microsoft Edge 拡張機能を使用すると、Web ページを簡単にスキャンし、DevTools 内のアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどについてフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="48a82-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="48a82-141">詳細については、 を参照してください [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="48a82-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   <span data-ttu-id="48a82-143">**Webhint**ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール</span><span class="sxs-lookup"><span data-stu-id="48a82-143">The **Hints** tool in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-144">[Microsoft Edge で webhint ブラウザー拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="48a82-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="48a82-145">拡張機能をインストールしたら、DevTools を開き、ヒント ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="48a82-145">Once you install the extension, open the DevTools and choose the **Hints** tool.</span></span>  <span data-ttu-id="48a82-146">ここから、カスタマイズ可能なサイト スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="48a82-146">From here, run a customizable site scan.</span></span>  <span data-ttu-id="48a82-147">詳細 [については、webhint.io][WebhintBrowserExtension] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a82-147">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <a name="3d-view"></a><span data-ttu-id="48a82-148">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="48a82-148">3D View</span></span>  

<span data-ttu-id="48a82-149">**3D ビューを使用**して、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して、Web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="48a82-149">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools の 3D ビュー" lightbox="../../images/2020/01/3dview.msft.png":::
   <span data-ttu-id="48a82-151">DevTools の 3D ビュー</span><span class="sxs-lookup"><span data-stu-id="48a82-151">The 3D View in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-152">3D ビューにアクセスするには、[3D ビュー] と入力し `Ctrl`  +  `Shift`  +  `P` **、[3D ビュー**の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="48a82-152">To access the 3D View, select `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="48a82-153">Microsoft Edge チームは、UI でクロム チームと作業を行い、3D ビューにさらに機能を追加していますので、フィードバックをお寄 [せください](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="48a82-153">The Microsoft Edge team is working with the Chromium team on the UI and adding more functionality to the 3D View, so please send your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="48a82-154">クロムの問題 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="48a82-154">Chromium issue [#987787][CR987787]</span></span>  

### <a name="visual-studio-code-extensions"></a><span data-ttu-id="48a82-155">Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="48a82-155">Visual Studio Code extensions</span></span>  

<span data-ttu-id="48a82-156">DevTools チームは、テキスト エディターから [直接 devTools][VisualStudioCode] の機能を使用できる Visual Studio コードの拡張機能もいくつかリリースしました。</span><span class="sxs-lookup"><span data-stu-id="48a82-156">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="48a82-157">以下の拡張機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="48a82-157">Check out the extensions below:</span></span>  

#### <a name="elements-for-microsoft-edge"></a><span data-ttu-id="48a82-158">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="48a82-158">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="48a82-159">Microsoft Edge 用の要素 [\(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studioコード拡張機能を追加して、コード内の Elements ツールVisual Studio使用します。</span><span class="sxs-lookup"><span data-stu-id="48a82-159">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="Microsoft Edge 拡張機能の要素Visual Studioコードの要素ツール" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   <span data-ttu-id="48a82-161">Microsoft  Edge 拡張機能の要素Visual Studioコードの要素ツール</span><span class="sxs-lookup"><span data-stu-id="48a82-161">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-162">詳細については [、「Elements for Microsoft Edge Visual Studio コード拡張機能」を参照してください][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="48a82-162">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <a name="debugger-for-microsoft-edge"></a><span data-ttu-id="48a82-163">Microsoft Edge のデバッガー</span><span class="sxs-lookup"><span data-stu-id="48a82-163">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="48a82-164">デバッガー for [Microsoft Edge Visual Studio][VisualStudioMarketplaceDebuggerEdge] コード拡張機能を使用して、Microsoft Edge で実行されている JavaScript をコードから直接Visual Studioします。</span><span class="sxs-lookup"><span data-stu-id="48a82-164">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="コード内の Microsoft Edge 拡張機能のデバッガー Visual Studioします。" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   <span data-ttu-id="48a82-166">コード内の Microsoft Edge 拡張機能のデバッガー Visual Studioします。</span><span class="sxs-lookup"><span data-stu-id="48a82-166">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-167">詳細については、「Microsoft Edge をコードからデバッグする方法」 [をVisual Studioしてください][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="48a82-167">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <a name="webhint"></a><span data-ttu-id="48a82-168">Webhint</span><span class="sxs-lookup"><span data-stu-id="48a82-168">webhint</span></span>  

<span data-ttu-id="48a82-169">[Webhint Visual Studio][VisualStudioMarketplaceWebhintExtension]コード拡張機能は、Web ページの作成中に Web ページを `webhint` 改善するために使用します。</span><span class="sxs-lookup"><span data-stu-id="48a82-169">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you are writing it.</span></span>  <span data-ttu-id="48a82-170">この拡張機能は、分析に基づいてワークスペース ファイルで診断を実行してレポート `webhint` します。</span><span class="sxs-lookup"><span data-stu-id="48a82-170">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="webhint Visual Studioコード内の .tsx ファイルを分析する Code Visual Studio拡張機能" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="48a82-172">webhint Visual Studio コード拡張機能でファイルを分析する Visual Studio `.tsx` Code</span><span class="sxs-lookup"><span data-stu-id="48a82-172">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-173">[コード webhint 拡張機能Visual Studio詳細については、以下を参照してください][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="48a82-173">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <a name="visual-studio-integration"></a><span data-ttu-id="48a82-174">Visual Studio統合</span><span class="sxs-lookup"><span data-stu-id="48a82-174">Visual Studio integration</span></span>  

<span data-ttu-id="48a82-175">2019 Visual Studio 16.2 以降では、Microsoft Edge で実行されている JavaScript をデバッグVisual Studioデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="48a82-175">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="48a82-176">[2019 Visual Studioダウンロードして][MicrosoftVisualStudioDownloads] 、この機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="48a82-176">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Visual Studio Microsoft Edge Canary、Dev、または Beta で Web アプリを起動するオプションを使用します。" lightbox="../../images/2020/01/vs.msft.png":::
   <span data-ttu-id="48a82-178">Visual Studio Microsoft Edge Canary、Dev、または Beta で Web アプリを起動するオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="48a82-178">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-179">[Microsoft Edge のデバッグの詳細については、Visual Studio。][MicrosoftVisualStudio]</span><span class="sxs-lookup"><span data-stu-id="48a82-179">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <a name="tracking-prevention-console-messages"></a><span data-ttu-id="48a82-180">追跡防止コンソール メッセージ</span><span class="sxs-lookup"><span data-stu-id="48a82-180">Tracking prevention Console messages</span></span>  

<span data-ttu-id="48a82-181">追跡防止は、以前にアクセスしたことがない Web サイトによって追跡されるのを防く Microsoft Edge の固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="48a82-181">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you have not visited before.</span></span>  <span data-ttu-id="48a82-182">既定の追跡防止設定はバランス モードで、プライバシーと Web の互換性のバランスを取るエクスペリエンスのために、サードパーティのトラッカーと既知の悪意のあるトラッカーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="48a82-182">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="48a82-183">特定のトラッカーがブロックされている場合の Web ページの互換性に関する詳細な分析情報を提供するために、トラッカーがブロック されているときに警告メッセージがコンソールに追加されました。</span><span class="sxs-lookup"><span data-stu-id="48a82-183">To give you more insight into the compatibility of your web page when certain trackers are blocked, warning messages were added in the **Console** when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="追跡防止がトラッカーのストレージへのアクセスをブロックする場合のコンソール内のメッセージ" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   <span data-ttu-id="48a82-185">追跡防止が **トラッカーのストレージ** へのアクセスをブロックする場合のコンソール内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="48a82-185">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-186">[追跡防止とプライバシーと Web の互換性のバランスについて詳しくは、以下をご覧ください][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="48a82-186">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="48a82-187">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="48a82-187">Announcements from the Chromium project</span></span>  

<span data-ttu-id="48a82-188">次のセクションでは、オープン ソースのクロム プロジェクトに貢献した Microsoft Edge 81 で利用できる追加機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="48a82-188">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <a name="moto-g4-support-in-device-mode"></a><span data-ttu-id="48a82-189">デバイス モードでの Moto G4 のサポート</span><span class="sxs-lookup"><span data-stu-id="48a82-189">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="48a82-190">デバイス [ツールバーを有効にした][DeviceToolbar]後、デバイス リストから Moto G4 ビューポートの寸法を **シミュレート** します。</span><span class="sxs-lookup"><span data-stu-id="48a82-190">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="Moto G4 ビューポートのシミュレーション" lightbox="../../images/2020/01/motog4.msft.png":::
   <span data-ttu-id="48a82-192">Moto G4 ビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="48a82-192">Simulating a Moto G4 viewport</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-193">[ [デバイス フレームの表示] を][DeviceFrame] 選択して、ビューポートの周囲に Moto G4 ハードウェアを表示します。</span><span class="sxs-lookup"><span data-stu-id="48a82-193">Choose [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="Moto G4 ハードウェアの表示" lightbox="../../images/2020/01/motog4frame.msft.png":::
   <span data-ttu-id="48a82-195">Moto G4 ハードウェアの表示</span><span class="sxs-lookup"><span data-stu-id="48a82-195">Showing the Moto G4 hardware</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-196">関連する機能:</span><span class="sxs-lookup"><span data-stu-id="48a82-196">Related features:</span></span>  

*   <span data-ttu-id="48a82-197">コマンド メニュー [を開き][CommandMenu] 、コマンドを実行 `Capture screenshot` して、Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります (デバイス フレームの表示を **有効**にした後)。</span><span class="sxs-lookup"><span data-stu-id="48a82-197">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="48a82-198">[ネットワークと CPU を調整して][ThrottleNetworkAndCpu] 、モバイル ユーザーの Web ブラウズ条件をより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="48a82-198">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="48a82-199">クロムの問題 [#924693][CR924693]</span><span class="sxs-lookup"><span data-stu-id="48a82-199">Chromium issue [#924693][CR924693]</span></span>  

### <a name="cookie-related-updates"></a><span data-ttu-id="48a82-200">Cookie 関連の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="48a82-200">Cookie-related updates</span></span>  

#### <a name="blocked-cookies-in-the-cookies-pane"></a><span data-ttu-id="48a82-201">[Cookie] ウィンドウのブロックされた Cookie</span><span class="sxs-lookup"><span data-stu-id="48a82-201">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="48a82-202">[アプリケーション] パネルの [Cookie] ウィンドウに、ブロックされた Cookie が黄色の背景で表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-202">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="[アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   <span data-ttu-id="48a82-204">[アプリケーション] パネルの [Cookie] ウィンドウでブロックされた Cookie</span><span class="sxs-lookup"><span data-stu-id="48a82-204">Blocked cookies in the Cookies pane of the Application panel</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-205">クロムの問題 [#1030258][CR1030258]</span><span class="sxs-lookup"><span data-stu-id="48a82-205">Chromium issue [#1030258][CR1030258]</span></span>  <!-- inaccessible  -->  

#### <a name="cookie-priority-in-the-cookie-pane"></a><span data-ttu-id="48a82-206">Cookie ウィンドウの Cookie の優先度</span><span class="sxs-lookup"><span data-stu-id="48a82-206">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="48a82-207">[ネットワーク] ツールと [アプリケーション] ツール**の** **Cookie**テーブルに [優先度] 列**が含**まれる。</span><span class="sxs-lookup"><span data-stu-id="48a82-207">The Cookies tables in the **Network** and **Application** tools now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="48a82-208">クロム ベースのブラウザー (Microsoft Edge など) は、Cookie の優先度をサポートする唯一のブラウザーです。</span><span class="sxs-lookup"><span data-stu-id="48a82-208">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="48a82-209">クロムの問題 [#1026879][CR1026879]</span><span class="sxs-lookup"><span data-stu-id="48a82-209">Chromium issue [#1026879][CR1026879]</span></span>  

#### <a name="edit-all-cookie-values"></a><span data-ttu-id="48a82-210">すべての Cookie 値を編集する</span><span class="sxs-lookup"><span data-stu-id="48a82-210">Edit all cookie values</span></span>  

<span data-ttu-id="48a82-211">Cookie テーブル内のすべてのセルは、サイズ列のセルを除いて 編集可能になります。この列は Cookie のネットワーク サイズをバイト単位で表します。</span><span class="sxs-lookup"><span data-stu-id="48a82-211">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="48a82-212">各列の説明については、[フィールド] に [移動します][CookiesFields]。</span><span class="sxs-lookup"><span data-stu-id="48a82-212">For an explanation of each column, navigate to [Fields][CookiesFields].</span></span>  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="Cookie 値の編集" lightbox="../../images/2020/01/editcookie.msft.png":::
   <span data-ttu-id="48a82-214">Cookie 値の編集</span><span class="sxs-lookup"><span data-stu-id="48a82-214">Editing a cookie value</span></span>  
:::image-end:::  

#### <a name="copy-as-nodejs-fetch-to-include-cookie-data"></a><span data-ttu-id="48a82-215">Cookie データをNode.jsフェッチとしてコピーする</span><span class="sxs-lookup"><span data-stu-id="48a82-215">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="48a82-216">Cookie データを含む式を取得するには、ネットワーク要求にポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[コピーをフェッチとしてコピー] をNode.js `fetch`   >  **します**。</span><span class="sxs-lookup"><span data-stu-id="48a82-216">To get a `fetch` expression that includes cookie data, hover on a network request, open the contextual menu \(right-click\), and choose **Copy** > **Copy as Node.js fetch**.</span></span>  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="フェッチとしてNode.jsする" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   <span data-ttu-id="48a82-218">フェッチとしてNode.jsする</span><span class="sxs-lookup"><span data-stu-id="48a82-218">Copy as Node.js fetch</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-219">クロムの問題 [#1029826][CR1029826]</span><span class="sxs-lookup"><span data-stu-id="48a82-219">Chromium issue [#1029826][CR1029826]</span></span>  

### <a name="more-accurate-web-app-manifest-icons"></a><span data-ttu-id="48a82-220">より正確な Web アプリ マニフェスト アイコン</span><span class="sxs-lookup"><span data-stu-id="48a82-220">More accurate web app manifest icons</span></span>  

<span data-ttu-id="48a82-221">以前は、[アプリケーション] パネルの [マニフェスト] ウィンドウから、Web アプリ マニフェスト アイコンを表示するために独自の要求が送信されました。</span><span class="sxs-lookup"><span data-stu-id="48a82-221">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="48a82-222">DevTools には、Microsoft Edge で使用されるマニフェスト アイコンとまったく同じアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-222">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="[マニフェスト] ウィンドウのアイコン" lightbox="../../images/2020/01/manifesticons.msft.png":::
   <span data-ttu-id="48a82-224">[マニフェスト] ウィンドウのアイコン</span><span class="sxs-lookup"><span data-stu-id="48a82-224">Icons in the Manifest pane</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-225">クロムの問題 [#985402][CR985402]</span><span class="sxs-lookup"><span data-stu-id="48a82-225">Chromium issue [#985402][CR985402]</span></span>  

### <a name="hover-on-css-content-properties-to-display-unescaped-values"></a><span data-ttu-id="48a82-226">CSS コンテンツ プロパティにカーソルを合わせると、エスケープされていない値が表示されます</span><span class="sxs-lookup"><span data-stu-id="48a82-226">Hover on CSS content properties to display unescaped values</span></span>  

<span data-ttu-id="48a82-227">プロパティの値にカーソルを合 `content` わせると、エスケープされていないバージョンの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-227">Hover on the value of a `content` property to display the unescaped version of the value.</span></span>  

<span data-ttu-id="48a82-228">たとえば、 [このデモでは][CSSContentDemo] 、擬似要素を検査すると、エスケープされた文字列が [スタイル] `p::after` ウィンドウに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-228">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element an escaped string is displayed in the **Styles** pane:</span></span>  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="エスケープされた文字列" lightbox="../../images/2020/01/escapedstring.msft.png":::
   <span data-ttu-id="48a82-230">エスケープされた文字列</span><span class="sxs-lookup"><span data-stu-id="48a82-230">The escaped string</span></span>  
:::image-end:::  

<span data-ttu-id="48a82-231">値にカーソルを合 `content` わせると、エスケープされていない値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-231">When you hover on the `content` value, the unescaped value is displayed.</span></span>  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="エスケープされていない値" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   <span data-ttu-id="48a82-233">エスケープされていない値</span><span class="sxs-lookup"><span data-stu-id="48a82-233">The unescaped value</span></span>  
:::image-end:::  

### <a name="more-detailed-source-map-errors-in-the-console"></a><span data-ttu-id="48a82-234">コンソールのソース マップエラーの詳細</span><span class="sxs-lookup"><span data-stu-id="48a82-234">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="48a82-235">コンソールでは、ソース マップの読み込みまたは解析に失敗した理由の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-235">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="48a82-236">以前は、何が間違っていたのかを説明せずにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="48a82-236">Previously it just provided an error without explaining what went wrong.</span></span>  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="コンソールでのソース マップの読み込みエラー" lightbox="../../images/2020/01/sourcemap.msft.png":::
   <span data-ttu-id="48a82-238">コンソールでのソース マップの読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="48a82-238">A source map loading error in the Console</span></span>  
:::image-end:::  

### <a name="setting-for-disabling-scrolling-past-the-end-of-a-file"></a><span data-ttu-id="48a82-239">ファイルの末尾を過ぎたスクロールを無効にする設定</span><span class="sxs-lookup"><span data-stu-id="48a82-239">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="48a82-240">[[設定]][Settings]を 開き、[基本設定のソース] を無効にする ファイルの末尾をスクロールし、[ソース] パネルでファイルの最後までスクロールできる既定の UI 動作を無効にします  >    >  。 </span><span class="sxs-lookup"><span data-stu-id="48a82-240">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="[ファイルの最後までスクロールを許可する] を無効にする" lightbox="../../images/2020/01/settings.msft.png":::
   <span data-ttu-id="48a82-242">[設定] **でファイルの末尾をスクロールするを許可するを** 無効にする</span><span class="sxs-lookup"><span data-stu-id="48a82-242">Disabling **Allow scrolling past end of file** in Settings</span></span>  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   <span data-ttu-id="48a82-244">ファイルの末尾をスクロールすると、[ソース] パネルで無効になりました</span><span class="sxs-lookup"><span data-stu-id="48a82-244">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="48a82-245">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="48a82-245">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="48a82-246">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="48a82-246">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="48a82-247">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="48a82-247">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="48a82-248">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="48a82-248">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートのシミュレート - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "デバイス フレームの表示 - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行|Microsoft Docs"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "ネットワークと CPU の調整 - Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Docs"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft Docs"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "Fields - Microsoft Edge DevTools を使用して Cookie を表示、編集、および削除|Microsoft Docs"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge コード拡張機能Visual Studioデバッガー"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge のコード拡張機能Visual Studio要素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー - Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) の要素 - Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿での追跡防止の改善"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows Visual Studio Mac 用 2019 &ダウンロード"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  

[CR924693]: https://crbug.com/924693 "機能要求: デバイス モード リストに Moto G4 を追加|クロム バグ"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |クロム バグ"  
[CR1026879]: https://crbug.com/1026879 "開発コンソールの [Cookie] タブに優先度が表示|クロム バグ"  
[CR1029826]: https://crbug.com/1029826 "ネットワーク タブ ->フェッチでは cookie がコピーされないので、> コピー -> コピーを要求するを選択|クロム バグ"  
[CR985402]: https://crbug.com/985402 "Web アプリ マニフェスト アイコンのエラー文字列は、わかりにくい|クロム バグ"  
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|クロム バグ"  
[CR941561]: https://crbug.com/941561 "DevTools ファイルのローカライズ|クロム バグ"  
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |クロム バグ"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープされていない CSS コンテンツのデモ"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - Microsoft Docs/Edge Developer"  

[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティインサイト"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  

[Webhint]: https://aka.ms/webhint "webhint"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint Browser Extension |webhint のドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio コード拡張機能 |webhint のドキュメント"  

> [!NOTE]
> <span data-ttu-id="48a82-285">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="48a82-285">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="48a82-286">元のページは [ここ](https://developers.google.com/web/updates/2020/01/devtools/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="48a82-286">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="48a82-288">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="48a82-288">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  