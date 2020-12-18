---
description: タイムラインで Allocation インストルメンテーションを使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。
title: タイムラインで Allocation Instrumentation を使用する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 946c2d8b45f316b491a604c16c37bb2467983222
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230916"
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

# タイムラインで Allocation インストルメンテーションを使用する方法  

タイムライン **で Allocation インストルメンテーションを** 使用して、適切にガベージ コレクションされていないオブジェクトを検索し、メモリを保持し続ける。  

## タイムラインでの Allocation のインストルメンテーションのしくみ  

**タイムラインでの割り当ての**インストルメンテーションは****、ヒープ プロファイラーの詳細なスナップショット情報と、パフォーマンス パネルの増分更新と追跡を**組み合**わせたものになります。  同様に、オブジェクトのヒープ割り当てを追跡するには、記録を開始し、一連の操作を実行し、分析のために記録を停止します。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

**タイムラインでの割** り当てインストルメンテーションは、記録 \(50 ミリ秒ごとに頻繁に) ヒープ スナップショットと、記録の最後に 1 つの最終的なスナップショットを定期的に取得します。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="タイムラインでの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **タイムラインでの割り当てインストルメンテーション**  
:::image-end:::  

> [!NOTE]
> その後の数値は、レコーディング セッション中に取得された複数のスナップショット全体にわたって保持される `@` オブジェクト ID です。  永続的なオブジェクト ID を使用すると、ヒープ状態を正確に比較できます。  オブジェクトはガベージ コレクション中に移動されます。そのため、オブジェクトのアドレスを表示する方法は意味がありません。  

## タイムラインで Allocation Instrumentation を有効にする  

タイムラインで Allocation インストルメンテーションの使用を開始するには、 **次の操作を実行します**。  

1.  [DevTools を開きます][DevtoolsOpenIndex]。  
1.  メモリ パネル **を開** き、タイムラインの [割り当て **インストルメンテーション] ラジオ ボタンを** 選択します。  
1.  Start recording (録画開始)   
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="レコード ヒープ割り当てプロファイラー" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       レコード ヒープ割り当てプロファイラー  
    :::image-end:::  
    
## ヒープ割り当てのタイムラインを読み取る  

ヒープ割り当てのタイムラインは、オブジェクトが作成されている場所を示し、保持パスを識別します。  次の図では、上部のバーは、ヒープ内で新しいオブジェクトが見つかったかどうかを示しています。  

各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトが最終的なヒープ スナップショット内にまだ存在するかどうかを示します。  青いバーは、タイムラインの最後にまだ存在しているオブジェクトを示し、灰色のバーは、タイムラインの間に割り当てられたが、その後ガベージ コレクションされたオブジェクトを示します。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="タイムライン スナップショットでの割り当てのインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   **タイムライン スナップショットでの割り当てのインストルメンテーション**  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

上のタイムラインのスライダーを使って、その特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認できます。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="スナップショットを拡大する" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   スナップショットを拡大する  
:::image-end:::  

ヒープ内の特定のオブジェクトをクリックすると、ヒープ スナップショットの下部に保持ツリーが表示されます。  オブジェクトへの保持パスを調べることで、オブジェクトが収集されていない理由を理解するのに十分な情報が得ら、不要な参照を削除するために必要なコードを変更する必要があります。  

## メモリ割り当てを関数別に表示する  

JavaScript 関数によってメモリ割り当てを表示できます。  詳細については、「関数別にメモリ割り [当てを調査する」に移動します][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "Microsoft Edge (Chromium) DevTools を開く |Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "関数別にメモリ割り当てを調査する - メモリの問題を修正する |Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルをダウンロードする"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここから [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
