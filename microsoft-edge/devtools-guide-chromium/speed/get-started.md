---
description: DevTools で web サイトMicrosoft Edge読み込む方法を見つける方法について学習します。
title: DevTools を使用して web サイトMicrosoft Edge最適化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 304cf9e36260b8637af38ed0dfe1ba91f3a56504
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564883"
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
# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a>DevTools を使用して web サイトMicrosoft Edge最適化する  

## <a name="goal-of-tutorial"></a>チュートリアルの目標  

このチュートリアルでは、DevTools Microsoft Edgeを使用して、Web サイトの読み込み速度を向上させる方法について説明します。  

## <a name="prerequisites"></a>前提条件  

*   この 「Web 開発の概要」クラスで説明されているのと同様に、基本的な Web 開発エクスペリエンス [が必要です][CourseraIntroductionWebDevelopmentClass]。  
*   読み込みパフォーマンスについて何も知る必要はありません。  詳細については、このチュートリアルで説明します。  

## <a name="introduction"></a>はじめに  

これは Tony です。  トニーは猫社会で非常に有名です。  ファンが自分の好きな食べ物について学べる Web サイトを構築しました。  彼のファンはサイトを愛していますが、Tony はサイトの読み込み時間が遅いという苦情を聞き続ける。  Tony は、サイトの速度を上げろと頼んだ。  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="猫のトニー" lightbox="../media/speed-tony.msft.png":::
   猫のトニー  
:::image-end:::  

## <a name="step-1-audit-the-site"></a>手順 1: サイトを監査する  

サイトの読み込みパフォーマンスを向上させるために設定する場合は常に、 **監査から始める必要があります**。  
監査には、次の 2 つの重要な機能があります。  

*   それ以降の変更 **を測定** する基準を作成します。  
*   これは、変更 **が最も影響を** 与える影響に関する操作可能なヒントを提供します。  
    
### <a name="set-up"></a>設定  

最初に、後で変更を加えるサイトをセットアップする必要があります。  

