---
description: Visual Studio コードから Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をデバッグする方法
title: Visual Studio コードから Microsoft Edge (Chromium) をデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、デバッガー
ms.openlocfilehash: df15b76cc26ad01d3b8508362aa4b86998f8b41b
ms.sourcegitcommit: acf8ad7cb6c8ecf83a6170f8eeb9bec32878f8ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182506"
---
# Microsoft Edge Visual Studio コード拡張用デバッガー  

Microsoft Edge Visual Studio コード拡張機能 [のデバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge] を使って、フロントエンド JavaScript コードを1行ずつデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接表示します。  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="勤務先の Edge Visual Studio コード拡張用デバッガー" lightbox="./media/debugger-for-edge.gif":::
   勤務先の Edge Visual Studio コード拡張用デバッガー  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## Microsoft Edge を起動する  

`Ctrl` + `Shift` + `D` アクティビティバーの (Windows または macOS 上の `Command` + `Shift` + `D` ) **Activity Bar**デバッグビューに移動します。  Visual Studio コードにいずれの構成も含まれていない場合 `F5` は、Windows または macOS を押すか、緑色の **再生** ボタンを選択します。  ドロップダウンで [ **エッジ** ] を選択します。  `launch.json`次の構成のファイルが表示されます。  

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

`F5`Windows または macOS を押すか、緑色の [**再生**] ボタンをもう一度選択すると、visual Studio コードが Microsoft Edge \ (EdgeHTML \) を起動し、ポートで実行している Web プロジェクトを `8080` visual studio コードから直接デバッグできます。  

### Microsoft Edge (Chromium)  

Microsoft edge \ (EdgeHTML \) ではなく、microsoft edge \ (Chromium \) を起動するには、microsoft edge \ ( `version` Chromium \) を起動するバージョンの microsoft edge \ (\) を使って、既存の構成に属性を追加するだけ `dev` `beta` `canary` です。  以下の構成では、Microsoft Edge \ (Chromium) のカナリアバージョンが起動されます。  

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

Visual Studio コードを Microsoft Edge \ (Chromium) に添付します。  ターミナルから次のコマンドを実行します。  

```shell
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

この構成を現在実行している場合、Visual Studio コードは Microsoft Edge \ (Chromium \) にアタッチされ、デバッグが開始されます。  

## Microsoft Edge Visual Studio コード拡張チームの要素に連絡する    

拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2]で[問題を整理][GithubMicrosoftVscodeEdgeDebug2NewIssue]して、フィードバックを送信します。  `%temp%`名前の付いたディレクトリの各実行に対して作成された debug adapter ログファイルを含めてください `vscode-edge-debug2.txt` 。  このファイルを問題のコメントにドラッグして、GitHub にアップロードします。  

Microsoft Edge Visual Studio のコード拡張機能の要素を向上させるために、投稿は歓迎されます。  拡張機能の [GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2] で始めるのに必要なものをすべて見つけます。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]:/media/debugger-for-edge.png "Edge Visual Studio のコード拡張機能が動作しています"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題-microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
