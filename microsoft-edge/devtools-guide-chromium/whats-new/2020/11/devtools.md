---
description: Linux 上の Microsoft Edge、問題ツールの Webhint ヒントの改善、新しいサービス ワーカー デバッグ機能など。
title: DevTools の新機能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 9e4bdfcb3cc32364931894dcb3c857ac6e082809
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313087"
---
# DevTools の新機能 (Microsoft Edge 88)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## Microsoft Edge と Microsoft Edge ドライバーが Linux で利用可能に  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

Microsoft Edge Dev は、Ubuntu、Debian、Fedora、openSUSE の配布でサポートされます。  Microsoft Edge Dev `.deb`または`.rpm`パッケージを [Microsoft Edge Insider サイト][MicrosoftinsiderDownloadPlatformLinux]から直接ダウンロードしてインストールするか、お使いの Linux 配布の標準パッケージ管理ツールを使用します。   

継続的インテグレーションおよび配信 \(CI/CD\) ソリューションで Linux 環境を使用している場合は、Linux でも Microsoft Edge ドライバーを利用できます。  Microsoft Edge ドライバーを使用した Microsoft Edge Dev の自動化を開始する方法については、[Microsoft Edge ドライバーのダウンロードページに移動します][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。  Microsoft Edge ドライバーと共に Microsoft Edge Dev を自動化する方法については、[「テスト オートメーションに WebDriver (Chromium) を使用する」][WebDriverChromiumMain]に移動してください。  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Linux 上の Microsoft Edge の DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   Linux 上の Microsoft Edge の DevTools  
:::image-end:::  

## 問題ツールの Webhint とプラットフォームのヒントの向上  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

オープン ソース ツールである [webhint][WebhintMain]は、Web サイトとローカル Web ページに対してリアルタイムでのフィードバックを提供します。  [Microsoft Edge バージョン 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel] から、[問題][DevtoolsIssuesIndex]ツールで webhint フィードバックを確認できます。  **問題**ツールに表示される問題は、次のカテゴリを追加することで簡単に確認できます。  

*   [アクセシビリティ][WebhintUserGuideHintsAccessibility]  
*   [互換性][WebhintUserGuideHintsCompatibility]  
*   [パフォーマンス][WebhintUserGuideHintsPerformance]  
*   [落とし穴][WebhintUserGuideHintsPitfalls]  
*   [PWA][WebhintUserGuideHintsPwa]  
*   [セキュリティ][WebhintUserGuideHintsSecurity]  
    
新しいチェックボックスを使用して、サードパーティの問題をフィルター処理できます。  フィルター機能を使用すると、サードパーティ製のライブラリや他のソースからのコードに関連した問題を非表示にできます。  

[Webhint][WebhintMain] によって表示される問題を確認するために、**問題**ツールに次の情報が表示されるようになりました。  

*   コード スニペットが改善されました。  
*   他の関連パネルへのリンク。  
*   Web サイトの問題の解決に役立つドキュメントへのリンク。  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="問題ツール" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   **問題** ツール  
:::image-end:::  

## コンポジット レイヤーが 3D ビューに表示される  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Z インデックス値と ドキュメント オブジェクト モデル \(DOM\) と共に、**レイヤー** コンテンツを視覚化できるようになりました。  この機能は、[3D ビュー][Devtools3dViewIndex]と**レイヤー** ツールを頻繁に切り替えることなくデバッグするのに役立ちます。  視覚的なデバッグを総合的に行う目的で、[3D ビューレイヤーと複合レイヤーが結合されました][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ  
:::image-end:::  

## [スタイル] ウィンドウの CSS 変数の定義  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

**[スタイル]** ウィンドウで、[CSS 変数][MdnUsingCssCustomProperties]が各定義に直接リンクされます。  CSS 変数の定義を簡単に表示または変更するには、変数を選択します。  この例では、DevTools は`body`要素の CSS 属性を表示します。  `--theme-body-background`CSS 変数の変数定義を表示するには、次のアクションを実行します。  

1.  **[スタイル]** ウィンドウで、`var(--theme-body-background)`を選択します。  
1.  **[スタイル]** ウィンドウに `--theme-body-background`CSS 変数の定義が表示されます。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="スタイルにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         スタイルにリンクされた CSS 変数  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="スタイル ターゲットにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         スタイル ターゲットにリンクされた CSS 変数  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## サービス ワーカー デバッグの機能強化  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

[ネットワーク ツール](#network-tool)、[アプリケーション ツール](#application-tool)、および[ソース ツール](#sources-tool)の次の新機能は、[PWA][ProgressiveWebAppsChromiumIndex] の構築に役立ちます。  サービス ワーカーのデバッグが困難な場合は、次の機能を使用します。  

要求ルーティングは、サービス ワーカーを経由して実行されるネットワーク要求に基づいて、`startup` と `fetch` イベントを表示します。  タイムラインには、**アプリケーション ツール**または**ネットワーク ツール**からアクセスします。  タイムラインは、サービス ワーカーに問題が発生し、`startup` または `fetch` イベントに何の問題があるかを確信する場合に役立ちます。  

### アプリケーション ツール  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

新しい **[ネットワーク要求]** リンクを使用して、すべてのサービス ワーカー 要求ルーティング情報を表示 します。  サービス ワーカーをデバッグするときに追加のコンテキストを表示するには、次のアクションを実行します。  

1.  **アプリケーション ** > **サービス ワーカー**に移動します。  
1.  **[ネットワーク 要求]**.を選びます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="[サービス ワーカー] ウィンドウから、ネットワーク ツールを開く" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       **[サービス ワーカー]** ウィンドウから、**ネットワーク** ツールを開く
    :::image-end:::  
    
1.  **ネットワーク ツール**が**ドロワー**で開き、サービス ワーカー関連のすべてのネットワーク要求が表示されます。  ネットワーク要求は、`is:service-worker-intercepted` を使用してフィルター処理されます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="ドロワー内のネットワーク ツール" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       **ドロワー**内の**ネットワーク** ツール  
    :::image-end:::
    
1. **ネットワーク** ツールをトップ パネルに戻す場合は、**ドロワー**を閉じます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="ドロワーを閉じて、ネットワーク ツールを返す" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       **ドロワー**を閉じて、**ネットワーク ツール**を返す  
    :::image-end:::  
    
### ネットワーク ツール  

サービス ワーカーを介して実行されるネットワーク要求をデバッグします。  **アプリケーション** ツールからネットワーク要求を開く場合があります。  要求ごとに、DevTools はタイミング ウィンドウに次の情報を[[タイミング]][DevtoolsNetworkReferenceViewTimingBreakdownRequest] ウインドウに表示 します。  

*   ブートストラップの要求の開始と期間。  
*   サービス ワーカーの登録に対する変更。  
*   `fetch`イベント ハンドラーのランタイム。  
*   クライアントを読み込むすべての `fetch` イベントのランタイム。  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="[タイミング] ウィンドウ" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   **[タイミング]** ウィンドウ  
:::image-end:::  

### ソース ツール  

以前のバージョンの Microsoft Edge では、呼び出し履歴の深さのレベルは、サービス ワーカーの JavaScript コードに制限されています。  Microsoft Edge 88 では、呼び出し履歴に、サービス ワーカーを介して実行される要求を行ったイニシエーターが表示されます。  

要求を行ったイニシエーターを見つけるには、サービス ワーカーで JavaScript コードの呼び出し履歴を使用します。  次の図の呼び出し履歴は、サービス ワーカーの JavaScript コードから始まり、元の Web ページ要求への参照を `(index):157` のように表示します。  2 番目の図では、参照が選択され、要求を行ったイニシエーターが開きます。  2 番目の図のイニシエーターは Web ページです。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="service-worker.js ファイルと呼び出し履歴の強調表示要求の発信者" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         `service-worker.js` ファイルと呼び出し履歴の強調表示要求の発信者  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="(インデックス) Web ページは、要求のイニシエーターです" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         `(index)` Web ページは要求のイニシエーターです  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## ネットワーク要求のプロパティ値をコピーする  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

**ネットワーク** ツールで、新しい **[値のコピー]** オプションを使用して、ネットワーク要求のプロパティ値をコピーします。  プロパティ値は、デコードされた JSON 値としてコピーされます。  以前のバージョンの Microsoft Edge では、次のいずれかの操作を使用して値をコピーする必要があります。  

*   テキスト全体を強調表示してコピーします。  
*   必要に応じ、値をグローバル変数として格納し、DevTools [コンソール][DevtoolsConsoleIndex]からコピー します。  
    
プロパティ値をクリップボードにコピーするには、[[書式設定された応答 JSON をクリップボードにコピーする]][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard] に移動します。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1132084][CR1132084] に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="DevTools のプロパティ値をコピーする" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         DevTools のプロパティ値をコピーする  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="Visual Studio Code にプロパティ値を貼り付ける" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         Visual Studio Code にプロパティ値を貼り付ける  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 複数押しのキーボード ショートカットをカスタマイズする  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

[Microsoft Edge バージョン 87 以降][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]では、DevTools でいずれのアクションのキーボード ショートカットもカスタマイズできます。  Microsoft Edge バージョン 88 では、複数押しのキーボード ショートカットを作成できます。  DevTools でアクションのショートカットを設定するには、[[設定][DevtoolsCustomizeIndexSettings] > **の実験**] に移動し、[**キーボード ショートカット エディターを有効にする**] の横にあるチェックボックスをオンにします。  ショートカットのカスタマイズと編集の詳細については、「[キーボード ショートカット エディターの試験的機能を有効にする][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]」に移動します。  

たとえば、赤い強調表示は、[**イベントの記録の開始**] アクション用にカスタマイズされた複数押しの キーボード ショートカットが表示 されます。  Chromium オープン ソース プロジェクトで、この機能に関するリアルタイムの更新を確認するについては、[問題 #174309][CR174309] に移動します。  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="コード キーボード ショートカット" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   複数押しキーボード ショートカット  
:::image-end:::  

## DevTools がブラウザーの言語と一致する  

Microsoft Edge バージョン 87 では、[DevTools の設定][DevtoolsCustomizeIndexSettings]で [**ブラウザーの言語の一致**] 設定をオンにした場合、DevTools はブラウザーの言語と一致しません。  Microsoft Edge バージョン 88 では、[**ブラウザーの言語の一致]** 設定をオンにすると、DevTools はブラウザーの言語と一致します。  **ブラウザーの言語の一致** DevTools 設定の詳細については、[「DevTools 言語設定の変更」][DevtoolsCustomizeLocalization]に移動します。  

:::image type="complex" source="../../media/2020/11/startpage-devtools-settings-japanese.msft.png" alt-text="日本語でのブラウザーの言語の一致 DevTools 設定" lightbox="../../media/2020/11/startpage-devtools-settings-japanese.msft.png":::
   日本語での**ブラウザーの言語の一致** DevTools 設定   
:::image-end:::  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新しい CSS 角度可視化ツール  

DevTools では、CSS 角度デバッグのサポートが向上しました。  ページ上の HTML 要素に CSS 角度が適用されている場合、**[スタイル]** ツールの角度の横に時計アイコンが表示 されます。  クロック オーバーレイを切り替えるには、時計アイコンを選択します。  角度を変更するには、時計の任意の場所を選択するか、または針をドラッグします。  角度の値を変更するには、マウス ショートカットとキーボード ショートカットを使用することもできます。  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1126178][CR1126178] および [1138633][CR1138633]に移動します。  

<!--todo:  add link when css angle clock section exists.  -->  

この例では、次の CSS 角度を使用します。  

```css
background: linear-gradient(100deg, lightblue, pink);
```

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS の角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   CSS の角度  
:::image-end:::  

### [記憶域] ウィンドウで、記憶域クォータのサイズをシミュレートする  

**[記憶域]** ウィンドウで記憶域クォータのサイズを上書きする場合があります。  この機能を使用すると、ディスクの可用性が低いシナリオで、さまざまなデバイスをシミュレートし、Web サイトまたはアプリの動作をテストできます。  記憶域クォータをシミュレートするには、次の操作を実行します。  

1.  **アプリケーション**  > **ストレージ**に移動します。  
1.  **[カスタム ストレージ クォータをシミュレートする]** のチェック ボックスをオンにします。  
1.  有効な数値を入力します。  
    
DevTools でモバイル デバイスや他の機能をエミュレートする方法の詳細については、[「Microsoft Edge DevTools でモバイル デバイスをエミュレートする」][DevtoolsDeviceModeIndex] に移動します。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題[945786][CR945786] および [1146985][CR1146985]に移動します。  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="記憶域クォータのサイズをシミュレートする" lightbox="../../media/2020/11/storage-quota.msft.png":::
   記憶域クォータのサイズをシミュレートする  
:::image-end:::  

### ネットワーク ツールで CORS エラーを報告する  

[「CORS エラー デモ」][GlitchCorsErrors]に移動して、この機能を試してみてください。  **ネットワーク** ツールを開き、ページを更新して、失敗した CORS ネットワーク要求を確認します。  状態の列には、**CORS エラー**が表示されます。  エラーの上にホバーすると、ツールヒントにエラー コードが表示されます。  Microsoft Edge バージョン 87 以前では、DevTools は CORS エラーの一般的な **(失敗)** 状態のみを表示しました。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1141824][CR1141824] に移動します。  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS エラー" lightbox="../../media/2020/11/cors-err.msft.png":::
   CORS エラー  
