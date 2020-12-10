---
description: Linux の Microsoft Edge、問題ツールの web ヒントのヒント、新しいサービスワーカーのデバッグ機能などが改善されました。
title: DevTools の新機能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 500b64e7b51e0f02c9fcbcb7a83e8273b3a5a0d7
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11205244"
---
# DevTools の新機能 (Microsoft Edge 88)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## Microsoft Edge および Microsoft Edge ドライバーが Linux で利用できるようになりました  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

Microsoft Edge Dev は、Ubuntu、Debian、Fedora、openSUSE の配布でサポートされるようになりました。  Microsoft edge の開発者 `.deb` または `.rpm` パッケージを [microsoft edge Insider サイト][MicrosoftinsiderDownloadPlatformLinux] から直接ダウンロードしてインストールするか、またはお使いの Linux ディストリビューションの標準パッケージ管理ツールを使用します。  

継続的インテグレーションと配信 \ (CI/CD \) ソリューションで Linux 環境を使用している場合は、Microsoft Edge ドライバーも Linux で利用できます。  Microsoft edge ドライバーを使用した Microsoft Edge の開発を開始するには、 [Microsoft Edge ドライバーのダウンロードページ][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]に移動します。  Microsoft edge ドライバーと共に Microsoft edge Dev を自動化する方法については、「 [WebDriver (Chromium) を使ってテストオートメーションを使用][WebDriverChromiumMain]する」を参照してください。  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Linux での Microsoft Edge の DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   Linux での Microsoft Edge の DevTools  
:::image-end:::  

## 問題解決ツールの web ヒントとプラットフォームのヒントの改善  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

オープンソースツールである web [ヒント][WebhintMain]は、web サイトやローカル web ページについてリアルタイムでフィードバックを提供します。  [Microsoft Edge バージョン 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]以降では、[[問題][DevtoolsIssuesIndex]] ツールの webhint のフィードバックを確認します。  **懸案事項**ツールに表示される問題は、次のカテゴリを追加することで簡単に確認できるようになりました。  

*   [アクセシビリティ][WebhintUserGuideHintsAccessibility]  
*   [互換性][WebhintUserGuideHintsCompatibility]  
*   [パフォーマンス][WebhintUserGuideHintsPerformance]  
*   [Pitfalls][WebhintUserGuideHintsPitfalls]  
*   [PWA][WebhintUserGuideHintsPwa]  
*   [セキュリティ][WebhintUserGuideHintsSecurity]  
    
これで、新しいチェックボックスを使ってサードパーティの問題をフィルター処理できるようになりました。  フィルター機能を使用すると、サードパーティのライブラリやその他のソースからのコードに関連する問題を非表示にすることができます。  

[Webhint][WebhintMain]によって発生した問題を確認するために、**問題**ツールには次の情報が表示されるようになりました。  

*   改善されたコードスニペット。  
*   他の関連パネルへのリンク。  
*   Web サイトの問題を解決するのに役立つドキュメントへのリンクです。  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="問題ツール" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   **問題** ツール  
:::image-end:::  

## 合成レイヤーが3D ビューに表示されるようになりました  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

