---
description: Microsoft Edge DevTools の最も一般的なネットワーク関連機能のチュートリアルです。
title: Microsoft Edge DevTools でネットワーク アクティビティを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 16b60716c91d2f4ce778f1fac37afc0e73e30ab6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398659"
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

# <a name="inspect-network-activity-in-microsoft-edge-devtools"></a>Microsoft Edge DevTools でネットワーク アクティビティを検査する  

これは、最も一般的な DevTools 機能のいくつかの実践的なチュートリアルで、ページのネットワーク アクティビティの検査に関連しています。  

機能を参照する場合は、[ネットワーク参照] [に移動します][DevtoolsNetworkReference]。  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <a name="when-to-use-the-network-panel"></a>ネットワーク パネルを使用する場合  

通常、リソースが予期したとおりにダウンロードまたはアップロードされるようにする必要がある場合にネットワーク パネルを使用します。  ネットワーク パネルの最も一般的なユースケースは、次のとおりです。  

*   リソースが実際にすべてアップロードまたはダウンロードされていることを確認する。  
*   HTTP ヘッダー、コンテンツ、サイズなど、個々のリソースのプロパティを検査する。  
    
ページ読み込みパフォーマンスを向上させる方法を探している場合は、ネットワーク**ツールを****使用して開始**してください。  ネットワーク アクティビティに関連しない読み込みパフォーマンスの問題には、さまざまな種類があります。  ページを改善する方法についての対象候補が表示されるので、監査パネルから開始します。  [Web サイト [の速度の最適化] に移動します][DevtoolsSpeedGetStarted]。  

## <a name="open-the-network-panel"></a>ネットワーク パネルを開く  

このチュートリアルを最大限に活用するには、デモを開いてデモのページで機能を試してみてください。  

