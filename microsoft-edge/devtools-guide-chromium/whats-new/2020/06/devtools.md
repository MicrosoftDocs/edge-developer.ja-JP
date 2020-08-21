---
title: DevTools の新機能 (Microsoft Edge 85)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f569414a95336278c93b1bbafd57153ca902df12
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942191"
---
# DevTools の新機能 (Microsoft Edge 85)  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。  DevTools、VS コード拡張機能などで新機能を試すには、お知らせを参照してください。  開発者ツールの最新機能と最大の機能をすべて最新の状態に保つには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルをダウンロードし [、Twitter で Microsoft Edge DevTools チームに従います][EdgeDevToolsTwitterAccount]。  

### CSS グリッド デバッグ機能  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   実用的な機能  
:::image-end:::  

Microsoft Edge DevTools チームは Chrome DevTools チームと Chromium コミュニティと共同作業を行い、DevTools に新しい CSS グリッドデッド機能を追加します。  グリッド線の番号、グリッド間、および拡張された目盛線をオンページ上の重なりとして表示できるようになりました。  また、グリッド ツールの機能の改善が、もちらつもなくリリース予定です。  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS グリッド デバッグ機能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   CSS グリッド デバッグ機能
:::image-end:::  

> [!NOTE]
> 実用機能を有効にするには、「 [環境内][DevtoolsExperimentalFeaturesTurnOn] の機能を有効にする」を参照し、[新しい CSS グリッドのデバッグ機能を有効にする] の横にあるチェックボックス **をオンにします**。  
> 
> サンプルの試すには [、CSS グリッド計画ツールの例を参照してください][CodepenRachelweilYzwBzKM]。  

