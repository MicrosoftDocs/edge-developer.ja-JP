---
description: Microsoft Edge DevTools プロトコル バージョン 0.2 でサポートされているドメインの参照リスト。
title: DevTools プロトコル ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 03688ff2a1757205cc1c83d23a13d205e38011c7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234788"
---
# DevTools プロトコル ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)  

## [CSS](css.md)  

このドメインは、CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、およびスタイル) は、関連するオブジェクトに対する後続の `id` 操作で使用されます。 各オブジェクトの種類は、特定の構造を持ち、異なる種類の `id` オブジェクト間で互換性を持つものではありません。 CSS オブジェクトは、呼び出し (DOM ノード ID を受 `get*ForNode()` け入れる) を使用して読み込まれます。 クライアントは、イベントを介してスタイルシートを追跡し、メソッドを使用して必要なスタイルシートの `styleSheetAdded` / `styleSheetRemoved` コンテンツを読み `getStyleSheet[Text]()` 込むすることもできます。
## [DOM](dom.md)
このドメインは、DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、ミラー オブジェクトで表されます `id` 。 これは `id` 、Node に関する追加情報の取得、JavaScript オブジェクト ラッパーへの解決などに使用できます。クライアントが DOM イベントを受け取るのは、クライアントに既知のノードについてのみ重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを 2 回送信する必要はありません。 クライアントに送信されたノードに関する情報を収集する必要があります。<p>所有者要素 `iframe` は、対応するドキュメント要素を子ノードとして返します。</p>
## [DOMDebugger](domdebugger.md)
DOM デバッグでは、特定の DOM 操作とイベントにブレークポイントを設定できます。 JavaScript の実行は、通常のブレークポイント セットがある場合と同様に、これらの操作で停止します。
## [デバッガー](debugger.md)
デバッガー ドメインは、JavaScript デバッグ機能を公開します。 ブレークポイントの設定と削除、実行のステップ実行、スタック トレースの探索などを行えます。
## [オーバーレイ](overlay.md)
オーバーレイ ドメインは視覚的な視覚効果とノード選択操作を公開します
## [Page](page.md)
検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
## [ランタイム](runtime.md)
ランタイム ドメインは、リモート評価オブジェクトとミラー オブジェクトを使用して JavaScript ランタイムを公開します。 評価結果は、オブジェクトの種類、文字列表現、および一意の識別子を公開するミラー オブジェクトとして返され、さらにオブジェクト参照に使用できます。 元のオブジェクトは、明示的に解放されていない限り、メモリ内に保持されます。
## [スキーマ](schema.md)
プロトコル スキーマに関する情報を提供します。
