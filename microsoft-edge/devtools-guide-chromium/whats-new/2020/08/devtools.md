---
description: キーボード ショートカットを Visual Studio Code と一致させる、Surface Duo と Samsung Galaxy Fold をエミュレートする、CSS グリッドのオーバーレイの機能強化など。
title: DevTools の新機能 (Microsoft Edge 86)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 3853f097877fc45b14ceb0674309cb35b58a0aa6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398617"
---
# <a name="whats-new-in-devtools-microsoft-edge-86"></a>DevTools の新機能 (Microsoft Edge 86)  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <a name="match-keyboard-shortcuts-in-devtools-to-visual-studio-code"></a>DevTools のキーボード ショートカットを Visual Studio Code と一致させる  

Microsoft Edge 86 では、DevTools のキーボード ショートカットを Microsoft コードのショートカットと一致Visual Studio [があります][VisualStudioCode]。  

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="DevTools のキーボード ショートカットを Visual Studio Code と一致させる" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   DevTools のキーボード ショートカットを Visual Studio Code と一致させる  
:::image-end:::  

この機能を有効にするには、「[Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする][DevtoolsCustomizeShortcuts]」に移動します。  

たとえば、[Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボード ショートカットは `F5` です。  **DevTools (既定)** の事前設定では、DevTools での同じショートカットは `F8` ですが、**Visual Studio Code** の事前設定を選ぶと、`F5` も同じショートカットとして利用できるようになります。  

Chromium の問題 [#174309][CR174309]  

### <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>Surface Duo と Samsung Galaxy Fold のエミュレート  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

Microsoft Edge を使用して、[Surface Duo][MicrosoftSurfaceDevicesDuo] と [Samsung Galaxy Fold][SamsungMobileGalaxyFold] の 2 つの新しいデバイスでの Web サイトまたはアプリの外観をテストできるようになりました。  

デュアルスクリーン デバイスと折りたたみ式デバイスのために Web サイトやアプリを強化するには、[デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。  

*   [スパニング][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: Web サイト (またはアプリ) が両方の画面に表示されます。
*   [シームのレンダリング][DualScreenIntroductionHowWorkSeam]: シームとは、2 つの画面の間の領域のことです。
*   [試験的な Web プラットフォーム API を有効にして][DevtoolsExperimentalFeaturesEnableExperimentalApis]、新しい [CSS メディア画面スパニング機能][DualScreenWebCssMediaSpanning]と [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments] にアクセスします。  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Surface Duo のデバイス エミュレーション" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   Surface Duo のデバイス エミュレーション  
:::image-end:::  

この試験的機能を有効にするには、「[実験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**エミュレーション: デュアル スクリーン モードのサポート**] の横にあるチェックボックスをオンにします。  

この実験の詳細については、「[エミュレーション: デュアル スクリーン モードのサポート][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]」を参照してください。  

Chromium の問題: [#1054281][CR1054281]  

### <a name="css-grid-overlay-improvements-and-new-experimental-grid-features"></a>CSS グリッドのオーバーレイの機能強化と新しい試験的なグリッド機能  

CSS グリッドのオーバーレイの機能強化について、積極的なご意見をお寄せいただきありがとうございました。  CSS グリッドのオーバーレイは既定で有効になりましたので、実験を有効にする必要はありません。  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="article 要素の CSS グリッドのオーバーレイ" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   `article` 要素の CSS グリッドのオーバーレイ  
:::image-end:::  

> [!NOTE]
> グリッド オーバーレイの詳細については、「CSS グリッド デバッグ [機能」に移動します][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]。  

Microsoft Edge DevTools チームと Chrome DevTools チームは、追加機能のための共同作業を行っています。  新しい機能には、要素ツールの新しいレイアウト ウィンドウから永続的**** で構成可能な複数のオーバーレイ**が含**まれます。  

この試験的機能を有効にするには、「[実験的な機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**新しい CSS グリッドのデバッグ機能を有効にする (再起動後、[要素] にある [レイアウト] サイド バーウィンドウで構成オプションを利用できます)**] の横にあるチェックボックスをオンにします。  

この実験の詳細については、「[新しい CSS グリッドのデバッグ機能を有効にする][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]」を参照してください。  

Chromium の問題: [#1047356][CR1047356]  

### <a name="table-copied-from-the-console-preserves-formatting"></a>コンソールからコピーした表の書式の保持  

Microsoft Edge 85 以前のバージョンでは、コピーした `console.table` の書式設定が失われていました。  [table][DevtoolsConsoleApiTable] コンソール API から出力をコピーして貼り付けた場合、表のテキストのみが保持されました。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="Microsoft Edge 85 以前の table コンソール API の出力" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` Microsoft Edge 85 以前のコンソール API の出力  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 85 以前のバージョンから Visual Studio Code に貼り付けられた table コンソール API" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 85 以前のバージョンから Visual Studio Code に貼り付けられたコンソール API  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Microsoft Edge 86 以降のバージョンでは、**コンソール**から表をコピーすると、書式設定が保持されるようになりました。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="Microsoft Edge 86 以降の table コンソール API の出力" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` Microsoft Edge 86 以降のコンソール API の出力  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="Microsoft Edge 86 以降のバージョンから Visual Studio Code に貼り付けられた table コンソール API" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 86 以降のバージョンから Visual Studio Code に貼り付けられたコンソール API  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium の問題: [#1115011][CR1115011]  

### <a name="source-order-viewer-for-easier-accessibility-testing"></a>アクセシビリティ テストをより簡単にするためのソース オーダー ビューアー  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

新しくなったアクセシビリティ ヘルパーでは、ソース内の要素の順序を表示できます。  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="ソースの順序の表示を有効にする" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   **ソースの順序の表示**を有効にする  
:::image-end:::  

この機能により、スクリーン リーダーとキーボード ユーザーの Web サイトまたはアプリ エクスペリエンスをより簡単にテストできます。  スクリーン リーダーとキーボード ナビゲーションは、コンテンツが Web サイトまたはアプリのソース コードと同じ順序で配置され、レンダリングするページと一致しているかどうかに依存しています。  ソース オーダー ビューアーは、レンダリングされたページとソース コードの順序の潜在的な相違点を表示します。  

この試験的機能を有効にするには、「[試験的機能を有効にする][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]」に移動し、[**ソース オーダー ビューアーを有効にする**] の横にあるチェックボックスをオンにします。  

この実験の詳細については、「[ソース オーダー ビューアーを有効にする][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]」を参照してください。  

Chromium の問題: [#1094406][CR1094406]  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="Microsoft Edge DevTools in Traditional Chinese" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="Microsoft Edge DevTools in Japanese" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### <a name="highlight-all-search-results-in-elements-tool"></a>[要素] ツールですべての検索結果を強調表示する  

Microsoft Edge 84 および 85 では、要素ツールの最初 **の検索結果が** 強調表示されない。  残りの検索結果だけが正しく強調表示されました。  

フィードバックにより Chromium の改善にご協力いただき、ありがとうございました。  フィードバックにより、オープン ソースの Chromium プロジェクトの問題 [#1103316][CR1103316] が発見されました。  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="Microsoft Edge 84 以降のバージョンで [要素] パネルで最初の検索結果が強調表示されている" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   Microsoft Edge 84 以降の **要素** ツールで最初の検索結果を強調表示  
:::image-end:::  

この問題は、Microsoft Edge のすべてのバージョンで修正されました。  

Chromium の問題: [#1103316][CR1103316]  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-media-tool"></a>新しいメディア ツール  

DevTools は、メディア ツールにメディア プレイヤーの情報を [表示][DevtoolsMediaPanelIndex] します。  

新しいメディア ツールを **開く** 場合は、次の手順を実行します。  

1.  [**DevTools のカスタマイズとコントロール**] \(`...`\) > [**その他のツール**] > [**メディア**] の順に選びます。  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="新しいメディア ツール" lightbox="../../media/2020/08/media-panel.msft.png":::
       新 **しいメディア** ツール  
    :::image-end:::  

DevTools **の新** しいメディア ツールの前に、ビデオ プレーヤーに関するログとデバッグの情報は、[最近使ったプレイヤー] **設定の下に置** かれていました。  [最近使用した **プレイヤー] 設定を** 開く場合は、[ `edge://media-internals` プレイヤー] ツールに移動して **選択** します。  

ライブ コンテンツを表示して、次の例を含む潜在的な問題をより迅速に検査します。  

*   フレームが破棄される原因。  
*   JavaScript が予期しない方法でプレーヤーと対話している原因。  

### <a name="capture-node-screenshots-using-the-elements-tool-context-menu"></a>要素ツールのコンテキスト メニューを使用してノードのスクリーンショットをキャプチャする  

要素ツールのコンテキスト メニューを使用して、ノードのスクリーンショットを **キャプチャ** できます。  

たとえば、目次のスクリーンショットを撮るには、要素にカーソルを合わせてコンテキスト メニューを開き (右クリック)、[**ノードのスクリーンショットをキャプチャ**] を選びます。  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="ノードのスクリーンショットのキャプチャ" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   ノードのスクリーンショットのキャプチャ  
:::image-end:::  

Chromium の問題: [#1100253][CR1100253]  

### <a name="issues-tool-updates"></a>[問題] ツールの更新  

コンソール ツールの [問題] **警告バー** が通常のメッセージに置き換えられる。  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text=""コンソール内の問題" メッセージ" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   "コンソール内の問題" メッセージ  
:::image-end:::  

サードパーティの Cookie の問題は、[**問題**] ツールで既定で非表示になっています。  新しい [**サードパーティの Cookie の問題を含める**] チェックボックスをオンにして、問題を表示します。  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="サードパーティの Cookie の問題チェックボックス" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   サードパーティの Cookie の問題チェックボックス  
:::image-end:::  

Chromium の問題: [1096481][CR1096481]、[1068116][CR1068116]、[1080589][CR1080589]  

### <a name="emulate-missing-local-fonts"></a>見つからないローカル フォントのエミュレート  

[[レンダリング ツール][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]] を開いて、新しい [**ローカル フォントを無効にする**] 機能を使用して `@font-face` 規則の見つからない `local()` ソースをエミュレートします。  

たとえば、お使いのデバイスに `Rubik` フォントがインストールされていて、`@font-face src` ルールによって `local()` フォントとして使用されている場合、Microsoft Edge は、お使いのデバイスのローカル フォント ファイルを使用します。  

[**ローカル フォントを無効にする**] が有効になっている場合、DevTools は `local()` フォントを無視し、それぞれのフォントをネットワークから取得します。  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="見つからないローカル フォントのエミュレート" lightbox="../../media/2020/08/disable-font.msft.png":::
   見つからないローカル フォントのエミュレート  
:::image-end:::  

次の例のように、開発中に同じフォントの異なる 2 つのコピーを使用する場合:  

*   デザイン ツールにローカル フォントを使用する。  
*   コードに Web フォントを使用する。  

[**ローカル フォントを無効にする**] を使用して、次の作業をより簡単に実行できるようにします。  

*   読み込みのパフォーマンスと Web フォントの最適化をデバッグし、計測する。  
*   CSS `@font-face` ルールの精度を検証する。  
*   デバイスにインストールされているローカル バージョンと Web フォントの違いを見つける。  

Chromium の問題: [#384968][CR384968]  

### <a name="emulate-inactive-users"></a>非アクティブなユーザーのエミュレート  

[アイドル検出 API][WebDevIdleDetection] によって、開発者は非アクティブなユーザーを検出し、アイドル状態の変更を反映することができます。  DevTools を使って、[**センサー**] ツールでユーザーの状態と画面の状態の両方に対してアイドル状態の変更をエミュレートできるようになりました。これにより、実際のアイドル状態が変更されるのを待つ必要がなくなります。  [**センサー**] ツールは [[ドロワー][DevtoolsCustomizeIndexDrawer]] から開くことができます。  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="非アクティブなユーザーのエミュレート" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   非アクティブなユーザーのエミュレート  
:::image-end:::  

Chromium の問題: [#1090802][CR1090802]  

### <a name="emulate-prefers-reduced-data"></a>prefers-reduced-data のエミュレート  

> [!NOTE]
> Microsoft Edge 86 で、この機能を有効にするには、[実験用 Web プラットフォームの機能] フラグに移動して `edge://flags#enable-experimental-web-platform-features` **オン** にします。  エミュレーション オプションは、フラグが有効になっている場合にのみ表示されます。  

[prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] メディア クエリは、データを最少化するユーザーのコンテンツ設定を検出します。  これが選択されている場合、ユーザーはより少ないデータを使用する代替のページ コンテンツを受け取ります。  

DevTools を使って `prefers-reduced-data` メディア クエリをエミュレートできるようになりました。  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="prefers-reduced-data のエミュレート" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   prefers-reduced-data のエミュレート  
:::image-end:::  

Chromium の問題: [#1096068][CR1096068]  

### <a name="support-for-new-javascript-features"></a>新しい JavaScript 機能のサポート  

DevTools では、次の JavaScript 言語機能がサポートされるようになりました。  

| JavaScript 言語機能 | 詳細 |  
|:--- |:--- |  
| [論理代入演算子][V8FeaturesLogicalAssignment] | DevTools では、コンソール ツールとソース ツールの新しい演算子 、演算子を使用した論理割 `&&=` `||=` `??=` **り** 当 **てがサポート** されます。  |  
| [数値区切り記号][V8FeaturesNumericSeparators]の整形出力 | DevTools は、Sources ツールで数値の区切り記号を適切に **印刷** します。  |  

Chromium の問題: [1086817][CR1086817]、[1080569][CR1080569]  

### <a name="lighthouse-62-in-the-lighthouse-panel"></a>Lighthouse パネルの Lighthouse 6.2  

ライト **ハウス ツール** は現在、ライトハウス 6.2 を実行しています。  変更の完全な一覧については、ライトハウスの [リリース ノートに移動します][GithubGooglechromeLighthouseV620]。  

Chromium の問題: [#772558][CR772558]  

### <a name="deprecation-of-other-origins-listing-in-the-service-workers-pane"></a>[サービス ワーカー] ウィンドウにおける他のオリジン一覧の廃止  

DevTools は、サービス ワーカー**** ウィンドウ**\(** Application tool > **Service workers** pane\) からのリンクを提供し、他の発生元からのサービス ワーカーの完全な一覧を表示します。  DevTools を開かなくてもリストにアクセスするには、に移動します `edge://service-worker-internals/?devtools` 。  

以前の DevTools には、[サービス**** ワーカー] ウィンドウの [アプリケーション ツール] ウィンドウの下に入>**が表示**されています。  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="他のオリジンへのリンク" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   他のオリジンへのリンク  
:::image-end:::  

Chromium の問題: [#807440][CR807440]  

### <a name="show-coverage-summary-for-filtered-items"></a>フィルター処理されたアイテムのカバレッジの概要を表示する  

DevTools は、カバレッジ情報を再計算し、概要を動的に表示するようになりました。  動的表示は、[[カバレッジ][DevtoolsCoverageIndex]] ツールでフィルターが適用されたときにトリガーされます。  以前、[**カバレッジ**] ツールでは、常にすべてのカバレッジ情報の概要が表示されていました。  

次の図のうちの最初の図で、初めは概要に `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` と表示されていますが、次の図のうちの 2 番目の図では CSS フィルターが適用され、概要に `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` と表示されています。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="カバレッジの概要" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         カバレッジの概要  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="フィルター処理されたアイテムのカバレッジの概要" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         フィルター処理されたアイテムのカバレッジの概要  
      :::image-end:::  
   :::column-end:::
:::row-end:::

Chromium の問題: [#1061385][CR1090802]  

### <a name="new-frame-details-view-in-application-panel"></a>[アプリケーション] パネルでの新しいフレームの詳細ビュー  

DevTools で、各フレームの詳細ビューが表示されるようになりました。  アクセスするには、アプリケーション ツールの [フレーム] **メニューでフレーム** を **選択** します。  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="[アプリケーション] パネルでのフレームの新しい詳細ビュー" lightbox="../../media/2020/08/frame-details.msft.png":::
   アプリケーション ツールのフレームの新しい**詳細ビュー**  
:::image-end:::  

Chromium の問題: [#1093247][CR1093247]  

#### <a name="frame-details-for-opened-windows"></a>開いているウィンドウのフレームの詳細  

開いているウィンドウとポップアップ ウィンドウがフレーム ツリーの下にも表示されるようになりました。  開いているウィンドウの詳細ビューには、セキュリティに関する追加情報が含まれます。  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="開いているウィンドウの新しいフレーム詳細ビュー" lightbox="../../media/2020/08/window-opener.msft.png":::
   開いているウィンドウの新しいフレーム詳細ビュー  
:::image-end:::  

Chromium の問題: [#1107766][CR1107766]  

#### <a name="security-and-isolation-information"></a>セキュリティと分離に関する情報  

セキュリティで保護されたコンテキスト、[Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep]、[Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] がフレーム詳細に表示されるようになりました。  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="セキュリティと分離に関する情報" lightbox="../../media/2020/08/coep-coop.msft.png":::
   セキュリティと分離に関する情報  
:::image-end:::  

今後、Microsoft Edge DevTools チームと Chrome DevTools チームは、フレーム詳細にさらに多くのセキュリティ情報を追加する予定です。  

Chromium の問題: [#1051466][CR1051466]  

### <a name="elements-and-network-panel-updates"></a>[要素] パネルと [ネットワーク] パネルの更新  

#### <a name="accessible-color-suggestion-in-the-styles-pane"></a>[スタイル] ウィンドウでのアクセシビリティに対応した色の候補  

DevTools では、コントラストの低い色のテキストに対して色の候補が表示されるようになりました。  

次の例で、`h1` のテキストにコントラストの低い色が設定されています。  これを修正するには、[**スタイル**] ウィンドウで `color` プロパティのカラー ピッカーを開きます。  [**コントラスト比**] セクションを展開すると、DevTools は AA と AAA の色の候補を提供します。  色を適用するには、推奨される色を選択します。  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="カラー ピッカーで AA と AAA の色の候補が提示される" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   カラー ピッカーで AA と AAA の色の候補が提示される  
:::image-end:::  

Chromium の問題: [#1093227][CR1093227]  

#### <a name="reinstate-properties-pane-in-the-elements-panel"></a>[要素] パネルに [プロパティ] ウィンドウを復元  

[**プロパティ**] ウィンドウが復元されました。  このウィンドウは [Microsoft Edge 84 で廃止されました][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。  Microsoft Edge DevTools チームと Chrome DevTools チームは、要素のプロパティ検査のための改善を計画しています。  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="[要素] パネルの [プロパティ] ウィンドウ" lightbox="../../media/2020/08/properties-pane.msft.png":::
   **[要素** ] ツールの **[プロパティ]** ウィンドウ  
:::image-end:::  

Chromium の問題:  <!--  [#1105205][CR1105205],  -->  [#1116085][CR1116085]  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="Human-readable `X-Client-Data` header values" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <a name="autocomplete-custom-fonts-in-the-styles-pane"></a>[スタイル] ウィンドウでのカスタム フォントのオートコンプリート  

[**スタイル**] ウィンドウで `font-family` プロパティを編集するときの CSS のオートコンプリート一覧に、インポートされたフォント フェイスが追加されるようになりました。  

たとえば、ローカル コンピューターにインストールされているカスタム フォントの場合は `monospace` 、CSS 完了リストに表示されます。  以前のバージョンの Microsoft Edge では、フォントは表示されません。

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="カスタム フォントのオートコンプリート" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   カスタム フォントのオートコンプリート  
:::image-end:::  

Chromium の問題: [#1106221] [CR1106221]  

#### <a name="consistently-display-resource-type-in-network-panel"></a>[ネットワーク] パネルでリソースの種類を一貫して表示する  

DevTools では、元のネットワーク要求と同じリソースの種類が一貫して表示され、リダイレクト (HTTP 状態コード 302) が発生すると [**種類**] 列の値に `/ Redirect` が追加されるようになりました。  

以前は、DevTools が種類を `Other` に変更する場合がありました。  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="リダイレクト時にリソースの種類を表示する" lightbox="../../media/2020/08/network-redirect.msft.png":::
   リダイレクト時にリソースの種類を表示する  
:::image-end:::  

Chromium の問題: [#997694][CR997694]  

#### <a name="clear-buttons-in-the-elements-and-network-tools"></a>要素とネットワーク ツールのボタンをクリアする  

次のテキスト ボックスに、[**クリア**] ボタンが表示されるようになりました。  

*   [スタイル] ウィンドウと [ネットワーク] ツール**の****フィルター**テキスト ボックス。  
*   要素ツールの DOM 検索テキスト **ボックス** 。  

[**クリア**] ボタンを選択して、入力されたテキストを削除します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="[要素] パネルの [クリア] ボタン" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         要素ツールのボタン **をクリア** する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="[ネットワーク] パネルの [クリア] ボタン" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         ネットワーク ツールの  **ボタンをクリア** する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium の問題: [#1067184][CR1067184]  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "[要素] パネルの [プロパティ] ウィンドウの廃止 - DevTools の新機能 (Microsoft Edge 84) | Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッドのデバッグ機能 - DevTools の新機能 (Microsoft Edge 85) | Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的機能を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaPanelIndex]: /microsoft-edge/devtools-guide-chromium/media-panel/index "メディアプレーヤー情報を表示してデバッグする | Microsoft Docs"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code の Windows 用キーボード ショートカット"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR384968]: https://crbug.com/384968 "local () フォントを無視するオプション | Chromium bugs"  
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR807440]: https://crbug.com/807440 "SW の数が多いと Chrome がロックされる | Chromium bugs"  
[CR997694]: https://crbug.com/997694 "[ネットワーク] パネルの "xhr" フィルターの下に 302 状態の XHR 要求が表示されない | Chromium bugs"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1054281]: https://crbug.com/1054281 "機能に関する要望: DevTools で折りたたみ式デバイスとデュアルスクリーン デバイスをエミュレートできるようにしてほしい | Chromium bugs"  
[CR1067184]: https://crbug.com/1067184 "機能に関する要望: ネットワークと要素の [フィルターのクリア] ボタン > スタイル フィルター入力 | Chromium bugs"  
[CR1068116]: https://crbug.com/1068116 "☂ [問題] パネルのリリース | Chromium bugs"  
[CR1080569]: https://crbug.com/1080569 "Acorn で論理代入演算子がサポートされていない | Chromium bugs"  
[CR1080589]: https://crbug.com/1080589 "サードパーティ/ファーストパーティによる問題を分類する | Chromium bugs"  
[CR1086817]: https://crbug.com/1086817 "Acorn で数値区切り記号がサポートされていない | Chromium bugs"  
[CR1090802]: https://crbug.com/1090802 "アイドル検出 API からのアイドル状態の変更をシミュレーションする | Chromium bugs"  
[CR1093227]: https://crbug.com/1093227 "DevTools: アクセシビリティに対応した最も近い色を提案する | Chromium bugs"  
[CR1093247]: https://crbug.com/1093247 "[アプリケーション] パネルにフレームに関する情報を表示する | Chromium bugs"  
[CR1094406]: https://crbug.com/1094406 "開発者は AT のためにソース オーダー ビューアーを希望しているhttps://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools: prefers-reduced-data メディア機能のエミュレートのサポート | Chromium bugs"  
[CR1096481]: https://crbug.com/1096481 "問題バナーの配置 |Chromium bugs"  
[CR1100253]: https://crbug.com/1100253 "[要素] のコンテキスト メニューでスクリーンショット ノードのショートカットを追加する | Chromium bugs"  
[CR1103316]: https://crbug.com/1103316 "要素の検索で最初の検索結果のノード (テキストの強調表示など) が解決しない | Chromium bugs"  
[CR1103854]: https://crbug.com/1103854 "開発者ツール X クライアントデータ値の難読化を解除する | Chromium bugs"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]: https://crbug.com/1106221 「[スタイル] パネルでフォントファミリーのオートコンプリートにインポートされたフォントを追加する | Chromium bugs」  
[CR1107766]: https://crbug.com/1107766 「フレーム ツリーで 'window.open()' によって生成されたフレームに関する情報を表示する | Chromium bugs」  
[CR1115011]: https://crbug.com/1115011 「コンソールから表をコピーするときに表の構造が保持されない | Chromium bugs」  
[CR1116085]: https://crbug.com/1116085 「DevTools プロパティ検査を元に戻してください | Chromium bugs」  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "prefers-reduced-data - メディア クエリ レベル 5 | W3C CSS ワーキング グループ エディター ドラフト"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v6.2.0 - GoogleChrome/lighthouse | GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "Protocol Buffers | Google Developers"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "論理代入 | V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数値区切り記号 | V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "COOP と COEP を使用して Web サイトを \"クロスオリジン分離\" する | web.dev"  
[WebDevIdleDetection]: https://web.dev/idle-detection "アイドル検出 API で非アクティブなユーザーを検出する | web.dev"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "合成されていないアニメーションを回避する | web.dev"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/08/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
