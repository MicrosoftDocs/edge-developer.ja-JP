---
description: 新しい CSS Grid のデバッグツール、Webauthn ツール、移動可能ツール、および計算されたサイドバーパネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0e4b1972918797d69e2068236f6d1336c54cc858
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134103"
---
# DevTools の新機能 (Microsoft Edge 87)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## DevTools のローカライズの改善  

翻訳のニーズを満たすために、Microsoft Edge DevTools チームは翻訳品質を向上させることに重点を置いています。  Microsoft Edge バージョン87以降では、いくつかの文字列と用語がロックされており、他の DevTools が他の言語で表示されている場合でも変更されません。  影響を受ける文字列と用語の一覧には、次のようなものがあります。  

*   **Lighthouse**ツールの文字列。  
*   用語 `service worker` 。  
*   **ネットワーク**ツールには、、、、などのフィルターがあり `URL` `XHR` `JS` `CSS` ます。  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソールユーティリティ API。  
    
[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] は、devtools のローカライズされたバージョンでのユーザーの [コンソール](/microsoft-edge/devtools-guide-chromium/console/index.md) で利用できるようになりました。   Microsoft Edge DevTools のローカライズの改善に向けて、世界中の開発者コミュニティに感謝します。  すべてのロケールでの DevTools のサポートを向上させるために、引き続き [ローカリゼーションの品質に関するフィードバックを送信して](#getting-in-touch-with-microsoft-edge-devtools-team) ください。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1136655][CR1136655]] に移動します。  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   ローカライズされていないフィルターが表示された**ネットワーク**ウィンドウ  
:::image-end:::  

## 上下パネル間の移動ツール  

DevTools では、上と下のパネル間の移動ツールがサポートされるようになりました。  同時に2つのツールを自由に組み合わせて表示して、開発者向けツールをカスタマイズして生産性を向上させることができます。  たとえば、 **要素** と **ソース** ツールを ( **ソース** ツールを下に移動することによって) 表示します。  Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、[懸案事項の [#1075732][CR1075732]に移動します。  

:::row:::
   :::column span="":::
      一番上のツールを下に移動するには、タブをポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **下へ移動**] を選択します。  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         下へ移動  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      一番下にあるツールを一番上に移動するには、タブ上にカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **先頭へ移動**] を選びます。  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/move-to-top.msft.png":::
         先頭に移動  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## ネットワークコンソールを使用した保存とエクスポート  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール":::
   実験的機能  
:::image-end:::  

**ネットワークコンソール**ツールでは、 [Postman v 2.1][PostmanSchemaJsonCollectionv210Index]スキーマと[openapi v2][SwaggerSpecificationV2]スキーマとの互換性が改善されました。  実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] を有効にする」に移動し、[ **ネットワーク本体を有効**にする] の横にあるチェックボックスをオンにします。  **ネットワークコンソール**の詳細については、「[ネットワーク本体の実験的機能を有効][DevtoolsExperimentalFeaturesEnableNetworkConsole]にする」を参照してください。  この実験では、次の操作がサポートされるようになりました。  

*   コレクションと環境を保存し、エクスポートします。  
*   **ネットワークコンソール**ツール内の環境変数のセットを編集およびエクスポートします。  
    
Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1093687][CR1093687]] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         新しい環境の名前を入力する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         新しい環境の形式を選ぶ  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 強化された CSS Grid ツール  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール":::
   実験的機能  
:::image-end:::  

Microsoft Edge DevTools では、CSS グリッドの検査、表示、デバッグのための次の機能がサポートされるようになりました。  

*   **検査**ツールを使用してシンプルなグリッドオーバーレイを表示するか、持続的なオーバーレイを使って詳細な情報を取得します。  
*   永続的なグリッドオーバーレイを有効にするには、 **要素** ツールで grid コンテナー要素の横にあるグリッドアイコンを選択するか、 **レイアウト** ツールでグリッドを選択します。  
*   複数のグリッドに対して持続的なオーバーレイを有効にすることができます。  
*   新しい **レイアウト** ツールでは、グリッドのオーバーレイを簡単に切り替えて、それぞれの外観と内容を構成することができます。  
    
