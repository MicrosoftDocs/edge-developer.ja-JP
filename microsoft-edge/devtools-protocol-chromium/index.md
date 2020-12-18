---
description: Microsoft Edge DevTools プロトコルの更新
title: Microsoft Edge DevTools プロトコル更新プログラム
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 15b13e2b93d1dbd013a82ea52b643071fa5b6f7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234832"
---
# Microsoft Edge (Chromium) DevTools プロトコルの概要  

Microsoft Edge の基礎となる Web プラットフォームが Chromium に移行すると [、Microsoft Edge (EdgeHTML) DevTools プロトコル](../edgehtml/devtools-protocol/index.md) はそれ以上の更新プログラムを受信しなくる可能性があります。  Microsoft Edge \(Chromium\) DevTools プロトコルは、今後 Chrome DevTools プロトコルの API と一致します。  

これらのドメインとメソッドに関するドキュメントは [、Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot/)プロトコル ビューアーを参照して確認できます。  

> [!NOTE]
> `ms` [Microsoft Edge (EdgeHTML) DevTools プロトコル](../edgehtml/devtools-protocol/index.md)でプレフィックスが付いたメソッドは、Microsoft Edge \(Chromium\) DevTools プロトコルではサポートされなくなりました。  

## DevTools プロトコルの使用  

Microsoft Edge \(Chromium\) の DevTools Server にカスタム ツール クライアントを接続する方法を次に示します。  

1.  Microsoft Edge \(Chromium\) のすべてのインスタンスが閉じているか確認します。  
1.  リモート デバッグ ポートを使用して Microsoft Edge \(Chromium\) を起動します。 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  必要に応じて、個別のユーザー プロファイルを使用して Edge の個別のインスタンスを開始できます。  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  次に、HTTP エンドポイント `list` を使用して、接続可能なページ ターゲットの一覧を取得します。  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  最後に、目的のターゲットの接続とコマンドの発行/DevTools Web ソケット サーバー経由でのイベント メッセージ `webSocketDebuggerUrl` のサブスクライブを行います。  

## DevTools プロトコル HTTP エンドポイント  

Microsoft Edge \(Chromium\) DevTools プロトコルは、次の HTTP エンドポイントをサポートしています。  

## /json/version  

ホスト コンピューターのブラウザーと、それがサポートする DevTools プロトコルのバージョンに関する情報を提供します。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

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

**なし**  

**Return オブジェクト**  

プロトコルの現在のバージョンで使用可能な API サーフェスを表す JSON オブジェクト。  

## /json/list  

デバッグ対象のページ ターゲットの候補リストを提供します。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, ...  ]
```  

## /json/close  

ターゲット プロセス \(たとえば、Microsoft Edge \(Chromium\) を閉じ、ページ タブ\) を閉じます。  

**パラメーター**  

ターゲット ID  

**Return オブジェクト**  

```
String(“Target is closing”)
```  

## Microsoft Edge のリモート ツール (ベータ版)  

これで[、Microsoft Store](https://www.microsoft.com/store/apps/windows)から Microsoft Edge 用リモート ツール[(ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)をインストールできます。  このアプリを使用すると、開発用コンピューターから Windows 10 デバイスで実行されている Microsoft Edge (Chromium) をリモートでデバッグできます。  

Windows 10 デバイスをセットアップし、開発用コンピューターからデバイスに接続する方法については [、「Windows 10](../devtools-guide-chromium/remote-debugging/windows.md)デバイスのリモート デバッグの開始」に移動します。  

Microsoft Edge 用リモート ツール [(ベータ版)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) は [、DevTools](../devtools-guide-chromium/index.md) と同じ Microsoft Edge (Chromium) DevTools プロトコルを使用して、デバッグする Windows 10 デバイスで実行されている Microsoft Edge と通信します。  このアプリでは、プロトコルの `/msedge/` 各呼び出しの前に先頭に追加され、プロセス ID ( ) `pid` が追加されます。  次の HTTP エンドポイントをサポートしています。  

### /msedge/json/list  

デバッグ用の Windows 10 デバイス上のすべてのプロセス \(PAS と Microsoft Edge のすべてのインスタンスのすべてのタブを含む) の候補リストを `msedge.exe` 提供します。 [](../progressive-web-apps-chromium/index.md)  

**パラメーター**  

**なし**  

**Return オブジェクト**  

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
}, ...  ]
```  

### /msedge/  

[/msedge/json/list と機能的に同等です](#msedgejsonlist)。  

### /msedge/[pid]/json/list  

提供されたデバッグに一致する Microsoft Edge インスタンスのページ ターゲットの候補リスト `[pid]` を提供します。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

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
}, ...  ]
```  

### /msedge/[pid]/json/version  

指定されたバージョンと一致する Microsoft Edge インスタンスと、それがサポートする DevTools プロトコルのバージョンに関する `[pid]` 情報を提供します。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

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

指定されたオブジェクトに一致する Microsoft Edge インスタンスの JSON としてシリアル化されたプロトコル API サーフェス全体を提供します `[pid]` 。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

指定されたバージョンと一致する Microsoft Edge インスタンスが使用しているプロトコルのバージョンで使用可能な API サーフェスを表す JSON `[pid]` オブジェクト。  
