---
description: アクセシビリティの向上、他の言語での DevTools の使用など。
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1388cbf62bd341837d92c51ad137f3909e60e476
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514397"
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
# <a name="whats-new-in-devtools-microsoft-edge-80"></a><span data-ttu-id="12081-104">DevTools の新機能 (Microsoft Edge 80)</span><span class="sxs-lookup"><span data-stu-id="12081-104">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="12081-105">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="12081-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="12081-106">以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="12081-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="12081-107">DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12081-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="12081-108">開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。</span><span class="sxs-lookup"><span data-stu-id="12081-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="accessibility-improvements-to-the-devtools"></a><span data-ttu-id="12081-109">DevTools のアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="12081-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="12081-110">DevTools チームは、devTools で影響の大きなカラー コントラスト、キーボード、スクリーン リーダーの問題に対処するために、Chromium に 170 の変更を提供しました。</span><span class="sxs-lookup"><span data-stu-id="12081-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="12081-111">Web を構築する開発者は、すべての開発者が DevTools を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="12081-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="キーボード ナビゲーションとスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="12081-113">キーボード **ナビゲーション** とスクリーン リーダーの機能強化を備え、DevTools のパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="12081-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="12081-114">すべてのユーザーが Web ページにアクセス可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12081-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="12081-115">アクセシビリティインサイト[と][AccessibilityInsights] [webhint][WebhintBrowserExtension]拡張機能をダウンロードして、Microsoft Edgeを開始します。</span><span class="sxs-lookup"><span data-stu-id="12081-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="12081-116">スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合[][PostTweetEdgeDevTools]は、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコン[を選択してフィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。</span><span class="sxs-lookup"><span data-stu-id="12081-116">If you use screen readers or the keyboard to navigate around the DevTools, send your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="12081-117">Chromium[の問題][CR963183]#963183</span><span class="sxs-lookup"><span data-stu-id="12081-117">Chromium issue [#963183][CR963183]</span></span>  

### <a name="using-the-devtools-in-other-languages"></a><span data-ttu-id="12081-118">DevTools を他の言語で使用する</span><span class="sxs-lookup"><span data-stu-id="12081-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="12081-119">多くの開発者は、英語ではなく、母国語で StackOverflow や Visual Studio Codeなどの他の開発者ツールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="12081-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="12081-120">英語以外の 10 か国語で使用できる DevTools のローカライズをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="12081-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="12081-121">中国語 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="12081-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12081-122">中国語 \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="12081-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="12081-123">フランス語 – フランス語&#231;ais</span><span class="sxs-lookup"><span data-stu-id="12081-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12081-124">ドイツ語 - deutsch</span><span class="sxs-lookup"><span data-stu-id="12081-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="12081-125">イタリア語 - イタリア語</span><span class="sxs-lookup"><span data-stu-id="12081-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12081-126">日本語 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="12081-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="12081-127">韓国語 - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="12081-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12081-128">ポルトガル語 - portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="12081-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="12081-129">ロシア語 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="12081-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="12081-130">スペイン語 - espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="12081-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="12081-131">[ローカライズされた `edge://flags` 開発者ツールを有効 **にする] フラグに移動し、[** 有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="12081-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="12081-132">また、[開発者ツールの **実験] フラグを [** 有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="12081-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="12081-133">再起動Microsoft Edge DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="12081-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Select `F1` in the DevTools or navigate to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="12081-134">DevTools は、 で使用する言語とMicrosoft Edge一致します `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="12081-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="ドイツ語の DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   <span data-ttu-id="12081-136">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="12081-136">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="12081-137">DevTools を使用可能な言語とは異なる言語で使用する場合は、ツイートするか、[[][PostTweetEdgeDevTools]フィードバックの送信][アイコンを選択](#getting-in-touch-with-microsoft-edge-devtools-team)します。</span><span class="sxs-lookup"><span data-stu-id="12081-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or choose the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="12081-138">Chromium[の問題][CR941561]#941561</span><span class="sxs-lookup"><span data-stu-id="12081-138">Chromium issue [#941561][CR941561]</span></span>  

