---
description: Microsoft Edge DevTools のネットワークパネル機能の包括的な参照。
title: ネットワーク分析のリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4d4dc8ad5102766f3ad3c8322dbf9342a69e9097
ms.sourcegitcommit: 6571bcc0b7f1c4c9d6ead65081374bab87cd4469
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203907"
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

## ネットワーク要求を記録する  

既定では、devtools が開いている限り、すべてのネットワーク要求が **ネットワーク** パネルに記録されます。  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/network-network-panel.msft.png":::
   [ **ネットワーク** ] パネル  
:::image-end:::  

### ネットワーク要求の記録を停止する  

要求の記録を停止するには、次の手順を実行します。  

1.  [ **ネットワーク** ] パネルで、[ **ネットワークログの記録を停止** する] を選択します ( ![ ネットワークログの記録を停止し ][ImageRecordOnIcon] ます)。  灰色に変わり、DevTools が要求を記録しなくなったことを示します。  
1.  `Control` + `E` `Command` + `E` **ネットワーク**パネルがフォーカスされているときに、[\ (Windows, Linux \)] または [\ (macOS \)] を選びます。  

### 要求をクリアする  

[ネットワーク] パネルで [**クリア**\ (クリア)] を選択して ![ ][ImageClearIcon] 、要求**** テーブルからすべての要求をクリアします。  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="[クリア] ボタン" lightbox="../media/network-network-clear-button.msft.png":::
   [ **クリア** ] ボタン  
:::image-end:::  

### ページのロード間で要求を保存する  

ページのロード間で要求を保存するには、[ **ネットワーク** ] パネルで、[ **ログの保持** ] チェックボックスをオンにします。  DevTools では、 **Preserve log**を無効にするまで、すべての要求が保存されます。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="[ログの保存] チェックボックス" lightbox="../media/network-network-preserve-log.msft.png":::
   [ **ログの保存** ] チェックボックス  
:::image-end:::  

### ページの読み込み中にスクリーンショットをキャプチャする  

ページが読み込まれるのを待っている間にユーザーに表示される内容を分析するためのスクリーンショットをキャプチャします。  

スクリーンショットを有効にするには、[ **ネットワーク設定**] を選び、[ **ネットワーク** ] パネルで [ **スクリーンショットのキャプチャ** ] チェックボックスをオンにします。  

**ネットワーク**パネルがフォーカスされているときにページを更新して、スクリーンショットをキャプチャします。  

スクリーンショットをキャプチャした後、次のように操作します。  

*   スクリーンショットにマウスポインターを置くと、そのスクリーンショットがキャプチャされたポイントが表示されます。  [ **概要** ] ウィンドウに黄色の線が表示されます。  
*   画面のサムネイルを選択して、スクリーンショットがキャプチャされた後に発生した要求をすべて除外します。  
*   サムネイルをダブルクリックして拡大します。  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="スクリーンショットにマウスポインターを移動する" lightbox="../media/network-network-screenshot-hover.msft.png":::
   スクリーンショットにマウスポインターを移動する  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## 読み込み動作を変更する  

### ブラウザーのキャッシュを無効にして、初めてのユーザーをエミュレートする  

初めてのユーザーがサイトをどのように体験したかをエミュレートするには、[ **キャッシュを無効** にする] チェックボックスをオンにします。  DevTools は、ブラウザーのキャッシュを無効にします。  この機能は、初回のユーザーエクスペリエンスをより正確にエミュレートします。要求は、繰り返しアクセスの際にブラウザーのキャッシュから提供されるためです。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="[キャッシュを無効にする] チェックボックス" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   [ **キャッシュを無効にする** ] チェックボックス  
:::image-end:::  

#### [ネットワーク条件] ドロアーからブラウザーキャッシュを無効にする  

他の DevTools パネルを操作しているときに、キャッシュを無効にするには、[ネットワーク条件] ドローワを使用します。  

1.  [ **ネットワーク条件** ] ドローワを開きます。  
1.  [ **キャッシュを無効にする** ] チェックボックスをオン (またはオフ) にします。  

