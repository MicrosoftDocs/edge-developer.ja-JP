---
description: Windows 10 デバイスで Microsoft Edge をリモートでデバッグし、設定にアクセスするための新しい方法を表示します。
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 94b8d067738a1749f136edf2a562652bece183a9
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993430"
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

更新された Chromium のスケジュールに従って、今後の Microsoft Edge リリースのスケジュールを調整し、Microsoft Edge 82 リリースをキャンセルしています。 詳しくは、 [ブログの投稿][WindowsBlogStableRelease] をご覧ください。  

Microsoft Edge 83 の DevTools で利用できる新機能を紹介します。  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションでは、Microsoft Edge DevTools チームから見落とした可能性があるお知らせの一覧を示します。 これらを確認して、DevTools、VS コード拡張などの新機能を試してみてください。  開発者ツールの最新の機能と最大の機能を常に最新の状態に維持するには、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] をダウンロードして、 [Twitter に従っ][EdgeDevToolsTwitterAccount]てください。  

### Windows 10 デバイスで Microsoft Edge をリモートでデバッグする  

Microsoft [Edge \ (ベータ版) アプリのリモートツール][RemoteTools] は、 [microsoft Store][MicrosoftStore]で利用できるようになりました。  [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal]を拡張するこのアプリを使うと、開発用コンピューター上で実行されている microsoft edge のインスタンスからリモートの windows 10 デバイスに接続することができます。ターゲットの一覧 (Microsoft Edge と Pwas は Windows 10 デバイスで開か[れていました][PprgressiveWebAppsChromiumIndex]) をご覧ください。また、開発用コンピューターで、リモートの windows 10 デバイスで実行さ  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="Microsoft Store で利用できる Microsoft Edge (ベータ版) アプリのリモートツール" lightbox="../../media/2020/03/remote-tools.msft.png":::
   図 1: microsoft [Store][MicrosoftStore]で利用できる[Microsoft Edge (ベータ版) アプリのリモートツール][RemoteTools]  
:::image-end:::  

