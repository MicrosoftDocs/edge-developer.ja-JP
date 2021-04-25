---
description: このセクションでは、メモリ分析で使用される一般的な用語について説明し、さまざまな言語のさまざまなメモリ プロファイリング ツールに適用できます。
title: メモリの関連用語
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c9659255e2bf0082cd1be3e6615c9d54c293b967
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519311"
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

# <a name="memory-terminology"></a>メモリの関連用語  

この記事では、メモリ分析で使用される一般的な用語について説明し、さまざまな言語のさまざまなメモリ プロファイリング ツールに適用できます。  

ここで説明する用語と用語は、メモリ パネルを [参照します][DevtoolsMemoryProblemsHeapSnapshots]。  アプリケーション、.NET、または他のJavaプロファイラーを使用した場合、この記事は更新プログラムになる可能性があります。  

## <a name="object-sizes"></a>オブジェクトのサイズ  

メモリは、プリミティブ型 \(数値や文字列\など) とオブジェクト \(連想配列\) を持つグラフと考えてください。  次の図のような多くの相互に接続されたポイントを含むグラフとして表示される場合があります。  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="メモリの視覚的表現" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   メモリの視覚的表現  
:::image-end:::  

オブジェクトは、次の 2 つの方法でメモリを保持できます。  

*   オブジェクトによって直接指定します。  
*   暗黙的に、他のオブジェクトへの参照を保持し、ガベージ コレクターによってそれらのオブジェクトが自動的に破棄されるのを防ぐ。  

DevTools [][DevtoolsMemoryProblemsHeapSnapshots] \(Memory **\で**見つかったメモリの問題を調査するツール) のメモリ パネルを操作すると、いくつかの異なる列の情報を見ている場合があります。  目立つのは、**シャロー サイズと****保持サイズですが**、これらは何を表していますか?  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅いサイズと保持サイズ" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   浅いサイズと保持サイズ  
:::image-end:::  

### <a name="shallow-size"></a>浅いサイズ  

これは、オブジェクトによって保持されるメモリのサイズです。  

一般的な JavaScript オブジェクトには、説明用と即時値の格納用に予約されたメモリがあります。  通常、配列と文字列だけが大きな浅いサイズを持つ可能性があります。  ただし、文字列と外部配列は、多くの場合、メイン ストレージをレンダラー メモリに格納し、JavaScript ヒープ上の小さなラッパー オブジェクトのみを公開します。  

レンダラー メモリは、検査されたページがレンダリングされるプロセスのすべてのメモリです。ページによって開始された専用ワーカーのネイティブ メモリ + JS ヒープ メモリ + JS ヒープ メモリ。  それにもかかわらず、小さなオブジェクトでも、自動ガベージ コレクション プロセスによって他のオブジェクトが破棄されるのを防ぐことによって、大量のメモリを間接的に保持できます。  

### <a name="retained-size"></a>保持サイズ  

これは、ガベージ コレクターのルートから到達不能にされた依存オブジェクトと共にオブジェクトが削除された後に解放されるメモリ **のサイズです**。  

**ガベージ コレクターのルート**は、**** ネイティブ コードから V8 以外の JavaScript オブジェクトへの参照を行う際に \(local または global\) で作成されるハンドルで構成されます。  このようなハンドルはすべて **、GC**ルート の [スコープの処理] および [GC ルート] グローバル ハンドルのヒープ スナップショット  >  ******内**  >  **で見つかる場合があります**。  ブラウザーの実装の詳細を詳しく説明せずに、このドキュメントのハンドルを記述すると、わかりにくい場合があります。  ガベージ コレクターのルートとハンドルはどちらも、心配する必要はありません。  

ガベージ コレクターの内部ルートは多数あるが、そのほとんどはユーザーにとって興味深くない。  アプリケーションの観点から、次の種類のルートがあります。  

