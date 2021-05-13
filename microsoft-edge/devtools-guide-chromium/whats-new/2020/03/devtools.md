---
description: 色覚の欠陥をエミュレートする、コマンド メニューで左にドッキングする、など。
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e5fa4b066e47b0779fcdf2b3e814c598e9615ccf
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564953"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-83"></a>DevTools の新機能 (Microsoft Edge 83)  

更新されたスケジュールにChromium、今後のリリースのスケジュールを調整し、Microsoft Edge 82 リリースMicrosoft Edgeキャンセルします。 詳細については、 [ブログの][WindowsBlogStableRelease] 投稿をご覧ください。  

83 の DevTools で利用できる新機能を次にMicrosoft Edgeします。  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームからのもので、見落としがあった可能性のあるお知らせの一覧を示します。  DevTools、コード拡張機能、その他の新機能を試Microsoft Visual Studioお知らせをご覧ください。  開発者ツールのすべての最新および最大の機能を最新の情報に更新するには、プレビュー チャネルMicrosoft Edge[][MicrosoftEdgePreviewChannels]ダウンロードし[、Twitter][EdgeDevToolsTwitterAccount]でフォローしてください。  

### <a name="remotely-debug-microsoft-edge-on-windows-10-devices"></a>デバイスでリモートMicrosoft EdgeデバッグWindows 10する  

