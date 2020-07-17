---
description: Microsoft Edge DevTools プロトコルバージョン0.1 でサポートされているドメインの参照の一覧です。
title: DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: de816e2b07838ba1b6151967ff7b8751789c60ea
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882948"
---
# DevTools プロトコルのドメイン-DevTools Protocol バージョン 0.1 (EdgeHTML)  

## [デバッガー](debugger.md)  

デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
## [Page](page.md)
検査されたページに関連するアクションとイベントは、ページドメインに属しています。
## [ランタイム](runtime.md)
ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
## [スキーマ](schema.md)
プロトコルスキーマに関する情報を提供します。