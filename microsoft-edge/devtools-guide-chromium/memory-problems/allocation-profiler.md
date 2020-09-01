---
title: タイムラインでの割り当てインストルメンテーションの使い方
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d0a7a66a9f061d1a5d98e57269ffbcc0a0afefa4
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985753"
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





# タイムラインでの割り当てインストルメンテーションの使い方  



**タイムライン上で割り当てインストルメンテーション**を使用して、適切なガベージコレクションが実行されていないオブジェクトを探し、引き続きメモリを保持します。  

## タイムラインの割り当てインストルメンテーションのしくみ  

**タイムライン上の割り当てインストルメンテーション** は、 **ヒーププロファイラー** の詳細なスナップショット情報を、 **パフォーマンス** パネルの段階的な更新と追跡と組み合わせたものです。  同様に、オブジェクトのヒープ割り当てのトラッキングでは、記録の開始、一連の操作の実行、分析のための記録の停止などを行います。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

**タイムラインの割り当てインストルメンテーション** は、記録中の (50 ミリ秒間のすべての頻度で) ヒープスナップショットと、記録の最後に1つの最終スナップショットを受け取ります。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="タイムライン上の割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **タイムライン上の割り当てインストルメンテーション**  
:::image-end:::  

> [!NOTE]
> の後の番号は、 `@` 記録セッション中に作成された複数のスナップショット間で保持されるオブジェクト ID です。  永続的なオブジェクト ID によって、ヒープの状態を正確に比較できます。  オブジェクトはガベージコレクション中に移動されるため、オブジェクトのアドレスを表示すると意味がありません。  

## タイムラインでの割り当てインストルメンテーションの有効化  

**タイムラインでの割り当てインストルメンテーションの**使用を開始するには、次の手順に従います。  

1.  [DevTools を開き][DevtoolsOpenIndex]ます。  
1.  [ **メモリ** ] パネルを開き、[ **タイムライン上の割り当てインストルメンテーション** ] を選択します。  
1.  Start recording (録画開始)   
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="ヒープ割り当てプロファイラーの記録" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       ヒープ割り当てプロファイラーの記録  
    :::image-end:::  
    
## ヒープ割り当てタイムラインの読み取り  

ヒープ割り当てのタイムラインには、オブジェクトが作成されている場所と保持パスが示されます。  次の図では、上部のバーは、新しいオブジェクトがヒープで見つかったことを示します。  

各バーの高さは、最近割り当てられたオブジェクトのサイズに対応し、バーの色は、それらのオブジェクトが最終的なヒープスナップショットでまだ存在するかどうかを示します。  青いバーは、タイムラインの最後にあるオブジェクトを示します。灰色のバーは、タイムラインで割り当てられたが、ガベージコレクションされているオブジェクトを示します。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="タイムラインスナップショットの割り当てインストルメンテーション" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   **タイムラインスナップショットの割り当てインストルメンテーション**  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

上のタイムラインのスライダーを使用して、特定のスナップショットを拡大し、その時点で最近割り当てられたオブジェクトを確認することができます。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="スナップショットの拡大" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   スナップショットの拡大  
:::image-end:::  

ヒープ内の特定のオブジェクトをクリックすると、ヒープスナップショットの下の部分に保持ツリーが表示されます。  オブジェクトへの保持パスを調べることで、オブジェクトが収集されなかった理由を理解するために十分な情報を得ることができます。また、不要な参照を削除するために必要なコードの変更を行う必要があります。  

## 関数によるメモリ割り当てを表示する   

JavaScript 関数によるメモリ割り当てを表示できます。  詳細については、「 [関数によるメモリ割り当てを調査][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction] する」を参照してください。  

<!--
## Feedback   


-->  

<!-- links -->  

[DevToolsOpenIndex]: ../open.md "Microsoft Edge (Chromium) DevTools を開く |Microsoft ドキュメント"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "関数によるメモリ割り当てを調べる-メモリの問題を解決する |Microsoft ドキュメント"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "Microsoft Edge チャネルをダウンロードする"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