これらの機能は、既定で有効になっています。  機能の詳細については、「 [CSS グリッド][DevtoolsCssGrid]」を参照してください。  Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、[懸案事項の [#1047356][CR1047356]に移動します。  さらに、Microsoft Edge DevTools チームでは、Chromium コミュニティを使用して、新しい flexbox ツール機能を DevTools に追加しています。  Chromium のオープンソースプロジェクトの flexbox ツーリングでの更新については、[問題の [#1136394][CR1136394]] に移動します。  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   グリッド付き**レイアウト**ツール  
:::image-end:::  

## 設定のショートカットキーをカスタマイズする  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール":::
   実験的機能  
:::image-end:::  

DevTools で操作のキーボードショートカットをカスタマイズできるようになりました。  Microsoft Edge バージョン84以降では、[キーボードショートカット][DevtoolsCustomizeShortcuts]の**Visual Studio コード**と**devtools (既定)** プリセットのいずれかを選ぶことができます。  Microsoft Edge バージョン87以降では、キーボードショートカットの **有効化を有効** にすることで、 [キーボードショートカット][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]をさらにカスタマイズすることができます。  

実験を有効にするには、「 [実験的な機能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] を有効にする」に移動し、[ショートカットキーを **有効**にする] の横にあるチェックボックスをオンにします。  ショートカットのカスタマイズと編集について詳しくは、「 [キーボードショートカットエディターの実験的機能を有効][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]にする」を参照してください。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#174309][CR174309]] に移動します。  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   スクリプトを一時停止するためのカスタムショートカット  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio のコード拡張機能の概要  

Visual studio**コードおよび visual studio コード拡張**用の**要素**は、 [Microsoft Edge 開発者向けの visual studio コード拡張用][VisualStudioCodeMarketplaceMsEdgedevtools]の新しいツールにマージされました。  Visual Studio コードを終了せずに、次のアクティビティには Microsoft Edge DevTools を使用します。  

*   DOM をデバッグする  
*   CSS を編集する  
*   ネットワークトラフィックを検査する  

拡張機能を使用して、Microsoft Edge を起動するか、ブラウザーの既存のインスタンスに接続するか、またはエディターから直接ヘッドレスブラウザーを使用します。  この拡張機能についてのフィードバックを投稿して、問題の投稿とファイリングを開始するには、GitHub の [Visual Studio コードリポジトリ用 Microsoft Edge 開発者ツール][GithubMicrosoftVscodeEdgeDevtools] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         完全ブラウザーモードのスクリーンショットで拡張機能を使用する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         ヘッドレスモードのスクリーンショットで拡張機能を使用する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新しい WebAuthn ツール  

以前のバージョンの Microsoft Edge では、ネイティブの WebAuthn デバッグのサポートはありませんでした。  Web アプリケーションを [Web 認証 API][GithubW3cWebauthn]でテストするには、物理認証が必要です。  新しい **WebAuthn** ツールを使用すると、物理的なオーセンティケータを使用せずに、次の操作を実行できます。

*   オーセンティケータのエミュレート
*   オーセンティケータの属性をカスタマイズする
*   オーセンティケータの状態を検査する
    
**WebAuthn**機能の詳細については、「 [Microsoft Edge devtools でオーセンティケータをエミュレートし、WebAuthn をデバッグする」][DevtoolsWebauthnIndex]を参照してください。  

新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使って、オーセンティケータをエミュレートし、 [Web 認証 API][GithubW3cWebauthn]をデバッグすることができます。  **Webauthn**ツールを開くには、[**ユーザー設定と制御のための devtools** \ ( `...` \)] アイコン > [**その他のツール**] WebAuthn を選び  >  **WebAuthn**ます。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1034663][CR1034663]] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         [ **WebAuthn** ] ツールを開く  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         **WebAuthn** ツール  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 要素ツールの更新プログラム  

#### [スタイル] ウィンドウの [計算されたサイドバー] ウィンドウを表示する  

[**スタイル**] ウィンドウで**計算**されたウィンドウを切り替えます。  既定では、[**スタイル**] ウィンドウの**計算**ウィンドウは折りたたまれています。  切り替えを行うには、ボタンを選択します。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1073899][CR1073899]] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         [計算された **サイドバー** ] ウィンドウを開く  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         **計算** されたサイドバーウィンドウ  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 計算されたパネルでの CSS プロパティのグループ化  

