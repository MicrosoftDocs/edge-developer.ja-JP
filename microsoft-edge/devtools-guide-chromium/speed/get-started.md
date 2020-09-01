---
title: Microsoft Edge DevTools を使用して Web サイトの速度を最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 42b742316ccaa64aa35fc1d21c5277e448b2d5b7
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984717"
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





# Microsoft Edge DevTools を使用して web サイトの速度を最適化する   



## チュートリアルの目標  

このチュートリアルでは、Microsoft Edge DevTools を使って、web サイトの読み込みを高速化する方法について説明します。  

## 前提条件  

*   この [Web 開発クラスの概要][CourseraIntroductionWebDevelopmentClass]で説明するように、基本的な web 開発環境を用意する必要があります。  
*   読み込みのパフォーマンスについて何も知りません。  これについては、このチュートリアルで説明します。  

## はじめに   

これは Tony です。  Tony は、cat 協会で非常に有名です。  彼は、お客様がお気に入りの食品について知ることができるように、web サイトを構築しました。  Tony のファンは、サイトを気に入っていますが、サイトの読み込み速度が遅いという苦情を耳にしています。  Tony から、サイトの速度を向上させるように求められました。  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="猫を Tony" lightbox="../media/speed-tony.msft.png":::
   猫を Tony  
:::image-end:::  

## 手順 1: サイトを監査する   

サイトの読み込みのパフォーマンスを向上させるために、 **必ず監査を開始して**ください。  
監査には、次の2つの重要な機能があります。  

*   以降の変更を測定するための **基準計画** を作成します。  
*   どのような変更が最も影響を与えるかに関する実用的な **ヒント** が提供されます。  
    
### 設定   

最初に、後で変更できるようにサイトを設定する必要があります。  