*   Window グローバル オブジェクト \(各 iframe\内)。  ヒープ スナップショットでは、フィールドはウィンドウからの最短保持パス上のプロパティ参照の数 `distance` を示します。  
*   ドキュメント DOM ツリーは、ドキュメントを通過して到達可能なすべてのネイティブ DOM ノードで構成されます。  すべてのノードに JavaScript ラッパーが含まれますが、ノードにラッパーがある場合は、ドキュメントが有効な間、ノードは有効です。  
*   場合によっては、ソース ツールとコンソールのデバッグ**** コンテキスト (コンソール評価**** 後など) でオブジェクトが保持される場合があります。  ソース ツールのデバッガーで、クリアされた **コンソール** ツールとアクティブなブレークポイントを使用してヒープ スナップショット **を作成** します。

>[!TIP]
> メモリ ツールでヒープ スナップショットを取得する[前][DevtoolsMemoryProblemsHeapSnapshots]に****、コンソール ツールをクリアし、[ソース] ツールでブレークポイント**を非アクティブ**化します。  コンソール ツールを **クリアするには** 、メソッドを実行 `clear()` します。  

メモリ グラフはルートから始まり、ブラウザーのオブジェクト、またはモジュールのオブジェクトNode.js `window` `Global` されます。  ルート オブジェクトのガベージ コレクション方法は制御されません。  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="ルート オブジェクトのガベージ コレクション方法を制御できない。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   ルート オブジェクトのガベージ コレクション方法を制御できない。  
:::image-end:::  

ルートから到達できないものは、ガベージ コレクションを取得します。  

