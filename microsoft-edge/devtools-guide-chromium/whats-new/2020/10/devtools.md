---
description: 新しい CSS Grid デバッグ ツール、Webauthn ツール、移動可能なツール、および計算されたサイドバー パネル。
title: DevTools の新機能 (Microsoft Edge 87)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0f4e0aaeba55f584697d1817f7ea54044dfdd380
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514355"
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
# <a name="whats-new-in-devtools-microsoft-edge-87"></a>DevTools の新機能 (Microsoft Edge 87)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="improving-devtools-localization"></a>DevTools ローカライズの改善  

翻訳のニーズを満たすために、DevTools チームMicrosoft Edge翻訳品質の向上に重点を置く必要があります。  バージョン 87 Microsoft Edgeから、いくつかの文字列と用語がロックされ、残りの DevTools が他の言語で表示されている場合でも変更されません。  影響を受ける文字列と用語の一覧には、次のものが含まれます。  

*   ライトハウス ツール **の** 文字列。  
*   用語 `service worker` .  
*   ネットワーク ツールの **フィルターの** 一部 `URL` `XHR` (、、、 `JS` `CSS` など)。  
*   [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]コンソール ユーティリティ API。  
    
[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]は、ローカライズされた[](/microsoft-edge/devtools-guide-chromium/console/index.md)バージョンの DevTools のユーザーがコンソールで利用できます。   DevTools のローカライズを改善するために、グローバル開発者コミュニティにMicrosoft Edgeありがとうございます。  すべての地域 [での DevTools](#getting-in-touch-with-microsoft-edge-devtools-team) のサポートを向上させるために、ローカライズ品質に関するフィードバックを引き続き送信します。  オープン ソース プロジェクトでこの機能に関するリアルタイムの更新Chromiumを確認するには、[問題の修正] に[#1136655。][CR1136655]  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="ローカライズされていないフィルターを含むネットワーク ツール" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   **ローカライズ** されていないフィルターを含むネットワーク ウィンドウ  
:::image-end:::  

## <a name="move-tools-between-top-and-bottom-panels"></a>上部パネルと下部パネルの間でツールを移動する  

DevTools では、上部パネルと下部パネルの間でのツールの移動がサポートされています。  2 つのツールの任意の組み合わせを同時に表示することで、DevTools をカスタマイズし、生産性を向上させます。  たとえば、[要素] ツールと******[** ソース] ツールを同時に表示します ([ソース] ツールを下部\に移動します)。 ****  この機能の履歴をオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#1075732。][CR1075732]  

:::row:::
   :::column span="":::
      上部のツールを下部に移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[下へ移動] を **選択します**。  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="下に移動する" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         下に移動する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      下部ツールを上部に移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] を **選択します**。  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="上に移動する" lightbox="../../media/2020/10/move-to-top.msft.png":::
         上に移動する  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <a name="save-and-export-using-the-network-console"></a>ネットワーク コンソールを使用して保存およびエクスポートする  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

ネットワーク **コンソール ツール** は、Postman [v2.1][PostmanSchemaJsonCollectionv210Index] および [OpenAPI v2][SwaggerSpecificationV2] スキーマとの互換性を向上しました。  実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]を有効にする] に移動し、[ネットワーク コンソールを有効にする] の横にある**チェック ボックスをオンにします**。  ネットワーク コンソールの詳細については、「 **ネットワーク**コンソールの実験機能を有効 [にする」に移動します][DevtoolsExperimentalFeaturesEnableNetworkConsole]。  この実験では、次のアクションがサポートされます。  

*   コレクションと環境を保存およびエクスポートします。  
*   ネットワーク コンソール ツール内の環境変数のセットを **編集およびエクスポート** します。  
    
この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#1093687。][CR1093687]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="新しい環境の名前を入力する" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         新しい環境の名前を入力する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="新しい環境の形式を選択する" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         新しい環境の形式を選択する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-grid-tooling"></a>CSS グリッド ツールの改善  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

DevTools Microsoft Edgeでは、CSS グリッドの検査、表示、およびデバッグに関する次の機能がサポートされています。  

*   [検査] ツールを使用して簡略化されたグリッド **オーバーレイを表示** するか、永続的なオーバーレイを使用して詳細な情報を取得します。  
*   永続的なグリッド オーバーレイを有効にするには、[要素] ツールでグリッド コンテナー要素の**** 横にあるグリッド アイコンを選択するか、レイアウト ツールでグリッドを**選択**します。  
*   複数のグリッドに対して永続的なオーバーレイを有効にできます。  
*   新しい **レイアウト ツール** を使用すると、グリッド オーバーレイを簡単に切り替え、それぞれの外観とコンテンツを構成できます。  
    
