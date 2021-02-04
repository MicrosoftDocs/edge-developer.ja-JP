---
description: 新しい CSS グリッド デバッグ ツール、Webauthn ツール、移動可能なツール、コンピューティングサイドバー パネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cf3a685a1a4e9a3f13d2401a6294058a71dd5104
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313031"
---
# DevTools の新機能 (Microsoft Edge 87)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## DevTools ローカライズの改善  

Microsoft Edge DevTools チームは、翻訳のニーズを満たすために、翻訳品質の向上に重点を置いしています。  Microsoft Edge バージョン 87 から、いくつかの文字列と用語がロックされ、残りの DevTools が他の言語で表示されている場合でも変更されません。  影響を受ける文字列と用語の一覧は次のとおりです。  

*   [大島] **ツールの** 文字列。  
*   用語 `service worker` 。  
*   ネットワーク ツール **フィルターの** 一部 (例: `URL` , , , `XHR` `JS` `CSS` .  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソール ユーティリティ API。  
    
[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]は、ローカライズされた[](/microsoft-edge/devtools-guide-chromium/console/index.md)バージョンの DevTools のユーザーがコンソールで利用できます。   Microsoft Edge DevTools のローカライズの改善に役立つグローバル開発者コミュニティに感謝します。  すべてのローカライズ [での DevTools のサポートを](#getting-in-touch-with-microsoft-edge-devtools-team) 向上させるために、ローカライズ品質に関するフィードバックを引き続き送信します。  Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1136655。][CR1136655]  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワーク ツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   **ローカライズ** されていないフィルターを含むネットワーク ウィンドウ  
:::image-end:::  

## 上部と下部のパネル間でツールを移動する  

DevTools では、上部と下部のパネル間でのツールの移動がサポートされます。  2 つのツールの任意の組み合わせを同時に表示して、DevTools をカスタマイズし、生産性を向上させます。  たとえば、要素**ツールとソース**ツール**** を同時に表示します **(Sources**ツールを一番下に移動します\)。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue #1075732] [に移動します][CR1075732]。  

:::row:::
   :::column span="":::
      上部のツールを下部に移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] **を選択します**。  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="下に移動" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         下に移動  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      一番下のツールを一番上に移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] を **選択します**。  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="上へ移動" lightbox="../../media/2020/10/move-to-top.msft.png":::
         上へ移動  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## ネットワーク コンソールを使用して保存およびエクスポートする  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