> [!NOTE]
> [浅 [いサイズ] 列と](#shallow-size) [[保持サイズ] 列の両方](#retained-size) が、データをバイト単位で表します。  

## <a name="objects-retaining-tree"></a>オブジェクト保持ツリー  

ヒープは、相互接続されたオブジェクトのネットワークです。  数学的な世界では、この構造はグラフまたは **メモリ グラフ** と呼ばれる。  グラフは、**エッジによって接続**されたノードから構成**** され、どちらもラベルが与えられる。  

*   **ノード**\(**またはオブジェクト**\) は、ビルドに使用**** されたコンストラクター関数の名前を使用してラベル付けされます。  
*   **エッジ** には、プロパティの名前を使用してラベルが付 **きます**。  

ヒープ [プロファイラーを使用してプロファイルを記録する方法について学習します][DevtoolsMemoryProblemsHeapSnapshots]。  次の図では、メモリ ツールのヒープ スナップショット記録の中で特に[][DevtoolsMemoryProblemsHeapSnapshots]注意点として、ガベージ コレクター ルートからの距離が含まれます。  同じ種類のオブジェクトのほとんどすべてが同じ距離で、少数のオブジェクトが大きな距離にある場合は、調査する価値があります。  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="ルートからの距離" lightbox="../media/memory-problems-root.msft.png":::
   ルートからの距離  
:::image-end:::  

## <a name="dominators"></a>ドミネーター  

ドミネーター オブジェクトは、各オブジェクトに 1 つのドミネーターを持つため、ツリー構造で構成されます。  オブジェクトのドミネーターは、そのオブジェクトが支配するオブジェクトへの直接参照を欠いている可能性があります。つまり、ドミネーターのツリーはグラフのスパニング ツリーではありません。  

次の図では、次のステートメントは true です。  

*   ノード 1 がノード 2 を支配する  
*   ノード 2 がノード 3、4、6 を支配する  
*   ノード 3 がノード 5 を支配する  
*   ノード 5 がノード 8 を支配する  
*   ノード 6 がノード 7 を支配する  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="ドミネーター ツリー構造" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   ドミネーター ツリー構造  
:::image-end:::  

次の図では、node はのドミネーターですが、ガベージ コレクターから `#3` `#10` `#7` `#10` .  したがって、ルートからオブジェクト A への単純なパスに B が存在する場合、オブジェクト B はオブジェクト A のドミネーターになります。  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="アニメーションのドミネーター図" lightbox="../media/memory-problems-dominators.msft.gif":::
   アニメーションのドミネーター図  
:::image-end:::  

## <a name="v8-specifics"></a>V8 の詳細  

メモリをプロファイリングする場合、ヒープ スナップショットが特定の方法で見える理由を理解すると便利です。  このセクションでは **、V8 JavaScript** 仮想マシン \(V8 VM または VM\) に特に対応するメモリ関連のトピックについて説明します。  

### <a name="javascript-object-representation"></a>JavaScript オブジェクト表現  

プリミティブ型は次の 3 種類です。  

*   数値 \(たとえば `3.14159...` \)  
*   Booleans \( `true` `false` または \)  
*   文字列 \(たとえば `"Werner Heisenberg"` \)  

プリミティブは他の値を参照できないので、常にリーフノードまたは終了ノードです。  

**数値** は次のように格納できます。  

*   小さい整数 \(**SMI**s\) と呼ばれる即時の 31 ビット整数値、または****  
*   ヒープ番号 と呼ばれるヒープ **オブジェクト**。 ヒープ番号は、SMI フォームに収まらない値 (**倍**数など) を格納したり、値をボックス化する必要がある**** 場合 (プロパティの設定など) に使用されます。  

**文字列** は、次のいずれかの場所に格納できます。  

*   **VM ヒープ**、または
*   レンダラー のメモリ **に外部的に**.  ラッパー **オブジェクトが** 作成され、外部ストレージにアクセスするために使用されます。たとえば、スクリプト ソースや Web から受信した他のコンテンツは VM ヒープにコピーされるのではなく、格納されます。

新しい JavaScript オブジェクトのメモリは、専用の JavaScript ヒープ \(または VM ヒープ **\) から割り当**てられます。  これらのオブジェクトは V8 のガベージ コレクターによって管理されるため、少なくとも 1 つの強い参照がある限り、生き続けます。  

JavaScript ヒープ内に含めなかったものはネイティブ オブジェクトと**呼ばれる。**  ヒープ オブジェクトとは対照的に、ネイティブ オブジェクトは、V8 ガベージ コレクターの有効期間を通じて管理されるのではなく、JavaScript ラッパー オブジェクトを使用して JavaScript からしかアクセスできない場合があります。  

**Cons string** は、格納された文字列と結合された文字列のペアで構成されるオブジェクトであり、連結の結果です。  cons 文字列の内容の **結合は** 、必要に応じてのみ行われます。  たとえば、結合された文字列の部分文字列を作成する必要がある場合です。

たとえば、連結して、連結の結果を表 `a` `b` す文字列 `(a, b)` を取得します。  後でその結果と `d` 連結すると、別の cons 文字列 : **が取得されます** `((a, b, d)` 。  

**配列** は数値キーを持つオブジェクトです。 **配列** は、大量のデータを格納するために V8 VM で広範囲に使用されます。 辞書のようなキーと値のペアのセットは、配列によってバックアップ **されます**。  

一般的な JavaScript オブジェクトは、次の 2 つの配列の種類の 1 つとして **のみ格納** されます。  

*   名前付きプロパティ、および  
*   数値要素  

プロパティの数が少ない場合、プロパティは内部的に JavaScript オブジェクトに格納されます。  

**Map** は、オブジェクトの種類とレイアウトの両方を記述するオブジェクトです。 たとえば、マップは、高速なプロパティ アクセスのために暗黙的なオブジェクト階層を [記述するために使用されます][V8FastProperties]。  

### <a name="object-groups"></a>オブジェクト グループ  

各 **ネイティブ オブジェクト グループ** は、相互参照を保持するオブジェクトで作成されます。  たとえば、すべてのノードが相対親へのリンクを持ち、次の子と次の兄弟へのリンクを持つ DOM サブツリーが接続されたグラフを形成するとします。  

> [!NOTE]
> ネイティブ オブジェクトは JavaScript ヒープでは表されません。  表現の欠如は、ネイティブ オブジェクトのサイズが 0 である理由です。 代わりに、ラッパー オブジェクトが作成されます。  

各ラッパー オブジェクトは、対応するネイティブ オブジェクトへの参照を保持し、コマンドをリダイレクトします。  次に、オブジェクト グループはラッパー オブジェクトを保持します。  ただし、ガベージ コレクターはラッパーが参照されなくなったオブジェクト グループを解放するのに十分なスマートな機能を持つので、コレクションできないサイクルは作成されません。  ただし、1 つのラッパーを解放することを忘れた場合は、グループ全体と関連付けられたラッパーが保持されます。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "ヒープ スナップショットを記録する|Microsoft Docs"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 の Fast プロパティ|V8"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) つかり [、Meggin Kearney][MegginKearney] \(Technical Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