### <a name="webhint-microsoft-edge-extension"></a><span data-ttu-id="12081-139">webhint Microsoft Edge拡張子</span><span class="sxs-lookup"><span data-stu-id="12081-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="12081-140">webhint Microsoft Edge拡張機能を使用すると、Web ページを簡単にスキャンし、DevTools 内のアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどについてフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="12081-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="12081-141">詳細については、 を参照してください [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="12081-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="Webhint ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   <span data-ttu-id="12081-143">**Webhint**ブラウザー拡張機能がインストールされている場合の DevTools のヒント ツール</span><span class="sxs-lookup"><span data-stu-id="12081-143">The **Hints** tool in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="12081-144">[webhint ブラウザー拡張機能を試Microsoft Edge。][MicrosoftEdgeInsiderAddons]</span><span class="sxs-lookup"><span data-stu-id="12081-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="12081-145">拡張機能をインストールしたら、DevTools を開き、ヒント ツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="12081-145">Once you install the extension, open the DevTools and choose the **Hints** tool.</span></span>  <span data-ttu-id="12081-146">ここから、カスタマイズ可能なサイト スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="12081-146">From here, run a customizable site scan.</span></span>  <span data-ttu-id="12081-147">詳細 [については、webhint.io][WebhintBrowserExtension] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12081-147">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <a name="3d-view"></a><span data-ttu-id="12081-148">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="12081-148">3D View</span></span>  

<span data-ttu-id="12081-149">**3D ビューを使用**して、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z-index][MDNZIndex]スタック コンテキストを移動して、Web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="12081-149">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools の 3D ビュー" lightbox="../../images/2019/12/3dview.msft.png":::
   <span data-ttu-id="12081-151">DevTools **の 3D** ビュー</span><span class="sxs-lookup"><span data-stu-id="12081-151">The **3D View** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="12081-152">3D ビューにアクセスするには、[開発者ツールの実験] フラグが [有効] に設定されています `edge://flags` 。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12081-152">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="12081-153">再起動Microsoft Edge DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="12081-153">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="12081-154">`F1`[DevTools] で選択するか、[テスト設定]**セクション**を開き、[3D ビューを有効にする  >  \*\*\*\*]**チェック ボックスをオン**にします。</span><span class="sxs-lookup"><span data-stu-id="12081-154">Select `F1` in the DevTools or open the **Settings** > **Experiments** section, and turn on the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="12081-155">次に `Ctrl`  +  `Shift`  +  `P` **、[3D**ビュー] と入力し **、[3D ビューの表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="12081-155">Now, select `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="12081-156">UI に取り組み、3D ビューに機能を追加していますので、フィードバックをお寄 [せください](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="12081-156">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="12081-157">Chromium[問題#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="12081-157">Chromium issue [#987787][CR987787]</span></span>

### <a name="visual-studio-code-extensions"></a><span data-ttu-id="12081-158">Visual Studio Code拡張機能</span><span class="sxs-lookup"><span data-stu-id="12081-158">Visual Studio Code extensions</span></span>  

<span data-ttu-id="12081-159">DevTools チームは、テキスト エディター Visual Studio Code [][VisualStudioCode] DevTools の機能を直接使用できる拡張機能をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="12081-159">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor.</span></span> <span data-ttu-id="12081-160">次の拡張機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="12081-160">Check out the following extensions.</span></span>  

#### <a name="elements-for-microsoft-edge"></a><span data-ttu-id="12081-161">ユーザーの要素Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="12081-161">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="12081-162">拡張機能 (Visual Studio Code) の要素を追加して、Microsoft Edge[内ChromiumツールVisual Studio Code][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]します。</span><span class="sxs-lookup"><span data-stu-id="12081-162">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge (Chromium)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="拡張機能の要素を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   <span data-ttu-id="12081-164">拡張機能**の要素**を使用Visual Studio Code内の Elements ツールMicrosoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="12081-164">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="12081-165">詳細については、「Elements for [Microsoft Edge Visual Studio Code」を参照してください][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="12081-165">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <a name="debugger-for-microsoft-edge"></a><span data-ttu-id="12081-166">デバッガーのMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="12081-166">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="12081-167">デバッガーを[使用して、Microsoft Edge Visual Studio Code][VisualStudioMarketplaceDebuggerEdge]で実行されている JavaScript をデバッグし、Microsoft Edgeから直接実行Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="12081-167">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="デバッガー内の Microsoft Edge拡張機能Visual Studio Code" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   <span data-ttu-id="12081-169">デバッガー内の Microsoft Edge拡張機能Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="12081-169">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="12081-170">詳細については、「デバッグ方法」を[参照Microsoft Edgeを参照Visual Studio Code。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="12081-170">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <a name="webhint"></a><span data-ttu-id="12081-171">Webhint</span><span class="sxs-lookup"><span data-stu-id="12081-171">webhint</span></span>  

