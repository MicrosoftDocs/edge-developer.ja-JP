---
description: Microsoft Edge DevTools ネットワーク パネル機能の包括的な参照。
title: ネットワーク分析リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 94a7031763da1e540b4dab802358e5f200e0db4a
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439704"
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

# <a name="network-analysis-reference"></a>ネットワーク分析リファレンス  

Microsoft Edge DevTools ネットワーク分析機能の包括的なリファレンスで、ページの読み込み方法を分析する新しい方法について説明します。  

## <a name="record-network-requests"></a>ネットワーク要求を記録する  

既定では、DevTools が開いている限り、DevTools はネットワーク ツール内のすべてのネットワーク要求を記録します。 ****  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   ネットワーク**ツール**  
:::image-end:::  

### <a name="stop-recording-network-requests"></a>ネットワーク要求の記録を停止する  

要求の記録を停止するには、次の手順を実行します。  

1.  ネットワーク ツール **で、[** ネットワーク ログの記録 **を停止する** ] \( [ネットワーク ログの記録 ![ を停止する ](../media/record-on-icon.msft.png) ] \) を選択します。  DevTools が要求を記録しなくなった場合は灰色になります。  
1.  ネットワーク `Control` + `E` ツールのフォーカス中に `Command` + `E` [\(Windows,Linux\)**** または \(macOS\) を選択します。  

### <a name="clear-requests"></a>要求をクリアする  

[**要求]** テーブルからすべての要求をクリアするには、[ネットワーク] ツールで [\( Clear ![ ](../media/clear-requests-icon.msft.png) \) をクリアする] を選択します。 ****  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   [ **クリア]** ボタン  
:::image-end:::  

### <a name="save-requests-across-page-loads"></a>ページの読み込み中に要求を保存する  

ページ読み込み時に要求を保存**** するには、[ネットワーク] ツールで 、[ログの保持] チェック**ボックスをオン**にします。  DevTools は、ログの保持を無効にするまで、すべての要求 **を保存します**。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保持] チェック ボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   [ **ログの保持]** チェック ボックス  
:::image-end:::  

### <a name="capture-screenshots-during-page-load"></a>ページの読み込み中にスクリーンショットをキャプチャする  

スクリーンショットをキャプチャして、ページの読み込み待ち中にユーザーの表示を分析します。  

スクリーンショットを有効にするには、[ネットワーク設定]**を**選択し****、[ネットワーク] ツールで 、[スクリーンショットのキャプチャ]**チェック ボックスをオン**にします。  

ネットワーク ツールがフォーカス **されている間に** ページを更新して、スクリーンショットをキャプチャします。  

スクリーンショットをキャプチャした後、次の方法で操作します。  

*   スクリーンショットにカーソルを合わせると、そのスクリーンショットがキャプチャされたポイントが表示されます。  [概要] ウィンドウに黄色の線 **が表示** されます。  
*   スクリーンのサムネイルを選択して、スクリーンショットのキャプチャ後に発生した要求をフィルター処理します。  
*   サムネイルをダブルクリックして拡大表示します。  

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

## <a name="change-loading-behavior"></a>読み込み動作の変更  

### <a name="emulate-a-first-time-visitor-by-disabling-the-browser-cache"></a>ブラウザー キャッシュを無効にして初めての訪問者をエミュレートする  

初めてのユーザーがサイトを体験する方法をエミュレートするには、[キャッシュを無効にする] **チェック ボックスをオン** にします。  DevTools はブラウザー キャッシュを無効にします。  この機能は、繰り返し訪問時にブラウザー キャッシュから要求が提供されるので、初めてのユーザー エクスペリエンスをより正確にエミュレートします。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェック ボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   [ **キャッシュを無効にする]** チェック ボックス  
:::image-end:::  

#### <a name="disable-the-browser-cache-from-the-network-conditions-drawer"></a>ネットワーク条件ドロワーからブラウザー キャッシュを無効にする  

