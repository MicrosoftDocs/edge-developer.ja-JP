---
description: Wavy の下線は、要素ツール、サービス ワーカー更新タイムラインなどでコードの問題を強調表示します。
title: DevTools の新機能 (Microsoft Edge 91)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 69fcd29f9b4cae9ec290798b767fbe54793cb2fd
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624781"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-91"></a><span data-ttu-id="e8880-104">DevTools の新機能 (Microsoft Edge 91)</span><span class="sxs-lookup"><span data-stu-id="e8880-104">What's New In DevTools (Microsoft Edge 91)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a><span data-ttu-id="e8880-105">Wavy の下線は、要素ツールのコードの問題と改善点を強調表示します</span><span class="sxs-lookup"><span data-stu-id="e8880-105">Wavy underlines highlight code issues and improvements in Elements tool</span></span>  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

<span data-ttu-id="e8880-106">最新のほとんどの ID では、テキストの下線が波線で構文エラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e8880-106">In most modern IDEs, wavy underlines under text indicate syntax errors.</span></span>   <span data-ttu-id="e8880-107">バージョン Microsoft Edge 91 以降では、要素ツールの**DOM**ビューで HTML の下に波線が**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-107">In Microsoft Edge version 91 or later, wavy underlines display under HTML in the **DOM** view of the **Elements** tool.</span></span>  <span data-ttu-id="e8880-108">波の下線は、アクセシビリティ、互換性、パフォーマンスに関連するコードの問題と提案を示します。</span><span class="sxs-lookup"><span data-stu-id="e8880-108">The wavy underlines indicate code issues and suggestions related to accessibility, compatibility, performance, and so on.</span></span>  <span data-ttu-id="e8880-109">問題を確認および編集する方法の詳細については、「問題ツールを使用して問題を検索して修正する」 [に移動します][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="e8880-109">For more information about how to review and edit issues, navigate to [Find and fix problems using the Issues tool][DevtoolsIssuesIndex].</span></span>  

<span data-ttu-id="e8880-110">[問題] ツール **を開** き、問題の詳細と修正方法を確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-110">To open the **Issues** tool and learn more about the issue and how to fix it, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e8880-111">を選択して押 `Shift` し続け、波線の下線を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-111">Select and hold `Shift`, and then choose any wavy underline.</span></span>  
*   <span data-ttu-id="e8880-112">次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-112">Complete the following actions.</span></span>  
    1.  <span data-ttu-id="e8880-113">任意の波線の下線にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="e8880-113">Hover on any wavy underline.</span></span>  
    1.  <span data-ttu-id="e8880-114">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-114">Open the contextual menu \(right-click\).</span></span>  
    1.  <span data-ttu-id="e8880-115">[ **問題に表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-115">Choose **Show in Issues**.</span></span>  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="要素ツールで下線付きエラーを選択する" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         <span data-ttu-id="e8880-117">要素ツールで下線付きエラーを **選択** する</span><span class="sxs-lookup"><span data-stu-id="e8880-117">Choose the underlined error in the **Elements** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="[問題] ツールにエラーの詳細を表示する" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         <span data-ttu-id="e8880-119">[問題] ツールにエラー **の詳細を表示** する</span><span class="sxs-lookup"><span data-stu-id="e8880-119">Display error details in the **Issues** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="e8880-120">有益なツール ヒントを使用した DevTools の詳細</span><span class="sxs-lookup"><span data-stu-id="e8880-120">Learn about DevTools with informative tooltips</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

<span data-ttu-id="e8880-121">DevTools ツールヒント機能は、DevTools のすべての異なるツールとウィンドウについて学習するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8880-121">The DevTools Tooltips feature helps you learn about all the different tools and panes in DevTools.</span></span>  <span data-ttu-id="e8880-122">ツールヒントをオフにする場合は、 を選択します `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="e8880-122">To turn off Tooltips, select `Esc`.</span></span>  <span data-ttu-id="e8880-123">ツールヒントを有効にするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-123">To turn on Tooltips, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e8880-124">`Ctrl` + `Shift` + `H` \(Windows/Linux\) または `Cmd` + `Shift` + `H` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-124">Select `Ctrl`+`Shift`+`H` \(Windows/Linux\) or `Cmd`+`Shift`+`H` \(macOS\).</span></span>  
*   <span data-ttu-id="e8880-125">[コマンド メニューを開き、][DevtoolsCommandMenuIndexOpenCommandMenu] と入力します `tooltips` 。</span><span class="sxs-lookup"><span data-stu-id="e8880-125">[Open the Command Menu][DevtoolsCommandMenuIndexOpenCommandMenu] and then type `tooltips`.</span></span>  
*   <span data-ttu-id="e8880-126">**[DevTools のツールヒントの**切り替え `...` > \*\*\*\* DevTools \( \) のカスタマイズと  >  **制御を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-126">Choose **Customize and control DevTools** \(`...`\) > **Help** > **Toggle the DevTools Tooltips**.</span></span>  

<span data-ttu-id="e8880-127">また、フォーカス モードと [DevTools ツール][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] ヒント実験を有効にした場合は、アクティビティ バーの下部にある **[DevTools** ツールヒントの切り替え \( \) ] ボタンを `?` **選択することもできます**。</span><span class="sxs-lookup"><span data-stu-id="e8880-127">Also, if you turn on the [Focus Mode and DevTools Tooltips][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] experiment, you may also choose the **Toggle the DevTools Tooltips** \(`?`\) button at the bottom of the **Activity Bar**.</span></span>  

<span data-ttu-id="e8880-128">DevTools の使い方の詳細を表示するには、[ツールヒント] をオンにしてから、DevTools のアウトライン表示された各領域にマウス ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-128">To display more information about how to use the DevTools, turn on Tooltips, and then hover on each outlined region of the DevTools.</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="[問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置くと、詳細が表示されます。" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   <span data-ttu-id="e8880-130">[問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置 **くと、詳細** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-130">Hover on anywhere in the highlighted region of the **Issues** tool to display more details</span></span>  
:::image-end:::  

## <a name="service-worker-update-timeline"></a><span data-ttu-id="e8880-131">サービス ワーカーの更新タイムライン</span><span class="sxs-lookup"><span data-stu-id="e8880-131">Service worker update timeline</span></span>  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

<span data-ttu-id="e8880-132">バージョン 91 以降Microsoft Edgeプログレッシブ Web アプリまたは Service Worker 開発者の場合は、アプリケーション ツールでサービス ワーカーの更新ライフサイクルをタイムラインとして**表示**します。</span><span class="sxs-lookup"><span data-stu-id="e8880-132">In Microsoft Edge version 91 or later, if you're a Progressive Web App or Service Worker developer, display the update lifecycle of your Service Workers as a timeline in the **Application** tool.</span></span>  <span data-ttu-id="e8880-133">この機能は、サービス ワーカーが次の各段階で費やした時間を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8880-133">This feature helps you understand the time your Service Worker spends in each of the following stages.</span></span>  

*   **<span data-ttu-id="e8880-134">Install</span><span class="sxs-lookup"><span data-stu-id="e8880-134">Install</span></span>**  
*   **<span data-ttu-id="e8880-135">待機</span><span class="sxs-lookup"><span data-stu-id="e8880-135">Wait</span></span>**  
*   **<span data-ttu-id="e8880-136">ライセンス認証</span><span class="sxs-lookup"><span data-stu-id="e8880-136">Activate</span></span>**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="Service Worker の更新サイクルでタイムラインを確認する" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   <span data-ttu-id="e8880-138">Service Worker **の更新** サイクル **で** タイムラインを確認する</span><span class="sxs-lookup"><span data-stu-id="e8880-138">Review the **Timeline** in the **Update Cycle** for your Service Worker</span></span>  
:::image-end:::  

<span data-ttu-id="e8880-139">サービス ワーカーのライフサイクルの詳細については、「Service Worker ライフサイクル [」に移動します][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]。</span><span class="sxs-lookup"><span data-stu-id="e8880-139">For more information about the lifecycle of your Service Workers, navigate to [The Service Worker lifecycle][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle].</span></span>  <span data-ttu-id="e8880-140">DevTools のプログレッシブ Web アプリとサービス ワーカーのデバッグ ツールの詳細については、「Service Worker の機能強化 [」に移動します][DevtoolsServiceWorkerIndex]。</span><span class="sxs-lookup"><span data-stu-id="e8880-140">For more information about debugging tools for Progressive Web Apps and Service Workers in the DevTools, navigate to [Service Worker improvements][DevtoolsServiceWorkerIndex].</span></span>  <span data-ttu-id="e8880-141">オープンソース プロジェクトでこの機能に関するリアルタイムの更新Chromium、Issue [1066604 に移動します][CR1066604]。</span><span class="sxs-lookup"><span data-stu-id="e8880-141">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1066604][CR1066604].</span></span>  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a><span data-ttu-id="e8880-142">プログレッシブ Web アプリで四角形以外のアイコンに対する警告が表示されなくなりました</span><span class="sxs-lookup"><span data-stu-id="e8880-142">Progressive Web Apps no longer display warnings for non-square icons</span></span>  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

<span data-ttu-id="e8880-143">Microsoft Edge [90][DevtoolsWhatsNew202102Devtools]以前のバージョンでは、PWA の Web アプリ マニフェストに四角形以外のアイコンが含まれている場合は、四角形以外\*\*\*\* のアイコンごとに [エラーと警告] セクションに警告が表示されました。</span><span class="sxs-lookup"><span data-stu-id="e8880-143">In [Microsoft Edge version 90][DevtoolsWhatsNew202102Devtools] or earlier, if the Web App Manifest of your PWA included a non-square icon, a warning was displayed in the **Errors and Warnings**  section for each non-square icon.</span></span>  <span data-ttu-id="e8880-144">バージョン Microsoft Edge 91 以降では、少\*\*\*\* なくとも 1\*\*\*\* つの正方形のアイコンを指定した場合、アプリケーション ツールの [マニフェスト] セクションに警告は表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-144">In Microsoft Edge version 91 or later, the **Manifest** section in the **Application** tool displays no warnings if you provide at least one square icon.</span></span>  <span data-ttu-id="e8880-145">四角形のアイコンを指定しない場合は、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-145">If you don't provide any square icons, a warning displays the following message.</span></span>  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="e8880-147">バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-147">In Microsoft Edge version 90 or earlier, an error displays for each icon that is non-square</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="e8880-149">バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな</span><span class="sxs-lookup"><span data-stu-id="e8880-149">In Microsoft Edge version 91 or later, no error displays when you provide at least one square icon</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e8880-150">Web アプリ マニフェストでエラーと警告を確認するには、アプリケーション\*\*\*\* ツールに移動し、[マニフェスト] セクション**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="e8880-150">To review errors and warnings in your Web App Manifest, navigate to the **Application** tool and choose the **Manifest** section.</span></span>  <span data-ttu-id="e8880-151">エラーと警告は、[エラーと警告] の **見出しの下に一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-151">Errors and warnings are listed under the **Errors and Warnings** heading.</span></span>  <span data-ttu-id="e8880-152">Web アプリ マニフェストの詳細については、「Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する」 [に移動します][ProgressiveWebAppsWebappmanifests]。</span><span class="sxs-lookup"><span data-stu-id="e8880-152">For more information about the Web App Manifest, navigate to [Use the Web App Manifest to integrate your Progressive Web App into the Operating System][ProgressiveWebAppsWebappmanifests].</span></span>  <span data-ttu-id="e8880-153">Web アプリ マニフェストに含めるアイコンを作成するには [、PWABuilder イメージ ジェネレーターに移動します][PwabuilderImagegenerator]。</span><span class="sxs-lookup"><span data-stu-id="e8880-153">To create icons to include in your Web App Manifest, navigate to the [PWABuilder Image Generator][PwabuilderImagegenerator].</span></span>  <span data-ttu-id="e8880-154">Chromium オープンソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[Issue [1185945][CR1185945] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-154">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1185945][CR1185945].</span></span>  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a><span data-ttu-id="e8880-155">ローカライズされた DevTools が、Chromiumベースのブラウザーでサポートされる</span><span class="sxs-lookup"><span data-stu-id="e8880-155">Localized DevTools now supported in Chromium-based browsers</span></span>  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

<span data-ttu-id="e8880-156">バージョン[81 Microsoft Edgeから][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]、DevTools Microsoft Edge独自の言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-156">Starting in [Microsoft Edge version 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages], Microsoft Edge DevTools displays in your own language.</span></span>  <span data-ttu-id="e8880-157">多くの開発者は、英語ではなく、StackOverflow や Visual Studio Codeなどの他の開発者ツールを母国語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="e8880-157">Many developers use other developer tools like StackOverflow and Visual Studio Code in their native language, not just in English.</span></span>  <span data-ttu-id="e8880-158">DevTools Microsoft Edge、Chrome DevTools チーム、Google ライトハウス チームが協力して、すべてのユーザー ベースのブラウザーで同じChromium提供しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-158">The Microsoft Edge DevTools team, Chrome DevTools team, and the Google Lighthouse team collaborated to provide the same experience in all Chromium-based browsers.</span></span>  <span data-ttu-id="e8880-159">言語で DevTools を使用する方法の詳細については、「DevTools 言語設定の変更 [」に移動します][DevtoolsCustomizeLocalization]。</span><span class="sxs-lookup"><span data-stu-id="e8880-159">For more information about how to use DevTools in your language, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  <span data-ttu-id="e8880-160">Chromium オープンソース プロジェクトでのこの機能のコラボレーションの詳細については、「[1136655][CR1136655]」に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-160">For more information about the collaboration on this feature in the Chromium open-source project, navigate to [1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edgeと DevTools が日本語に設定されている" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   <span data-ttu-id="e8880-162">Microsoft Edgeと DevTools が日本語に設定されている</span><span class="sxs-lookup"><span data-stu-id="e8880-162">Microsoft Edge browser and DevTools set to Japanese</span></span>  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a><span data-ttu-id="e8880-163">キーボードを使用して CSS 変数に移動する</span><span class="sxs-lookup"><span data-stu-id="e8880-163">Use the keyboard to navigate to CSS variables</span></span>  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

<span data-ttu-id="e8880-164">バージョン[88 Microsoft Edgeから][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]、[スタイル] ウィンドウ\*\*\*\* に CSS 変数が表示され、各変数の定義へのリンクが直接提供されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-164">Starting in [Microsoft Edge version 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane], the **Styles** pane displays CSS variables and provides a link directly to the definition of each variable.</span></span>  <span data-ttu-id="e8880-165">Microsoft Edge バージョン 91 以降では、矢印キーを使用して CSS 変数に簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-165">In Microsoft Edge version 91 or later, you may use the arrow keys to easily navigate to CSS variables.</span></span>  <span data-ttu-id="e8880-166">[スタイル] ウィンドウで定義 **を開** く場合は、変数にカーソルを合わせると、 を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e8880-166">To open the definition in the **Styles** pane, hover on a variable, and then select `Enter`.</span></span>  <span data-ttu-id="e8880-167">CSS 変数の詳細については、「USING CSS カスタム プロパティ [(変数)」を参照してください][MdnDocsWebCssUsingCssCustomProperties]。</span><span class="sxs-lookup"><span data-stu-id="e8880-167">For more information about CSS variables, navigate to [Using CSS custom properties (variables)][MdnDocsWebCssUsingCssCustomProperties].</span></span>  <span data-ttu-id="e8880-168">Chromium オープンソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[Issue [1187735][CR1187735] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-168">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1187735][CR1187735].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="スタイル ウィンドウで強調表示されている --theme-body-background CSS 変数" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   <span data-ttu-id="e8880-170">[ `--theme-body-background` スタイル] ウィンドウで強調表示されている CSS**変数**</span><span class="sxs-lookup"><span data-stu-id="e8880-170">The `--theme-body-background` CSS variable highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a><span data-ttu-id="e8880-171">問題は重大度別に自動的に並べ替え</span><span class="sxs-lookup"><span data-stu-id="e8880-171">Issues are automatically sorted by severity</span></span>  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

<span data-ttu-id="e8880-172">[ **問題] ツール** には、アクセシビリティ、パフォーマンス、セキュリティなど、Web サイトを改善するための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-172">The **Issues** tool displays recommendations to improve your website, including accessibility, performance, security, and so on.</span></span> <span data-ttu-id="e8880-173">フィードバックに基づいて、問題は重大度別に自動的に並べ替えされます。</span><span class="sxs-lookup"><span data-stu-id="e8880-173">Based on your feedback, issues are now automatically sorted by severity.</span></span>  <span data-ttu-id="e8880-174">各フィードバック カテゴリでは、エラーとしてマークされた\*\*\*\* 各問題が最初に表示され、警告としてマークされた\*\*\*\* 各問題の後に、ヒントとしてマークされた各問題が続**きます**。</span><span class="sxs-lookup"><span data-stu-id="e8880-174">In each feedback category, each issue marked as an **Error** appears first, followed each issue marked as a **Warning**, then each issue marked as a **Tip**.</span></span>  <span data-ttu-id="e8880-175">問題を絞り込むのに役立つ、追加のフィルター オプションが今後の更新に向け計画されています。</span><span class="sxs-lookup"><span data-stu-id="e8880-175">To help you refine your issues, extra filter options are planned for a future update.</span></span>  <span data-ttu-id="e8880-176">問題を確認する方法の詳細については、「問題ツールを使用して問題を検索して修正する [」に移動します][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="e8880-176">For more information about how to review issues, navigate to [Find and fix problems using the Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text="[問題] ツールは、重大度別に並べ替えた問題を表示します。" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   <span data-ttu-id="e8880-178">[ **問題] ツールは** 、重大度別に並べ替えた問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8880-178">The **Issues** tool displays sorted issues by severity</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a><span data-ttu-id="e8880-179">Microsoft Edgeバージョン 1.1.7 Visual Studio Code開発者向けツール</span><span class="sxs-lookup"><span data-stu-id="e8880-179">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.7</span></span>  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

<span data-ttu-id="e8880-180">拡張[Microsoft Edge][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]バージョン 1.1.7 Visual Studio Codeツールには、バージョン[88][DevtoolsWhatsNew202011Devtools]の DevTools Microsoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="e8880-180">The [Microsoft Edge Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 provides the DevTools from [Microsoft Edge version 88][DevtoolsWhatsNew202011Devtools].</span></span>  <span data-ttu-id="e8880-181">この拡張機能では、ARMがサポートされ、拡張機能の[デバッガーに依存Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]なくなりました。</span><span class="sxs-lookup"><span data-stu-id="e8880-181">This extension now supports ARM devices and no longer depends on the [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge] extension.</span></span>  <span data-ttu-id="e8880-182">バージョン 1.1.7 には、次のバグ修正と改善が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8880-182">Version 1.1.7 includes the following bug fixes and improvements.</span></span>  

*   <span data-ttu-id="e8880-183">ターゲットクロージャの信頼性を更新しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-183">Updated the reliability of target closure.</span></span>  
*   <span data-ttu-id="e8880-184">作成または破棄されたターゲットをデバッグすると、サイド パネルが自動的に更新される更新を行いました。</span><span class="sxs-lookup"><span data-stu-id="e8880-184">Updated the side panel to automatically refreshes when you debug targets that are created or destroyed.</span></span>  
*   <span data-ttu-id="e8880-185">拡張機能の設定と最新の Changelog に迅速にアクセスできる新しいコンテキスト メニューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e8880-185">Added a new contextual menu that gives you faster access to the extension settings and the latest Changelog.</span></span>  
*   <span data-ttu-id="e8880-186">最新の機能を含む拡張機能のドキュメントのリリースを更新および簡略化しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-186">Updated and simplified the release of extension documentation including the newest features.</span></span>  
    
<span data-ttu-id="e8880-187">バージョン 1.1.7 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。</span><span class="sxs-lookup"><span data-stu-id="e8880-187">To manually update to version 1.1.7, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="e8880-188">[vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルすると、拡張機能に貢献できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-188">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="e8880-189">Chromium プロジェクトからのお知らせ</span><span class="sxs-lookup"><span data-stu-id="e8880-189">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="visualize-css-scroll-snap"></a><span data-ttu-id="e8880-190">CSS のスクロール スナップを表示する</span><span class="sxs-lookup"><span data-stu-id="e8880-190">Visualize CSS scroll-snap</span></span>  

<span data-ttu-id="e8880-191">これで、要素ツールの `scroll-snap` バッジを切り **替** え、CSS のスクロール スナップの配置を検査できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-191">You may now toggle the `scroll-snap` badge in the **Elements** tool to inspect the CSS scroll-snap alignment.</span></span>  <span data-ttu-id="e8880-192">Web ページの HTML 要素が適用されると、その横に [要素] ツール `scroll-snap-type` `scroll-snap` にバッジが **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-192">When an HTML element on your webpage has `scroll-snap-type` applied to it, a `scroll-snap` badge displays next to it in the **Elements** tool.</span></span>  <span data-ttu-id="e8880-193">Web ページ上のスクロール スナップ オーバーレイの表示を \(または off\) オンにするバッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-193">Choose the badge to turn on \(or off\) the display of a scroll-snap overlay on the webpage.</span></span>  <span data-ttu-id="e8880-194">Web ページの例を確認するには、[スクロール スナップデモ [] に移動します][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]。</span><span class="sxs-lookup"><span data-stu-id="e8880-194">To review an example webpage, navigate to [Scroll Snap Demo][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml].</span></span>  <span data-ttu-id="e8880-195">この例では、スナップエッジにドットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-195">In the example, dots display on snap edges.</span></span>  <span data-ttu-id="e8880-196">スクロール ポートのアウトラインは、スナップ項目にダッシュアウトラインがある場合は、アウトラインが点灯します。</span><span class="sxs-lookup"><span data-stu-id="e8880-196">The scroll port has a solid outline while the snap items have dash outlines.</span></span>  <span data-ttu-id="e8880-197">スクロールの余白がオレンジ色で塗りつぶされている間、スクロールの余白は緑で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="e8880-197">The scroll padding is filled in green while the scroll margin is filled in orange.</span></span>  <span data-ttu-id="e8880-198">この機能の履歴をオープンソース プロジェクトで確認するにはChromium Issue [862450 に移動します][CR862450]。</span><span class="sxs-lookup"><span data-stu-id="e8880-198">To review the history of this feature in the Chromium open-source project, navigate to Issue [862450][CR862450].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-scroll-snap-highlight.msft.png" alt-text="CSS のスクロール スナップ" lightbox="../../media/2021/04/elements-scroll-snap-highlight.msft.png":::
   <span data-ttu-id="e8880-200">CSS のスクロール スナップ</span><span class="sxs-lookup"><span data-stu-id="e8880-200">CSS scroll-snap</span></span>  
:::image-end:::  

### <a name="new-memory-inspector-tool"></a><span data-ttu-id="e8880-201">新しいメモリ インスペクター ツール</span><span class="sxs-lookup"><span data-stu-id="e8880-201">New Memory Inspector tool</span></span>  

<span data-ttu-id="e8880-202">新しいメモリ **インスペクター ツールを** 使用して、JavaScript メモリと `ArrayBuffer` Wasm メモリを検査します。</span><span class="sxs-lookup"><span data-stu-id="e8880-202">Use the new **Memory Inspector** tool to inspect an `ArrayBuffer` in JavaScript and Wasm memory.</span></span>  <span data-ttu-id="e8880-203">JS デモ [Web ページでメモリを][GlitchMemoryInspectorDemoJsHtml] 開きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-203">Open the [Memory in JS][GlitchMemoryInspectorDemoJsHtml] demo webpage.</span></span>  <span data-ttu-id="e8880-204">[ソース **] ツールで** 、ファイルを開 `memory-write-wasm` き、行にブレークポイントを設定します `0x03c` 。</span><span class="sxs-lookup"><span data-stu-id="e8880-204">In the **Sources** tool, open the `memory-write-wasm` file, and set a breakpoint at line `0x03c`.</span></span>  <span data-ttu-id="e8880-205">Web ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="e8880-205">Refresh the webpage.</span></span>  <span data-ttu-id="e8880-206">デバッガー ウィンドウ **で [** スコープ] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e8880-206">Expand the **Scope** section in the debugger pane.</span></span>  <span data-ttu-id="e8880-207">バッファー値の横に新しいアイコン **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-207">The new icon is displayed next to the **buffer** value.</span></span>  <span data-ttu-id="e8880-208">新しいメモリ インスペクター ツールを **開く場合は、このツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-208">Choose it to open the new **Memory Inspector** tool.</span></span>  

<span data-ttu-id="e8880-209">ソース ツールでのデバッグの詳細については\*\*\*\*、「デバッガー ウィンドウを使用して JavaScript コードをデバッグする[」に移動します][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]。</span><span class="sxs-lookup"><span data-stu-id="e8880-209">To learn more about debugging in the **Sources** tool, navigate to [Using the Debugger pane to debug JavaScript code][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode].</span></span>  <span data-ttu-id="e8880-210">この機能の履歴を Chromium オープンソース プロジェクトで確認するには、[Issue [1166577][CR1166577] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-210">To review the history of this feature in the Chromium open-source project, navigate to Issue [1166577][CR1166577].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png" alt-text="メモリ インスペクター ツール" lightbox="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png":::
   <span data-ttu-id="e8880-212">**メモリ インスペクター** ツール</span><span class="sxs-lookup"><span data-stu-id="e8880-212">**Memory inspector** tool</span></span>  
:::image-end:::  

### <a name="new-badge-settings-pane-in-the-elements-tool"></a><span data-ttu-id="e8880-213">[要素] ツールの [新しいバッジ設定] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="e8880-213">New Badge settings pane in the Elements tool</span></span>  

<span data-ttu-id="e8880-214">次に、 **要素ツールのバッジ** 設定 **を使用** して、個々のバッジを \(または off\) オンにします。</span><span class="sxs-lookup"><span data-stu-id="e8880-214">Now, use the **Badge settings** in the **Elements** tool to turn on \(or off\) individual badges.</span></span>  <span data-ttu-id="e8880-215">この機能を使用して、Web ページの検査中に重要なバッジをカスタマイズし、集中します。</span><span class="sxs-lookup"><span data-stu-id="e8880-215">Use this feature to customize and stay focused on important badges while you inspect webpages.</span></span>  <span data-ttu-id="e8880-216">[要素] ツールの上部にバッジ設定ウィンドウを **表示** するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-216">To display the badge settings pane at the top of the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="e8880-217">任意の要素にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="e8880-217">Hover on any element.</span></span>  
1.  <span data-ttu-id="e8880-218">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-218">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="e8880-219">[ **バッジの設定]を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-219">Choose **Badge settings...**.</span></span>  
    
<span data-ttu-id="e8880-220">バッジを \(または hide\) で表示するには、バッジ名の横にあるチェックボックスを \(または remove\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-220">To display \(or hide\) the badges, choose \(or remove\) the checkbox next to the badge name.</span></span>  

<!--  To review the history of this feature in the Chromium open-source project, navigate to Issue [1066772][CR1066772].  -->  

:::image type="complex" source="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png" alt-text="要素ツールのバッジ設定ウィンドウ" lightbox="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png":::
   <span data-ttu-id="e8880-222">**要素ツールの** バッジ **設定** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="e8880-222">**Badge settings** pane in the **Elements** tool</span></span>  
:::image-end:::  

### <a name="enhanced-image-preview-with-aspect-ratio-information"></a><span data-ttu-id="e8880-223">縦横比情報による拡張画像プレビュー</span><span class="sxs-lookup"><span data-stu-id="e8880-223">Enhanced image preview with aspect ratio information</span></span>  

<span data-ttu-id="e8880-224">DevTools のイメージ プレビューは、次の詳細を含む詳細情報を表示するために拡張されました。</span><span class="sxs-lookup"><span data-stu-id="e8880-224">Image previews in the DevTools have been enhanced to display more information, including the following details.</span></span>  

*   <span data-ttu-id="e8880-225">レンダリングされたサイズ</span><span class="sxs-lookup"><span data-stu-id="e8880-225">Rendered size</span></span>  
*   <span data-ttu-id="e8880-226">レンダリングされた縦横比</span><span class="sxs-lookup"><span data-stu-id="e8880-226">Rendered aspect ratio</span></span>  
*   <span data-ttu-id="e8880-227">組み込みサイズ</span><span class="sxs-lookup"><span data-stu-id="e8880-227">Intrinsic size</span></span>  
*   <span data-ttu-id="e8880-228">組み込みの縦横比</span><span class="sxs-lookup"><span data-stu-id="e8880-228">Intrinsic aspect ratio</span></span>  
*   <span data-ttu-id="e8880-229">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="e8880-229">File size</span></span>  
    
<span data-ttu-id="e8880-230">この情報は、画像をよりよく理解し、最適化を適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8880-230">The  information helps you better understand your images and apply optimization.</span></span>  <span data-ttu-id="e8880-231">画像の縦横比情報は、画像プレビュー **を選択** するときにネットワーク ツールでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-231">The image aspect ratio information is also available in the **Network** tool, when you choose an image preview.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e8880-232">[要素 **] ツール** で、画像のプレビューに画像に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-232">In the **Elements** tool, image preview now displays more information about the image.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e8880-233">また、画像の縦横比情報は、画像 **プレビューを選択** するときにネットワーク ツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-233">Also, the image aspect ratio information is available in the **Network** tool, when you choose an image preview.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png" alt-text="要素ツールの縦横比情報を含む画像プレビュー" lightbox="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png":::
         <span data-ttu-id="e8880-235">要素ツールの縦横比情報を含む画像**プレビュー**</span><span class="sxs-lookup"><span data-stu-id="e8880-235">Image preview with aspect ratio information in the **Element** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/network-img-name-filters-preview.msft.png" alt-text="ネットワーク ツールの画像縦横比情報" lightbox="../../media/2021/04/network-img-name-filters-preview.msft.png":::
         <span data-ttu-id="e8880-237">ネットワーク ツールの画像縦横 **比** 情報</span><span class="sxs-lookup"><span data-stu-id="e8880-237">Image aspect ratio information in the **Network** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e8880-238">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、「Issues [1149832][CR1149832]」および[1170656][CR1170656]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-238">To review the history of this feature in the Chromium open-source project, navigate to Issues [1149832][CR1149832] and [1170656][CR1170656].</span></span>  

### <a name="new-options-to-configure-content-encodings-in-the-network-conditions-tool"></a><span data-ttu-id="e8880-239">ネットワーク条件ツールでコンテンツ エンコードを構成するための新しいオプション</span><span class="sxs-lookup"><span data-stu-id="e8880-239">New options to configure Content-Encodings in the Network conditions tool</span></span> 

<span data-ttu-id="e8880-240">[ネットワーク]**ツールで**、新しい [その他のネットワーク条件\*\*\*\*\*\*]を選択します。[\*\* 調整] ドロップダウン メニューの横にあるボタンをクリックして、[ネットワーク条件]**ツールを開**きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-240">In the **Network** tool, choose the new **More network conditions...** button next to the **Throttling** dropdown menu to open the **Network conditions** tool.</span></span>  <span data-ttu-id="e8880-241">[gzip、brotli、][GnuSoftwareGzipManual]または別の将来をサポートしないブラウザーでサーバー応答が正しく[][|::ref1::|Main]エンコードされていることをテストするには、次のアクション `Content-Encoding` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-241">To test if server responses are correctly encoded for browsers that don't support [gzip][GnuSoftwareGzipManual], [brotli][|::ref1::|Main], or another future `Content-Encoding`, complete the following actions.</span></span>  

1.  <span data-ttu-id="e8880-242">ネットワーク条件 **ツールを開** く</span><span class="sxs-lookup"><span data-stu-id="e8880-242">Open the **Network conditions** tool</span></span>
1.  <span data-ttu-id="e8880-243">[承諾された **コンテンツ エンコード] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-243">Navigate to **Accepted Content-Encodings**.</span></span> 
1.  <span data-ttu-id="e8880-244">テストするチェックボックスの横 `Content-Encoding` にあるチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e8880-244">Remove the checkbox next to the `Content-Encoding` you want to test.</span></span>  
    
<span data-ttu-id="e8880-245">Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1162042][CR1162042] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-245">To review the history of this feature in the Chromium open-source project, navigate to Issue [1162042][CR1162042].</span></span>  

:::image type="complex" source="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png" alt-text="新しいその他のネットワーク条件...ボタンをクリックすると、[ネットワーク条件] ツールが開き、コンテンツ エンコードを構成します。" lightbox="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png":::
   <span data-ttu-id="e8880-247">New **More network conditions....** ボタンは、 **構成するネットワーク条件** ツールを開きます</span><span class="sxs-lookup"><span data-stu-id="e8880-247">New **More network conditions...** button opens the **Network conditions** tool to configure</span></span> `Content-Encoding`  
:::image-end:::  

### <a name="styles-pane-enhancements"></a><span data-ttu-id="e8880-248">スタイル ウィンドウの機能強化</span><span class="sxs-lookup"><span data-stu-id="e8880-248">Styles pane enhancements</span></span>  

#### <a name="new-shortcut-to-display-computed-value-in-the-styles-pane"></a><span data-ttu-id="e8880-249">[スタイル] ウィンドウに計算値を表示する新しいショートカット</span><span class="sxs-lookup"><span data-stu-id="e8880-249">New shortcut to display computed value in the Styles pane</span></span>  

<span data-ttu-id="e8880-250">次に、[スタイル] ウィンドウに計算された CSS 値 **を表示** するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-250">Now, to display the computed CSS value in the **Styles** pane, complete the following actions.</span></span>  

1.  <span data-ttu-id="e8880-251">CSS プロパティにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="e8880-251">Hover on a CSS property.</span></span>  
1.  <span data-ttu-id="e8880-252">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-252">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="e8880-253">[ **計算値の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-253">Choose **View computed value**.</span></span>  
    
<span data-ttu-id="e8880-254">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1076198][CR1076198] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-254">To review the history of this feature in the Chromium open-source project, navigate to Issue [1076198][CR1076198].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png" alt-text="計算値を表示する新しいショートカット" lightbox="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png":::
   <span data-ttu-id="e8880-256">計算値を表示する新しいショートカット</span><span class="sxs-lookup"><span data-stu-id="e8880-256">New shortcut to display computed value</span></span>  
:::image-end:::  

#### <a name="support-for-the-accent-color-keyword"></a><span data-ttu-id="e8880-257">アクセントカラー キーワードのサポート</span><span class="sxs-lookup"><span data-stu-id="e8880-257">Support for the accent-color keyword</span></span>  

<span data-ttu-id="e8880-258">スタイル ウィンドウのオートコンプリート UI\*\*\*\* で CSS キーワードが検出され、要素によって生成される UI コントロールのアクセントカラー `accent-color` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8880-258">The autocomplete UI of the **Styles** pane now detects the `accent-color` CSS keyword, which allows you to specify the accent color for UI controls generated by the element.</span></span>  <span data-ttu-id="e8880-259">要素によって生成される UI コントロールの例には、チェック ボックスやラジオ ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="e8880-259">Examples of UI controls that are generated by an element include checkboxes or radio buttons.</span></span> <span data-ttu-id="e8880-260">実装の状態の詳細については、「フィーチャー: Chromium CSS プロパティ」[に移動します][ChromestatusFeature4752739957473280]。</span><span class="sxs-lookup"><span data-stu-id="e8880-260">For more information about the status of the Chromium implementation, navigate to [Feature: accent-color CSS property][ChromestatusFeature4752739957473280].</span></span>  <span data-ttu-id="e8880-261">この機能を有効にする場合は、チェック ボックスに移動 `edge://flags#enable-experimental-web-platform-features` して [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-261">To turn on this feature, navigate to `edge://flags#enable-experimental-web-platform-features` and set the checkbox to **Enabled**.</span></span>  <span data-ttu-id="e8880-262">この機能の履歴を Chromium オープンソース プロジェクトで確認するには、[Issue [1092093][CR1092093] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-262">To review the history of this feature in the Chromium open-source project, navigate to Issue [1092093][CR1092093].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-accent-color.msft.png" alt-text="アクセントカラー CSS キーワード" lightbox="../../media/2021/04/elements-styles-accent-color.msft.png":::
   `accent-color` <span data-ttu-id="e8880-264">CSS キーワード</span><span class="sxs-lookup"><span data-stu-id="e8880-264">CSS keyword</span></span>
:::image-end:::  

### <a name="display-details-about-blocked-features-in-the-frame-details-view"></a><span data-ttu-id="e8880-265">[フレームの詳細] ビューにブロックされた機能の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e8880-265">Display details about blocked features in the Frame details view</span></span>  

<span data-ttu-id="e8880-266">アクセス許可ポリシーは、Web プラットフォーム API で、Web サイトが個々のフレームまたは埋め込みブラウザー機能の使用を許可またはブロックする機能を `iframe` 提供します。</span><span class="sxs-lookup"><span data-stu-id="e8880-266">Permissions Policy is a web platform API that gives a website the ability to allow or block the use of browser features in an individual frame or in an `iframe` that it embeds.</span></span> <span data-ttu-id="e8880-267">詳細については、「アクセス許可ポリシー [の説明」に移動します][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]。</span><span class="sxs-lookup"><span data-stu-id="e8880-267">For more information, navigate to [Permissions Policy Explainer][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd].</span></span>  <span data-ttu-id="e8880-268">機能がブロックされる理由の詳細を表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-268">To display the details on why a feature is blocked, complete the following actions.</span></span>  

1.  <span data-ttu-id="e8880-269">[[OOPIF アクセス許可ポリシー] に移動します][GlitchPermissionPolicyDemoMain]。</span><span class="sxs-lookup"><span data-stu-id="e8880-269">Navigate to [OOPIF Permissions Policy][GlitchPermissionPolicyDemoMain].</span></span>  
1.  <span data-ttu-id="e8880-270">[アプリケーション] ツール **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-270">Navigate to the **Application** tool.</span></span>  
1.  <span data-ttu-id="e8880-271">フレームを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-271">Choose a frame.</span></span>  
1.  <span data-ttu-id="e8880-272">[アクセス許可ポリシー **] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-272">Navigate to the **Permissions Policy** section.</span></span>  
1.  <span data-ttu-id="e8880-273">[無効な機能 **] プロパティに移動** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-273">Navigate to the **Disabled Features** property.</span></span>  
1.  <span data-ttu-id="e8880-274">[詳細 **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-274">Choose **Show details**.</span></span>  
1.  <span data-ttu-id="e8880-275">各ポリシーの横にあるアイコンを選択して、機能をブロックしたネットワーク `iframe` 要求に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-275">Choose the icon next to each policy to navigate to the `iframe` or network request that blocked the feature.</span></span>  
    
<span data-ttu-id="e8880-276">Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1158827][CR1158827] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-276">To review the history of this feature in the Chromium open-source project, navigate to Issue [1158827][CR1158827].</span></span>  

:::image type="complex" source="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png" alt-text="[フレームの詳細] ビューのブロックされた機能" lightbox="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png":::
   <span data-ttu-id="e8880-278">[フレームの詳細] ビューのブロックされた機能</span><span class="sxs-lookup"><span data-stu-id="e8880-278">Blocked features in the Frame details view</span></span>  
:::image-end:::  

### <a name="filter-experiments-in-the-experiments-setting"></a><span data-ttu-id="e8880-279">[実験] 設定で実験をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e8880-279">Filter experiments in the Experiments setting</span></span>  

<span data-ttu-id="e8880-280">新しい実験フィルターを使用して、実験を迅速に見つける。</span><span class="sxs-lookup"><span data-stu-id="e8880-280">Find experiments quicker with the new experiment filter.</span></span>  <span data-ttu-id="e8880-281">たとえば、コードの問題に関する新しい実験を有効にするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-281">For example, to turn on new experiments for code issues, complete the following actions.</span></span>
``

1.  <span data-ttu-id="e8880-282">[テスト]**設定**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e8880-282">Navigate to **Settings** > **Experiments**.</span></span>  
1.  <span data-ttu-id="e8880-283">[フィルター] **テキスト ボックスに** 移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-283">Navigate to the **Filter** textbox.</span></span>  
1.  <span data-ttu-id="e8880-284">「`issues`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e8880-284">Type `issues`.</span></span>  
    
:::image type="complex" source="../../media/2021/04/settings-experiments-filter-by-issues.msft.png" alt-text="[実験] 設定で実験をフィルター処理する" lightbox="../../media/2021/04/settings-experiments-filter-by-issues.msft.png":::
   <span data-ttu-id="e8880-286">[実験] 設定で **実験をフィルター** 処理する</span><span class="sxs-lookup"><span data-stu-id="e8880-286">Filter experiments in the **Experiments** setting</span></span>  
:::image-end:::  

### <a name="new-vary-header-column-in-the-cache-storage-pane"></a><span data-ttu-id="e8880-287">[キャッシュ] ストレージ ウィンドウの [ヘッダーの変更] 列</span><span class="sxs-lookup"><span data-stu-id="e8880-287">New Vary Header column in the Cache storage pane</span></span>  

<span data-ttu-id="e8880-288">[キャッシュ] ウィンドウ `Vary Header` の新**しいStorageを使用**して、[HTTP[][HttpwgSpecsRfc7231HtmlHeaderVary]応答ヘッダーの値を変更する] を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8880-288">Use the new `Vary Header` column in the **Cache Storage** pane to display the [Vary][HttpwgSpecsRfc7231HtmlHeaderVary] HTTP response header values.</span></span>  <span data-ttu-id="e8880-289">Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1186049][CR1186049]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-289">To review the history of this feature in the Chromium open-source project, navigate to Issue [1186049][CR1186049].</span></span>  

:::image type="complex" source="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png" alt-text="[ヘッダーの変更] 列" lightbox="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png":::
   <span data-ttu-id="e8880-291">[ヘッダーの変更] 列</span><span class="sxs-lookup"><span data-stu-id="e8880-291">Vary Header column</span></span>  
:::image-end:::  

### <a name="sources-tool-improvements"></a><span data-ttu-id="e8880-292">ソース ツールの機能強化</span><span class="sxs-lookup"><span data-stu-id="e8880-292">Sources tool improvements</span></span>  

#### <a name="support-for-new-javascript-features"></a><span data-ttu-id="e8880-293">新しい JavaScript 機能のサポート</span><span class="sxs-lookup"><span data-stu-id="e8880-293">Support for new JavaScript features</span></span>  

<span data-ttu-id="e8880-294">DevTools は、新しいプライベート ブランドチェック [a.k.a. #foo obj][V8DevFeaturesPrivateBrandChecks] JavaScript 言語機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e8880-294">DevTools now support the new [Private brand checks a.k.a. #foo in obj][V8DevFeaturesPrivateBrandChecks] JavaScript language feature.</span></span>  <span data-ttu-id="e8880-295">プライベート ブランド チェック機能は、in 演算子を拡張 [して][MdnDocsWebJavascriptReferenceOperatorsIn] 、特定のオブジェクトの [Private クラス フィールド][V8DevFeaturesClassFieldsPrivateClassFields] をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e8880-295">The private brand checks feature extends the [in operator][MdnDocsWebJavascriptReferenceOperatorsIn] to support [Private class fields][V8DevFeaturesClassFieldsPrivateClassFields] on a specific object.</span></span>  <span data-ttu-id="e8880-296">コンソール ツールとソース**ツール\*\*\*\*で試**してみてください。</span><span class="sxs-lookup"><span data-stu-id="e8880-296">Try it in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="e8880-297">また、プライベート フィールドを検査するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8880-297">Also, to inspect the private fields, complete the following actions.</span></span>  

1.  <span data-ttu-id="e8880-298">デバッガー ウィンドウ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-298">Navigate to **debugger** pane.</span></span>  
1.  <span data-ttu-id="e8880-299">[スコープ] **セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="e8880-299">Navigate to the **Scope** section.</span></span>  
    
<span data-ttu-id="e8880-300">オープンソース プロジェクトでこの機能の履歴を確認Chromium、Issue [11374 に移動します][CR11374]。</span><span class="sxs-lookup"><span data-stu-id="e8880-300">To review the history of this feature in the Chromium open-source project, navigate to Issue [11374][CR11374].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png" alt-text="JavaScript のプライベート ブランド チェック" lightbox="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png":::
   <span data-ttu-id="e8880-302">JavaScript のプライベート ブランド チェック</span><span class="sxs-lookup"><span data-stu-id="e8880-302">JavaScript private brand checks</span></span>  
:::image-end:::  

#### <a name="enhanced-support-for-breakpoints-debugging"></a><span data-ttu-id="e8880-303">ブレークポイントのデバッグのサポートの強化</span><span class="sxs-lookup"><span data-stu-id="e8880-303">Enhanced support for breakpoints debugging</span></span>  

<span data-ttu-id="e8880-304">Webpack やロールアップのような最新 [の JavaScript][WebpackJsMain]バンドル [は、コード][RollupjsMain] 分割をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e8880-304">Modern JavaScript bundlers like [Webpack][WebpackJsMain], and [Rollup][RollupjsMain] support code splitting.</span></span>  <span data-ttu-id="e8880-305">コード分割の詳細については、「コード分割」 [に移動します][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]。</span><span class="sxs-lookup"><span data-stu-id="e8880-305">To learn more about code splitting, navigate to [Code splitting][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules].</span></span>  <span data-ttu-id="e8880-306">バージョン 90 Microsoft Edgeバージョンでは、DevTools は 1 つのバンドルにのみブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="e8880-306">In Microsoft Edge version 90 or earlier, DevTools only set breakpoints in a single bundle.</span></span>  <span data-ttu-id="e8880-307">バージョン 91 以降Microsoft Edge DevTools は、共有コンポーネントをデバッグするときに複数のバンドルにブレークポイントを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="e8880-307">In Microsoft Edge version 91 or later, DevTools properly sets breakpoints in multiple bundles when you debug a shared component.</span></span>  <span data-ttu-id="e8880-308">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issues [1142705][CR1142705]、979000、および [1180794][CR1180794]に移動します。 [][CR979000]</span><span class="sxs-lookup"><span data-stu-id="e8880-308">To review the history of this feature in the Chromium open-source project, navigate to Issues [1142705][CR1142705], [979000][CR979000], and [1180794][CR1180794].</span></span>  

#### <a name="support-hover-preview-with-bracket-notation"></a><span data-ttu-id="e8880-309">かっこ表記を使用したホバー プレビューのサポート</span><span class="sxs-lookup"><span data-stu-id="e8880-309">Support hover preview with bracket notation</span></span>  

<span data-ttu-id="e8880-310">DevTools は、ソース ツールの表記を使用する JavaScript メンバー式のホバー `[]` プレビュー **をサポート** しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-310">DevTools now support hover preview on JavaScript member expressions that use the `[]` notation in the **Sources** tool.</span></span>  <span data-ttu-id="e8880-311">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1178305][CR1178305] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-311">To review the history of this feature in the Chromium open-source project, navigate to Issue [1178305][CR1178305].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png" alt-text="[] 表記でホバー プレビューをサポートする" lightbox="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png":::
   <span data-ttu-id="e8880-313">表記付きホバー プレビューの `[]` サポート</span><span class="sxs-lookup"><span data-stu-id="e8880-313">Support hover preview with `[]` notation</span></span>  
:::image-end:::  

#### <a name="improved-outline-of-html-files"></a><span data-ttu-id="e8880-314">HTML ファイルのアウトラインの改善</span><span class="sxs-lookup"><span data-stu-id="e8880-314">Improved outline of HTML files</span></span>  

<span data-ttu-id="e8880-315">DevTools では、ファイルのアウトラインサポートが向上 `.html` しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-315">DevTools now has better outline support for `.html` files.</span></span>  <span data-ttu-id="e8880-316">[ソース **] ツールで** 、ファイルを開 `.html` きます。</span><span class="sxs-lookup"><span data-stu-id="e8880-316">In the **Sources** tool, open the `.html` file.</span></span>  <span data-ttu-id="e8880-317">\(or off\) コード アウトラインを有効にする場合は、Windows/Linux または `Ctrl` + `Shift` + `O` `Cmd` + `Shift` + `O` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="e8880-317">To turn on \(or off\) the code outline, select `Ctrl`+`Shift`+`O` on Windows/Linux or `Cmd`+`Shift`+`O` on macOS.</span></span>  <span data-ttu-id="e8880-318">次の図では、DevTools がアウトライン内のすべての関数を正しく一覧表示するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e8880-318">In the following figure, DevTools now correctly list all functions in the outline.</span></span>  <span data-ttu-id="e8880-319">以前は、DevTools は一部の関数のみを表示しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-319">Previously, DevTools only displayed some of the functions.</span></span>  <span data-ttu-id="e8880-320">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [761019][CR761019]および [1191465][CR1191465]に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-320">To review the history of this feature in the Chromium open-source project, navigate to Issues [761019][CR761019] and [1191465][CR1191465].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-jobobbx-at.msft.png" alt-text=" HTML ファイルのアウトラインの改善" lightbox="../../media/2021/04/sources-page-jobobbx-at.msft.png":::
   <span data-ttu-id="e8880-322">HTML ファイルのアウトラインの改善</span><span class="sxs-lookup"><span data-stu-id="e8880-322">Improved outline of HTML files</span></span>  
:::image-end:::  

#### <a name="proper-error-stack-traces-for-wasm-debugging"></a><span data-ttu-id="e8880-323">Wasm デバッグの適切なエラー スタック トレース</span><span class="sxs-lookup"><span data-stu-id="e8880-323">Proper error stack traces for Wasm debugging</span></span>  

<span data-ttu-id="e8880-324">バージョン 90 Microsoft Edge以前のバージョンでは、DevTools はエラー スタック トレースで汎用の Wasm 参照のみを表示しました。</span><span class="sxs-lookup"><span data-stu-id="e8880-324">In Microsoft Edge version 90 or earlier, DevTools only displayed generic Wasm references in Error stack traces.</span></span>  <span data-ttu-id="e8880-325">バージョン 91 以降Microsoft Edge DevTools はインライン関数要求を解決し、Wasm デバッグのエラー スタック トレースにソースの場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8880-325">In Microsoft Edge version 91 or later, DevTools resolves inline function requests and displays the source location in Error stack traces for Wasm debugging.</span></span>  <span data-ttu-id="e8880-326">コンソールのエラー スタック トレースの詳細については、 **エラー**に移動 [します][DevtoolsConsoleApiError]。</span><span class="sxs-lookup"><span data-stu-id="e8880-326">To learn more about Error stack traces in the **Console**, navigate to [error][DevtoolsConsoleApiError].</span></span>  

<span data-ttu-id="e8880-327">バージョン 91 以降Microsoft Edge DevTools はインライン関数要求を解決し、Wasm デバッグの適切なエラー スタック トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8880-327">In Microsoft Edge version 91 or later, DevTools resolves inline function requests and displays proper error stack traces for Wasm debugging.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="e8880-328">バージョン 90 Microsoft Edge以前のバージョンでは、ソースの場所はエラー スタック トレースに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e8880-328">In Microsoft Edge version 90 and earlier, the source location doesn't display in the Error stack traces.</span></span>  <span data-ttu-id="e8880-329">ソースの場所には、 が含まれます `dsquare` 。</span><span class="sxs-lookup"><span data-stu-id="e8880-329">Source locations include `dsquare`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="e8880-330">バージョン Microsoft Edge 91 以降では、エラー スタック トレースにソースの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8880-330">In Microsoft Edge version 91 and later, the source location displays in the Error stack traces.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png" alt-text="Wasm デバッグの以前のエラー スタック トレース" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png":::
         <span data-ttu-id="e8880-332">Wasm デバッグの適切なエラー スタック トレース</span><span class="sxs-lookup"><span data-stu-id="e8880-332">Proper error stack traces for Wasm debugging</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png" alt-text="Wasm デバッグの適切なエラー スタック トレース" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png":::
         <span data-ttu-id="e8880-334">Wasm デバッグの適切なエラー スタック トレース</span><span class="sxs-lookup"><span data-stu-id="e8880-334">Proper error stack traces for Wasm debugging</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e8880-335">Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1189161][CR1189161] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8880-335">To review the history of this feature in the Chromium open-source project, navigate to Issue [1189161][CR1189161].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="e8880-336">Microsoft Edge プレビュー チャネルをダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8880-336">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="e8880-337">Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e8880-337">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="e8880-338">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e8880-338">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="e8880-339">Microsoft Edge DevTools チームに連絡</span><span class="sxs-lookup"><span data-stu-id="e8880-339">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "他の言語で DevTools を使用する - What's New In DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../2020/11/devtools.md#css-variable-definitions-in-styles-pane "[スタイル] ウィンドウの CSS 変数定義 - DevTools の新機能 (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "フォーカス モードでツールをグループ化する - DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "[コマンド] メニューを開く - [DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsConsoleApiError]: ../../../console/api.md#error "error - コンソール API リファレンス |Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "DevTools の言語設定を変更する | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "[問題] ツール を使用して問題を見つけて修正|Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "Service Worker の機能強化|Microsoft Docs"  
[DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]: ../../../sources/index.md#using-the-debugger-pane-to-debug-javascript-code "デバッガー ウィンドウを使用して JavaScript コードをデバッグする - ソース ツールの概要|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "Service Worker ライフサイクル - サービス ワーカーを使用してネットワーク要求とプッシュ通知を管理|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システム アプリケーションに統合|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Visual Studio Code 用 Microsoft Edge Tools |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  

[BrotliMain]: https://www.brotli.org "Brotli"  

[ChromestatusFeature4752739957473280]: https://chromestatus.com/feature/4752739957473280 "機能: アクセントカラー CSS プロパティ |Chrome プラットフォームの状態"  

[CsswgDraftsCssUi4WidgetAccent]: https://drafts.csswg.org/css-ui-4/#widget-accent "ウィジェットのアクセントカラー: accent-color プロパティ - CSS Basic User Interface Module Level 4 |CSS ワーキング グループ エディターの下書き"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR11374]: https://crbug.com/v8/11374 "問題 11374: プライベート フィールドのエルゴノミック ブランドチェックを実装する"  
[CR761019]: https://crbug.com/761019 "問題 761019: 'Go to symbol' は最初の関数を見逃し、型指定された文字が含まれている場合は一致しない方が優先されます"  
[CR862450]: https://crbug.com/862450 "問題 862450: [css-scroll-snap] css スクロール スナップの Devtools 機能の追加を検討する"  
[CR979000]: https://crbug.com/979000 "問題 979000: ソース パスが照合されているソース マップは機能しません。"  
[CR1066604]: https://crbug.com/1066604 "問題 1066604: DevTools: ServiceWorker のインストールとアクティブ化イベントの詳細を参照|Chromiumバグ"  
<!--  [CR1066772]: https://crbug.com/1066772 "Issue 1066772: "  locked  -->  
[CR1076198]: https://crbug.com/1076198 "Issue 1076198: [機能要求] タブから計算プロパティにジャンプ `styles` する"  
[CR1092093]: https://crbug.com/1092093 "Issue 1092093: 'accent-color' CSS プロパティをサポートすることで、フォーム コントロールの色スタイルを変更する"  
[CR1136655]: https://crbug.com/1136655 "Issue 1136655: Devtools: Localization V2 |Chromiumバグ」  
[CR1142705]: "Issue 1142705: ブレークポイントは、2 つのソースマップが Webpack を使用するときに同じ仮想ファイルを指している場合に動作 https://crbug.com/1142705 を停止します"  
[CR1149832]: https://crbug.com/1149832 "Issue 1149832: 機能要求: イメージ プレビューにはファイル サイズも表示する必要があります"  
[CR1158827]: https://crbug.com/1158827 "Issue 1158827: [Permissions Policy] アクセス許可ポリシーの devtool サポートを実装する"  
[CR1162042]: https://crbug.com/1162042 "Issue 1162042: DevTools: gzip/brotli/jxl コンテンツ エンコードの無効化をサポート"  
[CR1166577]: https://crbug.com/1166577 "Issue 1166577: ☂️ リニア メモリ インスペクター 1.0"  
[CR1170656]: https://crbug.com/1170656 "Issue 1170656: 組み込みのアスペクト比を表示する"  
[CR1178305]: "Issue 1178305: デバッガーは、ホバー時にインデックス付き要素のプロパティ値を表示 https://crbug.com/1178305 しない"  
[CR1180794]: https://crbug.com/1180794 "Issue 1180794: ブレークポイントはクロージャ コンパイラのインライニング最適化では機能しません"  
[CR1185945]: "Issue 1185945: マニフェストの警告は、すべてのアイコンが四角形である必要 https://crbug.com/1185945 |Chromiumバグ」  
[CR1186049]: https://crbug.com/1186049 "Issue 1186049: Column for Vary: header in Cache Storageビューアー"  
<span data-ttu-id="e8880-380"> https://crbug.com/1187735[CR1187735]: "Issue 1187735: アクセシビリティ: MAS2.1.1: キーボード: キーボードを使用して 'Var(...)' 関数を呼び出|Chromiumバグ」</span><span class="sxs-lookup"><span data-stu-id="e8880-380">[CR1187735]: https://crbug.com/1187735 "Issue 1187735: Accessibility: MAS2.1.1: Keyboard: Unable to invoke the 'Var(..)' function using keyboard | Chromium bugs"</span></span>  
[CR1189161]: https://crbug.com/1189161 "Issue 1189161: スタックトレースは `new Error` DWARF 経由で変換されません"  
[CR1191465]: https://crbug.com/1191465 "Issue 1191465: Ctrl + Shift+O が HTML で壊れている"  

[GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "アクセス許可ポリシーの説明| GitHub"  

[GlitchMemoryInspectorDemoJsHtml]: https://memory-inspector.glitch.me/demo-js.html "JS ファイルのメモリ|Glitch"  
[GlitchMemoryInspectorDemoWasmHtml]: https://memory-inspector.glitch.me/demo-wasm.html "Wasm |Glitch"  

[GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]: https://microsoft-edge-chromium-devtools.glitch.me/css-dbg-stories/css-scroll-snap.html "スクロール スナップのデモ |Glitch"  

[GlitchPermissionPolicyDemoMain]: http://permission-policy-demo.glitch.me "OOPIF アクセス許可ポリシー |Glitch"  

[GnuSoftwareGzipManual]: https://www.gnu.org/software/gzip/manual "gzip: データ圧縮プログラム|GNU オペレーティング システム"  

[HttpwgSpecsRfc7231HtmlHeaderVary]: https://httpwg.org/specs/rfc7231.html#header.vary "Vary - Hypertext Transfer Protocol (HTTP/1.1): セマンティクスとコンテンツ |IETF HTTP ワーキング グループ"  

[JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]: https://webpack.js.org/guides/code-splitting/#:~:text=There%20are%20three%20general%20approaches%20to%20code%20splitting,Split%20code%20via%20inline%20function%20calls%20within%20modules. "利用可能なコード分割には、3 つの一般的な方法があります。エントリ ポイント: エントリ構成を使用してコードを手動で分割します。 重複を防止する: エントリの依存関係または SplitChunksPlugin を使用してチャンクを重複排除および分割します。 動的インポート: モジュール内のインライン関数呼び出しを介してコードを分割します。- コード分割|webpack"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタム プロパティ (変数) を使用する |MDN"  

[MdnDocsWebJavascriptReferenceOperatorsIn]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/in "in 演算子|MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "Image Generator |PWABuilder"  

[RollupjsMain]: https://rollupjs.org "rollup.js"  

[V8DevFeaturesPrivateBrandChecks]: https://v8.dev/features/private-brand-checks "プライベート ブランドは、obj ファイルで a.k.a. #fooをチェック|V8"  
[V8DevFeaturesClassFieldsPrivateClassFields]: https://v8.dev/features/class-fields#private-class-fields "プライベート クラス フィールド - パブリック クラスフィールドとプライベート クラス フィールド|V8"  

[WebpackJsMain]: https://webpack.js.org "webpack"  

> [!NOTE]
> <span data-ttu-id="e8880-398">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="e8880-398">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e8880-399">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-91)にあります。</span><span class="sxs-lookup"><span data-stu-id="e8880-399">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-91) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e8880-401">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e8880-401">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
