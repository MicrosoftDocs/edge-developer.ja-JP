---
title: Microsoft Edge DevTools でネットワークアクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 267b0113e07085dd565a3ff3437a3fcac2dff9d7
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611813"
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





# Microsoft Edge DevTools でネットワークアクティビティを検査する   



これは、ページのネットワークアクティビティの検査に関連する、よく使われる DevTools 機能のいくつかの実践的なチュートリアルです。  

代わりに機能を参照する場合は、[ネットワークの参照][DevtoolsNetworkReference]を参照してください。  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## [ネットワーク] パネルを使用する場合   

通常、[ネットワーク] パネルは、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合に使用します。  [ネットワーク] パネルの最も一般的なユースケースは、次のとおりです。  

*   リソースが実際にはまったくアップロードまたはダウンロードされていることを確認します。  
*   HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査します。  

ページの読み込みのパフォーマンスを向上させる方法を探している場合は、[ネットワーク] パネルから開始しないで**ください**。  ネットワークアクティビティに関連していない読み込みパフォーマンスの問題には、さまざまな種類があります。  ページを改善する方法についての候補が表示されるため、監査パネルから開始します。  「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。  

## [ネットワーク] パネルを開く   

このチュートリアルを最大限に活用するには、デモを開き、デモページの機能を試してください。  

1.  [はじめに] の[デモ][GlitchNetworkGetStarted]を開きます。  
    
    > ##### 図 1  
    > デモ  
    > ![デモ][ImagesTutorialDemo]  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    > ##### old Figure 2  
    > The demo in one window and this tutorial in a different window  
    > ![The demo in one window and this tutorial in a different window][ImagesTutorialWindows]  -->

