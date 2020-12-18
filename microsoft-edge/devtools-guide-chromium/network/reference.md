---
description: Microsoft Edge DevTools ネットワーク パネル機能の包括的なリファレンス。
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c600197ffa0e415fe42aecc704a523d1b23f8260
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230755"
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

# ネットワーク分析のリファレンス  

Microsoft Edge DevTools ネットワーク分析機能の包括的なリファレンスで、ページの読み込み方法を分析する新しい方法について説明します。  

## ネットワーク要求を記録する  

既定では、DevTools が開いている限り、DevTools はネットワーク パネルにすべてのネットワーク要求を記録します。 ****  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   [ **ネットワーク]** パネル  
:::image-end:::  

### ネットワーク要求の記録を停止する  

要求の記録を停止するには、次の手順を実行します。  

1.  [ネットワーク] **パネルで** 、[ネットワーク ログの **記録を停止** する] \( [ネットワーク ログの記録 ![ を停止する] ][ImageRecordOnIcon] \) を選択します。  DevTools が要求を記録しなくなった場合は灰色になります。  
1.  ネットワーク `Control` + `E` パネルにフォーカスがある場合は `Command` + `E` 、\(Windows,Linux\)**** または \(macOS\) を選択します。  

### 要求をクリアする  

[**要求]** テーブルからすべての要求をクリアするには、[ネットワーク] パネルで [クリア \ (クリア ![ ][ImageClearIcon] \) ] を選択します。 ****  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   [ **クリア]** ボタン  
:::image-end:::  

### ページの読み込み時に要求を保存する  

ページの読み込み時に要求を保存するには、[ **ネットワーク** ] パネルで [保持ログ] チェック **ボックスをオン** にします。  DevTools は、保持ログを無効にするまで、すべての要求 **を保存します**。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保持] チェック ボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   [ **ログの保持]** チェック ボックス  
:::image-end:::  

### ページ読み込み中のスクリーンショットのキャプチャ  

スクリーンショットをキャプチャして、ページが読み込むのを待っている間にユーザーに表示される画面を分析します。  

スクリーンショットを有効にするには、[ネットワーク**設定]** を選択し****、[ネットワーク] パネルで [スクリーンショットのキャプチャ]**チェック ボックスをオン**にします。  

ネットワーク パネルにフォーカス **がある間に** ページを更新し、スクリーンショットをキャプチャします。  

スクリーンショットをキャプチャした後は、次の方法で操作します。  

*   スクリーンショットをポイントすると、そのスクリーンショットがキャプチャされたポイントが表示されます。  [概要] ウィンドウに黄色の線 **が表示** されます。  
*   スクリーンショットをキャプチャした後に発生した要求をフィルター処理するには、画面のサムネイルを選択します。  
*   サムネイルをダブルクリックして拡大します。  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショットにカーソルを合わせる" lightbox="../media/network-network-screenshot-hover.msft.png":::
   スクリーンショットにカーソルを合わせる  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## 読み込み時の動作を変更する  

### ブラウザー キャッシュを無効にして初回訪問者をエミュレートする  

初めてのユーザーがサイトを体験する方法をエミュレートするには、[キャッシュを無効にする] チェック **ボックスをオン** にします。  DevTools はブラウザー キャッシュを無効にします。  この機能は、初回のユーザー エクスペリエンスをより正確にエミュレートします。これは、要求は繰り返しアクセス時にブラウザー キャッシュから提供されます。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェック ボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   [ **キャッシュを無効にする] チェック** ボックス  
:::image-end:::  

#### ネットワーク条件ドロワーからブラウザー キャッシュを無効にする  

他の DevTools パネルで作業している間にキャッシュを無効にする場合は、ネットワーク条件ドロワーを使用します。  

1.  ネットワーク条件ドロ **ワーを開** きます。  
1.  [キャッシュを無効にする] チェック ボックスをオン **またはオフ** にします。  

<!--todo: add network condition section when available -->  

### ブラウザー キャッシュを手動でクリアする  

ブラウザー キャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキスト メニュー \(右クリック\) を開き、[ブラウザー キャッシュのクリア] を選択 **します**。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="ブラウザー キャッシュのクリアを選択する" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   ブラウザー **キャッシュのクリアを選択する**  
:::image-end:::  

### オフラインでエミュレートする  