これで、 **レイヤー** コンテンツと、z インデックス値、ドキュメントオブジェクトモデル \ (DOM \) を視覚化することができるようになりました。  この機能により、 [3d ビュー][Devtools3dViewIndex] と **レイヤー** ツールを頻繁に切り替えることなく、デバッグを行うことができます。  包括的なビジュアルデバッグエクスペリエンスを実現するために、 [3D ビューレイヤーと合成レイヤーが結合されました][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="合成レイヤーウィンドウ" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   **合成レイヤー** ウィンドウ  
:::image-end:::  

## [スタイル] ウィンドウの CSS 変数の定義  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

[ **スタイル** ] ウィンドウで、 [CSS 変数][MdnUsingCssCustomProperties] が各定義に直接リンクされるようになりました。  変数を選択して、CSS 変数定義を簡単に表示したり、変更したりします。  この例では、DevTools に要素の CSS 属性が表示されて `body` います。  CSS 変数の変数定義を表示するには `--theme-body-background` 、次の操作を実行します。  

1.  [ **スタイル** ] ウィンドウで、を選択し `var(--theme-body-background)` ます。  
1.  [ **スタイル** ] ウィンドウに、CSS 変数の定義が表示されるようになりました `--theme-body-background` 。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="スタイルにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         スタイルにリンクされた CSS 変数  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="Style ターゲットにリンクされた CSS 変数" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         Style ターゲットにリンクされた CSS 変数  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## サービスワーカーのデバッグ機能の改善  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

[ネットワーク](#network-tool)、[アプリケーション](#application-tool)、[ソース](#sources-tool)の各ツールの次の新機能を使うと、 [PWA][ProgressiveWebAppsChromiumIndex]を構築することができます。  サービスワーカーのデバッグが困難な場合は、次の機能を使用します。  

[ルーティングの要求] は、 `startup` `fetch` サービスワーカーによって実行されるネットワーク要求に基づいて、およびイベントを表示します。  タイムラインには、 **アプリケーション** または **ネットワーク** ツールからアクセスできます。  タイムラインは、service worker の問題が発生していて、or イベントに何らかの問題があるかどうかを確認したい場合に役立ち `startup` `fetch` ます。  

### アプリケーションツール  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

[新しい **ネットワーク要求** ] リンクを使用して、すべてのサービスワーカー要求ルーティング情報を表示します。  サービスワーカーのデバッグ時に追加のコンテキストを表示するには、次の操作を実行します。  

1.  **アプリケーション**サービスの担当  >  **者**に移動します。  
1.  [ **ネットワーク要求**] を選びます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="[Service Worker] ウィンドウからネットワークツールを開く" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       [ **Service worker** ] ウィンドウから**ネットワーク**ツールを開く
    :::image-end:::  
    
1.  [ **ネットワーク** ] ツールが **引き出し** で開き、すべてのサービスワーカー関連のネットワーク要求が表示されます。  ネットワーク要求は、を使ってフィルター処理され `is:service-worker-intercepted` ます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="ドロアーのネットワークツール" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       **ドロアー**の**ネットワーク**ツール  
    :::image-end:::
    
1. **ネットワーク**ツールを上のパネルに戻すには、**引き出し**を閉じます。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="ネットワークツールを戻すには、[引き出し] を閉じます。" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       **ネットワーク**ツールを戻すには、[**引き出し**] を閉じます。  
    :::image-end:::  
    
### ネットワークツール  

サービスワーカーを通じて実行されるネットワーク要求をデバッグします。  また、 **アプリケーション** ツールからネットワーク要求を開くこともできます。  各要求について、DevTools では、[ [タイミング][DevtoolsNetworkReferenceViewTimingBreakdownRequest] ] ウィンドウに次の情報が表示されます。  

*   要求の開始とブートストラップの期間。  
*   サービスワーカー登録の変更。  
*   イベントハンドラーの実行時 `fetch` 。  
*   `fetch`クライアントを読み込むすべてのイベントのランタイム。  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="タイミングウィンドウ" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   **タイミング** ウィンドウ  
:::image-end:::  

### ソースツール  

以前のバージョンの Microsoft Edge では、コールスタックの深度レベルは、サービスワーカーの JavaScript コードに制限されていました。  Microsoft Edge 88 では、呼び出し履歴にサービスワーカーを通じて実行される要求のイニシエーターが表示されるようになりました。  

要求のイニシエーターを見つけるには、サービスワーカーの JavaScript コードのコールスタックを使用します。  次の図のコールスタックは、サービスワーカーの JavaScript コードから始まり、元の web ページの要求としての参照を表示し `(index):157` ます。  2番目の図では、参照が選択され、要求を行ったイニシエーターが開かれています。  2番目の図のイニシエーターは web ページです。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="要求元の service-worker.js ファイルとコールスタックの強調表示" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         要求の送信 `service-worker.js` 元を強調表示したファイルとコールスタック  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="(インデックス) web ページが要求の開始者である" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         `(index)`Web ページが要求の開始者である  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## ネットワーク要求のプロパティ値をコピーする  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

[ **ネットワーク** ツール] で、[新しい **値のコピー** ] オプションを使用して、ネットワーク要求のプロパティの値をコピーします。  プロパティ値はデコードされた JSON 値としてコピーされます。  以前のバージョンの Microsoft Edge では、次のいずれかのアクションを使用して値をコピーする必要がありました。  

*   テキスト全体を強調表示してコピーします。  
*   該当する場合はグローバル変数として値を保存し、DevTools [コンソール][DevtoolsConsoleIndex]からコピーします。  
    
プロパティの値をクリップボードにコピーするには、[ [書式設定された応答 JSON をクリップボードにコピー][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]] に移動します。  Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1132084][CR1132084]」に移動します。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="DevTools でのプロパティ値のコピー" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         DevTools でのプロパティ値のコピー  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="Visual Studio コードでのプロパティ値の貼り付け" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         Visual Studio コードでのプロパティ値の貼り付け  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## マルチキーボードショートカットをカスタマイズする  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

[Microsoft Edge バージョン87以降][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]では、devtools で操作のキーボードショートカットをカスタマイズすることができます。  Microsoft Edge バージョン88では、複数のキーボードショートカットを作成できるようになりました。  Devtools で操作のショートカットを設定するには、[[設定][DevtoolsCustomizeIndexSettings]の試験] に移動  >  **** し、[**キーボードショートカットエディターを有効**にする] の横にあるチェックボックスをオンにします。  ショートカットのカスタマイズと編集について詳しくは、「 [キーボードショートカットエディターの実験的機能を有効][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]にする」を参照してください。  

たとえば、赤色の強調表示は、[記録して **イベントを開始** ] アクション用にカスタマイズされた複数のキーボードショートカットを示しています。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[ [問題の #174309][CR174309]] に移動します。  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="弦のショートカットキー" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   複数のキーボードショートカットを使用する  
:::image-end:::  

## Chromium プロジェクトからのお知らせ  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新しい CSS アングル視覚エフェクトツール  

DevTools で CSS アングルデバッギングのサポートが強化されました。  ページの HTML 要素に CSS アングルが適用されている場合、 **スタイル** ツールの角度の横に時計アイコンが表示されます。  時計のオーバーレイを切り替えるには、時計アイコンを選びます。  角度を変更するには、時計の任意の場所を選ぶか、または針をドラッグします。  [角度] の値を変更するには、マウスとキーボードのショートカットを使うこともできます。  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1126178][CR1126178] および [1138633][CR1138633]] に移動します。  

<!--todo:  add link when css angle clock section exists.  -->  

この例では、次の CSS アングルが使われています。  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS アングル" lightbox="../../media/2020/11/css-angle.msft.png":::
   CSS アングル  
:::image-end:::  

### [記憶域] ウィンドウで記憶域のクォータサイズをシミュレートする  

**ストレージ**ウィンドウでストレージのクォータサイズを上書きできるようになりました。  この機能により、さまざまなデバイスをシミュレートし、ディスク可用性の低いシナリオで web サイトやアプリの動作をテストすることができます。  記憶域のクォータをシミュレートするには、次の操作を実行します。  

1.  **アプリケーション**  >  **ストレージ**に移動します。  
1.  [ **カスタム記憶域クォータのシミュレート** ] チェックボックスをオンにします。  
1.  有効な番号を入力してください。  
    
モバイルデバイスやその他の機能を開発ツールでエミュレートする方法の詳細については、「 [Microsoft Edge DevTools でモバイルデバイスをエミュレートする」 ][DevtoolsDeviceModeIndex]を参照してください。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [945786][CR945786] および [1146985][CR1146985]] に移動します。  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="記憶域のクォータサイズのシミュレート" lightbox="../../media/2020/11/storage-quota.msft.png":::
   記憶域のクォータサイズのシミュレート  
