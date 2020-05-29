---
title: DevTools の新機能 (Microsoft Edge 81)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6de8f7b11edb476f2656dd6f16e02413b1873ed8
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684714"
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







# <span data-ttu-id="fb54e-103">DevTools の新機能 (Microsoft Edge 81)</span><span class="sxs-lookup"><span data-stu-id="fb54e-103">What's New In DevTools (Microsoft Edge 81)</span></span>   



## <span data-ttu-id="fb54e-104">Microsoft Edge DevTools チームからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="fb54e-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="fb54e-105">以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="fb54e-106">これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="fb54e-107">開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="fb54e-108">DevTools のアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="fb54e-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="fb54e-109">DevTools チームは、Chromium に170の変更を加え、色のコントラスト、キーボード、スクリーンリーダーに関する大きな問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="fb54e-110">Web を構築するすべての開発者は、DevTools を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb54e-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="fb54e-111">図 1</span><span class="sxs-lookup"><span data-stu-id="fb54e-111">Figure 1</span></span>  
> <span data-ttu-id="fb54e-112">キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール</span><span class="sxs-lookup"><span data-stu-id="fb54e-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![キーボードナビゲーションとスクリーンリーダーの改良による DevTools のパフォーマンスツール][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="fb54e-114">すべてのユーザーが web ページにアクセスできるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="fb54e-115">使用を開始するには、Microsoft Edge のアクセシビリティに関する[洞察][AccessibilityInsights]と[webhint][WebhintBrowserExtension]の拡張機能をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="fb54e-116">スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、[ツイート][PostTweetEdgeDevTools]または[フィードバック](#feedback)アイコンをクリックして、フィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="fb54e-117">Chromium の問題[#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="fb54e-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="fb54e-118">他の言語での DevTools の使用</span><span class="sxs-lookup"><span data-stu-id="fb54e-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="fb54e-119">多くの開発者は、英語だけでなく、StackOverflow や VS コードなどの他の開発者ツールをネイティブ言語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="fb54e-120">ここでは、開発ツールのローカライズについて説明します。ここでは、英語以外の10言語のいずれかで使用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="fb54e-121">中国語 \ (簡体字)- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="fb54e-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb54e-122">中国語 (繁体字)- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="fb54e-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="fb54e-123">フランス語– fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="fb54e-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb54e-124">ドイツ語-deutsch</span><span class="sxs-lookup"><span data-stu-id="fb54e-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="fb54e-125">イタリア語-italiano</span><span class="sxs-lookup"><span data-stu-id="fb54e-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb54e-126">日本語- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="fb54e-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="fb54e-127">韓国語- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="fb54e-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb54e-128">ポルトガル語-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="fb54e-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="fb54e-129">ロシア語–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="fb54e-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="fb54e-130">スペイン語-&#241;ol</span><span class="sxs-lookup"><span data-stu-id="fb54e-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="fb54e-131">DevTools は、Microsoft Edge で使用する言語と自動的に一致し `edge://settings/languages` ます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="fb54e-132">Microsoft Edge を1つの言語で使用し、DevTools を英語のままにしておく場合は、 `F1` DevTools を押して [[設定][Settings]] を開き、[**ブラウザー言語の一致**] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

> ##### <span data-ttu-id="fb54e-133">図 2</span><span class="sxs-lookup"><span data-stu-id="fb54e-133">Figure 2</span></span>  
> <span data-ttu-id="fb54e-134">ドイツ語の DevTools</span><span class="sxs-lookup"><span data-stu-id="fb54e-134">The DevTools in German</span></span>  
> ![ドイツ語の DevTools][ImageLocalizedGerman]  

<span data-ttu-id="fb54e-136">**コンソール**メッセージはローカライズされません。</span><span class="sxs-lookup"><span data-stu-id="fb54e-136">**Console** messages are not localized.</span></span>  <span data-ttu-id="fb54e-137">DevTools UI で使用されている文字列のみが、Microsoft Edge で使用する言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-137">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="fb54e-138">使用可能な言語とは異なる言語で DevTools を使う場合は、[ツイート][PostTweetEdgeDevTools]にサインインするか、[フィードバック](#feedback)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Feedback](#feedback) icon.</span></span>  