<span data-ttu-id="12081-172">[webhint Visual Studio Code][VisualStudioMarketplaceWebhintExtension]は、Web ページの作成中に Web ページを改善 `webhint` するために使用します。</span><span class="sxs-lookup"><span data-stu-id="12081-172">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="12081-173">この拡張機能は、分析に基づいてワークスペース ファイルで診断を実行してレポート `webhint` します。</span><span class="sxs-lookup"><span data-stu-id="12081-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="webhint Visual Studio Codeで .tsx ファイルを分析する拡張機能Visual Studio Code" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="12081-175">webhint Visual Studio Codeファイルを分析する拡張機能 `.tsx` Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="12081-175">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="12081-176">[webhint 拡張機能のVisual Studio Code詳細を参照してください][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="12081-176">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <a name="visual-studio-integration"></a><span data-ttu-id="12081-177">Visual Studio統合</span><span class="sxs-lookup"><span data-stu-id="12081-177">Visual Studio integration</span></span>  

<span data-ttu-id="12081-178">2019 Visual Studio 16.2 以降では、Visual Studio デバッガーを使用して、Microsoft Edge で実行されている JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="12081-178">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="12081-179">[2019 Visual Studioダウンロード][MicrosoftVisualStudioDownloads]して、この機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="12081-179">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out.</span></span>  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。" lightbox="../../images/2019/12/vs.msft.png":::
   <span data-ttu-id="12081-181">Visual Studio、開発、またはベータ版で Web アプリを起動するMicrosoft Edgeオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="12081-181">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="12081-182">[ブログの投稿を読んで、ブログ記事からMicrosoft EdgeをVisual Studio。][MicrosoftVisualStudioBlogDebugJavascript]</span><span class="sxs-lookup"><span data-stu-id="12081-182">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <a name="tracking-prevention-console-messages"></a><span data-ttu-id="12081-183">追跡防止コンソール メッセージ</span><span class="sxs-lookup"><span data-stu-id="12081-183">Tracking prevention Console messages</span></span>  

