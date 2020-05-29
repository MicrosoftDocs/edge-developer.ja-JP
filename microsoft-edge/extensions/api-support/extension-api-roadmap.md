---
description: Microsoft Edge 拡張機能 API の完了に向けて、現在の進行状況に関する情報を見つけます。
title: Extensions API のロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、api、拡張機能、javascript、開発者
ms.custom: seodec18
ms.openlocfilehash: ce40dd2d37b7ef446516a743286c5285ad3187a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569535"
---
# Microsoft Edge extension API のロードマップ  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

拡張 API を使用すると、web Api に加えて、ブラウザーホストとの緊密な統合を実現することができます。 この API により、開発者は、タブやウィンドウ操作などの Microsoft Edge のブラウザー機能にアクセスできます。 次の表では、Microsoft Edge の公開されている Windows 10 ビルドの開発でサポートされる Api について説明します。


|     クラス     |                                                              説明                                                              |                状態: ビルド番号                 |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
|   ブックマーク   |                                          ブックマークの作成、整理、操作に使用します。                                          | サポートされている: Microsoft Edge (40)/Windows 10 (15063) |
| browserAction |                                 Microsoft Edge で拡張機能を追加して、固定ボタンを追加できるようにします。                                  | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
| コマンド      |                                                      キーボードショートカットを定義します。                                                      | 考慮事項
| contextMenus  |                           特定の URL に、web ページの指定されたコンテキストでコンテキストメニュー項目を追加します。                            | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|    cookie    |                                 Cookie のクエリと変更、および変更時に通知するために使用されます。                                 | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|   downloads   |                           ダウンロードをプログラムで開始、監視、操作、検索するために使用されます。                           |                 考慮事項                  |
|   補助   |                                      任意の拡張ページで使用できるユーティリティが含まれています。                                       | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|    履歴    |                                         ブラウザーのアクセスページの記録とやり取りします。                                         |                 考慮事項                  |
|     プロパティー      |                                         拡張機能に対して国際化を実装します。                                          | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|   ID    |                                       OAuth2 認証コードまたはアクセストークンを取得するために使われます。                                       |                 考慮事項                  |
|     アイドル      |                                       コンピューターのアイドル状態が変更されたときに検出されます。                                        | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|  マネージメント   |                                              インストールされているアドオンに関する情報を取得します。                                                |                 考慮事項                  |
| 通知 |                      テンプレートを使用して、ユーザーのシステムトレイに表示される通知を作成できます。                      | サポートされている-Microsoft Edge (42)/Windows 10 (17134) |
|  Page アクション   |                                      アドレスバー内にボタンを追加するための拡張機能を有効にします。                                       | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|  権限  |                   ユーザーが、拡張機能にアクセス権を付与するオプションの権限を選択できるようにします。                   |                 考慮事項                  |
|    言語    | バックグラウンドページを取得し、マニフェストに関する詳細を返し、拡張機能のライフサイクルでイベントをリッスンして応答します。 | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|    ストレージ    |                                      データの読み取り/書き込み、データの同期を行うために拡張機能によって使用されます。                                       | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|     タブ      |                ブラウザーでタブを作成、変更、および再配置することにより、Microsoft Edge のタブシステムとやり取りします。                | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
| Web ナビゲーション |                           フライト中のナビゲーション要求の状態に関する通知を受信するために使用されます。                            | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|  webRequest   |        WebRequest API を使用してトラフィックを監視および分析し、フライト中の要求を傍受、ブロック、または変更します。        | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |
|    windows    |                              Windows を作成、変更、および再配置することで、ブラウザーとやり取りします。                              | サポートされている: Microsoft Edge (38)/Windows 10 (14393) |

