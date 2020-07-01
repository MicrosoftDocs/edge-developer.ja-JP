---
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ec8969fbf7b54512f00120ac4a253b952c55768f
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844020"
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

Microsoft Edge DevTools のネットワーク分析機能の包括的な参照でページがどのように読み込まれるかを分析するための新しい方法について説明します。  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## ネットワーク要求を記録する  

既定では、devtools はネットワークパネルのすべてのネットワーク要求を記録します。これは、DevTools が開いている場合に限ります。  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   図 1: [**ネットワーク**] パネル  
:::image-end:::  

### ネットワーク要求の記録を停止する  

要求の記録を停止するには、次の手順を実行します。  

1.  [ **Stop recording network log** ![ ][ImageRecordOnIcon] **ネットワーク**] パネルで [ネットワークログの記録停止] を選択します。  灰色に変わり、DevTools が要求を記録しなくなったことを示します。  
1.  `Control` + `E` `Command` + `E` **ネットワーク**パネルがフォーカスされているときに、\ (Windows \) または \ (macOS \) を押します。  

### 要求をクリアする  

[ネットワーク] パネルの [**クリア] を**選ん ![ ][ImageClearIcon] で、要求テーブルからのすべての要求をクリアします。  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   図 2: [**クリア**] ボタン  
:::image-end:::  

### ページのロード間で要求を保存する  

ページの読み込み時に要求を保存するには、[ネットワーク] パネルの [**ログを保持**する] チェックボックスをオンにします。  DevTools では、 **Preserve log**を無効にするまで、すべての要求が保存されます。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保存] チェックボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   図 3: [**ログの保存**] チェックボックス  
:::image-end:::  

### ページの読み込み中にスクリーンショットをキャプチャする  

スクリーンショットをキャプチャして、ページの読み込みを待機しているユーザーに表示される内容を分析します。  

スクリーンショットを有効にするには、[**ネットワーク設定**] を選択し、[**ネットワーク**] パネルの [**スクリーンショットのキャプチャ**] チェックボックスを選択します。  

**ネットワーク**パネルがフォーカスされているときにページを更新して、スクリーンショットをキャプチャします。  

スクリーンショットをキャプチャした後、次のように操作します。  

*   スクリーンショットにマウスポインターを置くと、そのスクリーンショットがキャプチャされた点が表示されます。  [**概要**] ウィンドウに黄色の線が表示されます。  
*   スクリーンショットがキャプチャされた後に発生した要求をすべて除外するには、画面のサムネイルを選択します。  
*   サムネイルをダブルクリックして拡大します。  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショット上のマウスポインター" lightbox="../media/network-network-screenshot-hover.msft.png":::
   図 4: スクリーンショット上のマウスポインター  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and select **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Selecting Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Old Figure 5:  Selecting Replay XHR  
:::image-end:::  
-->  

## 読み込み動作を変更する  

### ブラウザーのキャッシュを無効にして、初めてのユーザーをエミュレートする  

初めてのユーザーがサイトを体験した方法をエミュレートするには、[**キャッシュを無効**にする] チェックボックスをオンにします。  DevTools は、ブラウザーのキャッシュを無効にします。  これにより、初回のユーザーエクスペリエンスが正確にエミュレートされます。要求は、繰り返しアクセスの際にブラウザーのキャッシュから提供されるためです。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェックボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   図 5:**キャッシュを無効にする**チェックボックス  
:::image-end:::  

#### [ネットワーク条件] ドロアーからブラウザーキャッシュを無効にする  

他の DevTools パネルを操作しているときに、キャッシュを無効にするには、[ネットワーク条件] ドローワを使用します。  

1.  [**ネットワーク条件**] ドローワを開きます。  
1.  [**キャッシュを無効にする**] チェックボックスをオンまたはオフにします。  

<!--todo: add network condition section when available -->  

### ブラウザキャッシュを手動でクリアする  

ブラウザーのキャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[**ブラウザキャッシュのクリア**] を選びます。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ブラウザーキャッシュのクリア] を選ぶ" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   図 6: [**ブラウザキャッシュのクリア**] の選択  
:::image-end:::  

