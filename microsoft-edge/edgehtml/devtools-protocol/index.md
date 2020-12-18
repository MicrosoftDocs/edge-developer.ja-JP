---
description: Microsoft Edge DevTools プロトコルを使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグします。
title: Microsoft Edge DevTools プロトコル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2ba81e51d3f9abd2aa2011993532566885ce553f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234784"
---
# Microsoft Edge (EdgeHTML) DevTools プロトコル

> [!NOTE]
> Microsoft Edge (EdgeHTML) DevTools プロトコルは [、Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 以降のビルドでのみ動作します。

開発者ツールは **、Microsoft Edge (EdgeHTML) DevTools プロトコル** を使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグできます。 EdgeHTML エンジンインストルメンテーションの異なる [ドメイン](0.2/domains/index.md) に編成されたメソッドとイベントのセットを提供します。

 ツール クライアントは、これらのメソッドを呼び出し、Microsoft Edge (EdgeHTML) または Windows Device Portal によってホストされる *DevTools Server* と交換される JSON Web ソケット メッセージを介してこれらのイベントを監視できます。 Microsoft Edge (EdgeHTML) DevTools は[](0.2/clients.md#microsoft-edge-devtools-preview)、このプロトコルを使用して[、Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から利用できるスタンドアロンの DevTools クライアントから Microsoft Edge (EdgeHTML) を実行しているホスト コンピューターのリモート デバッグを有効にします。

Microsoft Edge (EdgeHTML) DevTools プロトコルは、Chrome DevTools プロトコル [(DevTools プロトコルの W3C WICG](https://github.com/WICG/devtools-protocol/)を参照) と密接に一致するように設計されています。しかし、このリリースでは相互運用性のギャップが既知です。

## プロトコルの使用

Microsoft Edge (EdgeHTML) の DevTools Server にカスタム ツール クライアントを接続する方法を次に示します。 Microsoft Edge DevTools [を](0.2/clients.md#microsoft-edge-devtools-preview) クライアントとして使用している場合は、リモート デバッグの手順を参照してください。

1. リモート デバッグ ポートを開き、開く URL を指定して Microsoft Edge (EdgeHTML) を起動します。 次に、例を示します。

    ```shell
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    Edge が既に起動されている場合、URL パラメーターは省略可能です。 ブラウザーのアドレス バーの横に、開発者ツール サーバーが起動した **かどうかを示すボタンが** 表示されます。

    ![開発者ツール サーバー](media/developer-tools-server.png) 

2. この [HTTP エンドポイントを使用して](0.2/http.md) 、接続可能なページ ターゲットの一覧を取得します。

    ```http
    http://localhost:9222/json/list
    ```

3. 目的のページの一覧に接続して、さらにプロトコル コマンドを発行し、devtools ソケット サーバー経由でイベント メッセージ `webSocketDebuggerUrl` を受信します。 [](0.2/domains/index.md)

## 状態とフィードバック

DevTools プロトコルのバージョン[0.2](0.2/index.md)には、バージョン[0.1](0.1/index.md)で導入されたコア スクリプトデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール API 用の新しいドメインが提供されています。 Microsoft Edge DevTools UI では、これは要素パネル、コンソール[****](../devtools-guide/elements.md)パネル、デバッガー パネルで利用可能な[**機能**](../devtools-guide/console.md)に[**変換**](../devtools-guide/debugger.md)されます。

Edge DevTools プロトコルをお試しして下さり、感謝します。 次の場所でフィードバックをお寄せください。

 - [**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): DevTools 機能のアイデアと要求

 - [**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol、DevTools、および EdgeHTML プラットフォームのバグと問題

 - [**Microsoft Edge DevTools Feedback Hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): フィードバック Hub アプリによるプロトコルと DevTools の問題と提案

## FAQ

#### 複数のクライアントが同じ DevTools Server に接続できますか?
いいえ。クライアントがデバッグしている場合は同時ではありません。 接続する最後のクライアントは、前のクライアントを開始します。 今後、追加のツールがサポートされる場合、同時クライアント接続がサポートされる可能性があります。

#### DevTools Server ポートとして 9222 を使用する必要がありますか。
いいえ、そうではありません。 任意のポートを指定することができますが、まだ使用されていないポートを選ぶ必要があります。 リモート デバッグ用のポート 9222 は、規則によって使用されます。

#### DevTools Server を実行している Microsoft Edge (EdgeHTML) にカスタム ツール クライアントを接続する方法
ローカル [*コンピューターで実行されている*](#using-the-protocol) Microsoft Edge (EdgeHTML) に接続するには、上記のプロトコル手順の使用を参照してください。 リモート デバッグをサポートする場合は [、Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) が使用するインストール ダイアログなど、ホスト マシンの SSL 証明書をクライアントにインストールするユーザー ワークフローを作成する必要があります。

#### Edge DevTools を使用してリモート デバッグを行う場合 *、--devtools-server-port* cmd ライン スイッチを使用してホスト ブラウザー プロセスを開始する必要がありますか? 
いいえ、そうではありません。 [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)を使用してリモート デバッグをセットアップする場合、Edge を起動するためにコマンド ライン スイッチ `--devtools-server-port` は必要ありません。 この場合、Windows *Device Portal は* ブラウザーの代わりに DevTools Server をホストしています。

#### Edge DevTools プロトコルを使用して、アプリケーション プロセスまたは webview プロセスWWAHost.exeデバッグできますか。
現在、Edge DevTools プロトコルはブラウザーのタブのみをサポートしています。 WWAHost.exe Webview プロセスはサポートされていません。
