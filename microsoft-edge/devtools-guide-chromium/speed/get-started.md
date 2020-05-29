---
title: Microsoft Edge DevTools を使用して Web サイトの速度を最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7efc76fbcb3d1ed6cbd0760f789c8c952030d70c
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611890"
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





# Microsoft Edge DevTools を使用して Web サイトの速度を最適化する   



## チュートリアルの目標  

このチュートリアルでは、Microsoft Edge DevTools を使って、web サイトの読み込みを高速化する方法について説明します。  

## 前提条件  

*   この[Web 開発クラスの概要][CourseraIntroductionWebDevelopmentClass]で説明するように、基本的な web 開発環境を用意する必要があります。  
*   読み込みのパフォーマンスについて何も知りません。  これについては、このチュートリアルで説明します。  

## はじめに   

これは Tony です。  Tony は、cat 協会で非常に有名です。  彼は、お客様がお気に入りの食品について知ることができるように、web サイトを構築しました。  Tony のファンは、サイトを気に入っていますが、サイトの読み込み速度が遅いという苦情を耳にしています。  Tony から、サイトの速度を向上させるように求められました。  

> ##### 図 1  
> 猫を Tony  
> ![猫を Tony][ImageTony]  

## 手順 1: サイトを監査する   

サイトの読み込みのパフォーマンスを向上させるために、**必ず監査を開始して**ください。  
監査には、次の2つの重要な機能があります。  

*   以降の変更を測定するための**基準計画**を作成します。  
*   どのような変更が最も影響を与えるかに関する実用的な**ヒント**が提供されます。  

### 設定   

最初に、後で変更できるようにサイトを設定する必要があります。  

