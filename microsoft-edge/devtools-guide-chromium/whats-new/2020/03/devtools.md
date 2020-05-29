---
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 17dab9120535ae11ea5a5456552d47dbd7f9e236
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684721"
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







# DevTools の新機能 (Microsoft Edge 83)   

  

更新された Chromium のスケジュールに従って、今後の Microsoft Edge リリースのスケジュールを調整し、Microsoft Edge 82 リリースをキャンセルしています。 詳しくは、[ブログの投稿][WindowsBlogStableRelease]をご覧ください。

Microsoft Edge 83 の DevTools で利用できる新機能を紹介します。

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### Windows 10 デバイスで Microsoft Edge をリモートでデバッグする  

Microsoft [Edge \ (ベータ版) アプリのリモートツール][RemoteTools]は、 [microsoft Store][MicrosoftStore]で利用できるようになりました。  [Windows Device Portal][WindowsDevicePortal]を拡張するこのアプリを使うと、開発用コンピューター上で実行されている microsoft edge のインスタンスからリモートの windows 10 デバイスに接続することができます。ターゲットの一覧 (Microsoft Edge と Pwas は Windows 10 デバイスで開か[れていました][PWADoc]) をご覧ください。また、開発用コンピューターで、リモートの windows 10 デバイスで実行さ  

> ##### 図 1  
> Microsoft [Store][MicrosoftStore]で利用できる[Microsoft Edge (ベータ版) アプリのリモートツール][RemoteTools]  
> ![Microsoft Store で利用できる Microsoft Edge (ベータ版) アプリのリモートツール][ImageRemoteTools]  

[Windows 10 デバイスと、リモートデバッグ用の開発マシンのセットアップガイドを参照][RemoteDebuggingWin10]してください。  [ツイート][PostTweetEdgeDevTools]するか、[フィードバック](#feedback)アイコンをクリックして、リモートデバッグのエクスペリエンスについてお知らせください。  

### 新しい設定へのアクセス方法 

Devtools にはさまざまな設定が用意されており、これらをカスタマイズして、開発者向けツールの外観、操作性、および作業を行うことができます。 Microsoft Edge 83 では、DevTools の[設定][OverviewSettings]へのアクセスが非常に簡単になりました。 [コンソール通知] の横にある歯車アイコンとメインメニューの [設定] を開きます。

> ##### 図 2 
> 歯車アイコンによって、DevTools の [設定] が開きます。 ![][ImageSettingsGearIcon]  

[**その他のツール**] の下にある**メインメニュー**から[設定][OverviewSettings]を開くこともできます。

> ##### 図 3 
> メインメニュー > [その他のツール] > 設定 ![ ] メインメニュー > その他のツール > 設定][ImageSettingsMainMenu]  