1.  [Open DevTools][DevToolsOpen] `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押して、devtools を開きます。  **コンソール**パネルが開きます。  
    
    > ##### 図 2  
    > 本体  
    > ![コンソール][ImagesTutorialConsole]  
    
    [ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。  
    
    > ##### 図 3  
    > ウィンドウの下部にドッキングされた DevTools  
    > ![DevTools] ウィンドウの下部にドッキングされています。[ImagesTutorialDocked]  

1.  [**ネットワーク**] タブを選択します。 [ネットワーク] パネルが開きます。  
    
    > ##### 図 4  
    > ウィンドウの下部にドッキングされた DevTools  
    > ![DevTools] ウィンドウの下部にドッキングされています。[ImagesTutorialNetwork]  

[ネットワーク] パネルが空になりました。  DevTools は、開いた後にのみネットワークアクティビティを記録し、DevTools を開いた後のネットワークアクティビティは発生しませんでした。  

## ネットワークアクティビティをログに記録する   

ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。  

1.  ページを再読み込みします。  ネットワークパネルでは、ネットワーク**ログ**にすべてのネットワークアクティビティが記録されます。  
    
    > ##### 図 5  
    > ネットワークログ  
    > ![ネットワークログ][ImagesTutorialLog]  
    
    **ネットワークログ**の各行は、リソースを表します。  既定では、リソースは時系列順に表示されます。  トップリソースは、通常、メインの HTML 文書です。  一番下のリソースは、要求されたすべてのものです。  
    
    各列は、リソースに関する情報を表します。  [**図 6**](#figure-6)は、既定の列を示しています。  

    *   **状態**。  応答の HTTP 状態コード。  
    *   **[種類]**。  リソースの種類。  
    *   **イニシエーター**。  リソース要求の原因。  [イニシエーター] 列のリンクを選ぶと、要求を発生させたソースコードが表示されます。  
    *   **時刻**。  要求の期間。  
    *   **ウォーターフォール**  要求の異なるステージのグラフィカル表現。  
        ウォーターフォールの上にマウスポインターを置くと、ブレークダウンが表示できます。  
    
    > [!NOTE]
    > ネットワークログの上のグラフは概要と呼ばれます。  このチュートリアルの概要グラフは使用しないため、非表示にすることができます。  「[概要ウィンドウを非表示にする」を][DevtoolsReferenceHideOverview]参照してください。
        
1.  DevTools を開くと、ネットワークログにネットワークアクティビティが記録されます。  
    これを示すには、まず**ネットワークログ**の下部を確認し、最後のアクティビティを記録します。  
1.  次に、デモの [**データの取得**] ボタンを選択します。  
1.  もう一度**ネットワークログ**の下部を確認します。  という新しいリソースが表示され `getstarted.json` ます。  [**データの取得**] ボタンを選択すると、ページによってこのファイルが要求されます。  
    
    > ##### 図 6  
    > ネットワークログの新しいリソース  
    > ![ネットワークログの新しいリソース][ImagesTutorialRuntime]  

## 詳細情報を表示する   

ネットワークログの列は構成可能です。  使用していない列を非表示にすることができます。  
既定で非表示になっている列も数多く用意されています。  

1.  ネットワークログテーブルのヘッダーを右クリックし、[**ドメイン**] を選択します。  各リソースのドメインが表示されるようになりました。  
    
    > ##### 図 7  
    > ドメイン列を有効にする  
    > ![Domain 列を有効にする][ImagesTutorialDomain]  
    
    > [!TIP]
    > [**名前**列のセルの上にマウスポインターを置くと、リソースの完全な URL が表示されます。  

## 低速ネットワーク接続のシミュレーション   

サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデバイスのネットワーク接続よりも高速です。  ページを調整することによって、モバイルデバイスでページが読み込まれるまでの時間を把握することができます。  

1.  [**調整**] ドロップダウンを選択します。これは、既定で [**オンライン**] に設定されています。  
    
    > ##### 図 8  
    > 調整を有効にする  
    > ![調整を有効にする][ImagesTutorialThrottling]  
    
1.  [**低速 3g**] を選びます。  
    
    > ##### 図 9  
    > 低速3G の選択  
    > ![低速3G の選択][ImagesTutorialSlow3G]  
    
1.  長押しして、[**リロード** ![ ] をクリックし、 ][ImageRefreshIcon] [**キャッシュを空**にする] を選択します。  
    
    > ##### 図 10  
    > 空のキャッシュとハードリロード  
    > ![空のキャッシュとハードリロード][ImagesTutorialHardReload]  
    
    繰り返しアクセスした場合、ブラウザーは通常[キャッシュ][MDNHTTPCache]の一部のファイルを提供します。これにより、ページの読み込みが高速化されます。  **空のキャッシュとハードリロード**は、ブラウザーがすべてのリソースについてネットワークにアクセスすることを強制します。  これは、初めてのユーザーがページの読み込みを体験する方法を確認する場合に便利です。  
    
    > [!NOTE]
    > **空のキャッシュと "Hard Reload** " ワークフローは、devtools が開いている場合にのみ使用できます。  

## スクリーンショットをキャプチャする   

スクリーンショットを使用すると、ページの読み込み中にページがどのように表示されるかを確認できます。  

1.  [ ![ ネットワーク設定] を選択 ][ImageSettingsIcon] し、[**スクリーンショットのキャプチャ**] チェックボックスをオンにします。
1.  **空のキャッシュとハードリロード**ワークフローを使用して、もう一度ページを再読み込みします。  この方法について事前に確認が必要な場合は[、「低速接続をシミュレート](#simulate-a-slower-network-connection)する」を参照してください。  
    スクリーンショットウィンドウには、読み込み処理中のさまざまなポイントでページがどのように表示されるかが表示されます。  
    
    > ##### 図 11  
    > ページの読み込みのスクリーンショット  
    > ![ページの読み込みのスクリーンショット][ImagesTutorialAllScreenshots]  

1.  最初のサムネイルを選択します。  DevTools は、現時点で発生していたネットワークアクティビティを示しています。  
    
    > ##### 図 12  
    > 最初のスクリーンショットで発生したネットワークアクティビティ  
    > ![最初のスクリーンショットで発生したネットワークアクティビティ][ImagesTutorialFirstScreenshot]  

1.  [ ![ ネットワーク設定] を ][ImageSettingsIcon] もう一度選択し、[**スクリーンショットのキャプチャ**] チェックボックスをオフにして、スクリーンショットウィンドウを閉じます。
1.  ページをもう一度読み込みます。  

## リソースの詳細を調べる   

詳細については、リソースを選択してください。  今すぐお試しください:  

1.  を選択し `getstarted.html` ます。  [**ヘッダー** ] タブが表示されます。  このタブを使用して、HTTP ヘッダーを検査します。  
    
    > ##### 図 13  
    > [ヘッダー] タブ  
    > ![ヘッダー] タブ[ImagesTutorialHeaders]  
    
1.  [**プレビュー** ] タブを選択します。 HTML の基本的なレンダリングが表示されます。  
    
    > ##### 図 14  
    > [プレビュー] タブ  
    > ![プレビュー] タブ[ImagesTutorialPreview]  

     このタブは、API が HTML でエラーコードを返す場合に便利です。  HTML ソースコードよりもレンダリングされた HTML を読みやすくしたり、画像を検査したりすることができます。  

1.  [**応答**] タブを選択します。 HTML ソースコードが表示されます。  
    
    > ##### 図 15  
    > [応答] タブ  
    > ![返信] タブ[ImagesTutorialResponse]  
    
    > [!TIP]
    > ファイルが縮小されたときに、 **Format** [ ![ 返信] タブの下部にある [書式の書式設定] を選ぶと、 ][ImageFormatIcon] ファイルの内容が読みやすくなります。 **Response**  

1.  [**タイミング**] タブを選択します。 このリソースのネットワークアクティビティの内訳が表示されます。  
    
    > ##### 図 16  
    > [タイミング] タブ  
    > ![タイミング] タブ[ImagesTutorialTiming]  

1.  [閉じる] を**選択し** ![ ][ImageCloseIcon] て、もう一度ネットワークログを表示します。  
    
    > ##### 図 17  
    > [閉じる] ボタン  
    > ![閉じる] ボタン[ImagesTutorialCloseTiming]  

## ネットワークのヘッダーと返信を検索する   

特定の文字列または正規表現について、すべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、[**検索**] ウィンドウを使用します。  

たとえば、リソースが適切な**キャッシュポリシー**を使っていることを確認する必要があるとします。  

<!--TODO: add cache policies section when available  -->

1.  [**検索**検索] を選び ![ ][ImageSearchIcon] ます。  [検索] ウィンドウがネットワークログの左側に表示されます。  
    
    > ##### 図18  
    > [検索] ウィンドウ  
    > ![検索ウィンドウ][ImagesTutorialSearch]  

1.  入力 `Cache-Control` して、キーを押し `Enter` ます。  [検索] ウィンドウには、 `Cache-Control` リソースヘッダーまたはコンテンツ内で見つかったすべてのインスタンスが一覧表示されます。  
    
    > ##### 図19  
    > 検索結果 `Cache-Control`  
    > ![キャッシュの検索結果][ImagesTutorialResults]  

1.  結果を選択すると、結果が見つかったリソースが表示されます。  リソースの詳細が表示されている場合は、結果を選択して直接移動します。  たとえば、ヘッダーで検索されたクエリの場合、[ヘッダー] タブが開きます。   コンテンツ内にクエリが見つかった場合は、[**応答**] タブが開きます。  
    
    > ##### 図20  
    > [ヘッダー] タブで強調表示された検索結果  
    > ![ヘッダー] タブで強調表示された検索結果[ImagesTutorialCache]  
    
1.  [検索] ウィンドウと [ヘッダー] タブを閉じます。  
    
    > ##### 図21  
    > [閉じる] ボタン  
    > ![閉じる] ボタン[ImagesTutorialCloseButtons]  
    
## リソースをフィルター処理する   

DevTools には、タスクに関連していないリソースをフィルター処理するための多数のワークフローが用意されています。  

> ##### 図22  
> [フィルター] ツールバー  
> ![フィルター] ツールバー[ImagesTutorialFilters]  

[**フィルター** ] ツールバーは、既定で有効になっています。  そうでなければ：  

1.  [**フィルターフィルター] を選択**し ![ ][ImageFilterIcon] て表示します。  

### 文字列、正規表現、またはプロパティによるフィルター処理   

**フィルター**テキストボックスでは、さまざまな種類のフィルターがサポートされています。  

1.  `png`[**フィルター** ] テキストボックスに入力します。  テキストが含まれているファイルのみ `png` が表示されます。  この場合、フィルターに一致するファイルは PNG 画像のみです。  
    
    > ##### 図23  
    > 文字列フィルター  
    > ![文字列フィルター][ImagesTutorialPNG]  

1.  「`/.*\.[cj]s+$/`」と入力します。  DevTools では、末尾が a または a の後に1つ以上の文字が続いているファイル名でリソースをフィルター処理 `j` `c` `s` します。  
    
    > ##### 図24  
    > 正規表現フィルター  
    > ![正規表現フィルター][ImagesTutorialRegEx]  
    
1.  「`-main.css`」と入力します。  DevTools でフィルター処理 `main.css` します。  他のファイルがそのパターンに一致した場合は、それらもフィルターで除外されます。  
    
    > ##### 図25  
    > ネガティブフィルター  
    > ![ネガティブフィルター][ImagesTutorialNegative]  
    
1.  `domain:cdn.glitch.com`[**フィルター** ] テキストボックスに入力します。  DevTools は、このドメインと一致しない URL のリソースをフィルター処理します。  
    
    > ##### 図26  
    > プロパティフィルター  
    > ![プロパティフィルター][ImagesTutorialProperty]  

    フィルター処理可能なプロパティの完全なリストについては、「[プロパティ別に要求をフィルター処理][DevtoolsReferenceProperty]する」をご覧ください。  
    
    
1.  任意のテキストの**フィルター**テキストボックスをクリアします。  

### リソースの種類でフィルター処理する   

スタイルシートなど、特定の種類のファイルにフォーカスを移動するには、次の操作を行います。  

1.  [ **CSS**] を選びます。  その他のすべての種類のファイルはフィルターで除外されます。  
    
    > ##### 図27  
    > CSS ファイルのみを表示する  
    > ![CSS ファイルのみ表示][ImagesTutorialCSS]  
    
1.  スクリプトも表示するに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、[ **JS**] を選びます。  
    
    > ##### 図28  
    > CSS と JS ファイルのみを表示する  
    > ![CSS と JS ファイルのみを表示します][ImagesTutorialCSSJS]  
    
1.  [**すべて**] を選択してフィルターを削除し、すべてのリソースをもう一度表示します。  

「他のフィルター処理ワークフローの[フィルター要求][DevtoolsNetworkReferenceFilter]」を参照してください。  

## リクエストをブロック   

ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?  完全に失敗したか、まだ機能していますか?  確認要求をブロックする:  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ **Command Menu**(macOS \) を押します。  
    
    > ##### 図29  
    > コマンドメニュー  
    > ![コマンドメニュー][ImagesTutorialCommandMenu]  
    
1.  「」と入力し `block` 、[**要求ブロックの表示**] を選択して、キーを押し `Enter` ます。  
    
    > ##### 図30  
    > リクエストブロックの表示  
    > ![要求のブロックを表示][ImagesTutorialBlock]  

1.  [パターン追加パターンの**追加**] を選択し ![ ][ImageAddIcon] ます。  
1.  「`main.css`」と入力します。  
    
    > ##### 図31  
    > ブロッキング `main.css`  
    > ![ブロックする][ImagesTutorialAddBlock]  
    
1.  **[追加]** をクリックします。  
1.  ページを再読み込みします。  期待どおり、メインのスタイルシートがブロックされているため、ページのスタイルが少し messed ます。  
    
    > [!NOTE]
    > `main.css`ネットワークログの行。  赤いテキストは、リソースがブロックされたことを意味します。
    
    > ##### 図32  
    > `main.css` がブロックされています  
    > ![メイン .css はブロックされています][ImagesTutorialBlockedStyles]  

1.  [**リクエストのブロックを有効にする**] チェックボックスをオフにします。  

## まとめ  

これでチュートリアルを完了しました。  Microsoft Edge DevTools でのネットワークパネルの使い方について説明しました。






ネットワークの[参照][DevtoolsNetworkReference]を確認して、ネットワークアクティビティの調査に関連するその他の devtools 機能を見つけます。  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-icon.msft.png  
[ImageCloseIcon]: /microsoft-edge/devtools-guide-chromium/media/close-icon.msft.png  
[ImageFilterIcon]: /microsoft-edge/devtools-guide-chromium/media/filter-icon.msft.png  
[ImageFormatIcon]: /microsoft-edge/devtools-guide-chromium/media/format-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: /microsoft-edge/devtools-guide-chromium/media/screenshots-icon.msft.png  
[ImageSearchIcon]: /microsoft-edge/devtools-guide-chromium/media/search-icon.msft.png  
[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png

[ImagesTutorialDemo]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-inspect-network-activity-demo.msft.png "図 1: デモ"  
<!--[ImagesTutorialWindows]: /microsoft-edge/devtools-guide-chromium/media/network-tutorial/windows.msft.png " old Figure 2: The demo in one window and this tutorial in a different window"  -->  
[ImagesTutorialConsole]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-console.msft.png "図 2: 本体  
[ImagesTutorialDocked]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-console-bottom.msft.png "図 3: ウィンドウの下部にドッキングされている DevTools  
[ImagesTutorialNetwork]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-bottom.msft.png "図 4: ウィンドウの下部にドッキングされている DevTools  
[ImagesTutorialLog]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network.msft.png "図 5: ネットワークログ"  
[ImagesTutorialRuntime]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-new-resource.msft.png "図 6: ネットワークログの新しいリソース  
[ImagesTutorialDomain]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-edit-column.msft.png "図 7: ドメイン列を有効にする"  
[ImagesTutorialThrottling]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling.msft.png "図 8: 調整を有効にする"  
[ImagesTutorialSlow3G]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling-slow-3g.msft.png "図 9: 低速 3G" の選択  
[ImagesTutorialHardReload]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-empty-cache-and-hard-reset.msft.png "図 10: 空のキャッシュとハードリロード"  
[ImagesTutorialAllScreenshots]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots.msft.png "図 11: ページ読み込みのスクリーンショット"  
[ImagesTutorialFirstScreenshot]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots-first.msft.png "図 12: 最初のスクリーンショットの間に発生したネットワークアクティビティ  
[ImagesTutorialHeaders]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-headers.msft.png "図 13: [ヘッダー] タブ  
[ImagesTutorialPreview]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-preview.msft.png "図 14: [プレビュー] タブ  
[ImagesTutorialResponse]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-response.msft.png "図 15: [応答] タブ  
[ImagesTutorialTiming]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-timing.msft.png "図 16: [タイミング] タブ  
[ImagesTutorialCloseTiming]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-close-tabs.msft.png "図 17: [閉じる] ボタン  
[ImagesTutorialSearch]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-empty.msft.png "図 18: [検索] ウィンドウ  
[ImagesTutorialResults]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control.msft.png "図 19: キャッシュコントロールの検索結果  
[ImagesTutorialCache]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control-headers-response-headers.msft.png "図 20: [ヘッダー] タブで強調表示された検索結果  
[ImagesTutorialCloseButtons]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-close.msft.png "図 21: [閉じる] ボタン  
[ImagesTutorialFilters]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-empty.msft.png "図 22: [フィルター] ツールバー  
[ImagesTutorialPNG]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-png.msft.png "図 23: 文字列フィルター"  
[ImagesTutorialRegEx]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-regex.msft.png "図 24: 正規表現フィルター"  
[ImagesTutorialNegative]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-negative-statement.msft.png "図 25: 負のフィルター"  
[ImagesTutorialProperty]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-property-value.msft.png "図 26: プロパティフィルター"  
[ImagesTutorialCSS]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css.msft.png "Figure 27: CSS ファイルのみを表示しています"  
[ImagesTutorialCSSJS]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css-js.msft.png "図 28: CSS と JS ファイルのみ表示されます"  
[ImagesTutorialCommandMenu]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-empty.msft.png "図 29: コマンドメニュー  
[ImagesTutorialBlock]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block.msft.png "図 30: ブロック要求の表示"  
[ImagesTutorialAddBlock]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-add-pattern.msft.png "図 31: メイン .css をブロックする"  
[ImagesTutorialBlockedStyles]:/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-main-css.msft.png "図 32: メイン .css はブロックされています"  

<!-- links -->  


<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsNetworkReference]: /microsoft-edge/devtools-guide-chromium/network/reference "ネットワーク分析のリファレンス"
[DevtoolsNetworkReferenceFilter]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests "フィルター要求-ネットワーク分析リファレンス"  
[DevtoolsReferenceHideOverview]: /microsoft-edge/devtools-guide-chromium/network/reference#hide-the-overview-pane "概要ウィンドウを非表示にする-ネットワーク分析のリファレンス"
[DevtoolsReferenceProperty]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "プロパティによって要求をフィルター処理する-ネットワーク分析リファレンス"
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワークアクティビティのデモを検査する"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュMDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/network/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