1.  [サイトのソース コードを開きます](https://glitch.com/edit/#!/tony)。  このタブは、エディター タブと **呼ばれます**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="[エディター] タブ" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       [ **エディター] タブ**  
    :::image-end:::  
    
1.  Tony **を選択します**。  メニューが表示されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="tony を選択した後に表示されるメニュー" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       tony を選択した後に表示される **メニュー**  
    :::image-end:::  
    
1.  **[Remix Project] を選択します**。  プロジェクトの名前が **tony** からランダムに生成された名前に変わります。  これで、コードの独自の編集可能なコピーが作成されます。  後で、このコードを変更できます。  
1.  [表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。  デモが新しいタブで開きます。 このタブは、デモ タブと **呼ばれます**。 サイトの読み込みには時間がかかる場合があります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="[デモ] タブ" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       [デモ] タブ  
    :::image-end:::  
    
1.  `Control` + `Shift` + `J` \(Windows Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。  Microsoft EdgeDevTools はデモと一緒に開きます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools とデモ" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       DevTools とデモ  
    :::image-end:::  
    
このチュートリアルの残りのスクリーンショットについては、DevTools が別のウィンドウに表示されます。  `Control` + `Shift` + `P` \(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) `Undock` **** を選択してコマンド メニューを開き、入力し、[別のウィンドウにドッキング解除] を選択します。  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="ドッキングされていない DevTools" lightbox="../media/speed-console.msft.png":::
   ドッキングされていない DevTools  
:::image-end:::  

### <a name="establish-a-baseline"></a>ベースラインを確立する  

ベースラインは、パフォーマンスを向上させる前にサイトがどのように実行されたのかの記録です。  

1.  [監査] **ツールを選択** します。  [その他のパネル] \( **More Panels** \) ボタン ![ の ](../media/more-panels-icon.msft.png) 背後に非表示になる場合があります。  このパネルには、監査パネルの電源を供給するプロジェクトが「ライトハウス」という名前なので、ライトハウス **があります**。  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="監査ツール" lightbox="../media/speed-audits-performance.msft.png":::
       監査**ツール**  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  監査構成設定を前の図の監査構成設定と一致します。  さまざまなオプションの説明を次に示します。  
    
    *   **デバイス .**  [モバイル] **に設定** すると、ユーザー エージェント文字列が変更され、モバイル ビューポートがシミュレートされます。  デスクトップに **設定すると** 、モバイルの変更が **オフ** になります。  
    *   **監査**。  カテゴリをオフにし、[監査] パネル **で** これらの監査を実行し、それらの監査をレポートから除外します。  提供される推奨事項の種類を表示する場合は、他のカテゴリをオンのままにします。  カテゴリをオフにし、監査プロセスを少し高速化します。  
    *   **調整 .**  [ **シミュレートされた低速 4G] に設定すると、4 倍の CPU** スローダウンによって、モバイル デバイスでの一般的なブラウズ条件がシミュレートされます。  監査プロセス中に監査パネルが実際に調整されないので、"シミュレート" という名前が付きます。  代わりに、モバイル条件下でページの読み込みにかかる時間を余分に表示します。  一 **方、Applied...** の設定は、より長い監査プロセスのトレードオフを使用して、CPU とネットワークを実際に調整します。  
    *   **[Storage] をStorage**します。  チェック ボックスをオンにすると、すべての監査の前にページに関連付けられているすべての記憶域がクリアされます。  初めての訪問者がサイトを体験する方法を監査する場合は、この設定をオンのままにします。  繰り返し訪問エクスペリエンスが必要な場合は、この設定をオフにします。  
    
1.  [ **監査の実行] を選択します**。  10 ~ 30 秒後に、[ **監査** ] パネルにサイトのパフォーマンスのレポートが表示されます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="サイトのパフォーマンスの [監査] パネルのレポート" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       サイトのパフォーマンスの [監査] パネルのレポート  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a>レポート エラーの処理  

監査パネル レポートでエラーが発生した場合は、他のタブが開いていない **InPrivate** ウィンドウからデモ タブを実行してみてください。  これにより、クリーンな状態からMicrosoft Edge実行できます。  Microsoft Edge特に拡張機能は、多くの場合、監査プロセスに干渉します。  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a>レポートを理解する  

レポートの上部にある数値は、サイトの全体的なパフォーマンス スコアです。  後で、コードを変更すると、表示される番号が上がる必要があります。  スコアが高いほど、パフォーマンスが向上します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="全体的なパフォーマンス スコア" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   全体的なパフォーマンス スコア  
:::image-end:::  

[ **メトリック] セクション** には、サイトのパフォーマンスの定量測定値が表示されます。  各メトリックは、パフォーマンスの異なる側面に関する分析情報を提供します。  たとえば **、First Contentful ペイント**は、コンテンツが最初に画面にペイントされる時期を示します。これは、ページの読み込みに対するユーザーの認識における重要なマイルストーンですが、Time **To Interactive**は、ページがユーザーの操作を処理するのに十分な準備ができていると表示されるポイントをマークします。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="[メトリック] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   [ **メトリック]** セクション  
:::image-end:::  

次の図で強調表示されているトグル ボタンを選択して、各指標の説明を表示し****、[詳細] を選択してドキュメントを読み取ってください。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="[メトリック] アイテムを展開するには、強調表示されたトグル ボタンを選択します。" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   [メトリック] アイテムを展開するには、強調表示されたトグル ボタンを選択します。  
:::image-end:::  

[指標] の下には、ページの読み込み時の外観を示すスクリーンショットのコレクションがあります。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="読み込み中のページの外観のスクリーンショット" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   読み込み中のページの外観のスクリーンショット  
:::image-end:::  

[ **機会] セクション** には、この特定のページの読み込みパフォーマンスを向上させる方法に関する具体的なヒントが示されています。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="[商談] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   [ **商談]** セクション  
:::image-end:::  

その詳細を知る機会を選ぶ。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="レンダリングブロックリソースの機会を排除する" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   **レンダリングブロックリソースの機会を排除** する  
:::image-end:::  

[ **詳細] を** 選択して、機会が重要な理由に関するドキュメントと、その修正方法に関する具体的な推奨事項を表示します。  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="レンダリングブロックリソースの排除機会に関するドキュメント" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   レンダリングブロックリソース**の排除機会に関するドキュメント**  
:::image-end:::  

[ **診断] セクション** では、ページの読み込み時間に寄与する要因の詳細について説明します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="[診断] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   [ **診断]** セクション  
:::image-end:::  

[ **渡された監査] セクション** には、サイトの正常な動作が表示されます。  セクションを展開する場合に選択します。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="[渡された監査] セクション" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   [ **渡された監査]** セクション  
:::image-end:::  

## <a name="step-2-experiment"></a>手順 2: 実験  

監査レポートの [機会] セクションには、ページのパフォーマンスを向上させる方法に関するヒントが表示されます。  このセクションでは、コードベースに対して推奨される変更を実装し、変更後にサイトを監査して、サイトの速度に与える影響を測定します。  

### <a name="enable-text-compression"></a>テキスト圧縮を有効にする  

レポートでは、膨大なネットワーク ペイロードを避けることは、ページのパフォーマンスを向上させる最も重要な機会の 1 つだと述べています。  テキスト圧縮を有効にすると、ページのパフォーマンスが向上します。  

テキスト圧縮は、テキスト ファイルをネットワーク上で送信する前に、テキスト ファイルのサイズを小さくするか、圧縮する場合です。  サイズを小さくするために、ディレクトリを送信する前にアーカイブする方法と同様です。  

圧縮を有効にする前に、テキスト リソースが圧縮されているかどうかを手動で確認する方法を次に示します。  

1.  [ネットワーク] **ツールを選択** します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="[ネットワーク] パネル" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       ネットワーク**ツール**  
    :::image-end:::  
    
1.  [ネットワーク設定 **] アイコンを選択** します。  
1.  [大きな **要求行を使用する] チェック ボックスを** オンにします。  ネットワーク要求のテーブル内の行の高さが増加します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="ネットワーク要求テーブルの大きい行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       ネットワーク要求テーブルの大きい行  
    :::image-end:::  
    
1.  ネットワーク要求 **の表** の [サイズ] 列が表示されない場合は、テーブル ヘッダーを [サイズ] > **選択します**。  

[各 **サイズ] セル** には、2 つの値が表示されます。  一番上の値は、ダウンロードしたリソースのサイズです。  
一番下の値は、圧縮されていないリソースのサイズです。  2 つの値が同じ場合は、ネットワークを使用して送信するときにリソースが圧縮されません。  たとえば、前の図では、上と下の値は `bundle.js` 、 `1.2 MB` と です `1.2 MB` 。  

リソースの HTTP ヘッダーを検査して圧縮を確認します。  

1.  を選択します `bundle.js` 。  
1.  [ヘッダー] **パネルを選択** します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="[ヘッダー] パネル" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       [ **ヘッダー]** パネル  
    :::image-end:::  
    
1.  [応答ヘッダー **] セクションで** ヘッダーを `content-encoding` 検索します。  見出 `content-encoding` しは表示されません。つまり、圧縮 `bundle.js` されません。  リソースが圧縮されている場合、通常、このヘッダーは `gzip` 、 、 または `deflate` に設定されます `br` 。  値の説明については、「ディレクティブ」 [に移動します][MDNContentEncodingDirectives]。  

説明で十分です。  いくつかの変更を加える時間。  次の 2 行のコードを追加して、テキスト圧縮を有効にします。  

1.  [エディター] タブで、[編集]**をserver.js。 **  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="編集server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       Edit `server.js`  
    :::image-end:::  
    
1.  次のコードを次のコード**にserver.js。 **  前に置く必要 `app.use(compression())` があります `app.use(express.static('build'))` 。  

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
    > 通常は、パッケージをインストールする必要 `compression` がありますが、 `npm i -S compression` これは既に行っています。  
    
1.  Glitch がサイトの新しいビルドを展開するのを待ちます。  [ツール] の横にある **アニメーションは** 、サイトが再構築され、再展開されるという意味です。  ツールの横にあるアニメーションが消え去った場合、変更 **の準備** ができました。  [表示 **] を** 選択し、[ **新しいウィンドウ] を再度選択** します。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
前に説明したワークフローを使用して、圧縮が機能しているのを手動で確認します。  

1.  デモ タブに戻り、ページを更新します。  [ **サイズ] 列** には、次のようなテキスト リソースに 2 つの異なる値が表示されます `bundle.js` 。  次の図では、for の上の値は、ネットワークを使用して送信されたファイルのサイズで、最下位の値は圧縮されていないファイル サイズ `256 KB` `bundle.js` `1.2 MB` です。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="[サイズ] 列に、テキスト リソースに 2 つの異なる値が表示される" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       [ **サイズ] 列** に、テキスト リソースに 2 つの異なる値が表示される  
    :::image-end:::  
    
1.  [ **応答ヘッダー]** セクションに `bundle.js` ヘッダーが含 `content-encoding: gzip` まれる必要があります。
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="[応答ヘッダー] セクションにコンテンツ エンコード ヘッダーが含まれる" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       [ **応答ヘッダー]** セクションにコンテンツ エンコード ヘッダーが含まれる  
    :::image-end:::  
    
ページを再度監査して、ページの読み込みパフォーマンスに与える影響の種類を測定します。  

1.  [監査] **ツールを選択** します。  
1.  [ **監査を実行する** ]を選択します ![ ([監査を実行 ](../media/perform-icon.msft.png) する]\)。  
1.  設定は以前と同じままにします。  
1.  [監査 **の実行] を選択します**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="テキスト圧縮を有効にした後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       テキスト圧縮を有効にした後の監査レポート  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  全体的なパフォーマンス スコアが上がっている必要があります。つまり、サイトの速度が速くなります。  

#### <a name="text-compression-in-the-real-world"></a>現実世界でのテキスト圧縮  

ほとんどのサーバーには、圧縮を有効にするための簡単な修正が実際に含まれています。  テキストの圧縮に使用するサーバーを構成する方法を検索します。  

### <a name="resize-images"></a>画像のサイズを変更する  

レポートは、膨大なネットワーク ペイロードを避けることは、ページのパフォーマンスを向上させる最も重要な機会の 1 つを示しています。  イメージのサイズを変更すると、ネットワーク ペイロードのサイズを小さくすることができます。  ユーザーが 500 ピクセル幅のモバイル デバイス画面で画像を表示している場合、1500 ピクセル幅の画像を送信しても意味はありません。  理想的には、最大で 500 ピクセル幅の画像を送信します。  

1.  レポートで、[巨大な **ネットワーク ペイロードを避** ける] を選択して、サイズを変更する画像を表示します。  jpg ファイルの 2 つが 2000 KB を超え、必要以上に大きいように見えます。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  [エディター] タブに戻り、を開きます `src/model.js` 。  
1.  に `const dir = 'big'` 置き換える `const dir = 'small'` 。  このディレクトリには、サイズ変更された同じイメージのコピーが含まれています。  
1.  ページを再度監査して、変更が読み込みパフォーマンスに与える影響を表示します。  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="イメージのサイズ変更後の監査レポート" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       イメージのサイズ変更後の監査レポート  
    :::image-end:::  
    
この変更は、全体的なパフォーマンス スコアにのみ影響します。  ただし、スコアが明確に表示されない点の 1 つは、ユーザーを保存しているネットワーク データの量です。  古い写真の合計サイズは約 5.3 メガバイトですが、現在は約 0.18 メガバイトです。  

#### <a name="resizing-images-in-the-real-world"></a>実世界の画像のサイズ変更  

小さなアプリの場合は、このような 1 回のサイズ変更で十分な場合があります。  しかし、大規模なアプリの場合、これは明らかにスケーラブルではありません。  大規模なアプリで画像を管理するための戦略を次に示します。  

*   ビルド プロセス中にイメージのサイズを変更します。  
*   ビルド プロセス中に各イメージの複数のサイズを作成し、コード `srcset` で使用します。  実行時に、ブラウザーはデバイスに最適なサイズを選択します。  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   要求時にCDNサイズを動的に変更できるイメージ コントロールを使用します。  
*   少なくとも、各画像を最適化します。  これにより、大きな節約が生まれる可能性があります。  
  最適化は、イメージ ファイルのサイズを小さくする特別なプログラムを使用してイメージを実行する場合です。  その他のヒントについては、「Essential [Image Optimization」に移動します][EssentialImageOptimization]。  
    
### <a name="eliminate-render-blocking-resources"></a>レンダリングブロックリソースを排除する  

最新のレポートでは、レンダリング ブロック リソースを排除する機会が最大の機会です。  

レンダリング ブロック リソースは、ブラウザーがページを表示する前にダウンロード、解析、および実行する必要がある外部 JavaScript または CSS ファイルです。  目標は、ページを適切に表示するために必要なコア CSS と JavaScript コードのみを実行します。  

最初のタスクは、ページの読み込み時に実行する必要はないコードを見つける方法です。  

1.  [ **レンダリング ブロック リソースを削除する] を選択** して、ブロックしているリソースを表示します。  
    `lodash.js` と `jquery.js` .  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="レンダリングブロックリソースの排除機会の詳細" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       レンダリングブロックリソースの**排除機会の詳細**  
    :::image-end:::  
    
1.  `Control` + `Shift` + `P` \(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\) `Coverage` **** を選択してコマンド メニューを開き、入力を開始し、[カバレッジの表示] を選択します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="[監査] パネルから [コマンド メニュー] を開きます。" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       [監査] パネルから [コマンド メニュー **] を開** きます。  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="カバレッジ ツール" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       カバレッジ**ツール**  
    :::image-end:::  
    
1.  [ **更新** \( ![ Refresh ](../media/reload-icon.msft.png) \] を選択します)。  [ **カバレッジ** ] ツールは、ページの読み込み中に実行されるコードの量の `bundle.js` `jquery.js` `lodash.js` 概要を示します。  次の図では、jQuery ファイルと Lodash ファイルの約 76% と 30% がそれぞれ使用されません。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="カバレッジ レポート" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       カバレッジ レポート  
    :::image-end:::  
    
1.  行を選択 `jquery.js` します。  DevTools は、[ソース] ツールで **ファイルを開** きます。  コード行が実行された場合、その横に青いバーが表示されます。  赤いバーは、コード行が実行されていないという意味で、Web ページの読み込み時には必ず必要とされません。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="ソース ツールでの jQuery ファイルの表示" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       ソース ツールでの jQuery ファイル **の** 表示  
    :::image-end:::  
    
1.  jQuery コードをスクロールします。  実行される行の一部は、実際にはコメントにすら見当たらされません。  コメントを削除し、ファイルのサイズを小さくするには、ミニフィアー アプリまたはスクリプトを使用してコードを実行します。  

つまり、独自のコードを操作する場合、カバレッジ ツール**** を使用すると、コードを 1 行 1 行で分析し、ページ読み込みに必要なコードのみを出荷できます。  

ページを `jquery.js` 読 `lodash.js` み込むにはファイルも必要ですか?  要求 **ブロック ツールは** 、リソースが利用できない場合の動作を表示します。  

1.  [ネットワーク] **ツールを選択** します。  
1.  `Control` + `Shift` + `P` \(Windows Linux\) または \(macOS\) を選択して、コマンド `Command` + `Shift` + `P` メニューを再度開きます。  
1.  入力を開始し `blocking` 、[要求ブロック **の表示] を選択します**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="要求ブロック ツール" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       要求 **ブロック** ツール  
    :::image-end:::  
    
1.  [ **パターンの追加** \( ![ Add Pattern ](../media/add-pattern-icon.msft.png) \), `/libs/*` type, and select to `Enter` confirm.  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="libs ディレクトリへの要求をブロックするパターンを追加する" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       ディレクトリへの要求をブロックするパターンを追加 `libs` する  
    :::image-end:::  
    
1.  ページを最新の情報に更新してください。  jQuery 要求と Lodash 要求は赤で、要求がブロックされました。   ページは読み込み、対話型なので、これらのリソースは一切必要とされていないように見えます。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="[ネットワーク] パネルは、要求がブロックされたと表示されます。" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       ネットワーク **ツール** は、要求がブロックされたと表示されます。  
    :::image-end:::  
    
1.  [ **すべてのパターンを削除する** ] \( ![ Remove all patterns \) を選択して、ブロック ](../media/remove-icon.msft.png) パターンを `/libs/*` 削除します。  
    
一般に、[ **要求のブロック** ] ツールは、特定のリソースが使用できない場合のページの動作をシミュレートする場合に役立ちます。  

次に、コードからこれらのファイルへの参照を削除し、ページを再度監査します。  

1.  [エディター] タブに戻り、を開きます `template.html` 。  
1.  `<script src="/libs/lodash.js">` と `<script src="/libs/jquery.js"></script>` を削除します。  
1.  サイトが再ビルドして再展開するのを待ちます。  
1.  [監査] ツールからページ **を再度監査** します。  全体的なスコアが再び向上している必要があります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="レンダリング ブロック リソースを削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       レンダリング **ブロック リソースを** 削除した後の監査レポート  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a>現実世界でのクリティカル レンダリング パスの最適化  

クリティカル **レンダリング パスは** 、ページを読み込む必要があるコードを参照します。  一般に、ページの読み込み中に重要なコードのみを出荷し、それ以外のコードを遅延読み込みすることで、ページの読み込みを高速化します。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   完全に削除できるスクリプトを見つけ出す可能性は低いですが、ページの読み込み中に要求する必要が生じ、代わりに非同期的に要求されるスクリプトが多数見つかるはずです。  <!--Navigate to [Using async or defer][async].  -->  
*   フレームワークを使用している場合は、実稼働モードを使用している必要があります。  このモードでは、重要なレンダリングを[][WebpackTreeShaking]ブロックしている不要なコードを排除するために、ツリーの揺れなどの機能を使用できます。  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a>メイン スレッドの作業を減らします  

最新のレポートには、[機会] セクションにわずかな節約が表示されますが、[診断] セクションを見下ろした場合、最大のボトルネックはメイン スレッド アクティビティが多すぎるように見えます。  

メイン スレッドは、HTML、CSS、JavaScript の解析と実行など、ページを表示するために必要なほとんどの作業をブラウザーが実行する場所です。  

目標は、[パフォーマンス] パネルを使用して、ページの読み込み中にメイン スレッドが実行している作業を分析し、不要な作業を延期または削除する方法を見つけ出すことです。  

1.  [パフォーマンス] **ツールを選択** します。  
1.  [**キャプチャ] 設定**\( ![ Capture 設定 ](../media/capture-icon.msft.png) \) を選択します。  
1.  [ **ネットワーク] を** **[低速 3G]** に設定し **、CPU** を **6 倍の低速に設定します**。  モバイル デバイスは通常、ラップトップやデスクトップよりもハードウェアの制約が多いので、これらの設定を使用すると、より強力なデバイスを使用している場合と同様に、ページの読み込みも発生します。  
1.  [ **更新** \( ![ Refresh ](../media/reload-icon.msft.png) \] を選択します)。  DevTools はページを更新し、ページを読み込むのに実行されたすべての作業の視覚化を生成します。  この視覚化は、トレースと呼 **ばれます**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="ページ読み込み時のパフォーマンス ツールのトレース" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       ページ **読み** 込み時のパフォーマンス ツールのトレース  
    :::image-end:::  
    
トレースは、左から右にアクティビティを時系列的に表示します。  上部の FPS、CPU、および NET グラフでは、1 秒あたりのフレーム数、CPU アクティビティ、およびネットワーク アクティビティの概要を示します。  次の図の後の図で強調表示されている黄色のブロックは、CPU がスクリプトアクティビティで完全にビジー状態でした。  これは、JavaScript の作業を減らしてページの読み込み速度を上げ得る手がかりです。  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="トレースの [概要] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   トレースの [概要] セクション  
:::image-end:::  

トレースを調査して、JavaScript の作業を少なくする方法を探します。  

1.  [タイミング **] セクションを選択** して展開します。  React から多くのタイミング対策がある可能性があるという[][MDNUserTimingApi]事実に基づいて、Tony のアプリが React の開発モードを使用しているようです。  アプリケーションの実稼働モードに切り替Reactパフォーマンスが低下する可能性があります。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="[タイミング] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       [ **タイミング]** セクション  
    :::image-end:::  
    
1.  もう **一度 [タイミング]** を選択して、そのセクションを折りたたみます。  
1.  [メイン] **セクションを参照** します。  このセクションでは、メイン スレッドアクティビティの時系列ログを左から右に示します。  y 軸 (上から下) は、イベントが発生した理由を示します。  たとえば、次の後の図では、イベントによって関数が実行され、その結果、実行が発生し、実行が引き起こ `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` されました。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="[メイン] セクション" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       [ **メイン]** セクション  
    :::image-end:::  
    
1.  [メイン] セクションの下部まで **下にスクロール** します。  フレームワークを使用する場合、上位のアクティビティの大部分はフレームワークによって引き起こされ、通常は制御が取り外されています。  アプリによって引き起こされたアクティビティは、通常、下部に表示されます。  このアプリでは、という名前の関数が関数に対して多くの要求 `App` を引き起こしている `mineBitcoin` ようです。  トニーがファンのデバイスを使って暗号化を採掘している可能性があるように聞こえます。..  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="mineBitcoin アクティビティにカーソルを合わせる" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       アクティビティにカーソルを合 `mineBitcoin` わせる  
    :::image-end:::  
    
    > [!NOTE]
    > フレームワークが行う要求は通常は制御されませんが、フレームワークを非効率的に実行する方法でアプリを構造化する場合があります。  フレームワークを効率的に使用するためにアプリを再構築すると、メイン スレッドの作業を減らします。  ただし、フレームワークをより効率的に使用するには、フレームワークの動作と、独自のコードで行う変更の種類について深く理解する必要があります。  
    
1.  [ボトム **アップ] セクションを** 展開します。  このタブでは、最も時間がかかったアクティビティを分解します。  [メイン] セクションに何もBottom-Up場合は、[メイン] セクションのラベルを **選択** します。  [ **ボトムアップ] セクション** には、現在選択しているアクティビティまたはアクティビティのグループに関する情報だけが表示されます。  たとえば、アクティビティの 1 つを選択した場合、[ボトムアップ] セクションでは、その 1 つのアクティビティの `mineBitcoin` 情報のみを表示します。 ****  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="[Bottom-Up] タブ" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       [ **ボトムアップ]** タブ  
    :::image-end:::  
    
[Self **Time]** 列には、各アクティビティに直接費やされた時間が表示されます。  たとえば、次の図では、メイン スレッド時間の約 63% が関数に費や `mineBitcoin` されています。  

実稼働モードを使用して JavaScript アクティビティを減らすと、ページの読み込み速度が上がる可能性があるかどうかを確認する時間。  実稼働モードから開始します。  

1.  [エディター] タブで、を開きます `webpack.config.js` 。  
1.  に `"mode":"development"` 変更します `"mode":"production"` 。  
1.  新しいビルドが展開されるのを待ちます。  
1.  ページを再度監査します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="実稼働モードを使用する Webpack を構成した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       実稼働モードを使用する Webpack を構成した後の監査レポート  
    :::image-end:::  
    
要求を削除して JavaScript アクティビティを減らします `mineBitcoin` 。  

1.  [エディター] タブで、を開きます `src/App.jsx` 。  
1.  に要求をコメント `this.mineBitcoin(1500)` アウト `constructor` します。  
1.  新しいビルドが展開されるのを待ちます。  
1.  ページを再度監査します。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="不要な JavaScript 作業を削除した後の監査レポート" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       不要な JavaScript 作業を削除した後の監査レポート  
    :::image-end:::  
    
その最後の変更がパフォーマンスの大きなジャンプを引き起こしたように見えます。  

> [!NOTE]
> このセクションでは、パフォーマンス パネルについて簡単に説明しました。  ページのパフォーマンスを分析する方法の詳細については、「パフォーマンス分析リファレンス [」に移動します][DevtoolsEvaluatePerformanceReference]。  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a>実際の世界でメイン スレッドの動作を減らします  

一般に、 **パフォーマンス ツールは** 、サイトが読み込まれるとどのようなアクティビティを行うのかを理解し、不要なアクティビティを削除する方法を見つける最も一般的な方法です。  

ユーザー タイミング API を使用すると、各フェーズにかかる時間を追跡するために、アプリのライフサイクルの特定のフェーズを任意にマークできます `console.log()` 。 [][MDNUserTimingApi]  

## <a name="summary"></a>要約  

*   サイトの読み込みパフォーマンスを最適化するために設定するたびに、常に監査を開始します。  監査はベースラインを確立し、改善方法に関するヒントを提供します。  
*   一度に 1 つの変更を行い、変更後に Web ページを監査して、分離された変更がパフォーマンスに与える影響を表示します。  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "パフォーマンス分析|Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 開発クラスの概要|Coursera"  

[EssentialImageOptimization]: https://images.guide "重要な画像の最適化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "ディレクティブ - コンテンツ エンコード |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "ユーザー タイミング API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "ツリーの揺れ|webpack"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