:::image-end:::  

### フレーム詳細ビューの更新  

#### フレーム詳細ビューのクロスオリジン分離情報  

クロスオリジン分離状態は、**「セキュリティと分離」** セクションに表示されます。  新しい **「API の可用性」** セクションには、`SharedArrayBuffer`s \(SAB\) の可用性と、バッファーを使用して共有できるかどうかが表示されます`postMessage()`。  SAB と `postMessage()` が現在利用可能な場合、非推奨の警告が表示されますが、コンテキストはクロスオリジン分離されていません。  クロスオリジン分離の詳細と、`SharedArrayBuffers`が必要な理由については、[WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated] に移動します。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1139899][CR1139899] に移動します。  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="クロスオリジン情報" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   クロスオリジン情報  
:::image-end:::  

#### フレーム詳細ビューの新しい Web ワーカー情報  

DevTools では、関連する親フレームの下に Web ワーカーが整理されます。  たとえば、`someName` フレームが `worker.js` を作成する場合、`worker.js` が**フレーム** リストの下にある `someName` に表示 されます。  Web ワーカーの詳細を表示するには、次のアクションを実行します。  

1.  **アプリケーション** ツールを開きます。  
1.  Web ワーカーを含むフレームを展開します。  
1.  **[ワーカー]** ツリーを展開します。  
1.  ワーカーを選択します。  
    
Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1122507][CR1122507] および [1051466][CR1051466]に移動します。  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web ワーカー情報" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   Web ワーカー情報  
:::image-end:::  

