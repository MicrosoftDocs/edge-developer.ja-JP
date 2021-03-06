---
description: Microsoft Edge DevTools メモリ パネルを使用して、高価な関数を識別します。
title: JavaScript ランタイムを高速化する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 682001ae8d265b342e5d6e0725f9f8ac4e298cf8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397602"
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

# <a name="speed-up-javascript-runtime"></a>JavaScript ランタイムを高速化する  

メモリ パネルを使用して、高価な **関数を識別** します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="サンプル プロファイル" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   サンプル プロファイル  
:::image-end:::  

### <a name="summary"></a>要約  

*   [メモリ] パネルの [割り当てサンプリング] を使用して、呼び出された関数と必要なメモリの量を **正確に記録** します。  
*   プロファイルを炎上グラフとして視覚化します。  
    
## <a name="record-a-sampling-profile"></a>サンプリング プロファイルの記録  

JavaScript で jank に気付いた場合は、サンプリング プロファイルを収集します。  サンプリング プロファイルは、ページ内の関数に実行時間が費やされる場所を示します。  

1.  DevTools **の [メモリ** ] パネルに移動します。  
1.  [割り当 **てサンプリング] ラジオ ボタン** を選択します。  
1.  [スタート **] を選択します**。  
1.  分析しようとしている内容に応じて、ページを更新するか、ページを操作するか、ページを実行できます。  
1.  完了したら **、[停止** ] ボタンを選択します。  
    
> [!NOTE]
> コンソール ユーティリティ API [を使用して][DevtoolsConsoleUtilities] 、コマンド ラインからプロファイルを記録およびグループ化することもできます。  

## <a name="view-sampling-profile"></a>サンプリング プロファイルの表示  

録音が完了すると、DevTools は [******サンプリング**プロファイル] の [メモリ] パネルに、レコーディングのデータを自動的に設定します。  

既定のビューは **Heavy \(Bottom Up\) です**。  このビューでは、パフォーマンスに最も影響を与えた関数を確認し、各関数の要求パスを確認できます。  

### <a name="change-sort-order"></a>並べ替え順序の変更  

並べ替え順序を変更するには、フォーカス選択関数 **\(** フォーカス選択関数 \) アイコンの横にあるドロップダウン メニューを選択し、次のいずれかのオプション ![ ][ImageFocusIcon] を選択します。

**グラフ**.  記録の時系列グラフを表示します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="フレーム グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   フレーム グラフ  
:::image-end:::  

**Heavy \(Bottom Up\)**.  パフォーマンスに影響を与える関数を一覧表示し、関数への呼び出しパスを確認できます。  これは既定のビューです。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="重いグラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   重いグラフ  
:::image-end:::  

**Tree \(Top Down\)**.  呼び出し履歴の上部から始まる呼び出し構造の全体像を示します。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="ツリー グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   ツリー グラフ  
:::image-end:::  

### <a name="exclude-functions"></a>関数を除外する  

サンプリング プロファイルから関数を除外するには、その関数を選択し、選択した **関数を除外** する \( 選択した関数 \) を ![ 除外するボタン ][ImageExcludeIcon] を選択します。  除外された関数 \(child\) の要求関数 \(parent\) は、除外された関数 \(child\) に割り当てられた割り当てられたメモリで課金されます。  

[すべての **関数を復元する** ] \( [すべての関数を復元する\] ボタンを選択して、除外されているすべての関数を記録 ![ ][ImageRestoreIcon] に戻します。  

## <a name="view-sampling-profile-as-chart"></a>サンプリング プロファイルをグラフとして表示する  

グラフ ビューは、サンプリング プロファイルの時間の間に視覚的な表現を提供します。  

サンプリング プロファイル [を記録した後、](#record-a-sampling-profile)並べ替え順序を [グラフ] に変更して、録音をフレーム [グラフとして](#change-sort-order) 表示 **します**。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="フレーム グラフ ビュー" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   フレーム グラフ ビュー  
:::image-end:::  

フレーム グラフは 2 つの部分に分割されます。  

| index | パーツ | 説明 |  
| --- |:--- |:--- |  
| 1 | 概要 | 記録全体の鳥の目のビュー。  バーの高さは、呼び出し履歴の深さに対応します。  そのため、バーが高いほど、呼び出し履歴は深くなります。  |  
| 2 | 呼び出し履歴 | これは、記録中に呼び出された関数の詳細なビューです。  横軸は時間、縦軸は呼び出し履歴です。  スタックはトップダウンで構成されます。  したがって、上の関数は、その下の関数を呼び出しました。  |  

関数はランダムに色付けされます。  他のパネルで使用される色には相関関係はありません。  ただし、関数は常に呼び出し間で同じ色を付け、各ランタイムでパターンを観察できます。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="注釈付きフレーム グラフ" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   注釈付きフレーム グラフ  
:::image-end:::  

高い呼び出し履歴は必ずしも重要ではなく、多くの関数が呼び出されたという意味です。  ただし、幅の広いバーは、関数の完了に長い時間がかかったという意味です。  これらは最適化の候補です。  

### <a name="zoom-in-on-specific-parts-of-recording"></a>記録の特定の部分を拡大する  

通話履歴の特定の部分を拡大するには、マウスの概要を左右に選択、保持、ドラッグします。  ズームすると、選択した録音の一部が通話履歴に自動的に表示されます。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="グラフのズーム" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   グラフのズーム  
:::image-end:::  

### <a name="view-function-details"></a>関数の詳細を表示する  

[ソース] パネルで定義を表示する **関数を選択** します。  

関数にカーソルを合わせると、名前とタイミング データが表示されます。  以下の情報が提供されます。  

| 詳細 | 説明 |  
|:--- |:--- |  
| **Name (名前)** | 関数の名前。  |  
| **自己サイズ** | 関数の現在の呼び出しのサイズ (関数内のステートメントのみを含む)。  |  
| **合計サイズ** | この関数の現在の呼び出しのサイズと、呼び出された関数。  |  
| **URL** | where 形式の関数定義の場所は、関数が定義されているファイルの名前であり、定義の行 `base.js:261` `base.js` `261` 番号です。  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="グラフで関数の詳細を表示する" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   グラフで関数の詳細を表示する  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "profile - コンソール ユーティリティ API リファレンス |Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - コンソール ユーティリティ API リファレンス |Microsoft Docs"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