[Windows 10 デバイスと、リモートデバッグ用の開発マシンのセットアップガイドを参照][DevtoolsRemoteDebuggingWindows]してください。  [ツイート][PostTweetEdgeDevTools]または [[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックして、リモートデバッグのエクスペリエンスについてお知らせください。  

### 新しい設定へのアクセス方法  

Devtools にはさまざまな設定が用意されており、これらをカスタマイズして、開発者向けツールの外観、操作性、および作業を行うことができます。 Microsoft Edge 83 では、DevTools の [設定][DevtoolsCustomizeIndexSettings] へのアクセスが非常に簡単になりました。 [コンソール通知] の横にある歯車アイコンとメインメニューの [設定] を開きます。  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="歯車アイコンによって、DevTools の設定が開きます。" lightbox="../../media/2020/03/settings.msft.png":::
   図 2: 歯車アイコンによって [DevTools] の **設定** が開きます。  
:::image-end:::  

[**その他のツール**] の下にある**メインメニュー**から[設定][DevtoolsCustomizeIndexSettings]を開くこともできます。

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="> の [その他のツール > 設定] のメインメニュー" lightbox="../../media/2020/03/settings2.msft.png":::
   図 3:**メインメニューの [**  >  **その他のツール**]  >  **設定**  
:::image-end:::  

Chromium の問題 [#1050855][CR1050855]

### 新機能と改善された infobars

DevTools の情報通知バー \ (infobars) では、見栄えと機能が改善されました。 Microsoft Edge 83 では、適切な操作をすぐに行うことができるように、infobars ボタンが読みやすく、提供されています。  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="Microsoft Edge 83 で縮小版のファイルをきれいに印刷するための情報バー" lightbox="../../media/2020/03/infobar.msft.png":::
   図 4: Microsoft Edge バージョン83でミニのファイルをきれいに印刷するための情報バー  
:::image-end:::  

Chromium の問題 [#1056348][CR1056348]

### キーボードでカラーピッカー内を移動する  

[カラーピッカー][DevtoolsCssReferenceColorPicker]は、変更と宣言のための[要素パネル][DevtoolsCssIndex]の GUI です `color` `background-color` 。  以前のバージョンの Microsoft Edge では、キーボードを使って[カラーピッカー][DevtoolsCssReferenceColorPicker]の [**階調**] セクションを移動できませんでした。  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="これでキーボードを使用して、カラーピッカーの [階調] セクションでセレクターを移動できるようになりました" lightbox="../../media/2020/03/color-picker.msft.png":::
   図 5: キーボードを使用して、[カラーピッカー][DevtoolsCssReferenceColorPicker]の [**階調**] セクションでセレクターを移動できるようになりました  
:::image-end:::  

Microsoft Edge 83 では、キーボードを使用して、カラーピッカーの [ **階調** ] セクションでセレクターを移動できるようになりました。  

Chromium の問題 [#963183][CR963183]  

### ページの更新後に [プロパティ] タブが表示されるようになりました  

Microsoft Edge 81 以前では、[[要素] パネル][DevtoolsCssIndex]の [**プロパティ] タブ**は、ページの更新によって解除されました。  ページを更新すると、[ **プロパティ] タブ** に現在選択されている要素のプロパティが設定されませんでした。  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="Microsoft Edge 81 以前のバージョンでは、ページの更新後に [プロパティ] タブが空白になっていました" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   図 6: Microsoft Edge 81 以前のバージョンでは、ページの更新後に [ **プロパティ] タブ** が空白になっていました  
:::image-end:::  

Microsoft Edge 83 では、[ **プロパティ] タブ**のページを更新した後に、現在選択されている要素のプロパティを表示できるようになりました。  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="Microsoft Edge 83 の [プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示されます。" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   図 7: Microsoft Edge 83 で、[ **プロパティ] タブ** には、ページの更新後に現在選択されている要素のプロパティが表示されます。  
:::image-end:::  

Chromium の問題 [#1050999][CR1050999]  

### 方向キーを使用して変更ツールをスクロールする  

[ **変更] ツール** では、DEVTOOLS で CSS または JavaScript に加えた変更を追跡します。  [ **変更] ツール** を使用して、すべての変更をすばやく確認して、エディター/IDE に戻すことができます。  

Devtools を押して [**変更] ツール**を開き、 `Ctrl` + `Shift` + `P` [コマンドメニュー][DevToolsCommandMenuIndex]を開き、入力 `changes` します。  [ **変更箇所の表示** ] コマンドを選択して実行し、[devtools] ドローワの [ **変更] ツール** を開きます。  

縮小されたファイルに変更を加えた場合は、[ **変更] ツール** を使って横方向にスクロールして、表示されているすべてのコードを表示することができます。  Microsoft Edge 83 以降、キーボードの方向キーを使用して水平方向にスクロールできるようになりました。  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[変更] ツールに表示されているバーを表示することができます。" lightbox="../../media/2020/03/changes.msft.png":::
   図 8: Microsoft Edge 83 では、方向キーを使用して水平方向にスクロールして、[**変更] ツール**の縮小表示コードに加えた変更を確認することができます。  
:::image-end:::  

スクリーンリーダーまたはキーボードを使用して DevTools を移動する場合は、 [ツイート][PostTweetEdgeDevTools] でフィードバックを送信するか、[ [フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team) ] アイコンをクリックしてフィードバックを送信してください。  

Chromium の問題 [#963183][CR963183]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、open source Chromium プロジェクトに寄与した Microsoft Edge 83 で利用可能なその他の機能を示します。  

### ビジョンの欠陥のエミュレート  

[ [レンダリング] タブ][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] を開き、新しい **エミュレート** されたビジョンの機能を使用して、さまざまな視覚障碍を持つユーザーがサイトでどのように利用できるかをわかりやすく把握します。  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ぼやけたビジョンのエミュレート" lightbox="../../media/2020/03/vision.msft.png":::
   図 9: ぼやけたビジョンのエミュレート  
:::image-end:::  

DevTools は、ぼやけたビジョンと次の [種類の色ビジョンの欠陥][ColorBlindnessTypes]をエミュレートできます。  

| カラービジョンの欠陥 | 詳細 |  
|:--- |:--- |  
| Protanopia | 赤の光を感じることはできません。 |  
| Deuteranopia | 緑の光を感じることはできません。 |  
| Tritanopia | 青い光を感じることはできません。 |  
| Achroopsia | 灰色の階調 (非常に珍しい) を除き、どの色もまったく感じられません。 |  

これらのカラービジョンの低画質バージョンが存在しますが、実際にはもっと一般的です。  
たとえば、protanomaly は赤の光に対する感度が低くなっています (protanopia とは異なり、赤の光を完全に認識できないことを示します)。 ただし、これらの視覚に障碍がある方が明確に定義されているわけではありません。このような視覚に障碍がある方は、どのユーザーも異なっている可能性があります (関連する色をもっと少なくしたり、小さくしたりできます)。  

DevTools での極端なシミュレーションを設計することで、web アプリは、protanomaly、deuteranomaly、tritanomaly、および achromatomaly のユーザーからもアクセスできることが保証されます。  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。  

Chromium の問題 [#1003700][CR1003700]  

### ロケールのエミュレート  

**センサー**の場所の位置を設定して、ロケールをエミュレート  >  **Location**します。 [**コマンドメニュー**を開き][DevToolsCommandMenuIndex]、「 `Sensors` **センサー** 」タブにアクセスして入力します。 これらの操作を実行すると、DevTools で現在の既定のロケールが変更され、次のコードに影響します。  

*   `Intl.*` Api などの例を次に示します。 `new Intl.NumberFormat().resolvedOptions().locale`  
*   その他のロケールに対応した JavaScript Api (など) `String.prototype.localeCompare` `*.prototype.toLocaleString` : `123_456..toLocaleString()`  
*   などの DOM Api `navigator.language` `navigator.languages`  
*   [`Accept-Language`][MDNAcceptLanguage]HTTP 要求のヘッダー  

> [!NOTE]
> の更新はすぐには `navigator.language` `navigator.languages` 表示されませんが、次のナビゲーションまたはページの更新後にのみ行われます。  HTTP ヘッダーへの変更 `Accept-Language` は、以降の要求に対してのみ反映されます。  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールのエミュレート" lightbox="../../media/2020/03/locale.msft.png":::
   図 10: ロケールのエミュレート  
:::image-end:::  

デモについては、「 [ロケールに依存するコードの例][MathiasByensLocaleDemo]」をご覧ください。

Chromium の問題 [#1051822][CR1051822]

### Cross-origin Embedder Policy (COEP) のデバッグ  

ネットワークパネルでは、 [クロスオリジンの Embedder ポリシー][COEP] のデバッグ情報が提供されるようになりました。  

[ **状態** ] 列には、要求がブロックされた理由と、さらにデバッグのためにその要求のヘッダーを表示するためのリンクが表示されるようになりました。  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="* * Status * * 列のブロックされたリクエスト" lightbox="../../media/2020/03/status.msft.png":::
   図 11: ブロックされたリクエストの [状態」列  
:::image-end:::  

[**ヘッダー** ] タブの [**応答ヘッダー** ] セクションには、問題を解決するための詳しいガイダンスが表示されます。  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションのその他のガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   図 12: [応答ヘッダー] セクションのその他のガイダンス  
:::image-end:::  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。  

Chromium の問題 [#1051466][CR1051466]  

### ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコン  

[ソース] パネルには、ブレークポイント、条件付きブレークポイント、および logpoints の新しいアイコンがあります。  

*   ブレークポイント \ (![まで](../../media/2020/03/breakpoint.msft.png)\) は赤い円で表されます。  
*   条件付きブレークポイント \ (![条件付きブレークポイント](../../media/2020/03/conditional.msft.png)\) は、半赤の半分が白の丸で表されます。  
*   Logpoints \ (![Logpoint](../../media/2020/03/logpoint.msft.png)\) は、コンソールアイコンが付いた赤い円で表されます。  

新しいアイコンの動機は、他の GUI デバッグツール (通常は色のブレークポイントが赤) との一貫性を高め、3つの機能を一目で簡単に区別できるようにすることです。  

Chromium の問題 [#1041830][CR1041830]  

### 特定の cookie パスを設定するネットワーク要求を表示する  

[ネットワーク] パネルの [新しいフィルター] キーワードを使用して、 `cookie-path` 特定の[cookie パス][MDNCookiePath]を設定するネットワーク要求に注目します。 **Network**  

他のキーワードを検索するには [、プロパティ別のフィルター要求][DevtoolsNetworkReferenceFilterRequestsProperties] を確認し `cookie-path` ます。

### [コマンド] メニューから左へドッキングする  

[コマンドメニュー][DevToolsCommandMenuIndex]を開き、コマンドを実行して、 `Dock to left` ビューポートの左側に devtools を移動します。  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキングされた DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   図 13: ビューポートの左側にドッキングされた DevTools  
:::image-end:::  

> [!NOTE]
> [ **左から左** ] 機能は、Microsoft Edge 75 以降で使用できますが、以前は [**メインメニュー**][DevtoolsCustomizePlacementsChangeMainMenu]からしかアクセスできませんでした。  Microsoft Edge 83 の新機能は、コマンドメニューからこの機能にアクセスできるということです。  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。  

Chromium の問題 [#1011679][CR1011679]  

### 監査パネルが Lighthouse パネルになりました  

DevTools チームは、開発者からのフィードバックを頻繁に発生させていますが、開発者は [Lighthouse][GithubGoogleChromeLighthouse] を試してみても、"Lighthouse" パネルを見つけることができなかったため、 **監査** パネルは **Lighthouse** パネルになりました。  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="Lighthouse パネル" lightbox="../../media/2020/03/lighthouse.msft.png":::
   図 14: Lighthouse パネル  
:::image-end:::  

> [!NOTE]
> **Lighthouse**パネルには、サードパーティの web サイトでホストされているコンテンツへのリンクが用意されています。  Microsoft は、これらのサイトのコンテンツと収集されるデータを管理する責任を負わないものとします。  

### フォルダー内のすべてのローカル上書きを削除する  

**ローカルの上書き**を設定した後、フォルダーを右クリックし、[**すべての上書きの削除**] オプションを選択して、そのフォルダー内のすべてのローカル上書きを削除することができます。  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべての上書きを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   図 15: すべての上書きを削除する  
:::image-end:::  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。  

Chromium の問題 [#1016501][CR1016501]  

### 長いタスクの UI を更新しました  

**長いタスク**とは、web ページをフリーズさせることによって、メインスレッドを長時間 Monopolizes する JavaScript コードです。  

現時点では、[ [パフォーマンス] パネルで長いタスクをビジュアル][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] 化することができましたが、Microsoft Edge 83 では、[パフォーマンス] パネルに長いタスクの視覚エフェクト UI が更新されています。  タスクの長いタスクの部分が色付きの赤の背景で色付けされるようになりました。  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   図 16: 新しい長いタスク UI  
:::image-end:::  

[ツイート][PostTweetEdgeDevTools]でフィードバックを送信するか、[[フィードバックの送信](#getting-in-touch-with-microsoft-edge-devtools-team)] アイコンをクリックします。  

Chromium の問題 [#1054447][CR1054447]  

### [マニフェスト] ウィンドウでのマスクのアイコンのサポート  

Android Oreo では、さまざまなデバイスモデルのさまざまな図形にアプリのアイコンを表示するアダプティブアイコンが導入されました。  **マスクのアイコン** は、アダプティブアイコンをサポートする新しいアイコン形式であり、これにより、 [PWA][PprgressiveWebAppsChromiumIndex] アイコンが、マスクアイコン標準をサポートするデバイスで適切に表示されるようになります。  

[**マニフェスト**] ウィンドウの [新しい**マスクアイコンの最小安全領域のみを表示**する] チェックボックスをオンにして、Oreo デバイスでのマスクアイコンが適切であることを確認します。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスクアイコンの最小安全領域のみを表示する] チェックボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   図 17: [ **マスクアイコンの最小安全領域のみを表示** する] チェックボックス  
:::image-end:::  

> [!NOTE]
> この機能は、Microsoft Edge 81 で開始されました。  Microsoft Edge 83 で取り上げられている更新プログラムについては、 [「DevTools (Microsoft edge 81) の新機能][WhatsNew81]」を参照してください。  

## Microsoft Edge preview チャネルをダウンロードする  

Windows または macOS を使用している場合は、 [Microsoft Edge preview チャネル][MicrosoftEdgePreviewChannels] を既定の開発ブラウザーとして使用することを検討してください。  プレビューチャネルを使うと、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題-Microsoft のドキュメント/エッジ-開発者-GitHub"  
[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://webwewant.fyi "必要な Web"  

[WhatsNew81]: ../01/devtools.md "DevTools の新機能 (Microsoft Edge 81) |Microsoft ドキュメント"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "カラーピッカーを使用して色を変更する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "メインメニューから配置を変更する |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "メインスレッドアクティビティの表示 |Microsoft ドキュメント"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブでのレンダリングのパフォーマンスの分析 |Microsoft ドキュメント"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ |Microsoft ドキュメント"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモートデバッグの概要 |Microsoft ドキュメント"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "行コードのブレークポイント-Microsoft Edge DevTools のブレークポイントでコードを一時停止する方法 |Microsoft ドキュメント"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティによるフィルター要求-ネットワーク分析のリファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal の概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 向けリモートツール (ベータ版)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft ストア"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Microsoft Edge の安定したチャネルリリースでの更新"

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色障碍のある種類"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "受諾-言語"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコードの例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[CR963183]: https://crbug.com/963183 "問題 963183: DevTools は WCAG に準拠していません"  
[CR1003700]: https://crbug.com/1003700 "問題 1003700: カラービジョンの欠陥シミュレーションのための DevTools のサポートを追加する"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: コマンドメニューを使用して "Dock to Left" を導入する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能の要求: すべてのローカル上書きを削除するためのボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "問題 1051466: DevTools での CO-OP/COEP のデバッグのサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools のタイムラインでのパフォーマンスメトリックの更新"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: ロケールをエミュレートするための UI を追加する"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: ブレークポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定ビューを見つけるのが難しい"
[CR1056348]: https://crbug.com/1056348 "問題 1056348: 情報バーのコンポーネントの更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "CO-OP および COEP についての説明 (クロスオリジンの Opener ポリシー)"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "CO-OP および COEP についての説明 (クロスオリジンの Embedder ポリシー)"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub リポジトリ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/updates/2020/03/devtools/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