<!--todo: add network condition section when available -->  

### ブラウザキャッシュを手動でクリアする  

ブラウザーのキャッシュをいつでも手動でクリアするには、[要求] テーブルの任意の場所でコンテキストメニュー \ (右クリック \) を開き、[ **ブラウザーキャッシュのクリア**] を選びます。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="[ブラウザーキャッシュのクリア] を選ぶ" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   [**ブラウザーキャッシュのクリア**] を選ぶ  
:::image-end:::  

### オフラインでエミュレートする  

[プログレッシブ Web アプリ][DevtoolsProgressiveWebApps]という名前の新しいクラスの web アプリでは、サービスの担当**者**のためにオフラインで機能します。  この種類のアプリを構築しているときに、データ接続がないデバイスをすばやくシミュレートすると便利です。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

[ **オンライン** ] ドロップダウンメニューの [ **プリセット**] で検索し、[ **オフライン** ] を選択して、オフラインネットワークエクスペリエンスをシミュレートします。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="[オフライン] ドロップダウンメニュー" lightbox="../media/network-network-offline-dropdown.msft.png":::
   [ **オフライン** ] ドロップダウンメニュー  
:::image-end:::  

### 低速ネットワーク接続のエミュレート  

「 **オンライン** 」ドロップダウンメニューから、低速の3G、Fast 3g、その他の接続速度をエミュレートできます。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="[調整] ドロップダウンメニュー" lightbox="../media/network-network-throttling-menu.msft.png":::
   [ **調整** ] ドロップダウンメニュー  
:::image-end:::  

低速の3G や Fast 3G など、さまざまなプリセットから選ぶことができます。  独自のカスタムプリセットを追加するには、[調整] メニューを開き、[**カスタム**  >  **追加**] を選びます。  

DevTools は、調整が有効になっていることを通知するために、[ **ネットワーク** ] タブの横に警告アイコンを表示します。  

#### ネットワークの状態のドロアーからの低速ネットワーク接続のエミュレート  

他の DevTools パネルでの作業中にネットワーク接続を調整したい場合は、ネットワーク条件の引き出しを使用します。  

1.  [ **ネットワーク条件** ] ドローワを開きます。  
1.  **調整**メニューから接続速度を選択します。  

<!--todo: add network condition section when available -->  

### ブラウザーの cookie を手動でクリアする  

ブラウザ cookie を手動でクリアするには、要求テーブルの任意の場所にマウスポインターを置いて、コンテキストメニュー \ (右クリック \) を開いて、[ **ブラウザクッキーのクリア**] を選びます。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="[ブラウザー Cookie のクリア] を選ぶ" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   [**ブラウザー cookie のクリア**] を選ぶ  
:::image-end:::  

### ユーザーエージェントを上書きする  

ユーザーエージェントを手動で上書きするには、次の手順を使用します。  

1.  [ **ネットワーク条件** ] ドローワを開きます。  
1.  **[自動的に選択**する] チェックボックスをオフにします。  
1.  メニューからユーザーエージェントオプションを選択するか、テキストボックスにユーザー設定のオプションを入力します。  

<!--todo: add network condition section when available -->  

## フィルター要求  

### プロパティによって要求をフィルター処理する  

[ **フィルター** ] テキストボックスを使用して、要求のドメインやサイズなどのプロパティによって要求をフィルター処理します。  

