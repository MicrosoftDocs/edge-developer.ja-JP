---
description: CSS グリッドのデバッグ機能、ネットワーク コンソールを使った要求の編集と再生など。
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5bd013fae617e9759aa91949acccf936d85f7160
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514362"
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
# <a name="whats-new-in-devtools-microsoft-edge-85"></a>DevTools の新機能 (Microsoft Edge 85)  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、Microsoft コード拡張機能、その他の新機能を試Visual Studioお知らせをご覧ください。  開発者ツールの最新で最良の機能について最新情報を入手するには、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、[Twitter で Microsoft Edge DevTools チームをフォローしますます][EdgeDevToolsTwitterAccount]。  

### <a name="css-grid-debugging-features"></a>CSS グリッドのデバッグ機能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   試験的な機能  
:::image-end:::  

Microsoft Edge DevTools チームは、Chrome DevTools チームと Chromium コミュニティと連携して、新しい CSS グリッドのデバッグ機能を DevTools に追加しています。  現在、グリッド線の番号、グリッドのギャップ、拡張グリッド線をページ上にオーバーレイとして表示できるようになりました。  さらに、グリッド ツールのさらなる改善が間もなく提供されます。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS グリッドのデバッグ機能
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[新しい CSS グリッド デバッグ機能を有効にする] の横にある**チェック ボックスをオンにします**。  
> 
> サンプルを使用して実験を試す場合は [、CSS グリッド プランナーの例に移動します][CodepenRachelweilYzwBzKM]。  

Chromium の問題 [#1047356][CR1047356]  

### <a name="edit-and-replay-requests-with-the-network-console"></a>ネットワーク コンソールを使用して要求を編集および再生する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   試験的な機能  
:::image-end:::  

**ネットワーク コンソール**を使用して、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]の要求に対して**編集と再生**を使用できるようになりました。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="ネットワーク コンソールを使用して NetworkLog で要求を編集して再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   **ネットワーク コンソール**を使用して[NetworkLog][DevtoolsNetworkIndexLogActivity]で要求を編集して再生する  
:::image-end:::  

新しいパネルとして、[DevTools のドロワー][DevtoolsCustomizeIndexDrawer]に **[ネットワーク コンソール]** が開き、HTTP 要求の情報が自動的に入力されます。  サーバーから返される応答を表示するには、要求 \(必要な場合は\) を編集し、[送信] を **選択します**。  

また、**[ネットワーク コンソール]** を使用して、DevTools から直接 HTTP 要求を作成して送信することもできます。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="[ネットワーク コンソール] パネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   **[ネットワーク コンソール]** パネル  
:::image-end:::  