他の DevTools パネルで作業している間にキャッシュを無効にする場合は、ネットワーク条件ドロワーを使用します。  

1.  [ネットワーク条件 **] ドロワーを開** きます。  
1.  [キャッシュを無効にする] チェック ボックスをオン **にします** 。  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-the-browser-cache"></a>ブラウザー キャッシュを手動でクリアする  

ブラウザー キャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキスト メニュー \(右クリック\) を開き、[ブラウザー キャッシュのクリア] を **選択します**。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ブラウザー キャッシュのクリア] を選択する" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   [ブラウザー **キャッシュのクリア] を選択する**  
:::image-end:::  

### <a name="emulate-offline"></a>オフラインでのエミュレート  

プログレッシブ Web アプリという名前の新しいクラスの Web アプリ [は][DevtoolsProgressiveWebApps]、サービス ワーカーの助けを借りてオフライン **で機能します**。  この種類のアプリを構築するときに、データ接続がないデバイスをすばやくシミュレートすると便利な場合があります。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

[オンライン **] ドロップダウン メニュー** を選択し、[プリセット] で検索 **し**、[オフライン] を選択 **して** オフライン ネットワーク エクスペリエンスをシミュレートします。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウン メニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   [ **オフライン]** ドロップダウン メニュー  
:::image-end:::  

### <a name="emulate-slow-network-connections"></a>低速ネットワーク接続のエミュレート  

[オンライン] ドロップダウン メニューから低速 3G、Fast 3G、その他の接続速度 **を** エミュレートします。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウン メニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   [ **調整]** ドロップダウン メニュー  
:::image-end:::  

スロー 3G や Fast 3G など、さまざまなプリセットから選択できます。  独自のカスタム プリセットを追加するには、[調整] メニューを開き、[カスタム追加]**を選択**  >  **します**。  

DevTools はネットワーク ツールの横**** に警告アイコンを表示し、調整が有効になっていることを通知します。  

#### <a name="emulate-slow-network-connections-from-the-network-conditions-drawer"></a>ネットワーク条件ドロワーからの低速ネットワーク接続のエミュレート  

他の DevTools パネルで作業している間にネットワーク接続を調整する場合は、[ネットワーク条件] ドロワーを使用します。  

1.  [ネットワーク条件 **] ドロワーを開** きます。  
1.  [調整] メニューから接続速度 **を選択** します。  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-browser-cookies"></a>ブラウザーの Cookie を手動でクリアする  

ブラウザーの Cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[ブラウザー Cookie のクリア] を **選択します**。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ブラウザーの Cookie のクリア] を選択する" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   [ブラウザー **の Cookie のクリア] を選択する**  
:::image-end:::  

### <a name="override-the-user-agent"></a>ユーザー エージェントを上書きする  

ユーザー エージェントを手動で上書きするには、次の手順を使用します。  

1.  [ネットワーク条件 **] ドロワーを開** きます。  
1.  [自動的に選択 **する] チェック ボックスを** オフにします。  
1.  メニューからユーザー エージェント オプションを選択するか、テキスト ボックスにカスタム エージェントを入力します。  

<!--todo: add network condition section when available -->  

## <a name="filter-requests"></a>要求をフィルター処理する  

### <a name="filter-requests-by-properties"></a>プロパティで要求をフィルター処理する  

[フィルター **] テキスト** ボックスを使用して、要求のドメインやサイズなどのプロパティで要求をフィルター処理します。  

