---
description: Microsoft Edge DevTools プロトコルに更新する
title: Microsoft Edge DevTools プロトコル更新プログラム
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: f1936a83f948dd17cc76139b7fd67fc73cd692d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569634"
---
# Microsoft Edge (Chromium) DevTools プロトコル

Microsoft Edge の基になっている web プラットフォーム (Microsoft Edge) で Chromium に移動しても、 [Microsoft edge (EdgeHTML) DevTools プロトコル](./devtools-protocol/index.md)は今後更新を受け取りません。 Microsoft Edge (Chromium) DevTools プロトコルは、Chrome DevTools プロトコルの Api と一致します。 

このようなドメインとメソッドのドキュメントについては、 [Chrome DevTools プロトコルビューアー](https://chromedevtools.github.io/devtools-protocol/tot/)を参照してください。

> [!NOTE]
> `ms` [Microsoft Edge (EdgeHTML) devtools プロトコル](./devtools-protocol/index.md)でプレフィックスが付けられたメソッドは、Microsoft edge (Chromium) devtools プロトコルでサポートされなくなりました。

## DevTools プロトコルの使用

Microsoft Edge (Chromium) の DevTools サーバーにカスタムツールクライアントをアタッチする方法を次に示します。

1. Microsoft Edge (Chromium) のすべてのインスタンスを閉じていることを確認します。

2. リモートデバッグポートを使用して Microsoft Edge (Chromium) を起動します。

    ```
    msedge.exe --remote-debugging-port=9222
    ```

3. 必要に応じて、個別のユーザープロファイルを使って別の Edge のインスタンスを開始することもできます。

    ```
    msedge.exe --user-data-dir=<some directory>
    ```

4. 次に、HTTP エンドポイントを使用して、アタッチ可能な `list` ページターゲットの一覧を取得します。

    ```
    http://localhost:9222/json/list
    ```

5. 最後に、目的の `webSocketDebuggerUrl` ターゲットに接続してコマンドを実行するか、DevTools web ソケットサーバーからイベントメッセージを購読します。

## DevTools プロトコルの HTTP エンドポイント

Microsoft Edge (Chromium) DevTools プロトコルでは、次の HTTP エンドポイントがサポートされています。

## /json/version
ホストコンピューターのブラウザーと、サポートされている DevTools プロトコルのバージョンについて説明します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
{
   "Browser": "Edg/75.0.115.0",
   "Protocol-Version": "1.3",
   "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.115.0",
   "V8-Version": "7.5.98",
   "WebKit-Version": "537.36 (@68a98f73c7d0f766fb5a013ea7f8dbb41089bc1b)",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/browser/a9d0e8cf-476a-4a89-bba9-0fc27ce691cd"
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
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, … ]
```

## /json/close

ターゲットプロセスを終了します (たとえば、Microsoft Edge (Chromium) の場合は、[ページ] タブを閉じます)。

**パラメーター**

ターゲット ID 

**返されるオブジェクト**

```
String(“Target is closing”)
```

## Microsoft Edge 向けリモートツール (ベータ版)

Microsoft [Store](https://www.microsoft.com/store/apps/windows)から[Microsoft Edge (ベータ) 版のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールできるようになりました。 このアプリでは、開発用コンピューターから Windows 10 デバイスで実行されている Microsoft Edge (Chromium) をリモートでデバッグできます。

Windows 10 デバイスをセットアップして開発用コンピューターから接続する方法については、[このチュートリアル](./devtools-guide-chromium/remote-debugging/windows.md)をご覧ください。

[Microsoft edge (ベータ版) のリモートツール](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)では、デバッグ対象の Windows 10 デバイスで実行されている microsoft edge と通信するための、同じ microsoft Edge (Chromium) Devtools プロトコルを[devtools](./devtools-guide-chromium.md)として使用しています。 このアプリで `/msedge/` `pid` は、プロトコルを呼び出す前に、先頭にプロセス ID () が挿入されます。 次の HTTP エンドポイントがサポートされています。

### /msedge/json/list

`msedge.exe`デバッグ用の Windows 10 デバイス上のすべてのプロセス ( [pwas](./progressive-web-apps-chromium/index.md)およびすべての Microsoft Edge のすべてのタブを含む) の候補リストを提供します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
[{
   "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "browserProcessId": 7264
}, … ]
```

### /msedge/

[/Msedge/json/list](#msedgejsonlist)と同等の機能。 

### /msedge/[pid]/json/list

デバッグ用に指定されたものと一致する、Microsoft Edge インスタンスのページターゲットの候補リストを提供 `[pid]` します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
[{
    "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB"
}, … ]
```

### /msedge/[pid]/json/version

提供されている、およびサポートされている `[pid]` DevTools プロトコルのバージョンと一致する Microsoft Edge インスタンスに関する情報を提供します。

**パラメーター**

*なし*

**返されるオブジェクト**

```json
{
    "Browser": "Edg/82.0.452.0",
    "Protocol-Version": "1.3",
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/82.0.4080.0 Safari/537.36 Edg/82.0.452.0",
    "V8-Version": "8.2.263",
    "WebKit-Version": "537.36 (@fe0232051787ca94ac8edfc0084c3488b7d9bdb2)",
    "webSocketDebuggerUrl": "172.17.75.195:80/msedge/7264/devtools/browser/7a67c8c4-138b-48e3-bfe0-cb7af34d559a"
}
```

### /msedge/[pid]/json/protocol/

指定されたものと一致する Microsoft Edge インスタンスの JSON としてシリアル化されたプロトコル API サーフェス全体を提供し `[pid]` ます。

**パラメーター**

*なし*

**返されるオブジェクト**

指定されたものと一致する Microsoft Edge インスタンスが使用しているプロトコルのバージョンで利用可能な API サーフェスを表す JSON オブジェクト `[pid]` 。