Chromium の [問題#1047356][CR1047356]  

### ネットワーク本体で要求を編集および再生する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   実用的な機能  
:::image-end:::  

ネットワーク本体を使用して、**ネットワーク**ログ内の要求に対[Network Log][DevtoolsNetworkIndexLogActivity]して編集と再生を**使用できるようになりました**。  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="NetworkConsole で NetworkLog で要求を編集および再生する" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   **NetworkConsole**で[NetworkLog で要求を][DevtoolsNetworkIndexLogActivity]編集および再生する  
:::image-end:::  

新しいパネル **(Network Console** は [DevTools Drawer で開][DevtoolsCustomizeIndexDrawer] き、HTTP 要求の情報が自動的に入力されます。  サーバーから返された応答を表示するには、要求 \(必要な場合) を編集し、[送信] を選 **びます**。  

また **、Network Console** を使用して、DevTools から直接 HTTP 要求を作成して送信することもできます。  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="[ネットワーク本体] パネル" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   **[ネットワーク本体] パ**ネル  
:::image-end:::  

> [!TIP]
> DevTools Drawer ではなくメイン \(top\) パネルに[Network Console を表示するには、パ][DevtoolsCustomizeIndexDrawer]ネル[間のツールを移動してください](#move-tools-between-panels)。 **Network Console**  

> [!NOTE]
> 実用機能を有効にするには、「 [ネットワーク][DevtoolsExperimentalFeaturesTurnOn] 本体を有効にする」の横にあるチェックボックス **をオンにします**。  
> 
> ネットワーク ログ [を開き][DevtoolsNetworkIndexLogActivity]、コンテキスト メニュー \(右クリック\) を開き、[ **編集と再生] を選択します**。  

Chromium の問題はキ [#1093687][CR1093687]  

### [タイミング] タブのサービス ワーカーの応答フォーム  

ネットワーク **パネルの** [ **タイミング] タブに** サービス作業者 `respondWith` イベントが含まれるようになりました。  サービス `respondWith` の作業者イベントは、ハンドラーの確率が設定されたときに、サービス ワーカー イベント ハンドラーが実行を開始する直前の時間からの期間を `fetch` `respondWith` `fetch` 示します。  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="ネットワーク パネルの [タイミング] タブにある応答するサービス ワーカー イベント" lightbox="../../media/2020/06/timing-tab.msft.png":::
   ネットワーク `respondWith` パネルの [**タイミング**]**Network**タブのサービス ワーカー イベント  
:::image-end:::  

返信 **の受信した返信を開き** 、返信から追加情報 (「あなた」、「、そして見つかった `fetch` `CacheStorageCacheName` `serviceWorkerResponseSource` 返信」など) を表示します `ResponseTime` 。  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="受信した応答を追加した返信を表示するには、受信した応答を展開する" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   返信**の受信した回答を**表示する `fetch`  
:::image-end:::  

Chromium[の問題][CR1066579]#1066579  

### [問題] パネルのウェーント フィードバック  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   実用的な機能  
:::image-end:::  

[Webhint][WebhintMain] はオープン ソース ツールであり、ブラウザーの互換性、セキュリティ、パフォーマンス、PWA、Web サイトのその他の一般的な Web 開発に関する問題に関するリアルタイムのフィードバックを提供します。  [問題] パネルでウェーント フィードバックを [表示することができるようにな][DevtoolsIssues] りました。  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="[問題] パネルのウェーント フィードバック" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   [問題] パネルのウェーント フィードバック  
:::image-end:::  

> [!NOTE]
> 実用機能を有効にするには、「実用 [的な機能を][DevtoolsExperimentalFeaturesTurnOn] 有効にする」を参照し、[ウェーンを有効にする] の横にあるチェック **ボックスをオンにします**。  
> 
> [問題 [] パネル][DevtoolsIssues] を開いて、Web ハイートからのフィードバックを表示する。  

Chromium の問題 [#1070378][CR1070378]  

### パネル間でツールを移動する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="実用的な機能":::
   実用的な機能  
:::image-end:::  

通常、要素やネットワークなどのツール**は**、DevTools**Network**のメイン \(top\) パネルでのみ開く必要があります。  同様に **、3D ビュー**や問題などのツールは、DevTools の [下部\] パネルでのみ開く場合があります。 **Issues**  上下のパネルと下部パネルの間にあるツールを移動して、DevTools レイアウトをカスタマイズできるようになりました。  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="パネル間のタブの移動" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   パネル間のタブの移動  
:::image-end:::  

> [!NOTE]
> 実線を有効にするには、「環境内の[Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn]機能を有効にする」を参照し、[サポートを有効にする] の横にあるチェックボックスをオンにして、パネル間の**タブを移動します**。  

Chromium の [問題#897944][CR897944]  

### ネットワーク パネルのイニシア ツールヒントの向上  

Microsoft Edge 83 と 84 では、リソース要求の原因を示す [イニシアター] 列の[Network Log][DevtoolsNetworkIndexLogActivity]ツールヒント。この列には、水平スクロール バーが表示されたネットワーク ログに表示されます。  ツールヒント内を横方向にスクロールして要求を開始した通話スタックを見るには、通話スタックのみが表示されます。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 のイニシア ツールヒント" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   Microsoft Edge 84 のイニシア ツールヒント  
:::image-end:::  

Microsoft Edge 85 以降では、ツールヒントで [イニターの通話の開始] スタックを表示できます。横スクロールは必要ありません。  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 のイニシア ツールヒント" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   Microsoft Edge 85 のイニシア ツールヒント
:::image-end:::  

Chromium の [問題#1069404][CR1069404]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、Microsoft Edge 85 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。  

### CSS イン-JS フレームワーク用のスタイル編集  

スタイル**ウィンドウでは**[、CSS オブジェクト モデル (CSSOM)][CsswgDraftsCssom] API で作成されたスタイルを編集できるようになりました。  多くの CSS インジャンネルおよびライブラリでは、体重の下にある CSSOM API を使用してスタイルを構造化しています。  

[作成済みスタイルシート] を使用して JavaScript で追加されたスタイル [を編集できるようになりました][WicgConstructStylesheet]。  [[Shadow DOM]][MdnShadowDom]を使用するときに再利用可能なスタイルを作成して配布する新しい方法です。  

たとえば `h1` `CSSStyleSheet` 、\(CSSOM API\ で追加されたスタイル) は以前編集できませんでした。  スタイルは編集可能になり、[スタイル] ウィンドウ **でスタイルが編集できるようになり** ました。  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="CSSStyleSheet で追加された h1 スタイルの背景プロパティをピンクから薄い色に変更する" lightbox="../../media/2020/06/css-in-js.msft.png":::
   追加 `background` したスタイルの `h1` プロパティを `CSSStyleSheet` 変更 `pink` `lightblue` する
:::image-end:::  

この機能には [、CSS-in-JS を使用するサンプルを試してみてください][CodepenZoherghadyaliAbdgrpz]。

Chromium の問題は、chromium [の#946975][CR946975]  

### 灯カッパネルの灯 6  

灯 **ェーズ パネ** ルで灯している灯言語は、灯後 6 が実行されます。  すべての変更の完全な一覧については [、v6.0.0 リリース ノートを参照してください][GithubGoogleChromeLighthouse600]。  

灯読 6.0 は、レポートに新しい指数を追加します。最大コンテンツ ペイント \(LCP\)、累積レイアウトシフト \(CLS\)、合計ブロック時間 \(TBT\) が追加されました。  

パフォーマンス スコアの数式も改善されました。ユーザーの読み込みエクスペリエンスがより適しています。  

Chromium の問題 [#772558][CR772558]  

#### First Meaningful Paint Deprecation  

First Meaningful Paint \(FMP\) は、Lighthouse 6.0 で廃止されました。  また、FMP はパフォーマンス パ **ネルから** 削除されました。  **最大コンテンツ ペイントは、FMP** に代替えることをお勧めします。  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

Chromium の[問題][CR1096008]は#1096008  

### JavaScript の新しい機能のサポート  

DevTools では、一部の JavaScript 言語機能のサポートが改良されるようになりました。  

:::row:::
   :::column span="1":::
      [オートコンプリー][V8DevOptionalChaining] ト  
   :::column-end:::
   :::column span="2":::
      本体のプロパティの自動コンプリート**Console**では、オプションのチェーン構文がサポートされるようになりました。たとえば、これ以外にも `name?.` `name.` 、同様に機能します `name[` 。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      プライベート フィールドの書式強調表示 [の構文][V8DevClassFieldsPrivate]  
   :::column-end:::
   :::column span="2":::
      プライベート クラス フィールドが [ソース] パネルで正しく強調表示され、[ソース] パネルで正しく印刷されるように **な** りました。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      ネルルシュ コーロッシュ演算子の [構文][V8DevNullishCoalescing]
   :::column-end:::
   :::column span="2":::
      DevTools は、[ソース] パネルの計算演算子を正しく **印刷** します。  
   :::column-end:::
:::row-end:::  

Chromium[の問題][CR1073903]#1073903、#1083214、#1083797 [#1083214][CR1083214] [#1083797][CR1083797]  

### マニフェスト ウィンドウの新しいアプリ ショートカット警告  

**アプリ のショートカットにより** 、ユーザーは Web アプリ内で一般的なまたは推奨タスクをすばやく開始できます。  

<!--todo: add App shortcuts when section is live  -->  

マ **ニフェスト** ウィンドウに、次の条件の警告が表示されるようになりました。  

* アプリのショートカット アイコンが 96x96 ピクセル未満  
* アプリのショートカット アイコンとマニフェスト アイコンは、\(アイコンが無視されるため\)  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="アプリのショートカットの警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   アプリのショートカットの警告  
:::image-end:::  

Chromium の[問題][CR955497]は#955497  

### [縮された] ウィンドウの一定の表示  

[ **要素] パネルの** [ **作業** 結果] ウィンドウでは、すべてのビューポート サイズで一定のウィンドウとして一定のウィンドウとして表示されるようになりました。  以前は**Styles****、DevTools ビューポ**ートの幅が絞り込されていた [スタイル] ウィンドウ内に差し込み印刷されたウィンドウが入ります。  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="[Computed] ウィンドウは、DevTools が絞り込みの場合でも、一定の個別ウィンドウとして表示される" lightbox="../../media/2020/06/computed-pane.msft.png":::
   **[Computed]** ウィンドウは、DevTools が絞り込みの場合でも、一定の個別ウィンドウとして表示されます。
:::image-end:::  

Chromium の問題は、chromium [の#1073899][CR1073899]  

### WebAssembly ファイルのバイトコード オフセット  

DevTools では、Wasm disassembly の行数を表示するバイトコード オフセットを使用しました。  
行番号を使用すると、バイナリ データを確認する方法が明らかになり、Wasm ランタイム参照の場所に一定性があります。  

Chromium の問題 [#1071432][CR1071432]  

### [ソース] パネルの行間のコピーと切り取り  

[ソース] パネル エディターでコピーを実行したり切り取ったり [するとき][DevtoolsSourcesEditCssJavascript]、DevTools はコンテンツの現在の行をコピーまたは切り取ります。  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="5 行の末尾にカーソルを移動し、DevTools の pen.js から行全体をコピーして VS コードに貼り付けます。" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   5 行の末尾にカーソルを移動し、DevTools の **pen.jsから行全体をコピーして ** [VS コードに貼り付けます][VSCode]。
:::image-end:::  

Chromium[の問題][CR800028]#800028

### 本体の設定更新  

#### 同じ本体メッセージのグループ化を解除する  

本 **体設定で** 同様のトグルが適用されるようになりました。  以前は、同様のメッセージに適用されています。  

前に、DevTools は同じグループのようにオフになっていてもメッセージのグループ化 `hello` を解除しませんでした。 **Group similar**  これで、メッセージ `hello` はグループ解除されます。  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="同様のグループをオフにすると、Hello メッセージはグループ解除されます。" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   同 **様のグループをオフ** にすると、メッセージ `hello` はグループ解除されます。
:::image-end:::  

本体に重複メッセージを送信するサンプルを試 [してみてください][CodepenZoherghadyaliZyrjgdJ]。  

Chromium の問題 [#1082963][CR1082963]  

### 選択したコンテキストのみの設定を行う  

本 **体の設定で選択** したコンテキストのみが保存されます。  以前は、設定は、開いてから開いたびに再度開いた度でした。  この変更により、その他の本体設定オプションと一体で設定が同じになっています。  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="選択されたコンテキストのみの設定" lightbox="../../media/2020/06/selected-context.msft.png":::
   **選択されたコンテキストのみの** 設定  
:::image-end:::  

Chromium の問題 [#1055875][CR1055875]  

### パフォーマンス パネルの更新  

#### パフォーマンス パネルの JavaScript コンパイル キャッシュ情報  

[JavaScript のコンパイルキ][V8DevCodeCaching] ャッシュ情報が、パフォーマンス パネルの [概要] タブに常に表示されるようになりました。  以前は、コード キャッシュが実行されていない場合、DevTools はコード キャッシュに関連するものが何も表示されませんでした。  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript のコンパイル情報" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   JavaScript のコンパイル情報  
:::image-end:::  

Chromium の [問題#912581][CR912581]  

#### パフォーマンス パネルのナビゲーションタイミングの調整  

記録 **開始** 時に基づいてルーラーの時間を表示するために使用されるパフォーマンス パネル。  ユーザーがナビゲーションする場合のタイミングが変更されるようになりました。この場合、代わりに DevTools でナビゲーションに対して、ルーラーが表示されるようになりました。  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="パフォーマンス パネルでナビゲーションのタイミングを揃える" lightbox="../../media/2020/06/nav-timing.msft.png":::
   パフォーマンス パネルでナビゲーションのタ **イミングを** 揃える  
:::image-end:::  

最初のコンテンツ、最初のコンテンツ ファイント、大きいコンテンツ フル ペイント イベントの時間は、ナビゲーションの開始と相対的に更新され、このタイミングは報告されるタイミングと `DOMContentLoaded` 一致します `PerformanceObserver` 。  

Chromium の [問題はc#974550][CR974550]  

### 区切り点、条件付き改行ポイント、およびロゴの新しいアイコン  

[ **ソース] パ** ネルには、改ページ、条件付きのブレークポイント、およびロゴの新しいデザインがあります。  改行ポイントは[VS][VSCode]コードやインクと同様に、破たされた[Visual Studio。][VS]  アイコンは、条件付きの改行ポイントとロックポイントを区別するものに追加されます。  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="ブレークポイント" lightbox="../../media/2020/06/breakpoints.msft.png":::
   ブレークポイント  
:::image-end:::  

Chromium[の問題][CR1041830]#1041830  

## Microsoft Edge のプレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームとのつながりを手にする  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "Microsoft Edge DevTools コマンド メニューでコマンドを実行する |Microsoft ドキュメント"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ダイヤルパー - Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "環境の機能を有効にする - 実用的な機能 |Microsoft ドキュメント"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "Microsoft Edge DevTools の問題ツールに関する問題を見つけ、解決する |Microsoft ドキュメント"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "CSS と JavaScript の編集 - ソース パネルの概要 |Microsoft ドキュメント"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "ネットワーク アクティビティのログ - Microsoft Edge DevTools でのネットワーク アクティビティの検査 |Microsoft ドキュメント"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS イン-JS フレームワーク用のスタイル編集 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "重複メッセージを本体に送信する |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS グリッド計画ツールの例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR772558]: https://crbug.com/772558 "DevTools:最新バージョンの Lighthouse に更新する |Chromium のバグ"  
[CR800028]: https://crbug.com/800028 "Chrome 更新後に開発者ツール エディターの複製線のショートカット |Chromium のバグ"  
[CR912581]: https://crbug.com/912581 "DevTools/about:tracing に V8 によってコードされたコード付きスクリプトを示します |Chromium のバグ"  
[CR946975]: https://crbug.com/946975 "DevTools スタイルのサイドバーが構造化されたスタイルシートでは機能しません |Chromium のバグ"  
[CR955497]: https://crbug.com/955497 "PWA のアプリ アイコンのショートカット メニュー |Chromium のバグ"  
[CR974550]: https://crbug.com/974550 "Perf パネルと performanceObserver 間のメトリックの不一致 |Chromium のバグ"  
[CR1041830]: https://crbug.com/1041830 "区切り点の色を改善する |Chromium のバグ"  
[CR1055875]: https://crbug.com/1055875 "開発者ツールの開発および再度開いた後に、選択したコンテキストのみの設定は保存されません|Chromium のバグ"  
[CR1066579]: https://crbug.com/1066579 "DevTools:[ネットワーク パネル] の要求ごとの ServiceWorkers フェッチ タイムライン |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[コンピュートされたスタイル] タブが応答モードで消えます |Chromium のバグ"  
[CR1073903]: https://crbug.com/1073903 "DevTools: プライベート フィールドの構文 |Chromium のバグ"  
[CR1082963]: https://crbug.com/1082963 "本体の同様のメッセージ動作を無効にできません |Chromium のバグ"  
[CR1083214]: https://crbug.com/1083214 "アンダーンは、オプションのチェーンをサポートしていません |Chromium のバグ"  
[CR1083797]: https://crbug.com/1083797 "ネルルシュ コーローのためにブロークが切れる場合 |Chromium のバグ"  
[CR1096008]: https://crbug.com/1096008 "FMP を削除する |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/表ツール |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "合理ネットワーク要求を作成および再再生するためのツール |Chromium のバグ"  
[CR1070378]: https://crbug.com/1070378 "Webhint を DevTools に統合する |Chromium のバグ"  
[CR1069404]: https://crbug.com/1069404 "[開発ツール] ウィジェットのポップアップがすべて絞り込みすぎる |Chromium のバグ"  
[CR897944]: https://crbug.com/897944 "ドラッグ可能なデベロッパネル |Chromium のバグ"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge 開発者"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "シャドウの DOM の使用 |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge Preview チャネル"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studioコード"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS オブジェクト モデル (CSSOM) |W3C CSS 作業グループ エディターの下書き"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "Twitter アカウント@EdgeDevTools Twitter アカウント"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "プライベート クラス フィールド - パブリック クラス フィールドとプライベート クラス フィールド |V8.開発"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "JavaScript デベロッパー向けのコード キャッシュ |V8.開発"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish coalescing |V8.開発"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "オプションのチェーン |V8.開発"  

[WebhintMain]: https://webhint.io "Webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "コンストルーラー スタイルシート オブジェクト |Web Incubator CG"

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
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> 元のページがここに [あ](https://developers.google.com/web/updates/2020/06/devtools/index) り [、Jecelyn Yeen][JecelynYeen] \(デベロッパーのアドバイト、Chrome DevTools\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
