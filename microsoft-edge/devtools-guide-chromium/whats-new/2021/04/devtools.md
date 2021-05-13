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
# <a name="whats-new-in-devtools-microsoft-edge-91"></a>DevTools の新機能 (Microsoft Edge 91)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a>Wavy の下線は、要素ツールのコードの問題と改善点を強調表示します  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

最新のほとんどの ID では、テキストの下線が波線で構文エラーを示しています。   バージョン Microsoft Edge 91 以降では、要素ツールの**DOM**ビューで HTML の下に波線が**表示**されます。  波の下線は、アクセシビリティ、互換性、パフォーマンスに関連するコードの問題と提案を示します。  問題を確認および編集する方法の詳細については[、「DevTools][DevtoolsIssuesIndex]の問題の検索と修正」ツールMicrosoft Edgeを参照してください。  

[問題] ツール **を開** き、問題の詳細と修正方法を確認するには、次のいずれかの操作を実行します。  

*   を選択して押 `Shift` し続け、波線の下線を選択します。  
*   次のアクションを実行します。  
    1.  任意の波線の下線にカーソルを合わせる。  
    1.  コンテキスト メニュー \(右クリック\) を開きます。  
    1.  [ **問題に表示] を選択します**。  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="要素ツールで下線付きエラーを選択する" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         要素ツールで下線付きエラーを **選択** する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="[問題] ツールにエラーの詳細を表示する" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         [問題] ツールにエラー **の詳細を表示** する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a>有益なツール ヒントを使用した DevTools の詳細  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

DevTools ツールヒント機能は、DevTools のすべての異なるツールとウィンドウについて学習するのに役立ちます。  ツールヒントをオフにする場合は、 を選択します `Esc` 。  ツールヒントを有効にするには、次のいずれかの操作を実行します。  

