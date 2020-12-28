---
description: Microsoft Edge DevTools Protocol Version 0.2 は、次の HTTP エンドポイントをサポートしています。
title: Microsoft Edge DevTools プロトコル バージョン 0.2 HTTP エンドポイント (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a0e100cee6a73d688b9b74a9b38d1dd37722428f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234786"
---
# Microsoft Edge DevTools プロトコル バージョン 0.2 HTTP エンドポイント (EdgeHTML)  

> [!NOTE]
> Microsoft Edge DevTools プロトコルのバージョン 0.2 は [、Windows 10 October 2018 Update]() 以降の [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) ビルドでのみ動作します。

**DevTools Protocol 0.2** は、次の HTTP エンドポイントをサポートしています。 ブラウザー[コンテンツ プロセスへの接続](../index.md#using-the-protocol)の詳細についてはプロトコルの使用を参照[](domains/index.md)してください。また、完全な Web ソケット ベースの devtools プロトコル API については、「ドメイン」のドキュメントを参照してください。

## /json/version
ホスト コンピューターのブラウザーと、それがサポートする DevTools プロトコルのバージョンに関する情報を提供します。

**パラメーター**

*なし*

**Return オブジェクト**

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

**Return オブジェクト**

プロトコルの現在のバージョンで使用可能な API サーフェスを表す JSON オブジェクト。

## /json/list

デバッグ対象のページ ターゲットの候補リストを提供します。

**パラメーター**

*なし*

**Return オブジェクト**

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

ターゲット プロセスを終了します (Microsoft Edge でページ タブを閉じるなど)。

**パラメーター**

ターゲット ID 

**Return オブジェクト**

```
String("Target is closing")
```