新しいクラスの Web アプリ [(Progressive Web Apps)][DevtoolsProgressiveWebApps]は、サービス ワーカーの支援を受け、オフライン **で機能します**。  この種類のアプリを構築するときに、データ接続がないデバイスをすばやくシミュレートすると便利な場合があります。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

[オンライン] **ドロップダウン メニュー** を選択し、[ **プリセット**] で検索し、[ **オフライン** ] を選択してオフライン ネットワーク エクスペリエンスをシミュレートします。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウン メニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   [ **オフライン]** ドロップダウン メニュー  
:::image-end:::  

### 低速ネットワーク接続をエミュレートする  

[オンライン] ドロップダウン メニューからスロー 3G、Fast 3G、その他の接続速度 **を** エミュレートします。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウン メニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   [ **調整]** ドロップダウン メニュー  
:::image-end:::  

スロー 3G や Fast 3G など、さまざまなプリセットから選択できます。  独自のカスタム プリセットを追加するには、[調整] メニューを開き、[カスタム追加]**を選択**  >  **します**。  

DevTools では、[ネットワーク] タブの横に警告アイコンが **表示** され、調整が有効になっていることを通知します。  

#### ネットワーク条件ドロワーからの低速ネットワーク接続をエミュレートする  

他の DevTools パネルで作業している間にネットワーク接続を調整する場合は、ネットワーク条件ドロワーを使用します。  

1.  ネットワーク条件ドロ **ワーを開** きます。  
1.  [調整] メニューから接続速度 **を選択** します。  

<!--todo: add network condition section when available -->  

### ブラウザーの Cookie を手動でクリアする  

ブラウザーの Cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[ブラウザー Cookie のクリア] を選択 **します**。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="ブラウザーの Cookie のクリアを選択する" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   ブラウザー **の Cookie のクリアを選択する**  
:::image-end:::  

### ユーザー エージェントを上書きする  

ユーザー エージェントを手動で上書きするには、次の手順を使用します。  

1.  ネットワーク条件ドロ **ワーを開** きます。  
1.  [自動的に選択 **] チェック ボックスを** オフにします。  
1.  メニューからユーザー エージェント オプションを選択するか、テキスト ボックスにカスタム エージェント オプションを入力します。  

<!--todo: add network condition section when available -->  

## 要求をフィルター処理する  

### プロパティで要求をフィルター処理する  

[フィルター **] テキスト** ボックスを使用して、要求のドメインやサイズなどのプロパティで要求をフィルター処理します。  

