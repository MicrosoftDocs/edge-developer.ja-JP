---
description: CSS grid のデバッグ機能、ネットワークコンソールを使った要求の編集と再生など。
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 96ad9a4f21c36135013033fa4de31281fe6c4e83
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993612"
---
# DevTools の新機能 (Microsoft Edge 85)  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。  このお知らせを参照して、DevTools、VS コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter の Microsoft edge devtools チームに従い][EdgeDevToolsTwitterAccount]ます。  

### CSS grid のデバッグ機能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   実験的機能  
:::image-end:::  

Microsoft Edge DevTools チームは、Chrome DevTools チームと Chromium コミュニティと連携して、新しい CSS grid のデバッグ機能を DevTools に追加します。  これで、グリッド線の番号、グリッドのギャップ、拡張グリッド線をページ内のオーバーレイとして表示できるようになりました。  さらに、グリッドツールの機能がさらに向上しました。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS grid のデバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS grid のデバッグ機能
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOn] 有効にする」を参照し、[ **新しい CSS グリッドのデバッグ機能を有効**にする] の横のチェックボックスをオンにします。  
> 
> サンプルを使って実験を試すには、「 [CSS グリッドプランナーの例][CodepenRachelweilYzwBzKM]」を参照してください。  

Chromium の問題 [#1047356][CR1047356]  

### ネットワークコンソールを使用して要求を編集および再生する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   実験的機能  
:::image-end:::  

ネットワーク**コンソール**を使用して、[ネットワークログ][DevtoolsNetworkIndexLogActivity]の要求に対して**編集と再生**を使用できるようになりました。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="ネットワークコンソールを使用して NetworkLog で要求を編集して再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   **ネットワークコンソール**を使用して[networklog][DevtoolsNetworkIndexLogActivity]で要求を編集して再生する  
:::image-end:::  

新しいパネルとして、[ [Devtools] ドロアー][DevtoolsCustomizeIndexDrawer]に**ネットワークコンソール**が開き、HTTP 要求の情報が自動的に入力されます。  サーバーから返された応答を確認するには、要求を編集し (必要な場合)、[ **送信**] を選択します。  

また、 **ネットワークコンソール** を使用して、devtools から直接 HTTP 要求を作成して送信することもできます。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="ネットワークコンソールパネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   **ネットワークコンソール**パネル  
:::image-end:::  

> [!TIP]
> [ [Devtools] ドロアー][DevtoolsCustomizeIndexDrawer]の代わりに、メインの \ (上部 \) パネルで**ネットワークコンソール**を表示するには、「[パネル間でのツールの移動](#move-tools-between-panels)」を参照してください。  

> [!NOTE]
> 実験を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOn] 有効にする」を参照し、[ **ネットワーク本体を有効**にする] の横のチェックボックスをオンにします。  
> 
> [ネットワークログ][DevtoolsNetworkIndexLogActivity]を開き、コンテキストメニューを開き (\ を右クリック)、[**編集と再生**] を選択します。  

Chromium の問題 [#1093687][CR1093687]  

### [タイミング] タブのイベントを使用したサービスワーカーの返信  

[**ネットワーク**] パネルの [**タイミング**] タブに、サービスワーカーイベントが表示されるようになりました `respondWith` 。  `respondWith`サービスワーカーイベントは、 `fetch` `respondWith` ハンドラーの promise が決済された時点までのサービスワーカーイベントハンドラーの開始時刻からの時間を示し `fetch` ます。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="[ネットワーク] パネルの [タイミング] タブにある [サービスワーカーイベント]" lightbox="../../media/2020/06/timing-tab.msft.png":::
   [ `respondWith` **ネットワーク**] パネルの [**タイミング**] タブのサービスワーカーイベント  
:::image-end:::  

[ **返信の受信** ] を展開して、、、、などの返信の追加情報を表示し `fetch` `CacheStorageCacheName` `serviceWorkerResponseSource` `ResponseTime` ます。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="[返信の受信] を展開して、フェッチ応答から追加情報を確認する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   [**返信の受信**] を展開して、応答から追加情報を確認する `fetch`  
:::image-end:::  

Chromium の問題 [#1066579][CR1066579]  

### [問題] パネルでの webhint のフィードバック  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   実験的機能  
:::image-end:::  

[webhint][WebhintMain] は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。  これで、[ [問題][DevtoolsIssues] ] パネルに webhint のフィードバックが表示されるようになります。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   [問題] パネルでの webhint のフィードバック  
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOn] を有効にする」を参照し、[ **Webhint を有効**にする] の横のチェックボックスをオンにします。  
> 
> [ [問題][DevtoolsIssues] ] パネルを開いて、web ヒントからのフィードバックを表示します。  

Chromium の問題 [#1070378][CR1070378]  

### パネル間の移動ツール  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実験的機能":::
   実験的機能  
:::image-end:::  

通常、 **要素** や **ネットワーク** などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。  同様に、 **3D ビュー** や **問題** などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。  これで、[上] と [下] パネルの間でツールを移動して、DevTools のレイアウトをカスタマイズできるようになりました。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   パネル間でタブを移動する  
:::image-end:::  

> [!NOTE]
> 実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOn] を有効にする」のチェックボックスをオンにし、[ **サポートを有効**にする] の横にあるチェックボックスをオンにします。  

Chromium の問題 [#897944][CR897944]  

### [ネットワーク] パネルでのイニシエーターのヒントの改善  

Microsoft Edge 83 および84では、[イニシエーター] 列のツールチップが表示されます。これにより、 [ネットワークログ][DevtoolsNetworkIndexLogActivity] には、水平スクロールバーが表示されます。  要求を開始したコールスタックを表示できるのは、ヒントを水平方向にスクロールすることだけです。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 のイニシエーターのヒント  
:::image-end:::  

Microsoft Edge 85 以降では、水平方向にスクロールしなくても、ツールヒントでイニシエーターのコールスタックを確認できるようになりました。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシエーターのヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 のイニシエーターのヒント
:::image-end:::  

Chromium の問題 [#1069404][CR1069404]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 85 で利用可能なその他の機能を示します。  

### CSS イン JS フレームワークのスタイルの編集  

[ **スタイル** ] ウィンドウで、 [CSS オブジェクトモデル (cssom)][CsswgDraftsCssom] api を使って作成されたスタイルの編集がさらにサポートされるようになりました。  CSS 内の多くのフレームワークとライブラリでは、内部の CSSOM Api を使ってスタイルを構築しています。  

構築した [表スタイルシート][WicgConstructStylesheet]を使って、JavaScript で追加したスタイルを編集できるようになりました。  構築された表スタイルシートは、 [シャドウ DOM][MdnShadowDom]を使用するときに、再利用可能なスタイルを作成して配布するための新しい方法です。  

たとえば、 `h1` `CSSStyleSheet` \ (Cssom api \) で追加されたスタイルは、以前は編集できませんでした。  スタイルは、[ **スタイル** ] ウィンドウで編集できるようになりました。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet によって追加された h1 スタイルの background プロパティをピンクからライトブルーに変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   `background` `h1` From からに追加されたスタイルのプロパティを変更 `CSSStyleSheet` `pink` `lightblue` します。
:::image-end:::  

この機能を試すには、 [CSS IN JS を使用するサンプル][CodepenZoherghadyaliAbdgrpz]が含まれています。

Chromium の問題 [#946975][CR946975]  

### Lighthouse パネルの Lighthouse 6  

**Lighthouse** panel は、現在 Lighthouse 6 を実行しています。  すべての変更の一覧については、「 [v 6.0.0 のリリースノート][GithubGoogleChromeLighthouse600]」を参照してください。  

Lighthouse 6.0 は、レポートに最大3つの新しいメトリックを導入します。これは、最大 Contentful 塗料 (LCP \)、累積レイアウトシフト \ (CLS \)、ブロック時間の合計 (TBT \) です。  

また、パフォーマンススコアの計算式も再重み付けされ、ユーザーの読み込み操作がより適切に反映されるようになりました。  

Chromium の問題 [#772558][CR772558]  

#### 最初の有意義な塗料の廃止  

Lighthouse 6.0 では、最初の有意義な塗料 \ (FMP \) は廃止されました。  FMP は、 **パフォーマンス** パネルからも削除されています。  **最大のコンテンツ** は、FMP に推奨される代替機能です。  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium の問題 [#1096008][CR1096008]  

### 新しい JavaScript 機能のサポート  

DevTools では、最新の JavaScript 言語機能の一部がサポートされるようになりました。  

:::row:::
   :::column span="1":::
      [オプションのチェーン][V8DevOptionalChaining] 構文のオートコンプリート  
   :::column-end:::
   :::column span="2":::
      **コンソール**内のプロパティのオートコンプリート機能により、オプションのチェーン構文がサポートされるようになりました。たとえば、との組み合わせ `name?.` でも動作するようになりました `name.` `name[` 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [プライベートフィールド][V8DevClassFieldsPrivate]の構文強調表示  
   :::column-end:::
   :::column span="2":::
      プライベートクラスのフィールドが適切に強調表示されるようになり、[ **ソース** ] パネルできれいに印刷されるようになりました。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      [Nullish 合体演算子][V8DevNullishCoalescing]の構文の強調表示
   :::column-end:::
   :::column span="2":::
      DevTools では、[ **ソース** ] パネルで nullish 合体演算子が適切に印刷されるようになりました。  
   :::column-end:::
:::row-end:::  

Chromium の問題 [#1073903][CR1073903]、 [#1083214][CR1083214]、 [#1083797][CR1083797]  

### [マニフェスト] ウィンドウでの新しいアプリのショートカットの警告  

**アプリのショートカット** を使用すると、web アプリ内で一般的または推奨されるタスクをすばやく開始できます。  

<!--todo: add App shortcuts when section is live  -->  

**マニフェスト**ウィンドウには、次の条件の警告が表示されるようになりました。  

* アプリのショートカットアイコンが 96 x 96 ピクセルより小さい  
* アプリのショートカットアイコンとマニフェストアイコンは、(アイコンが無視されているため) 四角形ではありません。  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   アプリのショートカットの警告  
:::image-end:::  

Chromium の問題 [#955497][CR955497]  

### 計算されたウィンドウの一貫性のある表示  

[**要素**] パネルの**計算**ウィンドウは、すべてのビューポートサイズのウィンドウとして一貫して表示されるようになりました。  以前は、DevTools ビューポートの幅が狭い場合に、[**スタイル**] ウィンドウ内にマージされた**計算**ウィンドウ。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="DevTools が限定されている場合でも、計算ウィンドウは個別のウィンドウとして表示されます" lightbox="../../media/2020/06/computed-pane.msft.png":::
   この **ウィンドウは、** devtools が限定されている場合でも、個別のウィンドウとして常に表示されます。
:::image-end:::  

Chromium の問題 [#1073899][CR1073899]  

### Webasfiles のバイトコードオフセット  

DevTools では、Wasm 逆アセンブルの行番号を表示するためにバイトコードオフセットを使用できるようになりました。  
行番号によって、バイナリデータを見ているかどうかがわかりやすくなり、Wasm ランタイムが位置情報を参照する方法に一貫性が保たれます。  

Chromium の問題 [#1071432][CR1071432]  

### [ソース] パネルでの線ごとのコピーと切り取り  

[ソースパネルエディター][DevtoolsSourcesEditCssJavascript]で選択なしでコピーまたは切り取りを実行すると、devtools で現在のコンテンツの行がコピーまたは切り取りられます。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="カーソルが行5の最後にある状態で、DevTools の pen.js から行全体をコピーして、VS コードに貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   カーソルが行5の最後にある状態で、DevTools の **pen.js** から行全体をコピーして、 [VS コード][VSCode]に貼り付けます。
:::image-end:::  

Chromium の問題 [#800028][CR800028]

### 本体の設定の更新  

#### 同じ本体のメッセージをグループ解除する  

[コンソール設定] の [ **同様のグループ]** が、重複するメッセージに適用されるようになりました。  以前は同様のメッセージに適用されました。  

たとえば、前の例で `hello` は、グループの同様のチェックマークがオフになっているにもかかわらず、DevTools がメッセージのグループ **化** を解除しました。  これで、 `hello` メッセージはグループ解除されます。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="[グループ類似] がオフの場合、hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   [ **グループ類似]** がオフの場合、 `hello` メッセージはグループ解除されます。
:::image-end:::  

この機能については、 [コンソールに重複したメッセージを送信するサンプル][CodepenZoherghadyaliZyrjgdJ]を試してみてください。  

Chromium の問題 [#1082963][CR1082963]  

### 選択されたコンテキストのみの設定を保持する  

コンソール設定で **選択されたコンテキストのみ** の設定が保持されるようになりました。  以前は、DevTools を閉じてもう一度開くたびに、設定はリセットされました。  この変更により、設定動作は、他の本体の設定オプションと一貫性が保たれます。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="選択されたコンテキストのみの設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   **選択されたコンテキストのみ** の設定  
:::image-end:::  

Chromium の問題 [#1055875][CR1055875]  

### パフォーマンスパネルの更新  

#### パフォーマンスパネルの JavaScript コンパイルキャッシュ情報  

[JavaScript コンパイルキャッシュ情報][V8DevCodeCaching] が、常に [パフォーマンス] パネルの [概要] タブに表示されるようになりました。  以前は、コードキャッシュが行われなかった場合、DevTools でコードキャッシュに関連するものは表示されませんでした。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript コンパイルキャッシュ情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript コンパイルキャッシュ情報  
:::image-end:::  

Chromium の問題 [#912581][CR912581]  

#### パフォーマンスパネルでのナビゲーションのタイミングの配置  

[ **パフォーマンス** ] パネルでは、録画が開始されたタイミングに基づいてルーラーに時間が表示されます。  これで、ユーザーが移動する記録のタイミングが変更されました。これで、DevTools でナビゲーションに対するルーラーの時間が表示されるようになりました。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="[パフォーマンス] パネルでのナビゲーションのタイミングの調整" lightbox="../../media/2020/06/nav-timing.msft.png":::
   [ **パフォーマンス** ] パネルでのナビゲーションのタイミングの調整  
:::image-end:::  

`DOMContentLoaded`最初の塗料、First Contentful 塗りつぶしの塗料、および最大の contentful ような塗料イベントは、ナビゲーションの開始からの相対的な時間に更新されます。つまり、タイミングは、によって報告されるタイミングと一致し `PerformanceObserver` ます。  

Chromium の問題 [#974550][CR974550]  

### ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコン  

[ **ソース** ] パネルには、ブレークポイント、条件付きブレークポイント、および logpoints の新しいデザインが用意されています。  ブレークポイントは、 [VS コード][VSCode] と [Visual Studio][VS]と同様に、赤い円で表されます。  条件付きブレークポイントと logpoints を区別するためにアイコンが追加されます。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   ブレークポイント  
:::image-end:::  

Chromium の問題 [#1041830][CR1041830]  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript の編集-ソースパネルの概要 |Microsoft ドキュメント"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワークアクティビティのログ-Microsoft Edge DevTools でネットワークアクティビティを検査するMicrosoft ドキュメント"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS イン JS フレームワークのスタイルの編集 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージをコンソールに送信 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッドプランナーの例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome の更新後に、開発者ツールエディターの重複した行のショートカットが機能しないChromium のバグ"  
[CR912581]: https://crbug.com/912581 "V8 によってコードがキャッシュされていたスクリプトを、DevTools/about: tracing | に公開します。Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools のスタイルサイドバーは、構築されたスタイルシートに対応していません。Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWAs のアプリアイコンショートカットメニュー |Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "パフォーマンスパネルとパフォーマンスオブザーバーの間のメトリックの不一致 |Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "ブレークポイントの色を改善する |Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールを終了してもう一度開くと、選択したコンテキストのみのコンソール設定の値が保持されません。Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools: ServiceWorkers の表示 [ネットワークパネル] での要求ごとのタイムラインの取得 |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 開発者エクスペリエンス |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[計算されたスタイル] タブが応答モードで表示されなくなります。Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: 構文の強調表示は、プライベートフィールドでは使用できません。Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "本体のグループ類似メッセージの動作を無効にすることはできません |Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "acorn はオプションのチェーンをサポートしていません |Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "Nullish 合体については、非常に印刷されませんでした |Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除 |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツーリング |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "代理ネットワーク要求を作成および再生するためのツールを作成する |Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "DevTools への web ヒントの統合 |Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "[開発ツール] ウィジェットのポップアップがすべて狭すぎます。Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能になった devtool パネル |Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v 6.0.0-GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "Shadow DOM を使用する |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge Preview チャネル"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio コード"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクトモデル (CSSOM) |W3C CSS ワーキンググループエディターの下書き"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベートクラスフィールド-パブリックとプライベートクラスのフィールド |V8.者"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript 開発者向けのコードキャッシュ |V8.者"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合体 |V8.者"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "オプションのチェーン |V8.者"  

[WebhintMain]: https://webhint.io "web ヒント"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "構築方法の表スタイルオブジェクト |Web Incubator CG"

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

[TheWebWeWant]: https://webwewant.fyi/ "必要な Web"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/06/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
