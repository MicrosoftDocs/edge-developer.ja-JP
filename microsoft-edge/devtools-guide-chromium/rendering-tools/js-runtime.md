---
title: JavaScript ランタイムを高速化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2f05ef2911c855df39d60fa732ff5f784ab49473
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984875"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->





# JavaScript の実行時間を短縮する   




**メモリ**パネルを使用して負荷の高い機能を特定します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="サンプリングプロファイル" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   サンプリングプロファイル  
:::image-end:::  

### まとめ  

*   呼び出された関数と、 **メモリ** パネルの割り当てサンプリングで必要なメモリの量を記録します。  
*   プロファイルを炎のグラフとして視覚化します。  
    
## サンプリングプロファイルを記録する  

JavaScript で jank に気付いた場合は、サンプリングプロファイルを収集します。  サンプリングプロファイルは、ページ内の関数で実行時間が消費される場所を示します。  

1.  DevTools の **メモリ** パネルに移動します。  
1.  [ **割り当てのサンプリング** ] ラジオボタンを選択します。  
1.  **[スタート]** を選択します。  
1.  分析しようとしている内容に応じて、ページをもう一度読み込むか、ページを操作するか、またはページを実行します。  
1.  完了したら、[ **停止** ] ボタンを選択します。  
    
> [!NOTE]
> また、 [コンソールユーティリティ API][DevtoolsConsoleUtilities] を使って、コマンドラインからプロファイルの記録とグループ化を行うこともできます。  

## サンプリングプロファイルを表示する  

録音が終了すると、DevTools は、記録されたデータを使って、[**サンプリングプロファイル**] の下に**メモリ**パネルを自動的に設定します。  

既定のビューは [ **ヘビー] (ボトムアップ)** です。  このビューでは、パフォーマンスに最も影響を及ぼしている関数を確認し、その機能への呼び出しパスを調べることができます。  

### 並べ替え順序を変更する   

並べ替え順序を変更するには、[ **選択した関数** \ (フォーカス選択された関数 \)] の横にあるドロップダウンメニューを選択し、 ![ ][ImageFocusIcon] 次のいずれかのオプションを選択します。

**グラフ**。  記録の時系列グラフを表示します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="炎のグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   炎のグラフ  
:::image-end:::  

**ヘビー (ボトムアップ)**  パフォーマンスに影響を与えて関数を一覧表示し、関数への呼び出しパスを調べることができます。  これは既定のビューです。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="ヘビーグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   ヘビーグラフ  
:::image-end:::  

**ツリー \ (上から下へ)**  呼び出し履歴の先頭から、呼び出し元の構造体の全体像が示されます。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="ツリーグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   ツリーグラフ  
:::image-end:::  

### 除外関数   

サンプリングプロファイルから関数を除外するには、関数を選択して選択し、[ **選択した関数を除外** \ ( ![ 選択した関数 \ を除外 ][ImageExcludeIcon] )] アイコンを選択します。  除外関数 \ (子 \) の要求関数 \ (親 \) には、除外された関数 \ (子) に割り当てられた割り当て済みのメモリが割り当てられます。  

すべての関数を **復元** する (すべての関数の復元) アイコンを選択して、除外され ![ たすべて ][ImageRestoreIcon] の関数を記録に戻します。  

## サンプリングプロファイルをグラフとして表示する   

グラフビューでは、時間の経過に伴うサンプリングプロファイルが視覚的に表示されます。  

[サンプリングプロファイルを記録](#record-a-sampling-profile)したら、[[並べ替え順序](#change-sort-order)] を [**グラフ**] に変更して、記録を炎グラフとして表示します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="炎のグラフビュー" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   炎のグラフビュー  
:::image-end:::  

炎のグラフは、2つの部分に分かれています。  

| | 領域 | 説明 |  
| --- |:--- |:--- |  
| 件 | 概要 | レコーディング全体の鳥ビュー。  バーの高さは、通話スタックの深度に対応しています。  そのため、バーが大きくなるほど、さらに多くのコールスタックが表示されます。  |  
| 両面 | 通話スタック | これは、記録中に呼び出された関数の詳細ビューです。  横軸は time と縦軸で、通話スタックです。  スタックは、上から順に並べて整理されます。  そのため、先頭の関数は、その下にある関数の下にあります。  |  

関数はランダムに色付けされます。  他のパネルで使用されている色との関連付けはありません。  ただし、各ランタイムでパターンを表示できるように、呼び出し時には関数の色が常に同じになります。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="注釈付きの炎のグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   注釈付きの炎のグラフ  
:::image-end:::  

長い通話スタックは必ずしも重大ではありません。これは、多くの関数が呼び出されたことを意味します。  ただし、ワイドバーは、関数が完了するまでに時間がかかりすぎることを意味します。  これらは最適化の候補です。  

### 記録の特定の部分を拡大する   

呼び出し履歴の特定の部分を拡大するには、マウスを選択してから、[概要] にドラッグします。  拡大すると、選択した記録の一部が自動的に通話スタックに表示されます。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="拡大されたグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   拡大されたグラフ  
:::image-end:::  

### 関数の詳細の表示   

[関数] を選択して、[ **ソース** ] パネルで定義を表示します。  

関数の上にマウスポインターを移動すると、名前とタイミングのデータが表示されます。  以下の情報が提供されます。  

| 詳しく | 説明 |  
|:--- |:--- |  
| **Name (名前)** | 関数の名前。  |  
| **自己サイズ** | 関数のステートメントのみを含む、関数の現在の呼び出しのサイズ。  |  
| **合計サイズ** | この関数と呼び出された関数の現在の呼び出しのサイズ。  |  
| **URL** | Where の形式での関数定義の場所は、関数が定義されている `base.js:261` `base.js` ファイルの名前であり、 `261` 定義の行番号です。  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="グラフでの関数の詳細の表示" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   グラフでの関数の詳細の表示  
:::image-end:::  

<!--  
## Feedback   


-->  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "コンソールユーティリティ API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "プロファイル-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd-本体ユーティリティー API リファレンス |Microsoft ドキュメント"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) にあり、 [Kayce basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