#### 開いたウィンドウのオープン フレームの詳細を表示する  

DevTools では、関連する親[フレーム][MdnWindowFrames]の下に開いている [Windows][MdnWindowConstructors] が整理 されます。  たとえば、`top` フレームが `Window` を `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` に開く場合は、**フレーム** リストの下の `top` に `Window` が表示されます。  

**要素**ツールで別の Window を開くためのフレームを表示するには、次のアクションを実行します。  

1.  **フレーム** ツリーを開きます。  
1.  **[開いた Windows]** を展開 し、知りたい親フレームの `Window` を選択します。  
1.  **[Opener フレーム]** リンクを選択します。  

どのフレームが別の `Window` を開いたのかについての詳細が表示されます。  **要素**ツールで Opener を表示するには、次のアクションを実行します。  

1.  **フレーム** ツリーを開きます。  
1.  開いているウィンドウを選択して `Window` の詳細を開きます。  
1.  **[Opener フレーム]** リンクを選択します。  
    
Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1107766][CR1107766]に移動します。  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="開いたフレームの詳細" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   開いたフレームの詳細  
:::image-end:::  

### ネットワーク イニシエーターの stacktrace をコピーする  

stacktrace をクリップボードにコピーするには、次のアクションを実行します。  

1.  コンテキスト メニュー \(右クリック\) を開きます。  
1.  **[コピー]** を選んでから、 > **[stacktrace をコピー]** を選びます。  
    
Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1139615][CR1139615] に移動します。

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="stacktrace のコピー" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   stacktrace のコピー  
:::image-end:::  