テキスト ボックスが表示されない場合、[フィルター] **ウィンドウ** は非表示の可能性があります。  
詳細については、「フィルター ウィンドウを非表示 [にする」に移動します](#hide-the-filters-pane)。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキスト ボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   [ **フィルター]** テキスト ボックス  
:::image-end:::  

各プロパティをスペースで区切って、複数のプロパティを同時に使用できます。  たとえば `mime-type:image/png larger-than:1K` 、1 KB を超えるすべての PNG を表示します。  マルチプロパティ フィルターは、操作と同 `AND` じです。  `OR` 操作は現在サポートされていません。  

サポートされているプロパティの完全な一覧。  

| プロパティ | 詳細 |  
|:--- | :--- |  
| `domain` | 指定したドメインのリソースのみを表示します。  複数のドメインを含めるには、ワイルドカード文字 \( `*` \) を使用できます。  たとえば、で `*.com` 終わるすべてのドメイン名のリソースを表示します `.com` 。  DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべてのドメインを設定します。 |  
| `has-response-header` | 指定した HTTP 応答ヘッダーを含むリソースを表示します。  DevTools は、オートコンプリート ドロップダウンに、見つかったすべての応答ヘッダーを設定します。 |  
| `is` | リソース `is:running` の検索に `WebSocket` 使用します。 |  
| `larger-than` | 指定したサイズより大きいリソースをバイト単位で表示します。  値の設定は `1000` 、 の値を設定するのと同じです `1k` 。 |  
| `method` | 指定した HTTP メソッドの種類で取得されたリソースを表示します。  DevTools はドロップダウンに、見つかったすべての HTTP メソッドを設定します。 |  
| `mime-type` | 指定した MIME の種類のリソースを表示します。  DevTools はドロップダウンに、見つかったすべての MIME の種類を設定します。 |  
| `mixed-content` | すべての混在コンテンツ リソース \( \) または現在表示されている `mixed-content:all` コンテンツの \( `mixed-content:displayed` \) を表示します。 |  
| `scheme` | 保護されていない HTTP \( \) または保護された HTTPS \( \) を使用して取得された `scheme:http` リソースを `scheme:https` 表示します。 |  
| `set-cookie-domain` | 指定した値に一致 `Set-Cookie` する属性を持 `Domain` つヘッダーを持つリソースを表示します。  DevTools はオートコンプリートに、見つかったすべての Cookie ドメインを設定します。 |  
| `set-cookie-name` | 指定した値に一致 `Set-Cookie` する名前のヘッダーを持つリソースを表示します。  DevTools はオートコンプリートに、見つかったすべての Cookie 名を設定します。 |  
| `set-cookie-value` | 指定した値に一致 `Set-Cookie` する値を持つヘッダーを持つリソースを表示します。  DevTools はオートコンプリートに、見つかったすべての Cookie 値を設定します。 |  
| `status-code` | 特定の HTTP 状態コードに一致するリソースを表示します。  DevTools は、オートコンプリートドロップダウン メニューに、見つかったすべての状態コードを設定します。 |  

### <a name="filter-requests-by-type"></a>種類別に要求をフィルター処理する  

要求の種類別に要求をフィルター処理するには、ネットワーク ツールで次のいずれかのボタンを **選択** します。  

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
      **メディア**  
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
      リストされていないその他の型。  
   :::column-end:::
:::row-end:::  

ボタンが表示されない場合は、[フィルター] **ウィンドウ** が非表示になる場合があります。  
詳細については、「フィルター ウィンドウを非表示 [にする」に移動します](#hide-the-filters-pane)。  

複数の種類のフィルターを同時に有効にするには `Control` 、\(Windows、Linux\) または `Command` \(macOS\) を保持してから選択します。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="Type フィルターを使用して JS、CSS、および Document リソースを表示する" lightbox="../media/network-network-type-filters.msft.png":::
   Type フィルターを使用して JS、CSS、および Document リソースを表示する  
:::image-end:::  

### <a name="filter-requests-by-time"></a>時間別に要求をフィルター処理する  

[概要] ウィンドウで左または **右にドラッグ** して、その期間にアクティブだった要求のみを表示します。  フィルターは含まれています。  強調表示された時間にアクティブだったすべての要求が表示されます。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="約 300 ミリ秒で非アクティブだった要求をフィルター処理する" lightbox="../media/network-network-overview-filter.msft.png":::
   約 300 ミリ秒で非アクティブだった要求をフィルター処理する  
:::image-end:::  

### <a name="hide-data-urls"></a>データ URL を非表示にする  

[データ URL は、][MDNHTTPDataURIs] 他のドキュメントに埋め込まれた小さなファイルです。  で始まる Requests テーブルに表示される要求は `data:` 、データ URL です。  

要求を非表示にするには、[データ URL を非表示 **にする] チェック ボックスをオフ** にします。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ URL を非表示にする] チェック ボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   [ **データ URL を非表示にする] チェック** ボックス  
:::image-end:::  

## <a name="sort-requests"></a>要求の並べ替え  

既定では、[要求] テーブル内の要求は開始時刻によって並べ替えされますが、他の条件を使用してテーブルを並べ替える場合があります。  

### <a name="sort-by-column"></a>列による並べ替え  

[要求] で任意の列のヘッダーを選択し、その列で要求を並べ替える。  

### <a name="sort-by-activity-phase"></a>アクティビティフェーズ別の並べ替え  

ウォーターフォールが要求を並べ替える方法を変更するには、Requests テーブルのヘッダーにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、 **ウォーター**フォール にカーソルを合わせると、次のいずれかのオプションを選択します。  

:::row:::
   :::column span="1":::
      **開始時刻**  
   :::column-end:::
   :::column span="2":::
      開始された最初の要求は、上部に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **応答時間**  
   :::column-end:::
   :::column span="2":::
      ダウンロードを開始した最初の要求が一番上に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **終了時刻**  
   :::column-end:::
   :::column span="2":::
      完了した最初の要求は、上部に表示されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **合計期間**  
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
      応答の最も短い時間を待った要求は、一番上に表示されます。  
   :::column-end:::
:::row-end:::  

これらの説明では、それぞれのオプションが最短から最長にランク付けされている必要があります。  [ウォーターフォール] 列のヘッダー **を選択** して、順序を逆にします。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="合計期間でウォーターフォールを並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   合計時間 \(各バーの明るい部分は待機時間、暗い部分はバイトのダウンロードに費やされた時間\) でウォーターフォールを並べ替える  
:::image-end:::  

## <a name="analyze-requests"></a>要求の分析  

DevTools が開いている限り、すべての要求がネットワーク ツールに **記録** されます。  
[ネットワーク] パネルを使用して要求を分析します。  

### <a name="display-a-log-of-requests"></a>要求のログを表示する  

DevTools が開いている間に行われたすべての要求のログを表示するには、[要求] テーブルを使用します。  各アイテムの詳細を表示するには、要求を選択またはホバーします。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="Requests テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   Requests テーブル  
:::image-end:::  

[要求] テーブルには、既定で次の列が表示されます。  

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
      **状態**  
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
      要求されたリソースの MIME の種類。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **イニシエーター**  
   :::column-end:::
   :::column span="2":::
      次のオブジェクトまたはプロセスが要求を開始します。  
      
      *   **パーサー**  Microsoft Edge の HTML パーサー。  
      *   **リダイレクト**  HTTP リダイレクト。  
      *   **スクリプト**  JavaScript 関数。  
      *   **その他**  リンクを使用してページに移動したり、アドレス バーに URL を入力したりなど、他のプロセスやアクションもあります。  
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
      要求の開始から応答の最終バイトの受信まで、合計期間。  
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

#### <a name="add-or-remove-columns"></a>列の追加または削除  

Requests テーブルのヘッダーにポインターを置き、コンテキスト メニュー \(右クリック\) を開き、非表示または表示するオプションを選択します。  現在表示されているオプションには、各アイテムの横にチェックマークが付きます。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="[要求] テーブルに列を追加する" lightbox="../media/network-network-requests-add-column.msft.png":::
   [要求] テーブルに列を追加する  
:::image-end:::  

#### <a name="add-custom-columns"></a>カスタム列の追加  

カスタム列を Requests テーブルに追加するには、Requests テーブルのヘッダーにマウス ポインターを置き、コンテキスト メニュー \(右クリック**** \) を開き、[応答ヘッダーヘッダーのヘッダー列の管理] を選択  >  **します**。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルにカスタム列を追加する" lightbox="../media/network-network-requests-add-custom.msft.png":::
   要求テーブルにカスタム列を追加する  
:::image-end:::  

### <a name="display-the-timing-relationship-of-requests"></a>要求のタイミング関係を表示する  

要求のタイミング関係を表示するには、ウォーターフォールを使用します。  
ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。  
そのため、左側より遠い要求は、右に遠い要求よりも早く開始されました。  

ウォーターフォールを並べ替えるさまざまな方法を確認するには、[アクティビティで並べ替え] [フェーズに移動します](#sort-by-activity-phase)。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウの [ウォーターフォール] 列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   [要求] ウィンドウの **[ウォーターフォール]** 列  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** panel.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames panel" lightbox="../media/network-frames.msft.png":::
   The **Frames** panel  
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

### <a name="display-a-preview-of-a-response-body"></a>応答本文のプレビューを表示する  

応答本文のプレビューを表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [プレビュー] **パネルを選択** します。  

[プレビュー] タブは、主に画像を表示する場合に便利です。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] パネル" lightbox="../media/network-network-resources-preview.msft.png":::
   [ **プレビュー]** パネル  
:::image-end:::  

### <a name="display-a-response-body"></a>応答本文の表示  

要求に対する応答本文を表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [応答] **パネルを選択** します。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] パネル" lightbox="../media/network-network-resources-response.msft.png":::
   [ **応答]** パネル  
