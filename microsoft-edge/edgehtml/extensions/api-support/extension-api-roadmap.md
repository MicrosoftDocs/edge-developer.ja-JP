---
description: Microsoft Edge 拡張機能 API の完成に向けた現在の進捗状況について説明します。
title: 拡張機能 API ロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, api, 拡張機能, javascript, 開発者
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d3552fede729a37ff83ac4b19cfadf89d6917a75
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235048"
---
# Microsoft Edge 拡張機能 API ロードマップ  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

拡張 API では、Web API に加えて、拡張機能を使用してブラウザー ホストとのより深い統合を実現できます。 この API を使用すると、開発者はタブやウィンドウの操作など、Microsoft Edge のブラウザー機能にアクセスできます。 次の表では、Microsoft Edge の一般にリリースされた Windows 10 ビルドでサポートされている API と開発中の API について詳しく説明します。


|     クラス     |                                                              説明                                                              |                Status - ビルド番号                 |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
|   ブックマーク   |                                          ブックマークの作成、整理、および操作に使用します。                                          | サポート — Microsoft Edge (40) / Windows 10 (15063) |
| browserAction |                                 拡張機能で Microsoft Edge 内に永続的なボタンを追加できます。                                  | サポート — Microsoft Edge (38) / Windows 10 (14393) |
| コマンド      |                                                      キーボード ショートカットを定義します。                                                      | 検討中
| contextMenus  |                           Web ページの指定されたコンテキストで、特定の URL にコンテキスト メニュー項目を追加します。                            | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|    cookie    |                                 Cookie のクエリと変更、および変更時の通知に使用されます。                                 | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|   downloads   |                           ダウンロードの開始、監視、操作、および検索をプログラムで行う場合に使用します。                           |                 検討中                  |
|   extension   |                                      任意の拡張機能ページで使用できるユーティリティが含まれている。                                       | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|    履歴    |                                         ブラウザーのアクセスされたページのレコードを操作します。                                         |                 検討中                  |
|     i18n      |                                         拡張機能全体で国際化を実装します。                                          | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|   ID    |                                       OAuth2 認証コードまたはアクセス トークンを取得するために使用されます。                                       |                 検討中                  |
|     idle      |                                       コンピューターのアイドル状態が変更された場合の検出に使用されます。                                        | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|  management   |                                              インストールされているアドオンに関する情報を取得します。                                                |                 検討中                  |
| 通知 |                      テンプレートを使用して通知を作成し、ユーザーのシステム トレイに表示できます。                      | サポートされている - Microsoft Edge (42) / Windows 10 (17134) |
|  pageAction   |                                      拡張機能でアドレス バー内にボタンを追加できます。                                       | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|  permissions  |                   拡張機能へのアクセスを許可するオプションのアクセス許可をユーザーが選択できます。                   |                 検討中                  |
|    runtime    | バックグラウンド ページを取得し、マニフェストに関する詳細を返し、拡張機能のライフサイクル内のイベントをリッスンして応答します。 | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|    ストレージ    |                                      拡張機能で、データの読み取り/書き込み、およびデータの同期に使用されます。                                       | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|     tabs      |                ブラウザーでタブを作成、変更、および並び替えすることで、Microsoft Edge のタブ システムを操作します。                | サポート — Microsoft Edge (38) / Windows 10 (14393) |
| webNavigation |                           移動中のナビゲーション要求の状態に関する通知を受信するために使用されます。                            | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|  webRequest   |        webRequest API を使用して、トラフィックの監視と分析、およびインフライトでの要求の取得、ブロック、または変更を行います。        | サポート — Microsoft Edge (38) / Windows 10 (14393) |
|    windows    |                              ブラウザーを操作するには、ウィンドウの作成、変更、および並び変更を行います。                              | サポート — Microsoft Edge (38) / Windows 10 (14393) |