[\(Beta\)][RemoteTools]アプリMicrosoft Edgeリモート ツールは、このアプリで使用[Microsoft Store。][MicrosoftStore]  Windows デバイス ポータルを拡張するこのアプリを使用すると、開発マシンで実行されている[Microsoft Edge][WindowsUwpDebugTestPerfDevicePortal]のインスタンスからリモート Windows 10 デバイスに接続し、ターゲット \(Microsoft Edge のすべてのタブと Windows 10 デバイスで開いている[PWAs][ProgressiveWebAppsChromiumIndex]の一覧を表示し、リモート Windows 10 デバイスで実行されているターゲットに対して開発マシンで DevTools を使用できます。  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="アプリで使用Microsoft Edge (Beta) アプリのリモート Microsoft Store" lightbox="../../media/2020/03/remote-tools.msft.png":::
   アプリ[で使用Microsoft Edge (Beta)][RemoteTools]アプリのリモート[Microsoft Store][MicrosoftStore]  
:::image-end:::  

[リモート デバッグ用にデバイス][DevtoolsRemoteDebuggingWindows]とWindows 10コンピューターをセットアップする方法については、このガイドをご覧ください。  フィードバックの送信アイコンをツイートまたは選択して、[][PostTweetEdgeDevTools]リモート デバッグ エクスペリエンスについて[お知](#getting-in-touch-with-microsoft-edge-devtools-team)らせします。  

### <a name="new-ways-to-access-settings"></a>新しいアクセス方法設定  

DevTools には、DevTools の外観、使い方、作業を必要な方法でカスタマイズできる数多くの設定があります。 83 Microsoft Edgeでは、DevTools[設定にアクセス][DevtoolsCustomizeIndexSettings]する方がずっと簡単になりました。  [コンソール設定メイン メニュー] の横にある歯車アイコンを使用して、このアイコンを開きます。  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="歯車アイコンが DevTools 設定開きます" lightbox="../../media/2020/03/settings.msft.png":::
   歯車アイコンが DevTools**設定**開きます  
:::image-end:::  

[その他のツール] の[設定][DevtoolsCustomizeIndexSettings]メニューからファイル**を****開くすることもできます**。

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="メイン メニュー > その他の> 設定" lightbox="../../media/2020/03/settings2.msft.png":::
   **メイン メニュー**  > **その他のツール**  > **設定**  
:::image-end:::  

Chromium[問題#1050855][CR1050855]

### <a name="new-and-improved-infobars"></a>新しい情報バーと改善された情報バー

DevTools の情報通知バー \(infobars\) の外観が改善され、機能が強化されました。 83 Microsoft Edgeでは、infobars の方が読みやすく、ボタンを提供し、関連するアクションを簡単に実行できます。  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="83 でファイルを美しい印刷用の infobar Microsoft Edge 83" lightbox="../../media/2020/03/infobar.msft.png":::
   バージョン 83 でファイルをかなり印刷Microsoft Edge Infobar  
:::image-end:::  

Chromium[問題#1056348][CR1056348]

### <a name="navigate-the-color-picker-with-your-keyboard"></a>キーボードでカラー ピッカーを移動する  

Color [Picker は][DevtoolsCssReferenceColorPicker] 、変更と宣言を [行う要素パネル][DevtoolsCssIndex] `color` の GUI `background-color` です。  以前のバージョンの Microsoft Edgeでは、キーボードを使用してカラー ピッカーの****[網掛け][セクションを][DevtoolsCssReferenceColorPicker]移動する必要が生じていました。  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="これで、キーボードを使用して、カラー ピッカーの [網掛け] セクションでセレクターを移動できます。" lightbox="../../media/2020/03/color-picker.msft.png":::
   これで、キーボードを使用して、カラー ピッカーの [ **網** 掛け] セクションでセレクターを [移動できます。][DevtoolsCssReferenceColorPicker]  
:::image-end:::  

83 Microsoft Edgeでは、キーボードを使用して、カラー ピッカーの [網掛け]**** セクションでセレクターを移動できます。  

Chromium[の問題][CR963183]#963183  

### <a name="properties-tab-now-populates-after-a-page-refresh"></a>ページの更新後に [プロパティ] タブが設定される  

81 Microsoft Edge以前のバージョンでは、[要素****] パネルの[][DevtoolsCssIndex][プロパティ] タブがページ更新によって壊れています。  ページを更新すると、[プロパティ] **タブに** 現在選択されている要素のプロパティが設定されません。  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="81 Microsoft Edge以前のバージョンでは、ページの更新後に [プロパティ] タブが空白でした" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   81 Microsoft Edge以前のバージョンでは、ページの更新**後**に [プロパティ] タブが空白でした  
:::image-end:::  

83 Microsoft Edgeページ更新後に、現在選択されている要素のプロパティを [プロパティ] タブに**表示できます**。  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="83 Microsoft Edge、[プロパティ] タブには、ページ更新後に現在選択されている要素のプロパティが表示されます。" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   83 Microsoft Edge、[プロパティ] タブ**** には、ページ更新後に現在選択されている要素のプロパティが表示されます。  
:::image-end:::  

Chromium[問題#1050999][CR1050999]  

### <a name="use-the-arrow-keys-to-scroll-in-the-changes-tool"></a>[変更] ツールで矢印キーを使用してスクロールする  

[ **変更] ツール** は、DevTools で CSS または JavaScript に加えた変更を追跡します。  [変更] ツールを **使用すると** 、すべての変更をすばやく表示し、エディター/IDE に戻します。  

[変更] ツール**を開く**には `Ctrl` + `Shift` + `P` 、DevTools で選択してコマンド メニュー[を開き、と][DevtoolsCommandMenuIndex]入力します `changes` 。  [変更の表示]**コマンドを**選択して**** 実行して、DevTools ドロワーで [変更] ツールを開きます。  

ファイルを変更すると、[変更] ツールを使用すると、**** 水平方向にスクロールして、すべてのコードを表示できます。  83 Microsoft Edgeから、キーボードの矢印キーを使用して水平方向にスクロールできます。  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="83 Microsoft Edgeでは、矢印キーを使用して水平方向にスクロールして、変更ツールにコードを表示できます。" lightbox="../../media/2020/03/changes.msft.png":::
   83 Microsoft Edgeでは、矢印キーを使用して水平方向にスクロールして、変更ツールでコードの変更を表示**できます**。  
:::image-end:::  

スクリーン リーダーまたはキーボードを使用して DevTools の周りを移動する場合は[][PostTweetEdgeDevTools]、フィードバックの送信アイコンをツイートするか、フィードバックの送信アイコンを選択してフィードバック[を送信](#getting-in-touch-with-microsoft-edge-devtools-team)してください。  

Chromium[の問題][CR963183]#963183  

## <a name="announcements-from-the-chromium-project"></a>Chromium プロジェクトからのお知らせ  

次のセクションでは、Microsoft Edge 83 で利用可能な追加の機能についてChromiumします。  

### <a name="emulate-vision-deficiencies"></a>視覚欠陥をエミュレートする  

[レンダリング [] タブを][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTool] 開き、新しい **エミュレート** ビジョンの欠陥機能を使用して、さまざまな種類のビジョンの欠陥を持つユーザーがサイトをどのように経験するのかについて、より良いアイデアを得る。  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ぼやけたビジョンの画像を表示する" lightbox="../../media/2020/03/vision.msft.png":::
   ぼやけたビジョンの画像を表示する  
:::image-end:::  

DevTools は、ぼやけたビジョンと次の種類のカラー ビジョンの欠陥 [をエミュレートできます][ColorBlindnessTypes]。  

| カラー ビジョンの不足 | 詳細 |  
|:--- |:--- |  
| Protanopia | 赤い光を認識しきれない。 |  
| Deuteranopia | 緑色の光を認識しきれない。 |  
| トリタニア | 青い光を認識しきれな |  
| アクロマトプシア | 灰色 \(極めてまれな\) の色合いを除き、色を認識することの困難。 |  

これらの色覚の欠陥の極端なバージョンは少なく、実際にはより一般的です。  
たとえば、protanomaly は赤色光に対する感度の低下です (protanopia とは対照的に、赤い光を認識する完全な機能がなくなります)。 しかし、 **これらの -omaly** ビジョンの欠陥は、明確に定義されているわけではありません。このような視力不足を持つすべての人は異なって、物事が異なって見える場合があります\(関連する色のより多く/より少なく認識できる\)。  

DevTools のより極端なシミュレーションを設計することで、Web アプリは、protanomaly、deuteranomaly、tritanomaly、および achromatomaly を持つユーザーにもアクセスできます。  

[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium[の問題][CR1003700]#1003700  

### <a name="emulate-locales"></a>ローカルをエミュレートする  

Sensors Location で場所を設定して、**ローカルをエミュレート**  >  **します**。 [コマンド メニュー **を開き、**][DevtoolsCommandMenuIndex] センサー `Sensors` タブに **アクセスします** 。 これらのアクションを実行した後、DevTools は現在の既定のロケールを変更し、次のコードに影響を与えます。  

*   `Intl.*` API の例: `new Intl.NumberFormat().resolvedOptions().locale`  
*   その他のロケール対応 JavaScript API (たとえば、次のように `String.prototype.localeCompare` `*.prototype.toLocaleString` ) `123_456..toLocaleString()`  
*   DOM API (次のような `navigator.language` DOM API) `navigator.languages`  
*   [Accept-Language][MDNAcceptLanguage] HTTP 要求ヘッダー  

> [!NOTE]
> 更新プログラム `navigator.language` は `navigator.languages` 、すぐには表示されませんが、次のナビゲーションまたはページ更新後にのみ表示されます。  HTTP ヘッダーへの `Accept-Language` 変更は、後続の要求にのみ反映されます。  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールの表示" lightbox="../../media/2020/03/locale.msft.png":::
   ロケールの表示  
:::image-end:::  

デモを試す場合は、[ロケールに依存 [するコード例] に移動します][MathiasByensLocaleDemo]。

Chromium[問題#1051822][CR1051822]

### <a name="cross-origin-embedder-policy-coep-debugging"></a>クロスオリジン エンベダー ポリシー (COEP) のデバッグ  

[ネットワーク] パネルには、 [クロスオリジン エンベダー ポリシーのデバッグ情報][COEP] が表示されます。  

[ **状態]** 列には、要求がブロックされた理由の簡単な説明と、その要求のヘッダーを表示するリンクが表示され、さらにデバッグが行えます。  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**Status** 列のブロックされた要求" lightbox="../../media/2020/03/status.msft.png":::
   [状態] 列のブロック **された** 要求  
:::image-end:::  

[ **ヘッダー] タブの** [応答 **ヘッダー** ] セクションでは、問題を解決する方法について詳しいガイダンスを提供します。  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションの詳細なガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   [応答ヘッダー] セクション **の詳細な** ガイダンス  
:::image-end:::  

[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium[問題#1051466][CR1051466]  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a>ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコン  

[ソース] パネルには、ブレークポイント、条件付きブレークポイント、およびログポイントの新しいアイコンがあります。  

*   ブレークポイント \(![ブレークポイント](../../media/2020/03/breakpoint.msft.png)\) は赤い円で表されます。  
*   条件付きブレークポイント \(![条件付きブレークポイント](../../media/2020/03/conditional.msft.png)\) は、半赤の半白の円で表されます。  
*   Logpoints \(![Logpoint](../../media/2020/03/logpoint.msft.png)\) は、コンソール アイコンを持つ赤い円で表されます。  

新しいアイコンの動機は、UI を他の GUI デバッグ ツール \(通常は色ブレークポイント赤\) と整合性を高め、3 つの機能を一目で区別しやすくする点でした。  

Chromium の問題 [#1041830][CR1041830]  

### <a name="view-network-requests-that-set-a-specific-cookie-path"></a>特定の Cookie パスを設定するネットワーク要求を表示する  

ネットワーク ツールの新しいフィルター キーワードを使用して、特定の Cookie パスを設定する `cookie-path` ネットワーク要求に[集中します][MDNCookiePath]。 ****  

プロパティで [要求をフィルター処理して、その][DevtoolsNetworkReferenceFilterRequestsProperties] 他のキーワード (など) を確認してください `cookie-path` 。

### <a name="dock-to-left-from-the-command-menu"></a>コマンド メニューから左にドッキングする  

コマンド メニュー [を開き][DevtoolsCommandMenuIndex] 、コマンド `Dock to left` を実行して DevTools をビューポートの左側に移動します。  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキングされた DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   ビューポートの左側にドッキングされた DevTools  
:::image-end:::  

> [!NOTE]
> 左側**のドック機能**は 75 以降Microsoft Edge使用できますが、以前はメイン メニューから[しかアクセスできません][DevtoolsCustomizePlacementsChangeMainMenu]。  83 の新機能Microsoft Edgeコマンド メニューからこの機能にアクセスできる点です。  

[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium[問題#1011679][CR1011679]  

### <a name="the-audits-panel-is-now-the-lighthouse-panel"></a>[監査] パネルが [ライトハウス] パネル  

DevTools チームは、多くの場合、Web 開発者から、DevTools から[ライト][GithubGoogleChromeLighthouse]ハウスを実行できる一方で、「ライトハウス」パネルが見つからないので、Audits パネルが**** ライトハウス パネルに変更**** されたというフィードバックを頻繁に受け取っています。  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="[ライトハウス] パネル" lightbox="../../media/2020/03/lighthouse.msft.png":::
   [ライトハウス] パネル  
:::image-end:::  

> [!NOTE]
> [ **ライトハウス** ] パネルには、サードパーティの Web サイトでホストされているコンテンツへのリンクが表示されます。  Microsoft は、これらのサイトのコンテンツおよび収集する可能性があるデータに対して責任を負う責任を負いません。  

### <a name="delete-all-local-overrides-in-a-folder"></a>フォルダー内のすべてのローカル オーバーライドを削除する  

ローカル オーバーライド**を設定**した後、ディレクトリにマウス ポインターを置き、コンテキスト メニュー \(右クリック\)**** を開き、新しい [すべての上書きを削除] オプションを選択して、そのフォルダー内のすべてのローカル オーバーライドを削除します。  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべての上書きを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   すべての上書きを削除する  
:::image-end:::  

[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromiumの問題[#1016501][CR1016501]  

### <a name="updated-long-tasks-ui"></a>更新された長いタスクの UI  

Long **Task は** JavaScript コードで、メイン スレッドを長時間独占し、Web ページがフリーズします。  

しばらくの間、[パフォーマンス[][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]] パネルで長いタスクを視覚化できますが、Microsoft Edge 83 では、[パフォーマンス] パネルの [長いタスク] の視覚化 UI が更新されました。  タスクの長いタスク部分が、ストライプの赤い背景で色付けされました。  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   新しい長いタスク UI  
:::image-end:::  

[フィードバックの送信] [アイコンをツイート][PostTweetEdgeDevTools] または選択してフィードバック [を送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromiumの問題[#1054447][CR1054447]  

### <a name="maskable-icon-support-in-the-manifest-pane"></a>マニフェスト ウィンドウでのマスク可能なアイコンのサポート  

Android Oreo では、さまざまなデバイス モデルのさまざまな図形にアプリ アイコンを表示するアダプティブ アイコンが導入されました。  **マスク可能なアイコン**は、アダプティブ アイコンをサポートする新しいアイコン形式で、マスク可能なアイコンの標準をサポートするデバイスで PWA アイコン[が][ProgressiveWebAppsChromiumIndex]適切に表示されます。  

[マニフェスト]**ウィンドウの**[マスク可能なアイコンの最小セーフ**** 領域のみを表示する] チェック ボックスをオンにして、Android Oreo デバイスでマスク可能なアイコンが良好に表示されるのを確認します。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスク可能なアイコンの最小安全領域のみを表示する] チェック ボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   [**マスク可能なアイコンの最小安全領域のみを表示する] チェック ボックス**  
:::image-end:::  

> [!NOTE]
> この機能は、Microsoft Edge 81 で起動しました。  この 83 のMicrosoft Edgeについては[、「What's New In DevTools (Microsoft Edge 81) 」で説明されていない][WhatsNew81]。  

## <a name="download-the-microsoft-edge-preview-channels"></a>Microsoft Edge プレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合、[Microsoft Edge プレビュー チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "DevTools の新機能 (Microsoft Edge 81) |Microsoft Docs"  

[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "[DevTools コマンド メニュー] Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevtoolsCssIndex]: ../../../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: ../../../css/reference.md#change-colors-with-the-color-picker "[カラー ピッカー] を使用して色を|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "設定 - DevTools Microsoft Edgeをカスタマイズ|Microsoft Docs"  
[DevtoolsCustomizePlacementsChangeMainMenu]: ../../../customize/placement.md#change-placement-from-the-main-menu "メイン メニューから配置を変更|Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTool]: ../../../evaluate-performance/reference.md#analyze-rendering-performance-with-the-rendering-tool "レンダリング ツール を使用してレンダリングパフォーマンスを分析|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: ../../../evaluate-performance/reference.md#view-main-thread-activity "メイン スレッドアクティビティの|Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: ../../../javascript/breakpoints.md#line-of-code-breakpoints "コード行ブレークポイント - DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: ../../../network/reference.md#filter-requests-by-properties "プロパティ別に要求をフィルター処理する - ネットワーク分析|Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../../../remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  

[ProgressiveWebAppsChromiumIndex]: ../../../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリ | Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windowsデバイス ポータルの概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "リモート ツール for Microsoft Edge (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge プレビュー チャネル"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "システムの安定したチャネル リリースMicrosoft Edge"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[Devtools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio Code"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  
[TheWebWeWantMain]: https://webwewant.fyi "必要な Web"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色覚の種類"  
<!-- this link must be http, not https -->  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "Accept-Language |MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Set-Cookie |MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコード例"  

[CR963183]: https://crbug.com/963183 "問題 963183: DevTools が WCAG 準拠ではない"  
[CR1003700]: https://crbug.com/1003700 "Issue 1003700: カラー ビジョン不足シミュレーションの DevTools サポートの追加"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: コマンド メニューを使用して 'Dock to Left' を導入する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能要求: すべてのローカルオーバーライドを削除するボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での COOP/COEP デバッグのサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools タイムラインでパフォーマンス 指標を更新する"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: ロケールをエミュレートするための UI の追加"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: ブレークポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定が検出しにくい"
[CR1056348]: https://crbug.com/1056348 "問題 1056348: Infobar コンポーネントの更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "COOP と COEP の説明 - クロスオリジン の Opener ポリシー"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP と COEP の説明 - クロスオリジン エンベダー ポリシー"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "ライトハウス |GitHub"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/blog/new-in-devtools-83) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