> [!TIP]
> [DevTools][DevtoolsCustomizeIndexDrawer]**ドロ**ワーの代わりにメインの \(top\) パネルにネットワーク コンソールを表示するには、パネル間で[ツールを移動するに移動します](#move-tools-between-panels)。  

> [!NOTE]
> 実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。  
> 
> ネットワーク ログ [を開き、][DevtoolsNetworkIndexLogActivity]コンテキスト メニュー \(右クリック\) を開き、[編集] と [再生] **を選択します**。  

Chromium の問題 [#1093687][CR1093687]  

### <a name="service-worker-respondwith-events-in-the-timing-tab"></a>[タイミング] タブのサービス ワーカーのrespondWith イベント  

ネットワーク **ツールの [** タイミング] **タブに** サービス ワーカー `respondWith` イベントが含まれる。  `respondWith`サービス ワーカー イベントは、サービス ワーカー `fetch` イベント ハンドラーの実行が開始される直前から、`respondWith` ハンドラーの `fetch` Promise が解決されるまでの期間を示します。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="[ネットワーク] パネルの [タイミング] タブ内の respondWith サービス ワーカー イベント" lightbox="../../media/2020/06/timing-tab.msft.png":::
   ネットワーク `respondWith` ツールの [タイミング]**タブ**のサービス ワーカー イベント****  
:::image-end:::  

[受信 **した応答] を** 展開して、応答からの追加情報 `fetch` `CacheStorageCacheName` を表示 `serviceWorkerResponseSource` します `ResponseTime` 。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="受信した応答を展開して、フェッチ応答からの追加情報を表示する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   [受信 **した応答] を** 展開して、応答からの追加情報を表示 `fetch` する  
:::image-end:::  

Chromium の問題 [#1066579][CR1066579]  

### <a name="webhint-feedback-in-the-issues-panel"></a>[問題] パネル内の webhint のフィードバック  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   試験的な機能  
:::image-end:::  

[webhint][WebhintMain] は、アクセシビリティ、ブラウザ間の互換性、セキュリティ、パフォーマンス、PWA、および Web サイトの他の一般的な Web 開発の問題に関するリアルタイムのフィードバックを提供するオープン ソース ツールです。  [問題] パネルで webhint フィードバック [を確認][DevtoolsIssues] するには。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   [問題] パネル内の webhint のフィードバック  
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[Webhint を有効にする] の横にあるチェック ボックス**をオンにします**。  
> 
> [問題 [] パネルを開][DevtoolsIssues] き、webhint からのフィードバックを表示します。  

Chromium の問題 [#1070378][CR1070378]  

### <a name="move-tools-between-panels"></a>パネル間でツールを移動する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的な機能":::
   試験的な機能  
:::image-end:::  

通常、**要素**や**ネットワーク**などのツールは、DevTools のメイン (上部) パネルでのみ開くことができます。  同様に、**3D ビュー**や**問題**などのツールは、DevTools のドロワー (下部) パネルでのみ開くことができます。  現在、上と下のパネル間でツールを移動して、DevTools のレイアウトをカスタマイズできるようになりました。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間でツールを移動する" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   パネル間でツールを移動する  
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOn]を有効にする] に移動し、[パネル間でタブを移動するサポートを有効にする] の横にある**チェック ボックスをオンにします**。  

Chromium の問題 [#897944][CR897944]  

### <a name="improved-initiator-tooltip-in-the-network-panel"></a>[ネットワーク] パネルでのイニシエーターのヒントの改善  

Microsoft Edge 83 および 84 では、[イニシエーター] 列にヒントが表示されます。これにより、[ネットワーク ログ][DevtoolsNetworkIndexLogActivity]には、水平スクロールバーが表示されます。  ツールヒントで水平方向にスクロールすることで、要求を開始した呼び出し履歴のみを表示できたのです。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 のイニシエーターのヒント  
:::image-end:::  

Microsoft Edge 85 から、水平方向にスクロールすることなく、イニシエーター呼び出し履歴をツールヒントに表示できます。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 のイニシエーターのヒント
:::image-end:::  

Chromium の問題 [#1069404][CR1069404]  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、オープン ソースの Chromium プロジェクトに寄与した Microsoft Edge 85 で利用できるその他の機能について説明します。  

### <a name="style-editing-for-css-in-js-frameworks"></a>CSS-in-JS フレームワークのスタイルの編集  

**[スタイル]** ウィンドウで、[CSS オブジェクトモデル (CSSOM)][CsswgDraftsCssom] API を使って作成されたスタイルの編集がより適切にサポートされるようになりました。  多くの CSS-in-JS フレームワークとライブラリは、内部で CSSOM API を使ってスタイルを構築します。  

現在、[Constructable Stylesheets][WicgConstructStylesheet] を使って、JavaScript で追加されたスタイルを編集できるようになりました。  Constructable Stylesheets は、[Shadow DOM][MdnShadowDom]を使用するときに、再利用可能なスタイルを作成して配布するための新しい方法です。  

たとえば、`CSSStyleSheet` (CSSOM API) で追加された `h1` スタイルは、以前は編集できませんでした。  スタイルは、[スタイル] パネルで **編集可能** になります。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet で追加された h1 スタイルの background プロパティをピンクからライトブルーに変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   `CSSStyleSheet` で追加された `h1` スタイルの `background` プロパティを `pink` から `lightblue` に変更します。
:::image-end:::  

この機能は、[CSS-in-JS を使用するサンプル][CodepenZoherghadyaliAbdgrpz]で試すことができます。

Chromium の問題 [#946975][CR946975]  

### <a name="lighthouse-6-in-the-lighthouse-panel"></a>[Lighthouse] パネルの Lighthouse 6  

**[Lighthouse]** パネルは、現在 Lighthouse 6 を実行しています。  すべての変更の完全な一覧については [、v6.0.0][GithubGoogleChromeLighthouse600]リリース ノートに移動します。  

Lighthouse 6.0 では、レポートに 3 つの新しい指標が導入されています。最大コンテンツのペイント (LCP)、累積レイアウト シフト (CLS)、および合計ブロッキング時間 (TBT) です。  

また、パフォーマンス スコアの計算式も再重み付けされ、ユーザーの読み込み操作がより適切に反映されるようになりました。  

Chromium の問題 [#772558][CR772558]  

#### <a name="first-meaningful-paint-deprecation"></a>First Meaningful Paint の廃止  

Lighthouse 6.0 では、最初の意味のあるペイント (FMP) が廃止されました。  FMP は、**[パフォーマンス]** パネルからも削除されています。  **最大コンテンツのペイント**が、推奨される FMP の代替機能です。  <!--For an explanation of why it was deprecated, navigate to [First Meaningful Paint][WebDevFirstMeaningfulPaint].  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium の問題 [#1096008][CR1096008]  

### <a name="support-for-new-javascript-features"></a>新しい JavaScript 機能のサポート  

DevTools では、最新の JavaScript 言語機能の一部がより適切にサポートされるようになりました。  

:::row:::
   :::column span="1":::
      [optional chaining][V8DevOptionalChaining] 構文のオートコンプリート  
   :::column-end:::
   :::column span="2":::
      **コンソール**内のプロパティのオートコンプリート機能により、optional chaining 構文がサポートされるようになりました。たとえば、`name.` と `name[` に加えて、`name?.` も使えます。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [プライベート フィールド][V8DevClassFieldsPrivate]の構文の強調表示  
   :::column-end:::
   :::column span="2":::
      プライベート クラスのフィールドが、**[ソース]** パネルで適切に強調表示され、整形出力されるようになりました。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [Nullish 合体演算子][V8DevNullishCoalescing]の構文の強調表示
   :::column-end:::
   :::column span="2":::
      **[ソース]** パネルで nullish 合体演算子が整形出力されるようになりました。  
   :::column-end:::
:::row-end:::  

Chromium の問題 [#1073903][CR1073903]、 [#1083214][CR1083214]、 [#1083797][CR1083797]  

### <a name="new-app-shortcut-warnings-in-the-manifest-pane"></a>[マニフェスト] ウィンドウでの新しいアプリのショートカットの警告  

**アプリのショートカット** を使用すると、Web アプリ内で一般的または推奨されるタスクをすばやく開始できます。  

<!--todo: add App shortcuts when section is live  -->  

**[マニフェスト]** ウィンドウには、次の条件の警告が表示されるようになりました。  

* アプリのショートカット アイコンが 96 x 96 ピクセルより小さい  
* アプリのショートカット アイコンとマニフェスト アイコンが四角形でない (アイコンが無視されているため)  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   アプリのショートカットの警告  
:::image-end:::  

Chromium の問題 [#955497][CR955497]  

### <a name="consistent-display-of-the-computed-pane"></a>[計算済み] ウィンドウの一貫性のある表示  

[ **要素] ツールの** [計算] **ウィンドウ** が、すべてのビューポート サイズにわたって一貫してウィンドウとして表示されます。  以前は、DevTools ビューポートの幅が狭い場合、**[計算済み]** ウィンドウは、**[スタイル]** ウィンドウ内にマージされました。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="DevTools の幅が狭い場合でも、[計算済み] ウィンドウは個別のウィンドウとして表示されます" lightbox="../../media/2020/06/computed-pane.msft.png":::
   DevTools の幅が狭い場合でも、**[計算済み]** ウィンドウは個別のウィンドウとして常に表示されます。
:::image-end:::  

Chromium の問題 [#1073899][CR1073899]  

### <a name="bytecode-offsets-for-webassembly-files"></a>WebAssembly ファイルのバイトコード オフセット  

DevTools は、Wasm 逆アセンブルの行番号を表示するためにバイトコード オフセットを使用するようになりました。  
行番号によって、バイナリデータを見ていることが明確になり、Wasm ランタイムが場所を参照する方法に一貫性が保たれます。  

Chromium の問題 [#1071432][CR1071432]  

### <a name="line-wise-copy-and-cut-in-sources-panel"></a>[ソース] パネルでの行ごとのコピーと切り取り  

[ソース パネル エディター][DevtoolsSourcesEditCssJavascript]で選択なしでコピーまたは切り取りを実行すると、現在のコンテンツの行がコピーまたは切り取りられます。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="カーソルが 5 行目の最後にある状態で、DevTools の pen.js から行全体をコピーして、Visual Studio Code に貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   カーソルが 5 行目の最後にある状態で、DevTools の **pen.js** から行全体をコピーして、[Visual Studio Code][VisualStudioCode] に貼り付けます。
:::image-end:::  

Chromium の問題 [#800028][CR800028]

### <a name="console-settings-updates"></a>コンソールの設定の更新  

#### <a name="ungroup-same-console-messages"></a>同じコンソールのメッセージをグループ解除する  

コンソールの設定の **[類似のグループ化]** 切り替えが、重複するメッセージに適用されるようになりました。  以前は単に類似のメッセージに適用されていました。  

たとえば、以前は、**[類似のグループ化]** がオフになっている場合でも、`hello` メッセージはグループ解除されませんでした。  現在、`hello` メッセージはグループ解除されます。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="[類似のグループ化] がオフの場合、hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   **[類似のグループ化]** がオフの場合、`hello` メッセージはグループ解除されます。
:::image-end:::  

この機能は、[コンソールに重複したメッセージを送信するサンプル][CodepenZoherghadyaliZyrjgdJ]で試すことができます。  

Chromium の問題 [#1082963][CR1082963]  

### <a name="persisting-selected-context-only-settings"></a>選択されたコンテキストのみの設定を保持する  

コンソールの設定で **[選択されたコンテキストのみ]** の設定が保持されるようになりました。  以前は、DevTools を閉じてもう一度開くたびに、設定はリセットされました。  この変更により、設定の動作が他のコンソールの設定オプションと一致するようになります。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="[選択されたコンテキストのみ] の設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   **[選択されたコンテキストのみ]** の設定  
:::image-end:::  

Chromium の問題 [#1055875][CR1055875]  

### <a name="performance-panel-updates"></a>[パフォーマンス] パネルの更新  

#### <a name="javascript-compilation-cache-information-in-performance-tool"></a>パフォーマンス ツールの JavaScript コンパイル**キャッシュ情報**  

[JavaScript のコンパイル キャッシュ情報][V8DevCodeCaching] は、パフォーマンス ツールの **[概要** ] パネルに常に **表示** されます。  以前は、コード キャッシュが行われなかった場合、DevTools でコード キャッシュに関連するものは表示されませんでした。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript コンパイルキャッシュ情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript コンパイルキャッシュ情報  
:::image-end:::  

Chromium の問題 [#912581][CR912581]  

#### <a name="navigation-timing-alignment-in-the-performance-panel"></a>[パフォーマンス] パネルでの移動のタイミングの調整  

**[パフォーマンス]** パネルでは、記録が開始された時間に基づいてルーラーに時間が表示されていました。  現在、タイミングはユーザーが移動する記録に変更され、移動に関連するルーラー時間が表示されるようになりました。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="パフォーマンス ツールでナビゲーションのタイミングを調整する" lightbox="../../media/2020/06/nav-timing.msft.png":::
   パフォーマンス ツールでナビゲーションのタイミング **を調整** する  
:::image-end:::  

`DOMContentLoaded`、First Paint (最初のペイント)、First Contentful Paint (最初のコンテンツのペイント)、最大コンテンツのペイント (Largest Contentful Paint) の各イベントの時間は、移動の開始からの相対的な時間に更新されます。つまり、タイミングは、`PerformanceObserver` によって報告されるタイミングと一致します。  

Chromium の問題 [#974550][CR974550]  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a>ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコン  

**[ソース]** パネルには、ブレークポイント、条件付きブレークポイント、およびログポイントの新しいデザインが用意されています。  ブレークポイントは、[Visual Studio Code][VisualStudioCode] と [Visual Studio][VisualStudio]と同様に、赤い円で表されます。  条件付きブレークポイントとログポイントを区別するためにアイコンが追加されています。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   ブレークポイント  
:::image-end:::  

Chromium の問題 [#1041830][CR1041830]  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する | Microsoft Docs"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools のカスタマイズ | Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的な機能を有効にする - 試験的な機能 | Microsoft Docs"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題を見つけて解決するツール | Microsoft Docs"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript を編集する - [ソース] パネルの概要 | Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティをログに記録する - Microsoft Edge DevTools でネットワーク アクティビティを検査する | Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS-in-JS フレームワークのスタイルの編集 | CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージをコンソールに送信する | CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッドプランナーの例 | CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する | Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome の更新後に、開発者ツール エディターの重複した行のショートカットが機能しない | Chromium のバグ"  
[CR912581]: https://crbug.com/912581 "V8 によってコードがキャッシュされたスクリプトが DevTools/about: tracing に公開される | Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools のスタイル サイドバーが Constructable Stylesheets で機能しない | Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWA のアプリ アイコン ショートカット メニュー | Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "[パフォーマンス] パネルと performanceObserver 間の指標の不一致 | Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "ブレークポイントの色を改善する | Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールを終了してもう一度開いたとき、コンソールの設定で指定した [選択したコンテキストのみ] の値が保持されない | Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools: [ネットワーク] パネルで要求ごとに ServiceWorkers フェッチ タイムラインを表示する | Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 開発者のエクスペリエンス | Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: 構文の強調表示がプライベート フィールドで使用できない | Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "コンソールの類似メッセージのグループ化の動作を無効にできない | Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "acorn で optional chaining がサポートされない | Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "nullish 合体演算子が整形出力されない | Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除 | Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/フレキシブル ボックス/テーブル ツール | Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "DevTools に webhint を統合する | Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "DevTools ウィジェットのポップアップがすべて狭すぎる | Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能な DevTools パネル | Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - Microsoft Docs/Edge Developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "Shadow DOM を使用する | MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge プレビュー チャネル"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"
[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio Code"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクトモデル (CSSOM) | W3C CSS ワーキング グループ エディター ドラフト"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベート クラス フィールド - パブリック クラスとプライベート クラスのフィールド | V8.Dev"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript 開発者向けのコード キャッシュ | V8.Dev"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合体 | V8.Dev"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "Optional chaining | V8.Dev"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "Constructable Stylesheet オブジェクト | Web Incubator CG"

<!--[WebDevLighthouseWhatsNew60]: https://web.dev/lighthouse-whats-new-6.0 "What's New in Lighthouse 6.0 | Web.Dev"  -->  
<!--[WebDevVitalsCoreWeb]: https://web.dev/vitals#core-web-vitals "Core Web Vitals - Web Vitals | Web.Dev"  -->  
<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebFundamentalComponentsShadowdom]: /web/fundamentals/web-components/shadowdom  -->  
<!--[WebDevLcp]: https://web.dev/lcp "Largest Contentful Paint (LCP) | Web.Dev"  -->  
<!--[WebDevFirstMeaningfulPaint]: https://web.dev/first-meaningful-paint "First Meaningful Paint | Web.Dev"  -->  
<!--[WhatsNew201902ConstructableStylesheets]: ../../2019/02/constructable-stylesheets.md "Constructable Stylesheets: seamless reusable styles | Microsoft Docs"  -->  

[TheWebWeWant]: https://webwewant.fyi/ "必要とされる Web"  

> [!NOTE]
> このページの一部は、[Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更であり、「[Creative Commons Attribution 4.0 International License][CCA4IL]」に記載されている条項に従って使用されます。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-85)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
