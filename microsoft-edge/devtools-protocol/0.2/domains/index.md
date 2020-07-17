---
description: Microsoft Edge DevTools プロトコルバージョン0.2 でサポートされているドメインの参照の一覧です。
title: DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: ba56b31bb750eb9c575c6d13ef296aae6604e99f
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882752"
---
# DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.2 (EdgeHTML)  

## [CSS](css.md)  

このドメインは CSS の読み取り/書き込み操作を公開します。 すべての CSS オブジェクト (スタイルシート、ルール、スタイル) には、 `id` 関連オブジェクトの後続の操作で使用される関連付けがあります。 各オブジェクト型には特定の構造体があり、 `id` さまざまな種類のオブジェクト間で相互に交換することはできません。 CSS オブジェクトは、 `get*ForNode()` 呼び出し (DOM ノード id を受け取る) を使って読み込むことができます。 クライアントは、イベントによってスタイル変更 `styleSheetAdded` / `styleSheetRemoved` を追跡し、そのメソッドを使って必要なスタイルシートの内容を読み込むこともでき `getStyleSheet[Text]()` ます。
## [DOM](dom.md)
このドメインは DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、が含まれているミラーオブジェクトで表され `id` ます。 これを使って、 `id` ノードの追加情報を取得したり、JavaScript オブジェクトラッパーなどに解決したりすることができます。クライアントが認識しているノードでのみ DOM イベントを受信することが重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを2回送信することはありません。 クライアントに送信されたノードに関する情報は、クライアント側で収集する必要があります。<p>`iframe`Owner 要素は、子ノードとして対応するドキュメント要素を返します。</p>
## [DOMDebugger](domdebugger.md)
DOM デバッグでは、特定の DOM 操作およびイベントに対してブレークポイントを設定することができます。 通常のブレークポイントが設定されている場合と同様に、JavaScript の実行はこの操作によって停止されます。
## [デバッガー](debugger.md)
デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
## [オーバーレイ](overlay.md)
オーバーレイドメインは、視覚表示修飾要素とノード選択の相互作用を公開します。
## [Page](page.md)
検査されたページに関連するアクションとイベントは、ページドメインに属しています。
## [ランタイム](runtime.md)
ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
## [スキーマ](schema.md)
プロトコルスキーマに関する情報を提供します。