<span data-ttu-id="fb54e-139">Chromium の問題[#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="fb54e-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="fb54e-140">webhint Microsoft Edge extension</span><span class="sxs-lookup"><span data-stu-id="fb54e-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="fb54e-141">Webhint Microsoft Edge 拡張機能を使用すると、web ページを簡単にスキャンして、開発ツールでアクセシビリティ、ブラウザーの互換性、セキュリティ、パフォーマンスなどのフィードバックを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="fb54e-142">詳細はこちら [https://webhint.io][Webhint] をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="fb54e-143">図 3</span><span class="sxs-lookup"><span data-stu-id="fb54e-143">Figure 3</span></span>  
> <span data-ttu-id="fb54e-144">Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ</span><span class="sxs-lookup"><span data-stu-id="fb54e-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![Webhint ブラウザー拡張機能がインストールされている場合の DevTools の [ヒント] タブ][ImageHintsTabWebhintExtension]  

<span data-ttu-id="fb54e-146">[Microsoft Edge で webhint ブラウザーの拡張機能を試してみてください][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="fb54e-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="fb54e-147">拡張機能をインストールしたら、DevTools を開いて、[ヒント] タブを選択します。 ここで、カスタマイズ可能なサイトスキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="fb54e-148">詳細については、 [webhint.io][WebhintBrowserExtension]にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="fb54e-149">3D View (3D ビュー)</span><span class="sxs-lookup"><span data-stu-id="fb54e-149">3D View</span></span>  

<span data-ttu-id="fb54e-150">**3D ビュー**を使って、[ドキュメントオブジェクトモデル \ (DOM \)][MDNDocumentObjectModel]または[z インデックス][MDNZIndex]スタッキングのコンテキストを移動して、web アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="fb54e-151">図 4</span><span class="sxs-lookup"><span data-stu-id="fb54e-151">Figure 4</span></span>  
> <span data-ttu-id="fb54e-152">DevTools の3D ビュー</span><span class="sxs-lookup"><span data-stu-id="fb54e-152">The 3D View in the DevTools</span></span>  
> ![DevTools の3D ビュー][Image3DView]  

<span data-ttu-id="fb54e-154">3d ビューにアクセスするには、キーを押して `Ctrl`  +  `Shift`  +  `P` **3d ビュー**で入力し、[ **3d ビューの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-154">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="fb54e-155">現在、UI を使って3D ビューに機能を追加していますので、[フィードバック](#feedback)をお送りください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-155">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#feedback).</span></span>  

<span data-ttu-id="fb54e-156">Chromium の問題[#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="fb54e-156">Chromium issue [#987787][crbug987787]</span></span>  

### <span data-ttu-id="fb54e-157">Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="fb54e-157">Visual Studio Code extensions</span></span>  

<span data-ttu-id="fb54e-158">[Visual Studio コード \ (VS コード \)][VisualStudioCode]用の一部の拡張機能がリリースされました。この機能を使って、テキストエディターから、開発者ツールの機能を直接使うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-158">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="fb54e-159">以下の拡張子を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-159">Check out the extensions below:</span></span>  

#### <span data-ttu-id="fb54e-160">Microsoft Edge の要素</span><span class="sxs-lookup"><span data-stu-id="fb54e-160">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="fb54e-161">[Microsoft Edge \ (Chromium \)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] vs コード拡張の要素を追加して、vs コード内の要素ツールを使います。</span><span class="sxs-lookup"><span data-stu-id="fb54e-161">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="fb54e-162">図 5</span><span class="sxs-lookup"><span data-stu-id="fb54e-162">Figure 5</span></span>  
> <span data-ttu-id="fb54e-163">Microsoft Edge の要素を使用した VS コードの要素ツールは、 ![ Microsoft edge extension の要素を使って Vs コードの要素ツールを拡張します。][ImageElementsVisualStudioCode]</span><span class="sxs-lookup"><span data-stu-id="fb54e-163">The Elements tool in VS Code using the Elements for Microsoft Edge extension ![The Elements tool in VS Code using the Elements for Microsoft Edge extension][ImageElementsVisualStudioCode]</span></span>  

<span data-ttu-id="fb54e-164">詳細については、「 [Microsoft EDGE VS コード拡張の要素][VisualStudioCodeElementEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-164">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="fb54e-165">Microsoft Edge 用デバッガー</span><span class="sxs-lookup"><span data-stu-id="fb54e-165">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="fb54e-166">[Microsoft edge vs のコード拡張用デバッガー][VisualStudioMarketplaceDebuggerEdge]を使って、microsoft edge で実行されている JAVASCRIPT を vs コードから直接デバッグします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-166">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="fb54e-167">図 6</span><span class="sxs-lookup"><span data-stu-id="fb54e-167">Figure 6</span></span>  
> <span data-ttu-id="fb54e-168">VS コードの Microsoft Edge Extension のデバッガー</span><span class="sxs-lookup"><span data-stu-id="fb54e-168">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS コードの Microsoft Edge Extension のデバッガー][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="fb54e-170">詳細については、「 [VS コードから Microsoft Edge をデバッグする方法][VisualStudioCodeDebuggerEdgeExtension]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-170">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="fb54e-171">web ヒント</span><span class="sxs-lookup"><span data-stu-id="fb54e-171">webhint</span></span>  

<span data-ttu-id="fb54e-172">Web ページを作成しているときに、web ページの品質を向上させるために、 [webhint][VisualStudioMarketplaceWebhintExtension] VS コード拡張を使います。 `webhint`</span><span class="sxs-lookup"><span data-stu-id="fb54e-172">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="fb54e-173">この拡張機能は、分析に基づいて、ワークスペースファイルで診断を実行して報告し `webhint` ます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="fb54e-174">図 7</span><span class="sxs-lookup"><span data-stu-id="fb54e-174">Figure 7</span></span>  
> <span data-ttu-id="fb54e-175">VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="fb54e-175">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![VS コードでの tsx ファイルの分析のための webhint VS コード拡張機能][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="fb54e-177">[詳細については、「VS コード webhint 拡張機能」を参照して][WebhintVisualStudioCodeExtension]ください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-177">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="fb54e-178">Visual Studio との統合</span><span class="sxs-lookup"><span data-stu-id="fb54e-178">Visual Studio integration</span></span>  

<span data-ttu-id="fb54e-179">Visual Studio 2019 バージョン16.2 以降では、Visual Studio デバッガーを使って、Microsoft Edge で実行されている JavaScript をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-179">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="fb54e-180">この機能を試すには、 [Visual Studio 2019 をダウンロード][MicrosoftVisualStudioDownloads]してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-180">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="fb54e-181">図 8</span><span class="sxs-lookup"><span data-stu-id="fb54e-181">Figure 8</span></span>  
> <span data-ttu-id="fb54e-182">Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb54e-182">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="fb54e-184">[詳細については、「Visual Studio からの Microsoft Edge のデバッグ」を参照して][MicrosoftVisualStudio]ください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-184">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="fb54e-185">防止コンソールのメッセージを追跡する</span><span class="sxs-lookup"><span data-stu-id="fb54e-185">Tracking prevention Console messages</span></span>  

<span data-ttu-id="fb54e-186">追跡防止は、以前にアクセスしていない web サイトによって管理されることを防ぐ、Microsoft Edge の固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="fb54e-186">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="fb54e-187">既定の追跡防止設定はバランスモードで、サードパーティのトラッカーと既知の悪意のあるトラッカーが、プライバシーと web の互換性のバランスを保つためにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-187">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="fb54e-188">特定のトラッカーがブロックされているときに、web ページの互換性をさらに把握できるように、トラッカーがブロックされたときに、コンソールでも警告メッセージが追加されています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-188">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="fb54e-189">図 9</span><span class="sxs-lookup"><span data-stu-id="fb54e-189">Figure 9</span></span>  
> <span data-ttu-id="fb54e-190">予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-190">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![予防を追跡するときに本体に表示されるメッセージは、トラッカーの記憶域へのアクセスをブロックします。][ImageTrackingPrevention]  

<span data-ttu-id="fb54e-192">[詳細については、「プライバシーと web の互換性のバランスを管理する」を参照して][TrackingPrevention]ください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-192">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>



## <span data-ttu-id="fb54e-193">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="fb54e-193">Announcements from the Chromium project</span></span>  

<span data-ttu-id="fb54e-194">次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 81 で利用可能なその他の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-194">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="fb54e-195">デバイスモードでの Moto G4 のサポート</span><span class="sxs-lookup"><span data-stu-id="fb54e-195">Moto G4 support in Device Mode</span></span> 

<span data-ttu-id="fb54e-196">[デバイスのツールバーを有効][DeviceToolbar]にした後、**デバイス**の一覧から Moto G4 のビューポートのサイズをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-196">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

> ##### <span data-ttu-id="fb54e-197">図 10</span><span class="sxs-lookup"><span data-stu-id="fb54e-197">Figure 10</span></span>  
> <span data-ttu-id="fb54e-198">Moto G4 のビューポートのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="fb54e-198">Simulating a Moto G4 viewport</span></span>  
> ![Moto G4 のビューポートのシミュレーション][ImageMotoG4]  

<span data-ttu-id="fb54e-200">[[デバイスフレームの表示][DeviceFrame]] をクリックして、ビューポートの周りに Moto G4 のハードウェアを表示します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-200">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

> ##### <span data-ttu-id="fb54e-201">図 11</span><span class="sxs-lookup"><span data-stu-id="fb54e-201">Figure 11</span></span>  
> <span data-ttu-id="fb54e-202">Moto G4 のハードウェアの表示</span><span class="sxs-lookup"><span data-stu-id="fb54e-202">Showing the Moto G4 hardware</span></span>  
> ![Moto G4 のハードウェアの表示][ImageMotoG4Frame]  

<span data-ttu-id="fb54e-204">関連する機能:</span><span class="sxs-lookup"><span data-stu-id="fb54e-204">Related features:</span></span>  

*   <span data-ttu-id="fb54e-205">[コマンドメニュー][CommandMenu]を開き、コマンドを実行して、 `Capture screenshot` Moto G4 ハードウェアを含むビューポートのスクリーンショットを撮ります ([**デバイスの表示] フレームを**有効にした後)。</span><span class="sxs-lookup"><span data-stu-id="fb54e-205">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="fb54e-206">[ネットワークと CPU を調整][ThrottleNetworkAndCpu]して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="fb54e-206">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="fb54e-207">Chromium の問題[#924693][crbug924693]</span><span class="sxs-lookup"><span data-stu-id="fb54e-207">Chromium issue [#924693][crbug924693]</span></span>  

### <span data-ttu-id="fb54e-208">Cookie 関連の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="fb54e-208">Cookie-related updates</span></span>   

#### <span data-ttu-id="fb54e-209">[Cookie] ウィンドウでブロックされた cookie</span><span class="sxs-lookup"><span data-stu-id="fb54e-209">Blocked cookies in the Cookies pane</span></span>   

<span data-ttu-id="fb54e-210">アプリケーションパネルの [Cookie] ウィンドウに、ブロックされている cookie と黄色の背景が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb54e-210">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

> ##### <span data-ttu-id="fb54e-211">図 12</span><span class="sxs-lookup"><span data-stu-id="fb54e-211">Figure 12</span></span>  
> <span data-ttu-id="fb54e-212">アプリケーションパネルの Cookie ウィンドウのブロックされた cookie</span><span class="sxs-lookup"><span data-stu-id="fb54e-212">Blocked cookies in the Cookies pane of the Application panel</span></span>  
> ![アプリケーションパネルの Cookie ウィンドウのブロックされた cookie][ImageBlockedCookies]  

<span data-ttu-id="fb54e-214">Chromium の問題[#1030258][crbug|::ref1::|]</span><span class="sxs-lookup"><span data-stu-id="fb54e-214">Chromium issue [#1030258][crbug|::ref1::|]</span></span>  

#### <span data-ttu-id="fb54e-215">Cookie ウィンドウの cookie の優先度</span><span class="sxs-lookup"><span data-stu-id="fb54e-215">Cookie priority in the Cookie pane</span></span>   

<span data-ttu-id="fb54e-216">[ネットワーク] および [アプリケーション] パネルの [Cookie] テーブルに、**優先度**列が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb54e-216">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="fb54e-217">Chromium ベースのブラウザー (Microsoft Edge など) は、cookie の優先順位をサポートしている唯一のブラウザーです。</span><span class="sxs-lookup"><span data-stu-id="fb54e-217">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="fb54e-218">Chromium の問題[#1026879][crbug1026879]</span><span class="sxs-lookup"><span data-stu-id="fb54e-218">Chromium issue [#1026879][crbug1026879]</span></span>  

#### <span data-ttu-id="fb54e-219">すべての cookie 値を編集する</span><span class="sxs-lookup"><span data-stu-id="fb54e-219">Edit all cookie values</span></span>   

<span data-ttu-id="fb54e-220">Cookie テーブル内のすべてのセルは、[**サイズ**] 列のセルを除いて編集できるようになりました。この列は、cookie のネットワークサイズ (バイト単位) を表しているためです。</span><span class="sxs-lookup"><span data-stu-id="fb54e-220">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="fb54e-221">各列の説明については、「[フィールド][CookiesFields]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-221">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

> ##### <span data-ttu-id="fb54e-222">図 13</span><span class="sxs-lookup"><span data-stu-id="fb54e-222">Figure 13</span></span>  
> <span data-ttu-id="fb54e-223">Cookie の値を編集する</span><span class="sxs-lookup"><span data-stu-id="fb54e-223">Editing a cookie value</span></span>  
> ![Cookie の値を編集する][ImageEditCookie]  

#### <span data-ttu-id="fb54e-225">.Js を取得して cookie データを含めるようにする</span><span class="sxs-lookup"><span data-stu-id="fb54e-225">Copy as Node.js fetch to include cookie data</span></span>   

<span data-ttu-id="fb54e-226">ネットワーク要求を右クリックし、[コピー**コピー] を選択し**  >  て、cookie データを含む式を取得し**ます。** `fetch`</span><span class="sxs-lookup"><span data-stu-id="fb54e-226">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

> ##### <span data-ttu-id="fb54e-227">図 14</span><span class="sxs-lookup"><span data-stu-id="fb54e-227">Figure 14</span></span>  
> <span data-ttu-id="fb54e-228">.Js の取得としてコピーする</span><span class="sxs-lookup"><span data-stu-id="fb54e-228">Copy as Node.js fetch</span></span>  
> ![.Js の取得としてコピーする][ImageCopyFetch]  

<span data-ttu-id="fb54e-230">Chromium の問題[#1029826][crbug1029826]</span><span class="sxs-lookup"><span data-stu-id="fb54e-230">Chromium issue [#1029826][crbug1029826]</span></span>  

### <span data-ttu-id="fb54e-231">より正確な web アプリマニフェストアイコン</span><span class="sxs-lookup"><span data-stu-id="fb54e-231">More accurate web app manifest icons</span></span>   

<span data-ttu-id="fb54e-232">以前は、アプリケーションパネルのマニフェストウィンドウは、web アプリマニフェストのアイコンを表示するために、独自の要求を送信しました。</span><span class="sxs-lookup"><span data-stu-id="fb54e-232">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="fb54e-233">DevTools には、Microsoft Edge で使用するマニフェストアイコンとまったく同じものが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb54e-233">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

> ##### <span data-ttu-id="fb54e-234">図 15</span><span class="sxs-lookup"><span data-stu-id="fb54e-234">Figure 15</span></span>  
> <span data-ttu-id="fb54e-235">[マニフェスト] ウィンドウのアイコン</span><span class="sxs-lookup"><span data-stu-id="fb54e-235">Icons in the Manifest pane</span></span>  
> ![[マニフェスト] ウィンドウのアイコン][ImageManifestIcon]   

<span data-ttu-id="fb54e-237">Chromium の問題[#985402][crbug985402]</span><span class="sxs-lookup"><span data-stu-id="fb54e-237">Chromium issue [#985402][crbug985402]</span></span>  

### <span data-ttu-id="fb54e-238">CSS コンテンツプロパティの上にマウスポインターを移動して、エスケープ解除した値を表示する</span><span class="sxs-lookup"><span data-stu-id="fb54e-238">Hover over CSS content properties to see unescaped values</span></span>   

<span data-ttu-id="fb54e-239">プロパティの値の上にマウスポインターを置くと、 `content` 値のエスケープ解除されたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-239">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="fb54e-240">たとえば、この[デモ][CSSContentDemo]では、擬似要素を調べると、 `p::after` [スタイル] ウィンドウにエスケープされた文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-240">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

> ##### <span data-ttu-id="fb54e-241">図 16</span><span class="sxs-lookup"><span data-stu-id="fb54e-241">Figure 16</span></span>  
> <span data-ttu-id="fb54e-242">エスケープされた文字列</span><span class="sxs-lookup"><span data-stu-id="fb54e-242">The escaped string</span></span>  
> ![エスケープされた文字列][ImageEscapedString]   

<span data-ttu-id="fb54e-244">値の上にマウスポインターを置くと `content` 、エスケープされていない値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-244">When you hover over the `content` value you see the unescaped value:</span></span>  

> ##### <span data-ttu-id="fb54e-245">図 17</span><span class="sxs-lookup"><span data-stu-id="fb54e-245">Figure 17</span></span>  
> <span data-ttu-id="fb54e-246">エスケープされていない値</span><span class="sxs-lookup"><span data-stu-id="fb54e-246">The unescaped value</span></span>  
> ![エスケープされていない値][ImageUnescapedString]   

### <span data-ttu-id="fb54e-248">本体の詳細なソースマップのエラー</span><span class="sxs-lookup"><span data-stu-id="fb54e-248">More detailed source map errors in the Console</span></span>   

<span data-ttu-id="fb54e-249">これで、本体のマップで読み込みまたは解析に失敗した理由について、コンソールで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-249">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="fb54e-250">以前は、問題の原因を説明せずにエラーが表示されました。</span><span class="sxs-lookup"><span data-stu-id="fb54e-250">Previously it just provided an error without explaining what went wrong.</span></span>  

> ##### <span data-ttu-id="fb54e-251">図18</span><span class="sxs-lookup"><span data-stu-id="fb54e-251">Figure 18</span></span>  
> <span data-ttu-id="fb54e-252">本体でのソースマップ読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="fb54e-252">A source map loading error in the Console</span></span>  
> ![本体でのソースマップ読み込みエラー][ImageSourcemapError]  

### <span data-ttu-id="fb54e-254">ファイルの末尾を超えてスクロールを無効にする設定</span><span class="sxs-lookup"><span data-stu-id="fb54e-254">Setting for disabling scrolling past the end of a file</span></span>   

<span data-ttu-id="fb54e-255">[設定][Settings]を開いて、 **[設定] を無効**  >  **Sources**  >  にします。 [**ファイルの最後までスクロール**する] では、[**ソース**] パネルでファイルの末尾を超えてスクロールできる既定の UI 動作を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-255">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

> ##### <span data-ttu-id="fb54e-256">図19</span><span class="sxs-lookup"><span data-stu-id="fb54e-256">Figure 19</span></span>  
> <span data-ttu-id="fb54e-257">[設定] で [**ファイルの最後までスクロールを許可する**] を無効にする</span><span class="sxs-lookup"><span data-stu-id="fb54e-257">Disabling **Allow scrolling past end of file** in Settings</span></span>  
> ![ファイルの最後までのスクロールを無効にする][ImageSettings]  

> ##### <span data-ttu-id="fb54e-259">図20</span><span class="sxs-lookup"><span data-stu-id="fb54e-259">Figure 20</span></span>  
> <span data-ttu-id="fb54e-260">ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました</span><span class="sxs-lookup"><span data-stu-id="fb54e-260">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
> ![ソースパネルでは、ファイルの末尾を超えてスクロールすることができなくなりました][ImageScroll]  

## <span data-ttu-id="fb54e-262">フィードバック</span><span class="sxs-lookup"><span data-stu-id="fb54e-262">Feedback</span></span>   



<span data-ttu-id="fb54e-263">この投稿の新機能や変更点について、または DevTools に関連するその他のものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-263">To discuss the new features and changes in this post, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="fb54e-264">DevTools の**フィードバック**アイコンを使ってフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="fb54e-264">Send your feedback using the **Feedback** icon in the DevTools</span></span>  

> ##### <span data-ttu-id="fb54e-265">図21</span><span class="sxs-lookup"><span data-stu-id="fb54e-265">Figure 21</span></span>  
> <span data-ttu-id="fb54e-266">Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="fb54e-266">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
> ![Microsoft Edge DevTools の \* \* フィードバック \* \* アイコン][ImageFeedbackIcon]  

*   <span data-ttu-id="fb54e-268">[@EdgeDevTools][PostTweetEdgeDevTools]ツイート</span><span class="sxs-lookup"><span data-stu-id="fb54e-268">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
*   <span data-ttu-id="fb54e-269">[目的の Web サイト][TheWebWeWant]に提案を送信する</span><span class="sxs-lookup"><span data-stu-id="fb54e-269">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
*   <span data-ttu-id="fb54e-270">[エッジ開発者][GitHubMicrosoftDocsEdgeDeveloperNewIssue]リポジトリでこのドキュメントのバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="fb54e-270">File bugs on this document in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

## <span data-ttu-id="fb54e-271">Microsoft Edge preview チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="fb54e-271">Download the Microsoft Edge preview channels</span></span>   

<span data-ttu-id="fb54e-272">Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]を既定の開発ブラウザーとして使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fb54e-272">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="fb54e-273">プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-273">The preview channels give you access to the latest DevTools features.</span></span>  

<!-- <<../../_shared/devtools-feedback.md>>

<<../../_shared/canary.md>>

<<../../_shared/discover.md>> -->



<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "図 1: キーボードナビゲーションとスクリーンリーダーの機能強化による DevTools のパフォーマンスツール"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "図 2: ドイツ語の DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "図 3: webhint ブラウザー拡張機能がインストールされている場合の Microsoft Edge DevTools の [ヒント] タブ"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "図 4: Microsoft Edge DevTools の3D ビュー"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "図 5: Microsoft Edge Extension の要素を使用した VS コードの要素ツール"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "図 6: VS コードの Microsoft Edge Extension 用デバッガー"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "図 7: web ヒント VS コード拡張機能 (VS コードでの tsx ファイルの分析)"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "図 8: Microsoft Edge カナリア、Dev、またはベータ版で web アプリを起動するオプションが表示された Visual Studio"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "図 9: 予防を追跡するときに本体に表示されるメッセージによって、トラッカーの記憶域へのアクセスがブロックされる" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "図 10: Moto G4 のビューポートのシミュレート" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "図 11: Moto G4 ハードウェアの表示" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "図 12: アプリケーションパネルの Cookie ウィンドウでブロックされた cookie"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "図 13: cookie の値を編集する"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "図 14: .js の取得としてコピーする"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "図 15: [マニフェスト] ウィンドウのアイコン"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "図 16: エスケープされた文字列"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "図 17: エスケープされていない値"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "図 18: 本体のソースマップ読み込みエラー"
[ImageSettings]: ../../images/2020/01/settings.msft.png "図 19: [設定] の [ファイルの最後までのスクロールを許可する] を無効にする"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "図 20: [ソース] パネルでファイルの末尾を超えてスクロールできるようになりました"
[ImageFeedbackIcon]: ../../images/2020/01/feedback-icon.msft.png "図 21: Microsoft Edge DevTools の * * フィードバック * * アイコン"


<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイスモードでモバイルビューポートをシミュレートする"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "[デバイスフレームの表示] を選択して、ビューポートの周りに物理デバイスフレームを表示します。"
[CommandMenu]: ../../../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "ネットワークと CPU を調整して、モバイルユーザーの web 閲覧条件をより正確にシミュレートします。"
[crbug924693]: https://crbug.com/924693 "924693: 機能の要求: Moto G4 をデバイスモードリストに追加する"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879: dev 本体の [Cookie] タブに優先度が表示されない"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookies テーブルのフィールド"
[crbug1029826]: https://crbug.com/1029826 "1029826: [ネットワーク] タブ-> 右クリックによるコピーの要求-> のコピー > フェッチでは cookie をコピーできません"
[crbug985402]: https://crbug.com/985402 "985402: web アプリマニフェストアイコンのエラー文字列がわかりにくくなっている"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "エスケープ解除した CSS コンテンツのデモ"
[Settings]: ../../../customize/index.md#settings "設定を使用して Microsoft Edge DevTools をカスタマイズする"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge VS コード拡張用デバッガー"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge VS コード拡張の要素"  
[crbug963183]: https://crbug.com/963183 "963183-DevTools は WCAG に準拠していません"
[crbug941561]: https://crbug.com/941561 "941561-DevTools のローカライズ可能性"
[crbug987787]: https://crbug.com/987787 "987787-Dom 3D ビュー"
[AccessibilityInsights]: https://aka.ms/a11yinsights "アクセシビリティの分析"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider のアドオン"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "Visual Studio 2019 for Windows & Mac をダウンロードする"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "ドキュメントオブジェクトモデル (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z インデックス |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio コード"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 用デバッガー-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium) の要素: Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "web ヒント"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint ブラウザ拡張 |webhint に関するドキュメント"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint VS コード拡張 |webhint に関するドキュメント"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "Microsoft Edge ブログ投稿の追跡防止の向上"

> [!NOTE]
> <span data-ttu-id="fb54e-331">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb54e-331">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fb54e-332">元のページは[ここ](https://developers.google.com/web/updates/2020/01/devtools/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-332">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="fb54e-334">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="fb54e-334">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  