### オフラインでエミュレートする  

[プログレッシブ Web アプリ][DevtoolsProgressiveWebApps]という名前の新しいクラスの web アプリでは、サービスの担当**者**のためにオフラインで機能します。  この種類のアプリを構築しているときに、データ接続がないデバイスをすばやくシミュレートすると便利です。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

[**オンライン**] ドロップダウンメニューを選択し、[**プリセット**] で検索し、[**オフライン**] を選択して、完全にオフラインのネットワークエクスペリエンスをシミュレートします。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウンメニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   図 7: [**オフライン**] ドロップダウンメニュー  
:::image-end:::  

### 低速ネットワーク接続のエミュレート  

「**オンライン**」ドロップダウンメニューから、低速の3G、Fast 3g、その他の接続速度をエミュレートできます。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウンメニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   図 8: [**調整**] ドロップダウンメニュー  
:::image-end:::  

低速の3G や Fast 3G など、さまざまなプリセットから選ぶことができます。  また、[調整] メニューを開き、[**カスタム**追加] を選択して、独自のカスタムプリセットを追加することもでき  >  **Add**ます。  

DevTools は、調整が有効になっていることを通知するために、[**ネットワーク**] タブの横に警告アイコンを表示します。  

#### ネットワークの状態のドロアーからの低速ネットワーク接続のエミュレート  

他の DevTools パネルでの作業中にネットワーク接続を調整したい場合は、ネットワーク条件の引き出しを使用します。  

1.  [**ネットワーク条件**] ドローワを開きます。  
1.  **調整**メニューから希望の接続速度を選択します。  

<!--todo: add network condition section when available -->  

### ブラウザーの cookie を手動でクリアする  

ブラウザーの cookie をいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[**ブラウザ cookie のクリア**] を選びます。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ブラウザーのクリア Cookie の選択]" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   図 9:**クリアブラウザーの cookie**の選択  
:::image-end:::  

### ユーザーエージェントを上書きする  

ユーザーエージェントを手動で上書きするには、次の操作を行います。  

1.  [**ネットワーク条件**] ドローワを開きます。  
1.  **[自動] をオフに**します。  
1.  メニューからユーザーエージェントオプションを選択するか、テキストボックスにユーザー設定のオプションを入力します。  

<!--todo: add network condition section when available -->  

## フィルター要求  

### プロパティによって要求をフィルター処理する  

[**フィルター** ] テキストボックスを使用して、要求のドメインやサイズなどのプロパティによって要求をフィルター処理します。  