:::image-end:::  

### ネットワークツールで CORS エラーを報告する  

この機能を試すには、「 [CORS エラーデモ][GlitchCorsErrors]」に移動します。  **ネットワーク**ツールを開き、ページを更新して、失敗した CORS ネットワーク要求を確認します。  [状態の列には、 **CORS エラー**が表示されます。  エラーをポイントすると、ヒントにエラーコードが表示されるようになりました。  Microsoft Edge バージョン87以前の DevTools では、CORS エラーの一般的な (失敗した) 状態しか表示され **ませんでした** 。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[問題 [1141824][CR1141824]] に移動します。  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS エラー" lightbox="../../media/2020/11/cors-err.msft.png":::
   CORS エラー  
:::image-end:::  

### フレームの詳細ビューの更新  

#### フレームの詳細表示のクロスオリジンの分離情報  

[ **セキュリティ & 分離** ] セクションの下に、クロスオリジン分離ステータスが表示されるようになりました。  [新しい **API の可用性** ] セクションには、 `SharedArrayBuffer` s \ (sab \) の空き時間と、バッファーを使用して共有できるかどうかが表示され `postMessage()` ます。  非推奨警告は、SAB と現在利用可能な場合に表示され `postMessage()` ますが、コンテキストはクロスオリジン分離されません。  クロスオリジン分離およびそのような機能に必要な理由の詳細については `SharedArrayBuffers` 、「 [WindowOrWorkerGlobalScope][MdnWindoworworkerglobalscopeCrossoriginisolated]」を参照してください。  Chromium のオープンソースプロジェクトでこの機能のリアルタイムの更新を確認するには、「案件 [1139899][CR1139899]」に移動します。  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="Cross-origin 情報" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   Cross-origin 情報  
:::image-end:::  

#### フレームの詳細表示の新しい Web ワーカー情報  

DevTools は、web ワーカーを関連する親フレームの下に整理するようになりました。  たとえば、フレームで作成された場合は、 `someName` `worker.js` `worker.js` [フレーム] の一覧の下に表示され `someName` ます。 ****  Web worker の詳細を表示するには、次の操作を実行します。  

1.  **アプリケーション**ツールを開きます。  
1.  Web ワーカーを含むフレームを展開します。  
1.  [ **社員** ] ツリーを展開します。  
1.  作業者を選択します。  
    
Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1122507][CR1122507] および [1051466][CR1051466]] に移動します。  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web ワーカー情報" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   Web ワーカー情報  
:::image-end:::  

