---
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8e9e6885d04c7ad15a688b51cee4c16440d3ca1e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942113"
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

# <span data-ttu-id="c0462-103">DevTools の新機能 (Microsoft Edge 81)</span><span class="sxs-lookup"><span data-stu-id="c0462-103">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <span data-ttu-id="c0462-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="c0462-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="c0462-105">以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c0462-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="c0462-106">デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c0462-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="c0462-107">開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="c0462-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="c0462-108">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="c0462-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="c0462-109">DevTools チームは Chromium に変更を加え、DevTools のコントラスト、キーボード、スクリーン リーダーの問題に対する影響を許可します。</span><span class="sxs-lookup"><span data-stu-id="c0462-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="c0462-110">Web を構築するすべてのデベロッパーが DevTools を使用できるはずです。</span><span class="sxs-lookup"><span data-stu-id="c0462-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="c0462-111">図 1</span><span class="sxs-lookup"><span data-stu-id="c0462-111">Figure 1</span></span>  
> <span data-ttu-id="c0462-112">キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="c0462-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="c0462-114">すべてのユーザーが Web ページにアクセスできるようにする方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="c0462-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="c0462-115">使い [始めるには][AccessibilityInsights] 、Microsoft Edge 用のアクセシビリティ インサイトと Web [の][WebhintBrowserExtension] 拡張機能をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c0462-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="c0462-116">スクリーン リーダーまたはキーボードを使用して DevTools 内を移動する場合は、Microsoft における [タイル][PostTweetEdgeDevTools] をタイーションするか、[フィードバックの送信] アイコンをクリックして、フィードバック [を送信してください](#getting-in-touch-with-microsoft-edge-devtools-team) 。</span><span class="sxs-lookup"><span data-stu-id="c0462-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0462-117">Chromium の問題 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="c0462-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="c0462-118">他の言語で DevTools を使用する</span><span class="sxs-lookup"><span data-stu-id="c0462-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="c0462-119">多くのデベロッパーは、英語以外の開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="c0462-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="c0462-120">この DevTools のローカリゼーションのローカリゼーションを発表するため、英語の両側にある 10 の言語で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c0462-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c0462-121">中小 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="c0462-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c0462-122">中チェーン \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="c0462-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="c0462-123">フランス語 – フラン&#231;フラン&#231;フラン</span><span class="sxs-lookup"><span data-stu-id="c0462-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c0462-124">ドイツ語 - deutsch</span><span class="sxs-lookup"><span data-stu-id="c0462-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="c0462-125">イタリア語 - イタリアノ</span><span class="sxs-lookup"><span data-stu-id="c0462-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c0462-126">日本語 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="c0462-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="c0462-127">Korean - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="c0462-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c0462-128">ポルトガル語 - ポルトガル&#234;トル</span><span class="sxs-lookup"><span data-stu-id="c0462-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="c0462-129">ロシア語 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="c0462-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c0462-130">スペイン語 - エスパス&#241;ーリング</span><span class="sxs-lookup"><span data-stu-id="c0462-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="c0462-131">DevTools は、Microsoft Edge で使用する言語と自動的に対応付けます `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="c0462-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="c0462-132">Microsoft Edge を 1 つの言語にして DevTools を英語のままにする場合は `F1` 、DevTools で [設定] を開き、[ブラウザー言語に合 [わせる]][Settings] **を無効にします**。</span><span class="sxs-lookup"><span data-stu-id="c0462-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

> ##### <span data-ttu-id="c0462-133">図 2</span><span class="sxs-lookup"><span data-stu-id="c0462-133">Figure 2</span></span>  
> <span data-ttu-id="c0462-134">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="c0462-134">The DevTools in German</span></span>  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

<span data-ttu-id="c0462-136">**本体メッセージは** ローカライズされません。</span><span class="sxs-lookup"><span data-stu-id="c0462-136">**Console** messages are not localized.</span></span>  <span data-ttu-id="c0462-137">DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-137">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="c0462-138">使用可能な言語とは異なる言語で DevTools を使用する場合は、弊内で [チ][PostTweetEdgeDevTools] ェイトをチェイトにするか、[フィードバックの [送信] アイコンをクリック](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="c0462-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="c0462-139">Chromium の [問題#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="c0462-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="c0462-140">Webhint Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="c0462-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="c0462-141">Webhint Microsoft Edge 拡張機能を使用すると、Web ページを簡単に見て、DevTools 内のアクセシビリティ、ブラウザー互換性、セキュリティ、パフォーマンスなどに関するフィードバックを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="c0462-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="c0462-142">詳細については、次を参照 [https://webhint.io][Webhint] してください。</span><span class="sxs-lookup"><span data-stu-id="c0462-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="c0462-143">図 3</span><span class="sxs-lookup"><span data-stu-id="c0462-143">Figure 3</span></span>  
> <span data-ttu-id="c0462-144">WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ</span><span class="sxs-lookup"><span data-stu-id="c0462-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

<span data-ttu-id="c0462-146">[Microsoft Edge の Web ブラウザー拡張機能を試してください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="c0462-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="c0462-147">拡張機能をインストールしたら、DevTools を開き、[ヒント] タブを選択します。 ここから、カスタマイズ可能なサイト スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0462-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="c0462-148">詳細については [、webhint.io][WebhintBrowserExtension] にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c0462-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="c0462-149">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="c0462-149">3D View</span></span>  

<span data-ttu-id="c0462-150">**3D ビューを使用して**、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z イン][MDNZIndex]デックス スタック コンテキストを移動して Web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="c0462-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="c0462-151">図 4</span><span class="sxs-lookup"><span data-stu-id="c0462-151">Figure 4</span></span>  
> <span data-ttu-id="c0462-152">DevTools の 3D ビュー</span><span class="sxs-lookup"><span data-stu-id="c0462-152">The 3D View in the DevTools</span></span>  
> ![DevTools の 3D ビュー][Image3DView]  

<span data-ttu-id="c0462-154">3D ビューにアクセスするには、3D ビュー `Ctrl`  +  `Shift`  +  `P` **に入力し、[3D ビュー\*\*\*\*の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c0462-154">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="c0462-155">Microsoft では、UI に関する作業を行い、3D ビューに機能を追加するため、フィードバックをお送り [ください](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="c0462-155">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="c0462-156">Chromium の問題 [#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="c0462-156">Chromium issue [#987787][crbug987787]</span></span>  

### <span data-ttu-id="c0462-157">Visual Studio拡張機能</span><span class="sxs-lookup"><span data-stu-id="c0462-157">Visual Studio Code extensions</span></span>  

<span data-ttu-id="c0462-158">DevTools チームには、テキスト エディターから直接 DevTools の機能を利用できる [Visual Studio Code \(VS Code\)][VisualStudioCode] 用の拡張機能もいくつかリリースされています。</span><span class="sxs-lookup"><span data-stu-id="c0462-158">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="c0462-159">下の拡張機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0462-159">Check out the extensions below:</span></span>  

#### <span data-ttu-id="c0462-160">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="c0462-160">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="c0462-161">[Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]および VS コード拡張子を追加して、VS コード内から要素ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0462-161">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="c0462-162">図 5</span><span class="sxs-lookup"><span data-stu-id="c0462-162">Figure 5</span></span>  
> <span data-ttu-id="c0462-163">Microsoft Edge 拡張機能の要素を使用した VS コードの要素ツールを ![ VS コード内の要素ツール][ImageElementsVisualStudioCode]</span><span class="sxs-lookup"><span data-stu-id="c0462-163">The Elements tool in VS Code using the Elements for Microsoft Edge extension ![The Elements tool in VS Code using the Elements for Microsoft Edge extension][ImageElementsVisualStudioCode]</span></span>  

<span data-ttu-id="c0462-164">詳細については [、Microsoft Edge VS コード拡張機能の要素をご覧ください][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="c0462-164">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="c0462-165">Microsoft Edge のデバッガー</span><span class="sxs-lookup"><span data-stu-id="c0462-165">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="c0462-166">Microsoft Edge VS コード [拡張機能][VisualStudioMarketplaceDebuggerEdge] を使用して、VS コードから直接 Microsoft Edge で実行されている JavaScript をデバッグします!</span><span class="sxs-lookup"><span data-stu-id="c0462-166">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="c0462-167">図 6</span><span class="sxs-lookup"><span data-stu-id="c0462-167">Figure 6</span></span>  
> <span data-ttu-id="c0462-168">VS コードの Microsoft Edge 拡張機能のデバッガー</span><span class="sxs-lookup"><span data-stu-id="c0462-168">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS コードの Microsoft Edge 拡張機能のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="c0462-170">詳細については [、VS コードから Microsoft Edge をデバッグする方法を確認してください][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="c0462-170">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="c0462-171">Webhint</span><span class="sxs-lookup"><span data-stu-id="c0462-171">webhint</span></span>  

<span data-ttu-id="c0462-172">Web [ハイント][VisualStudioMarketplaceWebhintExtension] VS コード拡張機能を使用して、Web ページの作成中に Web ページ `webhint` を向上させます。</span><span class="sxs-lookup"><span data-stu-id="c0462-172">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="c0462-173">この拡張機能は分析に基づいてワークスペース ファイルに基づいて診定を実行および `webhint` レポートします。</span><span class="sxs-lookup"><span data-stu-id="c0462-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="c0462-174">図 7</span><span class="sxs-lookup"><span data-stu-id="c0462-174">Figure 7</span></span>  
> <span data-ttu-id="c0462-175">VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子</span><span class="sxs-lookup"><span data-stu-id="c0462-175">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="c0462-177">[VS コードウェート拡張機能の詳細をご覧ください][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="c0462-177">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="c0462-178">Visual Studio統合</span><span class="sxs-lookup"><span data-stu-id="c0462-178">Visual Studio integration</span></span>  

<span data-ttu-id="c0462-179">Visual Studio 2019 バージョン 16.2 以降では、Visual Studio デバッガーを使用して Microsoft Edge で実行されている JavaScript のデバッグを行います。</span><span class="sxs-lookup"><span data-stu-id="c0462-179">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="c0462-180">[この機能Visual Studioするには、2019][MicrosoftVisualStudioDownloads] をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c0462-180">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="c0462-181">図 8</span><span class="sxs-lookup"><span data-stu-id="c0462-181">Figure 8</span></span>  
> <span data-ttu-id="c0462-182">Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="c0462-182">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="c0462-184">[Microsoft Edge のデバッグの詳細については、こちらVisual Studio。][MicrosoftVisualStudio]</span><span class="sxs-lookup"><span data-stu-id="c0462-184">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="c0462-185">本体メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="c0462-185">Tracking prevention Console messages</span></span>  

<span data-ttu-id="c0462-186">追跡防止は、Microsoft Edge で、これまでアクセスした Web サイトで追跡されないように保護する固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="c0462-186">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="c0462-187">既定の追跡防止設定は、プライバシーと Web 互換性のバランスを取るエクスペリエンスについてサード パーティのトラッカーと既知の重大なトラッカーをブロックするバランス化モードです。</span><span class="sxs-lookup"><span data-stu-id="c0462-187">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="c0462-188">特定のトラッカーがブロックされたときに Web ページの互換性に関する分け情報を取得できるように、トラッカーがブロックされたときに本体に警告メッセージも追加されています。</span><span class="sxs-lookup"><span data-stu-id="c0462-188">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="c0462-189">図 9</span><span class="sxs-lookup"><span data-stu-id="c0462-189">Figure 9</span></span>  
> <span data-ttu-id="c0462-190">トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="c0462-190">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ][ImageTrackingPrevention]  

<span data-ttu-id="c0462-192">[トラッキング防止の詳細と、][TrackingPrevention]プライバシーと Web 互換性のバランスの残高について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0462-192">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="c0462-193">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="c0462-193">Announcements from the Chromium project</span></span>  

<span data-ttu-id="c0462-194">次のセクションでは、オープン ソース Chromium プロジェクトに投稿された Microsoft Edge 81 で利用可能なその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0462-194">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="c0462-195">デバイス モードでのモート G4 のサポート</span><span class="sxs-lookup"><span data-stu-id="c0462-195">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="c0462-196">デバイス [ツール バーを有効][DeviceToolbar]にした後、[デバイス] の一覧からモート G4 のビューポートの大きさを **シリュレート** します。</span><span class="sxs-lookup"><span data-stu-id="c0462-196">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

> ##### <span data-ttu-id="c0462-197">図 10</span><span class="sxs-lookup"><span data-stu-id="c0462-197">Figure 10</span></span>  
> <span data-ttu-id="c0462-198">Moto G4 ビューポートのシンボルシュ</span><span class="sxs-lookup"><span data-stu-id="c0462-198">Simulating a Moto G4 viewport</span></span>  
> ![Moto G4 ビューポートのシンボルシュ][ImageMotoG4]  

<span data-ttu-id="c0462-200">[ [デバイス フレームを][DeviceFrame] 表示] をクリックして、ビューポートの周囲の Moto G4 ハードウェアを表示します。</span><span class="sxs-lookup"><span data-stu-id="c0462-200">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

> ##### <span data-ttu-id="c0462-201">図 11</span><span class="sxs-lookup"><span data-stu-id="c0462-201">Figure 11</span></span>  
> <span data-ttu-id="c0462-202">Moto G4 ハードウェアを示しています</span><span class="sxs-lookup"><span data-stu-id="c0462-202">Showing the Moto G4 hardware</span></span>  
> ![Moto G4 ハードウェアを示しています][ImageMotoG4Frame]  

<span data-ttu-id="c0462-204">関連機能:</span><span class="sxs-lookup"><span data-stu-id="c0462-204">Related features:</span></span>  

*   <span data-ttu-id="c0462-205">コマンド メニュー[を開き][CommandMenu]、Moto G4 ハードウェアを含むビューポートの `Capture screenshot` スクリーンショットを撮るコマンドを実行します (デバイス フレームを**有効にした後)。**</span><span class="sxs-lookup"><span data-stu-id="c0462-205">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="c0462-206">[モバイル ユーザーの Web 閲][ThrottleNetworkAndCpu] 覧条件をより正確にシミュレートするのにネットワークと CPU をスロットルします。</span><span class="sxs-lookup"><span data-stu-id="c0462-206">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="c0462-207">Chromium の問題 [#924693][crbug924693]</span><span class="sxs-lookup"><span data-stu-id="c0462-207">Chromium issue [#924693][crbug924693]</span></span>  

### <span data-ttu-id="c0462-208">Cookie 関連の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="c0462-208">Cookie-related updates</span></span>  

#### <span data-ttu-id="c0462-209">Cookie ウィンドウでブロックされた Cookie がブロックされています</span><span class="sxs-lookup"><span data-stu-id="c0462-209">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="c0462-210">アプリケーション パネルの Cookie ウィンドウに、黄色の背景でブロックされている Cookie が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c0462-210">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

> ##### <span data-ttu-id="c0462-211">図 12</span><span class="sxs-lookup"><span data-stu-id="c0462-211">Figure 12</span></span>  
> <span data-ttu-id="c0462-212">アプリケーション パネルの Cookie ウィンドウでブロックされた Cookie がブロックされました</span><span class="sxs-lookup"><span data-stu-id="c0462-212">Blocked cookies in the Cookies pane of the Application panel</span></span>  
> ![アプリケーション パネルの Cookie ウィンドウでブロックされた Cookie がブロックされました][ImageBlockedCookies]  

<span data-ttu-id="c0462-214">Chromium の [問題#1030258][crbug|::ref1::|]</span><span class="sxs-lookup"><span data-stu-id="c0462-214">Chromium issue [#1030258][crbug|::ref1::|]</span></span>  

#### <span data-ttu-id="c0462-215">Cookie ウィンドウの Cookie 優先度</span><span class="sxs-lookup"><span data-stu-id="c0462-215">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="c0462-216">ネットワークパネルとアプリケーション パネルの Cookie テーブルに優先 **度列が追加されるようになり** ました。</span><span class="sxs-lookup"><span data-stu-id="c0462-216">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="c0462-217">Microsoft Edge などの Chromium ベースのブラウザーは、Cookie 優先度をサポートするブラウザーのみです。</span><span class="sxs-lookup"><span data-stu-id="c0462-217">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="c0462-218">Chromium の問題は、Chromium [の問題#1026879][crbug1026879]</span><span class="sxs-lookup"><span data-stu-id="c0462-218">Chromium issue [#1026879][crbug1026879]</span></span>  

#### <span data-ttu-id="c0462-219">すべての Cookie 値を編集する</span><span class="sxs-lookup"><span data-stu-id="c0462-219">Edit all cookie values</span></span>  

<span data-ttu-id="c0462-220">Cookie テーブルのすべてのセルは編集可能になり、サイズ列のセルは、 **バ** イト単位で Cookie のネットワーク サイズを表すためです。</span><span class="sxs-lookup"><span data-stu-id="c0462-220">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="c0462-221">各 [列の][CookiesFields] 説明についてはフィールドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0462-221">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

> ##### <span data-ttu-id="c0462-222">図 13</span><span class="sxs-lookup"><span data-stu-id="c0462-222">Figure 13</span></span>  
> <span data-ttu-id="c0462-223">Cookie 値を編集する</span><span class="sxs-lookup"><span data-stu-id="c0462-223">Editing a cookie value</span></span>  
> ![Cookie 値を編集する][ImageEditCookie]  

#### <span data-ttu-id="c0462-225">フェッチとしてコピーNode.jsCookie データを含める</span><span class="sxs-lookup"><span data-stu-id="c0462-225">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="c0462-226">ネットワーク要求を右クリックし、[**Copy**  >  **コピーとしてコピーNode.js選択] を選択して** `fetch` 、Cookie データを含む式を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0462-226">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

> ##### <span data-ttu-id="c0462-227">図 14</span><span class="sxs-lookup"><span data-stu-id="c0462-227">Figure 14</span></span>  
> <span data-ttu-id="c0462-228">[コピー] Node.jsフェッチとしてコピーする</span><span class="sxs-lookup"><span data-stu-id="c0462-228">Copy as Node.js fetch</span></span>  
> ![[コピー] Node.jsフェッチとしてコピーする][ImageCopyFetch]  

<span data-ttu-id="c0462-230">Chromium の [問題#1029826][crbug1029826]</span><span class="sxs-lookup"><span data-stu-id="c0462-230">Chromium issue [#1029826][crbug1029826]</span></span>  

### <span data-ttu-id="c0462-231">正確な Web アプリ マニフェスト アイコン</span><span class="sxs-lookup"><span data-stu-id="c0462-231">More accurate web app manifest icons</span></span>  

<span data-ttu-id="c0462-232">以前は、アプリケーション パネルのマニフェスト ウィンドウでは、Web アプリ マニフェスト アイコンを表示するため、独自の要求を送信しました。</span><span class="sxs-lookup"><span data-stu-id="c0462-232">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="c0462-233">DevTools では、Microsoft Edge で使用されるのとまる同じマニフェスト アイコンが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c0462-233">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

> ##### <span data-ttu-id="c0462-234">図 15</span><span class="sxs-lookup"><span data-stu-id="c0462-234">Figure 15</span></span>  
> <span data-ttu-id="c0462-235">マニフェスト ウィンドウのアイコン</span><span class="sxs-lookup"><span data-stu-id="c0462-235">Icons in the Manifest pane</span></span>  
> ![マニフェスト ウィンドウのアイコン][ImageManifestIcon]  

<span data-ttu-id="c0462-237">Chromium の [問題#985402][crbug985402]</span><span class="sxs-lookup"><span data-stu-id="c0462-237">Chromium issue [#985402][crbug985402]</span></span>  

### <span data-ttu-id="c0462-238">CSS コンテンツ プロパティにマウス ポインターを置くと、不一りの値が表示される</span><span class="sxs-lookup"><span data-stu-id="c0462-238">Hover over CSS content properties to see unescaped values</span></span>  

<span data-ttu-id="c0462-239">プロパティの値をマウスで `content` 置き、値の不予重のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-239">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="c0462-240">たとえば、このデ [モでは][CSSContentDemo] 、pseudo 要素を検査すると、[スタイル] ウィンドウにエスケープ文字列 `p::after` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-240">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

> ##### <span data-ttu-id="c0462-241">図 16</span><span class="sxs-lookup"><span data-stu-id="c0462-241">Figure 16</span></span>  
> <span data-ttu-id="c0462-242">Escaped 文字列</span><span class="sxs-lookup"><span data-stu-id="c0462-242">The escaped string</span></span>  
> ![Escaped 文字列][ImageEscapedString]  

<span data-ttu-id="c0462-244">値にマウス ポインタ `content` ーを移動すると、未一の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-244">When you hover over the `content` value you see the unescaped value:</span></span>  

> ##### <span data-ttu-id="c0462-245">図 17</span><span class="sxs-lookup"><span data-stu-id="c0462-245">Figure 17</span></span>  
> <span data-ttu-id="c0462-246">不一の値</span><span class="sxs-lookup"><span data-stu-id="c0462-246">The unescaped value</span></span>  
> ![不一の値][ImageUnescapedString]  

### <span data-ttu-id="c0462-248">本体の詳細なソース マップ エラー</span><span class="sxs-lookup"><span data-stu-id="c0462-248">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="c0462-249">本体では、ソース マップの読み込みや解析に失敗した理由の詳細が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c0462-249">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="c0462-250">以前は、エラーが発生したものを説明せずにエラーを提供していました。</span><span class="sxs-lookup"><span data-stu-id="c0462-250">Previously it just provided an error without explaining what went wrong.</span></span>  

> ##### <span data-ttu-id="c0462-251">図 18</span><span class="sxs-lookup"><span data-stu-id="c0462-251">Figure 18</span></span>  
> <span data-ttu-id="c0462-252">本体のソース マッチの読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="c0462-252">A source map loading error in the Console</span></span>  
> ![本体のソース マッチの読み込みエラー][ImageSourcemapError]  

### <span data-ttu-id="c0462-254">ファイルの末尾のスクロールを無効にする設定</span><span class="sxs-lookup"><span data-stu-id="c0462-254">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="c0462-255">[[設定] を開][Settings]き、[**環境設定ソース]** を無効にして、[ソース] パネルでファイルの末尾をスクロールする既定の UI 動作を  >  **Sources**  >  **Allow scrolling past end of file\*\*\*\*無効**にします。</span><span class="sxs-lookup"><span data-stu-id="c0462-255">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

> ##### <span data-ttu-id="c0462-256">図 19</span><span class="sxs-lookup"><span data-stu-id="c0462-256">Figure 19</span></span>  
> <span data-ttu-id="c0462-257">[設定] で [スクロールを許可する] のファイルの末尾の **スクロールを無効** にする</span><span class="sxs-lookup"><span data-stu-id="c0462-257">Disabling **Allow scrolling past end of file** in Settings</span></span>  
> ![[スクロールを許可する] ファイルの末尾のスクロールを無効にする][ImageSettings]  

> ##### <span data-ttu-id="c0462-259">図 20</span><span class="sxs-lookup"><span data-stu-id="c0462-259">Figure 20</span></span>  
> <span data-ttu-id="c0462-260">[ソース] パネルでファイルの末尾をスクロールすると無効になるようになりました</span><span class="sxs-lookup"><span data-stu-id="c0462-260">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
> ![[ソース] パネルでファイルの末尾をスクロールすると無効になるようになりました][ImageScroll]  

## <span data-ttu-id="c0462-262">Microsoft Edge のプレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c0462-262">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="c0462-263">Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。</span><span class="sxs-lookup"><span data-stu-id="c0462-263">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="c0462-264">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c0462-264">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="c0462-265">Microsoft Edge DevTools チームとのつながりを手にする</span><span class="sxs-lookup"><span data-stu-id="c0462-265">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "図 1: キーボード ナビゲーションとスクリーン リーダーの機能強化を使用して DevTools のパフォーマンス ツール"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "図 3: Web ホント ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "図 4: Microsoft Edge DevTools の 3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "図 5: Microsoft Edge 拡張機能の要素を使用して VS コード内の要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "図 6:VS コードの Microsoft Edge 拡張機能のデバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "図 7: VS コードで .tsx ファイルを分析する Webhint VS コード拡張子"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "図 8: Microsoft Edge Canary Visual Studio、Dev、Beta で Web アプリを起動するオプションが表示された"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "図 9: トラッカーの記憶域へのアクセスがブロックされている場合に本体内のメッセージ" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "図 10: Moto G4 ビューポートのシクル" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "図 11:Moto G4 ハードウェアを表示する" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "図 12: アプリケーション パネルの Cookie ウィンドウでブロックされている Cookie がブロックされました"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "図 13: Cookie 値を編集する"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "図 14: コピーしてフェッチNode.jsする"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "図 15:マニフェスト ウィンドウのアイコン"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "図 16:エスケープ文字列"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "図 17: 未満の値"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "図 18: 本体のソース マッチの読み込みエラー"
[ImageSettings]: ../../images/2020/01/settings.msft.png "図 19:[設定] でのファイルの [スクロールを許可する] の [スクロールを許可する]"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "図 20: [ソース] パネルでファイルの末尾のスクロールが無効になりました"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイス モードを使用してモバイル ビューポートをシイクルする"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "[デバイス フレームを表示] を選びます。ビューポートの周囲にデバイス フレームが表示されます。"
[CommandMenu]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニューでコマンドを実行する"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "モバイル ユーザーの Web 閲覧条件をより正確にシミュレートするのに、ネットワークと CPU をスロットルします。"
[crbug924693]: https://crbug.com/924693 "924693: 機能要求: デバイス モード リストにモート G4 を追加する"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879: 開発本体の [Cookie] タブには優先度が表示されない"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookie テーブルのフィールド"
[crbug1029826]: https://crbug.com/1029826 "1029826: ネットワーク タブ - > 右クリックして要求 -> コピーをリクエストする -> > コピーをリクエストしても、Cookie がコピーされない"
[crbug985402]: https://crbug.com/985402 "985402: Web アプリ マニフェスト アイコン エラー文字列がわからない"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "Esmo forescaped CSS コンテンツのデモ"
[Settings]: ../../../customize/index.md#settings "設定を使用して Microsoft Edge DevTools をカスタマイズする"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張機能のデバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張機能の要素"  
[crbug963183]: https://crbug.com/963183 "963183 - DevTools は WCAG に準格していません"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools のローカライズ性"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D ビュー"
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティ インサイト"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows \& Mac Visual Studio 2019 for Windows のダウンロード"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge のデバッガー - マVisual Studio市"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) - マーケットプレーVisual Studioース"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "Webhint - マーケットプレVisual Studioプレース"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Web ハイント ブラウザー拡張 |Webhint ドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |Webhint ドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿に追跡防止を行う"

> [!NOTE]
> <span data-ttu-id="c0462-322">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-322">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c0462-323">元のページがここに [あ](https://developers.google.com/web/updates/2020/01/devtools/index) り [、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools & Lighthouse\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0462-323">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c0462-325">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c0462-325">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  