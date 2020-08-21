---
title: DevTools の新機能 (Microsoft Edge 80)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 03fd78eddf54b68d072ba11401a897ad9f109058
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942142"
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

# <span data-ttu-id="21f15-103">DevTools の新機能 (Microsoft Edge 80)</span><span class="sxs-lookup"><span data-stu-id="21f15-103">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <span data-ttu-id="21f15-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="21f15-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="21f15-105">以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。</span><span class="sxs-lookup"><span data-stu-id="21f15-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="21f15-106">デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="21f15-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="21f15-107">開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="21f15-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="21f15-108">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="21f15-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="21f15-109">DevTools チームは Chromium に変更を加え、DevTools のコントラスト、キーボード、スクリーン リーダーの問題に対する影響を許可します。</span><span class="sxs-lookup"><span data-stu-id="21f15-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="21f15-110">Web を構築するすべてのデベロッパーが DevTools を使用できるはずです。</span><span class="sxs-lookup"><span data-stu-id="21f15-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="21f15-111">図 1</span><span class="sxs-lookup"><span data-stu-id="21f15-111">Figure 1</span></span>  
> <span data-ttu-id="21f15-112">キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="21f15-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![キーボード ナビゲーションとスクリーン リーダーの機能強化を使用した DevTools のパフォーマンス ツール][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="21f15-114">すべてのユーザーが Web ページにアクセスできるようにする方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="21f15-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="21f15-115">使い [始めるには][AccessibilityInsights] 、Microsoft Edge 用のアクセシビリティ インサイトと Web [の][WebhintBrowserExtension] 拡張機能をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="21f15-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="21f15-116">スクリーン リーダーまたはキーボードを使用して DevTools 内を移動する場合は、Microsoft における [タイル][PostTweetEdgeDevTools] をタイーションするか、[フィードバックの送信] アイコンをクリックして、フィードバック [を送信してください](#getting-in-touch-with-microsoft-edge-devtools-team) 。</span><span class="sxs-lookup"><span data-stu-id="21f15-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="21f15-117">Chromium の問題 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="21f15-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="21f15-118">他の言語で DevTools を使用する</span><span class="sxs-lookup"><span data-stu-id="21f15-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="21f15-119">多くのデベロッパーは、英語以外の開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="21f15-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="21f15-120">この DevTools のローカリゼーションのローカリゼーションを発表するため、英語の両側にある 10 の言語で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="21f15-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="21f15-121">中小 \(簡体字\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="21f15-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="21f15-122">中チェーン \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="21f15-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="21f15-123">フランス語 – フラン&#231;フラン&#231;フラン</span><span class="sxs-lookup"><span data-stu-id="21f15-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="21f15-124">ドイツ語 - deutsch</span><span class="sxs-lookup"><span data-stu-id="21f15-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="21f15-125">イタリア語 - イタリアノ</span><span class="sxs-lookup"><span data-stu-id="21f15-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="21f15-126">日本語 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="21f15-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="21f15-127">Korean - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="21f15-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="21f15-128">ポルトガル語 - ポルトガル&#234;トル</span><span class="sxs-lookup"><span data-stu-id="21f15-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="21f15-129">ロシア語 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="21f15-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="21f15-130">スペイン語 - エスパス&#241;ーリング</span><span class="sxs-lookup"><span data-stu-id="21f15-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="21f15-131">ローカ `edge://flags` ライズされた **開発者ツール フラグを** 有効に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="21f15-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="21f15-132">また **、Developer Tools の実用** フラグを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="21f15-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="21f15-133">Microsoft Edge を再起動し、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="21f15-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="21f15-134">DevTools は、Microsoft Edge で使用する言語と一致します `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

> ##### <span data-ttu-id="21f15-135">図 2</span><span class="sxs-lookup"><span data-stu-id="21f15-135">Figure 2</span></span>  
> <span data-ttu-id="21f15-136">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="21f15-136">The DevTools in German</span></span>  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

<span data-ttu-id="21f15-138">使用可能な言語とは異なる言語で DevTools を使用する場合は、弊内で [チ][PostTweetEdgeDevTools] ェイトをチェイトにするか、[フィードバックの [送信] アイコンをクリック](#getting-in-touch-with-microsoft-edge-devtools-team) します。</span><span class="sxs-lookup"><span data-stu-id="21f15-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="21f15-139">Chromium の [問題#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="21f15-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="21f15-140">Webhint Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="21f15-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="21f15-141">Webhint Microsoft Edge 拡張機能を使用すると、Web ページを簡単に見て、DevTools 内のアクセシビリティ、ブラウザー互換性、セキュリティ、パフォーマンスなどに関するフィードバックを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="21f15-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="21f15-142">詳細については、次を参照 [https://webhint.io][Webhint] してください。</span><span class="sxs-lookup"><span data-stu-id="21f15-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="21f15-143">図 3</span><span class="sxs-lookup"><span data-stu-id="21f15-143">Figure 3</span></span>  
> <span data-ttu-id="21f15-144">WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ</span><span class="sxs-lookup"><span data-stu-id="21f15-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![WebHint ブラウザー拡張機能がインストールされているときの DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

<span data-ttu-id="21f15-146">[Microsoft Edge の Web ブラウザー拡張機能を試してください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="21f15-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="21f15-147">拡張機能をインストールしたら、DevTools を開き、[ヒント] タブを選択します。 ここから、カスタマイズ可能なサイト スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="21f15-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="21f15-148">詳細については [、webhint.io][WebhintBrowserExtension] にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="21f15-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="21f15-149">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="21f15-149">3D View</span></span>  

<span data-ttu-id="21f15-150">**3D ビューを使用して**、ドキュメント オブジェクト モデル[\(DOM\)][MDNDocumentObjectModel]または[z イン][MDNZIndex]デックス スタック コンテキストを移動して Web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="21f15-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="21f15-151">図 4</span><span class="sxs-lookup"><span data-stu-id="21f15-151">Figure 4</span></span>  
> <span data-ttu-id="21f15-152">DevTools の 3D ビュー</span><span class="sxs-lookup"><span data-stu-id="21f15-152">The 3D View in the DevTools</span></span>  
> ![DevTools の 3D ビュー][Image3DView]  

<span data-ttu-id="21f15-154">3D ビューにアクセスするには `edge://flags` **、Developer Tools の** 有効期限フラグが有効に設定されていることを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="21f15-154">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="21f15-155">Microsoft Edge を再起動し、DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="21f15-155">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="21f15-156">`F1`DevTools 内を押すか、[設定 **] セクション**に移動し、[詳細設定] セクションに移動し **、[3D ビューを有効にする] チェック ボックスを**オンにします。 **Experiments**</span><span class="sxs-lookup"><span data-stu-id="21f15-156">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="21f15-157">次に `Ctrl`  +  `Shift`  +  `P` **、3D ビューに入力し、[3D ビュー**の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="21f15-157">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="21f15-158">Microsoft では、UI に関する作業を行い、さらに機能を 3D ビューに追加するため、フィードバックをお送り [ください](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="21f15-158">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="21f15-159">Chromium の問題 [#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="21f15-159">Chromium issue [#987787][crbug987787]</span></span>

### <span data-ttu-id="21f15-160">Visual Studio拡張機能</span><span class="sxs-lookup"><span data-stu-id="21f15-160">Visual Studio Code extensions</span></span>  

<span data-ttu-id="21f15-161">DevTools チームには、テキスト エディターから直接 DevTools の機能を利用できる [Visual Studio Code \(VS Code\)][VisualStudioCode] 用の拡張機能もいくつかリリースされています。</span><span class="sxs-lookup"><span data-stu-id="21f15-161">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="21f15-162">下の拡張機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="21f15-162">Check out the extensions below:</span></span>  

#### <span data-ttu-id="21f15-163">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="21f15-163">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="21f15-164">[Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]および VS コード拡張子を追加して、VS コード内から要素ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="21f15-164">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="21f15-165">図 5</span><span class="sxs-lookup"><span data-stu-id="21f15-165">Figure 5</span></span>  
> <span data-ttu-id="21f15-166">Microsoft Edge 拡張機能の要素を使用した VS コード内の要素ツール</span><span class="sxs-lookup"><span data-stu-id="21f15-166">The Elements tool in VS Code using the Elements for Microsoft Edge extension</span></span>  
> ![Microsoft Edge 拡張機能の要素を使用した VS コード内の要素ツール][ImageElementsVisualStudioCode]  

<span data-ttu-id="21f15-168">詳細については [、Microsoft Edge VS コード拡張機能の要素をご覧ください][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="21f15-168">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="21f15-169">Microsoft Edge のデバッガー</span><span class="sxs-lookup"><span data-stu-id="21f15-169">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="21f15-170">Microsoft Edge VS コード [拡張機能][VisualStudioMarketplaceDebuggerEdge] を使用して、VS コードから直接 Microsoft Edge で実行されている JavaScript をデバッグします!</span><span class="sxs-lookup"><span data-stu-id="21f15-170">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="21f15-171">図 6</span><span class="sxs-lookup"><span data-stu-id="21f15-171">Figure 6</span></span>  
> <span data-ttu-id="21f15-172">VS コードの Microsoft Edge 拡張機能のデバッガー</span><span class="sxs-lookup"><span data-stu-id="21f15-172">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS コードの Microsoft Edge 拡張機能のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="21f15-174">詳細については [、VS コードから Microsoft Edge をデバッグする方法を確認してください][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="21f15-174">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="21f15-175">Webhint</span><span class="sxs-lookup"><span data-stu-id="21f15-175">webhint</span></span>  

<span data-ttu-id="21f15-176">Web [ハイント][VisualStudioMarketplaceWebhintExtension] VS コード拡張機能を使用して、Web ページの作成中に Web ページ `webhint` を向上させます。</span><span class="sxs-lookup"><span data-stu-id="21f15-176">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="21f15-177">この拡張機能は分析に基づいてワークスペース ファイルに基づいて診定を実行および `webhint` レポートします。</span><span class="sxs-lookup"><span data-stu-id="21f15-177">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="21f15-178">図 7</span><span class="sxs-lookup"><span data-stu-id="21f15-178">Figure 7</span></span>  
> <span data-ttu-id="21f15-179">VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子</span><span class="sxs-lookup"><span data-stu-id="21f15-179">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![VS コード内の .tsx ファイルを分析する Webhint VS コード拡張子][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="21f15-181">[VS コードウェート拡張機能の詳細をご覧ください][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="21f15-181">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="21f15-182">Visual Studio統合</span><span class="sxs-lookup"><span data-stu-id="21f15-182">Visual Studio integration</span></span>
<span data-ttu-id="21f15-183">Visual Studio 2019 バージョン 16.2 以降では、Visual Studio デバッガーを使用して Microsoft Edge で実行されている JavaScript のデバッグを行います。</span><span class="sxs-lookup"><span data-stu-id="21f15-183">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="21f15-184">[この機能Visual Studioするには、2019][MicrosoftVisualStudioDownloads] をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="21f15-184">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="21f15-185">図 8</span><span class="sxs-lookup"><span data-stu-id="21f15-185">Figure 8</span></span>  
> <span data-ttu-id="21f15-186">Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="21f15-186">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Visual Studio Microsoft Edge Canary、Dev、Beta で Web アプリを起動するオプションを使用する][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="21f15-188">[ブログ投稿を読み、Microsoft Edge を使用して、Microsoft Edge を開発する方法をごVisual Studio。][MicrosoftVisualStudioBlogDebugJavascript]</span><span class="sxs-lookup"><span data-stu-id="21f15-188">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="21f15-189">本体メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="21f15-189">Tracking prevention Console messages</span></span>  

<span data-ttu-id="21f15-190">追跡防止は、Microsoft Edge で、これまでアクセスした Web サイトで追跡されないように保護する固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="21f15-190">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="21f15-191">既定の追跡防止設定は、プライバシーと Web 互換性のバランスを取るエクスペリエンスについてサード パーティのトラッカーと既知の重大なトラッカーをブロックするバランス化モードです。</span><span class="sxs-lookup"><span data-stu-id="21f15-191">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="21f15-192">特定のトラッカーがブロックされたときに Web ページの互換性に関する分け情報を取得できるように、トラッカーがブロックされたときに本体に警告メッセージも追加されています。</span><span class="sxs-lookup"><span data-stu-id="21f15-192">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="21f15-193">図 9</span><span class="sxs-lookup"><span data-stu-id="21f15-193">Figure 9</span></span>  
> <span data-ttu-id="21f15-194">トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="21f15-194">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![トラッカーの記憶域へのアクセスを追跡している場合に本体内のメッセージ][ImageTrackingPrevention]  

<span data-ttu-id="21f15-196">[トラッキング防止の詳細と、][TrackingPrevention]プライバシーと Web 互換性のバランスの残高について説明します。</span><span class="sxs-lookup"><span data-stu-id="21f15-196">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="21f15-197">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="21f15-197">Announcements from the Chromium project</span></span>  

<span data-ttu-id="21f15-198">次のセクションでは、Microsoft Edge 80 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="21f15-198">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="21f15-199">本体でのサポートとクラスの再宣宣表示のサポート</span><span class="sxs-lookup"><span data-stu-id="21f15-199">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="21f15-200">本体では、ステートメントの再宣宣文 `let` が `class` サポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="21f15-200">The Console now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="21f15-201">再展開する機能は、本体を使用して新しい JavaScript コードを実実化している Web 開発者の一般的な発行者の一般的な発行者でした。</span><span class="sxs-lookup"><span data-stu-id="21f15-201">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="21f15-202">本体外または 1 つの本体入力内のスクリプトでスクリプトまたはステートメントを取り換 `let` `class` えた場合でも、引き続きそれを引き換えられます `SyntaxError` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-202">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="21f15-203">前述のとこそ、ローカル変数を再宣例すると `let` 、本体はエラーを脅威にするエラーをトラッキングします。</span><span class="sxs-lookup"><span data-stu-id="21f15-203">For example, previously, when redeclaring a local variable with `let`, the Console threw an error:</span></span>  

> ##### <span data-ttu-id="21f15-204">図 10</span><span class="sxs-lookup"><span data-stu-id="21f15-204">Figure 10</span></span>  
> <span data-ttu-id="21f15-205">Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する</span><span class="sxs-lookup"><span data-stu-id="21f15-205">The Console in Microsoft Edge 79 showing that the let redeclaration fails</span></span>  
> ![Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する][ImageConsoleRedeclarationFails]  

<span data-ttu-id="21f15-207">本体では、本体を再宣計算できます。</span><span class="sxs-lookup"><span data-stu-id="21f15-207">Now, the Console allows the redeclaration:</span></span>  

> ##### <span data-ttu-id="21f15-208">図 11</span><span class="sxs-lookup"><span data-stu-id="21f15-208">Figure 11</span></span>  
> <span data-ttu-id="21f15-209">Microsoft Edge 80 の本体では、再宣宣宣宣宣宣書が成功したものが示されます</span><span class="sxs-lookup"><span data-stu-id="21f15-209">The Console in Microsoft Edge 80 showing that the let redeclaration succeeds</span></span>  
> ![Microsoft Edge 80 の本体では、再宣宣宣宣宣宣書が成功したものが示されます][ImageConsoleRedeclarationSucceeds]  

<span data-ttu-id="21f15-211">Chromium[の問題][crbug1004193]#1004193</span><span class="sxs-lookup"><span data-stu-id="21f15-211">Chromium issue [#1004193][crbug1004193]</span></span>  

### <span data-ttu-id="21f15-212">改善された WebAssembly デバッグ機能が改善されました</span><span class="sxs-lookup"><span data-stu-id="21f15-212">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="21f15-213">DevTools は [DWARF デバッグ標準のサポート][DwarfHome]を開始しました。つまり、DevTools 内のソース言語でのコードの手順の詳細設定、ブレードポイントの設定、スタック トレースの解決に関するサポートが向上しています。</span><span class="sxs-lookup"><span data-stu-id="21f15-213">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### <span data-ttu-id="21f15-214">ネットワーク パネルの更新</span><span class="sxs-lookup"><span data-stu-id="21f15-214">Network panel updates</span></span>  

#### <span data-ttu-id="21f15-215">[イニシアター] タブでイニシアター チェーンを要求する</span><span class="sxs-lookup"><span data-stu-id="21f15-215">Request Initiator Chains in the Initiator tab</span></span>  

<span data-ttu-id="21f15-216">ネットワーク要求の開始者と依存関係を、ネストされたリストとして表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="21f15-216">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="21f15-217">このようにすると、リソースが要求された理や特定のリソース \(スクリプト\など) の原因を理解するのに役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="21f15-217">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

> ##### <span data-ttu-id="21f15-218">図 12</span><span class="sxs-lookup"><span data-stu-id="21f15-218">Figure 12</span></span>  
> <span data-ttu-id="21f15-219">[イニシアター] タブの要求イニシャー チェーン</span><span class="sxs-lookup"><span data-stu-id="21f15-219">A Request Initiator Chain in the Initiator tab</span></span>  
> ![[イニシアター] タブの要求イニシャー チェーン][ImageRequestInitiatorChain]  

<span data-ttu-id="21f15-221">ネットワーク [パネルでネットワーク アクティビティ][DevToolsNetworkIndex]をログ記録した後、リソースをクリックし、[ **開始者** ] タブに移動して、[イニシアタ **ー] タブに移動し、[イニシアター] タブに移動して、[イニシアター の Chainor Chain] を表示します**。</span><span class="sxs-lookup"><span data-stu-id="21f15-221">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="21f15-222">検 **査されたリソースは** 太字です。</span><span class="sxs-lookup"><span data-stu-id="21f15-222">The **inspected resource** is bold.</span></span>  <span data-ttu-id="21f15-223">上のスクリーンショットでは `ai.2.min.js` 、検査されたリソースです。</span><span class="sxs-lookup"><span data-stu-id="21f15-223">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="21f15-224">検査されたリソースの上のリソースはイ **ニシャットです**。</span><span class="sxs-lookup"><span data-stu-id="21f15-224">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="21f15-225">上のスクリーンショットでは `https://www.microsoftedgeinsider.com` 、イニシャーです `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-225">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="21f15-226">つまり、ネットワーク `https://www.microsoftedgeinsider.com` 要求を原因としています `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-226">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="21f15-227">検査されたリソースの下位のリソースは依存 **関係です**。</span><span class="sxs-lookup"><span data-stu-id="21f15-227">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="21f15-228">上のスクリーンショットでは `https://dc.services.visualstudio.com/v2/track` 、依存関係があります `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-228">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="21f15-229">つまり、ネットワーク `ai.2.min.js` 要求を原因としています `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-229">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="21f15-230">開始者と依存関係の情報には、ネットワーク リソースをホストしてからマウス `Shift` でホバーすることでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="21f15-230">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="21f15-231">イ [ニシャリストと依存関係を表示する][DevToolsNetworkReferenceViewInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="21f15-231">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="21f15-232">Chromium の [問題#842488][crbug842488]</span><span class="sxs-lookup"><span data-stu-id="21f15-232">Chromium issue [#842488][crbug842488]</span></span>  

#### <span data-ttu-id="21f15-233">選択したネットワーク要求を概要で強調表示する</span><span class="sxs-lookup"><span data-stu-id="21f15-233">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="21f15-234">ネットワーク リソースをクリックして検査するためにネットワーク リソースをクリックすると、[ネットワーク パネル] の概要で、そのリソースを囲む青い枠線が **表示されるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="21f15-234">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="21f15-235">これは、ネットワーク要求が予定よりも以前またはそれ以降のいかを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21f15-235">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

> ##### <span data-ttu-id="21f15-236">図 13</span><span class="sxs-lookup"><span data-stu-id="21f15-236">Figure 13</span></span>  
> <span data-ttu-id="21f15-237">検査されたリソースが強調表示されている [概要] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="21f15-237">The Overview pane highlighting the inspected resource</span></span>  
> ![検査されたリソースが強調表示されている [概要] ウィンドウ][ImageOverviewPaneInspectedResource]  

<span data-ttu-id="21f15-239">Chromium の [問題#988253][crbug988253]</span><span class="sxs-lookup"><span data-stu-id="21f15-239">Chromium issue [#988253][crbug988253]</span></span>  

#### <span data-ttu-id="21f15-240">[ネットワーク パネル] の URL 列とパス列</span><span class="sxs-lookup"><span data-stu-id="21f15-240">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="21f15-241">ネットワーク パネ**ルの**新**しいパスと URL**列を使用して、各ネットワーク リソースの絶対パスまたは完全な URL を確認します。 **Network**</span><span class="sxs-lookup"><span data-stu-id="21f15-241">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

> ##### <span data-ttu-id="21f15-242">図 14</span><span class="sxs-lookup"><span data-stu-id="21f15-242">Figure 14</span></span>  
> <span data-ttu-id="21f15-243">[ネットワーク パネル] の新しいパスと URL 列</span><span class="sxs-lookup"><span data-stu-id="21f15-243">The new Path and URL columns in the Network panel</span></span>  
> ![[ネットワーク パネル] の新しいパスと URL 列][ImagePathNetworkPanel]  

<span data-ttu-id="21f15-245">ウォーターフォール テーブルの見 **出しを** 右クリックし、[ **パス]** または **[URL]** を選び、新しい列を表示します。</span><span class="sxs-lookup"><span data-stu-id="21f15-245">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="21f15-246">Chromium の [問題#993366][crbug993366]</span><span class="sxs-lookup"><span data-stu-id="21f15-246">Chromium issue [#993366][crbug993366]</span></span>  

#### <span data-ttu-id="21f15-247">ユーザー エージェント文字列が更新されました</span><span class="sxs-lookup"><span data-stu-id="21f15-247">Updated User-Agent strings</span></span>  

<span data-ttu-id="21f15-248">DevTools では、[ネットワーク条件] タブからカスタム ユーザー エージェント **の文字列を設定** できます。 ユーザー エージェント文字列は、ネットワーク リソースに添付された HTTP ヘッダーと値 `User-Agent` に影響します `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="21f15-248">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="21f15-249">定義済みのユーザー エージェント文字列は、最新バージョンのブラウザー バージョンに合うように更新されました。</span><span class="sxs-lookup"><span data-stu-id="21f15-249">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

> ##### <span data-ttu-id="21f15-250">図 15</span><span class="sxs-lookup"><span data-stu-id="21f15-250">Figure 15</span></span>  
> <span data-ttu-id="21f15-251">[ネットワークの状態] タブの [ユーザー エージェント] メニュー</span><span class="sxs-lookup"><span data-stu-id="21f15-251">The User Agent menu in the Network Conditions tab</span></span>  
> ![[ネットワークの状態] タブの [ユーザー エージェント] メニュー][ImageUserAgentNetworkConditionsTab]  

<span data-ttu-id="21f15-253">ネットワークの**条件にアクセスするには、[**[コマンド メニュー] を開き][DevToolsCommandMenuIndex]、コマンドを実行 `Show Network Conditions` します。</span><span class="sxs-lookup"><span data-stu-id="21f15-253">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="21f15-254">デバイス モードでは、 [ユーザー エージェント文字列も設定できます][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="21f15-254">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="21f15-255">Chromium の問題は、chromium [の#1029031][crbug1029031]</span><span class="sxs-lookup"><span data-stu-id="21f15-255">Chromium issue [#1029031][crbug1029031]</span></span>  

### <span data-ttu-id="21f15-256">監査パネルの更新</span><span class="sxs-lookup"><span data-stu-id="21f15-256">Audits panel updates</span></span>  

#### <span data-ttu-id="21f15-257">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="21f15-257">New configuration UI</span></span>  

<span data-ttu-id="21f15-258">構成 UI には、新しく応答性が高く、構成オプションが簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="21f15-258">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="21f15-259">サ [イドロットの][GitHubGoogleChromeDevToolsAuditsPanelThrottling] UI の変更の詳細については、[監査パネル] のサンプルのサタントリングを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21f15-259">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

> ##### <span data-ttu-id="21f15-260">図 16</span><span class="sxs-lookup"><span data-stu-id="21f15-260">Figure 16</span></span>  
> <span data-ttu-id="21f15-261">新しい構成 UI</span><span class="sxs-lookup"><span data-stu-id="21f15-261">The new configuration UI</span></span>  
> ![新しい構成 UI][ImageConfigurationUI]  

### <span data-ttu-id="21f15-263">カバレージ タブの更新</span><span class="sxs-lookup"><span data-stu-id="21f15-263">Coverage tab updates</span></span>  

#### <span data-ttu-id="21f15-264">機能ごとまたはブロックごとのカバレッジ モード</span><span class="sxs-lookup"><span data-stu-id="21f15-264">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="21f15-265">[[カバレージ][DevToolsCoverageIndex]] タブには、関数ごと、ブロックごとのコードカバレッジ データを収集するかどうかを指定できる**新しいドロップダウン\*\*\*\*メニューがあります**。</span><span class="sxs-lookup"><span data-stu-id="21f15-265">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="21f15-266">**ブロックご** との範囲ごとの詳細は、さらに詳しくあり、収集の高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="21f15-266">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="21f15-267">DevTools では既定で **関数ご** との範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="21f15-267">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="21f15-268">HTML ファイルでの大規模なコードの違いは、関数ごとの使用頻度とブロック モードのど **れ** で **使用されるかによって異** なります。</span><span class="sxs-lookup"><span data-stu-id="21f15-268">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="21f15-269">関数モード **で使用すると** 、HTML ファイルのインライン スクリプトは関数としては計算されます。</span><span class="sxs-lookup"><span data-stu-id="21f15-269">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="21f15-270">スクリプトがすべて実行される場合、DevTools は、スクリプト全体をコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="21f15-270">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="21f15-271">スクリプトがまったく実行されない場合にのみ、スクリプトは未使用コードとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="21f15-271">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

> ##### <span data-ttu-id="21f15-272">図 17</span><span class="sxs-lookup"><span data-stu-id="21f15-272">Figure 17</span></span>  
> <span data-ttu-id="21f15-273">カバレッジ モードのドロップダウン メニュー</span><span class="sxs-lookup"><span data-stu-id="21f15-273">The coverage mode dropdown menu</span></span>  
> ![カバレッジ モードのドロップダウン メニュー][ImageCoverageMode]  

#### <span data-ttu-id="21f15-275">カバレージをページ再読み込みで開始する必要がある</span><span class="sxs-lookup"><span data-stu-id="21f15-275">Coverage must now be initiated by a page reload</span></span>  

<span data-ttu-id="21f15-276">カバレッジ データが不合成になったためにページ再読み込みを行わないようにコード カバーを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="21f15-276">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="21f15-277">たとえば、ランタイムが長い時間が過ぎていて、V8 ガーバンド コレクターがクリーンアップした場合、関数を未使用として報告できます。</span><span class="sxs-lookup"><span data-stu-id="21f15-277">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="21f15-278">Chromium の問題は、chromium [の#1004203][crbug1004203]</span><span class="sxs-lookup"><span data-stu-id="21f15-278">Chromium issue [#1004203][crbug1004203]</span></span>  

## <span data-ttu-id="21f15-279">Microsoft Edge のプレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="21f15-279">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="21f15-280">Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。</span><span class="sxs-lookup"><span data-stu-id="21f15-280">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="21f15-281">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="21f15-281">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="21f15-282">Microsoft Edge DevTools チームとのつながりを手にする</span><span class="sxs-lookup"><span data-stu-id="21f15-282">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "図 1: キーボード ナビゲーションとスクリーン リーダーの機能強化を使用して DevTools のパフォーマンス ツール"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "図 3: Web ホント ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "図 4: Microsoft Edge DevTools の 3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "図 5: Microsoft Edge 拡張機能の要素を使用して VS コード内の要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "図 6:VS コードの Microsoft Edge 拡張機能のデバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "図 7: VS コードで .tsx ファイルを分析する Webhint VS コード拡張子"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "図 8: Microsoft Edge Canary Visual Studio、Dev、Beta で Web アプリを起動するオプションが表示された"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "図 9: トラッカーの記憶域へのアクセスがブロックされている場合に本体内のメッセージ"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "図 10: Microsoft Edge 79 の本体では、再宣宣宣宣書が失敗する"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "図 11: Microsoft Edge 80 の本体が、再宣宣宣宣の成功を示す Microsoft Edge 80 の本体"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "図 12: [イニシアター] タブの要求イニシアター チェーン"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "図 13: 検査されたリソースが強調表示されている [概要] ウィンドウ"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "図 14: [ネットワーク パネル] の新しいパスと URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "図 15: [ネットワーク条件] タブの [ユーザー エージェント] メニュー"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "図 16:新しい構成 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "図 17: カバレッジ モードのドロップダウン メニュー"  

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンド メニューでコマンドを実行する"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "Microsoft Edge DevTools の [Coverage] タブで未使用の JavaScript および CSS 番号を検索する"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "モバイル ビューポートをシイクルする - Microsoft Edge DevTools のデバイス モードを使用してモバイル デバイスをシイクル化する"  
[DevToolsNetworkIndex]: ../../../network/index.md "Microsoft Edge DevTools でのネットワーク アクティビティの検査"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "イニシャリストと依存関係を表示する - ネットワーク分析参照"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML の新機能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張機能のデバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張機能の要素"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488 - [イニシアター] フィールドを [ヘッダー] タブ - モナリ"  
[crbug988253]: https://crbug.com/988253 "988253 - バグのデバッグ デバッグデーション - ネットワーク要求とタイムライン グラフの間の関連付けなし - モノラル"  
[crbug993366]: https://crbug.com/993366 "993366 - ネットワーク パネル要求一覧に URL のパスの一部を表示してください - モナール"  
[crbug1004193]: https://crbug.com/1004193 "1004193 - V8 - モナールの REPL モード"  
[crbug1004203]: https://crbug.com/1004203 "1004203 - モナール"  
[crbug1029031]: https://crbug.com/1029031 "1029031 - UA 文字列が最新のものになりました - モナール" 
[crbug963183]: https://crbug.com/963183 "963183 - DevTools は WCAG に準格していません"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools のローカライズ性"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D ビュー"

[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティ インサイト"  

[DwarfHome]: https://dwarfstd.org "Dwarf Home"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools' Audits Panel Throttling - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題 - MicrosoftDocs/edge 開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider アドオン"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "Visual Studio |Visual Studioブログ"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Windows \& Mac Visual Studio 2019 for Windows のダウンロード"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメント オブジェクト モデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "Twitter アカウント@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studioコード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge のデバッガー - マVisual Studio市"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) - マーケットプレーVisual Studioース"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "Webhint - マーケットプレVisual Studioプレース"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Web ハイント ブラウザー拡張 |Webhint ドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |Webhint ドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿に追跡防止を行う"
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"

> [!NOTE]
> <span data-ttu-id="21f15-339">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="21f15-339">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="21f15-340">元のページがここに [あ](https://developers.google.com/web/updates/2019/12/devtools/index) り [、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools & Lighthouse\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="21f15-340">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="21f15-342">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="21f15-342">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
