---
description: キーボードショートカットを Visual Studio コードに合わせて、Surface Duo と Samsung Galaxy をエミュレートし、CSS グリッドのオーバーレイ機能を強化します。
title: DevTools の新機能 (Microsoft Edge 86)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 74fb4e276547d9f653a5bcbdcab9c4406d09a81a
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104862"
---
# DevTools の新機能 (Microsoft Edge 86)  

## Microsoft Edge DevTools チームからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### DevTools のキーボードショートカットを Visual Studio コードに一致させる  

Microsoft Edge 86 では、DevTools のキーボードショートカットが [Visual Studio コード][VisualStudioCode]のショートカットに対応している可能性があります。 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   DevTools for Visual Studio コードのキーボードショートカットを一致させる  
:::image-end:::  

この機能を有効にするには、 [Microsoft Edge DevTools の [キーボードショートカットのカスタマイズ][DevtoolsCustomizeShortcuts]] に移動します。  

たとえば、 [Visual Studio コード][VisualStudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは、 `F5` です。  **Devtools (既定)** の事前設定を使用すると、devtools でも同じショートカットが表示され `F8` ますが、 **Visual Studio のコード**プリセットを選択すると、このようにショートカットが作成され `F5` ます。  

Chromium の問題 [#174309][CR174309]  

### Surface Duo と Samsung Galaxy 折りたたみのエミュレート  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる":::
   実験的機能  
:::image-end:::  

Microsoft Edge で、  [Surface Duo][MicrosoftSurfaceDevicesDuo] と [Samsung Galaxy][SamsungMobileGalaxyFold] の2つの新しいデバイスで web サイトまたはアプリの外観をテストできるようになりました。  

デュアル画面と折りたたみ式デバイスのために web サイトやアプリを強化するには、 [デバイスをエミュレート][DevtoolsDeviceModeIndex]するときに次の機能を使用します。  

*   [スパニング][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: web サイト \ (またはアプリ \) が両方の画面に表示されます。
*   2つの画面の間の領域である[継ぎ目をレンダリング][DualScreenIntroductionHowWorkSeam]します。
*   [実験的な Web プラットフォーム api を有効][DevtoolsExperimentalFeaturesEnableExperimentalApis] にして、新しい [CSS メディア画面のスパニング機能][DualScreenWebCssMediaSpanning] と [JavaScript getwindowsegments api][DualScreenWebJavascriptGetwindowsegments]にアクセスします。  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   Surface Duo のデバイスエミュレーション  
:::image-end:::  

この実験的な機能を有効にするには、「 [実験的な機能を有効][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] にする」に移動し、[ **エミュレーション: Support dual screen mode**] の横にあるチェックボックスをオンにします。  

この実験の詳細については、「 [エミュレーション: デュアルスクリーンモードのサポート][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]」を参照してください。  

Chromium の問題: [#1054281][CR1054281]  

### CSS グリッドのオーバーレイの改善と新しい実験的なグリッド機能  

CSS グリッドのオーバーレイの改善について、ご意見をお寄せいただきありがとうございます。  CSS グリッドのオーバーレイは既定で有効になりました。実験を有効にする必要はありません。  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   要素の CSS グリッドのオーバーレイ `article`  
:::image-end:::  

> [!NOTE]
> グリッドオーバーレイの詳細については、「 [CSS grid デバッグ機能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]」を参照してください。  

Microsoft Edge DevTools チームと Chrome DevTools チームは、その他の機能について共同作業しています。  新機能には、[**要素**] パネルの新しい**レイアウト**ウィンドウで永続的かつ構成可能な複数のオーバーレイが含まれています。  

この実験的な機能を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 有効にする」のチェックボックスをオンにし、[新しい CSS グリッドのデバッグ機能を有効にする] の横にあるチェックボックスをオンにします **(再起動後に、[レイアウト] サイドバーウィンドウで利用できる構成オプション)**。  

この実験の詳細については、「 [新しい CSS grid デバッグ機能を有効][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]にする」を参照してください。  

Chromium の問題: [#1047356][CR1047356]  

### コンソールからコピーした表の書式が保持される  

Microsoft Edge 85 以前のバージョンでは、コピーの書式設定が `console.table` 失われました。  [表][DevtoolsConsoleApiTable]本体 API から出力をコピーして貼り付けた場合、表のテキストのみが保持されます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` Microsoft Edge 85 以前の本体の API 出力  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 85 またはそれ以前のバージョンの Visual Studio コードに貼り付けられた本体 API の出力  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Microsoft Edge 86 以降では、 **コンソール**から表をコピーすると、書式設定が保持されるようになりました。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` Microsoft Edge 86 以降の本体の API 出力  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` Microsoft Edge 86 以降で Visual Studio コードに貼り付けられた本体 API の出力  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium の問題: [#1115011] [CR1115011]  

### 簡単なアクセシビリティテストのためのソースオーダービューアー  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる":::
   実験的機能  
:::image-end:::  

新しいアクセシビリティヘルパーは、ソース内の要素の順序を表示します。  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   **ソース注文の表示を**アクティブ化する  
:::image-end:::  

この機能により、web サイトやアプリのスクリーンリーダーとキーボードユーザーの操作性を簡単にテストできます。  スクリーンリーダーとキーボードナビゲーションは、web サイトまたはアプリのソースコードで特定の順序に配置されているコンテンツに依存するため、表示されているページと一致するようになります。  ソースオーダービューアーには、レンダリングされたページとソースコードとの順序が異なる可能性があります。  

この実験的な機能を有効にするには、「 [実験的な機能を][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 有効にする」に移動し、[ **ソースオーダービューアーを有効**にする] の横にあるチェックボックスをオンにします。  

この実験の詳細については、「 [ソースオーダービューアーを有効][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]にする」を参照してください。  

Chromium の問題: [#1094406][CR1094406]  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### [要素] ツールですべての検索結果を強調表示する  

Microsoft Edge 84 および85では、 **要素** パネルの最初の検索結果は強調表示されませんでした。  残りの検索結果が正しく強調表示されました。  

フィードバックを送信して、Chromium の改善に努めていただき、ありがとうございました。  Chromium によって報告される [#1103316][CR1103316] 問題は、オープンソースのプロジェクトにあります。  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   Microsoft Edge 84 以降の **要素** パネルで強調表示された最初の検索結果  
:::image-end:::  

この問題は、Microsoft Edge のすべてのバージョンで修正されました。  

Chromium の問題: [#1103316][CR1103316]  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新しいメディアパネル  

DevTools でメディアプレーヤーの情報が [メディア][DevtoolsMediaPanelIndex] パネルに表示されるようになりました。  

新しい **メディア** パネルを開くには、次の手順を実行します。  

1.  [**カスタマイズと制御 devtools** \ (\)] を選択して、 `...` **その他のツール**  >  **メディア**> します。  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/media-panel.msft.png":::
       新しい **メディア** パネル  
    :::image-end:::  

DevTools の新しい **メディア** パネルの前に、ビデオプレーヤーに関するログとデバッグ情報は [ **最近のプレイヤー** ] の設定の下にありました。  「 **最近** 」のプレイヤーの設定を開くには、「 `edge://media-internals` players ( **プレーヤー** )」タブを選択します。  

ライブコンテンツを表示して、次の例を含む、潜在的な問題をより迅速に検査します。  

*   フレームが削除されるのはなぜですか?  
*   JavaScript が予期しない方法でプレーヤーとやり取りしているのはなぜですか?  

### [要素] パネルのコンテキストメニューを使用したノードのスクリーンショットのキャプチャ  

[ **要素** ] パネルのコンテキストメニューを使って、ノードのスクリーンショットをキャプチャできるようになりました。  

たとえば、目次のスクリーンショットを撮るには、要素をポイントしてコンテキストメニューを開き (\ を右クリックし)、[ **キャプチャノードのスクリーンショット**] を選びます。  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   キャプチャノードのスクリーンショット  
:::image-end:::  

Chromium の問題: [#1100253][CR1100253]  

### 問題ツールの更新プログラム  

**コンソール**パネルの問題の警告バーは、通常のメッセージに置き換えられました。  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   コンソールメッセージの問題  
:::image-end:::  

サードパーティの cookie の問題は、[ **問題** ] ツールで既定で非表示になっています。  [ **サードパーティの cookie の追加の問題** ] チェックボックスをオンにして、問題を表示します。  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   サードパーティの cookie の問題チェックボックス  
:::image-end:::  

Chromium の問題: [1096481][CR1096481]、 [1068116][CR1068116]、 [1080589][CR1080589]  

### 見つからないローカルフォントのエミュレート  

[レンダリングツール][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]を開いて、[新しい**ローカルフォントの無効化**] 機能を使用して、 `local()` ルールに含まれないソースをエミュレートし `@font-face` ます。  

たとえば、デバイスにフォントがインストールされていて、ルールによってフォントとして使用されている場合、 `Rubik` `@font-face src` `local()` Microsoft Edge では、デバイスのローカルフォントファイルが使用されます。  

[ **ローカルフォントを無効** にする] が有効になっている場合、devtools ではフォントが無視され、 `local()` 各ネットワークからの取り出しが行われます。  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/disable-font.msft.png":::
   見つからないローカルフォントのエミュレート  
:::image-end:::  

開発中に同じフォントの2つのコピーを使う場合は、次の例のようにします。  

*   デザインツールのローカルフォント。  
*   コードの web フォント。  

[ **ローカルフォントの無効化** ] を使用して、次の作業を簡単に実行できるようにします。  

*   ロードパフォーマンスと web フォントの最適化をデバッグして計測します。  
*   CSS ルールの精度を確認 `@font-face` します。  
*   デバイスにインストールされているローカルバージョンと web フォントの違いを見つけます。  

Chromium の問題: [#384968][CR384968]  

### アクティブでないユーザーのエミュレート  

[アイドル検出 API][WebDevIdleDetection]を使うと、開発者は非アクティブなユーザーを検出し、アイドル状態の変更を反映することができます。  この時点で、DevTools を使って、 **センサー** ツールでのアイドル状態の変更を、ユーザーの状態と画面の状態の両方に対してエミュレートすることができるようになりました。これは、実際のアイドル状態が変更されるのを待機する必要はありません。  [引き出し][DevtoolsCustomizeIndexDrawer]から**センサー**ツールを開くことができます。  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   アクティブでないユーザーのエミュレート  
:::image-end:::  

Chromium の問題: [#1090802][CR1090802]  

### 割引の優先のエミュレート-データ  

> [!NOTE]
> Microsoft Edge 86 でこの機能を有効にするには、「 `edge://flags#enable-experimental-web-platform-features` 実験的な **Web Platform 機能** 」フラグをオンにして有効にします。  エミュレーションオプションは、フラグが有効になっている場合にのみ表示されます。  

データ削減の [優先][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] メディアクエリは、データを減らしたユーザーのコンテンツ設定を検出します。  選択されている場合、ユーザーは、少ないデータを使用する代替ページコンテンツを受け取ります。  

これで、DevTools を使ってメディアクエリをエミュレートでき `prefers-reduced-data` ます。  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   割引の優先のエミュレート-データ  
:::image-end:::  

Chromium の問題: [#1096068][CR1096068]  

### 新しい JavaScript 機能のサポート  

DevTools では、次の JavaScript 言語機能がサポートされるようになりました。  

| JavaScript 言語機能 | 詳細 |  
|:--- |:--- |  
| [論理代入演算子][V8FeaturesLogicalAssignment] | DevTools は、 `&&=` `||=` `??=` **本体** と **ソース** パネルでの新しい演算子、and 演算子による論理割り当てをサポートするようになりました。  |  
| [数値の区切り記号][V8FeaturesNumericSeparators]を整形して印刷する | DevTools では、[ **ソース** ] パネルで数値の区切り記号が適切に印刷されるようになりました。  |  

Chromium の問題: [1086817][CR1086817]、 [1080569][CR1080569]  

### Lighthouse パネルの Lighthouse 6.2  

**Lighthouse** panel で、Lighthouse 6.2 が実行されています。  すべての変更の一覧については、 [Lighthouse のリリースノート][GithubGooglechromeLighthouseV620]を参照してください。  

Chromium の問題: [#772558][CR772558]  

### [サービス Worker] ウィンドウの他の元のリストの廃止  

DevTools では、[ **サービス作業者** ] ウィンドウからのリンクを提供します。 (**アプリケーション** パネル > [ **サービス作業** ] ウィンドウ \)、他の元からのサービスワーカーの完全な一覧を表示できます。  DevTools を開かずにリストにアクセスするには、に移動 `edge://service-worker-internals/?devtools` します。  

以前の DevTools は、 **アプリケーション** パネル > **Service worker** ] ウィンドウの下に入れ子になっているリストを表示していました。  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   他のオリジンとのリンク  
:::image-end:::  

Chromium の問題: [#807440][CR807440]  

### フィルター処理されたアイテムのカバレッジの概要を表示する  

DevTools は、更新されたカバレッジ情報の概要を動的に表示します。  動的表示は、 [カバレッジ][DevtoolsCoverageIndex] ツールでフィルターが適用されたときにトリガーされます。  **補充**ツールには、常にすべての補充情報の概要が表示されます。  

次の図の最初の図では、最初に概要が表示され、 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` 次の図の2番目に概要が表示され `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` ます。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         カバレッジの概要  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         フィルター処理されたアイテムのカバレッジの概要  
      :::image-end:::  
   :::column-end:::
:::row-end:::

Chromium の問題: [#1061385][CR1090802]  

### アプリケーションパネルの新しいフレームの詳細ビュー  

DevTools には、各フレームの詳細ビューが表示されるようになりました。  このアプリにアクセスするには、**アプリケーション**パネルの**フレーム**メニューの下にあるフレームを選択します。  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/frame-details.msft.png":::
   **アプリケーション**パネルのフレームの新しい詳細表示  
:::image-end:::  

Chromium の問題: [#1093247][CR1093247]  

#### 開いているウィンドウのフレームの詳細  

ウィンドウを開くと、フレームツリーにも表示されるようになりました。  開いているウィンドウの詳細ビューには、追加のセキュリティ情報が含まれます。  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/window-opener.msft.png":::
   開いているウィンドウの新しいフレームの詳細ビュー  
:::image-end:::  

Chromium の問題: [#1107766] [CR1107766]  

#### セキュリティと分離に関する情報  

セキュリティで保護されたコンテキスト、 [クロスオリジン-ポリシー (COEP)][WebDevCoopCoep]、および [クロスオリジン-Opener-ポリシー (co-op)][WebDevCoopCoep] がフレームの詳細に表示されるようになりました。  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/coep-coop.msft.png":::
   セキュリティと分離に関する情報  
:::image-end:::  

今後、Microsoft Edge DevTools チームと Chrome DevTools チームは、フレームの詳細により多くのセキュリティ情報を追加する予定です。  

Chromium の問題: [#1051466][CR1051466]  

### 要素とネットワークパネルの更新  

#### [スタイル] ウィンドウのアクセシビリティに対応した色の候補  

DevTools では、色の低いコントラストのテキストの色の候補が表示されるようになりました。  

次の例で `h1` は、コントラストの低いテキストが設定されています。  修正するには、 `color` [ **スタイル** ] ウィンドウでプロパティのカラーピッカーを開きます。  [ **コントラスト比** ] セクションを展開すると、DEVTOOLS で AA と AAA の色候補が提供されます。  色を適用する色を選択します。  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   色のピッカーで AA と AAA の色候補が提示される  
:::image-end:::  

Chromium の問題: [#1093227][CR1093227]  

#### [要素] パネルの [復元のプロパティ] ウィンドウ  

[ **プロパティ** ] ウィンドウが再び表示されます。  [Microsoft Edge 84 では廃止][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]されました。  Microsoft Edge DevTools チームと Chrome DevTools チームは、要素の検査プロパティの改善を計画しています。  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/properties-pane.msft.png":::
   [**要素**] パネルの [**プロパティ**] ウィンドウ  
:::image-end:::  

Chromium の問題:  <!--  [#1105205][CR1105205],  -->  [#1116085][CR1116085]  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### [スタイル] ウィンドウでのユーザー設定のフォントのオートコンプリート  

`font-family`[**スタイル**] ウィンドウでプロパティを編集すると、インポートされたフォントフェイスが CSS のオートコンプリートの一覧に追加されるようになりました。  

たとえば、 `monospace` カスタムフォントがローカルコンピューターにインストールされている場合は、CSS コンプリートリストに表示されます。 以前のバージョンの Microsoft Edge では、フォントは表示されませんでした。

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   オートコンプリートのカスタムフォント  
:::image-end:::  

Chromium の問題: [#1106221] [CR1106221]  

#### [ネットワーク] パネルでのリソースの種類の一貫した表示  

DevTools では、元のネットワーク要求と同じリソースの種類が一貫して表示されるようになりまし `/ Redirect` た。リダイレクション \ (HTTP 状態コード 302) が発生したときに **type** 列の値が追加されます。  

以前の DevTools によって型が変わる場合がありました `Other` 。  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/network-redirect.msft.png":::
   リダイレクトリソースの種類を表示する  
:::image-end:::  

Chromium の問題: [#997694][CR997694]  

#### 要素とネットワークパネルのボタンをクリアする  

次のテキストボックスには、 **クリア** ボタンが表示されるようになりました。  

*   [ **スタイル** ] ウィンドウと [ **ネットワーク** ] パネルのフィルターテキストボックス。  
*   [ **要素** ] パネルの DOM 検索テキストボックス。  

[ **クリア** ] ボタンを選択して、入力されテキストを削除します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         [ **要素** ] パネルの [クリア] ボタン  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         **ネットワーク**パネルのボタンをクリアする  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

Chromium の問題: [#1067184][CR1067184]  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools の設定アイコン"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "[要素] パネルの [プロパティ] ウィンドウの廃止-DevTools の新機能 (Microsoft Edge 84) |Microsoft ドキュメント"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS grid のデバッグ機能-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "実験的な Api を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "ソース注文ビューアーを有効にする-実験的な機能 |Microsoft ドキュメント"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "エミュレーション: デュアルスクリーンモードのサポート-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "折りたたみ式とデュアルスクリーンデバイスでのテスト-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "実験的な機能を有効にする-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-コンソール API リファレンス |Microsoft ドキュメント"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Microsoft Edge DevTools の [カバレッジ] タブを使用して、使用されていない JavaScript と CSS コードを見つけます。Microsoft ドキュメント"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "ドローワ-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブの [パフォーマンス分析] 参照で、レンダリングのパフォーマンスを分析します。Microsoft ドキュメント"  
[DevtoolsMediaPanelIndex]: /microsoft-edge/devtools-guide-chromium/media-panel/index "メディアプレーヤー情報を表示してデバッグする |Microsoft ドキュメント"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "CSS メディア画面のスパン機能で、デュアルスクリーン検出Microsoft ドキュメント"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーンデバイス用の getWindowSegments JavaScript API |Microsoft ドキュメント"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Windows 用 Visual Studio コードのキーボードショートカット"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "DevTools: キーボードショートカット/キーバインディングのカスタマイズを許可する |Chromium のバグ"
[CR384968]: https://crbug.com/384968 "ローカル () フォントを無視するオプションChromium のバグ"  
[CR772558]: https://crbug.com/772558 "DevTools: 最新バージョンの Lighthouse を更新する |Chromium のバグ"  
[CR807440]: https://crbug.com/807440 "Chrome では、多数の SWs | を使ってロックするChromium のバグ"  
[CR997694]: https://crbug.com/997694 "[ネットワーク] パネルの \ "xhr \" フィルターの下に、302状態の XHR 要求が表示されません。Chromium のバグ"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table ツール"  
[CR1051466]: https://crbug.com/1051466 "DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1054281]: https://crbug.com/1054281 "機能の要求: DevTools では、折りたたみ式とデュアルスクリーンデバイスをエミュレートする必要があります。Chromium のバグ"  
[CR1067184]: https://crbug.com/1067184 "機能の要求: ネットワーク & 要素で [フィルターのクリア] ボタンを > スタイルフィルターの入力 |Chromium のバグ"  
[CR1068116]: https://crbug.com/1068116 "☂出荷問題] パネル |Chromium のバグ"  
[CR1080569]: https://crbug.com/1080569 "acorn は論理代入演算子をサポートしていません |Chromium のバグ"  
[CR1080589]: https://crbug.com/1080589 "サードパーティ/ファーストパーティで問題を分類する |Chromium のバグ"  
[CR1086817]: https://crbug.com/1086817 "acorn では、数字の区切り文字はサポートされません |Chromium のバグ"  
[CR1090802]: https://crbug.com/1090802 "Idle Detection API からのアイドル状態の変更をシミュレートする |Chromium のバグ"  
[CR1093227]: https://crbug.com/1093227 "DevTools: アクセシビリティの高い色を提案する |Chromium のバグ"  
[CR1093247]: https://crbug.com/1093247 "アプリケーションパネルのフレームに関する情報を表示する |Chromium のバグ"  
[CR1094406]: https://crbug.com/1094406 "開発者は、でのソース注文ビューアーの使用を希望 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools: 低優先データメディア機能のエミュレートのサポート |Chromium のバグ"  
[CR1096481]: https://crbug.com/1096481 "バナーの配置の問題 |Chromium のバグ"  
[CR1100253]: https://crbug.com/1100253 "要素のコンテキストメニューで [スクリーンショット] ノードショートカットを追加する |Chromium のバグ"  
[CR1103316]: https://crbug.com/1103316 "要素の検索では、最初の検索結果で resolveNode (テキストを強調表示するなど) はできません。Chromium のバグ"  
[CR1103854]: https://crbug.com/1103854 ""開発者ツール" の非難読化される X-クライアントデータ値Chromium のバグ"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]: https://crbug.com/1106221 "[スタイル] パネルで、[フォントファミリのオートコンプリートにインポートされたフォントを追加します] |Chromium のバグ  
[CR1107766]: https://crbug.com/1107766 "ウィンドウによって生成されたフレームについての情報を表示します。Chromium のバグ  
[CR1115011]: https://crbug.com/1115011 "コンソールからテーブルをコピーするときに、テーブルの構造は保持されません。Chromium のバグ  
[CR1116085]: https://crbug.com/1116085 "DevTools プロパティ検査をもう一度お手元にお寄せください |Chromium のバグ  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "低優先データメディアクエリレベル 5 |W3C CSS ワーキンググループエディターの下書き"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v 6.2.0-GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "プロトコルバッファー |Google 開発者"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy 折りたたみ |Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "論理的な割り当て |V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数値の区切り文字 |V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "Web サイトの作成 \ "クロスオリジン分離" (CO-OP と COEP を使用) |web.xml"  
[WebDevIdleDetection]: https://web.dev/idle-detection "アイドル検出 API を使用して非アクティブなユーザーを検出する |web.xml"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "合成しないアニメーションを避けます。web.xml"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/08/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
