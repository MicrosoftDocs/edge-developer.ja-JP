---
description: DevTools プロトコルMicrosoft Edge更新
title: Microsoft EdgeDevTools プロトコルの更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: de7d6c39c09ba321f21b34e6e461ec030f09f6ad
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480161"
---
# <a name="microsoft-edge-chromium-devtools-protocol-overview"></a>Microsoft Edge (Chromium) DevTools プロトコルの概要  

Microsoft Edge の基になる Web プラットフォームが Chromium に移行すると[、Microsoft Edge (EdgeHTML) DevTools プロトコル](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)はそれ以上の更新プログラムを受け取る必要があります。  Microsoft Edge \(Chromium\) DevTools プロトコルは、今後の Chrome DevTools プロトコルの API と一致します。  

これらのドメインとメソッドについては [、Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot)プロトコル ビューアーを参照してください。  

> [!NOTE]
> `ms` [Microsoft Edge (EdgeHTML) DevTools プロトコル](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)でプレフィックスが付いたメソッドは、Microsoft Edge \(Chromium\) DevTools プロトコルではサポートされなくなりました。  

## <a name="using-the-devtools-protocol"></a>DevTools プロトコルの使用  

\(Chromium\) の DevTools Server にカスタム ツール クライアントを接続するMicrosoft Edge次に示します。  

1.  \(Microsoft Edge\) のすべてのインスタンスがChromium閉じられます。  
1.  リモート デバッグ Microsoft Edge \(Chromium\) を起動します。 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  必要に応じて、個別のユーザー プロファイルを使用してエッジの別のインスタンスを開始できます。  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  次に、HTTP エンドポイント `list` を使用して、接続可能なページ ターゲットの一覧を取得します。  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  最後に、目的のターゲットに接続し、コマンドを発行/DevTools Web ソケット サーバーを介してイベント メッセージ `webSocketDebuggerUrl` をサブスクライブします。  

## <a name="devtools-protocol-http-endpoints"></a>DevTools プロトコル HTTP エンドポイント  

Microsoft Edge \(Chromium\) DevTools プロトコルは、次の HTTP エンドポイントをサポートします。  

## <a name="jsonversion"></a>/json/version  

ホスト コンピューターのブラウザーと、サポートする DevTools プロトコルのバージョンに関する情報を提供します。  

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

## <a name="jsonprotocol"></a>/json/protocol  

JSON としてシリアル化されたプロトコル API サーフェス全体を提供します。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

現在のバージョンのプロトコルで使用可能な API サーフェスを表す JSON オブジェクト。  

## <a name="jsonlist"></a>/json/list  

デバッグ用のページ ターゲットの候補リストを提供します。  

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

## <a name="jsonclose"></a>/json/close  

ターゲット プロセス \(たとえば、\(Microsoft Edge Chromium\) を閉じて、ページ タブ\を閉じます。  

**パラメーター**  

ターゲット ID  

**Return オブジェクト**  

```
String(“Target is closing”)
```  

## <a name="remote-tools-for-microsoft-edge-beta"></a>リモート ツール for Microsoft Edge (Beta)  

これで、リモート ツール[(Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) Microsoft Edgeからインストール[Microsoft Store。](https://www.microsoft.com/store/apps/windows)  このアプリを使用すると、開発Microsoft EdgeデバイスChromium (Chromium Windows 10) をリモートでデバッグできます。  

開発マシンから Windows 10 デバイスをセットアップして接続する方法については、「リモート デバッグ はじめに デバイス」にWindows 10[します](../devtools-guide-chromium/remote-debugging/windows.md)。  

[Microsoft Edge (Beta)](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)のリモート ツールは、デバッグする Windows 10 デバイスで実行されている Microsoft Edge と通信するために、DevTools と同じ Microsoft Edge (Chromium) DevTools プロトコルを使用します。 [](../devtools-guide-chromium/index.md)  このアプリは、プロトコルへの各呼び出しの前に、先頭とプロセス `/msedge/` ID ( `pid` ) を追加します。  次の HTTP エンドポイントがサポートされています。  

### <a name="msedgejsonlist"></a>/msedge/json/list  

デバッグ用のデバイス上のすべてのプロセス `msedge.exe` [\(PWA](../progressive-web-apps-chromium/index.md)と Microsoft Edge\のすべてのインスタンスのすべてのタブを含む) の候補リストをWindows 10します。  

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

### <a name="msedge"></a>/msedge/  

機能的には [/msedge/json/list と同等です](#msedgejsonlist)。  

### <a name="msedgepidjsonlist"></a>/msedge/[pid]/json/list  

デバッグ用に指定されたインスタンスと一致するMicrosoft Edgeページ ターゲットの候補リスト `[pid]` を提供します。  

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

### <a name="msedgepidjsonversion"></a>/msedge/[pid]/json/version  

指定されたバージョンと一Microsoft Edge、サポートする DevTools プロトコルのバージョンに一致するインスタンスに関する情報 `[pid]` を提供します。  

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

### <a name="msedgepidjsonprotocol"></a>/msedge/[pid]/json/protocol/  

指定されたインスタンスと一致するインスタンスの JSON としてシリアル化Microsoft Edgeプロトコル API サーフェス全体を提供します `[pid]` 。  

**パラメーター**  

**なし**  

**Return オブジェクト**  

指定されたインスタンスに一致するプロトコルのバージョンで使用可能な API サーフェスを表Microsoft Edge JSON `[pid]` オブジェクト。  
