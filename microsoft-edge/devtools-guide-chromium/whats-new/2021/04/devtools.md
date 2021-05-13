---
description: Wavy の下線は、要素ツール、サービス ワーカー更新タイムラインなどでコードの問題を強調表示します。
title: DevTools の新機能 (Microsoft Edge 91)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 473b2537b631a77a182c04b6986051a4ce7aae03
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564820"
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
# <a name="whats-new-in-devtools-microsoft-edge-91"></a><span data-ttu-id="ee81c-104">DevTools の新機能 (Microsoft Edge 91)</span><span class="sxs-lookup"><span data-stu-id="ee81c-104">What's New In DevTools (Microsoft Edge 91)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a><span data-ttu-id="ee81c-105">Wavy の下線は、要素ツールのコードの問題と改善点を強調表示します</span><span class="sxs-lookup"><span data-stu-id="ee81c-105">Wavy underlines highlight code issues and improvements in Elements tool</span></span>  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

<span data-ttu-id="ee81c-106">最新のほとんどの ID では、テキストの下線が波線で構文エラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee81c-106">In most modern IDEs, wavy underlines under text indicate syntax errors.</span></span>   <span data-ttu-id="ee81c-107">バージョン Microsoft Edge 91 以降では、要素ツールの**DOM**ビューで HTML の下に波線が**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-107">In Microsoft Edge version 91 or later, wavy underlines display under HTML in the **DOM** view of the **Elements** tool.</span></span>  <span data-ttu-id="ee81c-108">波の下線は、アクセシビリティ、互換性、パフォーマンスに関連するコードの問題と提案を示します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-108">The wavy underlines indicate code issues and suggestions related to accessibility, compatibility, performance, and so on.</span></span>  <span data-ttu-id="ee81c-109">問題を確認および編集する方法の詳細については[、「DevTools][DevtoolsIssuesIndex]の問題の検索と修正」ツールMicrosoft Edgeを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee81c-109">For more information about how to review and edit issues, navigate to [Find and fix problems with the Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

<span data-ttu-id="ee81c-110">[問題] ツール **を開** き、問題の詳細と修正方法を確認するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-110">To open the **Issues** tool and learn more about the issue and how to fix it, complete one of the following actions.</span></span>  

*   <span data-ttu-id="ee81c-111">を選択して押 `Shift` し続け、波線の下線を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-111">Select and hold `Shift`, and then choose any wavy underline.</span></span>  
*   <span data-ttu-id="ee81c-112">次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-112">Complete the following actions.</span></span>  
    1.  <span data-ttu-id="ee81c-113">任意の波線の下線にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="ee81c-113">Hover on any wavy underline.</span></span>  
    1.  <span data-ttu-id="ee81c-114">コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-114">Open the contextual menu \(right-click\).</span></span>  
    1.  <span data-ttu-id="ee81c-115">[ **問題に表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ee81c-115">Choose **Show in Issues**.</span></span>  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="要素ツールで下線付きエラーを選択する" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         <span data-ttu-id="ee81c-117">要素ツールで下線付きエラーを **選択** する</span><span class="sxs-lookup"><span data-stu-id="ee81c-117">Choose the underlined error in the **Elements** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="[問題] ツールにエラーの詳細を表示する" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         <span data-ttu-id="ee81c-119">[問題] ツールにエラー **の詳細を表示** する</span><span class="sxs-lookup"><span data-stu-id="ee81c-119">Display error details in the **Issues** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="ee81c-120">有益なツール ヒントを使用した DevTools の詳細</span><span class="sxs-lookup"><span data-stu-id="ee81c-120">Learn about DevTools with informative tooltips</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

<span data-ttu-id="ee81c-121">DevTools ツールヒント機能は、DevTools のすべての異なるツールとウィンドウについて学習するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-121">The DevTools Tooltips feature helps you learn about all the different tools and panes in DevTools.</span></span>  <span data-ttu-id="ee81c-122">ツールヒントをオフにする場合は、 を選択します `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="ee81c-122">To turn off Tooltips, select `Esc`.</span></span>  <span data-ttu-id="ee81c-123">ツールヒントを有効にするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-123">To turn on Tooltips, complete one of the following actions.</span></span>  

*   <span data-ttu-id="ee81c-124">`Ctrl` + `Shift` + `H` \(Windows/Linux\) または `Cmd` + `Shift` + `H` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-124">Select `Ctrl`+`Shift`+`H` \(Windows/Linux\) or `Cmd`+`Shift`+`H` \(macOS\).</span></span>  
*   <span data-ttu-id="ee81c-125">[コマンド メニューを開き、][DevtoolsCommandMenuIndexOpenCommandMenu] と入力します `tooltips` 。</span><span class="sxs-lookup"><span data-stu-id="ee81c-125">[Open the Command Menu][DevtoolsCommandMenuIndexOpenCommandMenu] and then type `tooltips`.</span></span>  
*   <span data-ttu-id="ee81c-126">**[DevTools のツールヒントの**切り替え `...` > \*\*\*\* DevTools \( \) のカスタマイズと  >  **制御を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ee81c-126">Choose **Customize and control DevTools** \(`...`\) > **Help** > **Toggle the DevTools Tooltips**.</span></span>  

<span data-ttu-id="ee81c-127">また、フォーカス モードと [DevTools ツール][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] ヒント実験を有効にした場合は、アクティビティ バーの下部にある **[DevTools** ツールヒントの切り替え \( \) ] ボタンを `?` **選択することもできます**。</span><span class="sxs-lookup"><span data-stu-id="ee81c-127">Also, if you turn on the [Focus Mode and DevTools Tooltips][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] experiment, you may also choose the **Toggle the DevTools Tooltips** \(`?`\) button at the bottom of the **Activity Bar**.</span></span>  

<span data-ttu-id="ee81c-128">DevTools の使い方の詳細を表示するには、[ツールヒント] をオンにしてから、DevTools のアウトライン表示された各領域にマウス ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-128">To display more information about how to use the DevTools, turn on Tooltips, and then hover on each outlined region of the DevTools.</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="[問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置くと、詳細が表示されます。" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   <span data-ttu-id="ee81c-130">[問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置 **くと、詳細** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-130">Hover on anywhere in the highlighted region of the **Issues** tool to display more details</span></span>  
:::image-end:::  

## <a name="service-worker-update-timeline"></a><span data-ttu-id="ee81c-131">サービス ワーカーの更新タイムライン</span><span class="sxs-lookup"><span data-stu-id="ee81c-131">Service worker update timeline</span></span>  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

<span data-ttu-id="ee81c-132">バージョン 91 以降Microsoft Edge、プログレッシブ Web アプリまたは Service Worker 開発者の場合は、アプリケーション ツールでサービス ワーカーの更新ライフサイクルをタイムラインとして**表示**できます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-132">In Microsoft Edge version 91 or later, if you are a Progressive Web App or Service Worker developer, you may display the update lifecycle of your Service Workers as a timeline in the **Application** tool.</span></span>  <span data-ttu-id="ee81c-133">この機能は、サービス ワーカーが次の各段階で費やした時間を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-133">This feature helps you understand the time your Service Worker spends in each of the following stages.</span></span>  

*   **<span data-ttu-id="ee81c-134">Install</span><span class="sxs-lookup"><span data-stu-id="ee81c-134">Install</span></span>**  
*   **<span data-ttu-id="ee81c-135">待機</span><span class="sxs-lookup"><span data-stu-id="ee81c-135">Wait</span></span>**  
*   **<span data-ttu-id="ee81c-136">ライセンス認証</span><span class="sxs-lookup"><span data-stu-id="ee81c-136">Activate</span></span>**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="Service Worker の更新サイクルでタイムラインを確認する" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   <span data-ttu-id="ee81c-138">Service Worker **の更新** サイクル **で** タイムラインを確認する</span><span class="sxs-lookup"><span data-stu-id="ee81c-138">Review the **Timeline** in the **Update Cycle** for your Service Worker</span></span>  
:::image-end:::  

<span data-ttu-id="ee81c-139">サービス ワーカーのライフサイクルの詳細については、「Service Worker ライフサイクル [」に移動します][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-139">For more information about the lifecycle of your Service Workers, navigate to [The Service Worker lifecycle][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle].</span></span>  <span data-ttu-id="ee81c-140">DevTools のプログレッシブ Web アプリとサービス ワーカーのデバッグ ツールの詳細については、「Service Worker の機能強化 [」に移動します][DevtoolsServiceWorkerIndex]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-140">For more information about debugging tools for Progressive Web Apps and Service Workers in the DevTools, navigate to [Service Worker improvements][DevtoolsServiceWorkerIndex].</span></span>  <span data-ttu-id="ee81c-141">オープンソース プロジェクトでこの機能に関するリアルタイムの更新Chromium、Issue [1066604 に移動します][CR1066604]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-141">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1066604][CR1066604].</span></span>  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a><span data-ttu-id="ee81c-142">プログレッシブ Web アプリで四角形以外のアイコンに対する警告が表示されなくなりました</span><span class="sxs-lookup"><span data-stu-id="ee81c-142">Progressive Web Apps no longer display warnings for non-square icons</span></span>  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

<span data-ttu-id="ee81c-143">Microsoft Edge[バージョン 90][DevtoolsWhatsNew202102Devtools]以前では、PWA の Web アプリ マニフェストに四角形以外のアイコンを含める場合、\*\*\*\* アプリケーション ツールの [マニフェスト] セクション\*\*\*\* に、四角形以外のアイコンごとに [エラーと警告] の下に警告が表示されました。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ee81c-143">In [Microsoft Edge version 90][DevtoolsWhatsNew202102Devtools] or earlier, if you included a non-square icon in the Web App Manifest of your PWA, the **Manifest** section in the **Application** tool displayed a warning under **Errors and Warnings** for each non-square icon.</span></span>  <span data-ttu-id="ee81c-144">バージョン Microsoft Edge 91 以降では、少\*\*\*\* なくとも 1\*\*\*\* つの正方形のアイコンを指定した場合、アプリケーション ツールの [マニフェスト] セクションに警告は表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-144">In Microsoft Edge version 91 or later, the **Manifest** section in the **Application** tool displays no warnings if you provide at least one square icon.</span></span>  <span data-ttu-id="ee81c-145">四角形のアイコンを指定しない場合は、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-145">If you don't provide any square icons, a warning displays the following message.</span></span>  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="ee81c-147">バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-147">In Microsoft Edge version 90 or earlier, an error displays for each icon that is non-square</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="ee81c-149">バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな</span><span class="sxs-lookup"><span data-stu-id="ee81c-149">In Microsoft Edge version 91 or later, no error displays when you provide at least one square icon</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="ee81c-150">Web アプリ マニフェストでエラーと警告を確認するには、アプリケーション\*\*\*\* ツールに移動し、[マニフェスト] セクション**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-150">To review errors and warnings in your Web App Manifest, navigate to the **Application** tool and choose the **Manifest** section.</span></span>  <span data-ttu-id="ee81c-151">エラーと警告は、[エラーと警告] の **見出しの下に一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-151">Errors and warnings are listed under the **Errors and Warnings** heading.</span></span>  <span data-ttu-id="ee81c-152">Web アプリ マニフェストの詳細については、「Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する」 [に移動します][ProgressiveWebAppsWebappmanifests]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-152">For more information about the Web App Manifest, navigate to [Use the Web App Manifest to integrate your Progressive Web App into the Operating System][ProgressiveWebAppsWebappmanifests].</span></span>  <span data-ttu-id="ee81c-153">Web アプリ マニフェストに含めるアイコンを作成するには [、PWABuilder イメージ ジェネレーターに移動します][PwabuilderImagegenerator]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-153">To create icons to include in your Web App Manifest, navigate to the [PWABuilder Image Generator][PwabuilderImagegenerator].</span></span>  <span data-ttu-id="ee81c-154">オープンソース プロジェクトでこの機能に関するリアルタイムの更新Chromium、Issue [1185945 に移動します][CR1185945]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-154">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1185945][CR1185945].</span></span>  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a><span data-ttu-id="ee81c-155">ローカライズされた DevTools が、Chromiumベースのブラウザーでサポートされる</span><span class="sxs-lookup"><span data-stu-id="ee81c-155">Localized DevTools now supported in Chromium-based browsers</span></span>  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

<span data-ttu-id="ee81c-156">バージョン[81 Microsoft Edgeから][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]、DevTools Microsoft Edge独自の言語で表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-156">Starting in [Microsoft Edge version 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages], Microsoft Edge DevTools displays in your own language.</span></span>  <span data-ttu-id="ee81c-157">多くの開発者は、英語ではなく、StackOverflow や Visual Studio Codeなどの他の開発者ツールを母国語で使用しています。</span><span class="sxs-lookup"><span data-stu-id="ee81c-157">Many developers use other developer tools like StackOverflow and Visual Studio Code in their native language, not just in English.</span></span>  <span data-ttu-id="ee81c-158">DevTools Microsoft Edge、Chrome DevTools チーム、Google ライトハウス チームが協力して、すべてのユーザー ベースのブラウザーで同じChromium提供しました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-158">The Microsoft Edge DevTools team, Chrome DevTools team, and the Google Lighthouse team collaborated to provide the same experience in all Chromium-based browsers.</span></span>  <span data-ttu-id="ee81c-159">言語で DevTools を使用する方法の詳細については、「DevTools 言語設定の変更 [」に移動します][DevtoolsCustomizeLocalization]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-159">For more information about how to use DevTools in your language, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  <span data-ttu-id="ee81c-160">この機能に関するこの機能の詳細については、Chromium [1136655 に移動します][CR1136655]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-160">For more information about the collaboration on this feature in the Chromium open-source project, navigate to [1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edgeと DevTools が日本語に設定されている" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   <span data-ttu-id="ee81c-162">Microsoft Edgeと DevTools が日本語に設定されている</span><span class="sxs-lookup"><span data-stu-id="ee81c-162">Microsoft Edge browser and DevTools set to Japanese</span></span>  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a><span data-ttu-id="ee81c-163">キーボードを使用して CSS 変数に移動する</span><span class="sxs-lookup"><span data-stu-id="ee81c-163">Use the keyboard to navigate to CSS variables</span></span>  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

<span data-ttu-id="ee81c-164">バージョン[88 Microsoft Edgeから][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]、[スタイル] ウィンドウ\*\*\*\* に CSS 変数が表示され、各変数の定義へのリンクが直接提供されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-164">Starting in [Microsoft Edge version 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane], the **Styles** pane displays CSS variables and provides a link directly to the definition of each variable.</span></span>  <span data-ttu-id="ee81c-165">Microsoft Edge バージョン 91 以降では、矢印キーを使用して CSS 変数に簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-165">In Microsoft Edge version 91 or later, you may use the arrow keys to easily navigate to CSS variables.</span></span>  <span data-ttu-id="ee81c-166">[スタイル] ウィンドウで定義 **を開** く場合は、変数にカーソルを合わせると、 を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ee81c-166">To open the definition in the **Styles** pane, hover on a variable, and then select `Enter`.</span></span>  <span data-ttu-id="ee81c-167">CSS 変数の詳細については、「USING CSS カスタム プロパティ [(変数)」を参照してください][MdnDocsWebCssUsingCssCustomProperties]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-167">For more information about CSS variables, navigate to [Using CSS custom properties (variables)][MdnDocsWebCssUsingCssCustomProperties].</span></span>  <span data-ttu-id="ee81c-168">この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトChromium確認するには、Issue [1187735 に移動します][CR1187735]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-168">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1187735][CR1187735].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="スタイル ウィンドウで強調表示されている --theme-body-background CSS 変数" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   <span data-ttu-id="ee81c-170">[ `--theme-body-background` スタイル] ウィンドウで強調表示されている CSS**変数**</span><span class="sxs-lookup"><span data-stu-id="ee81c-170">The `--theme-body-background` CSS variable highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a><span data-ttu-id="ee81c-171">問題は重大度別に自動的に並べ替え</span><span class="sxs-lookup"><span data-stu-id="ee81c-171">Issues are automatically sorted by severity</span></span>  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

<span data-ttu-id="ee81c-172">[ **問題] ツール** には、アクセシビリティ、パフォーマンス、セキュリティなど、Web サイトを改善するための推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-172">The **Issues** tool displays recommendations to improve your website, including accessibility, performance, security, and so on.</span></span> <span data-ttu-id="ee81c-173">フィードバックに基づいて、問題は重大度別に自動的に並べ替えされます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-173">Based on your feedback, issues are now automatically sorted by severity.</span></span>  <span data-ttu-id="ee81c-174">各フィードバック カテゴリでは、エラーとしてマークされた\*\*\*\* 各問題が最初に表示され、警告としてマークされた\*\*\*\* 各問題の後に、ヒントとしてマークされた各問題が続**きます**。</span><span class="sxs-lookup"><span data-stu-id="ee81c-174">In each feedback category, each issue marked as an **Error** appears first, followed each issue marked as a **Warning**, then each issue marked as a **Tip**.</span></span>  <span data-ttu-id="ee81c-175">問題を絞り込むのに役立つ、追加のフィルター オプションが今後の更新に向け計画されています。</span><span class="sxs-lookup"><span data-stu-id="ee81c-175">To help you refine your issues, extra filter options are planned for a future update.</span></span>  <span data-ttu-id="ee81c-176">問題を確認する方法の詳細については、「DevTools の問題の検索と修正」Microsoft Edge[に移動します][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-176">For more information about how to review issues, navigate to [Find and fix problems with the Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text="[問題] ツールは、重大度別に並べ替えた問題を表示します。" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   <span data-ttu-id="ee81c-178">[ **問題] ツールは** 、重大度別に並べ替えた問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="ee81c-178">The **Issues** tool displays sorted issues by severity</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a><span data-ttu-id="ee81c-179">Microsoft Edgeバージョン 1.1.7 Visual Studio Code開発者向けツール</span><span class="sxs-lookup"><span data-stu-id="ee81c-179">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.7</span></span>  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

<span data-ttu-id="ee81c-180">拡張[Microsoft Edge][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]バージョン 1.1.7 Visual Studio Codeツールには、バージョン[88][DevtoolsWhatsNew202011Devtools]の DevTools Microsoft Edgeがあります。</span><span class="sxs-lookup"><span data-stu-id="ee81c-180">The [Microsoft Edge Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 provides the DevTools from [Microsoft Edge version 88][DevtoolsWhatsNew202011Devtools].</span></span>  <span data-ttu-id="ee81c-181">この拡張機能では、ARMがサポートされ、拡張機能の[デバッガーに依存Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]なくなりました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-181">This extension now supports ARM devices and no longer depends on the [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge] extension.</span></span>  <span data-ttu-id="ee81c-182">バージョン 1.1.7 には、次のバグ修正と改善が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee81c-182">Version 1.1.7 includes the following bug fixes and improvements.</span></span>  

*   <span data-ttu-id="ee81c-183">ターゲットクロージャの信頼性を更新しました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-183">Updated the reliability of target closure.</span></span>  
*   <span data-ttu-id="ee81c-184">作成または破棄されたターゲットをデバッグすると、サイド パネルが自動的に更新される更新を行いました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-184">Updated the side panel to automatically refreshes when you debug targets that are created or destroyed.</span></span>  
*   <span data-ttu-id="ee81c-185">拡張機能の設定と最新の Changelog に迅速にアクセスできる新しいコンテキスト メニューが追加されました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-185">Added a new contextual menu that gives you faster access to the extension settings and the latest Changelog.</span></span>  
*   <span data-ttu-id="ee81c-186">最新の機能を含む拡張機能のドキュメントのリリースを更新および簡略化しました。</span><span class="sxs-lookup"><span data-stu-id="ee81c-186">Updated and simplified the release of extension documentation including the newest features.</span></span>  
    
<span data-ttu-id="ee81c-187">バージョン 1.1.7 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。</span><span class="sxs-lookup"><span data-stu-id="ee81c-187">To manually update to version 1.1.7, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="ee81c-188">[vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルすると、拡張機能に貢献できます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-188">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

<!--## Announcements from the Chromium project  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### Ipsum et Chromium  

Lorem al lorem et Chromium  To review the history of this feature in the Chromium open-source project, navigate to Issue [xxxxxxx][CRxxxxxxx].  

:::image type="complex" source="../../media/2021/04/lorem-et-chromium.msft.png" alt-text="Ipsum et Chromium" lightbox="../../media/2021/04/lorem-et-chromium.msft.png":::
   Ipsum et Chromium  
:::image-end:::  -->  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="ee81c-189">Microsoft Edge プレビュー チャネルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ee81c-189">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="ee81c-190">Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ee81c-190">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="ee81c-191">プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ee81c-191">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="ee81c-192">Microsoft Edge DevTools チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="ee81c-192">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "他の言語で DevTools を使用する - What's New In DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../../whats-new/2020/11/devtools.md#css-variable-definitions-in-styles-pane "[スタイル] ウィンドウの CSS 変数定義 - DevTools の新機能 (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "フォーカス モードでツールをグループ化する - DevTools の新機能 (Microsoft Edge 90) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "[コマンド] メニューを開く - [DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "DevTools の言語設定を変更する | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "Service Worker の機能強化|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "Service Worker ライフサイクル - サービス ワーカーを使用してネットワーク要求とプッシュ通知を管理|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システム アプリケーションに統合|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "拡張機能を手動で更新する - 拡張機能 Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Visual Studio Code 用 Microsoft Edge Tools |Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  
[CR1066604]: https://crbug.com/1066604 "問題 1066604: DevTools: ServiceWorker のインストールとアクティブ化イベントの詳細を参照|Chromiumバグ"  
[CR1136655]: https://crbug.com/1136655 "問題 1136655: Devtools: ローカライズ V2 |Chromiumバグ"  
[CR1185945]: https://crbug.com/1185945 "問題 1185945: マニフェストの警告は、すべてのアイコンが正方形である必要|Chromiumバグ"  
[CR1187735]: https://crbug.com/1187735 "問題 1187735: アクセシビリティ: MAS2.1.1: キーボード: キーボードを使用して 'Var(...)' 関数を呼び出|Chromiumバグ"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタム プロパティ (変数) を使用する |MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "Image Generator |PWABuilder"  

<!--  > [!NOTE]
> Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].  
> The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-91) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).  

[![Creative Commons License][CCby4Image]][CCA4IL]  
This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen
-->
