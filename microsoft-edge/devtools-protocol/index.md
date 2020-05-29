---
description: Microsoft Edge DevTools プロトコルを使用して、Microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグします。
title: Microsoft Edge DevTools プロトコル
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 8bef24c98dae284f2111f6a16fca4a6f27c89dc4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569592"
---
# Microsoft Edge (EdgeHTML) DevTools プロトコル

> [!NOTE]
> Microsoft Edge (EdgeHTML) DevTools プロトコルは、 [Windows 10 年 4 2018 月の更新プログラム](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)以降のビルドでのみ動作します。

開発者ツールでは、 **Microsoft edge (EdgeHTML) DevTools プロトコル**を使用して、microsoft Edge (EdgeHTML) ブラウザーを検査およびデバッグできます。 EdgeHTML engine インストルメンテーションのさまざまな[ドメイン](0.2/domains/index.md)で構成されている一連のメソッドとイベントを提供します。

 ツールクライアントは、これらのメソッドを呼び出し、Microsoft Edge (EdgeHTML) または Windows Device Portal でホストされている*Devtools サーバー*との間でやり取りされる JSON web ソケットメッセージを通じて、これらのイベントを監視します。 Microsoft Edge (EdgeHTML) DevTools はこのプロトコルを使用して、microsoft [Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)から入手できるスタンドアロンの devtools クライアントから microsoft Edge (EdgeHTML) を実行しているホストコンピューターの[リモートデバッグ](0.2/clients.md#microsoft-edge-devtools-preview)を有効にします。

Microsoft Edge (EdgeHTML) DevTools プロトコルは、Chrome DevTools プロトコルと密接に整列するように設計されていますが、このリリースでは、相互運用性に[関する](https://github.com/WICG/devtools-protocol/)重要な点があります。

## プロトコルの使用

Microsoft Edge (EdgeHTML) の DevTools サーバーにカスタムツールクライアントをアタッチする方法を次に示します。 クライアントとして Microsoft Edge DevTools を使っている場合は、[リモートデバッグ](0.2/clients.md#microsoft-edge-devtools-preview)の手順を参照してください。

1. リモートデバッグポートを開いた状態で Microsoft Edge (EdgeHTML) を起動し、開こうとしている URL を指定します。 次に、例を示します。

    ```
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    Edge が既に起動されている場合、URL パラメーターは省略可能です。 ブラウザーのアドレスバーの横に、**開発者ツールサーバー**が起動したことを示すボタンが表示されます。

    ![開発者ツールサーバー](media/developer-tools-server.png) 

2. この[HTTP エンドポイント](0.2/http.md)を使用して、アタッチ可能なページターゲットの一覧を取得します。

    ```
    http://localhost:9222/json/list
    ```

3. 目的のページの一覧に接続して、 `webSocketDebuggerUrl` さらに[プロトコルコマンド](0.2/domains/index.md)を発行し、devtools ソケットサーバーを通じてイベントメッセージを受信します。

## 状態とフィードバック

DevTools プロトコルの[バージョン 0.2](0.2/index.md)では、[バージョン 0.1](0.1/index.md)で導入されたコアスクリプトのデバッグ機能に加えて、スタイルとレイアウト (読み取り専用) デバッグとコンソール api 用の新しいドメインが提供されています。 Microsoft Edge DevTools UI では、[**要素**](../devtools-guide/elements.md)、[**コンソール**](../devtools-guide/console.md)、[**デバッガー**](../devtools-guide/debugger.md)パネルで利用できる機能に変換されます。

ご利用いただき、ありがとうございました。 皆様からのフィードバックは、次のページでご意見をお寄せください。

 - [**Microsoft Edge Developer UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475): devtools 機能のアイデアと要求

 - [**EdgeHTML Issue Tracker**](https://developer.microsoft.com/microsoft-edge/platform/issues/): Protocol、Devtools、EdgeHTML platform のバグと問題

 - [**Microsoft Edge DevTools フィードバック hub**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344): フィードバック hub アプリによるプロトコルおよび devtools の問題と提案

## FAQ

#### 複数のクライアントが同じ DevTools サーバに接続することはできますか?
いいえ。クライアントがデバッグしているときに、同時には表示されません。 接続する最後のクライアントは、前のものを開始します。 今後、その他のツールがサポートされると、クライアント間の同時接続がサポートされる可能性があります。

#### DevTools サーバーのポートとして9222を使用する必要がありますか?
いいえ、そうではありません。 どのポートも指定できますが、まだ使用していないものを選ぶことができます。 リモートデバッグ用のポート9222は、慣例で使用されます。

#### DevTools サーバーを実行しているカスタムツールクライアントを Microsoft Edge (EdgeHTML) に接続するにはどうすればよいですか?
ローカルコンピューターで実行されている Microsoft Edge (EdgeHTML) への接続については、上記のプロトコルの手順[*を*](#using-the-protocol)参照してください。 リモートデバッグをサポートすることを検討している場合は、クライアントにホストコンピューターの SSL 証明書をインストールするためのユーザーワークフローを考案する必要があります。たとえば、 [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)でのインストールダイアログが使用されます。

#### Edge DevTools を使ってリモートデバッグを行う場合は、ホストブラウザープロセスを開始する必要があります。 *--devtools-server-port* cmd line スイッチ 
いいえ、そうではありません。 [Microsoft Edge DevTools Preview を使ってリモートデバッグ](./0.2/clients.md#microsoft-edge-devtools-preview)をセットアップしている場合、 `--devtools-server-port` コマンドラインスイッチは、edge を起動するために必要ありません。 この場合、Windows *Device Portal*は、ブラウザの代わりに Devtools サーバーをホストしています。

#### エッジ DevTools プロトコルを使用して、WWAHost .exe または webview プロセスをリモートでデバッグすることはできますか?
Edge DevTools プロトコルは現在、ブラウザーのタブのみをサポートしています。 WWAHost と webview のプロセスはサポートされていません。