<span data-ttu-id="12081-184">追跡防止は、Web サイトをMicrosoft Edgeする前に Web サイトで追跡されるのをブロックする、サイト内の一意の機能です。</span><span class="sxs-lookup"><span data-stu-id="12081-184">Tracking prevention is a unique feature in Microsoft Edge that blocks you from being tracked by a website before you visited it.</span></span>  <span data-ttu-id="12081-185">既定の追跡防止設定はバランス モードで、プライバシーと Web の互換性のバランスを取るエクスペリエンスのために、サードパーティのトラッカーと既知の悪意のあるトラッカーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="12081-185">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="12081-186">特定のトラッカーがブロックされている場合の Web ページの互換性に関する詳細な分析情報を提供するために、Microsoft Edge チームはトラッカーがブロックされている\*\*\*\* ときに警告メッセージをコンソールに追加しました。</span><span class="sxs-lookup"><span data-stu-id="12081-186">To give you more insight into the compatibility of your web page when certain trackers are blocked, The Microsoft Edge team added warning messages in the **Console** when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="追跡防止がトラッカーのストレージへのアクセスをブロックする場合のコンソール内のメッセージ" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   <span data-ttu-id="12081-188">追跡防止が **トラッカーのストレージ** へのアクセスをブロックする場合のコンソール内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="12081-188">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="12081-189">[追跡防止とプライバシーと Web の互換性のバランスについて詳しくは、以下をご覧ください][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="12081-189">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="12081-190">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="12081-190">Announcements from the Chromium project</span></span>  

<span data-ttu-id="12081-191">次のセクションでは、80 で利用可能Microsoft Edge、プロジェクトのオープン ソースにChromiumします。</span><span class="sxs-lookup"><span data-stu-id="12081-191">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <a name="support-for-let-and-class-redeclarations-in-the-console"></a><span data-ttu-id="12081-192">コンソールでの let および class redeclarations のサポート</span><span class="sxs-lookup"><span data-stu-id="12081-192">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="12081-193">コンソール **は** 、ステートメントの再宣言 `let` を `class` サポートします。</span><span class="sxs-lookup"><span data-stu-id="12081-193">The **Console** now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="12081-194">redeclare が利用できなかったのは、コンソールを使用して新しい JavaScript コードを試す Web 開発者に対して一般的な迷惑でした。</span><span class="sxs-lookup"><span data-stu-id="12081-194">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="12081-195">コンソールの外部または単一のコンソール入力内のスクリプトで a または ステートメントを再設定すると、引き続き `let` `class` `SyntaxError` .</span><span class="sxs-lookup"><span data-stu-id="12081-195">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="12081-196">たとえば、以前は、ローカル変数を使用して再宣言すると、 `let` コンソールはエラーを発生しました。</span><span class="sxs-lookup"><span data-stu-id="12081-196">For example, previously, when re-declaring a local variable with `let`, the Console threw an error:</span></span>  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="79 のコンソールMicrosoft Edge再宣言が失敗した場合" lightbox="../../images/2019/12/letbefore.msft.png":::
   <span data-ttu-id="12081-198">**79**のコンソールMicrosoft Edge再宣言が失敗した場合</span><span class="sxs-lookup"><span data-stu-id="12081-198">The **Console** in Microsoft Edge 79 showing that the let re-declaration fails</span></span>  
:::image-end:::  

<span data-ttu-id="12081-199">次に、コンソールで再宣言を許可します。</span><span class="sxs-lookup"><span data-stu-id="12081-199">Now, the Console allows the redeclaration:</span></span>  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="let 再宣言Microsoft Edge成功を示す 80 のコンソール" lightbox="../../images/2019/12/letafter.msft.png":::
   <span data-ttu-id="12081-201">let \*\*\*\* 再宣言Microsoft Edge成功を示すコンソール (80)</span><span class="sxs-lookup"><span data-stu-id="12081-201">The **Console** in Microsoft Edge 80 showing that the let re-declaration succeeds</span></span>  
:::image-end:::  

<span data-ttu-id="12081-202">Chromiumの問題[#1004193][CR1004193]</span><span class="sxs-lookup"><span data-stu-id="12081-202">Chromium issue [#1004193][CR1004193]</span></span>  

### <a name="improved-webassembly-debugging"></a><span data-ttu-id="12081-203">WebAssembly デバッグの改善</span><span class="sxs-lookup"><span data-stu-id="12081-203">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="12081-204">DevTools は [DWARF][DwarfHome]デバッグ標準のサポートを開始しました。つまり、コードのステップオーバー、ブレークポイントの設定、DevTools 内のソース言語でのスタック トレースの解決に対するサポートが強化されました。</span><span class="sxs-lookup"><span data-stu-id="12081-204">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <a name="network-panel-updates"></a><span data-ttu-id="12081-205">ネットワーク パネルの更新</span><span class="sxs-lookup"><span data-stu-id="12081-205">Network panel updates</span></span>  

#### <a name="request-initiator-chains-in-the-initiator-panel"></a><span data-ttu-id="12081-206">イニシエーター パネルでイニシエータ チェーンを要求する</span><span class="sxs-lookup"><span data-stu-id="12081-206">Request Initiator Chains in the Initiator panel</span></span>  

<span data-ttu-id="12081-207">これで、ネットワーク要求の開始者と依存関係を入れ子になったリストとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="12081-207">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="12081-208">これは、リソースが要求された理由、または特定のリソース \(script\など) が引き起こしたネットワーク アクティビティを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12081-208">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="イニシエーター パネルの要求イニシエーター チェーン" lightbox="../../images/2019/12/initiators.msft.png":::
   <span data-ttu-id="12081-210">イニシエーター パネルの要求 **イニシエーター** チェーン</span><span class="sxs-lookup"><span data-stu-id="12081-210">A Request Initiator Chain in the **Initiator** panel</span></span>  
:::image-end:::  

<span data-ttu-id="12081-211">[[ネットワーク] パネルでネットワーク アクティビティを][DevToolsNetworkIndex]ログに記録した後、リソース\*\*\*\* を選択し、[イニシエーター] パネルに移動して、要求イニシエータ**ー チェーンを表示します**。</span><span class="sxs-lookup"><span data-stu-id="12081-211">After [logging network activity in the Network panel][DevToolsNetworkIndex], choose a resource and then navigate to the **Initiator** panel to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="12081-212">検査 **されたリソースは太字** です。</span><span class="sxs-lookup"><span data-stu-id="12081-212">The **inspected resource** is bold.</span></span>  <span data-ttu-id="12081-213">上のスクリーンショットでは `ai.2.min.js` 、検査されたリソースです。</span><span class="sxs-lookup"><span data-stu-id="12081-213">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="12081-214">検査されたリソースの上にあるリソースは、イニシエータ **ーです**。</span><span class="sxs-lookup"><span data-stu-id="12081-214">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="12081-215">上のスクリーンショットでは `https://www.microsoftedgeinsider.com` 、 の開始者 `ai.2.min.js` です。</span><span class="sxs-lookup"><span data-stu-id="12081-215">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="12081-216">つまり、ネットワーク `https://www.microsoftedgeinsider.com` 要求が発生しました `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="12081-216">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="12081-217">検査されたリソースの下のリソースは、依存関係 **です**。</span><span class="sxs-lookup"><span data-stu-id="12081-217">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="12081-218">上のスクリーンショットでは `https://dc.services.visualstudio.com/v2/track` 、 の依存関係です `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="12081-218">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="12081-219">つまり、ネットワーク `ai.2.min.js` 要求が発生しました `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="12081-219">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="12081-220">イニシエーターと依存関係の情報にアクセスするには、ネットワーク リソースを保持してから `Shift` ホバリングします。</span><span class="sxs-lookup"><span data-stu-id="12081-220">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="12081-221">[イニシエータと [依存関係の表示] に移動します][DevToolsNetworkReferenceViewInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="12081-221">Navigate to [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="12081-222">Chromium[問題#842488][CR842488]</span><span class="sxs-lookup"><span data-stu-id="12081-222">Chromium issue [#842488][CR842488]</span></span>  

#### <a name="highlight-the-selected-network-request-in-the-overview"></a><span data-ttu-id="12081-223">[概要] で選択したネットワーク要求を強調表示する</span><span class="sxs-lookup"><span data-stu-id="12081-223">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="12081-224">ネットワーク リソースを検査するために選択した後、ネットワーク パネルは、そのリソースの周囲に青い枠線を [概要] に **表示します**。</span><span class="sxs-lookup"><span data-stu-id="12081-224">After you choose a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="12081-225">これにより、ネットワーク要求が予想よりも早くまたは後で発生した場合の検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12081-225">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="検査されたリソースを強調表示する [概要] ウィンドウ" lightbox="../../images/2019/12/overview.msft.png":::
   <span data-ttu-id="12081-227">検査 **されたリソース** を強調表示する [概要] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="12081-227">The **Overview** pane highlighting the inspected resource</span></span>  
:::image-end:::  

<span data-ttu-id="12081-228">Chromium[の問題][CR988253]#988253</span><span class="sxs-lookup"><span data-stu-id="12081-228">Chromium issue [#988253][CR988253]</span></span>  

#### <a name="url-and-path-columns-in-the-network-panel"></a><span data-ttu-id="12081-229">[ネットワーク] パネルの URL 列とパス列</span><span class="sxs-lookup"><span data-stu-id="12081-229">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="12081-230">ネットワーク ツールの**新しい [パス**] 列と\*\*\*\*\*\*[URL]\*\* 列を使用して、各ネットワーク リソースの絶対パスまたは完全な URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="12081-230">Use the new **Path** and **URL** columns in the **Network** tool to display the absolute path or full URL of each network resource.</span></span>  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="[ネットワーク] パネルの新しい [パス] 列と [URL] 列" lightbox="../../images/2019/12/columns.msft.png":::
   <span data-ttu-id="12081-232">ネットワーク ツールの新しい [パス] **列と** [URL] 列</span><span class="sxs-lookup"><span data-stu-id="12081-232">The new Path and URL columns in the **Network** tool</span></span>  
:::image-end:::  

<span data-ttu-id="12081-233">新しい列を表示するには、**ウォーター**フォール テーブル ヘッダーにマウス ポインターを置き、コンテキスト メニュー \(righ-click\) を開き、[パス] または **[URL]\*\*\*\*を**選択します。</span><span class="sxs-lookup"><span data-stu-id="12081-233">To display the new columns, hover on the **Waterfall** table header, open the contextual menu \(righ-click\), and choose **Path** or **URL**.</span></span>  

<span data-ttu-id="12081-234">Chromium[問題#993366][CR993366]</span><span class="sxs-lookup"><span data-stu-id="12081-234">Chromium issue [#993366][CR993366]</span></span>  

#### <a name="updated-user-agent-strings"></a><span data-ttu-id="12081-235">更新されたUser-Agent文字列</span><span class="sxs-lookup"><span data-stu-id="12081-235">Updated User-Agent strings</span></span>  

<span data-ttu-id="12081-236">DevTools では、[ネットワーク条件] パネルをUser-Agentカスタム 文字列 **の設定がサポート** されています。</span><span class="sxs-lookup"><span data-stu-id="12081-236">DevTools supports setting a custom User-Agent string through the **Network Conditions** panel.</span></span>  <span data-ttu-id="12081-237">このUser-Agentは、ネットワーク リソースに接続されている HTTP ヘッダーに影響します。また、 `User-Agent` の値にも影響します `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="12081-237">The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="12081-238">定義済みのUser-Agentは、最新のブラウザー バージョンを反映するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="12081-238">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="[ネットワーク条件] パネルの [ユーザー エージェント] メニュー" lightbox="../../images/2019/12/useragent.msft.png":::
   <span data-ttu-id="12081-240">[ネットワーク条件] パネルの **[ユーザー エージェント]** メニュー</span><span class="sxs-lookup"><span data-stu-id="12081-240">The User Agent menu in the **Network Conditions** panel</span></span>  
:::image-end:::  

<span data-ttu-id="12081-241">ネットワーク条件**にアクセスするには、**[コマンド メニューを開き][DevToolsCommandMenuIndex]、コマンドを実行 `Show Network Conditions` します。</span><span class="sxs-lookup"><span data-stu-id="12081-241">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="12081-242">デバイス モードで [文字列User-Agent設定することもできます][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="12081-242">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="12081-243">Chromiumの問題[#1029031][CR1029031]</span><span class="sxs-lookup"><span data-stu-id="12081-243">Chromium issue [#1029031][CR1029031]</span></span>  

### <a name="audits-panel-updates"></a><span data-ttu-id="12081-244">監査パネルの更新</span><span class="sxs-lookup"><span data-stu-id="12081-244">Audits panel updates</span></span>  

#### <a name="new-configuration-ui"></a><span data-ttu-id="12081-245">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="12081-245">New configuration UI</span></span>  

<span data-ttu-id="12081-246">構成 UI には応答性の高い新しいデザインが追加され、調整の構成オプションが簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="12081-246">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="12081-247">調整 UI の変更の詳細については [、「Audits Panel Throttling」に移動します][GitHubGoogleChromeDevToolsAuditsPanelThrottling]。</span><span class="sxs-lookup"><span data-stu-id="12081-247">For more information on the throttling UI changes, navigate to [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling].</span></span>  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新しい構成 UI" lightbox="../../images/2019/12/start.msft.png":::
   <span data-ttu-id="12081-249">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="12081-249">The new configuration UI</span></span>  
:::image-end:::  

### <a name="coverage-tool-updates"></a><span data-ttu-id="12081-250">カバレッジ ツールの更新</span><span class="sxs-lookup"><span data-stu-id="12081-250">Coverage tool updates</span></span>  

#### <a name="per-function-or-per-block-coverage-modes"></a><span data-ttu-id="12081-251">関数単位またはブロック単位のカバレッジ モード</span><span class="sxs-lookup"><span data-stu-id="12081-251">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="12081-252">カバレッジ[ツールには][DevToolsCoverageIndex]新しいドロップダウン メニューが追加され、コード カバレッジ データを関数\*\*\*\* ごとに収集するか、ブロックごとに収集するかどうかを**指定できます**。</span><span class="sxs-lookup"><span data-stu-id="12081-252">The [Coverage][DevToolsCoverageIndex] tool has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="12081-253">**ブロックごとのカバレッジ** は、より詳細ですが、収集するコストもはるかに高くなります。</span><span class="sxs-lookup"><span data-stu-id="12081-253">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="12081-254">DevTools では、関数 **ごとの範囲が既定** で使用されます。</span><span class="sxs-lookup"><span data-stu-id="12081-254">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="12081-255">HTML ファイルのコード範囲の違いは、関数ごとに使用するか、ブロック\*\*\*\* モードごとに使用するかによって**大きく異なる場合**があります。</span><span class="sxs-lookup"><span data-stu-id="12081-255">You may notice large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="12081-256">関数ごとの **モードを使用する** 場合、HTML ファイル内のインライン スクリプトは関数として扱います。</span><span class="sxs-lookup"><span data-stu-id="12081-256">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="12081-257">スクリプトが全く実行されている場合、DevTools はスクリプト全体を使用コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="12081-257">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="12081-258">スクリプトが全く実行されない場合にのみ、DevTools はスクリプトを未使用のコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="12081-258">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="[カバレッジ モード] ドロップダウン メニュー" lightbox="../../images/2019/12/modes.msft.png":::
   <span data-ttu-id="12081-260">[カバレッジ モード] ドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="12081-260">The coverage mode dropdown menu</span></span>  
:::image-end:::  

#### <a name="coverage-must-now-be-initiated-by-a-page-refresh"></a><span data-ttu-id="12081-261">ページの更新によってカバレッジを開始する必要があります</span><span class="sxs-lookup"><span data-stu-id="12081-261">Coverage must now be initiated by a page refresh</span></span>  

<span data-ttu-id="12081-262">ページの更新を行わずにコード範囲を切り込むのは、カバレッジ データが不当だったため削除されました。</span><span class="sxs-lookup"><span data-stu-id="12081-262">Toggling code coverage without a page refresh has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="12081-263">たとえば、ランタイムが長時間前で、V8 ガベージ コレクターがクリーンアップした場合、関数が使用されていないと報告される場合があります。</span><span class="sxs-lookup"><span data-stu-id="12081-263">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="12081-264">Chromiumの問題[#1004203][CR1004203]</span><span class="sxs-lookup"><span data-stu-id="12081-264">Chromium issue [#1004203][CR1004203]</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="12081-265">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="12081-265">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="12081-266">Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="12081-266">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="12081-267">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="12081-267">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="12081-268">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="12081-268">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "DevTools ページの [カバレッジ] ツールを使用して、使用されていない JavaScript および CSS Microsoft Edgeを|Microsoft Docs"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "モバイル ビューポートをシミュレートする - デバイス モードでモバイル デバイスをシミュレートする (DevTools Microsoft Edge) |Microsoft Docs"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "DevTools サーバーでネットワークMicrosoft Edgeを調|Microsoft Docs"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "開始者と依存関係の表示 - ネットワーク分析リファレンス |Microsoft Docs"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "デバッガーの拡張機能Microsoft Edge Visual Studio Codeの|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "拡張機能のMicrosoft Edge Visual Studio Code要素|Microsoft Docs"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "[イニシエーター] フィールドを [ヘッダー] タブに追加|Chromiumバグ"  
[CR988253]: https://crbug.com/988253 "Bug DevTools - ネットワーク要求とタイムライン の間に関連付Graph |Chromiumバグ"  
[CR993366]: https://crbug.com/993366 "ネットワーク パネル要求リストに URL のパス部分を表示|Chromiumバグ"  
[CR1004193]: https://crbug.com/1004193 "V8 の REPL モード|Chromiumバグ"  
[CR1004203]: https://crbug.com/1004203 "コード カバレッジをすばらしい|Chromiumバグ"  
[CR1029031]: https://crbug.com/1029031 "UA 文字列が古くなっている|Chromiumバグ" 
[CR963183]: https://crbug.com/963183 "DevTools は WCAG 準拠の|Chromiumバグ"
[CR941561]: https://crbug.com/941561 "DevTools ファイルのローカライズ|Chromiumバグ"
[CR987787]: https://crbug.com/987787 "Dom 3D ビュー |Chromiumバグ"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティインサイト"  

[DwarfHome]: https://dwarfstd.org "Dwarf Home"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools の監査パネル調整 - GoogleChrome/ライトハウス |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edgeプレビュー チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft EdgeInsider アドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "JavaScript を Microsoft EdgeからデバッグVisual Studio |Visual Studioブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "ダウンロード Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio Code"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "デバッガー for Microsoft Edge - Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "\Chromium(Microsoft Edge\) の要素 - Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint Browser Extension |webhint のドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio Code 拡張機能 |webhint のドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "ブログ投稿での追跡防止Microsoft Edge改善"
[TheWebWeWant]: https://aka.ms/webwewant "必要とされる Web"

> [!NOTE]
> <span data-ttu-id="12081-307">このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="12081-307">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="12081-308">元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-80) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="12081-308">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-80) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="12081-310">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="12081-310">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