#### 開いているウィンドウの opener フレームの詳細を表示する  

DevTools では、開いている [ウィンドウ][MdnWindowConstructors] が関連する親 [フレーム][MdnWindowFrames]の下に表示されるようになりました。  たとえば、 `top` フレームで `Window` をクリックすると、[ `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` `Window` フレーム] の一覧の下に表示され `top` ます。 ****  

[ **要素** ] ツールで別のウィンドウを開くためのフレームを表示するには、次の操作を実行します。  

1.  [ **フレーム** ] ツリーを開きます。  
1.  [ **開い** ているウィンドウ] を展開し、 `Window` 確認したい親フレームのを選びます。  
1.  [ **Opener Frame** ] リンクを選びます。  

詳細は、別のフレームを開くフレームについて表示され `Window` ます。  **Elements**ツールで opener を表示するには、次の操作を実行します。  

1.  [ **フレーム** ] ツリーを開きます。  
1.  開いているウィンドウを選択して詳細を表示し `Window` ます。  
1.  [ **Opener Frame** ] リンクを選びます。  
    
Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1107766][CR1107766]」に移動します。  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="開いているフレームの詳細" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   開いているフレームの詳細  
:::image-end:::  

### ネットワークイニシエーターの stacktrace をコピーする  

Stacktrace をクリップボードにコピーするには、次の操作を実行します。  

1.  コンテキストメニューを開きます (\ [\] を右クリックします)。  
1.  [ **Copy**  >  **copy stacktrace**] を選びます。  
    
Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1139615][CR1139615]」に移動します。

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="Stacktrace をコピーする" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   Stacktrace をコピーする  
:::image-end:::  

### マウスを置いたときの Wasm 変数値のプレビュー  

この機能を使用すると、コードが一時停止されているときに、(Wasm \) 変数の値を確認することができます。  変数の現在の値を表示するには、変数をポイントします。  Chromium のオープンソースプロジェクトでこの機能に関するリアルタイムの更新を確認するには、[懸案事項 [1058836][CR1058836] および [1071432][CR1071432]] に移動します。  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="マウスの上に表示される Wasm 変数のプレビュー" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   マウスの上に表示される Wasm 変数のプレビュー  
:::image-end:::  

### ファイルとメモリのサイズの一定の測定単位  

DevTools `kB` は、ファイルとメモリのサイズを表示するために一貫して使用されるようになりました。  以前の DevTools `kB` と `KiB` の混在。

*   `kB` またはキロバイト \ (10 ^ 3 または1000バイト)  
*   `KiB` または kibibyte \ (2 ^ 10 または1024バイト)  
    
たとえば、以前は**** ラベルで使用した `kB` が、計算に使用されたネットワークツールなどです `KiB` 。  この不整合により混乱が生じたことがフィードバックに示されました。  Chromium のオープンソースプロジェクトでこの機能の履歴を確認するには、「案件 [1035309][CR1035309]」に移動します。  

## Microsoft Edge preview チャネルをダウンロードする  