適用した CSS のスクロールを減らして、CSS のプロパティをカテゴリ別にグループ化するには、[ **計算** ] ウィンドウの [カテゴリ別] をグループ化します。  CSS を検査しながら、一連の関連するプロパティに対して選択的にフォーカスを設定することもできます。  **要素**ツールで要素を選択します。  [CSS のプロパティ] をグループ化またはグループ解除するには、[ **グループ化** ] チェックボックスをオンにします。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[ [#1096230][CR1096230]]、[ [#1084673][CR1084673]]、[ [#1106251][CR1106251]] に移動します。  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   CSS プロパティのグループ化  
:::image-end:::  

### Lighthouse ツールの Lighthouse 6.4  

**Lighthouse**ツールで Lighthouse 6.4 が実行されています。  すべての変更の一覧については、 [Lighthouse のリリースノート][GithubGoogleChromeLighthouseReleasesV641]を参照してください。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#772558][CR772558]] に移動します。  

### [タイミング] セクションの performance. mark () イベント  

[パフォーマンス][DevtoolsGuideChromiumEvaluatePerformanceReference]ツールの記録の [**タイミング] セクション**で、イベントがマークされるようになりました `performance.mark()` 。  この機能を試して、JavaScript コードのパフォーマンスを測定するには、 `performance.mark()` コードにイベントを追加します。  たとえば、次のコードスニペットでは、 `for` 7 のインクリメントを使用して0から1000までのループの前後にマーカーを追加します。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

次に、 [パフォーマンス][DevtoolsGuideChromiumEvaluatePerformanceReference] ツールを開き、[ **タイミング] セクション** に移動して、JavaScript コードを記録します。  `performance.mark()`追加したイベントが記録に表示されるようになりました。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` 事象  
:::image-end:::  

### ネットワークツールの新しいリソースの種類と url のフィルター  

ネットワークツールの新規とキーワードを使って、 `resource-type` `url` ネットワーク要求をフィルター処理します。 **Network**  たとえば、画像で `resource-type:image` あるネットワーク要求にフォーカスするために使用します。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   リソースの種類フィルター  
:::image-end:::  

などのその他の特殊なキーワードについて `resource-type` `url` は、「 [プロパティによる要求をフィルター処理][DevtoolsNetworkReferenceFilterRequestsProperties]する」を参照してください。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [#1121141][CR1121141] と [#1104188][CR1104188]に移動します。  

### フレームの詳細ビューの更新  

#### COEP と CO-OP レポートをエンドポイントに表示  

`reporting to`[**セキュリティ & 分離**] セクションで、cross-origin Embedder POLICY \ (coep \) と cross-origin Opener POLICY \ (co-op) エンドポイントを表示します。  [レポート API][MdnReportingApi]では、新しい HTTP ヘッダーが定義され `Report-To` ています。これにより、ブラウザーのサーバーエンドポイントを指定して、警告やエラーを送信できます。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1051466][CR1051466]] に移動します。  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   `reporting to`エンドポイント  
:::image-end:::  

#### COEP および CO-OP レポート専用モードの表示  

`report-only`DEVTOOLS と co-op のラベルが表示されるようになりました。これは、モードに設定されてい `report-only` ます。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1051466][CR1051466]] に移動します。  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   `report-only`モードラベル  
:::image-end:::  

### CSS の概要ツールで色のコントラストの問題を表示して修正する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール":::
   実験的機能  
:::image-end:::  

**CSS の概要**ツールでは、色のコントラストの問題があるページの要素の一覧が表示されるようになりました。  次のデモページでは、色のコントラストの問題の例を示します。  

[CSS の概要アクセシビリティの高い色のデモ][GlitchCssOverviewAccessibleColorsDemo]  

この実験を有効にするには、[**設定**の実験] で [  >  **Experiments** **CSS の概要**] チェックボックスをオンにします。  色のコントラストの問題がある要素の一覧を表示するには、[ **コントラストの問題**] で [ **テキスト**] を選択します。  **要素ツールで**要素を開くには、リスト内の要素を選択します。  コントラストの問題を解決するために、Microsoft Edge DevTools では [色候補が自動的に提供][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]されます。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題の [#1120316][CR1120316]] に移動します。  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="ローカライズされていないフィルターを含むネットワークツール" lightbox="../../media/2020/10/css-overview.msft.png":::
   低色のコントラストの問題  
:::image-end:::  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "要素ツールの [プロパティ] ウィンドウの廃止-DevTools の新機能 (Microsoft Edge 84) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS grid のデバッグ機能-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウでアクセシビリティの高い色の候補を表示する (DevTools の新機能 (Microsoft Edge 86) |Microsoft ドキュメント"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選んだ要素または JavaScript オブジェクト-コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "業績分析リファレンス |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "実験的な Api を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボードショートカットエディターを有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク本体の実験的機能を有効にする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース注文ビューアーを有効にする-実験的な機能 |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式とデュアルスクリーンデバイスでのテスト-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッドの検査 |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブの [パフォーマンス分析] 参照で、レンダリングのパフォーマンスを分析します。Microsoft ドキュメント"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディアプレーヤー情報を表示してデバッグする |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティによるフィルター要求-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "Microsoft Edge DevTools でオーセンティケータをエミュレートし、WebAuthn をデバッグします。Microsoft ドキュメント"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード |Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"
[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API のフロントエンドを作成します。 |Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツーリング |Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1073899]: https://crbug.com/1073899 "[計算されたスタイル] タブが応答モードで表示されなくなります。Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools パーソナル化-移動可能なタブ |Chromium のバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタムプロパティの表示方法を改善します ((別名)。CSS 変数) とその値 |Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "代理ネットワーク要求を作成および再生するためのツールを作成する |Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "計算されたスタイルウィンドウのカテゴリ別のグループ CSS プロパティ |Chromium のバグ"  
[CR1104188]: https://crbug.com/1104188 "ネットワークツール検索で完全な URL を検索しても結果が見つかりません |Chromium のバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算されたスタイルの改善] タブ |Chromium のバグ"  
[CR1120316]: https://crbug.com/1120316 "[CSS の概要 > 色] でコントラストの悪い箇所を強調表示する |Chromium のバグ"  
[CR1121141]: https://crbug.com/1121141 "ネットワークログでのリソースの種類によるフィルターの許可 |Chromium のバグ"  
[CR1121312]: https://crbug.com/1121312 "[その他のツール] メニューから設定を削除する必要があります。Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |Chromium のバグ"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズバージョン V2 |Chromium のバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v 6.4.1-GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証 |GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "こんにちは! |故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v 2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI の仕様 |Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/10/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
