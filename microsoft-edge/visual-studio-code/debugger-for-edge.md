---
description: VS コードから Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をデバッグする方法
title: VS コードから Microsoft Edge (Chromium) をデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー
ms.openlocfilehash: d9f33a17db7083a6a7cbb013dbf9886755f92c5e
ms.sourcegitcommit: 56cb5821d1b8e96f55bfa14a4ce87a3845b009c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182302"
---
# Microsoft Edge VS コード拡張用デバッガー  

[Microsoft Edge VS のコード拡張用デバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge]を使って、フロントエンド JavaScript コードを1行ずつデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接参照します。  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="Edge 用デバッガーと作業中のコード拡張機能":::
   Edge 用デバッガーと作業中のコード拡張機能  
:::image-end:::

<!--![Debugger for Edge VS Code extension at work][ImageGifDebuggerEdge]  -->  

## Microsoft Edge を起動する  

`Ctrl` + `Shift` + `D` アクティビティバーの (Windows または macOS 上の `Command` + `Shift` + `D` ) **Activity Bar**デバッグビューに移動します。  VS コードにまだ構成がない場合 `F5` は、Windows または macOS を押すか、緑色の **再生** ボタンを選択します。  ドロップダウンで [ **エッジ** ] を選択します。  `launch.json`次の構成のファイルが表示されます。  

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

`F5`Windows または macOS を押すか、緑色の「**再生**」ボタンをもう一度選択すると、vs コードによって Microsoft Edge \ (EdgeHTML \) が起動し、vs コードから直接ポートで実行している web プロジェクトをデバッグでき `8080` ます。  

### Microsoft Edge (Chromium)  

Microsoft edge \ (Chromium \) を起動するには、microsoft edge \ (EdgeHTML \) ではなく、microsoft edge の次のバージョンを起動するために、microsoft edge `version` \ (Chromium \) を起動するバージョンの microsoft edge \ (\) で属性を追加し `stable` `dev` `beta` `canary` ます。 以下の構成では、Microsoft Edge \ (Chromium) のカナリアバージョンが起動されます。  

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

Microsoft Edge \ (Chromium \) に VS コードをアタッチします。  ターミナルから次のコマンドを実行します。  

```console
start msedge --remote-debugging-port=9222
```  

以下の構成をファイルに追加し `launch.json` ます。   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

この構成を現在実行している場合、VS コードは Microsoft Edge \ (Chromium) にアタッチしてデバッグを開始します。  

## Microsoft Edge VS コード拡張チームの要素に連絡する    

拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2]で[問題を整理][GithubMicrosoftVscodeEdgeDebug2NewIssue]して、フィードバックを送信します。  `%temp%`名前の付いたディレクトリの各実行に対して作成された debug adapter ログファイルを含めてください `vscode-edge-debug2.txt` 。  このファイルを問題のコメントにドラッグして、GitHub にアップロードします。  

Microsoft Edge VS のコード拡張機能の向上に役立つように、投稿は歓迎されます。  拡張機能の [GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2] で始めるのに必要なものをすべて見つけます。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge VS Code extension in action"  -->  
[ImagePngDebuggerEdge]:/media/debugger-for-edge.png "のようなデバッガーで、Edge とコードの拡張が動作しています  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題-microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