テキストボックスが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。  
「[フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキストボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   図 10: [**フィルター** ] テキストボックス  
:::image-end:::  

各プロパティをスペースで区切ることで、複数のプロパティを同時に使うことができます。  たとえば、 `mime-type:image/png larger-than:1K` 1 kb より大きいすべての PNGs を表示します。  これらのマルチプロパティフィルターは、操作に相当 `AND` します。  `OR` 操作は現在サポートされていません。  

サポートされているプロパティの完全な一覧です。  

| プロパティ | 詳細 |  
|:--- | :--- |  
| `domain` | 指定したドメインのリソースのみを表示します。  複数のドメインを含めるには、ワイルドカード文字 \ (\) を使用することができ `*` ます。  たとえば、 `*.com` で終わるすべてのドメイン名のリソースが表示され `.com` ます。  DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべてのドメインを入力します。 |  
| `has-response-header` | 指定した HTTP 応答ヘッダーを含むリソースを表示します。  DevTools は、オートコンプリートのドロップダウンリストに、検出されたすべての応答ヘッダーを入力します。 |  
| `is` | `is:running`リソースを検索するために使用 `WebSocket` します。 |  
| `larger-than` | 指定したサイズよりも大きいリソースをバイト単位で表示します。  値の設定 `1000` は、の値の設定に相当 `1k` します。 |  
| `method` | 指定した HTTP メソッドの種類によって取得されたリソースを表示します。  DevTools は、検出されたすべての HTTP メソッドをドロップダウンに入力します。 |  
| `mime-type` | 指定した MIME の種類のリソースを表示します。  DevTools は、検出されたすべての MIME の種類をドロップダウンに入力します。 |  
| `mixed-content` | すべての混合コンテンツリソース \ ( `mixed-content:all` \) を表示するか、現在 \ (\) を表示しているものだけを表示し `mixed-content:displayed` ます。 |  
| `scheme` | 保護されていない HTTP \ ( `scheme:http` \) または保護された HTTPS \ (\) 経由で取得したリソースを表示 `scheme:https` します。 |  
| `set-cookie-domain` | 指定した `Set-Cookie` 値と一致する属性を持つヘッダーが含まれているリソースを表示し `Domain` ます。  DevTools は、検出されたすべての cookie ドメインにオートコンプリートを設定します。 |  
| `set-cookie-name` | 指定した値と一致する名前のヘッダーが含まれているリソースを表示し `Set-Cookie` ます。  DevTools は、検出されたすべての cookie 名でオートコンプリートを入力します。 |  
| `set-cookie-value` | 指定した `Set-Cookie` 値と一致する値を含むヘッダーが含まれているリソースを表示します。  DevTools は、検出されたすべての cookie 値でオートコンプリートを設定します。 |  
| `status-code` | HTTP ステータスコードが指定されたコードと一致するリソースのみを表示します。  DevTools は、オートコンプリートのドロップダウンメニューに、検出されたすべての状態コードを入力します。 |  

### 種類別に要求をフィルター処理する  

要求の種類によって要求をフィルター処理するには、[ネットワーク] パネルの**Xhr**、 **JS**、 **CSS**、 **Img**、 **Media**、 **Font**、 **Doc**、 **WS** \ (WebSocket \)、**マニフェスト**、**その他**\ (ここに一覧表示されていないその他の種類) ボタンを選択します。  

これらのボタンが表示されない場合は、[フィルター] ウィンドウが非表示になっている可能性があります。  
「[フィルターウィンドウを非表示にする」を](#hide-the-filters-pane)参照してください。  

複数の種類のフィルターを同時に有効にするに `Control` は、\ (Windows \) または `Command` \ (macOS \) を保持し、を選択します。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="型フィルターを使用した JS、CSS、およびドキュメントのリソースの表示" lightbox="../media/network-network-type-filters.msft.png":::
   図 11: 型フィルターを使用して JS、CSS、およびドキュメントのリソースを表示する  
:::image-end:::  

### 時間に基づいて要求をフィルター処理する  

[概要] ウィンドウで左または右にドラッグすると、その期間中にアクティブだった要求のみが表示されます。  フィルターは包含されています。  強調表示された時間にアクティブだった要求が表示されます。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="300ms の非アクティブな要求をすべてフィルターで除外する" lightbox="../media/network-network-overview-filter.msft.png":::
   図 12: 300ms を介して非アクティブになっていた要求をすべてフィルターで除外する  
:::image-end:::  

### データ Url を非表示にする  

[データ url][MDNHTTPDataURIs]は、他のドキュメントに埋め込まれた小さなファイルです。  が開始する要求テーブルに `data:` は、データの URL が表示されます。  

[**データ url を非表示**にする] チェックボックスをオンにして要求を非表示にします。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ Url を非表示にする] チェックボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   図 13: [**データ Url を非表示**にする] チェックボックス  
:::image-end:::  

## 並べ替え要求  

既定では、要求テーブルの要求は開始時刻によって並べ替えられますが、他の条件を使用してテーブルを並べ替えることができます。  

### 列で並べ替え  

要求内の任意の列のヘッダーを選び、その列によって要求を並べ替えます。  

### アクティビティ別の並べ替えフェーズ  

ウォーターフォールでのリクエストの並べ替え方法を変更するには、要求テーブルのヘッダーにカーソルを合わせて、コンテキストメニュー \ (右クリック \) を開き、**ウォーターフォール**をポイントして、次のいずれかのオプションを選択します。  

*   **開始時刻**。  最初に開始された要求は一番上にあります。  
*   **応答時間**。  ダウンロードを開始した最初の要求は上部にあります。  
*   **終了時刻**。  最初の要求が一番上にあります。  
*   **合計期間**。  最短接続の設定と要求/応答を含む要求が一番上にあります。  
*   **待機時間**。  応答の最短時間を待っている要求が一番上にあります。  

これらの説明は、それぞれのオプションが最短から最長の順にランク付けされていることを前提としています。  [**ウォーターフォール**] 列のヘッダーを選択すると、順序が逆になります。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="ウォーターフォールを合計期間で並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   図 14: ウォーターフォールを合計期間で並べ替える (各バーの明るい部分は待機時間で、暗い部分はバイトのダウンロードにかかる時間です)。  
:::image-end:::  

## 分析要求  

DevTools が開いている限り、すべての要求がネットワークパネルに記録されます。  
[ネットワーク] パネルを使用して要求を分析します。  

### 要求のログを表示する  

[要求] テーブルを使って、DevTools が開いている間に行われたすべての要求のログを表示します。  要求を選択またはマウスでポイントすると、各項目の詳細情報が示されます。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="要求テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   図 15: 要求テーブル  
:::image-end:::  

要求テーブルには、既定で次の列が表示されます。  

*   **[名前]**。  リソースのファイル名または識別子。  
*   **状態**。  HTTP 状態コード。  
*   **[種類]**。  要求されたリソースの MIME の種類。  
*   **イニシエーター**。  次のオブジェクトまたはプロセスで要求が開始されます。  
    *   **パーサー**。  Microsoft Edge の HTML パーサー。  
    *   **リダイレクト**。  HTTP リダイレクト。  
    *   **スクリプト**。  JavaScript 関数。  
    *   **その他**。  リンクを介してページに移動したり、アドレスバーに URL を入力したりするなど、他のプロセスまたはアクション。  
*   **サイズ**。  サーバーによって配信された、返信ヘッダーと応答本文の合計サイズ。  
*   **時刻**。  要求の開始から、応答の最後のバイトの受領までの合計時間。  
*   [**ウォーターフォール**](#view-the-timing-of-requests-in-relation-to-one-another)  各要求のアクティビティの視覚的な分類。  

#### 列を追加または削除する  

要求テーブルのヘッダーにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、表示または非表示にするオプションを選択します。  現在表示されているオプションは各項目の横にチェックマークが付いています。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="要求テーブルへの列の追加" lightbox="../media/network-network-requests-add-column.msft.png":::
   図 16: 要求テーブルに列を追加する  
:::image-end:::  

#### カスタム列を追加する  

要求テーブルにカスタム列を追加するには、要求テーブルのヘッダーにマウスポインターを合わせて、コンテキストメニューを開き (\ を右クリック \)、[**応答ヘッダー**で  >  **ヘッダー列を管理**する] を選択します。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルへのカスタム列の追加" lightbox="../media/network-network-requests-add-custom.msft.png":::
   図 17: 要求テーブルにカスタム列を追加する  
:::image-end:::  

### 相互に関連した要求のタイミングを表示する  

ウォーターフォールを使用すると、要求のタイミングを相互に関連して表示できます。  
既定では、ウォーターフォールは要求の開始時刻によって構成されています。  
そのため、左から右に向けて開始された要求よりも早く開始されています。  

ウォーターフォールのさまざまな並べ替え方法を確認するには、「[アクティビティ別に並べ替える](#sort-by-activity-phase)」を参照してください。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウの [ウォーターフォール] 列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   図 18: [**要求**] ウィンドウの [ウォーターフォール] 列  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-select the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   Old Figure 20:  The **Frames** tab  
:::image-end:::  
-->

<!--The table contains three columns:  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to their type:  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### 応答本文のプレビューを表示する  

応答本文のプレビューを表示するには、次の操作を行います。  

1.  要求の URL を要求テーブルの [**名前**] 列で選びます。  
1.  [**プレビュー** ] タブを選択します。  

このタブはほとんどの場合、画像を表示するのに役立ちます。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-network-resources-preview.msft.png":::
   図 19: [**プレビュー** ] タブ  
:::image-end:::  

### 応答本文を表示する  

要求に対する応答の本文を表示するには、次の操作を行います。  

1.  要求の URL を要求テーブルの [**名前**] 列で選びます。  
1.  [**応答**] タブを選択します。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-network-resources-response.msft.png":::
   図 20: [**応答**] タブ  
:::image-end:::  

### HTTP ヘッダーの表示  

要求に関する HTTP ヘッダーデータを表示するには、次の操作を行います。  

1.  要求の URL を要求テーブルの [**名前**] 列で選びます。  
1.  [**ヘッダー** ] タブを選択します。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-resources-headers.msft.png":::
   図 21: [**ヘッダー** ] タブ  
:::image-end:::  

#### HTTP ヘッダーソースの表示  

既定では、[ヘッダー] タブにはヘッダーの名前がアルファベット順に表示されます。  HTTP ヘッダーの名前を受け取った順序で表示するには、次の操作を行います。  

1.  興味のある要求の [**ヘッダー** ] タブを開きます。  「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。  
1.  [**要求ヘッダー** ] または [**応答ヘッダー** ] セクションの横にある [**ソースの表示**] を選択します。  

### クエリ文字列パラメーターの表示  

わかりやすい形式で URL のクエリ文字列パラメーターを表示するには、次の操作を行います。  

1.  興味のある要求の [**ヘッダー** ] タブを開きます。  「 [HTTP ヘッダーの表示](#view-http-headers)」を参照してください。  
1.  [**クエリ文字列パラメーター** ] セクションに移動します。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列パラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   図 22: [**クエリ文字列パラメーター** ] セクション  
:::image-end:::  

#### クエリ文字列パラメーターソースの表示  

要求のクエリ文字列のパラメーターソースを表示するには、次の操作を行います。  

1.  [クエリ文字列パラメーター] セクションに移動します。  「[クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。  
1.  [**ソースの表示**] を選択します。  

#### URL 形式でエンコードされたクエリ文字列パラメーターの表示  

わかりやすい形式でクエリ文字列パラメーターを表示するには、次のようにエンコードを保持します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  「[クエリ文字列パラメーターの表示](#view-query-string-parameters)」をご覧ください。  
1.  [**表示 URL をエンコード**した] を選択します。  

### Cookie の表示  

要求の HTTP ヘッダーで送信された cookie を表示するには、次の操作を行います。  

1.  要求の URL を要求テーブルの [**名前**] 列で選びます。  
1.  [ **Cookies** ] タブを選択します。  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] タブ" lightbox="../media/network-network-resources-cookies.msft.png":::
   図 23: [Cookie] タブ  
:::image-end:::  

### 要求のタイミングのブレークダウンを表示する  

要求のタイミングの詳細を表示するには、次の操作を行います。  

1.  要求の URL を要求テーブルの [**名前**] 列で選びます。  
1.  [**タイミング**] タブを選択します。  

このデータにすばやくアクセスする方法については、「[タイミングのブレークダウンをプレビュー](#preview-a-timing-breakdown)する」をご覧ください。  

「タイミング」タブに表示される各フェーズについて詳しくは、「[タイミングのブレークダウン](#timing-breakdown-phases-explained)」をご覧ください。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-network-resources-timing.msft.png":::
   図 24: [**タイミング**] タブ  
:::image-end:::  

各フェーズに関する詳細情報。  

このビューにアクセスする別の方法については、「[タイミングの内訳を表示](#view-the-timing-breakdown-of-a-request)する」を参照してください。  

#### タイミングの内訳をプレビューする  

要求のタイミングの内訳のプレビューを表示するには、要求テーブルの [**ウォーターフォール**] 列で要求のエントリにマウスポインターを合わせます。  

詳しくは[、「ホバーを必要](#view-the-timing-breakdown-of-a-request)としないデータにアクセスする方法」をご覧ください。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="要求のタイミングのブレークダウンのプレビューを >" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   図 25: 要求のタイミングのブレークダウンのプレビュー  
:::image-end:::  

#### タイミングのブレークフェーズについて  

[**タイミング**] タブに表示される各フェーズについて詳しく説明します。  

*   **キューイング**。  ブラウザーは、次の場合に要求をキューに表示します。  
    *   優先度の高い要求もあります。  
    *   この起点で既に6つの TCP 接続が開かれています。これは制限です。  HTTP/1.0 および HTTP/1.1 にのみ適用されます。  
    *   ブラウザーは、ディスクキャッシュの領域を一時的に割り当てます。  
*   **失速**します。  **キュー**に記載されている理由のいずれかで、要求が停止する可能性があります。  
*   **DNS 検索**。  ブラウザーが要求の IP アドレスを解決しています。  
*   **初期接続**。  ブラウザーでは、TCP ハンドシェイク、TCP リトライ、SSL のネゴシエーションなどの接続が確立されます。
*   **プロキシネゴシエーション**。  ブラウザーは、要求を[プロキシサーバー][WikiProxyServer]とネゴシエートしています。  
*   **リクエストを送信**しました。  要求が送信されています。  
*   **Serviceworker の準備**。  ブラウザーがサービスワーカーを開始しています。  
*   **ServiceWorker へのリクエスト**。  要求がサービスワーカーに送信されます。  
*   **\ (TTFB \) を待機**しています。  ブラウザーは、応答の最初のバイトを待機しています。  TTFB は、最初のバイトまでの時間を表します。  このタイミングには、待機時間が1往復、サーバーが応答の準備にかかった時間が含まれます。  
*   **コンテンツのダウンロード**。  ブラウザーが応答を受信します。  
*   **プッシュ配信**。  ブラウザーが、HTTP/2 Server プッシュ経由でこの応答のデータを受信しています。  
*   **プッシュ中**。  ブラウザーは、前に受信したローカルデータを読み取ります。  

### イニシエーターと依存関係を表示する  

要求のイニシエーターと依存関係を表示するには、[ `Shift` 要求] テーブルの要求をポイントしたままにします。  DevTools の色: イニシエーターは緑で表示され、依存関係は赤で示されます。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求のイニシエーターと依存関係の表示" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   図 26: 要求のイニシエーターと依存関係を表示する  
:::image-end:::  

要求テーブルが時系列順に並べ替えられている場合、ポイントしている1つ上の緑の要求が依存関係のイニシエーターになります。  別の緑の要求がその上に表示されている場合は、その上位の要求がイニシエーターのイニシエーターになります。  などなど。  

### 読み込みイベントを表示する  

DevTools は、 `DOMContentLoaded` [ `load` ネットワーク] パネル上の複数の場所にある [イベントのタイミング] を表示します。  `DOMContentLoaded`イベントは青色で色分けされ、 `load` イベントは赤になります。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="[ネットワーク] パネルでの DOMContentLoaded と load イベントの場所" lightbox="../media/network-network-requests-load-events.msft.png":::
   図 27: `DOMContentLoaded` `load` ネットワークパネル上のイベントとイベントの場所  
:::image-end:::  

### 要求の合計数を表示する  

[ネットワーク] パネルの下部にある [概要] ウィンドウに、要求の合計数が表示されます。  

> [!CAUTION]
> この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。  DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開かれてからの要求の合計数です。" lightbox="../media/network-network-total-requests.msft.png":::
   図 28: DevTools が開かれた後の要求の合計数  
:::image-end:::  

### ダウンロードの合計サイズを表示する  

要求の合計ダウンロードサイズが、[ネットワーク] パネルの下部にある [概要] ウィンドウに表示されます。  

> [!CAUTION]
> この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。  DevTools が開かれる前に、他の要求が発生した場合、以前の要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="リクエストのダウンロード合計サイズ" lightbox="../media/network-network-total-download-size.msft.png":::
   図 29: 要求のダウンロード合計サイズ  
:::image-end:::  

各項目を圧縮した後の大きなリソースについては[、「リソースの未圧縮サイズを表示](#view-the-uncompressed-size-of-a-resource)する」を参照してください。  

### 要求の原因となったスタックトレースを表示する  

JavaScript ステートメントでリソースを要求した後、[**イニシエーター** ] 列をマウスでポイントすると、要求までのスタックトレースが表示されます。  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="リソース要求までのスタックトレース" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   図 30: リソース要求までのスタックトレース  
:::image-end:::  

### リソースの未圧縮サイズを表示する  

[**大きな要求行を使用する**] チェックボックスをオンにして、[**サイズ**] 列の下の値を確認します。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="圧縮されていないリソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   図 31: 圧縮されていないリソースの例 \ (ネットワーク経由で送信されたファイルの圧縮サイズ、圧縮されてい `jquery-3.3.1.min.js` ない `29.9 KB` サイズなど `84.9 KB` )  
:::image-end:::  

## 要求データをエクスポートする  

### すべてのネットワーク要求を HAR ファイルに保存する  

すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。  

1.  要求テーブル内の任意の要求にマウスポインターを合わせ、コンテキストメニューを開きます (\ を右クリックします)。  
1.  [**コンテンツを含む HAR として保存**] を選びます。  DevTools は、HAR ファイルに対して DevTools を開いた後に発生した要求をすべて保存します。  要求をフィルター処理したり、1つの要求のみを保存したりする方法はありません。  

HAR ファイルを保存すると、そのファイルを分析用の DevTools にインポートして戻すことができます。  HAR ファイルを [要求] テーブルにドラッグアンドドロップするだけです。  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[コンテンツを含む HAR として保存] を選ぶ" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   図 32: [**コンテンツを含む HAR として保存] を**選ぶ  
:::image-end:::  

### 1つ以上の要求をクリップボードにコピーする  

要求テーブルの [**名前**] 列で、要求をポイントし、コンテキストメニューを開きます。 \ (右クリック \)、[**コピー**] をポイントして、次のいずれかのオプションを選びます。  

*   **リンクアドレスをコピー**します。  要求の URL をクリップボードにコピーします。  
*   **回答をコピー**します。  応答本文をクリップボードにコピーします。  
*   **取り出しとしてコピー**します。  
*   **CURL としてコピー**します。  CURL コマンドとして要求をコピーします。  
*   **すべてを Fetch としてコピー**します。  
*   **CURL としてすべてコピー**します。  すべての要求を cURL コマンドのチェーンとしてコピーします。  
*   **すべてを HAR としてコピー**します。  すべての要求を HAR データとしてコピーします。  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[返信のコピー] の選択" lightbox="../media/network-network-requests-copy-response.msft.png":::
   図 33: [**返信のコピー** ] の選択  
:::image-end:::  

## [ネットワーク] パネルのレイアウトを変更する  

ネットワークパネル UI のセクションを展開したり折りたたんだりして、重要な情報を強調することができます。  

### [フィルター] ウィンドウを非表示にする  

既定では、DevTools によって [**フィルター] ウィンドウ**が表示されます。  
[フィルターフィルター] を**選択し** ![ ][ImageFilterIcon] て非表示にします。  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   図 34: [フィルターの非表示] ボタン  
:::image-end:::  

### 大きな要求行を使用する  

ネットワーク要求テーブルにより多くの空白が必要な場合は、大きな行を使用します。  列によっては、大きな行を使用するときに、さらに多くの情報が表示される場合もあります。  たとえば、 **Size**列の下の値は、要求の非圧縮サイズです。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="要求ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   図 35: [**要求**] ウィンドウの大きな要求行の例  
:::image-end:::  

大きな行を有効にするには、[**大きな要求行を使用**する] チェックボックスをオンにします。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行の使用] チェックボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   図 36: [**大きな要求行の使用**] チェックボックス  
:::image-end:::  

### [概要] ウィンドウを非表示にする  

既定では、DevTools によって [**概要] ウィンドウ**が表示されます。  [**概要の表示**] チェックボックスをオフにして非表示にします。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェックボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   図 37: [**概要の表示**] チェックボックス  
:::image-end:::  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "プログレッシブ Web アプリをデバッグする"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシサーバー-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
