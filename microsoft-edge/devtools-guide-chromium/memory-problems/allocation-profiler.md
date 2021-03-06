---
description: タイムラインで Allocation インストルメンテーションを使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。
title: タイムラインで割り当てインストルメンテーションを使用する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 374b7f0ad80b8975319b2b0ec5cecf42ce4bde82
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397819"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->

# <a name="how-to-use-allocation-instrumentation-on-timeline"></a>タイムラインで割り当てインストルメンテーションを使用する方法  

タイムライン **で Allocation インストルメンテーション** を使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。  

## <a name="how-allocation-instrumentation-on-timeline-works"></a>タイムラインでの割り当てインストルメンテーションの動作  

**タイムライン上の割り当てインス**トルメンテーション**** は、ヒープ プロファイラーの詳細なスナップショット情報と、パフォーマンス パネルの増分更新と追跡を**組み合**わせたものになります。  同様に、オブジェクトのヒープ割り当てを追跡するには、記録を開始し、一連のアクションを実行し、分析のために記録を停止します。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

**タイムライン上の割り当て** インストルメンテーションは、記録 \(50 ms\ごとに頻繁に) と、記録の最後に 1 つの最終スナップショット全体でヒープ スナップショットを定期的に取得します。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="タイムラインでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **タイムラインでの割り当てインストルメンテーション**  
:::image-end:::  

> [!NOTE]
> the の後の番号は、記録セッション中に作成された複数のスナップショット全体で保持 `@` されるオブジェクト ID です。  永続オブジェクト ID を使用すると、ヒープ状態を正確に比較できます。  オブジェクトはガベージ コレクション中に移動されます。そのため、オブジェクトのアドレスを表示すると意味がありません。  

## <a name="enable-allocation-instrumentation-on-timeline"></a>タイムラインで割り当てインストルメンテーションを有効にする  

タイムラインでの割り当てインストルメンテーションの使用 **を開始するには、次のアクションを実行します**。  

1.  [DevTools を開きます][DevtoolsOpenIndex]。  
1.  [メモリ] **パネルを開** き、[タイムライン上の割り当て **インストルメンテーション] ラジオ ボタン** を選択します。  
1.  Start recording (録画開始)   
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="レコード ヒープ割り当てプロファイラー" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       レコード ヒープ割り当てプロファイラー  
    :::image-end:::  
    
## <a name="read-a-heap-allocation-timeline"></a>ヒープ割り当てタイムラインの読み取り  

ヒープ割り当てタイムラインは、オブジェクトが作成されている場所を示し、保持パスを識別します。  次の図では、上部のバーは、ヒープ内で新しいオブジェクトが見つかったかどうかを示しています。  

各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトがまだ最終的なヒープ スナップショットに存在するかどうかを示します。  青いバーは、タイムラインの最後にまだ存在するオブジェクトを示し、灰色のバーは、タイムライン中に割り当てられたが、その後ガベージ コレクションされたオブジェクトを示します。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="タイムライン スナップショットでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   **タイムライン スナップショットでの割り当てインストルメン** テーション  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple choose actions  -->  

上記のタイムラインのスライダーを使用して、その特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認できます。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="スナップショットを拡大する" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   スナップショットを拡大する  
:::image-end:::  

ヒープ内の特定のオブジェクトを選択すると、ヒープ スナップショットの下部に保持ツリーが表示されます。  オブジェクトへの保持パスを調べるには、オブジェクトが収集されていない理由を理解するのに十分な情報が提供され、不要な参照を削除するために必要なコードを変更する必要があります。  

## <a name="view-memory-allocation-by-function"></a>関数別にメモリ割り当てを表示する  

JavaScript 関数によってメモリ割り当てを表示できます。  詳細については、「関数別にメモリ [割り当てを調査する」に移動します][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "Microsoft Edge (クロム) DevTools ファイルを開|Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "関数別にメモリ割り当てを調査する - Fix Memory problems |Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルのダウンロード"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