ネットワーク **コンソール ツール** では [、Postman v2.1][PostmanSchemaJsonCollectionv210Index] および [OpenAPI v2][SwaggerSpecificationV2] スキーマとの互換性が向上しました。  実験を有効にするには、[試験的[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]な機能を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。  ネットワーク コンソールの詳細については、「ネットワーク コンソール **の**試験的機能を有効 [にする」に移動します][DevtoolsExperimentalFeaturesEnableNetworkConsole]。  この実験では、次の操作がサポートされます。  

*   コレクションと環境を保存およびエクスポートします。  
*   ネットワーク コンソール ツール内の環境変数のセットを **編集およびエクスポート** します。  
    
Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページ[#1093687。][CR1093687]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="新しい環境の名前を入力します。" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         新しい環境の名前を入力します。  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="新しい環境の形式を選択する" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         新しい環境の形式を選択する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## CSS グリッド ツールの強化  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

Microsoft Edge DevTools では、CSS グリッドを検査、表示、デバッグするために次の機能がサポートされます。  

*   **検査**ツールを使用して、簡略化されたグリッド オーバーレイを表示するか、永続的なオーバーレイを使用してより詳細な情報を取得します。  
*   固定グリッド オーバーレイを有効にするには、 **要素** ツールのグリッド コンテナー要素の横にあるグリッド アイコンを選択するか、レイアウト ツールでグリッドを **選択** します。  
*   複数のグリッドに対して固定オーバーレイを有効にできます。  
*   新しい **レイアウト ツールを** 使用すると、グリッド オーバーレイを簡単に切り替え、それぞれの外観とコンテンツを構成できます。  
    
この機能は既定で有効になっています。  機能の詳細については [、CSS グリッドに移動します][DevtoolsCssGrid]。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、[Issue #1047356] [に移動します][CR1047356]。  さらに、Microsoft Edge DevTools チームは Chrome DevTools チームおよび Chromium コミュニティと協力して、DevTools に新しい flexbox ツール機能を追加しています。  Chromium オープン ソース プロジェクトの flexbox ツールの更新については、[問題] ページ[#1136394。][CR1136394]  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="グリッドを含むレイアウト ツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   **グリッド** を含むレイアウト ツール  
:::image-end:::  

## [設定] でキーボード ショートカットをカスタマイズする  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  Microsoft Edge バージョン 84 以降では、キーボード ショートカットの既定の Visual Studio **コード** と **DevTools (既定)** のプリセットから [選択できます][DevtoolsCustomizeShortcuts]。  Microsoft Edge バージョン 87 から、キーボード ショートカット**** エディターの有効化実験を有効にして、キーボード ショートカットをさらに[カスタマイズできます][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

実験を有効にするには、[試験的[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]な機能を有効にする] に移動し、[キーボード ショートカット エディターを有効にする] の横にあるチェック**ボックスをオンにします**。  ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。  Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#174309。][CR174309]  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="スクリプトを一時停止するカスタム ショートカット" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   スクリプトを一時停止するカスタム ショートカット  
:::image-end:::  

## Microsoft Edge Tools for Visual Studio Code 拡張機能の紹介  

現在 **、Visual Studio Code** 拡張機能と **Network for Visual Studio コード** 拡張機能の要素は、新しい [Microsoft Edge Developer Tools for Visual Studio統合][VisualStudioCodeMarketplaceMsEdgedevtools] されました。  Microsoft Edge DevTools は、次のコードを残さずに次のVisual Studioします。  

*   DOM をデバッグする  
*   CSS の編集  
*   ネットワーク トラフィックを検査する  

拡張機能を使用して、Microsoft Edge を起動するか、ブラウザーの既存のインスタンスに接続するか、エディターから直接ヘッドレス ブラウザーを使用します。  この拡張機能に関するフィードバックに関する問題の提出と提出を開始するには、GitHub の [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] リポジトリに移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="ブラウザー モードの完全なスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         ブラウザー モードの完全なスクリーンショットで拡張機能を使用する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ヘッドレス モードでの拡張機能の使用のスクリーンショット" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         ヘッドレス モードでの拡張機能の使用のスクリーンショット  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新しい WebAuthn ツール  

以前のバージョンの Microsoft Edge では、ネイティブの WebAuthn デバッグサポートは提供されていませんでした。  Web 認証 API を使用して Web アプリケーションをテストするには、物理認証システム [が必要でした][GithubW3cWebauthn]。  新しい **WebAuthn** ツールを使用すると、物理認証を使用せずに次の操作を実行できます。

*   認証システムをエミュレートする
*   認証システムの属性をカスタマイズする
*   認証システムの状態を検査する
    
WebAuthn 機能の詳細 **については、「Authenticators** をエミュレートする」に移動し [、Microsoft Edge DevTools で WebAuthn をデバッグします][DevtoolsWebauthnIndex]。  

新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使用して、認証機能をエミュレートし、Web 認証[API][GithubW3cWebauthn]をデバッグできます。  **WebAuthn ツールを開**するには **、[DevTools**のカスタマイズと制御] アイコン (\) アイコンを選択し、[ `...` その他> ****  >  **WebAuthn] をクリックします**。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページ[#1034663。][CR1034663]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="WebAuthn ツールを開く" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         **WebAuthn ツールを開**く  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn ツール" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         **WebAuthn** ツール  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 要素ツールの更新  

#### [スタイル] ウィンドウの [計算されたサイドバー] ウィンドウを表示する  

[スタイル **] ウィンドウの [** 計算] ウィンドウ **を切り替** えます。  [ **スタイル] ウィンドウ** の [ **計算** ] ウィンドウは、既定で折りたたまれています。  切り替えるには、ボタンを選択します。  Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1073899。][CR1073899]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="計算されたサイドバー ウィンドウを開く" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         計算された **サイドバー ウィンドウを開** く  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="計算されたサイドバー ウィンドウ" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         **計算されたサイドバー** ウィンドウ  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 計算パネルでの CSS プロパティのグループ化  

適用されている CSS のスクロールを減らして表示するには、[計算] ウィンドウで CSS プロパティをカテゴリ別 **にグループ化** します。  また、CSS を検査する間は、関連するプロパティのセットに選択的に焦点を当てることができます。  要素ツール **から** 要素を選択します。  CSS プロパティを \(または ungroup\) グループ化するには、[グループ] チェック ボックスを **オフ** にします。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] #1096230 [#1084673][CR1096230] []、][CR1084673]および [更新[#1106251。][CR1106251]  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="CSS プロパティのグループ化" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   CSS プロパティのグループ化  
:::image-end:::  

### 1 つ以上のツールの 6.4  

これで **、The 立** ち回りツールは 6.4 を実行しています。  変更の完全な一覧については、大島のリリース [ノートに移動します][GithubGoogleChromeLighthouseReleasesV641]。  Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#772558。][CR772558]  

### [タイミング] セクションの performance.mark() イベント  

パフォーマンス **ツールの記録の** [タイミング] セクション [でイベントが][DevtoolsGuideChromiumEvaluatePerformanceReference] マーク `performance.mark()` されます。  この機能を試し、JavaScript コードのパフォーマンスを測定するには、コード `performance.mark()` にイベントを追加します。  たとえば、次のコード スニペットでは、ループの前と後にマーカーを追加し、7 の増分を使用して 0 から `for` 1000 まで反復します。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

次に、パフォーマンス ツール [を開][DevtoolsGuideChromiumEvaluatePerformanceReference] き、[ **タイミング]** セクションに移動して JavaScript コードを記録します。  追加 `performance.mark()` したイベントが記録に表示されます。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark イベント" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` events  
:::image-end:::  

### ネットワーク ツールの新しいリソースの種類と URL フィルター  

ネットワーク ツールの `resource-type` 新 `url` しいキーワードを**** 使用して、ネットワーク要求をフィルター処理します。  たとえば、画像 `resource-type:image` であるネットワーク要求に焦点を当てる場合に使用します。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="resource-type filter" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   resource-type filter  
:::image-end:::  

To discover more special keywords such as `resource-type` `url` and, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].  Chromium オープン ソース プロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題] [#1121141に移動][CR1121141]して[#1104188。][CR1104188]  

### フレーム詳細ビューの更新  

#### COEP および COOP レポートをエンドポイントに表示する  

[セキュリティと保護の分離] セクションで、クロスオリジン 埋め込みポリシー \(COEP\) およびクロスオリジン オープン ポリシー \(COOP\) `reporting to` **エンドポイント&表示** します。  レポート [API は][MdnReportingApi] 、新しい HTTP ヘッダーを定義します。これにより、ブラウザーが警告やエラーを送信するためのサーバー エンドポイント `Report-To` を指定できます。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページに移動[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="エンドポイントへのレポート" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   エンドポイント `reporting to`  
:::image-end:::  

#### COEP および COOP レポート専用モードを表示する  

DevTools に、モードに `report-only` 設定されている COEP と COOP のラベルが表示 `report-only` されます。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、[問題] ページに移動[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="レポート専用モード ラベル" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   モード `report-only` ラベル  
:::image-end:::  

### CSS 概要ツールで色コントラストの問題を表示および修正する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

CSS **概要ツールで** 、ページ上に色コントラストの問題がある要素の一覧が表示されます。  次のデモ ページには、カラー コントラストの問題の例が示されています。  

[CSS の概要のアクセス可能な色のデモ][GlitchCssOverviewAccessibleColorsDemo]  

この実験を有効にするには、[設定**の実験]**  >  **で**、[CSS の概要]**チェック ボックスをオン**にします。  色コントラストの問題がある要素の一覧を表示するには、[ **コントラスト**] の問題で [テキスト] を選択 **します**。  要素ツールで要素を **開く** 場合は、一覧から要素を選択します。  コントラストの問題を解決するために、Microsoft Edge DevTools は自動的に色の候補 [を提供します][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。  Chromium オープン ソース プロジェクトでこの機能のリアルタイムの更新を確認するには、[問題] ページ[#1120316。][CR1120316]  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色コントラストの問題" lightbox="../../media/2020/10/css-overview.msft.png":::
   低色コントラストの問題  
:::image-end:::  

## Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "Elements ツールの [プロパティ] ウィンドウの廃止 - DevTools (Microsoft Edge 84) の新機能|Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッド デバッグ機能 - DevTools の新機能 (Microsoft Edge 85) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウのアクセス可能な色の候補 - DevTools の新機能 (Microsoft Edge 86) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "パフォーマンス分析のリファレンス |Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク コンソールを有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "試験的機能を有効にする - 試験的な機能|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッド を検査|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディア プレーヤー情報の表示とデバッグ|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティで要求をフィルター処理する - ネットワーク分析の参照|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "Microsoft Edge DevTools アプリケーションで認証システムをエミュレートし、WebAuthn をデバッグ|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API サービスのフロントエンドを作成|Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools 個人用設定 - 移動可能なタブ |Chromium のバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタム プロパティ ((aka) を表示する方法を改善します。CSS 変数) とその値|Chromium のバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "[計算されたスタイル] ウィンドウのカテゴリ別に CSS プロパティを|Chromium のバグ"  
[CR1104188]: https://crbug.com/1104188 "完全な URL を検索しても、ネットワーク ツールの検索で結果が|Chromium のバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算されたスタイル] タブの|Chromium のバグ"  
[CR1120316]: https://crbug.com/1120316 "CSS Overview > Colors |Chromium Bugs"  
[CR1121141]: https://crbug.com/1121141 "ネットワーク ログ サーバーでリソースの種類によるフィルター処理を|Chromium のバグ"  
[CR1121312]: https://crbug.com/1121312 "[その他のツール] メニューから設定を削除する必要|Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |Chromium Bugs"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズ V2 |Chromium のバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/|GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "Hello! |Glitch"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 仕様|Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/10/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen