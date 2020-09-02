---
title: メモリの用語
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cb258135b7b3c931116d84b1e9b7a548a2b58a6d
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986258"
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

# メモリの用語  

このセクションでは、メモリ分析で使われる一般的な用語について説明します。また、さまざまな言語向けのさまざまなメモリプロファイリングツールにも適用されます。  

ここで説明する用語と意見は、「 [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]」を参照してください。  Java、.NET、または他のメモリプロファイラーのいずれかを使用したことがある場合は、これはリフレッシャーである可能性があります。  

## オブジェクトサイズ  

メモリは、プリミティブ型 \ (数値と文字列 \) とオブジェクト \ (連想配列) でのグラフと考えることができます。  視覚的には、次のように相互に接続された複数の点でグラフとして表示されることがあります。  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="メモリの視覚的表現" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   メモリの視覚的表現  
:::image-end:::  

オブジェクトには次の2つの方法でメモリを保持できます。  

*   オブジェクトを直接選びます。  
*   他**のオブジェクト** への参照を保持することによって暗黙的に、ガベージコレクターによってそれらのオブジェクトが自動的に破棄されることを防ぐことができます。  

DevTools で [メモリ][DevtoolsMemoryProblemsHeapSnapshots] パネルを操作しているときに ( **メモリ**にあるメモリの問題を調査するためのツール)、いくつかの情報の列が表示されることがあります。  目立たない2つの **サイズは浅いサイズ** で、保持されている **サイズ**ですが、これらは何を表しますか?  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅いサイズと保持サイズ" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   浅いサイズと保持サイズ  
:::image-end:::  

### 浅いサイズ  

これは、オブジェクトによって保持されているメモリのサイズです。  

一般的な JavaScript オブジェクトには、説明用に予約されたメモリ、および即時値を格納するためのメモリがあります。  通常、非常に浅いサイズを持つことができるのは、配列と文字列のみです。  ただし、文字列と外部配列には、多くの場合、レンダラーメモリ内にメインストレージがあり、JavaScript ヒープの小さなラッパーオブジェクトのみが公開されます。  

レンダラーメモリは、検査されたページがレンダリングされるプロセスのすべてのメモリです。このページで開始されるすべての専用ワーカーの、ネイティブメモリ + JS ヒープメモリ。  ただし、小さいオブジェクトは、他のオブジェクトが自動ガベージコレクションプロセスによって破棄されないようにすることで、大量のメモリを保持することができます。  

### 保持サイズ  

これは、オブジェクトが削除された後に、 **ガベージコレクタールート** \ (GC ルート) から到達不能になった従属オブジェクトと共に、解放されるメモリのサイズです。  

**ガベージコレクターのルート** \ (GC ルート \) は、ネイティブコードから V8 の外部の JavaScript オブジェクトへの参照を作成するときに、(ローカルまたはグローバル \ のどちらかに) 作成された **ハンドル** で構成されます。  このようなすべてのハンドルは、 **gc ルート**の  >  **スコープ**と**gc ルート**の  >  **グローバルハンドル**で、ヒープスナップショット内に存在する可能性があります。  このドキュメントでは、ブラウザーの実装の詳細について詳しく説明していませんが、混乱を招く可能性があります。  ガベージコレクター (GC) のルートとハンドルはどちらも、気にする必要はありません。  

多くの内部 GC ルートがあり、そのほとんどがユーザーにとって興味を持ちません。  アプリケーションの観点から見ると、次の種類のルートがあります。  

*   Window グローバルオブジェクト \ (各 iframe 内)  ヒープスナップショットには距離フィールドがあります。これは、ウィンドウから最短の保持パスにあるプロパティ参照の数です。  
*   ドキュメントを走査して到達可能なすべてのネイティブ DOM ノードで構成されるドキュメント DOM ツリー。  すべてのノードに JS ラッパーが含まれているわけではありませんが、ノードにラッパーがある場合は、ドキュメントが生きている間は生きています。  
*   場合によっては、 **ソース** パネルと **本体** (本体の評価の後など) で、デバッガーコンテキストによってオブジェクトが保持されることがあります。  クリアされた **コンソール** パネルを使ってヒープスナップショットを作成します。 [ **ソース** ] パネルでは、デバッガー内にアクティブなブレークポイントはありません。

>[!TIP]
> **Console** `clear()` [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots]でヒープスナップショットを取得する前に、[**ソース**] パネルでブレークポイントを実行して非アクティブ化して、コンソールパネルをクリアします。

メモリグラフは、 `window` ブラウザーのオブジェクトまたは Node.js モジュールのオブジェクトであるルートから始まり `Global` ます。  このルートオブジェクトのガベージコレクション (GCd) を制御することはできません。  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="ルートオブジェクトのガベージコレクションの方法を制御することはできません。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   ルートオブジェクトのガベージコレクションの方法を制御することはできません。  
:::image-end:::  

ルートから到達できないものはすべて、ガーベジコレクトされた \ (GCd \) を取得します。  

> [!NOTE]
> [ [緩斜面サイズ](#shallow-size) ] 列と [ [保持サイズ](#retained-size) ] 列は両方ともバイト単位のデータを表します。  

## ツリーを保持するオブジェクト  

ヒープは、相互接続されたオブジェクトのネットワークです。  数学の世界では、この構造は **グラフ** またはメモリグラフと呼ばれています。  グラフは、**エッジ**によって接続された**ノード**から構成され、両方のラベルにラベルが割り当てられます。  

*   **ノード** \ (または **オブジェクト**\) は、ビルドに使用された **コンストラクター** 関数の名前を使ってラベル付けされます。  
*   **エッジ** は、 **プロパティ**の名前を使用してラベル付けされます。  

[ヒーププロファイラーを使ってプロファイルを記録する方法について][DevtoolsMemoryProblemsHeapSnapshots]説明します。  次の図では、 [メモリパネル][DevtoolsMemoryProblemsHeapSnapshots] でのヒープスナップショットの記録には、距離 (ガベージコレクター \ (GC \) ルートからの距離) が含まれていることがあります。  同じ型のほぼすべてのオブジェクトが同じ距離にあり、数が大きい場合は、調査の対象となります。  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="ルートからの距離" lightbox="../media/memory-problems-root.msft.png":::
   ルートからの距離  
:::image-end:::  

## Dominators  

Dominator オブジェクトは、各オブジェクトに Dominator が1つしかないため、ツリー構造で構成されています。  オブジェクトの dominator には、優位なオブジェクトへの直接参照がない場合があります。つまり、dominator のツリーはグラフのスパニングツリーではありません。  

次の図では、次のステートメントが true になっています。  

*   ノード1の各ノード2  
*   ノード2の各ノード3、4、6  
*   ノード3の各ノード5  
*   ノード5のつのノード8  
*   ノード6の各バージョンノード7  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="Dominator ツリー構造" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   Dominator ツリー構造  
:::image-end:::  

次の図では、node `#3` が dominator のようになって `#10` いますが、 `#7` ガベージコレクター \ (GC) からのすべての単純なパスにも存在し `#10` ます。  したがって、オブジェクト B は、ルートからオブジェクト A へのすべての単純パスに B が存在する場合、オブジェクト A の dominator になります。  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="アニメーション化された dominator の図" lightbox="../media/memory-problems-dominators.msft.gif":::
   アニメーション化された dominator の図  
:::image-end:::  

## V8 の詳細  

メモリのプロファイリングを行うときは、ヒープスナップショットが特定の方法で表示される理由を理解しておくと便利です。  このセクションでは、 **V8 JavaScript 仮想マシン** \ (V8 VM または vm \) に特に対応する、いくつかのメモリ関連トピックについて説明します。  

### JavaScript オブジェクトの表現  

プリミティブ型には次の3種類があります。  

*   番号 ( `3.14159...` \ など)  
*   ブール型 ( `true` \ `false` )  
*   文字列 \ (\ など `"Werner Heisenberg"` )  

プリミティブは、他の値を参照することはできません。また、常に leafs ノードまたは終了ノードを参照します。  

**数値** は、次のいずれかの方法で保存できます。  

*   31ビットの **小さな** 整数値 (**SMI**s \)、または  
*   ヒープ **値**と呼ばれるヒープオブジェクト。 ヒープ値は、 **2 倍**などの SMI フォームに収まらない値や、プロパティの設定など、値の **ボックス**化が必要な場合に使用されます。  

**文字列** は、次のいずれかの方法で保存できます。  

*   **VM ヒープ**、または
*   **レンダラーのメモリ**内の外部。  **ラッパーオブジェクト**が作成され、外部ストレージへのアクセスに使用されます。たとえば、スクリプトソースや Web から受け取ったその他のコンテンツは、VM ヒープにコピーされるのではなく格納されます。

新しい JavaScript オブジェクト用のメモリは、専用の JavaScript ヒープ \ (または **VM ヒープ**\) から割り当てられます。  これらのオブジェクトは、V8 のガベージコレクターによって管理されるため、少なくとも1つの強い参照が存在する限り、生きたままです。  

JavaScript ヒープに含まれないものは、 **ネイティブオブジェクト**と呼ばれます。  ヒープオブジェクトとは対照的に、ネイティブオブジェクトは、有効期間を通じて V8 ガーベジコレクターによって管理されるものではなく、javascript のラッパーオブジェクトを使って JavaScript からのみアクセスできます。  

**短所文字列** は、格納された文字列のペアで構成され、その後結合されたオブジェクトです。  **短所の文字列**の内容の結合は、必要な場合にのみ発生します。 例としては、結合された文字列の部分文字列を構築する必要があります。

たとえば、とを連結する `a` と、 `b` 連結の結果を表す文字列を取得でき `(a, b)` ます。  後でその結果と連結した場合は `d` 、次のような別の **文字列**が返さ `((a, b, d)` れます。  

**配列** は数値キーを含むオブジェクトです。 大量のデータを格納するために、V8 VM では**配列**が広く使われています。 ディクショナリなどのキーと値のペアのセットは、 **配列**によってバックアップされます。  

一般的な JavaScript オブジェクトは、次の2つの **配列** 型のうちの1つに限定されます。  

*   "名前付きプロパティ" と "  
*   数値要素  

プロパティが少数の場合は、JavaScript オブジェクト内にプロパティが内部的に格納されます。  

**Map** は、オブジェクトの種類とレイアウトの両方を説明するオブジェクトです。 たとえば、 [fast プロパティにアクセス][V8FastProperties]するための暗黙的なオブジェクト階層の記述には、maps を使います。  

### オブジェクトグループ  

各 **native objects** グループは、相互参照を保持するオブジェクトで構成されています。  たとえば、すべてのノードに関連する親へのリンクと次の子とその次の兄弟へのリンクが含まれている DOM サブツリーで、接続されたグラフを形成することを検討してください。  

> [!NOTE]
> ネイティブオブジェクトは JavaScript ヒープには表示されません。  ネイティブオブジェクトのサイズが0でない場合は、表示されません。 代わりに、ラッパーオブジェクトが作成されます。  

各ラッパーオブジェクトは、対応するネイティブオブジェクトへの参照を保持します。これには、コマンドをリダイレクトするための参照が含まれています。  さらに、オブジェクトグループはラッパーオブジェクトを保持します。  ただし、ガベージコレクター \ (GC \) は、ラッパーが参照されなくなったオブジェクトグループを解放するのに十分なものであるため、この方法では、回収不能なサイクルは作成されません。 ただし、1つのラッパーの解放を忘れると、グループ全体と関連付けられたラッパーが保持されます。  

## Microsoft Edge DevTools チームと連絡を取り合う  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "ヒープスナップショットの記録方法 |Microsoft ドキュメント"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 の Fast プロパティ |V8"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) にあり、 [Meggin Kearney][MegginKearney] \ (テクニカルライター \) によって作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