1.  [サイトのソースコードを開き](https://glitch.com/edit/#!/tony)ます。  このタブは [**エディター] タブ**と呼ばれます。  
    
    > ##### 図 2  
    > [エディター] タブ  
    > ![[エディター] タブ][ImageEditor]  

1.  [ **Tony**] を選びます。  メニューが表示されます。  
    
    > ##### 図 3  
    > **Tony**をクリックした後に表示されるメニュー  
    > ![Tony をクリックした後に表示されるメニュー][ImageMenu]  
    
1.  [ **Remix Project**] を選びます。  プロジェクトの名前が**tony**からランダムに生成された名前に変更されます。  これで、独自のコードの編集可能なコピーが作成されました。  後で、このコードを変更することができます。  
1.  [**表示**] を選択し、**新しいウィンドウで**を選択します。  新しいタブでデモが開きます。 このタブは [**デモ] タブ**として参照されます。 サイトが読み込まれるまでには時間がかかることがあります。  
    
    > ##### 図 4  
    > [デモ] タブ  
    > ![[デモ] タブ][ImageDemo]  

1.  `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。  Microsoft Edge の DevTools がデモと共に開きます。  
    
    > ##### 図 5  
    > DevTools とデモ  
    > ![DevTools とデモ][ImageDevtools]  

このチュートリアルの残りのスクリーンショットでは、DevTools が別のウィンドウに表示されています。  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押すと、コマンドメニューが開き、入力した `Undock` 後、**別のウィンドウに装着解除**することができます。  

> ##### 図 6  
> アンドックした DevTools  
> ![アンドックした DevTools][ImageUndocked]  

### ベースラインを確立する   

ベースラインは、パフォーマンスを向上させる前に、サイトがどのように実行されたかを記録したものです。  

1.  [**監査**] タブを選択します。 **さら**に多くのパネルボタンが隠れている可能性があり ![ ][ImageMorePanelsIcon] ます。  監査パネルを累乗するプロジェクトには、 **Lighthouse**という名前が付いているため、このパネルには Lighthouse があります。  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    > ##### 図 7  
    > 監査パネル  
    > ![監査パネル][ImageAudits]  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  監査構成の設定を[図 7](#figure-7)の設定と一致させる。  さまざまなオプションについて説明します。  

    *   **デバイス**。  [**モバイル**に設定] をオンにすると、ユーザーエージェント文字列が変更され、モバイルビューポートがシミュレートされます。  **デスクトップ**に設定することで、**モバイル**の変更が無効になります。  
    *   **監査**。  カテゴリを無効にすると、監査パネルでそれらの監査が実行されなくなり、レポートから監査が除外されます。  提供されている推奨事項の種類を表示する場合は、その他のカテゴリを有効のままにします。  カテゴリを無効にすると、監査プロセスが少し速くなります。  
    *   **調整**。  シミュレートされた**4g の4倍の CPU 速度**は、モバイルデバイスでの一般的な参照条件をシミュレートしています。  監査プロセス中に監査パネルで実際にスロットルされないので、"シミュレート" という名前が付けられます。  代わりに、ページがモバイルの条件下で読み込むのにかかる時間を extrapolates だけです。  一方、適用された [. **..** ] 設定では、より多くの監査プロセスの代わりに、CPU とネットワークのスロットルが実際に行われます。  
    *   **ストレージをクリア**します。  このチェックボックスを有効にすると、ページに関連付けられているすべてのストレージが、各監査前に消去されます  この設定は、サイトでの初回の閲覧者の操作性を監査する場合にオンのままにしておきます。  この設定は、ユーザーが繰り返しアクセスするときに無効にします。  

1.  [**監査の実行**] を選びます。  10秒から30秒後に、監査パネルにサイトのパフォーマンスのレポートが表示されます。  
    
    > ##### 図 8  
    > サイトのパフォーマンスの監査パネルのレポート  
    > ![サイトのパフォーマンスの監査パネルのレポート][ImageReport]  

#### レポートのエラーを処理する   

監査パネルレポートにエラーが表示された場合は、他のタブが開いていない**InPrivate**ウィンドウで [デモ] タブを実行してみてください。  これにより、Microsoft Edge をクリーンな状態から実行することができます。  特に Microsoft Edge Extensions は、監査プロセスの妨げになることがよくあります。  

<!--todo: add screen capture for error in audit -->  
<!--
> ##### old Figure 9  
> A report that errored  
> ![A report that errored][ImageError]  
-->  

### レポートを理解する   

レポートの上部に表示される数値は、サイトの全体的なパフォーマンススコアです。  後でコードを変更すると、この数値の増加が確認できます。  高いスコアは、パフォーマンスが向上することを意味します。  

> ##### 図 9  
> 全体的なパフォーマンススコア  
> ![全体的なパフォーマンススコア][ImageOverall]  

[**メトリック**] セクションには、サイトのパフォーマンスの定量的な測定値が表示されます。  各メトリックは、パフォーマンスのさまざまな側面について把握します。  たとえば、**最初の Contentful 塗料**は、画面に最初にコンテンツが描画されたときに表示されます。これは、ユーザーがページの読み込みにおいて重要なマイルストーンであり、**対話型**のときには、ユーザーの操作を処理するのに必要なページが表示されている点を示します。  

> ##### 図 10  
> [メトリック] セクション  
> ![Metrics] セクション[ImageMetrics]  

[図 11](#figure-11)の強調表示されたトグルボタンを選択して各指標の説明を表示し、[**詳細**情報] をクリックしてその概要に関するドキュメントを参照します。  

> ##### 図 11  
> 強調表示されたトグルボタンを選択して、[ **Metrics** ] 項目を展開する  
> ![強調表示されているトグルボタンを選択して指標項目を展開する][ImageFirstMeaningfulPaint]  

メトリックの下には、ページが読み込まれたときにどのように見えるかを示すスクリーンショットのコレクションがあります。  

> ##### 図 12  
> ページの読み込み中の画面のスクリーンショット  
> ![読み込み中のページの外観のスクリーンショット][ImageScreenshots]  

[**営業案件**] セクションでは、この特定のページの読み込みパフォーマンスを向上させるためのヒントを紹介します。  

> ##### 図 13  
> [営業案件] セクション  
> ![営業案件] セクション[ImageOpportunities]  

詳細については、[営業案件] を選択します。  

> ##### 図 14  
> **レンダーブロックリソースの機会を排除**する  
> ![レンダーブロックリソースの機会の排除][ImageCompression]  

[**詳細情報**] を選択して、営業案件が重要である理由と、その解決方法に関する具体的な推奨事項についてのドキュメントを表示します。  

> ##### 図 15  
> **レンダーブロックリソース**の機会を減らすためのドキュメント  
> ![レンダーブロックリソースの機会の削減] のドキュメント[ImageReference]  

[**診断**] セクションには、ページの読み込み時間に影響する要因についての詳細情報が表示されます。  

> ##### 図 16  
> [診断] セクション  
> ![診断セクション][ImageDiagnostics]  

[**成功**した監査] セクションには、サイトが正常に動作していることが示されます。  セクションを展開する場合に選択します。  

> ##### 図 17  
> [成功した監査] セクション  
> ![成功した監査] セクション[ImagePassed]  

## 手順 2: 実験   

監査レポートの [営業案件] セクションには、ページのパフォーマンスを向上させるためのヒントが表示されます。  このセクションでは、コードベースへの推奨される変更を実装します。各変更の後でサイトを監査し、サイトの速度にどのような影響があるかを測定します。  

### テキストの圧縮を有効にする   

レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。  テキスト圧縮を有効にすると、ページのパフォーマンスを向上させることができます。  

テキストファイルをネットワーク経由で送信する前に、テキストファイルのサイズを縮小 (圧縮) する場合。  メールのサイズを小さくするためにメールを送信する前に、どのようにしてフォルダーを zip 圧縮するかなどです。  

圧縮を有効にする前に、テキストリソースが圧縮されているかどうかを手動で確認する方法がいくつかあります。  

1.  [**ネットワーク**] タブを選択します。  
    
    > ##### 図18  
    > [ネットワーク] パネル  
    > ![ネットワークパネル][ImageNetwork]  
    
1.  [**ネットワーク設定**] アイコンを選択します。  
1.  [**大きな要求行を使用する**] チェックボックスをオンにします。  ネットワーク要求のテーブルの行の高さが増加します。  
    
    > ##### 図19  
    > ネットワーク要求テーブルの大きな行  
    > ![ネットワーク要求テーブルの大きい行][ImageLargeRows]  
    
1.  ネットワーク要求のテーブルに [**サイズ**] 列が表示されない場合は、テーブルの見出しをクリックして、[**サイズ**] を選択します。  

各**Size**セルには2つの値が表示されます。  上の値は、ダウンロードしたリソースのサイズです。  
ボトム値は、圧縮されていないリソースのサイズです。  2つの値が同じである場合は、ネットワーク経由で送信されたときにリソースが圧縮されていないことを意味します。  たとえば、[図 19](#figure-19)では、の上位と下位の値は and で指定し `bundle.js` `1.2 MB` `1.2 MB` ます。  

リソースの HTTP ヘッダーを調べて、圧縮を確認します。  

1.  [ **Js**] を選びます。  
1.  [**ヘッダー** ] タブを選択します。  
    
    > ##### 図20  
    > [ヘッダー] タブ  
    > ![ヘッダー] タブ[ImageHeaders]  
    
1.  ヘッダーの [**応答ヘッダー** ] セクションを検索し `content-encoding` ます。  圧縮されていないことを示すものは表示されません `bundle.js` 。  リソースが圧縮されている場合、このヘッダーは通常、、またはに設定され `gzip` `deflate` `br` ます。  これらの値の説明については、「[ディレクティブ][MDNContentEncodingDirectives]」を参照してください。  

説明が必要です。  変更を加える時間  テキストの圧縮を有効にするには、数行のコードを追加します。  

1.  [エディター] タブで、[**サーバー .js**] をクリックします。  
    
    > ##### 図21  
    > サーバーの編集  
    > ![編集サーバー .js][ImageServer]  
    
1.  次のコードを**サーバー .js**に追加します。  前に必ず入力してください `app.use(compression())` `app.use(express.static('build'))` 。  

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
    
1.  サイトの新しいビルドが展開されるのを待ちます。  [**ツール**] の横にある凝ったアニメーションは、サイトが再構築されて再展開されることを意味します。  [**ツール**] の横にあるアニメーションが消えると、変更がすぐにできます。  [**表示**] を選択し、**新しいウィンドウで**もう一度選択します。  
    
    <!--
    > ##### Old Figure 22  
    > The animation that indicates that the site is getting built  
    > ![The animation that indicates that the site is getting built][ImageBuilding]  
    -->  
    
以前に学習したワークフローを使用して、圧縮が機能していることを手動で確認します。  

1.  [デモ] タブに戻り、ページを再読み込みします。  これで、[**サイズ**] 列に、次のようなテキストリソースの2つの異なる値が表示され `bundle.js` ます。  [図 23](#figure-23)では、[の最大値 `256 KB` `bundle.js` ] はネットワーク経由で送信されたファイルのサイズであり、の下の値は圧縮されていない `1.2 MB` ファイルサイズです。  
    
    > ##### 図22  
    > [サイズ] 列に、テキストリソースの2つの異なる値が表示されるようになりました  
    > ![Size] 列には、テキストリソースに対して2つの異なる値が表示されるようになりました。[ImageRequests]  
    
1.  [**応答ヘッダー** ] セクションに、 `bundle.js` ヘッダーを含めるようになりました `content-encoding: gzip` 。
    
    > ##### 図23  
    > 応答ヘッダーセクションにコンテンツエンコードヘッダーが含まれるようになりました  
    > ![応答ヘッダー] セクションには、コンテンツエンコードヘッダーが含まれています。[ImageGzip]  
    
ページをもう一度監査して、ページの読み込みパフォーマンスにどのような影響があるかを測定します。  

1.  [**監査**] タブを選択します。  
1.  [**監査**の実行] を選択し ![ ][ImagePerformIcon] ます。  
1.  設定は前の設定のままにしておきます。  
1.  [**監査の実行**] を選びます。  
    
    > ##### 図24  
    > テキストの圧縮を有効にした後の監査レポート  
    > ![テキスト圧縮を有効にした後の監査レポート][ImageReport2]  
    
Woohoo!  進行状況のように表示されます。  全体的なパフォーマンススコアは高くなります。つまり、サイトの速度が速くなります。  

#### 現実世界でのテキスト圧縮   

ほとんどのサーバーでは、圧縮を有効にするための単純な修正プログラムが用意されています。  テキストの圧縮に使用するサーバーを構成する方法について、検索を行うだけです。  

### 画像のサイズを変更する   

レポートでは、大量のネットワークペイロードを回避することが、ページのパフォーマンスを向上させるための最上位の機会の1つであることを示しています。  画像のサイズを変更すると、ネットワークペイロードのサイズを小さくすることができます。  ユーザーが500ピクセル幅のモバイルデバイス画面で画像を表示している場合、1500ピクセル幅の画像を送信することはまったくありません。  理想的には、500ピクセル幅の画像を送信することをお勧めします。  

1.  レポートで、[**大量のネットワークペイロード**を使用しない] をクリックして、サイズを変更する画像を確認します。  Jpg ファイルのうち2つは 2000 KB を超えるようですが、これは必要以上に大きくなります。  
    
    <!--
    > ##### Old Figure 27  
    > Details about the **Properly size images** opportunity  
    > ![Details about the properly size images opportunity][ImageResize]  
    -->

1.  [エディター] タブに戻り、[] を開き `src/model.js` ます。  
1.  置換後 `const dir = 'big'` の文字列 `const dir = 'small'`  このディレクトリには、サイズ変更された同じ画像のコピーが含まれています。  
1.  この変更が読み込みのパフォーマンスにどのように影響するかを確認するには、ページをもう一度監査します。  
    
    > ##### 図25  
    > 画像のサイズを変更した後の監査レポート  
    > !(画像のサイズを変更した後の監査レポート)[ImageReport3]  

変更は、全体的なパフォーマンススコアに対して軽微な影響を与えるようです。  ただし、スコアが明確に表示されない場合は、ユーザーに保存されているネットワークデータの量です。  以前の写真の合計サイズは、5.3 mb になりましたが、現時点では 0.18 mb にすぎません。  

#### 実際の画像のサイズ変更   

小規模のアプリでは、1回限りのサイズ変更を行っても問題が生じる可能性があります。  ただし、大規模なアプリでは、このようなスケーラビリティはありません。  大規模なアプリでイメージを管理するためのいくつかの方法を次に示します。  

*   ビルドプロセス中に画像のサイズを変更します。  
*   ビルドプロセス中に各画像のサイズを複数作成し、 `srcset` コードで使用します。  実行時には、ブラウザーは、デバイスに最適なサイズを選択する必要があります。  
    <!--See [Relative-sized images][relative].  -->

<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   要求時に画像のサイズを動的に変更できるようにするイメージ CDN を使用します。  
*   少なくとも、各画像を最適化します。  これにより、大幅に節約できます。  
  最適化とは、画像ファイルのサイズを小さくする特殊なプログラムで画像を実行する場合に使用されます。  その他のヒントについては、「[重要な画像の最適化][EssentialImageOptimization]」をご覧ください。  

### レンダーブロックリソースを排除する   

最新のレポートでは、レンダーブロックのリソースを除去することが最大の機会になりました。  

レンダーブロックリソースは、ページを表示する前に、ブラウザーがダウンロード、解析、実行する必要がある外部 JavaScript または CSS ファイルです。  目的は、ページを適切に表示するために必要なコア CSS と JavaScript コードを実行することだけです。  

最初のタスクでは、ページの読み込み時に実行する必要がないコードが検索されます。  

1.  [**レンダーブロックリソースの削除**] を選択して、ブロックされているリソースを確認します。  
    `lodash.js` および `jquery.js` 。  
    
    > ##### 図26  
    > **レンダーブロックリソース**の機会の削減に関するその他の情報  
    > ![レンダーブロックリソースの機会の削減] の詳細情報[ImageRender]  
    
1.  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押してコマンドメニューを開き、入力を開始して、[ `Coverage` **カバレッジの表示**] を選択します。  
    
    > ##### 図27  
    > 監査パネルからコマンドメニューを開く  
    > ![監査パネルからコマンドメニューを開く][ImageCommandMenu]  
    
    > ##### 図28  
    > [カバレッジ] タブ  
    > ![範囲] タブ[ImageCoverage]  
    
1.  [**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。  [**カバレッジ**] タブには、ページの読み込み時にのコードの量の概要が表示され `bundle.js` `jquery.js` `lodash.js` ます。  [図 30](#figure-30)は、76% と JQuery と lodash のファイルの30% が使用されないことを示しています。  
    
    > ##### 図29  
    > カバレッジレポート  
    > ![カバレージレポート][ImageCoverageReport]  
    
1.  **Jquery**という行を選択します。  DevTools [ソース] パネルでファイルを開きます。  横に青色のバーが表示されている場合は、コード行が実行されます。  赤色のバーは、実行されなかったため、ページの読み込み時には必要ありません。  
    
    > ##### 図30  
    > ソースパネルで jQuery ファイルを表示する  
    > ![ソースパネルで jQuery ファイルを表示][ImageJQuery]  
    
1.  JQuery コードを1ビットずつスクロールします。  "実行" を取得する行の一部は、実際にはコメントにすぎません。  このコードを実行するときには、コメントを取り除くための別の方法として、このファイルのサイズを小さくする方法もあります。  

つまり、独自のコードを操作している場合、[カバレッジ] タブでは、コードの分析や行ごとの分析を行うことができます。また、ページの読み込みに必要なコードのみを提供します。  

ページの `jquery.js` `lodash.js` 読み込みにもファイルが必要ですか?  [要求のブロック] タブには、リソースが利用できない場合の動作が表示されます。  

1.  [**ネットワーク**] タブを選択します。  
1.  `Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) キーを押して、もう一度コマンドメニューを開きます。  
1.  入力を開始し `blocking` 、[**要求ブロックの表示**] を選択します。  
    
    > ##### 図31  
    > [要求のブロック] タブ  
    > ![要求のブロック] タブ[ImageBlocking]  
    