機能は既定で有効になっています。  機能の詳細については [、CSS グリッドに移動します][DevtoolsCssGrid]。  この機能の履歴をオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#1047356。][CR1047356]  さらに、Microsoft Edge DevTools チームは Chrome DevTools チームおよび Chromium コミュニティと協力して、新しいフレックスボックス ツール機能を DevTools に追加しています。  オープン ソース プロジェクトの flexbox ツールChromium更新プログラムについては、[問題の修正] に[#1136394。][CR1136394]  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="グリッド付きレイアウト ツール" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   **グリッド** 付きレイアウト ツール  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a>[設定] でキーボード ショートカットをカスタマイズする  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

これで、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  バージョン Microsoft Edge 84 以降では、キーボード ショートカットVisual Studio Code **** **DevTools (既定)** のプリセットを[選択できます][DevtoolsCustomizeShortcuts]。  バージョン 87 Microsoft Edgeから、キーボード ショートカット の有効化実験を**** 有効にして、キーボード ショートカットをさらに[カスタマイズできます][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

実験を有効にするには、[実験機能[][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]を有効にする] に移動し、[キーボード ショートカット エディターを有効にする] の横にある**チェック ボックスをオンにします**。  ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。  この機能に関するリアルタイムの更新プログラムをオープン ソース プロジェクトで確認するには、[Chromium] に移動[#174309。][CR174309]  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="スクリプトを一時停止するカスタム ショートカット" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   スクリプトを一時停止するカスタム ショートカット  
:::image-end:::  

## <a name="introducing-the-microsoft-edge-tools-for-visual-studio-code-extension"></a>拡張機能のMicrosoft EdgeツールVisual Studio Code紹介  

拡張機能**の Visual Studio Code****およびネットワーク**Visual Studio Codeの要素は、新しい開発者ツールMicrosoft Edge[に][VisualStudioCodeMarketplaceMsEdgedevtools]統合され、Visual Studio Codeされます。  コードをMicrosoft Edgeせずに、次のアクティビティに DevTools のMicrosoft Visual Studioしてください。  

*   DOM のデバッグ  
*   CSS の編集  
*   ネットワーク トラフィックの検査  

拡張機能を使用して、Microsoft Edgeを起動するか、ブラウザーの既存のインスタンスに接続するか、エディターから直接ヘッドレス ブラウザーを使用します。  この拡張機能に関するフィードバックに関する問題の寄稿と提出を開始するには[][GithubMicrosoftVscodeEdgeDevtools]、Microsoft Edge 開発者向け Visual Studio Code GitHub に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="ブラウザー モードの完全なスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         ブラウザー モードの完全なスクリーンショットで拡張機能を使用する  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="ヘッドレス モードのスクリーンショットで拡張機能を使用する" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         ヘッドレス モードのスクリーンショットで拡張機能を使用する  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-webauthn-tool"></a>新しい WebAuthn ツール  

以前のバージョンでは、Microsoft Edge WebAuthn デバッグのサポートはサポートされていませんでした。  Web 認証 API を使用して Web アプリケーションをテストするには、物理認証 [機能が必要でした][GithubW3cWebauthn]。  新しい **WebAuthn ツールを使用** すると、物理認証機能を使用せずに次の操作を実行できます。

*   認証機能のエミュレート
*   オーセンティケーターの属性をカスタマイズする
*   オーセンティケータの状態を検査する
    
**WebAuthn 機能の詳細については、DevTools**の [認証機能のエミュレートと[WebAuthn][DevtoolsWebauthnIndex]のデバッグMicrosoft Edge移動します。  

新しい[WebAuthn][DevtoolsWebauthnIndex]ツールを使用して、オーセンティケーターをエミュレートし[、Web 認証 API][GithubW3cWebauthn]をデバッグできます。  **WebAuthn ツールを開く**場合は **、[DevTools** \( \) のカスタマイズと制御] アイコンを選択し、[ `...` その他> ****  >  **WebAuthn] をクリックします**。  この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#1034663。][CR1034663]  

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

### <a name="elements-tool-updates"></a>要素ツールの更新  

#### <a name="view-the-computed-sidebar-pane-in-the-styles-pane"></a>[スタイル] ウィンドウで [計算されたサイドバー] ウィンドウを表示する  

[スタイル **] ウィンドウの [** 計算] ウィンドウ **を切り替** えます。  既定 **では、[スタイル]** ウィンドウ **の [計算** ] ウィンドウが折りたたまれています。  切り替えるには、ボタンを選択します。  この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトChromium確認するには、[問題の修正][に#1073899。][CR1073899]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="[計算] サイドバー ウィンドウを開く" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         [計算 **] サイドバー ウィンドウを開** く  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="計算されたサイドバー ウィンドウ" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         **計算されたサイドバー** ウィンドウ  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="grouping-css-properties-in-the-computed-panel"></a>[計算] パネルでの CSS プロパティのグループ化  

スクロールが少ない適用された CSS を表示するには、[計算] ウィンドウで CSS プロパティをカテゴリ別 **にグループ化** します。  CSS の検査中に、関連するプロパティのセットに選択的に集中することもできます。  [要素 **] ツール** で、要素を選択します。  CSS プロパティを \(または ungroup\) グループ化するには、[グループ] チェック ボックスを **オンにします** 。  Chromium オープンソース プロジェクトでこの機能に関するリアルタイムの更新を確認するには[、[Issues][CR1096230]#1096230]、[#1084673]、[][CR1084673]および [#1106251] に[移動します][CR1106251]。  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="CSS プロパティのグループ化" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   CSS プロパティのグループ化  
:::image-end:::  

### <a name="lighthouse-64-in-the-lighthouse-tool"></a>ライトハウス ツールのライトハウス 6.4  

ライト **ハウス ツール** は現在、ライトハウス 6.4 を実行しています。  変更の完全な一覧については、ライトハウスの [リリース ノートに移動します][GithubGoogleChromeLighthouseReleasesV641]。  この機能に関するリアルタイムの更新プログラムをオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#772558。][CR772558]  

### <a name="performancemark-events-in-the-timings-section"></a>[タイミング] セクションの performance.mark() イベント  

パフォーマンス **ツールの記録の** [タイミング] [セクションにイベント][DevtoolsGuideChromiumEvaluatePerformanceReference] がマーク `performance.mark()` されます。  この機能を試して JavaScript コードのパフォーマンスを測定するには、コード `performance.mark()` にイベントを追加します。  たとえば、次のコード スニペットは、ループの前と後にマーカーを追加し、7 の増分を使用して 0 から `for` 1000 まで反復します。  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

次に、パフォーマンス ツール [を開][DevtoolsGuideChromiumEvaluatePerformanceReference] き、[タイミング] セクション **に移動して** JavaScript コードを記録します。  追加 `performance.mark()` したイベントが記録に表示されます。  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark イベント" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` イベント  
:::image-end:::  

### <a name="new-resource-type-and-url-filters-in-the-network-tool"></a>ネットワーク ツールの新しいリソースの種類と URL フィルター  

ネットワーク 要求を `resource-type` フィルター処理 `url` するには、 **ネットワーク** ツールの new キーワードとキーワードを使用します。  たとえば、画像 `resource-type:image` であるネットワーク要求に焦点を当てる場合に使用します。  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="リソース型フィルター" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   リソース型フィルター  
:::image-end:::  

などの特別なキーワードを検索するには、 `resource-type` `url` プロパティで要求 [をフィルター処理します][DevtoolsNetworkReferenceFilterRequestsProperties]。  この機能に関するリアルタイム更新プログラムをオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題][][CR1121141]と [#1121141] [#1104188。][CR1104188]  

### <a name="frame-details-view-updates"></a>フレーム詳細ビューの更新  

#### <a name="display-coep-and-coop-reporting-to-endpoint"></a>COEP レポートと COOP レポートをエンドポイントに表示する  

[セキュリティと分離] セクションの下で、クロスオリジン エンベダー ポリシー \(COEP\) およびクロスオリジン Opener Policy \(COOP\) `reporting to` **エンドポイント&表示** します。  Reporting [API では、][MdnReportingApi] 新しい HTTP ヘッダーが定義され、警告とエラーを送信するブラウザーのサーバー エンドポイント `Report-To` を指定できます。  オープン ソース プロジェクトでこの機能に関するリアルタイムの更新Chromiumを確認するには、[プロジェクトの問題] に[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="エンドポイントへのレポート" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   エンドポイント `reporting to`  
:::image-end:::  

#### <a name="display-coep-and-coop-report-only-mode"></a>COEP および COOP レポート専用モードの表示  

DevTools では、 `report-only` モードに設定されている COEP と COOP のラベルが表示 `report-only` されます。  オープン ソース プロジェクトでこの機能に関するリアルタイムの更新Chromiumを確認するには、[プロジェクトの問題] に[#1051466。][CR1051466]  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="レポート専用モード ラベル" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   モード `report-only` ラベル  
:::image-end:::  

### <a name="view-and-fix-color-contrast-issues-in-the-css-overview-tool"></a>CSS の概要ツールで色のコントラストの問題を表示および修正する  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="試験的機能":::
   試験的機能  
:::image-end:::  

**CSS の概要ツール**で、色のコントラストに問題がある要素の一覧がページに表示されます。  次のデモ ページには、色のコントラストの問題の例があります。  

[CSS の概要 アクセス可能な色のデモ][GlitchCssOverviewAccessibleColorsDemo]  

この実験を有効にするには、[**テスト]**  >  **設定[CSS**の概要] チェック**ボックスをオン**にします。  色のコントラストに問題がある要素の一覧を表示するには、[ **コントラスト**] の問題で、[テキスト] を **選択します**。  要素ツールで要素を **開く** 場合は、一覧で要素を選択します。  コントラストの問題を解決するために、DevTools Microsoft Edge色の候補[が自動的に提供されます][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。  この機能に関するリアルタイムの更新プログラムをオープン ソース プロジェクトで確認するにはChromiumに移動し、[問題] [#1120316。][CR1120316]  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色コントラストの問題" lightbox="../../media/2020/10/css-overview.msft.png":::
   低色コントラストの問題  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "要素ツールの [プロパティ] ウィンドウの廃止 - DevTools (Microsoft Edge 84) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS グリッドのデバッグ機能 - 新機能 DevTools (Microsoft Edge 85) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane "[スタイル] ウィンドウの [アクセス可能な色の提案] - DevTools の新機能 (Microsoft Edge 86) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近選択した要素または JavaScript オブジェクト - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "パフォーマンス分析|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "試験的な API を有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 実験的な|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアル スクリーン モードのサポート - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "ネットワーク コンソールを有効にする - 実験的な|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース オーダー ビューアーを有効にする - 試験的機能 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式デバイスとデュアルスクリーン デバイスのテスト - 試験的機能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験機能を有効にする - 実験的な|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - コンソール API リファレンス | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける | Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "CSS グリッド の検査|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでレンダリング パフォーマンスを分析する - パフォーマンス分析リファレンス | Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "メディア プレーヤーの情報を表示およびデバッグ|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "プロパティ別に要求をフィルター処理する - ネットワーク分析の参照|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "DevTools サーバーで認証機能をエミュレートし、webAuthn Microsoft Edgeデバッグ|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft EdgeツールのVisual Studio Code |Visual Studio Code"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium bugs"
[CR772558]: https://crbug.com/772558 "DevTools: Lighthouse の最新バージョンに更新する | Chromium bugs"  
[CR1034663]: https://crbug.com/1034663 "WebAuthn テスト API のフロントエンドを作成|Chromiumバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS グリッド/Flexbox/Table ツーリング | Chromium bugs"  
[CR1051466]: https://crbug.com/1051466 "DevTools での COOP/COEP デバッグのサポート | Chromium bugs"  
[CR1073899]: https://crbug.com/1073899 "計算済みのスタイル タブが応答モードで表示されない | Chromium のバグ"  
[CR1075732]: https://crbug.com/1075732 "DevTools 個人用設定 - 移動可能なタブ |Chromiumバグ"  
[CR1084673]: https://crbug.com/1084673 "DevTools: CSS カスタム プロパティの表示方法を改善します (別名)。CSS 変数) とその値|Chromiumバグ"  
[CR1093687]: https://crbug.com/1093687 "統合ネットワーク要求を作成および再生するためのツールを作成する | Chromium のバグ"  
[CR1096230]: https://crbug.com/1096230 "[計算スタイル] ウィンドウの [カテゴリ別に CSS プロパティをグループ化|Chromiumバグ"  
[CR1104188]: https://crbug.com/1104188 "完全な URL ファイルを検索しても、ネットワーク ツールの検索で結果が|Chromiumバグ"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools: [計算スタイル] タブを改善|Chromiumバグ"  
[CR1120316]: https://crbug.com/1120316 "[CSS の概要] の [色] の下で>コントラストを|Chromiumバグ"  
[CR1121141]: https://crbug.com/1121141 "ネットワーク ログ のリソースの種類によるフィルター処理を許可|Chromiumバグ"  
[CR1121312]: https://crbug.com/1121312 "設定[その他のツール] メニューから削除する必要|Chromiumバグ"  
[CR1136394]: https://crbug.com/1136394 "Flexbox ツール |Chromiumバグ"  
[CR1136655]: https://crbug.com/1136655 "Devtools: ローカライズ V2 |Chromiumバグ"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "レポート API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/ライトハウス |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 認証|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "Hello! |Glitch"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman コレクション形式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 仕様|スワッガー"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developer.chrome.com/blog/new-in-devtools-87)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