### マウスオーバー時の Wasm 変数値のプレビュー  

この機能を使用して、コードが一時停止した時に WebAssembly \(Wasm\) 変数の値を確認します。  変数の現在の値を表示するには、変数にホバーします。  Chromium オープン ソース プロジェクトでこの機能のリアルタイム更新を確認するには、問題 [1058836][CR1058836] および [1071432][CR1071432] に移動します。  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="マウスオーバー時の Wasm 変数のプレビュー" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   マウスオーバー時の Wasm 変数のプレビュー  
:::image-end:::  

### ファイルとメモリのサイズに対する一貫した測定単位  

DevTools は、ファイルとメモリのサイズを表示するために、`kB` を常に使用します。  以前の DevTools では、`kB` と `KiB` が混在していました。

*   `kB` またはキロバイト \(10^3 または 1000 バイト\)  
*   `KiB` またはキビバイト \(2^10 または 1024 バイト\)  
    
たとえば、**ネットワーク** ツールは以前`kB` をラベルで使用していましたが、計算には `KiB` を使用していました。  お客様のフィードバックから、この不整合によって混乱が生じることが明らかになりました。  Chromium オープン ソース プロジェクトでこの機能の履歴を確認するには、問題 [1035309][CR1035309] に移動します。  

## Microsoft Edge プレビュー チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、 [既定][MicrosoftEdgePreviewChannels] の開発ブラウザーとして Microsoft Edge プレビュー チャネルの使用を検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D ビュー | Microsoft Docs"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "コンソールの概要 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeLocalization]: /microsoft-edge/devtools-guide-chromium/customize/localization "DevTools の言語設定を変更する | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイル デバイスをエミュレートする | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボード ショートカット エディターを有効にする - 試験的な機能 | microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "3D ビューで複合レイヤーを有効にする - 試験的機能 | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "書式設定された応答 JSON をクリップボードにコピーする - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "要求のタイミング ブレークダウンを表示する - ネットワーク分析リファレンス | Microsoft Docs"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "テスト自動化に WebDriver (Chromium) を使用する | Microsoft Docs"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプログレッシブ Web アプリ | Microsoft Docs"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/10/devtools#customize-keyboard-shortcuts-in-settings "[設定] でキーボード ショートカットをカスタマイズする - DevTools の新機能 (Microsoft Edge 87) | Microsoft Docs"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools#webhint-feedback-in-the-issues-panel "[問題] パネルの webhint フィードバック - DevTools の新機能 (Microsoft Edge 85) | Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver のダウンロード | Microsoft 開発者"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボード ショートカット/キー バインドのカスタマイズを許可する | Chromium のバグ"  
[CR945786]: https://crbug.com/945786 "問題 945786: DevTools: navigator.storage.estimate() の上書きを許可する | Chromium のバグ"  
[CR1029427]: https://crbug.com/1029427 "問題 1029427: フロントエンドでのプロトコル メッセージ ディスパッチのパフォーマンス オーバーヘッドを削減する | Chromium のバグ"  
[CR1035309]: https://crbug.com/1035309 "問題 1035309: DevTools は MB をメビバイトではなくメガバイトという意味で一貫して使用する必要があります | Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での COOP/COEP デバッグのサポート | Chromium のバグ"  
[CR1058836]: https://crbug.com/1058836 "問題 1058836: Wasm のデバッグに関する UX の問題 | Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "問題 1071432: Wasm Basic Developer Experience ☂︝を使用する|Chromium のバグ"  
[CR1107766]: https://crbug.com/1107766 "問題 1107766: 'window.open()' によって生成されたフレームに関する情報をフレーム ツリーに表示する | Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレーム ツリー ビューでの Surface ワーカー情報 | Chromium のバグ"  
[CR1126178]: https://crbug.com/1126178 "問題 1126178: devTools ☂: CSS <タイプ> コンポーネント | Chromium のバグ"  
[CR1130556]: https://crbug.com/1130556 "問題 1130556: DevTools: テスト イメージのフォールバック (エミュレーション) | Chromium のバグ"  
[CR1132084]: https://crbug.com/1132084 "問題 1132084: JSON 要求ペイロードを簡単にコピーする方法がない | Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox ツール | Chromium のバグ"  
[CR1138633]: https://crbug.com/1138633 "問題 1138633: DevTools: CSS <角度> コンポーネントが、時計の背景にあるプロパティの外観を反射している必要がある |Chromium のバグ"  
[CR1139615]: https://crbug.com/1139615 "問題 1139615: ネットワーク イニシエーターがスタック トレースをコピーする機能を提供する必要がある | Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレーム詳細ビューでゲート API の可用性を報告する | Chromium のバグ"  
[CR1139945]: https://crbug.com/1139945 "問題 1139945: [スタイル] パネルの flexbox CSS プロパティのアイコン | Chromium のバグ"  
[CR1141824]: https://crbug.com/1141824 "問題 1141824: DevTools で CORS エラー報告を改善する | Chromium のバグ"  
[CR1144090]: https://crbug.com/1144090 "問題 1144090: 要素ツリーに柔軟なスタイルの装飾を追加する | Chromium のバグ"  
[CR1146985]: https://crbug.com/1146985 "問題 1146985: 「Dev Tools」ウィンドウの「ストレージ」セクションのテキスト ボックスに、クリアされたテキストが表示される | Chromium のバグ"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS エラー | Glitch"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "クロスオリジン リソース共有 (CORS) | MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタム プロパティ (変数) を使用する |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "コンストラクター - Window | MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "Window.frames |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope.crossOriginIsolated | MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "アクセシビリティ | webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "互換性 | webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "パフォーマンス | webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "落とし穴 | webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA | webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "セキュリティ | webhint"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/updates/2020/11/devtools/index)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