テキストボックスが表示されない場合は、[ **フィルター** ] ウィンドウが非表示になっている可能性があります。  
詳細については、「 [[フィルター] ウィンドウを非表示](#hide-the-filters-pane)にする」を参照してください。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="[フィルター] テキストボックス" lightbox="../media/network-network-filters-textbox.msft.png":::
   [ **フィルター** ] テキストボックス  
:::image-end:::  

各プロパティをスペースで区切ることで、複数のプロパティを同時に使うことができます。  たとえば、 `mime-type:image/png larger-than:1K` 1 kb より大きいすべての PNGs を表示します。  複数プロパティフィルターは、操作と同じです `AND` 。  `OR` 操作は現在サポートされていません。  

サポートされているプロパティの完全な一覧です。  

| プロパティ | 詳細 |  
|:--- | :--- |  
| `domain` | 指定したドメインのリソースのみを表示します。  複数のドメインを含めるには、ワイルドカード文字 \ (\) を使用することができ `*` ます。  たとえば、 `*.com` で終わるすべてのドメイン名のリソースが表示され `.com` ます。  DevTools は、見つかったすべてのドメインのオートコンプリートのドロップダウンメニューに入力します。 |  
| `has-response-header` | 指定した HTTP 応答ヘッダーを含むリソースを表示します。  DevTools は、見つかったすべての応答ヘッダーのオートコンプリートのドロップダウンリストにデータを設定します。 |  
| `is` | `is:running`リソースを検索するために使用 `WebSocket` します。 |  
| `larger-than` | 指定したサイズよりも大きいリソースを、バイト単位で表示します。  値の設定 `1000` は、の値の設定に相当 `1k` します。 |  
| `method` | 指定した HTTP メソッド型を経由して取得されたリソースを表示します。  DevTools は、検出されたすべての HTTP メソッドを使用して、ドロップダウンにデータを設定します。 |  
| `mime-type` | 指定した MIME の種類のリソースを表示します。  DevTools では、検出されたすべての MIME の種類がドロップダウンに設定されます。 |  
| `mixed-content` | すべての混合コンテンツリソース \ ( `mixed-content:all` \) を表示するか、現在 \ (\) を表示しているものだけを表示し `mixed-content:displayed` ます。 |  
| `scheme` | 保護されていない HTTP \ ( `scheme:http` \) または保護された HTTPS \ (\) 経由で取得したリソース `scheme:https` を表示します。 |  
| `set-cookie-domain` | 指定した値と一致する属性を持つヘッダーが含まれているリソースを表示 `Set-Cookie` `Domain` します。  DevTools は、検出されたすべての cookie ドメインにオートコンプリートを設定します。 |  
| `set-cookie-name` | 指定した値と一致する名前のヘッダーが含まれているリソースを表示 `Set-Cookie` します。  DevTools は、検出されたすべての cookie 名でオートコンプリートを設定します。 |  
| `set-cookie-value` | 指定された値と一致する値のヘッダーが含まれているリソースを表示 `Set-Cookie` します。  DevTools は、検出されたすべての cookie 値でオートコンプリートを設定します。 |  
| `status-code` | 特定の HTTP 状態コードに一致するリソースを表示します。  DevTools は、検出されたすべての状態コードと共にオートコンプリートのドロップダウンメニューに入力します。 |  

### 種類別に要求をフィルター処理する  

要求の種類別に要求をフィルター処理するには、[ **ネットワーク** ] パネルで次のいずれかのボタンを選択します。  

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
      **.JS**  
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
      **アドバイザー**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **WS-METADATA**  
   :::column-end:::
   :::column span="2":::
      WebSocket.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ノート**  
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

ボタンが表示されない場合は、[ **フィルター** ] ウィンドウが非表示になっている可能性があります。  
詳細については、「 [[フィルター] ウィンドウを非表示](#hide-the-filters-pane)にする」を参照してください。  

複数の種類のフィルターを同時に有効にするに `Control` は、\ (Windows、Linux \) または `Command` \ (macOS \) を保持し、を選択します。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="種類のフィルターを使用して、JS、CSS、およびドキュメントのリソースを表示する" lightbox="../media/network-network-type-filters.msft.png":::
   種類のフィルターを使用して、JS、CSS、およびドキュメントのリソースを表示する  
:::image-end:::  

### 時間に基づいて要求をフィルター処理する  

[ **概要** ] ウィンドウで左または右にドラッグすると、その期間中にアクティブだった要求のみが表示されます。  フィルターは包含されています。  強調表示された時間にアクティブだった要求が表示されます。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="300 ms で非アクティブな要求をすべてフィルターで除外する" lightbox="../media/network-network-overview-filter.msft.png":::
   300 ms で非アクティブな要求をすべてフィルターで除外する  
:::image-end:::  

### データ Url を非表示にする  

[データ url][MDNHTTPDataURIs] は、他のドキュメントに埋め込まれた小さなファイルです。  で始まる要求テーブルに表示されるすべての要求 `data:` は、データの URL です。  

要求を非表示にするには、[ **データ url を非表示** にする] チェックボックスをオフにします。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="[データ Url を非表示にする] チェックボックス" lightbox="../media/network-network-hide-data-urls.msft.png":::
   [ **データ url を非表示** にする] チェックボックス  
:::image-end:::  

## 並べ替え要求  

既定では、要求テーブルの要求は開始時刻によって並べ替えられますが、他の条件を使用してテーブルを並べ替えることができます。  

### 列で並べ替え  

要求内の任意の列のヘッダーを選び、その列によって要求を並べ替えます。  

### アクティビティ別の並べ替えフェーズ  

ウォーターフォールによる要求の並べ替え方法を変更するには、要求テーブルのヘッダーにカーソルを合わせて、コンテキストメニューを開きます (右クリック \)、 **ウォーターフォール**をポイントして、次のいずれかのオプションを選びます。  

:::row:::
   :::column span="1":::
      **開始時刻**  
   :::column-end:::
   :::column span="2":::
      最初に開始された要求は一番上にあります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **応答時間**  
   :::column-end:::
   :::column span="2":::
      ダウンロードを開始した最初の要求は上部にあります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **終了時刻**  
   :::column-end:::
   :::column span="2":::
      最初の要求が一番上にあります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **合計期間**  
   :::column-end:::
   :::column span="2":::
      最短の接続設定と要求または応答を含む要求が一番上にあります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **遅延**  
   :::column-end:::
   :::column span="2":::
      応答の最短時間を待っている要求が一番上にあります。  
   :::column-end:::
:::row-end:::  

これらの説明は、それぞれのオプションが最短から最長の順にランク付けされていることを前提としています。  順序を逆にするには、 **ウォーターフォール** 列のヘッダーを選択します。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="ウォーターフォールを合計期間で並べ替える" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   [ウォーターフォール (全体の期間)] の値を並べ替える (各バーの明るい部分は待機時間で、暗い部分はバイトのダウンロードにかかる時間です)。  
:::image-end:::  

## 分析要求  

DevTools が開いている限り、すべての要求が **ネットワーク** パネルに記録されます。  
[ネットワーク] パネルを使用して要求を分析します。  

### 要求のログを表示する  

[要求] テーブルを使用して、DevTools が開いている間に行われたすべての要求のログを表示します。  各アイテムについての詳細を参照するには、[リクエスト] を選択するか、マウスでポイントします。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="要求テーブル" lightbox="../media/network-network-requests-table.msft.png":::
   要求テーブル  
:::image-end:::  

要求テーブルには、既定で次の列が表示されます。  

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
      要求されたリソースの MIME の種類。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **・**  
   :::column-end:::
   :::column span="2":::
      次のオブジェクトまたはプロセスが要求を開始します。  
      
      *   **パーサー**  Microsoft Edge の HTML パーサー。  
      *   **Redirect**  HTTP リダイレクト。  
      *   **スクリプト**  JavaScript 関数。  
      *   **その他**  リンクを使用してページに移動したり、アドレスバーに URL を入力したりするなど、他のプロセスまたはアクション。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Size**  
   :::column-end:::
   :::column span="2":::
      サーバーによって配信された、返信ヘッダーと応答本文の合計サイズ。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **時間**  
   :::column-end:::
   :::column span="2":::
      要求の開始から、応答の最後のバイトの受領までの合計時間。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [ウォーターフォール図](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      各要求のアクティビティの視覚的な分類。  
   :::column-end:::
:::row-end:::  

#### 列を追加または削除する  

要求テーブルのヘッダーにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、表示または非表示にするオプションを選択します。  現在表示されているオプションは各項目の横にチェックマークが付いています。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="要求テーブルに列を追加する" lightbox="../media/network-network-requests-add-column.msft.png":::
   要求テーブルに列を追加する  
:::image-end:::  

#### カスタム列を追加する  

要求テーブルにカスタム列を追加するには、要求テーブルのヘッダーをポイントし、コンテキストメニューの [\ (右クリック \)] を開き、[**応答ヘッダー**] で [  >  **ヘッダー列の管理**] を選びます。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="要求テーブルにカスタム列を追加する" lightbox="../media/network-network-requests-add-custom.msft.png":::
   要求テーブルにカスタム列を追加する  
:::image-end:::  

### 要求のタイミング関係を表示する  

ウォーターフォールを使用して、要求のタイミングの関係を表示します。  
ウォーターフォールの既定の組織では、要求の開始時刻が使用されます。  
そのため、左から右への要求よりも早く開始されていた要求は、その前から始まります。  

ウォーターフォールのさまざまな並べ替え方法を確認するには、[ [アクティビティ別に並べ替え] フェーズ](#sort-by-activity-phase)に移動します。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="[要求] ウィンドウの [ウォーターフォール] 列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   [ **要求** ] ウィンドウの [ウォーターフォール] 列  
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

1.  要求の URL を要求テーブルの [ **名前** ] 列で選びます。  
1.  [ **プレビュー** ] タブを選択します。  

[プレビュー] タブはほとんどの場合、画像を表示するのに役立ちます。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="[プレビュー] タブ" lightbox="../media/network-network-resources-preview.msft.png":::
   [ **プレビュー** ] タブ  
:::image-end:::  

### 返信の本文を表示する  

要求に対する応答の本文を表示するには、次の手順を使用します。  

1.  要求の URL を要求テーブルの [ **名前** ] 列で選びます。  
1.  [ **応答** ] タブを選択します。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="[応答] タブ" lightbox="../media/network-network-resources-response.msft.png":::
   [ **応答** ] タブ  
:::image-end:::  

### HTTP ヘッダーの表示  

要求に関する HTTP ヘッダーデータを表示するには、次の手順を使用します。  

1.  要求の URL を要求テーブルの [ **名前** ] 列で選びます。  
1.  [ **ヘッダー** ] タブを選択します。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/network-resources-headers.msft.png":::
   [ **ヘッダー** ] タブ  
:::image-end:::  

#### HTTP ヘッダーソースを表示する  

既定では、[ヘッダー] タブにはヘッダーの名前がアルファベット順に表示されます。  受け取った順序で HTTP ヘッダーの名前を再生するには、次の手順を使用します。  

1.  興味のある要求の [ **ヘッダー** ] タブを開きます。  詳細については、「 [HTTP ヘッダーを表示](#display-http-headers)する」を参照してください。  
1.  [**要求ヘッダー**または**応答ヘッダー** ] セクションの横にある [**ソースの表示**] を選択します。  

### クエリ文字列パラメーターの表示  

人間が読める形式で URL のクエリ文字列パラメーターを表示するには、次の手順を使用します。  

1.  興味のある要求の [ **ヘッダー** ] タブを開きます。  詳細については、「 [HTTP ヘッダーを表示](#display-http-headers)する」を参照してください。  
1.  [ **クエリ文字列パラメーター** ] セクションに移動します。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="[クエリ文字列パラメーター] セクション" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   [ **クエリ文字列パラメーター** ] セクション  
:::image-end:::  

#### クエリ文字列のパラメーターソースの表示  

要求のクエリ文字列のパラメーターソースを表示するには、次の手順を使用します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、「 [クエリ文字列パラメーターを表示](#display-query-string-parameters)する」を参照してください。  
1.  [ **ソースの表示**] を選びます。  

#### 表示 URL エンコードされたクエリ文字列パラメーター  

ユーザーが判読できる形式でクエリ文字列パラメーターを表示するには、エンコードが保持されている場合は、次の手順を使用します。  

1.  [クエリ文字列パラメーター] セクションに移動します。  詳細については、「 [クエリ文字列パラメーターを表示](#display-query-string-parameters)する」を参照してください。  
1.  [ **表示 URL エンコード**] を選びます。  

### Cookie の表示  

要求の HTTP ヘッダーで送信された cookie を表示するには、次の手順を使用します。  

1.  要求の URL を要求テーブルの [ **名前** ] 列で選びます。  
1.  [ **Cookies** ] タブを選択します。  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="[Cookie] タブ" lightbox="../media/network-network-resources-cookies.msft.png":::
   [Cookie] タブ  
:::image-end:::  

### 要求のタイミングのブレークダウンを表示する  

要求のタイミングの詳細を表示するには、次の手順を使用します。  

1.  要求の URL を要求テーブルの [ **名前** ] 列で選びます。  
1.  [ **タイミング** ] タブを選択します。  

データにすばやくアクセスする方法については、「 [タイミングのブレークダウンのプレビュー](#preview-a-timing-breakdown)」を参照してください。  

[ **タイミング** ] タブに表示される可能性がある各フェーズについて詳しくは、「 [タイミングのブレークダウンフェーズ](#timing-breakdown-phases-explained)」を参照してください。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="[タイミング] タブ" lightbox="../media/network-network-resources-timing.msft.png":::
   [ **タイミング** ] タブ  
:::image-end:::  

各フェーズに関する詳細情報。  

ディスプレイへのアクセスについて詳しくは、「 [タイミングのブレークダウンを表示](#display-the-timing-breakdown-of-a-request)する」を参照してください。  

#### タイミングの内訳をプレビューする  

要求のタイミングの内訳のプレビューを表示するには、要求テーブルの [ **ウォーターフォール** ] 列で、要求のエントリをポイントします。  

マウスポインターを使わずにデータにアクセスする方法の詳細については、「 [要求のタイミングの](#display-the-timing-breakdown-of-a-request)詳細を表示する」を参照してください。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="要求のタイミングの詳細をプレビュー >" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   要求のタイミングの内訳をプレビューする  
:::image-end:::  

#### タイミングのブレークフェーズについて  

[ **タイミング** ] タブに表示される可能性のある各フェーズについて詳しく説明します。  

:::row:::
   :::column span="1":::
      **キュー**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、次のいずれかの条件が満たされた場合に要求を待ちます。  
      
      *   優先度の高い要求が存在します。  
      *   同じ起点 (上限) に対して6つの TCP 接続が開かれます。  HTTP/1.0 および HTTP/1.1 にのみ適用されます。  
      *   ブラウザーは、ディスクキャッシュの領域を一時的に割り当てます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **停止**  
   :::column-end:::
   :::column span="2":::
      **キュー**に記載されている理由により、要求は停止します。  
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
      ブラウザーは、TCP ハンドシェイク、TCP 再試行、セキュリティで保護されたソケットレイヤーのネゴシエーションを含む接続を確立します。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プロキシネゴシエーション**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、要求を [プロキシサーバー][WikiProxyServer]とネゴシエートしています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **送信要求**  
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
      ブラウザーがサービスワーカーを開始しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ServiceWorker へのリクエスト**  
   :::column-end:::
   :::column span="2":::
      要求がサービスワーカーに送信されます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **待機中 \ (TTFB \)**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、応答の最初のバイトを待機しています。  TTFB は、最初のバイトまでの時間を表します。  このタイミングには、待機時間のラウンドトリップの1つと、サーバーが応答の準備に費やした時間が含まれます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **コンテンツのダウンロード**  
   :::column-end:::
   :::column span="2":::
      ブラウザーが応答を受信します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プッシュ受信**  
   :::column-end:::
   :::column span="2":::
      ブラウザーが、HTTP/2 Server プッシュ経由でこの応答のデータを受信しています。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **プッシュの読み取り**  
   :::column-end:::
   :::column span="2":::
      ブラウザーは、前に受信したローカルデータを読み取ります。  
   :::column-end:::
:::row-end:::  

### イニシエーターと依存関係を表示する  

要求のイニシエーターと依存関係を表示するには、要求テーブルの要求を保留にして `Shift` ポイントします。  DevTools の色: イニシエーターは緑で表示され、依存関係は赤で示されます。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="要求のイニシエーターと依存関係を表示する" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   要求のイニシエーターと依存関係を表示する  
:::image-end:::  

要求テーブルが時系列で並べ替えられている場合、その行の上にカーソルを置くと、その行の前の行に緑色の要求が表示されます。  緑の要求は、依存関係のイニシエーターです。  この行の前に別の緑の要求が表示されている場合は、その上位の要求がイニシエーターのイニシエーターになります。  などなど。  

### 読み込みイベントを表示する  

DevTools は、 `DOMContentLoaded` [ `load` **ネットワーク** ] パネル上の複数の場所にある [イベントのタイミング] を表示します。  `DOMContentLoaded`イベントは青色で色分けされ、 `load` イベントは赤になります。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="[ネットワーク] パネルでの DOMContentLoaded と load イベントの場所" lightbox="../media/network-network-requests-load-events.msft.png":::
   [ `DOMContentLoaded` `load` **ネットワーク** ] パネルでのイベントとイベントの場所  
:::image-end:::  

### 要求の合計数を表示する  

[**ネットワーク**] パネルの下部にある [**概要**] ウィンドウに、要求の合計数が表示されます。  

> [!CAUTION]
> この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。  DevTools が開かれる前に他の要求が発生した場合、これらの要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="DevTools が開かれてからの要求の合計数です。" lightbox="../media/network-network-total-requests.msft.png":::
   DevTools が開かれてからの要求の合計数です。  
:::image-end:::  

### ダウンロードの合計サイズを表示する  

要求の合計ダウンロードサイズが、[**ネットワーク**] パネルの下部にある [**概要**] ウィンドウに表示されます。  

> [!CAUTION]
> この数値は、DevTools が開かれた後にログに記録された要求のみを追跡します。  DevTools が開かれる前に、他の要求が発生した場合、以前の要求はカウントされません。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="リクエストのダウンロード合計サイズ" lightbox="../media/network-network-total-download-size.msft.png":::
   リクエストのダウンロード合計サイズ  
:::image-end:::  

サイズの大きいリソースがどのように圧縮されているかを確認するには、[ [リソースの未圧縮サイズの表示](#display-the-uncompressed-size-of-a-resource)] に移動します。  

### 要求の原因となったスタックトレースを表示します。  

JavaScript ステートメントでリソースを要求した後、[ **イニシエーター** ] 列をポイントすると、要求までのスタックトレースが表示されます。  

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
   リソース要求までのスタックトレース  
:::image-end:::  

### リソースの未圧縮サイズを表示する  

[ **大きい要求行を使用する** ] チェックボックスをオンにして、[ **サイズ** ] 列の下の値を確認します。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="圧縮されていないリソースの例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   圧縮されていないリソースの例 \ (ネットワーク経由で送信されたファイルの圧縮サイズ、圧縮されてい `jquery-3.3.1.min.js` ない `29.9 KB` サイズなど `84.9 KB` )  
:::image-end:::  

## 要求データをエクスポートする  

### すべてのネットワーク要求を HAR ファイルに保存する  

すべてのネットワーク要求を HAR ファイルに保存するには、次の手順を実行します。  

1.  要求テーブル内の任意の要求にマウスポインターを合わせ、コンテキストメニューを開きます (\ を右クリックします)。  
1.  [ **コンテンツを含む HAR として保存**] を選びます。  DevTools は、HAR ファイルに対して DevTools を開いた後に発生した要求をすべて保存します。  要求をフィルター処理することはできません。  1つのリクエストを保存することもできません。  

HAR ファイルを保存すると、そのファイルを分析用の DevTools にインポートして戻すことができます。  HAR ファイルを [要求] テーブルにドラッグアンドドロップするだけです。  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="[コンテンツで HAR として保存] を選ぶ" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   [**コンテンツで HAR として保存**] を選ぶ  
:::image-end:::  

### 1つ以上の要求をクリップボードにコピーする  

要求テーブルの [ **名前** ] 列で、要求をポイントし、コンテキストメニューを開きます。 \ (右クリック \)、[ **コピー**] をポイントして、次のいずれかのオプションを選びます。  

| 名前 | 詳細 |  
|:--- |:--- |  
| **リンクアドレスをコピーする** | 要求の URL をクリップボードにコピーします。 |  
| **返信のコピー** | 応答本文をクリップボードにコピーします。 |  
| **フェッチとしてコピー** | &nbsp; |  
| **CURL としてコピー** | CURL コマンドとして要求をコピーします。 |  
| **すべてをフェッチとしてコピーする** | &nbsp; |  
| **CURL としてすべてコピー** | すべての要求を cURL コマンドのチェーンとしてコピーします。 |  
| **すべてを HAR としてコピーする** | すべての要求を HAR データとしてコピーします。 |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="[応答のコピー] を選ぶ" lightbox="../media/network-network-requests-copy-response.msft.png":::
   [**応答のコピー** ] を選ぶ  
:::image-end:::  

### 書式設定された応答の JSON をクリップボードにコピーする  

ネットワーク要求を選択し、[ **ヘッダー** ] ウィンドウに移動します。  応答の JSON 値をコピーするには、[ **要求ペイロード**] に移動し、JSON 応答コンテンツにカーソルを合わせて、コンテキストメニューを開き (\ を右クリックし)、[ **値のコピー**] を選びます。  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="コンテキストメニューで値をコピーする" lightbox="../media/network-header-copy-property-value.msft.png":::
          コンテキストメニューで**値をコピー**する  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="書式付き応答の JSON を含む Visual Studio コード" lightbox="../media/network-header-paste-property-value.msft.png":::
          Visual Studio コードでの書式付き応答の JSON の貼り付け  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### プロパティ値をネットワーク要求からクリップボードにコピーする  

プロパティの値をネットワーク要求からクリップボードにコピーするには、次の操作を実行します。  

1.  [ **ヘッダー** ] ウィンドウを開きます。  
1.  次のヘッダーセクションのいずれかを開きます。  
    *   要求ペイロード \ (JSON \)  
    *   フォームデータ  
    *   クエリ文字列パラメーター  
    *   要求ヘッダー  
    *   応答ヘッダー  
1.  コンテキストメニューを開きます \ (右クリック \) > **コピー値**)。  任意のエディターに値を貼り付けてレビューできるようになりました。  
    
## [ネットワーク] パネルのレイアウトを変更する  

**ネットワーク**パネル UI のセクションを展開したり折りたたんだりして、重要な情報を強調することができます。  

### [フィルター] ウィンドウを非表示にする  

既定では、DevTools によって [ **フィルター** ] ウィンドウが表示されます。  
[ **フィルター** \ ( ![ フィルター ][ImageFilterIcon] \)] を選択して非表示にします。  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="[フィルターの非表示] ボタン" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   [フィルターの非表示] ボタン  
:::image-end:::  

### 大きな要求行を使用する  

ネットワーク要求テーブルにより多くの空白が必要な場合は、大きな行を使用します。  列によっては、大きな行を使用するときに、さらに多くの情報が表示される場合もあります。  たとえば、 **Size** 列の下の値は、要求の非圧縮サイズです。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="要求ウィンドウの大きな要求行の例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   **要求ウィンドウの**大きな要求行の例  
:::image-end:::  

大きい行を有効にするには、[ **大きな要求行を使用** する] チェックボックスをオンにします。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="[大きな要求行の使用] チェックボックス" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   [ **大きな要求行の使用** ] チェックボックス  
:::image-end:::  

### [概要] ウィンドウを非表示にする  

既定では、DevTools によって [ **概要** ] ウィンドウが表示されます。  非表示にするには、[ **概要の表示** ] チェックボックスをオフにします。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="[概要の表示] チェックボックス" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   [ **概要の表示** ] チェックボックス  
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

[DevtoolsProgressiveWebApps]: ../progressive-web-apps.md "プログレッシブ Web アプリのデバッグ |Microsoft ドキュメント"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "データ Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "プロキシサーバー-Wikipedia"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