1.  [サイトのソースコードを開き](https://glitch.com/edit/#!/tony)ます。  このタブは [ **エディター] タブ**と呼ばれます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="[エディター] タブ" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       [ **エディター] タブ**  
    :::image-end:::  
    
1.  [ **Tony**] を選びます。  メニューが表示されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="Tony をクリックした後に表示されるメニュー" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       **Tony**をクリックした後に表示されるメニュー  
    :::image-end:::  
    
1.  [ **Remix Project**] を選びます。  プロジェクトの名前が **tony** からランダムに生成された名前に変更されます。  これで、独自のコードの編集可能なコピーが作成されました。  後で、このコードを変更することができます。  
1.  [ **表示** ] を選択し、 **新しいウィンドウで**を選択します。  新しいタブでデモが開きます。 このタブは [ **デモ] タブ**として参照されます。 サイトが読み込まれるまでには時間がかかることがあります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="[デモ] タブ" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       [デモ] タブ  
    :::image-end:::  
    
1.  `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。  Microsoft Edge の DevTools がデモと共に開きます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools とデモ" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       DevTools とデモ  
    :::image-end:::  
    
このチュートリアルの残りのスクリーンショットでは、DevTools が別のウィンドウに表示されています。  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、入力した `Undock` 後、**別のウィンドウに装着解除**することができます。  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="アンドックした DevTools" lightbox="../media/speed-console.msft.png":::
   アンドックした DevTools  
:::image-end:::  

### ベースラインを確立する   

ベースラインは、パフォーマンスを向上させる前に、サイトがどのように実行されたかを記録したものです。  

1.  [ **監査** ] タブを選択します。 その **他のパネル** \ ([ ![ その他のパネル]) ボタンの背後に隠れている可能性があり ][ImageMorePanelsIcon] ます。  監査パネルを累乗するプロジェクトには、 **Lighthouse**という名前が付いているため、このパネルには Lighthouse があります。  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="監査パネル" lightbox="../media/speed-audits-performance.msft.png":::
       **監査**パネル  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  監査構成の設定と前の図の設定を一致させる。  さまざまなオプションについて説明します。  
    
    *   **デバイス**。  [ **モバイル** に設定] をオンにすると、ユーザーエージェント文字列が変更され、モバイルビューポートがシミュレートされます。  **デスクトップ**に設定することで、**モバイル**の変更が無効になります。  
    *   **監査**。  カテゴリを無効にすると、監査パネルでそれらの監査が実行されなくなり、レポートから監査が除外されます。  提供されている推奨事項の種類を表示する場合は、その他のカテゴリを有効のままにします。  カテゴリを無効にすると、監査プロセスが少し速くなります。  
    *   **調整**。  シミュレートされた **4g の4倍の CPU 速度** は、モバイルデバイスでの一般的な参照条件をシミュレートしています。  監査プロセス中に監査パネルで実際にスロットルされないので、"シミュレート" という名前が付けられます。  代わりに、ページがモバイルの条件下で読み込むのにかかる時間を extrapolates だけです。  一方、適用された [. **..** ] 設定では、より多くの監査プロセスの代わりに、CPU とネットワークのスロットルが実際に行われます。  
    *   **ストレージをクリア**します。  このチェックボックスを有効にすると、ページに関連付けられているすべてのストレージが、各監査前に消去されます  この設定は、サイトでの初回の閲覧者の操作性を監査する場合にオンのままにしておきます。  この設定は、ユーザーが繰り返しアクセスするときに無効にします。  
    
1.  [ **監査の実行**] を選びます。  10秒から30秒後に、監査パネルにサイトのパフォーマンスのレポートが表示されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="サイトのパフォーマンスの監査パネルのレポート" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       サイトのパフォーマンスの監査パネルのレポート  
    :::image-end:::  
    
#### レポートのエラーを処理する   

監査パネルレポートにエラーが表示された場合は、他のタブが開いていない **InPrivate** ウィンドウで [デモ] タブを実行してみてください。  これにより、Microsoft Edge をクリーンな状態から実行することができます。  特に Microsoft Edge Extensions は、監査プロセスの妨げになることがよくあります。  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### レポートを理解する   

レポートの上部に表示される数値は、サイトの全体的なパフォーマンススコアです。  後でコードを変更すると、この数値の増加が確認できます。  高いスコアは、パフォーマンスが向上することを意味します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="全体的なパフォーマンススコア" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   全体的なパフォーマンススコア  
:::image-end:::  

[ **メトリック** ] セクションには、サイトのパフォーマンスの定量的な測定値が表示されます。  各メトリックは、パフォーマンスのさまざまな側面について把握します。  たとえば、 **最初の Contentful 塗料** は、画面に最初にコンテンツが描画されたときに表示されます。これは、ユーザーがページの読み込みにおいて重要なマイルストーンであり、 **対話型** のときには、ユーザーの操作を処理するのに必要なページが表示されている点を示します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="[メトリック] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   [ **メトリック** ] セクション  
:::image-end:::  

次の図の強調表示されたトグルボタンを選択すると、各メトリックの説明が表示され、[ **詳細** 情報] をクリックすると、その内容に関するドキュメントを参照できます。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="強調表示されたトグルボタンを選択して、[Metrics] 項目を展開する" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   強調表示されたトグルボタンを選択して、[Metrics] 項目を展開する  
:::image-end:::  

メトリックの下には、ページが読み込まれたときにどのように見えるかを示すスクリーンショットのコレクションがあります。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="ページの読み込み中の画面のスクリーンショット" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   ページの読み込み中の画面のスクリーンショット  
:::image-end:::  

[ **営業案件** ] セクションでは、この特定のページの読み込みパフォーマンスを向上させるためのヒントを紹介します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="[営業案件] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   [ **営業案件** ] セクション  
:::image-end:::  

詳細については、[営業案件] を選択します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="レンダーブロックリソースの機会を排除する" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   **レンダーブロックリソースの機会を排除** する  
:::image-end:::  

[ **詳細情報** ] を選択して、営業案件が重要である理由と、その解決方法に関する具体的な推奨事項についてのドキュメントを表示します。  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="レンダーブロックリソースの機会を減らすためのドキュメント" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   **レンダーブロックリソース**の機会を減らすためのドキュメント  
:::image-end:::  

[ **診断** ] セクションには、ページの読み込み時間に影響する要因についての詳細情報が表示されます。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="[診断] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   [ **診断** ] セクション  
:::image-end:::  

[ **成功** した監査] セクションには、サイトが正常に動作していることが示されます。  セクションを展開する場合に選択します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="[成功した監査] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   [ **成功** した監査] セクション  
:::image-end:::  

## 手順 2: 実験   

監査レポートの [営業案件] セクションには、ページのパフォーマンスを向上させるためのヒントが表示されます。  このセクションでは、コードベースへの推奨される変更を実装します。各変更の後でサイトを監査し、サイトの速度にどのような影響があるかを測定します。  

### テキストの圧縮を有効にする   

レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。  テキスト圧縮を有効にすると、ページのパフォーマンスを向上させることができます。  

テキストファイルをネットワーク経由で送信する前に、テキストファイルのサイズを縮小 (圧縮) する場合。  メールのサイズを小さくするためにメールを送信する前に、どのようにしてフォルダーを zip 圧縮するかなどです。  

圧縮を有効にする前に、テキストリソースが圧縮されているかどうかを手動で確認する方法がいくつかあります。  

1.  [ **ネットワーク** ] タブを選択します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       [ **ネットワーク** ] パネル  
    :::image-end:::  
    
1.  [ **ネットワーク設定** ] アイコンを選択します。  
1.  [ **大きな要求行を使用する** ] チェックボックスをオンにします。  ネットワーク要求のテーブルの行の高さが増加します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="ネットワーク要求テーブルの大きな行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       ネットワーク要求テーブルの大きな行  
    :::image-end:::  
    
1.  ネットワーク要求のテーブルに [ **サイズ** ] 列が表示されない場合は、テーブルの見出しをクリックして、[ **サイズ**] を選択します。  

各 **Size** セルには2つの値が表示されます。  上の値は、ダウンロードしたリソースのサイズです。  
ボトム値は、圧縮されていないリソースのサイズです。  2つの値が同じである場合は、ネットワーク経由で送信されたときにリソースが圧縮されていないことを意味します。  たとえば、上の図では、の上位と下位の値 `bundle.js` は and で指定し `1.2 MB` `1.2 MB` ます。  

リソースの HTTP ヘッダーを調べて、圧縮を確認します。  

1.  [ **bundle.js**] を選びます。  
1.  [ **ヘッダー** ] タブを選択します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="[ヘッダー] タブ" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       [ **ヘッダー** ] タブ  
    :::image-end:::  
    
1.  ヘッダーの [ **応答ヘッダー** ] セクションを検索し `content-encoding` ます。  圧縮されていないことを示すものは表示されません `bundle.js` 。  リソースが圧縮されている場合、このヘッダーは通常、、またはに設定され `gzip` `deflate` `br` ます。  これらの値の説明については、「 [ディレクティブ][MDNContentEncodingDirectives] 」を参照してください。  

説明が必要です。  変更を加える時間  テキストの圧縮を有効にするには、数行のコードを追加します。  

1.  [エディター] タブで、[ **server.js**] をクリックします。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="server.js を編集する" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       Edit `server.js`  
    :::image-end:::  
    
1.  **server.js**に次のコードを追加します。  前に必ず入力してください `app.use(compression())` `app.use(express.static('build'))` 。  

    ```javascript
    const express = require('express');
    const app = express();
    const fs = require('fs');
    const compression = require('compression');

    app.use(compression());
    app.use(express.static('build'));
    
    const listener = app.listen(process.env.PORT || 1234, function () {
        console.log(`Listening on port ${listener.address().port}`);
    });
    ```  
    
    > [!NOTE]
    > 通常は、次のような方法でパッケージをインストールする必要があり `compression` `npm i -S compression` ますが、これは既に行われています。  
    
1.  サイトの新しいビルドが展開されるのを待ちます。  [ **ツール** ] の横にある凝ったアニメーションは、サイトが再構築されて再展開されることを意味します。  [ **ツール** ] の横にあるアニメーションが消えると、変更がすぐにできます。  [ **表示** ] を選択し、 **新しいウィンドウで** もう一度選択します。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
以前に学習したワークフローを使用して、圧縮が機能していることを手動で確認します。  

1.  [デモ] タブに戻り、ページを再読み込みします。  これで、[ **サイズ** ] 列に、次のようなテキストリソースの2つの異なる値が表示され `bundle.js` ます。  次の図では、の値 `256 KB` `bundle.js` はネットワーク経由で送信されたファイルのサイズであり、の下の値は圧縮されていない `1.2 MB` ファイルサイズです。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="[サイズ] 列に、テキストリソースの2つの異なる値が表示されるようになりました" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       [ **サイズ** ] 列に、テキストリソースの2つの異なる値が表示されるようになりました  
    :::image-end:::  
    
1.  [ **応答ヘッダー** ] セクションに、 `bundle.js` ヘッダーを含めるようになりました `content-encoding: gzip` 。
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="応答ヘッダーセクションにコンテンツエンコードヘッダーが含まれるようになりました" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       **応答ヘッダー**セクションにコンテンツエンコードヘッダーが含まれるようになりました  
    :::image-end:::  
    
ページをもう一度監査して、ページの読み込みパフォーマンスにどのような影響があるかを測定します。  

1.  [ **監査** ] タブを選択します。  
1.  [ **監査を実行する** ] を選択し ![ ます (監査を実行 ][ImagePerformIcon] します)。  
1.  設定は前の設定のままにしておきます。  
1.  [ **監査の実行**] を選びます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="テキストの圧縮を有効にした後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       テキストの圧縮を有効にした後の監査レポート  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  全体的なパフォーマンススコアは高くなります。つまり、サイトの速度が速くなります。  

#### 現実世界でのテキスト圧縮   

ほとんどのサーバーでは、圧縮を有効にするための単純な修正プログラムが用意されています。  テキストの圧縮に使用するサーバーを構成する方法について、検索を行うだけです。  

### 画像のサイズを変更する   

レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。  画像のサイズを変更すると、ネットワークペイロードのサイズを小さくすることができます。  ユーザーが500ピクセル幅のモバイルデバイス画面で画像を表示している場合、1500ピクセル幅の画像を送信することはまったくありません。  理想的には、500ピクセル幅の画像を送信することをお勧めします。  

1.  レポートで、[ **大量のネットワークペイロード** を使用しない] をクリックして、サイズを変更する画像を確認します。  Jpg ファイルのうち2つは 2000 KB を超えるようですが、これは必要以上に大きくなります。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  [エディター] タブに戻り、[] を開き `src/model.js` ます。  
1.  置換後 `const dir = 'big'` の文字列 `const dir = 'small'`  このディレクトリには、サイズ変更された同じ画像のコピーが含まれています。  
1.  この変更が読み込みのパフォーマンスにどのように影響するかを確認するには、ページをもう一度監査します。  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="画像のサイズを変更した後の監査レポート" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       画像のサイズを変更した後の監査レポート  
    :::image-end:::  
    
変更は、全体的なパフォーマンススコアに対して軽微な影響を与えるようです。  ただし、スコアが明確に表示されない場合は、ユーザーに保存されているネットワークデータの量です。  以前の写真の合計サイズは、5.3 mb になりましたが、現時点では 0.18 mb にすぎません。  

#### 実際の画像のサイズ変更   

小規模のアプリでは、1回限りのサイズ変更を行っても問題が生じる可能性があります。  ただし、大規模なアプリでは、このようなスケーラビリティはありません。  大規模なアプリでイメージを管理するためのいくつかの方法を次に示します。  

*   ビルドプロセス中に画像のサイズを変更します。  
*   ビルドプロセス中に各画像のサイズを複数作成し、 `srcset` コードで使用します。  実行時には、ブラウザーは、デバイスに最適なサイズを選択する必要があります。  
    <!--See [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   要求時に画像のサイズを動的に変更できるようにするイメージ CDN を使用します。  
*   少なくとも、各画像を最適化します。  これにより、大幅に節約できます。  
  最適化とは、画像ファイルのサイズを小さくする特殊なプログラムで画像を実行する場合に使用されます。  その他のヒントについては、「 [重要な画像の最適化][EssentialImageOptimization] 」をご覧ください。  
    
### レンダーブロックリソースを排除する   

最新のレポートでは、レンダーブロックのリソースを除去することが最大の機会になりました。  

レンダーブロックリソースは、ページを表示する前に、ブラウザーがダウンロード、解析、実行する必要がある外部 JavaScript または CSS ファイルです。  目的は、ページを適切に表示するために必要なコア CSS と JavaScript コードを実行することだけです。  

最初のタスクでは、ページの読み込み時に実行する必要がないコードが検索されます。  

1.  [ **レンダーブロックリソースの削除** ] を選択して、ブロックされているリソースを確認します。  
    `lodash.js` および `jquery.js` 。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="レンダーブロックリソースの機会の削減に関するその他の情報" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       **レンダーブロックリソース**の機会の削減に関するその他の情報  
    :::image-end:::  
    
1.  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押してコマンドメニューを開き、入力を開始して、[ `Coverage` **カバレッジの表示**] を選択します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="[監査] パネルからコマンドメニューを開く" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       [ **監査** ] パネルからコマンドメニューを開く  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       [ **カバレッジ** ] タブ  
    :::image-end:::  
    
1.  [ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。  [ **カバレッジ** ] タブには、ページの読み込み時にのコードの量の概要が表示され `bundle.js` `jquery.js` `lodash.js` ます。  次の図では、それぞれ、jQuery と Lodash のファイルの76% と30% は使用されません。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="カバレッジレポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       カバレッジレポート  
    :::image-end:::  
    
1.  [ **jquery.js** ] 行を選択します。  DevTools [ソース] パネルでファイルを開きます。  横に青色のバーが表示されている場合は、コード行が実行されます。  赤色のバーは、実行されなかったため、ページの読み込み時には必要ありません。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="ソースパネルで jQuery ファイルを表示する" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       **ソース**パネルで jQuery ファイルを表示する  
    :::image-end:::  
    
1.  JQuery コードを1ビットずつスクロールします。  "実行" を取得する行の一部は、実際にはコメントにすぎません。  このコードを実行するときには、コメントを取り除くための別の方法として、このファイルのサイズを小さくする方法もあります。  

つまり、独自のコードを操作している場合、[カバレッジ] タブでは、コードの分析や行ごとの分析を行うことができます。また、ページの読み込みに必要なコードのみを提供します。  

ページの `jquery.js` `lodash.js` 読み込みにもファイルが必要ですか?  [要求のブロック] タブには、リソースが利用できない場合の動作が表示されます。  

1.  [ **ネットワーク** ] タブを選択します。  
1.  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押して、もう一度コマンドメニューを開きます。  
1.  入力を開始し `blocking` 、[ **要求ブロックの表示**] を選択します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="[要求のブロック] タブ" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       [ **要求のブロック** ] タブ  
    :::image-end:::  
    
1.  [ **パターンの追加** \ (パターンの追加 \)] を選択し、 ![ ][ImageAddPatternIcon] 「 `/libs/*` 」と入力して、[確認] `Enter` を押します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="すべての要求をライブラリディレクトリにブロックするためのパターンを追加する" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       ディレクトリへの要求をブロックするためのパターンを追加する `libs`  
    :::image-end:::  
    
1.  ページを最新の情報に更新してください。  JQuery と Lodash の要求は赤で、要求がブロックされたことを意味します。   ページは依然として読み込まれ、対話型であるため、これらのリソースは必要ではないようです。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="[ネットワーク] パネルに、リクエストがブロックされていることが示される" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       [ **ネットワーク** ] パネルに、リクエストがブロックされていることが示される  
    :::image-end:::  
    
1.  **Remove all patterns** ![ ][ImageRemoveIcon] ブロックパターンを削除するには、[すべてのパターンを削除する] (すべてのパターンを削除) を選択し `/libs/*` ます。  
    
一般的に、[要求のブロック] タブは、特定のリソースが利用できない場合にページがどのように動作するかをシミュレートするのに役立ちます。  

次に、これらのファイルへの参照をコードから削除して、ページをもう一度監査します。  

1.  [エディター] タブに戻り、[] を開き `template.html` ます。  
1.  `<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。  
1.  サイトが再構築され、再展開されるのを待ちます。  
1.  **監査パネルから**ページをもう一度監査します。  全体的なスコアは、もう一度向上させる必要があります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="レンダーブロックリソースを削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       レンダーブロックリソースを削除した後の **監査** レポート  
    :::image-end:::  
    
#### 現実世界での重大なレンダリングパスの最適化   

**クリティカルレンダリングパス**は、ページの読み込みに必要なコードを指します。  一般的には、ページの読み込み中にクリティカルコードのみを配布することにより、ページの読み込みを高速化し、その他のすべての機能を遅延読み込みします。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   完全に削除できるスクリプトを見つけることはできませんが、ページの読み込み中に要求する必要のないスクリプトが数多くあり、非同期で要求される可能性があります。  <!--See [Using async or defer][async].  -->  
*   フレームワークを使用している場合は、プロダクションモードであるかどうかを確認します。  このモードでは、重大なレンダリングをブロックしている不要なコードを取り除くために、 [ツリーのシェイク][WebpackTreeShaking] などの機能を使用する場合があります。  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### メインスレッドの作業量を少なくする   

最新のレポートでは、[営業案件] セクションで若干の節約が可能になりますが、[診断] セクションで確認すると、最大のボトルネックはメインスレッドのアクティビティが多すぎるようです。  

メインスレッドでは、HTML、CSS、JavaScript の解析や実行など、ページを表示するために必要な作業のほとんどがブラウザーで行われます。  

目標として、[パフォーマンス] パネルを使用して、ページの読み込み中にメインスレッドで実行されている作業を分析し、不要な作業を延期または削除する方法を見つけます。  

1.  [ **パフォーマンス** ] タブを選択します。  
1.  [ **キャプチャ設定** ] ( ![ キャプチャ設定 ][ImageCaptureIcon] ) を選びます。  
1.  [ **ネットワーク** ] を [ **3g** ] と [ **CPU** ] から [ **6x**] の速度に設定します。  通常、モバイルデバイスでは、ノート pc やデスクトップよりも多くのハードウェア制約があります。そのため、これらの設定では、より強力なデバイスを使用している場合と同じようにページの読み込みを行うことができます。  
1.  [ **Refresh** (更新)] を選び ![ ][ImageRefreshIcon] ます。  DevTools はページを更新し、ページを読み込むために実行されたすべての作業の視覚エフェクトを作成します。  この視覚エフェクトは、 **トレース**として参照されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="ページの読み込みのパフォーマンスパネルトレース" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       ページの読み込みの **パフォーマンス** パネルトレース  
    :::image-end:::  
    
トレースには、左から右へのアクティビティが時系列で表示されます。  上の FPS、CPU、およびネットチャートでは、1秒あたりのフレーム数、CPU アクティビティ、ネットワークアクティビティの概要がわかります。  図の中で、次のように表示される黄色のブロック。これにより、CPU はスクリプトアクティビティで完全にビジー状態になりました。  これは、JavaScript の作業を少なくすることで、ページの読み込み速度を向上させることができることを示しています。  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="トレースの概要セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   トレースの概要セクション  
:::image-end:::  

トレースを調べて、JavaScript の作業を軽減する方法を見つけます。  

1.  [ **タイミング** ] セクションを選択して展開します。  反応しない [タイミング][MDNUserTimingApi] が存在する可能性があるという事実に基づいて、Tony のアプリでは、反応の開発モードが使用されているように見えます。  処理の運用モードに切り替えると、パフォーマンスが簡単になります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="[タイミング] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       [ **タイミング** ] セクション  
    :::image-end:::  
    
1.  [ **タイミング** ] をもう一度選択すると、そのセクションが折りたたまれます。  
1.  **メイン**セクションを参照します。  このセクションでは、左から右へのメインスレッドアクティビティの時系列ログを示します。  Y 軸 (上から下) は、イベントが発生した理由を示しています。  たとえば、次のようにした後に、イベントによって関数が実行されました。これは、実行の原因となった場合などに発生し `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` ます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="メインセクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       **メイン**セクション  
    :::image-end:::  
    
1.  **メイン**セクションの下部まで下にスクロールします。  フレームワークを使っている場合、ほとんどのアクティビティは、通常はコントロール以外のフレームワークによって発生します。  アプリが原因で発生するアクティビティは、通常、下部にあります。  このアプリでは、という名前の関数 `App` が多くの要求を処理しているように見え `mineBitcoin` ます。  Tony のように、ファンのデバイスを使用している可能性があります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="MineBitcoin アクティビティにカーソルを移動する" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       アクティビティにマウスポインターを合わせる `mineBitcoin`  
    :::image-end:::  
    
    > [!NOTE]
    > 通常、フレームワークによって行われる要求はコントロールから除外されますが、フレームワークを効率的に実行するための方法でアプリを構成することもあります。  フレームワークを効果的に使用するようにアプリを再構築することは、メインスレッドの作業を少なくするための手段です。  ただし、フレームワークの動作について深く理解している必要があります。また、フレームワークをより効率的に使用するために、独自のコードで行った変更の種類についても理解しておく必要があります。  
    
1.  [ **ボトムアップ** ] セクションを展開します。  このタブでは、最も時間がかかるアクティビティを中断します。  下のセクションに何も表示されない場合は、 **メイン** セクションのラベルをクリックします。  **ボトムアップ**セクションには、現在選択されているすべてのアクティビティまたは活動のグループの情報のみが表示されます。  たとえば、アクティビティの1つをクリックした場合、 `mineBitcoin` **ボトムアップ** セクションには、その1つのアクティビティの情報のみが表示されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="[ボトムアップ] タブ" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       [ **ボトムアップ** ] タブ  
    :::image-end:::  
    
[ **セルフ時刻** の列には、各アクティビティで直接費やした時間が表示されます。  たとえば、次の図では、メインスレッドの63% が関数に費やした時間を示してい `mineBitcoin` ます。  

実行モードを使用し、JavaScript アクティビティを減らすことで、ページの読み込み速度を向上させることができるかどうかを確認します。  プロダクションモードで開始する:  

1.  [エディター] タブで、を開き `webpack.config.js` ます。  
1.  `"mode":"development"`をに変更 `"mode":"production"` します。  
1.  新しいビルドが展開されるまで待ちます。  
1.  ページをもう一度監査します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="プロダクションモードを使用するように webpack を構成した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       プロダクションモードを使用するように webpack を構成した後の監査レポート  
    :::image-end:::  
    
要求を削除して JavaScript のアクティビティを減らし `mineBitcoin` ます。  

1.  [エディター] タブで、を開き `src/App.jsx` ます。  
1.  の要求をにコメントアウトし `this.mineBitcoin(1500)` `constructor` ます。  
1.  新しいビルドが展開されるまで待ちます。  
1.  ページをもう一度監査します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="不要な JavaScript 作業を削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       不要な JavaScript 作業を削除した後の監査レポート  
    :::image-end:::  
    
前回の変更によってパフォーマンスが大幅に向上したようです。  

> [!NOTE]
> このセクションでは、パフォーマンスパネルについて簡単に説明します。  ページのパフォーマンスを分析する方法について詳しくは、「 [パフォーマンス分析のリファレンス][DevtoolsEvaluatePerformanceReference] 」をご覧ください。  

<!--todo: add section when available -->  

#### 実際の環境でのメインスレッドの使用量を少なくする   

一般的に、 **パフォーマンス** パネルは、サイトが読み込むときのアクティビティを理解するための最も一般的な方法です。また、不要なアクティビティを削除する方法についても説明します。  

もっと気に入ったアプローチが必要な場合は、 `console.log()` [ユーザーのタイミング API][MDNUserTimingApi] を使用して、各フェーズの所要時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークすることができます。  

## まとめ   

*   サイトの読み込みパフォーマンスを最適化するために、必ず監査を開始してください。  監査によって基準計画が設定され、改善のヒントを得ることができます。  
*   一度に1つずつ変更し、そのたびにページがどのように変化するかを確認するために、個別に変更を加えます。  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--  
  


-->  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "業績分析リファレンス |Microsoft ドキュメント"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本的な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ-コンテンツのエンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザーのタイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "木のぶれ |webpack"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
