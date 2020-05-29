---
description: Microsoft Edge DevTools プロトコルバージョン0.2 では、次の HTTP エンドポイントがサポートされています。
title: Microsoft Edge DevTools プロトコルバージョン 0.2 HTTP エンドポイント
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: cc3d0156d92ab479168e0b588ae2b7c9faa7e58f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569590"
---
# DevTools プロトコルの HTTP エンドポイント

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン0.2 は、 [windows 10 年 2018 10 月の更新プログラム]()以降の[windows Insider Preview](https://insider.windows.com/en-us/getting-started/)ビルドでのみ動作します。

**Devtools プロトコル 0.2**では、次の HTTP エンドポイントがサポートされています。 ブラウザコンテンツ処理への接続に関する詳細については、「web sockets ベースの devtools プロトコル API 用の[ドメイン](domains/index.md)[ドキュメント」を](../index.md#using-the-protocol)参照してください。

## /json/version
ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
}
```

## /json/protocol

JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。

**パラメーター**

*なし*

**返されるオブジェクト**

プロトコルの現在のバージョンで利用できる API サーフェスを表す JSON オブジェクト。

## /json/list

デバッグ用のページターゲットの候補リストを提供します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## /json/close

ターゲットプロセスを終了します (例: Microsoft Edge では、[ページ] タブを閉じます)。

**パラメーター**

ターゲット ID 

**返されるオブジェクト**

```
String("Target is closing")
```