テキスト ボックスが表示されていない場合は、[フィルター **]** ウィンドウは非表示である可能性があります。  
詳細については、[フィルター] ウィンドウ [を非表示にするに移動します](#hide-the-filters-pane)。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキスト ボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   [ **フィルター]** テキスト ボックス  
:::image-end:::  

各プロパティをスペースで区切って、複数のプロパティを同時に使用できます。  たとえば、1 キロバイトを超えるすべての `mime-type:image/png larger-than:1K` PNG を表示します。  マルチプロパティ フィルターは操作と同 `AND` じです。  `OR` 操作は現在サポートされていません。  

サポートされているプロパティの完全な一覧。  

| プロパティ | 詳細 |  
|:--- | :--- |  
| `domain` | 指定されたドメインのリソースのみを表示します。  複数のドメインを含めるには、ワイルドカード文字 `*` \( \) を使用できます。  たとえば、終 `*.com` わるすべてのドメイン名のリソースを表示します `.com` 。  DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべてのドメインを設定します。 |  
| `has-response-header` | 指定された HTTP 応答ヘッダーを含むリソースを表示します。  DevTools は、見つかったすべての応答ヘッダーをオートコンプリート ドロップダウンに設定します。 |  
| `is` | リソース `is:running` を検索するために `WebSocket` 使用します。 |  
| `larger-than` | 指定したサイズより大きいリソースをバイト単位で表示します。  値の設定は `1000` 、値を設定するのと同じです `1k` 。 |  
| `method` | 指定された HTTP メソッド型で取得されたリソースを表示します。  DevTools は、見つかったすべての HTTP メソッドをドロップダウンに設定します。 |  
| `mime-type` | 指定された MIME タイプのリソースを表示します。  DevTools は、見つかったすべての MIME タイプをドロップダウンに設定します。 |  
| `mixed-content` | すべての混在コンテンツ リソース \( \) または現在表示されているリソース `mixed-content:all` \( \) を表示 `mixed-content:displayed` します。 |  
| `scheme` | 保護されていない HTTP \( \) または保護された `scheme:http` HTTPS \( \) で取得したリソースを表示 `scheme:https` します。 |  
| `set-cookie-domain` | 指定された値と一致 `Set-Cookie` する属性を持つ `Domain` ヘッダーを持つリソースを表示します。  DevTools は、見つかったすべての Cookie ドメインをオートコンプリートに追加します。 |  
| `set-cookie-name` | 指定された値と一致 `Set-Cookie` する名前のヘッダーを持つリソースを表示します。  DevTools は、見つかったすべての Cookie 名をオートコンプリートに追加します。 |  
| `set-cookie-value` | 指定された値と一 `Set-Cookie` 致する値を持つヘッダーを持つリソースを表示します。  DevTools は、見つかったすべての Cookie 値をオートコンプリートに設定します。 |  
| `status-code` | 特定の HTTP 状態コードに一致するリソースを表示します。  DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべての状態コードを設定します。 |  

### 種類別に要求をフィルター処理する  

要求の種類によって要求をフィルター処理するには、[ネットワーク] パネルで次のいずれかのボタンを **選択** します。  

:::row:::
   :::column span="1":::
      **XHR**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **JS**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **CSS**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Img**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Media**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **フォント**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Doc**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **WS**  
   :::column-end:::
   :::column span="2":::
      WebSocket。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **マニフェスト**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Other**  
   :::column-end:::
   :::column span="2":::
      一覧に表示されないその他の型。  
   :::column-end:::
:::row-end:::  

ボタンが表示されない場合は、[フィルター] **ウィンドウ** が非表示になる場合があります。  
詳細については、[フィルター] ウィンドウ [を非表示にするに移動します](#hide-the-filters-pane)。  

複数の種類のフィルターを同時に有効にするには `Control` 、\(Windows,Linux\) または `Command` \(macOS\) を保持してから選択します。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="Type フィルターを使用して JS、CSS、および Document リソースを表示する" lightbox="../media/network-network-type-filters.msft.png":::
   Type フィルターを使用して JS、CSS、および Document リソースを表示する  
:::image-end:::  

### 時間で要求をフィルター処理する  

[概要] ウィンドウで左または**** 右に選択してドラッグすると、その期間にアクティブだった要求だけが表示されます。  フィルターは包括的です。  強調表示された時間中にアクティブだったすべての要求が表示されます。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="約 300 ミリ秒で非アクティブだったすべての要求をフィルター処理する" lightbox="../media/network-network-overview-filter.msft.png":::
   約 300 ミリ秒で非アクティブだったすべての要求をフィルター処理する  
:::image-end:::  

### データ URL を非表示にする  

[データ URL は、][MDNHTTPDataURIs] 他のドキュメントに埋め込まれた小さなファイルです。  [要求] テーブルに表示される要求は、データ `data:` URL です。  

要求を非表示にする場合は、[データ URL を非表示 **にする] チェック ボックスをオフ** にします。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ URL を非表示にする] チェック ボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   [ **データ URL を非表示にする] チェック** ボックス  
:::image-end:::  

## 要求を並べ替える  

既定では、[Requests] テーブルの要求は開始時刻で並べ替されますが、他の条件を使用してテーブルを並べ替える場合があります。  

### 列で並べ替える  

[要求] 内の任意の列のヘッダーを選択して、その列で要求を並べ替える。  

### アクティビティ フェーズでの並べ替え  

ウォーターフォールで要求を並べ替える方法を変更するには、[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、 **ウォーター**フォールにカーソルを合わせると、次のいずれかのオプションを選択します。  

:::row:::
   :::column span="1":::
      **開始時刻**  
   :::column-end:::
   :::column span="2":::
      最初に開始された要求が一番上にある。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **応答時間**  
   :::column-end:::
   :::column span="2":::
      最初にダウンロードを開始した要求が一番上に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **終了時刻**  
   :::column-end:::
   :::column span="2":::
      完了した最初の要求は一番上です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Total Duration**  
   :::column-end:::
   :::column span="2":::
      最短の接続設定と要求または応答を持つ要求が一番上に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **遅延**  
   :::column-end:::
   :::column span="2":::
      応答の最も短い時間を待った要求が一番上にある。  
   :::column-end:::
:::row-end:::  

これらの説明では、各オプションが最短から最長の間でランク付けされている必要があります。  [ウォーターフォール] 列の **ヘッダーを選択** して、順序を逆にします。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="ウォーターフォールを合計時間で並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   合計時間でウォーターフォールを並べ替える \(各バーの明るい部分は待機時間、暗い部分はバイトのダウンロードに費やされた時間\)  
:::image-end:::  

## 要求を分析する  

DevTools が開いている限り、すべての要求をネットワーク パネルに **記録** します。  
ネットワーク パネルを使用して要求を分析します。  

### 要求のログを表示する  

DevTools が開いている間に行われたすべての要求のログを表示するには、Requests テーブルを使用します。  各アイテムに関する詳細な情報を表示するには、要求を選択またはホバーします。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="要求テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   要求テーブル  
:::image-end:::  

既定では、[要求] テーブルには次の列が表示されます。  

:::row:::
   :::column span="1":::
      **名前**  
   :::column-end:::
   :::column span="2":::
      リソースのファイル名または識別子。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ステータス**  
   :::column-end:::
   :::column span="2":::
      HTTP 状態コード。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **型**  
   :::column-end:::
   :::column span="2":::
      要求されたリソースの MIME タイプ。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Initiator**  
   :::column-end:::
   :::column span="2":::
      次のオブジェクトまたはプロセスが要求を開始します。  
      
      *   **パーサー**  Microsoft Edge の HTML パーサー。  
      *   **リダイレクト**  HTTP リダイレクト。  
      *   **スクリプト**  JavaScript 関数。  
      *   **その他**  リンクを使用してページに移動したり、アドレス バーに URL を入力したりなど、その他のプロセスまたはアクション。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Size**  
   :::column-end:::
   :::column span="2":::
      サーバーによって配信される応答ヘッダーと応答本文の合計サイズ。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **時間**  
   :::column-end:::
   :::column span="2":::
      要求の開始から、応答の最後のバイトの受信まで、合計時間。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [ウォーターフォール](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      各要求のアクティビティの視覚的な内訳。  
   :::column-end:::
:::row-end:::  

#### 列を追加または削除する  

[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、表示または非表示にするオプションを選択します。  現在表示されているオプションでは、各項目の横にチェックマークが付きます。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="[要求] テーブルに列を追加する" lightbox="../media/network-network-requests-add-column.msft.png":::
   [要求] テーブルに列を追加する  
:::image-end:::  

#### カスタム列を追加する  

要求テーブルにカスタム列を追加するには、[要求] テーブルのヘッダーにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\)**** を開き、[応答ヘッダーヘッダーのヘッダー列の管理] を選択します  >  ****。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルにカスタム列を追加する" lightbox="../media/network-network-requests-add-custom.msft.png":::
   要求テーブルにカスタム列を追加する  
:::image-end:::  

### 要求のタイミング関係を表示する  

ウォーターフォールを使用して、要求のタイミング関係を表示します。  
ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。  
したがって、左側の要求は、右側の要求よりも早く開始されます。  

ウォーターフォールを並べ替えるさまざまな方法を確認するには、[アクティビティ別に並べ替え] [フェーズに移動します](#sort-by-activity-phase)。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウのウォーターフォール列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   [要求] ウィンドウの **ウォーターフォール** 列  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   The **Frames** tab  
:::image-end:::  
-->

<!--The table contains the following three columns.  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to each type.  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### 応答本文のプレビューを表示する  

応答本文のプレビューを表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [プレビュー] **タブを選択** します。  

[プレビュー] タブは、画像を表示する場合に最も便利です。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-network-resources-preview.msft.png":::
   **プレビュー** タブ  
:::image-end:::  

### 応答本文を表示する  

要求に応答本文を表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [応答] **タブを選択** します。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-network-resources-response.msft.png":::
   **応答** タブ  
:::image-end:::  

### HTTP ヘッダーを表示する  

要求に関する HTTP ヘッダー データを表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [ヘッダー **] タブを選択** します。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-resources-headers.msft.png":::
   **ヘッダー** タブ  
:::image-end:::  

#### HTTP ヘッダー ソースの表示  

既定では、[ヘッダー] タブにはヘッダー名がアルファベット順に表示されます。  HTTP ヘッダー名を受け取った順序で表示するには、次の手順を使用します。  

1.  関心のある **要求** の [ヘッダー] タブを開きます。  詳細については、「HTTP ヘッダーを表示 [する」に移動します](#display-http-headers)。  
1.  [**要求ヘッダー] セクションまたは**[応答ヘッダー] セクションの横にあるビュー**ソースを選択**します。 ****  

### クエリ文字列パラメーターを表示する  

URL のクエリ文字列パラメーターを人間が判読できる形式で表示するには、次の手順を使用します。  

1.  関心のある **要求** の [ヘッダー] タブを開きます。  詳細については、「HTTP ヘッダーを表示 [する」に移動します](#display-http-headers)。  
1.  [クエリ文字列パラメーター **] セクションに移動** します。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列パラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   [ **クエリ文字列パラメーター]** セクション  
:::image-end:::  

#### クエリ文字列パラメーター ソースを表示する  

要求のクエリ文字列パラメーター ソースを表示するには、次の手順を使用します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、クエリ文字列パラメーター [を表示するに移動します](#display-query-string-parameters)。  
1.  ビュー **ソースを選択します**。  

#### URL エンコードされたクエリ文字列パラメーターを表示する  

クエリ文字列パラメーターを人間が読み取り可能な形式で表示し、エンコードを保持するには、次の手順を使用します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、クエリ文字列パラメーター [を表示するに移動します](#display-query-string-parameters)。  
1.  エンコード **されたビュー URL を選択します**。  

### Cookie の表示  

要求の HTTP ヘッダーで送信された Cookie を表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [Cookie] **タブを選択** します。  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] タブ" lightbox="../media/network-network-resources-cookies.msft.png":::
   [Cookie] タブ  
:::image-end:::  

### 要求のタイミングの内訳を表示する  

要求のタイミングの内訳を表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [タイミング **] タブを選択** します。  

データに高速にアクセスするには、[タイミングの詳細をプレビューする [] に移動します](#preview-a-timing-breakdown)。  

[タイミング] タブに表示される各フェーズの詳細については、説明**** されているタイミングブレークダウン フェーズ[に移動します](#timing-breakdown-phases-explained)。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-network-resources-timing.msft.png":::
   **タイミング** タブ  
:::image-end:::  

各フェーズの詳細。  

表示にアクセスする方法の詳細については、[表示タイミングの詳細 [] に移動します](#display-the-timing-breakdown-of-a-request)。  

#### タイミングの詳細をプレビューする  

要求のタイミングの詳細のプレビューを表示するには、[要求] テーブルの **[ウォーター** フォール] 列で、要求のエントリをポイントします。  

ホバーせずにデータにアクセスする方法の詳細については、「要求のタイミングの内訳を表示 [する」に移動します](#display-the-timing-breakdown-of-a-request)。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">要求のタイミングの詳細をプレビューする" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   要求のタイミングの詳細をプレビューする  
:::image-end:::  

#### 説明されているタイミングブレークダウン フェーズ  

[タイミング] タブに表示される各フェーズ**の詳細。**  

:::row:::
   :::column span="1":::
      **キューに入る**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、次の場合に要求をキューに入れられます。  
      
      *   優先度の高い要求が存在します。  
      *   同じオリジンに対して 6 つの TCP 接続が開いている。これは制限です。  HTTP/1.0 および HTTP/1.1 にのみ適用されます。  
      *   ブラウザーは、ディスク キャッシュ内の領域を一時的に割り当て中です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ストール**  
   :::column-end:::
   :::column span="2":::
      要求は、「キュー」で説明されている理由の何らかの理由で **ストールします**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **DNS 参照**  
   :::column-end:::
   :::column span="2":::
      ブラウザーが要求の IP アドレスを解決しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **初期接続**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、TCP ハンドシェイク、TCP 再試行、および Secure Socket Layer のネゴシエートを含む接続を確立します。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プロキシ ネゴシエーション**  
   :::column-end:::
   :::column span="2":::
      ブラウザーがプロキシ サーバーと要求をネゴ [シエートしています][WikiProxyServer]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **送信された要求**  
   :::column-end:::
   :::column span="2":::
      要求が送信されています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ServiceWorker の準備**  
   :::column-end:::
   :::column span="2":::
      ブラウザーがサービス ワーカーを開始しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ServiceWorker への要求**  
   :::column-end:::
   :::column span="2":::
      要求はサービス ワーカーに送信されています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Waiting \(TTFB\)**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは応答の最初のバイトを待機しています。  TTFB は、Time To First Byte を表します。  このタイミングには、1 回の待機時間と、サーバーが応答の準備にかかった時間が含まれます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **コンテンツのダウンロード**  
   :::column-end:::
   :::column span="2":::
      ブラウザーが応答を受信しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プッシュの受信**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは HTTP/2 サーバー プッシュを介してこの応答のデータを受信しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プッシュ読み取り**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、以前に受信したローカル データを読み取り中です。  
   :::column-end:::
:::row-end:::  

### 開始者と依存関係を表示する  

要求の開始者と依存関係を表示するには、[要求] テーブルで要求を保持して `Shift` ポイントします。  DevTools の色: 開始者は緑色で表示され、依存関係は赤で表示されます。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求の開始者と依存関係を表示する" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   要求の開始者と依存関係を表示する  
:::image-end:::  

時間順に Requests テーブルが並べらた場合、行にカーソルを合わせると、前の行に緑色の要求が表示されます。  緑色の要求は、依存関係の開始者です。  それより前の行に別の緑色の要求が表示される場合、その上位の要求は開始者の開始者になります。  などなど。  

### 読み込みイベントを表示する  

DevTools は、ネットワーク パネル上の複数の場所にイベントの `DOMContentLoaded` `load` タイミングを **表示** します。  イベント `DOMContentLoaded` は青色で、イベントは `load` 赤です。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded の場所とネットワーク パネル上のイベントの読み込み" lightbox="../media/network-network-requests-load-events.msft.png":::
   ネットワーク パネル上 `DOMContentLoaded` の `load` イベント **の** 場所  
:::image-end:::  

### 要求の総数を表示する  

要求の総数は、[ネットワーク] パネルの下部**** にある [概要] ウィンドウに**表示**されます。  

> [!CAUTION]
> この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。  DevTools が開く前に他の要求が発生した場合、それらの要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開いた後の要求の総数" lightbox="../media/network-network-total-requests.msft.png":::
   DevTools が開いた後の要求の総数  
:::image-end:::  

### ダウンロード の合計サイズを表示する  

要求の合計ダウンロード サイズは、[概要] ウィンドウ**** の [ネットワーク] パネルの下部に**一覧表示**されます。  

> [!CAUTION]
> この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。  DevTools が開く前に他の要求が発生した場合、以前の要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="要求の合計ダウンロード サイズ" lightbox="../media/network-network-total-download-size.msft.png":::
   要求の合計ダウンロード サイズ  
:::image-end:::  

ブラウザーが各アイテムの圧縮を解除した後のリソースの大きさを確認するには、リソースの圧縮されていないサイズを表示 [します](#display-the-uncompressed-size-of-a-resource)。  

### 要求を発生したスタック トレースを表示する  

JavaScript ステートメントがリソースを要求した後 **、Initiator** 列をポイントして、要求に至るスタック トレースを表示します。  

<!-- [codepen.io/contoso/pen/yLBrOWa?editors=0010#0](https://codepen.io/contoso/pen/yLBrOWa?editors=0010#0) -->  

<!--
```javascript
function init() {
  getData();
}

function getData() {
  fetch('https:/httpbin.org/get?message=hi');
}

init();
```  
-->  

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="リソース要求に至るスタック トレース" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   リソース要求に至るスタック トレース  
:::image-end:::  

### リソースの圧縮されていないサイズを表示する  

[大きな要求 **行を使用する]** チェック ボックスをオンにし、[サイズ] 列の一番下の値 **を確認** します。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="圧縮されていないリソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   圧縮されていないリソース \(ネットワーク上で送信されたファイルの圧縮されたサイズは `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \) の例です。  
:::image-end:::  

## 要求データをエクスポートする  

### すべてのネットワーク要求を HAR ファイルに保存する  

すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。  

1.  [要求] テーブル内の任意の要求をポイントし、コンテキスト メニュー \(右クリック\) を開きます。  
1.  Choose **Save as HAR with Content**.  DevTools は、DevTools を開いた後に発生した要求を HAR ファイルに保存します。  要求をフィルター処理できない。  また、1 つの要求を保存する必要があります。  

HAR ファイルを保存したら、分析のために DevTools にインポートし戻します。  HAR ファイルを Requests テーブルにドラッグ アンド ドロップします。  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="Choose Save as HAR with Content" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   Choose **Save as HAR with Content**  
:::image-end:::  

### 1 つ以上の要求をクリップボードにコピーする  

[要求****] テーブルの [名前] 列で、要求をポイントし、コンテキスト メニュー \(右クリック\) を開き、[コピー] をポイントして、次のいずれかのオプションを選択します。 ****  

| 名前 | 詳細 |  
|:--- |:--- |  
| **リンク アドレスのコピー** | 要求の URL をクリップボードにコピーします。 |  
| **応答のコピー** | 応答本文をクリップボードにコピーします。 |  
| **フェッチとしてコピー** | &nbsp; |  
| **cURL としてコピー** | 要求を cURL コマンドとしてコピーします。 |  
| **すべてフェッチとしてコピー** | &nbsp; |  
| **すべて cURL としてコピー** | すべての要求を cURL コマンドのチェーンとしてコピーします。 |  
| **Copy All as HAR** | すべての要求を HAR データとしてコピーします。 |  

<!--
:::row:::
   :::column span="1":::
      **Copy Link Address**  
   :::column-end:::
   :::column span="2":::
      Copy the URL of the request to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy Response**  
   :::column-end:::
   :::column span="2":::
      Copy the response body to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy the request as a cURL command.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as a chain of cURL commands.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as HAR**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as HAR data.  
   :::column-end:::
:::row-end:::  
-->  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="Choose Copy Response" lightbox="../media/network-network-requests-copy-response.msft.png":::
   Choose **Copy Response**  
:::image-end:::  

### 書式設定された応答 JSON をクリップボードにコピーする  

ネットワーク要求を選択し、[ヘッダー] ウィンドウ **に移動** します。  応答の JSON 値をコピーするには、[要求**** ペイロード] に移動し、JSON 応答コンテンツにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[値のコピー] を選択**します**。  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="コンテキスト メニューの [値のコピー]" lightbox="../media/network-header-copy-property-value.msft.png":::
          **コンテキスト メニューの [値** のコピー]  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Visual Studio応答 JSON を含むコード" lightbox="../media/network-header-paste-property-value.msft.png":::
          書式設定された応答 JSON を Visual Studio コードに貼り付け  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### ネットワーク要求からクリップボードにプロパティ値をコピーする  

ネットワーク要求からクリップボードにプロパティ値をコピーするには、次の操作を実行します。  

1.  [ヘッダー **] ウィンドウを開** きます。  
1.  次のいずれかのヘッダー セクションを開きます。  
    *   要求ペイロード \(JSON\)  
    *   フォーム データ  
    *   クエリ文字列パラメーター  
    *   要求ヘッダー  
    *   応答ヘッダー  
1.  コンテキスト メニュー \(右クリック\) を開き、[値を> **します**。  これで、任意のエディターに値を貼り付け、確認できます。  
    
## ネットワーク パネルのレイアウトを変更する  

ネットワーク パネル UI のセクションを展開または折りたたみ、 **重要な情報** に集中することができます。  

### [フィルター] ウィンドウを非表示にする  

既定では、DevTools には [フィルター] ウィンドウ **が表示** されます。  
Choose **Filter** \( ![ Filter ][ImageFilterIcon] \) to hide it.  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   [フィルターの非表示] ボタン  
:::image-end:::  

### 大きな要求行を使用する  

ネットワーク要求テーブルに空白を追加する場合は、大きな行を使用します。  一部の列は、大きな行を使用する場合に、もう少し多くの情報を提供します。  たとえば、[Size] 列の下部**** の値は、要求の圧縮されていないサイズです。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="[要求] ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   [要求] ウィンドウの大きな要求行 **の** 例  
:::image-end:::  

大きい行を有効にするには、[大きい要求行を使用 **する] チェック ボックスをオン** にします。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行を使用する] チェック ボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   [ **大きな要求行を使用する] チェック** ボックス  
:::image-end:::  

### [概要] ウィンドウを非表示にする  

既定では、DevTools には [概要] ウィンドウ **が表示** されます。  非表示にする場合は、[概要の表示 **] チェック ボックスをオフ** にします。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェック ボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   [ **概要の表示]** チェック ボックス  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "段階的な Web アプリをデバッグする |Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ URL |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシ サーバー - Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