Windows、Linux、または macOS を使用している場合は、既定の開発ブラウザーとして [Microsoft Edge preview channels] [MicrosoftEdgePreviewChannels] を使うことを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D ビュー |Microsoft ドキュメント"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "本体の概要 |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Microsoft Edge DevTools でモバイルデバイスをエミュレートする |Microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "キーボードショートカットエディターを有効にする-実験的な機能 |microsoft ドキュメント"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "3D ビューでの合成レイヤーの有効化-実験的な機能 |Microsoft ドキュメント"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "書式設定された応答の JSON をクリップボードにコピーする-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "要求のタイミングの内訳を表示する-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "テストオートメーションに WebDriver (Chromium) を使います。Microsoft ドキュメント"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/10/devtools#customize-keyboard-shortcuts-in-settings "設定のショートカットキーをカスタマイズする-DevTools の新機能 (Microsoft Edge 87) |Microsoft ドキュメント"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools#webhint-feedback-in-the-issues-panel "[問題] パネルでの webhint のフィードバック-DevTools の新機能 (Microsoft Edge 85) |Microsoft ドキュメント"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver をダウンロード |Microsoft 開発者"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "Microsoft Edge Insider チャネルをダウンロードする"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium のバグ"  

[CR174309]: https://crbug.com/174309 "問題 174309: DevTools: キーボードショートカットとキーバインディングのカスタマイズを許可する |Chromium のバグ"  
[CR945786]: https://crbug.com/945786 "問題 945786: DevTools: 「ナビゲーターの上書きを許可する」の推定 () |Chromium のバグ"  
[CR1029427]: https://crbug.com/1029427 "問題 1029427: フロントエンドでのプロトコルメッセージディスパッチのパフォーマンスのオーバーヘッドを削減する |Chromium のバグ"  
[CR1035309]: https://crbug.com/1035309 "問題 1035309: DevTools では、mebibyte ではなく、MB を平均して MB を使用する必要があります。Chromium のバグ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での CO-OP/COEP のデバッグのサポート |Chromium のバグ"  
[CR1058836]: https://crbug.com/1058836 "問題 1058836: Wasm のデバッグに関する UX の問題 |Chromium のバグ"  
[CR1071432]: https://crbug.com/1071432 "問題 1071432: ☂️ Wasm Basic 開発者エクスペリエンス |Chromium のバグ"  
[CR1107766]: https://crbug.com/1107766 "問題 1107766: 「window. open ()」 (frame tree) で生成されたフレームについての情報を表示する |Chromium のバグ"  
[CR1122507]: https://crbug.com/1122507 "問題 1122507: フレームツリービューでの Surface worker 情報 |Chromium のバグ"  
[CR1126178]: https://crbug.com/1126178 "問題 1126178: ☂ DevTools: CSS <種類> コンポーネントを入力します。Chromium のバグ"  
[CR1130556]: https://crbug.com/1130556 "問題 1130556: DevTools: テストイメージフォールバック (エミュレーション) |Chromium のバグ"  
[CR1132084]: https://crbug.com/1132084 "問題 1132084: JSON 要求ペイロードを簡単にコピーする方法はありません |Chromium のバグ"  
[CR1136394]: https://crbug.com/1136394 "問題 1136394: Flexbox のツール |Chromium のバグ"  
[CR1138633]: https://crbug.com/1138633 "問題 1138633: DevTools: CSS <angle> component は、時計の背景に存在するプロパティの外観を反映する必要があります。Chromium のバグ"  
[CR1139615]: https://crbug.com/1139615 "問題 1139615: ネットワークイニシエーターは、スタックトレースをコピーする機能を提供する必要があります。 |Chromium のバグ"  
[CR1139899]: https://crbug.com/1139899 "問題 1139899: フレームの詳細表示でのゲート API の可用性レポート |Chromium のバグ"  
[CR1139945]: https://crbug.com/1139945 "問題 1139945: [スタイル] パネルでの flexbox CSS プロパティのアイコン |Chromium のバグ"  
[CR1141824]: https://crbug.com/1141824 "問題 1141824: DevTools で CORS のエラー報告を改善するChromium のバグ"  
[CR1144090]: https://crbug.com/1144090 "問題 1144090: 柔軟なスタイルの装飾を要素ツリーに追加する |Chromium のバグ"  
[CR1146985]: https://crbug.com/1146985 "問題 1146985: クリアテキストは、「Dev Tools」ウィンドウの「ストレージ」セクションのテキストボックスに引き続き表示されます。Chromium のバグ"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS のエラー |故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "クロスオリジンリソース共有 (CORS) |MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "CSS カスタムプロパティ (変数) を使用する |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "コンストラクター-Window |MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "ウィンドウ。フレーム |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope の分離 |MDN"  

[WebhintMain]: https://webhint.io "web ヒント"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "アクセシビリティ |web ヒント"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "互換性 |web ヒント"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "パフォーマンス |web ヒント"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "落とし穴 |web ヒント"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA |web ヒント"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "セキュリティ |web ヒント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/11/devtools/index) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