1.  [デモを開始する][GlitchNetworkGetStarted]を開きます。  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="デモ" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       デモ  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  [DevTools を開く][DevToolsOpen]には `Control` + `Shift` + `J` 、[\(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  コンソール **ツールが** 開きます。  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="コンソール" lightbox="../media/network-glitch-console.msft.png":::
       **コンソール**  
    :::image-end:::  
    
    [ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]することをお勧めします。  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       ウィンドウの下部にドッキングされた DevTools  
    :::image-end:::  
    
1.  ネットワーク ツール **を開** きます。  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="ウィンドウの下部にドッキングされた DevTools のコンソール ツール" lightbox="../media/network-glitch-network-bottom.msft.png":::
       ウィンドウの下部にドッキングされた DevTools の**コンソール**ツール  
    :::image-end:::  
    
現在、ネットワーク **ツール** は空です。  DevTools は、開始された場合のみネットワークアクティビティを記録し、DevTools を開始してからはネットワーク アクティビティは発生しません。  

## <a name="log-network-activity"></a>ネットワーク アクティビティをログする  

ページによって発生するネットワークアクティビティを表示するには、次の操作を行います。  

1.  Web ページを更新します。  ネットワーク パネルでは、**ネットワーク ログ**にすべてのネットワークアクティビティが記録されます。  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="ネットワーク ログ" lightbox="../media/network-glitch-network.msft.png":::
       **ネットワーク ログ**  
    :::image-end:::  
    
    **ネットワークログ**の各行は、リソースを表します。  既定では、リソースは時系列順に表示されます。  トップリソースは、通常、メインの HTML 文書です。  一番下のリソースは、最後にリクエストされたものです。  
    
    各列は、リソースに関する情報を表します。  前の図では、既定の列が表示されています。  

    *   **状態**。  応答用の HTTP 状態コード。  
    *   **種類**。  リソースの種類。  
    *   **イニシエーター**。  リソースによるリクエストの原因。  [イニシエーター] 列のリンクを CHoosing すると、要求の原因となるソース コードが表示されます。  
    *   **時刻**。  リクエストの期間。  
    *   **ウォーター フォール**。  リクエストの異なるステージのグラフィカル表現。  内訳を表示するには、ウォーターフォールにカーソルを合わせる。  
    
    > [!NOTE]
    > ネットワーク ログの上のグラフは概要と呼ばれています。  このチュートリアルの概要グラフは使用しないため、非表示にすることができます。  [概要] [ウィンドウを非表示にするに移動します][DevtoolsReferenceHideOverview]。
    
1.  DevTools を開くと、ネットワーク ログにネットワークアクティビティが記録されます。  
    これを実践するには、まず **ネットワーク ログ** の下部を確認し、最後のアクティビティを頭で記録します。  
1.  次に、デモで **データ取得** ボタンを選択します。  
1.  もう一度 **ネットワーク ログ** の下部を確認します。  という名前の新しいリソース `getstarted.json` が表示されます。  Web ページでファイルを要求するには、[データの取得] **ボタンを選択** します。  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="ネットワーク ログの新しいリソース" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       **ネットワーク ログ**の新しいリソース  
    :::image-end:::  
    
## <a name="show-more-information"></a>詳細情報を表示する  

ネットワークログの列は構成可能です。  使用していない列を非表示にすることができます。  
既定では非表示になっていますが、役に立つと思われる列も数多くあります。  

1.  ネットワーク ログ テーブルのヘッダーにカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[ドメイン] を **選択します**。  各リソースのドメインが表示されるようになりました。  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="ドメインの列を有効にする" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       ドメインの列を有効にする  
    :::image-end:::  
    
    > [!TIP]
    > リソースの完全な URL を確認するには、[名前] 列のセルにマウス ポインター **を置** きます。  
    
## <a name="simulate-a-slower-network-connection"></a>低速ネットワーク接続のシミュレーション  

サイトの構築に使用するコンピューターのネットワーク接続は、おそらく、ユーザーのモバイルデ バイスのネットワーク接続よりも高速です。  ページを調整して、モバイル デバイスでページが読み込まれるまでの時間を把握することができます。  

1.  [調整 **] ドロップダウンを選択** します。これは既定で **[オンライン] に** 設定されています。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="調整を有効にする" lightbox="../media/network-glitch-network-throttling.msft.png":::
       調整を有効にする  
    :::image-end:::  
    
1.  **スロー (低速) 3G** を選びます。  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="[低速 3G] を選択する" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       [低速 3G] を選択する  
    :::image-end:::  
    
1.  **再読み込み** \(![再読み込み][ImageRefreshIcon]\) を長押しして **キャッシュを空にして再読み込み** を選びます。  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="キャッシュを空にして再読み込み" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **キャッシュを空にして再読み込み**  
    :::image-end:::  
    
    繰り返しアクセスした場合、ブラウザーは通常 [キャッシュ][MDNHTTPCache] の一部のファイルを提供します。これにより、ページの読み込みが高速化します。  **キャッシュを空にして再読み込み** で、ブラウザーは強制的にすべてのリソースのネットワークにアクセスします。  初めての訪問者がページの読み込み方法を表示するために使用します。  
    
    > [!NOTE]
    > **キャッシュを空にして再読み込み** ワークフローは、DevTools を開いている場合にのみ使用できます。  
    
## <a name="capture-screenshots"></a>スクリーンショットをキャプチャする  

スクリーンショットは、Web ページの読み込み中の時間の表示方法を表示します。  

1.  [\( ![ Network settings ][ImageSettingsIcon] \) を選択し、[スクリーンショットのキャプチャ] **チェック ボックスをオン** にします。
1.  [空のキャッシュとハードリロード] **ワークフローを使用してページを再び更新** します。  これを行 [う方法に関するリマインダー](#simulate-a-slower-network-connection) が必要な場合は、[低速の接続をシミュレートする] に移動します。  
    [スクリーンショット] パネルには、読み込みプロセス中にページがさまざまなポイントを見た方法のサムネイルが表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="ページの読み込みのスクリーンショット" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       ページの読み込みのスクリーンショット  
    :::image-end:::  
    
1.  最初のサムネイルを選択します。  DevTools では、その地点で発生しているネットワーク アクティビティが表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="最初のスクリーンショット中に発生したネットワーク アクティビティ" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       最初のスクリーンショット中に発生したネットワーク アクティビティ  
    :::image-end:::  
    
1.  [\( Network settings \) を再度選択し、[スクリーンショットのキャプチャ] チェック ボックスをオフにして [スクリーンショット ![ ][ImageSettingsIcon] ] ウィンドウを閉じます。 ****
1.  ページを再び更新します。  
    
## <a name="inspect-the-details-of-the-resource"></a>リソースの詳細を検査する  

リソースを選択して、そのリソースの詳細を確認します。  今すぐお試しください:  

1.  を選択します `getstarted.html` 。  [ **ヘッダー]** パネルが表示されます。  このパネルを使用して HTTP ヘッダーを検査します。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       [ **ヘッダー]** パネル  
    :::image-end:::  
    
1.  [プレビュー] **パネルを選択** します。  HTML の基本的なレンダリングが表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text="[プレビュー] パネル" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       [ **プレビュー]** パネル  
    :::image-end:::  
    
    パネルは、API が HTML でエラー コードを返す場合に役立ちます。  HTML ソースコードよりも、または画像を検査する場合よりも、レンダリングされた HTML の方が読みやすいと思われるかもしれません。  

1.  [応答] **パネルを選択** します。  HTML ソース コードが表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="[応答] パネル" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       [ **応答]** パネル  
    :::image-end:::  
    
    > [!TIP]
    > ファイルが minified の場合は、[応答] パネルの下部にある [Format **\(** Format \)] ボタンを選択して、ファイルの内容を読みやすさのために再 ![ ][ImageFormatIcon] フォーマットします。 ****  
    
1.  [タイミング] **パネルを選択** します。  リソースのネットワーク アクティビティの内訳が表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="[タイミング] パネル" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       [ **タイミング]** パネル  
    :::image-end:::  
    
1.  **閉じる** \(![閉じる][ImageCloseIcon]\) を選択して、もう一度ネットワーク ログを表示します。  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       **閉じる** ボタン  
    :::image-end:::  
    
## <a name="search-network-headers-and-responses"></a>ネットワークのヘッダーと返信を検索する  

特定の文字列または正規表現に関するすべてのリソースの HTTP ヘッダーと応答を検索する必要がある場合は、**検索** ウィンドウを使用します。  

たとえば、リソースが適切な **キャッシュポリシー** を使用していることを確認する必要があるとします。  

<!--TODO: add cache policies section when available  -->

1.  **検索** \(![検索][ImageSearchIcon]\) を選びます。  [検索] ウィンドウがネットワーク ログの左側に表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="[検索] ウィンドウ" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       **検索** ウィンドウ  
    :::image-end:::  
    
1.  `Cache-Control` を入力して、`Enter` を選択します。  [検索] ウィンドウには、リソース ヘッダーまたはコンテンツ内で見つかった `Cache-Control` のすべてのインスタンスが一覧表示されます。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="キャッシュ コントロールの検索結果" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       検索結果 `Cache-Control`  
    :::image-end:::  
    
1.  結果を選択して、結果が見つかったリソースを表示します。  リソースの詳細を参照している場合は、結果を選択して直接移動します。  たとえば、クエリがヘッダーで見つかった場合は、[ヘッダー] **パネルが** 開きます。   クエリがコンテンツで見つかった場合は、[応答 **] パネルが** 開きます。  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="[ヘッダー] パネルで強調表示された検索結果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       [ヘッダー] パネルで強調表示された**検索結果**  
    :::image-end:::  
    
1.  [検索] ウィンドウと [ヘッダー] パネル **を閉** じます。  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="[閉じる] ボタン" lightbox="../media/network-glitch-network-search-close.msft.png":::
       **閉じる** ボタン  
    :::image-end:::  
    
## <a name="filter-resources"></a>リソースをフィルター処理する  

DevTools には、タスクに直接関連していないリソースをフィルター処理する多数のワークフローが用意されています。  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="[フィルター] ツールバー" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   **フィルター** ツールバー  
:::image-end:::  

既定 **では、[フィルター** ] ツールバーをオンにします。  そうでなければ：  

1.  **フィルター** \(![フィルター][ImageFilterIcon]\) を選んで表示します。  
    
### <a name="filter-by-string-regular-expression-or-property"></a>文字列、正規表現、またはプロパティによってフィルターする  

**フィルター** テキスト ボックスでは、さまざまな種類のフィルターがサポートされています。  

1.  `png` を **フィルター** テキストボックスに入力します。  テキスト `png` が含まれているファイルだけが表示されます。  この場合、フィルターに一致するファイルは PNG 画像のみです。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="文字列フィルター" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       文字列フィルター  
    :::image-end:::  
    
1.  「`/.*\.[cj]s+$/`」と入力します。  DevTools では、末尾が `j` または `c` で終わらず、1つ以上の`s`文字が続いているファイル名で任意のリソースをフィルター処理 します。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正規表現フィルター" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       正規表現フィルター  
    :::image-end:::  
    
1.  「`-main.css`」と入力します。  DevTools で `main.css` をフィルターします。  パターンに一致するファイルがある場合は、tit もフィルター処理されます。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="ネガティブ フィルター" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       ネガティブ フィルター  
    :::image-end:::  
    
1.  `domain:cdn.glitch.com` を **フィルター処理** テキスト ボックスに入力します。  DevTools では、このドメインと一致しない URL のリソースをフィルター処理します。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="プロパティ フィルター" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       プロパティ フィルター  
    :::image-end:::  
    
    フィルター可能なプロパティの完全な一覧については、[プロパティで要求 [をフィルター処理する] に移動します][DevtoolsReferenceProperty]。  
    
1.  任意のテキストのテキスト ボックスを **フィルター処理** をクリアします。  
    
### <a name="filter-by-resource-type"></a>リソースの種類でフィルター処理する  

スタイルシートなど、特定の種類のファイルに重点を置く場合は、次の操作を行います。  

1.  **CSS** を選びます。  その他のすべての種類のファイルはフィルター処理されます。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="CSS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       CSS ファイルのみを表示する  
    :::image-end:::  
    
1.  スクリプトも表示するには `Control` 、\(Windows、Linux\) または `Command` \(macOS\) を選択して保持し **、[JS] を選択します**。  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="CSS と JS ファイルのみを表示する" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       CSS と JS ファイルのみを表示する  
    :::image-end:::  
    
1.  フィルターを削除してすべてのリソースを再度表示するには、[すべて] を **選択します**。  
    
その他のフィルター ワークフローについては、[要求のフィルター [] に移動します][DevtoolsNetworkReferenceFilter]。  

## <a name="block-requests"></a>リクエストをブロック  

ページリソースの一部が利用できない場合、ページはどのように表示され、どのように動作しますか?  完全に失敗しましたか? それとも、まだ機能していますか?  リクエストをブロックして、以下の内容を見つけます:  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="コマンド メニュー" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       **コマンド メニュー**  
    :::image-end:::  
    
1.  `block` と入力して、**リクエストのブロックを表示** を選択してから、`Enter` を選択します。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="リクエストのブロックを表示" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **リクエストのブロックを表示**  
    :::image-end:::  
    
1.  **パターンを追加** \(![パターンを追加][ImageAddIcon]\) を選びます。  
1.  「`main.css`」と入力します。  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="メインの.css をブロックする" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       ブロッキング `main.css`  
    :::image-end:::  
    
1.  **追加** を選びます。  
1.  ページを最新の情報に更新してください。  予想どおり、メインのスタイルシートがブロックされているため、ページのスタイルがあまりよくありません。  
    
    > [!NOTE]
    > ネットワーク ログの `main.css` 行。  赤いテキストは、リソースがブロックされたことを意味します。
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="メインの.css がブロックされています" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` ブロックされています  
    :::image-end:::  
    
1.  **リクエストのブロックを有効にする** チェックボックスをオフにします。  

## <a name="conclusion"></a>まとめ  

おめでとうございます。これでチュートリアルは完了です。  これで、Microsoft Edge DevTools でネットワーク ツールを使用する方法がわかっています。 ****

[ネットワーク リファレンス][DevtoolsNetworkReference] に移動して、ネットワーク アクティビティの調査に関連するその他の DevTools 機能を見つけます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームに連絡する  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddIcon]: ../media/add-icon.msft.png  
[ImageCloseIcon]: ../media/close-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: ../media/screenshots-icon.msft.png  
[ImageSearchIcon]: ../media/search-icon.msft.png  
[ImageSettingsIcon]: ../media/settings-icon.msft.png

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "ネットワーク分析のリファレンス | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "フィルターのリクエスト - ネットワーク分析リファレンス | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "概要ウィンドウを非表示 - ネットワーク分析リファレンス | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "プロパティによるリクエストをフィルター処理 - ネットワーク分析のリファレンス | Microsoft Docs"
[DevToolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して web サイトの速度を最適化 | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "ネットワーク アクティビティのデモを検査 | グリッチ"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP キャッシュ | MDN"  

> [!NOTE]
> このページの一部は、 [Google によって][GoogleSitePolicies] 作成および共有され、 [クリエイティブ コモンズ 4.0 インターナショナル ライセンス][CCA4IL]で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
