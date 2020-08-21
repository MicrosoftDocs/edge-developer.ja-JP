---
title: DevTools の新機能 (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f1b5d147aac1b8b527cc7365f9f91a2a7974863e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942220"
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

更新された Chromium スケジュールの後に、今後の Microsoft Edge リリースのスケジュールを調整し、Microsoft Edge 82 リリースをキャンセルします。 詳細については、ブ [ログの投稿][WindowsBlogStableRelease] をご覧ください。  

Microsoft Edge 83 の DevTools で使用可能な新機能を以下に示します。  

## Microsoft Edge DevTools チームからのお知らせ  

以下のセクションは、Microsoft Edge DevTools チームに見つからない可能性があるお知らせの一覧です。 デベロッパー、VS コード拡張機能などで新機能を試すようにしてください。  開発者ツールの最新機能と最大の機能をすべて最新の状態に保つためには [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを [ダウンロードし、Twitter でフォローしてください][EdgeDevToolsTwitterAccount]。  

### Windows 10 デバイスで Microsoft Edge をリモートでデバッグする  

Microsoft [Edge \(ベータ\)][RemoteTools] アプリが Microsoft Store で入手できるようにな [りました][MicrosoftStore]。  このアプリを使用すると [、開][WindowsUwpDebugTestPerfDevicePortal]発機関で実行されている Microsoft Edge のインスタンスからリモート Windows 10 デバイスに接続できます。ターゲットのリストを確認し、ターゲットのリストを確認します (Windows 10 デバイスで開いた Microsoft Edge と [PWA の][PprgressiveWebAppsChromiumIndex] すべてのタブ)。開発用コンピューター上の DevTools を使用して、開発用コンピューターの DevTools をリモート Windows 10 デバイス上で実行しているターゲットと同じ方法で使用できます。  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="Microsoft Store で入手可能な Microsoft Edge (ベータ) アプリ" lightbox="../../media/2020/03/remote-tools.msft.png":::
   図 1: [Microsoft Store][MicrosoftStore]で入手可能[な Microsoft Edge (ベ][RemoteTools]ータ) アプリ  
:::image-end:::  

[リモート デバッグ用に Windows 10][DevtoolsRemoteDebuggingWindows]デバイスと開発機関の開発機関のマシンをセットアップする方法について説明します。  [フィードバックの送信] アイコンをタイルまたはクリックして、リ[tweeting][PostTweetEdgeDevTools]モート デバッグ エクスペリエンスについて[お知らせください](#getting-in-touch-with-microsoft-edge-devtools-team)。  

### [設定] にアクセスする新しい方法  

DevTools の設定には、DevTools の外観、操作などをカスタマイズできるものがいくつかあります。 Microsoft Edge 83 では、DevTools [の][DevtoolsCustomizeIndexSettings] 設定へのアクセスがさらに簡単になりました。 本体の通知とメイン メニューの横にあるギア アイコンを使用して [設定] を開きます。  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="[開発ツール] の [設定] を開く" lightbox="../../media/2020/03/settings.msft.png":::
   図 2: ギア アイコンが開発ツール **の** [設定] を開く  
:::image-end:::  

[その他のツール] のメ [イン メニュー][DevtoolsCustomizeIndexSettings] から **設定** を **開く方法もあります**。

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="メイン メニューの [>] タブの [>]" lightbox="../../media/2020/03/settings2.msft.png":::
   図 3: メ**イン メニュー**  >  **の [その他]**  >  **の [設定]**  
:::image-end:::  

Chromium の問題は、Chromium [の問題#1050855][CR1050855]

### 新しい情報バーと改善された情報バー

DevTools の情報通知バー \(infobars\) の外観が改善されました。 Microsoft Edge 83 では、情報バーを読みやすく、ボタンを提供して、関連するアクションをすでに取り入れることができます。  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="Microsoft Edge 83 でマイニフェイド ファイルを印刷する情報バー" lightbox="../../media/2020/03/infobar.msft.png":::
   図 4:Microsoft Edge バージョン 83 でマイニファイド ファイルを印刷する場合の情報バー  
:::image-end:::  

Chromium の [問題#1056348][CR1056348]

### キーボードで色の作成ウィンドウを移動する  

色 [の選択は要素][DevtoolsCssReferenceColorPicker] パネルの GUI で [、変更と][DevtoolsCssIndex] 宣 `color` `background-color` 宣表示を行います。  以前のバージョンの Microsoft Edge では、キーボードを使用して、**Shades**カラー ピッカーのシェーディ[ング セクションを移動できな][DevtoolsCssReferenceColorPicker]かった。  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="キーボードを使用して、[色の作成] セクションの [シェーダー] セクションで選択者を移動できるようになりました" lightbox="../../media/2020/03/color-picker.msft.png":::
   図 5: キーボードを使用して、カラー ピッカーの [塗**Shades**りつぶし] セクションで選択者[を移動できるようになりました][DevtoolsCssReferenceColorPicker]  
:::image-end:::  

Microsoft Edge 83 では、キーボードを使用して、色の作成の **[** 塗りつぶし] セクションで選択者を移動できるようになりました。  

Chromium の問題 [#963183][CR963183]  

### ページ更新後に [プロパティ] タブが表示されるようになりました  

Microsoft Edge 81 以前では、[ **要素** ] パネルの [プロパティ] [タブは][DevtoolsCssIndex] ページ更新によって分かれていました。  ページを更新すると、[ **プロパティ] タブ** には現在選択されている要素のプロパティが設定されませんでした。  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="Microsoft Edge 81 以前では、ページ更新後 、[プロパティ] タブが空白でした" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   図 6:Microsoft Edge 81 以前では、ページ更新後 、[ **プロパティ** ] タブが空白でした  
:::image-end:::  

Microsoft Edge 83 では、[プロパティ] タブでページを更新した後に現在選択されている要素のプロパティ **を表示できるようになりました**。  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="Microsoft Edge 83 の [プロパティ] タブには、ページの更新後に現在選択されている要素のプロパティが表示される" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   図 7:Microsoft Edge 83 の [ **プロパティ** ] タブには、ページの更新後に現在選択されている要素のプロパティが表示される  
:::image-end:::  

Chromium の [問題#1050999][CR1050999]  

### 方向キーを使用して [変更] ツールのスクロール  

変更 **ツールは** 、DevTools の CSS または JavaScript に加えたすべての変更を追跡します。  変更ツールを使用すると **、すべての** 変更をすばやく確認し、それらを編集者/IDE に戻すようにすることができます。  

開いて**コマンド メニューを**開き入力して `Ctrl` + `Shift` + `P` 変更ツールを開きます[Command Menu][DevToolsCommandMenuIndex] `changes` 。  [変更の表示 **]** コマンドを選択して**Changes tool**実行し、DevTools 描画ツールで変更ツールを開きます。  

マイニフェイド ファイルに変更を加えた場合 **、変更** ツールを使用すると、すべてのミニバーのコードを表示できます。  Microsoft Edge 83 以降では、キーボードの方向キーを使用して横方向にスクロールできるようになりました。  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="Microsoft Edge 83 では、方向キーで水平方向にスクロールすると、[変更] ツールでマイニフェイド コードが表示される場合があります。" lightbox="../../media/2020/03/changes.msft.png":::
   図 8: Microsoft Edge 83 では、矢印キーを使って横方向にスクロールし、[変更] ツールでマイニュアル コードに加えた変更を **確認できます。**  
:::image-end:::  

スクリーン リーダーまたはキーボードを使用して DevTools 内を移動する場合は、Microsoft における [タイル][PostTweetEdgeDevTools] をタイーションするか、[フィードバックの送信] アイコンをクリックして、フィードバック [を送信してください](#getting-in-touch-with-microsoft-edge-devtools-team) 。  

Chromium の問題 [#963183][CR963183]  

## Chromium プロジェクトからのお知らせ  

次のセクションでは、Microsoft Edge 83 で使用可能な追加機能について、オープン ソース Chromium プロジェクトに投稿された追加機能について説明します。  

### 視図を使ってみる  

[ [レンダリング][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ] タブを開き、新しい **エ** ミュレートの視視性機能を使用して、サイトのさまざまな視視性を高めた人にどのように役立つかをより深く理由を理由を深めます。  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="ブレージの視図をエミュレートする" lightbox="../../media/2020/03/vision.msft.png":::
   図 9: ブレージング ブレージングのブレージ  
:::image-end:::  

DevTools では視認知度が向上し、次の色の視認度が向 [上します][ColorBlindnessTypes]。  

| 色の視差 | 詳細 |  
|:--- |:--- |  
| Protanopia | 明るい光の割り付けを行う機能。 |  
| Deuteranopia | 緑のライトに対する割り付けをおくといいえます。 |  
| トリタノピア | 青色のライトを割りに合う機能。 |  
| アクロマトタ | 緑の \(とはみなかう) のシェーディングを除き、任意の色の色のパーセンティーをパーセンティブする機能。 |  

これらの色の視視用版が少なくなり、実に一般的です。  
たとえば、確率とは、明るさ (プロテールに対して認めないと完全にできる、プロテールに対しては小さいと見なされます)。 しかし、これらの -omaly 視認のデフォルトは明確に定義されていません。視認性を高めるすべてのユーザーが異なり、異なるように見える場合があります (色の割合をパーセント/縮小できる)。  

開発ツールでの非常に拡張のシミュレーションを設計することで、Web アプリは、プロテノラル、デュラノイマ、トラマリのユーザーもアクセスできる保証されます。  

フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium の問題はキ [#1003700][CR1003700]  

### エミュレート ロケール  

スニーズの場所に場所を設定することで **、ロケールをエミュレート**  >  **します**。 [コマンド メニュー **を開**][DevToolsCommandMenuIndex] き `Sensors` **、「Sensors」タブにアクセス** する。 これらのアクションを実行すると、現在の既定のロケールが変更されるため、次のコードに影響します。  

*   `Intl.*` たとえば、API の例を示します。 `new Intl.NumberFormat().resolvedOptions().locale`  
*   次に例を示します `String.prototype.localeCompare` `*.prototype.toLocaleString` 。 `123_456..toLocaleString()`  
*   DOM API などの DOM `navigator.language` API `navigator.languages`  
*   [`Accept-Language`][MDNAcceptLanguage]HTTP 要求ヘッダー  

> [!NOTE]
> 更新内容とすぐには表示されませんが、次のナビゲーションまたはページ更新後 `navigator.language` `navigator.languages` にのみ表示されます。  HTTP ヘッダーの変更は、以降の要求に対してのみ `Accept-Language` 表示されます。  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="ロケールをエミュレートする" lightbox="../../media/2020/03/locale.msft.png":::
   図 10: ロケールをエミュレートする  
:::image-end:::  

デモを試すには、 [ロケールに依存するコードの例を参照してください][MathiasByensLocaleDemo]。

Chromium の [問題#1051822][CR1051822]

### クロスプリッド ドライバー の埋め込みポリシー (COEP) デバッグ  

これで、[ネットワーク パネル] には、 [クロ][COEP] スクロステン 埋め込みポリシーデバッグ情報が提供されるようになりました。  

[ **状態** ] 列には、要求がブロックされた理由と、詳細にデバッグする必要があるその要求のヘッダーを表示するリンクが表示されます。  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**Status** 列のブロック要求" lightbox="../../media/2020/03/status.msft.png":::
   図 11:[状態] 列の [ブロックされたリクエスト]  
:::image-end:::  

[**ヘッダー] タブの**[応答ヘッダー]**Headers**セクションには、問題を解決する方法の詳細なガイダンスがあります。  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="[応答ヘッダー] セクションのその他のガイダンス" lightbox="../../media/2020/03/guidance.msft.png":::
   図 12: [応答ヘッダー] セクションのその他のガイダンス  
:::image-end:::  

フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium の [問題#1051466][CR1051466]  

### 区切り点、条件付き改行ポイント、およびロゴの新しいアイコン  

[ソース] パネルには、区切りポイント、条件付きのブレークポイント、およびロゴの新しいアイコンがあります。  

*   ブレークポイント \(![改ページ](../../media/2020/03/breakpoint.msft.png)\) は、リッドの回数で表されます。  
*   条件付き改行ポイント \(![条件付き改行ポイント](../../media/2020/03/conditional.msft.png)\) は、実数の下の中で表されます。  
*   Logpoints \(![Logpoint](../../media/2020/03/logpoint.msft.png)\) は、本体アイコン付きのリッド音の付きのシングルで表されます。  

新しいアイコンのムービーは、UI デバッグ ツール (通常は色分けの破線) に一定性があり、3 つの機能を簡単に区別できるようにすることです。  

Chromium[の問題][CR1041830]#1041830  

### 特定の Cookie パスを設定するネットワーク要求を表示する  

ネットワーク パネ `cookie-path` ルの新しいフィルター **キーワードを** 使用して、特定のクッキー パスを設定する [ネットワーク要求に注中します][MDNCookiePath]。  

プロパティ別 [のフィルター要求をチェックして、その][DevtoolsNetworkReferenceFilterRequestsProperties] 他のキーワードを見つけます `cookie-path` 。

### コマンド メニューからドックから左へドッキャッキ  

コマンド メニュー [を開き][DevToolsCommandMenuIndex] 、コマンド `Dock to left` を実行して、ビューポートの左側に DevTools を移動します。  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="ビューポートの左側にドッキャッキ化された DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   図 13: ビューポートの左側にドッキャッキ化された DevTools  
:::image-end:::  

> [!NOTE]
> **Dock から左**に表示される機能は、Microsoft Edge 75 以降利用可能になりましたが、以前はメイン メニューから[**のみアクセスできました**][DevtoolsCustomizePlacementsChangeMainMenu]。  Microsoft Edge 83 の新機能は、現在、[コマンド] メニューからこの機能にアクセスできる機能です。  

フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium の [問題#1011679][CR1011679]  

### [監査] パネルが灯した時にハッシュ パネルになりました  

DevTools チームは、Web 開発者からフィードバックを受けました。このチームが、DevTools から Lighthouse を実行できなかったときに、"Lighthouse" パネルが見つからなかったときに、[Lighthouse] パネルが見つからなかったため、[**監**査] パネルが**強調表示**されています。 [Lighthouse][GithubGoogleChromeLighthouse]  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="灯" lightbox="../../media/2020/03/lighthouse.msft.png":::
   図 14: 灯カウント パネル  
:::image-end:::  

> [!NOTE]
> **灯カウントには**、サード パーティの Web サイトでホストされているコンテンツへのリンクが表示されます。  Microsoft は、お客様のごなることは一切管理されており、これらのサイトのコンテンツや収集される可能性のあるすべてのデータを制御できません。  

### フォルダー内のすべてのローカル オーバーライドを削除する  

ローカル オー **バーライドを設定した後** 、フォルダーを右クリックして[すべて削除] **オプション** を選択して、そのフォルダー内のすべてのローカル オーバーライドを削除できます。  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="すべてのオーバーライドを削除する" lightbox="../../media/2020/03/overrides.msft.png":::
   図 15: すべてのオーバーライドを削除する  
:::image-end:::  

フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium の [問題#1016501][CR1016501]  

### 更新された長いタスク UI  

長 **いタスクは** 、メイン スレッドを一定時間に移動する JavaScript コードで、Web ページが固定されるためにフリーズします。  

長いタスクをパフ[visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]ォーマンス パネルで視覚化できるのは、パフォーマンス パネルの長いタスク視覚エフェクト UI が更新されました。  タスクの長いタスク部分は、強い背景で色付けされます。  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新しい長いタスク UI" lightbox="../../media/2020/03/long-task.msft.png":::
   図 16: 新しい長いタスク UI  
:::image-end:::  

フィードバックの送信アイコンをタ [イ][PostTweetEdgeDevTools] ロー化またはクリックして [、フィードバックを送信](#getting-in-touch-with-microsoft-edge-devtools-team) します。  

Chromium[の問題][CR1054447]#1054447  

### マスク可能なアイコンのサポート (マニフェスト) ウィンドウのサポート  

Android Oreo に導入されたアダプティブ アイコンが導入されました。このアイコンは、さまざまなデバイス モデル間でアプリ のアイコンを表示します。  **マスク可能なアイコンは** 、アダプティブ アイコンをサポートする新しいアイコンの書式で、マスク可能なアイコン標準をサポートするデバイスで [PWA][PprgressiveWebAppsChromiumIndex] アイコンが正しく表示されるようにすることができます。  

マニフェ**スト ウィンドウ**のマスク可能なアイコンのみを表示するチェックボックスをオンにして**Manifest**、マスク可能なアイコンが Android またはデバイスで良い状態であることを確認します。  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="[マスケートアイコンの最小値のみを表示する] チェック ボックス" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   図 17: マスク可能なアイコンの最小の安全な領域 **のみを表示** する  
:::image-end:::  

> [!NOTE]
> この機能は、Microsoft Edge 81 で起動しました。  Microsoft Edge 83 で説明した更新プログラムについては、Microsoft [Edge の新機能 (Microsoft Edge 81) には取り上がれませんでした][WhatsNew81]。  

## Microsoft Edge のプレビュー チャネルをダウンロードする  

Windows または macOS を使用している場合は [、Microsoft Edge のプレビュー][MicrosoftEdgePreviewChannels] チャネルを既定の開発ブラウザーとして使用することを検定してください。  プレビュー チャネルを使用すると、最新の DevTools 機能にアクセスできます。  

## Microsoft Edge DevTools チームとのつながりを手にする  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |チェットを投稿する"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "Twitter アカウント@EdgeDevTools Twitter アカウント"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新しい問題 - MicrosoftDocs/edge-developer - GitHub"  
[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview チャネル"  
[TheWebWeWant]: https://webwewant.fyi "必要な Web"  

[WhatsNew81]: ../01/devtools.md "Microsoft Edge 81 の新機能 |Microsoft ドキュメント"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンド メニューでコマンドを実行する |Microsoft ドキュメント"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "色の作成で色を変更する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を開始する |Microsoft ドキュメント"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "配置をメイン メニューから変更する |Microsoft ドキュメント"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "メイン スレッド アクティビティを表示する |Microsoft ドキュメント"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "[レンダリング] タブを使用してレンダリングのパフォーマンスを分析する |Microsoft ドキュメント"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上のプレイ Web アプリ |Microsoft ドキュメント"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Windows 10 デバイスのリモート デバッグの使用を開始する |Microsoft ドキュメント"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "コードの改行 - Microsoft Edge DevTools で、コードをブレークポイントと一体化する方法 |Microsoft ドキュメント"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティ別のフィルター要求 - ネットワーク分析リファレンス |Microsoft ドキュメント"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "設定 - Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows デバイス ポータルの概要"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge (ベータ) 用リモート ツール (ベータ)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft ストア"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Microsoft Edge の、スタブル リリースの更新プログラム"

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "コール ブリンジの種類"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "承諾する言語"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "ロケールに依存するコードの例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[CR963183]: https://crbug.com/963183 "発行 963183: DevTools は WCAG に準格していません"  
[CR1003700]: https://crbug.com/1003700 "問題 1003700: 色ビジエンシエンシェル シマーシュアルの DevTools サポートを追加する"  
[CR1011679]: https://crbug.com/1011679 "問題 1011679: [コマンド] メニューを使用して 'ドックを左に挿入する" を参照する"  
[CR1016501]: https://crbug.com/1016501 "問題 1016501: 機能リクエスト: すべてのローカル オーバーライドを削除するボタン"  
[CR1050999]: https://crbug.com/1050999 "問題 1050999: [プロパティ] タブ"  
[CR1051466]: https://crbug.com/1051466 "発行 1051466: DevTools での COOP/COEP デバッグをサポート"  
[CR1054447]: https://crbug.com/1054447 "問題 1054447: DevTools タイムラインでパフォーマンス測定を更新する"  
[CR1051822]: https://crbug.com/1051822 "問題 1051822: DevTools: DevTools: Add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add UI add uI add uI"
[CR1041830]: https://crbug.com/1041830 "問題 1041830: 区切りポイントの色を改善する"
[CR1050855]: https://crbug.com/1050855 "問題 1050855: 設定ビューが見つけにくい"
[CR1056348]: https://crbug.com/1056348 "1056348 の問題: Infobar Component 更新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "COOP と COEP の説明 - クロスプレーター ポリシー"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP と COEP の説明 - クロスクロスプレードダー ポリシー"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub リポジトリ"  

> [!NOTE]
> このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。  
> ここには元のページが表示[され](https://developers.google.com/web/updates/2020/03/devtools/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
