---
description: Wavy の下線は、要素ツール、サービス ワーカー更新タイムラインなどでコードの問題を強調表示します。
title: DevTools の新機能 (Microsoft Edge 91)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5f499a6c9f1109f80a9d459edf94ed2226734f19
ms.sourcegitcommit: 87ba918b0910373bb645615377709bf140dc9b19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "11583460"
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

バージョン 91 以降Microsoft Edgeプログレッシブ Web アプリまたは Service Worker 開発者の場合は、アプリケーション ツールでサービス ワーカーの更新ライフサイクルをタイムラインとして**表示**します。  この機能は、サービス ワーカーが次の各段階で費やした時間を理解するのに役立ちます。  

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

Microsoft Edge [90][DevtoolsWhatsNew202102Devtools]以前のバージョンでは、PWA の Web アプリ マニフェストに四角形以外のアイコンが含まれている場合は、四角形以外**** のアイコンごとに [エラーと警告] セクションに警告が表示されました。  バージョン Microsoft Edge 91 以降では、少**** なくとも 1**** つの正方形のアイコンを指定した場合、アプリケーション ツールの [マニフェスト] セクションに警告は表示されます。  四角形のアイコンを指定しない場合は、次のメッセージが表示されます。  

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

Web アプリ マニフェストでエラーと警告を確認するには、アプリケーション**** ツールに移動し、[マニフェスト] セクション**を選択**します。  エラーと警告は、[エラーと警告] の **見出しの下に一覧表示** されます。  Web アプリ マニフェストの詳細については、「Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する」 [に移動します][ProgressiveWebAppsWebappmanifests]。  Web アプリ マニフェストに含めるアイコンを作成するには [、PWABuilder イメージ ジェネレーターに移動します][PwabuilderImagegenerator]。  Chromium オープンソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[Issue [1185945][CR1185945] に移動します。  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a>ローカライズされた DevTools が、Chromiumベースのブラウザーでサポートされる  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

バージョン[81 Microsoft Edgeから][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]、DevTools Microsoft Edge独自の言語で表示されます。  多くの開発者は、英語ではなく、StackOverflow や Visual Studio Codeなどの他の開発者ツールを母国語で使用しています。  DevTools Microsoft Edge、Chrome DevTools チーム、Google ライトハウス チームが協力して、すべてのユーザー ベースのブラウザーで同じChromium提供しました。  言語で DevTools を使用する方法の詳細については、「DevTools 言語設定の変更 [」に移動します][DevtoolsCustomizeLocalization]。  Chromium オープンソース プロジェクトでのこの機能のコラボレーションの詳細については、「[1136655][CR1136655]」に移動します。  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edgeと DevTools が日本語に設定されている" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   Microsoft Edgeと DevTools が日本語に設定されている  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a>キーボードを使用して CSS 変数に移動する  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

バージョン[88 Microsoft Edgeから][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]、[スタイル] ウィンドウ**** に CSS 変数が表示され、各変数の定義へのリンクが直接提供されます。  Microsoft Edge バージョン 91 以降では、矢印キーを使用して CSS 変数に簡単に移動できます。  [スタイル] ウィンドウで定義 **を開** く場合は、変数にカーソルを合わせると、 を選択します `Enter` 。  CSS 変数の詳細については、「USING CSS カスタム プロパティ [(変数)」を参照してください][MdnDocsWebCssUsingCssCustomProperties]。  Chromium オープンソース プロジェクトでこの機能に関するリアルタイム更新プログラムを確認するには、[Issue [1187735][CR1187735] に移動します。  

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

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="visualize-css-scroll-snap"></a>CSS のスクロール スナップを表示する  

これで、要素ツールの `scroll-snap` バッジを切り **替** え、CSS のスクロール スナップの配置を検査できます。  Web ページの HTML 要素が適用されると、その横に [要素] ツール `scroll-snap-type` `scroll-snap` にバッジが **表示** されます。  Web ページ上のスクロール スナップ オーバーレイの表示を \(または off\) オンにするバッジを選択します。  Web ページの例を確認するには、[デモのスクロール][スナップ移動します][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]。  この例では、スナップエッジにドットが表示されます。  スクロール ポートのアウトラインは、スナップ項目にダッシュアウトラインがある場合は、アウトラインが点灯します。  スクロールの余白がオレンジ色で塗りつぶされている間、スクロールの余白は緑で塗りつぶされます。  この機能の履歴をオープンソース プロジェクトで確認するにはChromium Issue [862450 に移動します][CR862450]。  

:::image type="complex" source="../../media/2021/04/elements-scroll-snap-highlight.msft.png" alt-text="CSS のスクロール スナップ" lightbox="../../media/2021/04/elements-scroll-snap-highlight.msft.png":::
   CSS のスクロール スナップ  
:::image-end:::  

### <a name="new-memory-inspector-tool"></a>新しいメモリ インスペクター ツール  

新しいメモリ **インスペクター ツールを** 使用して、JavaScript メモリと `ArrayBuffer` Wasm メモリを検査します。  JS デモ [Web ページでメモリを][GlitchMemoryInspectorDemoJsHtml] 開きます。  [ソース **] ツールで** 、ファイルを開 `memory-write-wasm` き、行にブレークポイントを設定します `0x03c` 。  Web ページを更新します。  デバッガー ウィンドウ **で [** スコープ] セクションを展開します。  バッファー値の横に新しいアイコン **が表示** されます。  新しいメモリ インスペクター ツールを **開く場合は、このツールを選択** します。  

ソース ツールでのデバッグの詳細については****、「デバッガー ウィンドウを使用して JavaScript コードをデバッグする[」に移動します][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]。  この機能の履歴を Chromium オープンソース プロジェクトで確認するには、[Issue [1166577][CR1166577] に移動します。  

:::image type="complex" source="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png" alt-text="メモリ インスペクター ツール" lightbox="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png":::
   **メモリ インスペクター** ツール  
:::image-end:::  

### <a name="new-badge-settings-pane-in-the-elements-tool"></a>[要素] ツールの [新しいバッジ設定] ウィンドウ  

次に、 **要素ツールのバッジ** 設定 **を使用** して、個々のバッジを \(または off\) オンにします。  この機能を使用して、Web ページの検査中に重要なバッジをカスタマイズし、集中します。  [要素] ツールの上部にバッジ設定ウィンドウを **表示** するには、次の操作を実行します。  

1.  任意の要素にカーソルを合わせる。  
1.  コンテキスト メニュー \(右クリック\) を開きます。  
1.  [ **バッジの設定]を選択します**。  
    
バッジを \(または hide\) で表示するには、バッジ名の横にあるチェックボックスを \(または remove\) を選択します。  

<!--  To review the history of this feature in the Chromium open-source project, navigate to Issue [1066772][CR1066772].  -->  

:::image type="complex" source="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png" alt-text="要素ツールのバッジ設定ウィンドウ" lightbox="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png":::
   **要素ツールの** バッジ **設定** ウィンドウ  
:::image-end:::  

### <a name="enhanced-image-preview-with-aspect-ratio-information"></a>縦横比情報による拡張画像プレビュー  

DevTools のイメージ プレビューは、次の詳細を含む詳細情報を表示するために拡張されました。  

*   レンダリングされたサイズ  
*   レンダリングされた縦横比  
*   組み込みサイズ  
*   組み込みの縦横比  
*   ファイル サイズ  
    
この情報は、画像をよりよく理解し、最適化を適用するのに役立ちます。  画像の縦横比情報は、画像プレビュー **を選択** するときにネットワーク ツールでも使用できます。  

:::row:::
   :::column span="":::
      [要素 **] ツール** で、画像のプレビューに画像に関する詳細が表示されます。  
   :::column-end:::
   :::column span="":::
      また、画像の縦横比情報は、画像 **プレビューを選択** するときにネットワーク ツールで使用できます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png" alt-text="要素ツールの縦横比情報を含む画像プレビュー" lightbox="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png":::
         要素ツールの縦横比情報を含む画像**プレビュー**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/network-img-name-filters-preview.msft.png" alt-text="ネットワーク ツールの画像縦横比情報" lightbox="../../media/2021/04/network-img-name-filters-preview.msft.png":::
         ネットワーク ツールの画像縦横 **比** 情報  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、「Issues [1149832][CR1149832]」および[1170656][CR1170656]に移動します。  

### <a name="new-options-to-configure-content-encodings-in-the-network-conditions-tool"></a>ネットワーク条件ツールでコンテンツ エンコードを構成するための新しいオプション 

[ネットワーク]**ツールで**、新しい [その他のネットワーク条件******]を選択します。[** 調整] ドロップダウン メニューの横にあるボタンをクリックして、[ネットワーク条件]**ツールを開**きます。  [gzip、brotli、][GnuSoftwareGzipManual]または別の将来をサポートしないブラウザーでサーバー応答が正しく[][|::ref1::|Main]エンコードされていることをテストするには、次のアクション `Content-Encoding` を実行します。  

1.  ネットワーク条件 **ツールを開** く
1.  [承諾された **コンテンツ エンコード] に移動します**。 
1.  テストするチェックボックスの横 `Content-Encoding` にあるチェック ボックスをオフにします。  
    
Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1162042][CR1162042] に移動します。  

:::image type="complex" source="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png" alt-text="新しいその他のネットワーク条件...ボタンをクリックすると、[ネットワーク条件] ツールが開き、コンテンツ エンコードを構成します。" lightbox="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png":::
   New **More network conditions....** ボタンは、 **構成するネットワーク条件** ツールを開きます `Content-Encoding`  
:::image-end:::  

### <a name="styles-pane-enhancements"></a>スタイル ウィンドウの機能強化  

#### <a name="new-shortcut-to-display-computed-value-in-the-styles-pane"></a>[スタイル] ウィンドウに計算値を表示する新しいショートカット  

次に、[スタイル] ウィンドウに計算された CSS 値 **を表示** するには、次の操作を実行します。  

1.  CSS プロパティにカーソルを合わせる。  
1.  コンテキスト メニュー \(右クリック\) を開きます。  
1.  [ **計算値の表示] を選択します**。  
    
Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1076198][CR1076198] に移動します。  

:::image type="complex" source="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png" alt-text="計算値を表示する新しいショートカット" lightbox="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png":::
   計算値を表示する新しいショートカット  
:::image-end:::  

#### <a name="support-for-the-accent-color-keyword"></a>アクセントカラー キーワードのサポート  

スタイル ウィンドウのオートコンプリート UI**** で CSS キーワードが検出され、要素によって生成される UI コントロールのアクセントカラー `accent-color` を指定できます。  要素によって生成される UI コントロールの例には、チェック ボックスやラジオ ボタンがあります。 実装の状態の詳細については、「フィーチャー: Chromium CSS プロパティ」[に移動します][ChromestatusFeature4752739957473280]。  この機能を有効にする場合は、チェック ボックスに移動 `edge://flags#enable-experimental-web-platform-features` して [有効] に **設定します**。  この機能の履歴を Chromium オープンソース プロジェクトで確認するには、[Issue [1092093][CR1092093] に移動します。  

:::image type="complex" source="../../media/2021/04/elements-styles-accent-color.msft.png" alt-text="アクセントカラー CSS キーワード" lightbox="../../media/2021/04/elements-styles-accent-color.msft.png":::
   `accent-color` CSS キーワード
:::image-end:::  

### <a name="display-details-about-blocked-features-in-the-frame-details-view"></a>[フレームの詳細] ビューにブロックされた機能の詳細を表示する  

アクセス許可ポリシーは、Web プラットフォーム API で、Web サイトが個々のフレームまたは埋め込みブラウザー機能の使用を許可またはブロックする機能を `iframe` 提供します。 詳細については、「アクセス許可ポリシー [の説明」に移動します][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]。  機能がブロックされる理由の詳細を表示するには、次のアクションを実行します。  

1.  [[OOPIF アクセス許可ポリシー] に移動します][GlitchPermissionPolicyDemoMain]。  
1.  [アプリケーション] ツール **に移動** します。  
1.  フレームを選択します。  
1.  [アクセス許可ポリシー **] セクションに移動** します。  
1.  [無効な機能 **] プロパティに移動** します。  
1.  [詳細 **の表示] を選択します**。  
1.  各ポリシーの横にあるアイコンを選択して、機能をブロックしたネットワーク `iframe` 要求に移動します。  
    
Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1158827][CR1158827] に移動します。  

:::image type="complex" source="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png" alt-text="[フレームの詳細] ビューのブロックされた機能" lightbox="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png":::
   [フレームの詳細] ビューのブロックされた機能  
:::image-end:::  

### <a name="filter-experiments-in-the-experiments-setting"></a>[実験] 設定で実験をフィルター処理する  

新しい実験フィルターを使用して、実験を迅速に見つける。  たとえば、コードの問題に関する新しい実験を有効にするには、次のアクションを実行します。
``

1.  [テスト]**設定**  >  **移動します**。  
1.  [フィルター] **テキスト ボックスに** 移動します。  
1.  「`issues`」と入力します。  
    
:::image type="complex" source="../../media/2021/04/settings-experiments-filter-by-issues.msft.png" alt-text="[実験] 設定で実験をフィルター処理する" lightbox="../../media/2021/04/settings-experiments-filter-by-issues.msft.png":::
   [実験] 設定で **実験をフィルター** 処理する  
:::image-end:::  

### <a name="new-vary-header-column-in-the-cache-storage-pane"></a>[キャッシュ] ストレージ ウィンドウの [ヘッダーの変更] 列  

[キャッシュ] ウィンドウ `Vary Header` の新**しいStorageを使用**して、[HTTP[][HttpwgSpecsRfc7231HtmlHeaderVary]応答ヘッダーの値を変更する] を表示します。  Chromium プロジェクトでこの機能の履歴を確認するには、[Issue [1186049][CR1186049]に移動します。  

:::image type="complex" source="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png" alt-text="[ヘッダーの変更] 列" lightbox="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png":::
   [ヘッダーの変更] 列  
:::image-end:::  

### <a name="sources-tool-improvements"></a>ソース ツールの機能強化  

#### <a name="support-for-new-javascript-features"></a>新しい JavaScript 機能のサポート  

DevTools は、新しいプライベート ブランドチェック [a.k.a. #foo obj][V8DevFeaturesPrivateBrandChecks] JavaScript 言語機能をサポートしています。  プライベート ブランド チェック機能は、in 演算子を拡張 [して][MdnDocsWebJavascriptReferenceOperatorsIn] 、特定のオブジェクトの [Private クラス フィールド][V8DevFeaturesClassFieldsPrivateClassFields] をサポートします。  コンソール ツールとソース**ツール****で試**してみてください。  また、プライベート フィールドを検査するには、次のアクションを実行します。  

1.  デバッガー ウィンドウ **に移動** します。  
1.  [スコープ] **セクションに移動** します。  
    
オープンソース プロジェクトでこの機能の履歴を確認Chromium、Issue [11374 に移動します][CR11374]。  

:::image type="complex" source="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png" alt-text="JavaScript のプライベート ブランド チェック" lightbox="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png":::
   JavaScript のプライベート ブランド チェック  
:::image-end:::  

#### <a name="enhanced-support-for-breakpoints-debugging"></a>ブレークポイントのデバッグのサポートの強化  

Webpack やロールアップのような最新 [の JavaScript][WebpackJsMain]バンドル [は、コード][RollupjsMain] 分割をサポートします。  コード分割の詳細については、「コード分割」 [に移動します][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]。  バージョン 90 Microsoft Edgeバージョンでは、DevTools は 1 つのバンドルにのみブレークポイントを設定します。  バージョン 91 以降Microsoft Edge DevTools は、共有コンポーネントをデバッグするときに複数のバンドルにブレークポイントを適切に設定します。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issues [1142705][CR1142705]、979000、および [1180794][CR1180794]に移動します。 [][CR979000]  

#### <a name="support-hover-preview-with-bracket-notation"></a>かっこ表記を使用したホバー プレビューのサポート  

DevTools は、ソース ツールの表記を使用する JavaScript メンバー式のホバー `[]` プレビュー **をサポート** しました。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1178305][CR1178305] に移動します。  

:::image type="complex" source="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png" alt-text="[] 表記でホバー プレビューをサポートする" lightbox="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png":::
   表記付きホバー プレビューの `[]` サポート  
:::image-end:::  

#### <a name="improved-outline-of-html-files"></a>HTML ファイルのアウトラインの改善  

DevTools では、ファイルのアウトラインサポートが向上 `.html` しました。  [ソース **] ツールで** 、ファイルを開 `.html` きます。  \(or off\) コード アウトラインを有効にする場合は、Windows/Linux または `Ctrl` + `Shift` + `O` `Cmd` + `Shift` + `O` macOS で選択します。  次の図では、DevTools がアウトライン内のすべての関数を正しく一覧表示するようになりました。  以前は、DevTools は一部の関数のみを表示しました。  Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、Issues [761019][CR761019]および [1191465][CR1191465]に移動します。  

:::image type="complex" source="../../media/2021/04/sources-page-jobobbx-at.msft.png" alt-text=" HTML ファイルのアウトラインの改善" lightbox="../../media/2021/04/sources-page-jobobbx-at.msft.png":::
   HTML ファイルのアウトラインの改善  
:::image-end:::  

#### <a name="proper-error-stack-traces-for-wasm-debugging"></a>Wasm デバッグの適切なエラー スタック トレース  

バージョン 90 Microsoft Edge以前のバージョンでは、DevTools はエラー スタック トレースで汎用の Wasm 参照のみを表示しました。  バージョン 91 以降Microsoft Edge DevTools はインライン関数要求を解決し、Wasm デバッグのエラー スタック トレースにソースの場所を表示します。  コンソールのエラー スタック トレースの詳細については、 **エラー**に移動 [します][DevtoolsConsoleApiError]。  

バージョン 91 以降Microsoft Edge DevTools はインライン関数要求を解決し、Wasm デバッグの適切なエラー スタック トレースを表示します。  

:::row:::
   :::column span="":::
      バージョン 90 Microsoft Edge以前のバージョンでは、ソースの場所はエラー スタック トレースに表示されません。  ソースの場所には、 が含まれます `dsquare` 。  
   :::column-end:::
   :::column span="":::
      バージョン Microsoft Edge 91 以降では、エラー スタック トレースにソースの場所が表示されます。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png" alt-text="Wasm デバッグの以前のエラー スタック トレース" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png":::
         Wasm デバッグの適切なエラー スタック トレース  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png" alt-text="Wasm デバッグの適切なエラー スタック トレース" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png":::
         Wasm デバッグの適切なエラー スタック トレース  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium オープンソース プロジェクトでこの機能の履歴を確認するには、[Issue [1189161][CR1189161] に移動します。  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 既定の開発ブラウザーとして [Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]の使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

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
[DevtoolsIssuesIndex]: ../../../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
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
https://crbug.com/1187735[CR1187735]: "Issue 1187735: アクセシビリティ: MAS2.1.1: キーボード: キーボードを使用して 'Var(...)' 関数を呼び出|Chromiumバグ」  
[CR1189161]: https://crbug.com/1189161 "Issue 1189161: スタックトレースは `new Error` DWARF 経由で変換されません"  
[CR1191465]: https://crbug.com/1191465 "Issue 1191465: Ctrl + Shift+O が HTML で壊れている"  

[GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "アクセス許可ポリシーの説明| GitHub"  

[GlitchMemoryInspectorDemoJsHtml]: https://memory-inspector.glitch.me/demo-js.html "JS ファイルのメモリ|Glitch"  
[GlitchMemoryInspectorDemoWasmHtml]: https://memory-inspector.glitch.me/demo-wasm.html "Wasm |Glitch"  

[GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]: https://microsoft-edge-chromium-devtools.glitch.me/css-dbg-stories/css-scroll-snap.html "[デモスナップスクロール|Glitch"  

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
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-91)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