1.  [模様の追加パターンの**追加**] を選択し、 ![ ][ImageAddPatternIcon] 「 `/libs/*` 」と入力して、 `Enter` 確認します。  
    
    > ##### 図32  
    > ディレクトリへの要求をブロックするためのパターンを追加する `libs`  
    > ![パターンを追加して、ライブラリディレクトリへの要求をブロックする][Imagん Bs]  
    
1.  ページを最新の情報に更新してください。  JQuery と Lodash の要求は赤で、要求がブロックされたことを意味します。   ページは依然として読み込まれ、対話型であるため、これらのリソースは必要ではないようです。  
    
    > ##### 図33  
    > [ネットワーク] パネルに、リクエストがブロックされていることが示される  
    > ![ネットワーク] パネルには、リクエストがブロックされていることが示されます。[ImageBlockedLibs]  
    
1.  [**すべてのパターンの削除**] を選択 ![ ][ImageRemoveIcon] すると、すべてのパターンが削除され、ブロックパターンが削除さ `/libs/*` れます。  

一般的に、[要求のブロック] タブは、特定のリソースが利用できない場合にページがどのように動作するかをシミュレートするのに役立ちます。  

次に、これらのファイルへの参照をコードから削除して、ページをもう一度監査します。  

1.  [エディター] タブに戻り、[] を開き `template.html` ます。  
1.  `<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。  
1.  サイトが再構築され、再展開されるのを待ちます。  
1.  **監査パネルから**ページをもう一度監査します。  全体的なスコアは、もう一度向上させる必要があります。  
    
    > ##### 図34  
    > レンダーブロックリソースを削除した後の監査レポート  
    > ![レンダーブロックリソースを削除した後の監査レポート][ImageReport4]  

#### 現実世界での重大なレンダリングパスの最適化   

**クリティカルレンダリングパス**は、ページの読み込みに必要なコードを指します。  一般的には、ページの読み込み中にクリティカルコードのみを配布することにより、ページの読み込みを高速化し、その他のすべての機能を遅延読み込みします。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   完全に削除できるスクリプトを見つけることはできませんが、ページの読み込み中に要求する必要のないスクリプトが数多くあり、非同期で要求される可能性があります。  <!--See [Using async or defer][async].  -->  
*   フレームワークを使用している場合は、プロダクションモードであるかどうかを確認します。  このモードでは、重大なレンダリングをブロックしている不要なコードを取り除くために、[ツリーのシェイク][WebpackTreeShaking]などの機能を使用する場合があります。  

<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### メインスレッドの作業量を少なくする   

最新のレポートでは、[営業案件] セクションで若干の節約が可能になりますが、[診断] セクションで確認すると、最大のボトルネックはメインスレッドのアクティビティが多すぎるようです。  

メインスレッドでは、HTML、CSS、JavaScript の解析や実行など、ページを表示するために必要な作業のほとんどがブラウザーで行われます。  

目標として、[パフォーマンス] パネルを使用して、ページの読み込み中にメインスレッドで実行されている作業を分析し、不要な作業を延期または削除する方法を見つけます。  

1.  [**パフォーマンス**] タブを選択します。  
1.  [**キャプチャ設定** ![ キャプチャの設定] を選択し ][ImageCaptureIcon] ます。  
1.  [**ネットワーク**] を [ **3g** ] と [ **CPU** ] から [ **6x**] の速度に設定します。  通常、モバイルデバイスでは、ノート pc やデスクトップよりも多くのハードウェア制約があります。そのため、これらの設定では、より強力なデバイスを使用している場合と同じようにページの読み込みを行うことができます。  
1.  [**更新の更新]** を選び ![ ][ImageRefreshIcon] ます。  DevTools はページを更新し、ページを読み込むために実行されたすべての作業の視覚エフェクトを作成します。  この視覚エフェクトは、**トレース**として参照されます。  
    
    > ##### 図35  
    > ページの読み込みのパフォーマンスパネルトレース  
    > ![ページの読み込みのパフォーマンスパネルトレース][ImagePerformance]  

トレースには、左から右へのアクティビティが時系列で表示されます。  上の FPS、CPU、およびネットチャートでは、1秒あたりのフレーム数、CPU アクティビティ、ネットワークアクティビティの概要がわかります。  [図 37](#figure-37)に表示される黄色のブロックは、CPU がスクリプト処理によって完全にビジー状態であったことを意味します。  これは、JavaScript の作業を少なくすることで、ページの読み込み速度を向上させることができることを示しています。  

> ##### 図36  
> トレースの概要セクション  
> ![トレースの概要] セクション[ImageOverview]  

トレースを調べて、JavaScript の作業を軽減する方法を見つけます。  

1.  [**タイミング**] セクションを選択して展開します。  反応しない[タイミング][MDNUserTimingApi]が存在する可能性があるという事実に基づいて、Tony のアプリでは、反応の開発モードが使用されているように見えます。  処理の運用モードに切り替えると、パフォーマンスが簡単になります。  
    
    > ##### 図37  
    > [タイミング] セクション  
    > ![タイミング] セクション[ImageUserTiming]  

1.  [**タイミング**] をもう一度選択すると、そのセクションが折りたたまれます。  
1.  **メイン**セクションを参照します。  このセクションでは、左から右へのメインスレッドアクティビティの時系列ログを示します。  Y 軸 (上から下) は、イベントが発生した理由を示しています。  たとえば、[図 39](#figure-39)では、このイベントによって関数が実行されていました。これは、実行の原因となった実行の原因 `Evaluate Script` となり `(anonymous)` `(anonymous)` `__webpack__require__` ます。  
    
    > ##### 図38  
    > メインセクション  
    > ![メイン] セクション[ImageMain]  

1.  **メイン**セクションの下部まで下にスクロールします。  フレームワークを使っている場合、ほとんどのアクティビティは、通常はコントロール以外のフレームワークによって発生します。  アプリが原因で発生するアクティビティは、通常、下部にあります。  このアプリでは、という名前の関数 `App` が多くの要求を処理しているように見え `mineBitcoin` ます。  Tony のように、ファンのデバイスを使用している可能性があります。  
    
    > ##### 図39  
    > アクティビティの上にマウスポインターを置く `mineBitcoin`  
    > ![MineBitcoin アクティビティの上にマウスポインターを置く][ImageMine]  
    
    > [!NOTE]
    > 通常、フレームワークによって行われる要求はコントロールから除外されますが、フレームワークを効率的に実行するための方法でアプリを構成することもあります。  フレームワークを効果的に使用するようにアプリを再構築することは、メインスレッドの作業を少なくするための手段です。  ただし、フレームワークの動作について深く理解している必要があります。また、フレームワークをより効率的に使用するために、独自のコードで行った変更の種類についても理解しておく必要があります。  

1.  [**ボトムアップ**] セクションを展開します。  このタブでは、最も時間がかかるアクティビティを中断します。  下のセクションに何も表示されない場合は、**メイン**セクションのラベルをクリックします。  **ボトムアップ**セクションには、現在選択されているすべてのアクティビティまたは活動のグループの情報のみが表示されます。  たとえば、アクティビティの1つをクリックした場合、 `mineBitcoin` **ボトムアップ**セクションには、その1つのアクティビティの情報のみが表示されます。  
    
    > ##### 図40  
    > [ボトムアップ] タブ  
    > ![ボトムアップ] タブ[Imageボトムアップ]  

[**セルフ時刻**の列には、各アクティビティで直接費やした時間が表示されます。  たとえば、[図 41](#figure-41)は、メインスレッドの63% が関数に費やした時間を示してい `mineBitcoin` ます。  

実行モードを使用し、JavaScript アクティビティを減らすことで、ページの読み込み速度を向上させることができるかどうかを確認します。  プロダクションモードで開始する:  

1.  [エディター] タブで、を開き `webpack.config.js` ます。  
1.  `"mode":"development"`をに変更 `"mode":"production"` します。  
1.  新しいビルドが展開されるまで待ちます。  
1.  ページをもう一度監査します。  
    
    > ##### 図41  
    > プロダクションモードを使用するように webpack を構成した後の監査レポート  
    > ![運用モードを使用するように webpack を構成した後の監査レポート][ImageReport5]  

要求を削除して JavaScript のアクティビティを減らし `mineBitcoin` ます。  

1.  [エディター] タブで、を開き `src/App.jsx` ます。  
1.  の要求をにコメントアウトし `this.mineBitcoin(1500)` `constructor` ます。  
1.  新しいビルドが展開されるまで待ちます。  
1.  ページをもう一度監査します。  
    
    > ##### 図42  
    > 不要な JavaScript 作業を削除した後の監査レポート  
    > ![監査レポートの不要な JavaScript 作業を削除した後][ImageReport6]  

前回の変更によってパフォーマンスが大幅に向上したようです。  

> [!NOTE]
> このセクションでは、パフォーマンスパネルについて簡単に説明します。  ページのパフォーマンスを分析する方法について詳しくは、「[パフォーマンス分析のリファレンス][DevtoolsEvaluatePerformanceReference]」をご覧ください。  

<!--todo: add section when available -->  

#### 実際の環境でのメインスレッドの使用量を少なくする   

一般的に、**パフォーマンス**パネルは、サイトが読み込むときのアクティビティを理解するための最も一般的な方法です。また、不要なアクティビティを削除する方法についても説明します。  

もっと気に入ったアプローチが必要な場合は、 `console.log()` [ユーザーのタイミング API][MDNUserTimingApi]を使用して、各フェーズの所要時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークすることができます。  

## まとめ   

*   サイトの読み込みパフォーマンスを最適化するために、必ず監査を開始してください。  監査によって基準計画が設定され、改善のヒントを得ることができます。  
*   一度に1つずつ変更し、そのたびにページがどのように変化するかを確認するために、個別に変更を加えます。  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--    -->  



<!-- image links -->  

[ImageAddPatternIcon]: /microsoft-edge/devtools-guide-chromium/media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: /microsoft-edge/devtools-guide-chromium/media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-panels-icon.msft.png  
[ImagePerformIcon]: /microsoft-edge/devtools-guide-chromium/media/perform-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/reload-icon.msft.png  
[ImageRemoveIcon]: /microsoft-edge/devtools-guide-chromium/media/remove-icon.msft.png  

[ImageTony]: /microsoft-edge/devtools-guide-chromium/media/speed-tony.msft.png "図 1: 猫を Tony"  
[ImageEditor]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js.msft.png "図 2: [エディター] タブ"  
[ImageMenu]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-server-js-remix-project.msft.png "図 3: [tony] をクリックした後に表示されるメニュー"  
[ImageDemo]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live.msft.png "図 4: [デモ] タブ"  
[ImageDevtools]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-show-live-console.msft.png "図 5: DevTools とデモ"  
[ImageUndocked]: /microsoft-edge/devtools-guide-chromium/media/speed-console.msft.png "図 6: アンドックした DevTools"  
[ImageAudits]: /microsoft-edge/devtools-guide-chromium/media/speed-audits-performance.msft.png "図 7: 監査パネル"  
[ImageReport]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png "図 8: サイトのパフォーマンスの監査パネルのレポート"  
<!--[ImageError]: /microsoft-edge/devtools-guide-chromium/media/speed-.msft.png "Old Figure 9: A report that errored"  -->  
[ImageOverall]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png "図 9: 全体的なパフォーマンススコア"  
[ImageMetrics]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png "図 10: メトリックセクション"  
[ImageFirstMeaningfulPaint]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png "図 11: 強調表示されたトグルボタンを選択して、メトリクス項目を展開する"  
[ImageScreenshots]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png "図 12: 読み込み中のページの外観のスクリーンショット"  
[ImageOpportunities]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities.msft.png "図 13: 営業案件セクション"  
[ImageCompression]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png "図 14: レンダーブロックリソースの営業案件を除去する"  
[ImageReference]:/microsoft-edge/devtools-guide-chromium/media/speed-web-dev-performance-audits.msft.png "図 15: レンダーブロックリソースの機会を減らすためのドキュメント"  
[ImageDiagnostics]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png "図 16: 診断セクション"  
[ImagePassed]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png "図 17: 成功した監査セクション"  
[ImageNetwork]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network.msft.png "図 18: [ネットワーク] パネル  
[ImageLargeRows]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png "図 19: ネットワーク要求テーブルの大きな行"  
[ImageHeaders]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png "図 20: [ヘッダー] タブ  
[ImageServer]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js.msft.png "図 21: サーバーの編集"  
<!--[ImageBuilding]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-server-js-edited.msft.png "Old Figure 22: The animation that indicates that the site is getting built"  -->  
[ImageRequests]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-main.msft.png "図 22: Size 列にテキストリソースの2つの異なる値が表示されるようになりました"  
[ImageGzip]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png "図 23: 応答ヘッダーセクションにヘッダーが表示されるようになりました `content-encoding` "  
[ImageReport2]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance.msft.png "図 24: テキストの圧縮を有効にした後の監査レポート"  
<!--[ImageResize]: /microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png "Old Figure 27: Details about the properly size images opportunity"  -->
[ImageReport3]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-compression-small-images-audits-performance.msft.png "図 25: 画像のサイズを変更した後の監査レポート"  
[ImageRender]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png "図 26: レンダーブロックリソースの機会の削減」に関する詳細情報  
[ImageCommandMenu]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png "図 27: [監査] パネルからコマンドメニューを開く」  
[ImageCoverage]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png "Figure 28: [カバレッジ] タブ  
[ImageCoverageReport]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png "図 29: カバレッジレポート"  
[ImageJQuery]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png "図 30: ソースパネルでの jQuery ファイルの表示"  
[ImageBlocking]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png "図 31: [要求のブロック] タブ"  
[Imagん Bs]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png "図 32: パターンを追加して、ライブラリディレクトリへの要求をブロックする"  
[ImageBlockedLibs]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png "図 33: ネットワークパネルに要求がブロックされていることが示されています"  
[ImageReport4]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png "図 34: レンダーブロックリソースを削除した後の監査レポート"  
[ImagePerformance]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png "図 35: ページの読み込みのパフォーマンスパネルトレース  
[ImageOverview]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png "図 36: トレースの概要セクション  
[ImageUserTiming]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png "図 37: タイミングセクション"  
[ImageMain]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png "図 38: メインセクション"  
[ImageMine]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png "図 39: mineBitcoin アクティビティをマウスでポイントする  
[Imagebottom Up]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png "図 40: ボトムアップタブ"  
[ImageReport5]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png "図 41: webpack を使用して運用モードを使うように構成した後の監査レポート  
[ImageReport6]:/microsoft-edge/devtools-guide-chromium/media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png "図 42: 不要な JavaScript 作業を削除した後の監査レポート"  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "業績分析のリファレンス"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本的な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ-コンテンツのエンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザーのタイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "木のぶれ |webpack"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