Chromium の問題[#1050855][crbug1050855]

### 新機能と改善された infobars

DevTools の情報通知バー \ (infobars) では、見栄えと機能が改善されました。 Microsoft Edge 83 では、適切な操作をすぐに行うことができるように、infobars ボタンが読みやすく、提供されています。

> ##### 図 4
> Microsoft edge 83 で縮小版のファイルを印刷して、 ![ Microsoft edge 83 で縮小版のファイルをきれいに印刷するための情報バー][ImageInfobar]  

Chromium の問題[#1056348][crbug1056348]

### キーボードでカラーピッカー内を移動する  

[カラーピッカー][ColorPicker]は、変更と宣言のための[要素パネル][ElementsDoc]の GUI です `color` `background-color` 。  以前のバージョンの Microsoft Edge では、キーボードを使って[カラーピッカー][ColorPicker]の [**階調**] セクションを移動できませんでした。  

> ##### 図 5  
> これでキーボードを使用して、[カラーピッカー][ColorPicker]の [**階調**] セクションでセレクターを移動できるようになりました  
> ![これでキーボードを使用して、カラーピッカーの [階調] セクションでセレクターを移動できるようになりました][ImageColorPicker]  

Microsoft Edge 83 では、キーボードを使用して、カラーピッカーの [**階調**] セクションでセレクターを移動できるようになりました。  

Chromium の問題[#963183][crbug963183]  

### ページの更新後に [プロパティ] タブが表示されるようになりました  

Microsoft Edge 81 以前では、[[要素] パネル][ElementsDoc]の [**プロパティ] タブ**は、ページの更新によって解除されました。  ページを更新すると、[**プロパティ] タブ**に現在選択されている要素のプロパティが設定されませんでした。  

> ##### 図 6  
> Microsoft Edge 81 以前のバージョンでは、ページの更新後に [**プロパティ] タブ**が空白になっていました  
> ![Microsoft Edge 81 以前のバージョンでは、ページの更新後に [プロパティ] タブが空白になっていました][ImagePropertiesIn81]  

Microsoft Edge 83 では、[**プロパティ] タブ**のページを更新した後に、現在選択されている要素のプロパティを表示できるようになりました。  

> ##### 図 7  
> Microsoft Edge 83 の [**プロパティ] タブ**には、ページの更新後に現在選択されている要素のプロパティが表示されます。  
> ![Microsoft Edge 83 の [プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示されます。][ImagePropertiesIn82]  

Chromium の問題[#1050999][crbug1050999]  

### 方向キーを使用して変更ツールをスクロールする  

[**変更] ツール**では、DEVTOOLS で CSS または JavaScript に加えた変更を追跡します。  [**変更] ツール**を使用して、すべての変更をすばやく確認して、エディター/IDE に戻すことができます。  

Devtools を押して [**変更] ツール**を開き、 `Ctrl` + `Shift` + `P` [コマンドメニュー][DevToolsCommandMenuIndex]を開き、入力 `changes` します。  [**変更箇所の表示**] コマンドを選択して実行し、[devtools] ドローワの [**変更] ツール**を開きます。  

縮小されたファイルに変更を加えた場合は、[**変更] ツール**を使って横方向にスクロールして、表示されているすべてのコードを表示することができます。  Microsoft Edge 83 以降、キーボードの方向キーを使用して水平方向にスクロールできるようになりました。  

> ##### 図 8  
> Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[**変更] ツール**の縮小表示コードに加えた変更を確認することができます。  
> ![Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[変更] ツールに表示されているバーを表示することができます。][ImageChanges]  

スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、[ツイート][PostTweetEdgeDevTools]または[フィードバック](#feedback)アイコンをクリックして、フィードバックを送信してください。  

Chromium の問題[#963183][crbug963183]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 83 で利用可能なその他の機能を示します。  

### ビジョンの欠陥のエミュレート   

[[レンダリング] タブ][RenderingDoc]を開き、新しい**エミュレート**されたビジョンの機能を使用して、さまざまな視覚障碍を持つユーザーがサイトでどのように利用できるかをわかりやすく把握します。  

> ##### 図 9  
> ぼやけたビジョンのエミュレート  
> ![ぼやけたビジョンのエミュレート][ImageEmulatingBlurredVision]  

DevTools は、ぼやけたビジョンと次の[種類の色ビジョンの欠陥][ColorBlindnessTypes]をエミュレートできます。  

| カラービジョンの欠陥 | 詳細 |  
|:--- |:--- | 
| Protanopia | 赤の光を感じることはできません。 |  
| Deuteranopia | 緑の光を感じることはできません。 |  
| Tritanopia | 青い光を感じることはできません。 |  
| Achroopsia | 灰色の階調 (非常に珍しい) を除き、どの色もまったく感じられません。 | 

これらのカラービジョンの低画質バージョンが存在しますが、実際にはもっと一般的です。
たとえば、protanomaly は赤の光に対する感度が低くなっています (protanopia とは異なり、赤の光を完全に認識できないことを示します)。 ただし、これらの視覚に障碍がある方が明確に定義されているわけではありません。このような視覚に障碍がある方は、どのユーザーも異なっている可能性があります (関連する色をもっと少なくしたり、小さくしたりできます)。

DevTools での極端なシミュレーションを設計することで、web アプリは、protanomaly、deuteranomaly、tritanomaly、および achromatomaly のユーザーからもアクセスできることが保証されます。

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[フィードバック](#feedback)アイコンをクリックします。  

Chromium の問題[#1003700][crbug1003700]  

### ロケールのエミュレート 

**センサー**の場所の位置を設定して、ロケールをエミュレート  >  **Location**します。 [**コマンドメニュー**を開き][DevToolsCommandMenuIndex]、「 `Sensors` **センサー** 」タブにアクセスして入力します。これらの操作を実行した後、DevTools は現在の既定のロケールを変更します。次のような影響があります。

- `Intl.*` Api などの例を次に示します。 `new Intl.NumberFormat().resolvedOptions().locale`
- その他のロケールに対応した JavaScript Api (など) `String.prototype.localeCompare` `*.prototype.toLocaleString` :`123_456..toLocaleString()`
- などの DOM Api `navigator.language` `navigator.languages`
- [`Accept-Language`][MDNAcceptLanguage]HTTP 要求のヘッダー

> ##### 図 10  
> ロケールのエミュレート  
> ![ロケールのエミュレート][ImageEmulatingLocales]  

デモについては、「[ロケールに依存するコードの例][MathiasByensLocaleDemo]」をご覧ください。

Chromium の問題[#1051822][crbug1051822]

### Cross-origin Embedder Policy \ (COEP \) デバッグ   

ネットワークパネルでは、[クロスオリジンの Embedder ポリシー][COEP]のデバッグ情報が提供されるようになりました。  

[**状態**] 列には、要求がブロックされた理由と、さらにデバッグのためにその要求のヘッダーを表示するためのリンクが表示されるようになりました。  

> ##### 図 11  
> [**状態**」列でブロックされたリクエスト  
> ![[状態」列でブロックされたリクエスト][ImageNetworkStatus]  

[**ヘッダー** ] タブの [**応答ヘッダー** ] セクションには、問題を解決するための詳しいガイダンスが表示されます。  

> ##### 図 12  
> [応答ヘッダー] セクションのその他のガイダンス  
> ![[応答ヘッダー] セクションのその他のガイダンス][ImageNetworkGuidance]  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[フィードバック](#feedback)アイコンをクリックします。  

Chromium の問題[#1051466][crbug1051466]  

### 特定の cookie パスを設定するネットワーク要求を表示する 

[ネットワーク] パネルの [新しいフィルター] キーワードを使用して、 `cookie-path` 特定の[cookie パス][MDNCookiePath]を設定するネットワーク要求に注目します。 **Network**

他のキーワードを検索するには[、プロパティ別のフィルター要求][NetworkProperties]を確認し `cookie-path` ます。

### [コマンド] メニューから**左へドッキングする**   

[コマンドメニュー][DevToolsCommandMenuIndex]を開き、コマンドを実行して、 `Dock to left` ビューポートの左側に devtools を移動します。  

> ##### 図 13  
> ビューポートの左側にドッキングされた DevTools  
> ![ビューポートの左側にドッキングされた DevTools][ImageDockToLeft]  

> [!NOTE]
> [**左から左**] 機能は、Microsoft Edge 75 以降で使用できましたが、以前は[**メインメニュー**][MainMenuDoc]からしかアクセスできませんでした。  Microsoft Edge 83 の新機能は、コマンドメニューからこの機能にアクセスできるということです。  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[フィードバック](#feedback)アイコンをクリックします。  

Chromium の問題[#1011679][crbug1011679]  

### **監査**パネルが**Lighthouse**パネルになりました   

DevTools チームは、開発者からのフィードバックを頻繁に発生させていますが、開発者は[Lighthouse][GithubGoogleChromeLighthouse]を試してみても、"Lighthouse" パネルを見つけることができなかったため、**監査**パネルは**Lighthouse**パネルになりました。  

> ##### 図 14  
> Lighthouse パネル  
> ![Lighthouse パネル][ImageLighthouse]  

> [!NOTE]
> **Lighthouse**パネルには、サードパーティの web サイトでホストされているコンテンツへのリンクが用意されています。  Microsoft は、これらのサイトのコンテンツと収集されるデータを管理する責任を負わないものとします。  

### フォルダー内のすべてのローカル上書きを削除する   

**ローカルの上書き**を設定した後、フォルダーを右クリックし、[**すべての上書きの削除**] オプションを選択して、そのフォルダー内のすべてのローカル上書きを削除することができます。  

> ##### 図 15  
> すべての上書きを削除する  
> ![すべての上書きを削除する][ImageDeleteOverrides]  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[フィードバック](#feedback)アイコンをクリックします。  

Chromium の問題[#1016501][crbug1016501]  

### 長いタスクの UI を更新しました   

**長いタスク**とは、web ページをフリーズさせることによって、メインスレッドを長時間 Monopolizes する JavaScript コードです。  

現時点では、[[パフォーマンス] パネルで長いタスクをビジュアル][LongTasksInPerformancePanel]化することができましたが、Microsoft Edge 83 では、[パフォーマンス] パネルに長いタスクの視覚エフェクト UI が更新されています。  タスクの長いタスクの部分が色付きの赤の背景で色付けされるようになりました。  

> ##### 図 16  
> 新しい長いタスク UI  
> ![新しい長いタスク UI][ImageLongTask]  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[フィードバック](#feedback)アイコンをクリックします。  

Chromium の問題[#1054447][crbug1054447]  

### [マニフェスト] ウィンドウでのマスクのアイコンのサポート   

Android Oreo では、さまざまなデバイスモデルのさまざまな図形にアプリのアイコンを表示するアダプティブアイコンが導入されました。  **マスクのアイコン**は、アダプティブアイコンをサポートする新しいアイコン形式であり、これにより、 [PWA][PWADoc]アイコンが、マスクアイコン標準をサポートするデバイスで適切に表示されるようになります。  

[**マニフェスト**] ウィンドウの [新しい**マスクアイコンの最小安全領域のみを表示**する] チェックボックスをオンにして、Oreo デバイスでのマスクアイコンが適切であることを確認します。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

> ##### 図 17  
> "マスクアイコンの最小安全領域のみを表示" チェックボックス  
> !["マスクアイコンの最小安全領域のみを表示" チェックボックス][ImageMaskableIcons]  

> [!NOTE]
> この機能は、Microsoft Edge 81 で開始されました。  Microsoft Edge 83 で取り上げられている更新プログラムについては、 [「DevTools (Microsoft edge 81) の新機能][WhatsNew81]」を参照してください。  

## フィードバック   

  

この投稿の新機能や変更点について、または DevTools に関連するその他のものについて説明します。  

*   DevTools の**フィードバック**アイコンを使ってフィードバックを送信する  
*   [@EdgeDevTools][PostTweetEdgeDevTools]ツイート  
*   [目的の Web サイト][TheWebWeWant]に提案を送信する  
*   [エッジ開発者][GitHubMicrosoftDocsEdgeDeveloperNewIssue]リポジトリでこのドキュメントのバグを修正します。  

> ##### 図18  
> Microsoft Edge DevTools の**フィードバック**アイコン  
> ![Microsoft Edge DevTools の * * フィードバック * * アイコン][ImageFeedbackIcon]  

## Microsoft Edge preview チャネルをダウンロードする   

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels]を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

<!-- <<../../_shared/devtools-feedback.md>>

<<../../_shared/canary.md>>

<<../../_shared/discover.md>> -->

  

<!-- image links -->  

[ImageRemoteTools]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/remote-tools.msft.png "図 1: microsoft Store で利用できる Microsoft Edge (ベータ版) アプリのリモートツール"  
[ImageSettingsGearIcon]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/settings.msft.png "図 2: 歯車アイコンによって [DevTools] の設定が開きます。"
[ImageSettingsMainMenu]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/settings2.msft.png "図 3: [その他のツール > 設定] > メインメニュー"
[ImageInfobar]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/infobar.msft.png "図 4: Microsoft Edge 83 で縮小版のファイルをきれいに印刷するための情報バー"
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/color-picker.msft.png "図 5: キーボードを使用して、カラーピッカーの [階調] セクションでセレクターを移動できるようになりました"  
[ImagePropertiesIn81]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/properties-in-81.msft.png "図 6: Microsoft Edge 81 以前のバージョンでは、ページの更新後に [プロパティ] タブが空白になっていました"  
[ImagePropertiesIn82]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/properties-in-82.msft.png "図 7: Microsoft Edge 83 で、[プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示されます。"  
[ImageChanges]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/changes.msft.png "図 8: Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、変更ツールに表示されているバーを表示することができます。"  
[ImageEmulatingBlurredVision]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/vision.msft.png "図 9: ぼやけたビジョンのエミュレート"  
[ImageEmulatingLocales]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/locale.msft.png "図 10: ロケールのエミュレート"
[ImageNetworkStatus]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/status.msft.png "図 11: ブロックされたリクエストの [状態」列"  
[ImageNetworkGuidance]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/guidance.msft.png "図 12: [応答ヘッダー] セクションのその他のガイダンス"  
[ImageDockToLeft]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/dock-to-left.msft.png "図 13: ビューポートの左側にドッキングされた DevTools"  
[ImageLighthouse]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/lighthouse.msft.png "図 14: Lighthouse パネル"  
[ImageDeleteOverrides]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/overrides.msft.png "図 15: すべての上書きを削除する"  
[ImageLongTask]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/long-task.msft.png "図 16: 新しい長いタスク UI"  
[ImageMaskableIcons]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/maskable-icons.msft.png "図 17: [マスクアイコンの最小安全領域のみを表示する] チェックボックス"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/feedback-icon.msft.png "図 18: Microsoft Edge DevTools のフィードバックアイコン"  

[ImageLineOfCodeBreakpoint]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/breakpoint.msft.png
[ImageLogpoint]: /microsoft-edge/devtools-guide-chromium/whats-new/images/2020/03/logpoint.msft.png

<!-- links -->  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新しい問題-Microsoft のドキュメント/エッジ-開発者"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://aka.ms/webwewant "必要な Web"  

[WhatsNew81]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/01/devtools "DevTools の新機能 (Microsoft Edge 81)"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[ColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラーピッカーを使用して色を変更する"  
[ElementsDoc]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  
[MainMenuDoc]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "メインメニューから配置を変更する"  
[LongTasksInPerformancePanel]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "メインスレッドアクティビティの表示"  
[RenderingDoc]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでのレンダリングのパフォーマンスの分析"  
[PWADoc]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ"  
[RemoteDebuggingWin10]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモートデバッグの概要"  
[LineOfCodeBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "行コードのブレークポイント"
[NetworkProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties
[OverviewSettings]: /microsoft-edge/devtools-guide-chromium/customize/#settings

[WindowsDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal の概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 向けリモートツール (ベータ版)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft ストア"  
[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20/update-stable-channel-releases/ "Microsoft Edge の安定したチャネルリリースでの更新"

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness/ "色障碍のある種類"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "受諾-言語"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコードの例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[crbug963183]: https://crbug.com/963183 "問題 963183: DevTools は WCAG に準拠していません"  
[crbug1003700]: https://crbug.com/1003700 "問題 1003700: カラービジョンの欠陥シミュレーションのための DevTools のサポートを追加する"  
[crbug1011679]: https://crbug.com/1011679 "問題 1011679: コマンドメニューを使用して "Dock to Left" を導入する"  
[crbug1016501]: https://crbug.com/1016501 "問題 1016501: 機能の要求: すべてのローカル上書きを削除するためのボタン"  
[crbug1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[crbug1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での CO-OP/COEP のデバッグのサポート"  
[crbug1054447]: https://crbug.com/1054447 "問題 1054447: DevTools のタイムラインでのパフォーマンスメトリックの更新"  
[crbug1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: ロケールをエミュレートするための UI を追加する"
[crbug1041830]: https://crbug.com/1041830 "問題 1041830: ブレークポイントの色を改善する"
[crbug1050855]: https://crbug.com/1050855 "問題 1050855: 設定ビューを見つけるのが難しい"
[crbug1056348]: https://crbug.com/1056348 "問題 1056348: 情報バーのコンポーネントの更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "CO-OP および COEP についての説明 (クロスオリジンの Opener ポリシー)"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "CO-OP および COEP についての説明 (クロスオリジンの Embedder ポリシー)"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub リポジトリ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/updates/2020/03/devtools/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