:::image-end:::  

### <a name="display-http-headers"></a>HTTP ヘッダーの表示  

要求に関する HTTP ヘッダー データを表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [ヘッダー **]** psanel を選択します。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/network-resources-headers.msft.png":::
   [ **ヘッダー]** パネル  
:::image-end:::  

#### <a name="display-http-header-source"></a>HTTP ヘッダー ソースの表示  

既定では、[ヘッダー] **パネルには** ヘッダー名がアルファベット順に表示されます。  HTTP ヘッダー名を受け取った順序で表示するには、次の手順を使用します。  

1.  興味のある **要求** の [ヘッダー] パネルを開きます。  詳細については、[HTTP ヘッダーの表示 [] に移動します](#display-http-headers)。  
1.  [ **要求ヘッダー] または**[応答ヘッダー] セクションの横にある **[** ソース **の表示] を選択** します。  

### <a name="display-query-string-parameters"></a>クエリ文字列パラメーターの表示  

URL のクエリ文字列パラメーターを人間が読み取り可能な形式で表示するには、次の手順を使用します。  

1.  興味のある **要求** の [ヘッダー] パネルを開きます。  詳細については、[HTTP ヘッダーの表示 [] に移動します](#display-http-headers)。  
1.  [クエリ文字列パラメーター **] セクションに移動** します。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列のパラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   [ **クエリ文字列のパラメーター]** セクション  
:::image-end:::  

#### <a name="display-query-string-parameters-source"></a>クエリ文字列パラメーターソースの表示  

要求のクエリ文字列パラメーター ソースを表示するには、次の手順を使用します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、「クエリ文字列パラメーターの [表示」に移動します](#display-query-string-parameters)。  
1.  [ソース **の表示] を選択します**。  

#### <a name="display-url-encoded-query-string-parameters"></a>URL エンコードされたクエリ文字列パラメーターの表示  

クエリ文字列パラメーターを人間が読み取り可能な形式で表示し、エンコードを保持するには、次の手順を実行します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、「クエリ文字列パラメーターの [表示」に移動します](#display-query-string-parameters)。  
1.  [エンコード **された URL の表示] を選択します**。  

### <a name="display-cookies"></a>Cookie の表示  

要求の HTTP ヘッダーで送信された Cookie を表示するには、次の手順を実行します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [Cookie] **パネルを選択** します。  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] パネル" lightbox="../media/network-network-resources-cookies.msft.png":::
   [Cookie] パネル  
:::image-end:::  

### <a name="display-the-timing-breakdown-of-a-request"></a>要求のタイミングの内訳を表示する  

要求のタイミングの内訳を表示するには、次の手順を使用します。  

1.  [要求] テーブルの [名前****] 列で、要求の URL を選択します。  
1.  [タイミング] **パネルを選択** します。  

データにアクセスする方法を速くするには、[タイミングの内訳を [プレビューする] に移動します](#preview-a-timing-breakdown)。  

[タイミング] パネルに表示される各フェーズの詳細については、「タイミング**** の内訳フェーズ」[を参照してください](#timing-breakdown-phases-explained)。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] パネル" lightbox="../media/network-network-resources-timing.msft.png":::
   [ **タイミング]** パネル  
:::image-end:::  

各フェーズの詳細。  

表示にアクセスする方法の詳細については、「タイミングの内訳を表示 [する」に移動します](#display-the-timing-breakdown-of-a-request)。  

#### <a name="preview-a-timing-breakdown"></a>タイミングの内訳をプレビューする  

要求のタイミングの内訳のプレビューを表示するには、[要求] テーブルの **[ウォーター** フォール] 列で、要求のエントリにマウス ポインターを置きます。  

ホバーせずにデータにアクセスする方法の詳細については、「要求のタイミングの内訳を表示する」 [に移動します](#display-the-timing-breakdown-of-a-request)。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">要求のタイミングの内訳をプレビューする" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   要求のタイミングの内訳をプレビューする  
:::image-end:::  

#### <a name="timing-breakdown-phases-explained"></a>タイミングの内訳フェーズの説明  

タイミング パネルに表示される各フェーズの詳細。 ****  

:::row:::
   :::column span="1":::
      **キューに入る**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、次の値に当てはまる場合に要求をキューに入れられます。  
      
      *   優先度の高い要求が存在します。  
      *   同じオリジンに対して 6 つの TCP 接続が開いている。これは制限です。  HTTP/1.0 および HTTP/1.1 にのみ適用されます。  
      *   ブラウザーがディスク キャッシュ内の領域を簡単に割り当て中です。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ストール**  
   :::column-end:::
   :::column span="2":::
      「キューに入る」で説明されている理由で、要求が **停止します**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **DNS ルックアップ**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは要求の IP アドレスを解決しています。  
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
      ブラウザーが要求をプロキシ サーバーとネゴ [シエートしています][WikiProxyServer]。  
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
      要求がサービス ワーカーに送信されています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **待機中 \(TTFB\)**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは応答の最初のバイトを待機しています。  TTFB は、最初のバイトに時間を表します。  このタイミングには、1 回の待機時間と、サーバーが応答の準備にかかった時間が含まれます。  
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
      ブラウザーは HTTP/2 Server Push を介してこの応答のデータを受信しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プッシュの読み取り**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、以前に受信したローカル データを読み取り中です。  
   :::column-end:::
:::row-end:::  

### <a name="display-initiators-and-dependencies"></a>イニシエーターと依存関係の表示  

要求の開始者と依存関係を表示するには、[要求] テーブルで要求を保持してホ `Shift` バーします。  DevTools の色: イニシエーターは緑で表示され、依存関係は赤で表示されます。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求の開始者と依存関係を表示する" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   要求の開始者と依存関係を表示する  
:::image-end:::  

Requests テーブルが時系列的に並べらされている場合、行にカーソルを置くと、その前の行に緑色の要求が表示されます。  緑色の要求は、依存関係の開始者です。  それより前の行に別の緑色の要求が表示される場合、その高い要求は開始者の開始者です。  などなど。  

### <a name="display-load-events"></a>読み込みイベントの表示  

DevTools は、ネットワーク ツール上の複数 `DOMContentLoaded` の場所 `load` でイベントのタイミングを **表示** します。  イベント `DOMContentLoaded` は青で、イベント `load` は赤です。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="ネットワーク パネルの DOMContentLoaded イベントと読み込みイベントの場所" lightbox="../media/network-network-requests-load-events.msft.png":::
   ネットワーク ツール上の `DOMContentLoaded` イベント `load` の場所****  
:::image-end:::  

### <a name="display-the-total-number-of-requests"></a>要求の総数を表示する  

要求の総数は、[ネットワーク] ツールの下部**** にある [概要] ウィンドウに**表示**されます。  

> [!CAUTION]
> この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。  DevTools が開く前に他の要求が発生した場合、それらの要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開いた後の要求の総数" lightbox="../media/network-network-total-requests.msft.png":::
   DevTools が開いた後の要求の総数  
:::image-end:::  

### <a name="display-the-total-download-size"></a>ダウンロード サイズの合計を表示する  

要求の合計ダウンロード サイズは、[ネットワーク] ツール**** の下部にある [概要] ウィンドウに**表示**されます。  

> [!CAUTION]
> この番号は、DevTools が開いた後にログに記録された要求のみを追跡します。  DevTools が開く前に他の要求が発生した場合、前の要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="要求のダウンロード サイズの合計" lightbox="../media/network-network-total-download-size.msft.png":::
   要求のダウンロード サイズの合計  
:::image-end:::  

ブラウザーが各アイテムの圧縮を解除した後のリソースの大きさを確認するには、リソースの圧縮されていないサイズ [を表示します](#display-the-uncompressed-size-of-a-resource)。  

### <a name="display-the-stack-trace-that-caused-a-request"></a>要求を引き起こしたスタック トレースを表示する  

JavaScript ステートメントがリソースを要求した後、 **イニシエータ** ー列にカーソルを合わせると、要求に至るスタック トレースが表示されます。  

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

### <a name="display-the-uncompressed-size-of-a-resource"></a>リソースの圧縮されていないサイズを表示する  

[大きな要求 **行を使用する** ] チェック ボックスをオンにして、[サイズ] 列の下部の値 **を確認** します。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="非圧縮リソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   非圧縮リソースの例 \(ネットワーク上で送信されたファイルの圧縮サイズは `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \)  
:::image-end:::  

## <a name="export-requests-data"></a>要求データのエクスポート  

### <a name="save-all-network-requests-to-a-har-file"></a>すべてのネットワーク要求を HAR ファイルに保存する  

すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。  

1.  [要求] テーブルの任意の要求にカーソルを合わせると、コンテキスト メニュー \(右クリック\) が開きます。  
1.  [コンテンツ **を使用して HAR として保存] を選択します**。  DevTools は、DevTools を HAR ファイルに開いた後に発生したすべての要求を保存します。  要求をフィルター処理できない。  また、1 つの要求を保存する必要があります。  

HAR ファイルを保存したら、分析のために DevTools にインポートし戻す必要があります。  HAR ファイルを Requests テーブルにドラッグ アンド ドロップするだけ。  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[コンテンツを含む HAR として保存] を選択する" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   [コンテンツ **を含む HAR として保存] を選択する**  
:::image-end:::  

### <a name="copy-one-or-more-requests-to-the-clipboard"></a>1 つ以上の要求をクリップボードにコピーする  

[要求 **] テーブルの [** 名前] 列で、要求にカーソルを移動し、コンテキスト メニュー \(右クリック\) を開き、[ **コピー**] をポイントし、次のいずれかのオプションを選択します。  

| 名前 | 詳細 |  
|:--- |:--- |  
| **リンク アドレスのコピー** | 要求の URL をクリップボードにコピーします。 |  
| **応答のコピー** | 応答本文をクリップボードにコピーします。 |  
| **フェッチとしてコピーする** | &nbsp; |  
| **cURL としてコピーする** | 要求を cURL コマンドとしてコピーします。 |  
| **[すべてフェッチとしてコピー]** | &nbsp; |  
| **すべて cURL としてコピーする** | すべての要求を cURL コマンドのチェーンとしてコピーします。 |  
| **[すべて HAR としてコピー]** | すべての要求を HAR データとしてコピーします。 |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[応答のコピー] を選択する" lightbox="../media/network-network-requests-copy-response.msft.png":::
   [応答 **のコピー] を選択する**  
:::image-end:::  

### <a name="copy-formatted-response-json-to-the-clipboard"></a>書式設定された応答 JSON をクリップボードにコピーする  

ネットワーク要求を選択し、[ヘッダー] ウィンドウ **に移動** します。  応答の JSON 値をコピーするには、[要求**** ペイロード] に移動し、JSON 応答コンテンツにカーソルを置き、コンテキスト メニュー \(右クリック\) を開き、[値のコピー] を**選択します**。  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="コンテキスト メニューの [値のコピー]" lightbox="../media/network-header-copy-property-value.msft.png":::
          **コンテキスト メニューの [値** のコピー]  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Microsoft Visual Studio形式の応答 JSON を含むコード" lightbox="../media/network-header-paste-property-value.msft.png":::
          Microsoft Visual Studio コードでの書式設定された応答 JSON の貼りVisual Studioする  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="copy-property-values-from-network-requests-to-your-clipboard"></a>ネットワーク要求からクリップボードにプロパティ値をコピーする  

ネットワーク要求からクリップボードにプロパティ値をコピーするには、次のアクションを実行します。  

1.  [ヘッダー] **ウィンドウを開** きます。  
1.  次のいずれかのヘッダー セクションを開きます。  
    *   要求ペイロード \(JSON\)  
    *   フォーム データ  
    *   クエリ文字列パラメーター  
    *   要求ヘッダー  
    *   応答ヘッダー  
1.  コンテキスト メニュー \(右クリック\) を開き、[値をコピー> **クリックします**。  値を任意のエディターに貼り付け、確認できます。  
    
## <a name="change-the-layout-of-the-network-panel"></a>[ネットワーク] パネルのレイアウトを変更する  

重要な情報を集中するには、ネットワーク**** ツール UI のセクションを展開または折りたたみできます。  

### <a name="hide-the-filters-pane"></a>[フィルター] ウィンドウを非表示にする  

既定では、DevTools には [フィルター] ウィンドウ **が表示** されます。  
[ **フィルター** \( ![ Filter ](../media/filter-icon.msft.png) \) ] を選択して非表示にします。  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   [フィルターの非表示] ボタン  
:::image-end:::  

### <a name="use-large-request-rows"></a>大きな要求行を使用する  

ネットワーク要求テーブルに空白を追加する場合は、大きな行を使用します。  一部の列では、大きい行を使用する場合にもう少し情報を提供します。  たとえば、[サイズ] 列の下部の **値は、** 要求の圧縮されていないサイズです。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="[要求] ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   [要求] ウィンドウの大きな要求行**の例**  
:::image-end:::  

大きな行を有効にするには、[大きな要求行を使用 **する] チェック ボックスをオン** にします。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行を使用する] チェック ボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   [ **大きな要求行を使用する]** チェック ボックス  
:::image-end:::  

### <a name="hide-the-overview-pane"></a>[概要] ウィンドウを非表示にする  

既定では、DevTools は [概要] ウィンドウ **を表示** します。  非表示にするには、[概要の表示] **チェック ボックスをオフ** にします。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェック ボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   [ **概要の表示]** チェック ボックス  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "プログレッシブ Web アプリのデバッグ |Microsoft Docs"  

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
