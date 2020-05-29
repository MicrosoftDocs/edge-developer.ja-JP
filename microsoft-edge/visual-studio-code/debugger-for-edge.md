---
description: VS コードから Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をデバッグする方法
title: VS コードから Microsoft Edge (Chromium) をデバッグする
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/10/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー
ms.openlocfilehash: 7d8d2f87500b3e81866b49de32db91c0a525baf2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570737"
---
# Microsoft Edge VS コード拡張用デバッガー

[Microsoft Edge VS のコード拡張用のデバッガー](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)を使うと、フロントエンド JavaScript コードを1行ずつデバッグし、 `console.log()` [Visual Studio コード](https://code.visualstudio.com/)からステートメントを直接表示することができます。

![エッジと、作業中のコード拡張用デバッガーの GIF](./media/debugger-for-edge.gif)

## Microsoft Edge を起動する

`Ctrl`  +  `Shift`  +  `D` アクティビティバーの (Windows または Mac 上の `Command`  +  `Shift`  +  `D` ) **Activity Bar**デバッグビューに移動します。 VS コードにまだ構成がない場合 `F5` は、Windows または Mac を押すか、緑色の**再生**ボタンをクリックします。 ドロップダウンで [Edge] を選びます。 これで、次のように構成された**launch**ファイルが表示されます。

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "edge",
            "request": "launch",
            "name": "Launch Edge against localhost",
            "url": "http://localhost:8080",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```

`F5`Windows または Mac を押すか、緑色の [**再生**] ボタンをもう一度クリックすると、vs コードによって Microsoft Edge (EdgeHTML) が起動し、ポート**8080**で実行している web プロジェクトを vs コードから直接デバッグできるようになります。

### Microsoft Edge (Chromium)

Microsoft edge (Chromium) を起動するには、microsoft edge (EdgeHTML) の代わりに、次のバージョンの microsoft edge の代わりに、 `version` 起動する Microsoft edge (Chromium) のバージョンを使用して、既存の構成に属性を追加 `dev` `beta` `canary` します。 以下の構成では、Microsoft Edge (Chromium) のカナリアバージョンが起動されます。

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Edge against localhost",
    "url": "http://localhost:8080",
    "webRoot": "${workspaceFolder}"
}
```

## Microsoft Edge へのアタッチ

また、Microsoft Edge (Chromium) に VS コードをアタッチすることもできます。 ターミナルから次のコマンドを実行します。

`start msedge --remote-debugging-port=9222`

以下の構成を、使用**し**ている json ファイルに追加します。

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```

この構成を現在実行している場合、VS コードは Microsoft Edge (Chromium) にアタッチされ、デバッグを開始できます。

## フィードバック

この拡張機能の[GitHub リポジトリ](https://github.com/Microsoft/vscode-edge-debug2)に[関する問題を提出](https://github.com/Microsoft/vscode-edge-debug2/issues/new)して、フィードバックをお送りください。 名前の付いた% temp% ディレクトリで、実行ごとに作成された debug adapter ログファイルを含めてください `vscode-edge-debug2.txt` 。 このファイルを問題のコメントにドラッグして、GitHub にアップロードすることができます。

この延長を改善したい場合は、ご協力をお寄せください。 [GitHub リポジトリ](https://github.com/Microsoft/vscode-edge-debug2)での作業を開始するために必要なすべての情報を確認できます。