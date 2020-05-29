---
description: Microsoft Edge DevTools プロトコルバージョン0.1 でサポートされているドメインの参照の一覧です。
title: ドメイン-DevTools プロトコルバージョン0.1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: b3cf3411a8402b7407012eb789f8bf267b4997a8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569621"
---
# DevTools プロトコルのドメイン
## [ブレーク](debugger.md)
デバッガードメインは、JavaScript のデバッグ機能を公開します。 これにより、ブレークポイントの設定と削除、実行のステップ実行、スタックトレースの調査などを行うことができます。
## [Page](page.md)
検査されたページに関連するアクションとイベントは、ページドメインに属しています。
## [言語](runtime.md)
ランタイムドメインは、リモートの評価とミラーオブジェクトによって JavaScript ランタイムを公開します。 評価結果は、オブジェクトの型、文字列表現、およびさらにオブジェクト参照に使用できる一意の識別子を公開するミラーオブジェクトとして返されます。 元のオブジェクトは、明示的に解放されない限り、メモリ内に保持されます。
## [スキーマ](schema.md)
プロトコルスキーマに関する情報を提供します。