*   `Ctrl` + `Shift` + `H` \(Windows/Linux\) または `Cmd` + `Shift` + `H` \(macOS\) を選択します。  
*   [コマンド メニューを開き、][DevtoolsCommandMenuIndexOpenCommandMenu] と入力します `tooltips` 。  
*   **[DevTools のツールヒントの**切り替え `...` > **** DevTools \( \) のカスタマイズと  >  **制御を選択します**。  

また、フォーカス モードと [DevTools ツール][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] ヒント実験を有効にした場合は、アクティビティ バーの下部にある **[DevTools** ツールヒントの切り替え \( \) ] ボタンを `?` **選択することもできます**。  

DevTools の使い方の詳細を表示するには、[ツールヒント] をオンにしてから、DevTools のアウトライン表示された各領域にマウス ポインターを移動します。  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="[問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置くと、詳細が表示されます。" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   [問題] ツールの強調表示された領域の任意の場所にマウス ポインターを置 **くと、詳細** が表示されます。  
:::image-end:::  

## <a name="service-worker-update-timeline"></a>サービス ワーカーの更新タイムライン  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

バージョン 91 以降Microsoft Edge、プログレッシブ Web アプリまたは Service Worker 開発者の場合は、アプリケーション ツールでサービス ワーカーの更新ライフサイクルをタイムラインとして**表示**できます。  この機能は、サービス ワーカーが次の各段階で費やした時間を理解するのに役立ちます。  

*   **Install**  
*   **待機**  
*   **ライセンス認証**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="Service Worker の更新サイクルでタイムラインを確認する" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   Service Worker **の更新** サイクル **で** タイムラインを確認する  
:::image-end:::  

サービス ワーカーのライフサイクルの詳細については、「Service Worker ライフサイクル [」に移動します][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]。  DevTools のプログレッシブ Web アプリとサービス ワーカーのデバッグ ツールの詳細については、「Service Worker の機能強化 [」に移動します][DevtoolsServiceWorkerIndex]。  オープンソース プロジェクトでこの機能に関するリアルタイムの更新Chromium、Issue [1066604 に移動します][CR1066604]。  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a>プログレッシブ Web アプリで四角形以外のアイコンに対する警告が表示されなくなりました  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

Microsoft Edge[バージョン 90][DevtoolsWhatsNew202102Devtools]以前では、PWA の Web アプリ マニフェストに四角形以外のアイコンを含める場合、**** アプリケーション ツールの [マニフェスト] セクション**** に、四角形以外のアイコンごとに [エラーと警告] の下に警告が表示されました。 ****  バージョン Microsoft Edge 91 以降では、少**** なくとも 1**** つの正方形のアイコンを指定した場合、アプリケーション ツールの [マニフェスト] セクションに警告は表示されます。  四角形のアイコンを指定しない場合は、次のメッセージが表示されます。  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         バージョン 90 Microsoft Edgeでは、正方形以外のアイコンごとにエラーが表示されます。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         バージョン Microsoft Edge 91 以降では、少なくとも 1 つの正方形のアイコンを指定するとエラーが表示されな  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Web アプリ マニフェストでエラーと警告を確認するには、アプリケーション**** ツールに移動し、[マニフェスト] セクション**を選択**します。  エラーと警告は、[エラーと警告] の **見出しの下に一覧表示** されます。  Web アプリ マニフェストの詳細については、「Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する」 [に移動します][ProgressiveWebAppsWebappmanifests]。  Web アプリ マニフェストに含めるアイコンを作成するには [、PWABuilder イメージ ジェネレーターに移動します][PwabuilderImagegenerator]。  オープンソース プロジェクトでこの機能に関するリアルタイムの更新Chromium、Issue [1185945 に移動します][CR1185945]。  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a>ローカライズされた DevTools が、Chromiumベースのブラウザーでサポートされる  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

バージョン[81 Microsoft Edgeから][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]、DevTools Microsoft Edge独自の言語で表示されます。  多くの開発者は、英語ではなく、StackOverflow や Visual Studio Codeなどの他の開発者ツールを母国語で使用しています。  DevTools Microsoft Edge、Chrome DevTools チーム、Google ライトハウス チームが協力して、すべてのユーザー ベースのブラウザーで同じChromium提供しました。  言語で DevTools を使用する方法の詳細については、「DevTools 言語設定の変更 [」に移動します][DevtoolsCustomizeLocalization]。  この機能に関するこの機能の詳細については、Chromium [1136655 に移動します][CR1136655]。  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edgeと DevTools が日本語に設定されている" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   Microsoft Edgeと DevTools が日本語に設定されている  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a>キーボードを使用して CSS 変数に移動する  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

バージョン[88 Microsoft Edgeから][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]、[スタイル] ウィンドウ**** に CSS 変数が表示され、各変数の定義へのリンクが直接提供されます。  Microsoft Edge バージョン 91 以降では、矢印キーを使用して CSS 変数に簡単に移動できます。  [スタイル] ウィンドウで定義 **を開** く場合は、変数にカーソルを合わせると、 を選択します `Enter` 。  CSS 変数の詳細については、「USING CSS カスタム プロパティ [(変数)」を参照してください][MdnDocsWebCssUsingCssCustomProperties]。  この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトChromium確認するには、Issue [1187735 に移動します][CR1187735]。  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="スタイル ウィンドウで強調表示されている --theme-body-background CSS 変数" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   [ `--theme-body-background` スタイル] ウィンドウで強調表示されている CSS**変数**  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a>問題は重大度別に自動的に並べ替え  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

[ **問題] ツール** には、アクセシビリティ、パフォーマンス、セキュリティなど、Web サイトを改善するための推奨事項が表示されます。 フィードバックに基づいて、問題は重大度別に自動的に並べ替えされます。  各フィードバック カテゴリでは、エラーとしてマークされた**** 各問題が最初に表示され、警告としてマークされた**** 各問題の後に、ヒントとしてマークされた各問題が続**きます**。  問題を絞り込むのに役立つ、追加のフィルター オプションが今後の更新に向け計画されています。  問題を確認する方法の詳細については、「DevTools の問題の検索と修正」Microsoft Edge[に移動します][DevtoolsIssuesIndex]。  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text="[問題] ツールは、重大度別に並べ替えた問題を表示します。" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   [ **問題] ツールは** 、重大度別に並べ替えた問題を表示します。  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a>Microsoft Edgeバージョン 1.1.7 Visual Studio Code開発者向けツール  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

拡張[Microsoft Edge][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]バージョン 1.1.7 Visual Studio Codeツールには、バージョン[88][DevtoolsWhatsNew202011Devtools]の DevTools Microsoft Edgeがあります。  この拡張機能では、ARMがサポートされ、拡張機能の[デバッガーに依存Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]なくなりました。  バージョン 1.1.7 には、次のバグ修正と改善が含まれています。  

*   ターゲットクロージャの信頼性を更新しました。  
*   作成または破棄されたターゲットをデバッグすると、サイド パネルが自動的に更新される更新を行いました。  
*   拡張機能の設定と最新の Changelog に迅速にアクセスできる新しいコンテキスト メニューが追加されました。  
*   最新の機能を含む拡張機能のドキュメントのリリースを更新および簡略化しました。  
    
バージョン 1.1.7 に手動で更新するには、[拡張機能を手動で更新 [する] に移動します][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  [vscode-edge-devtools GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]で問題をファイルすると、拡張機能に貢献できます。  

<!--## Announcements from the Chromium project  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### Ipsum et Chromium  

Lorem al lorem et Chromium  To review the history of this feature in the Chromium open-source project, navigate to Issue [xxxxxxx][CRxxxxxxx].  

:::image type="complex" source="../../media/2021/04/lorem-et-chromium.msft.png" alt-text="Ipsum et Chromium" lightbox="../../media/2021/04/lorem-et-chromium.msft.png":::
   Ipsum et Chromium  
:::image-end:::  -->  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

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
