---
description: アプリケーションから Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をデバッグするVisual Studio Code
title: デバッグ Microsoft Edge (Chromium) からVisual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs code, visual studio code, Debugger
ms.openlocfilehash: e36348fc1ef5e30a511e6eda73c7646a85d8717e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399296"
---
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a>デバッガーの拡張機能Microsoft Edge Visual Studio Codeする  

デバッガーを[使用Microsoft Edge Visual Studio Code、][VisualstudioMarketplaceDebuggerMicrosoftEdge]フロントエンド JavaScript コード行を 1 行に 1 行でデバッグし、アプリケーションから `console.log()` 直接ステートメント[をVisual Studio Code!][VisualstudioCode]  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="動作中のエッジ Visual Studio Codeデバッガー" lightbox="./media/debugger-for-edge.gif":::
   動作中のエッジ Visual Studio Codeデバッガー  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a>起動Microsoft Edge  

アクティビティ バーの [デバッグ] ビュー \( `Ctrl` + `Shift` + `D` Windows `Command` + `Shift` + `D` macOS\) に**移動します**。  構成が設定されていない場合は、Visual Studio Codeまたは macOS Windowsを選択するか、緑色の [再生] `F5` ボタン**を選択**します。  ドロップダウン **で [エッジ** ] を選択します。  次の構成の `launch.json` ファイルが表示されます。  

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

Windows または macOS で選択するか、緑色の [再生] ボタンを再度選択すると、Visual Studio Code は `F5` Microsoft Edge \(EdgeHTML\) を起動し、ポートで実行している Web プロジェクトを Visual Studio Code から直接**** `8080` デバッグできます。  

### <a name="microsoft-edge-chromium"></a>Microsoft Edge (Chromium)  

Microsoft Edge \(Chromium\) を起動する場合は、Microsoft Edge \(EdgeHTML\) の代わりに新しい Microsoft Edge を起動する場合は、\( 、、\) を起動する `version` Microsoft Edge \(Chromium\) のバージョンで既存の構成に属性を追加します `dev` 。 `beta` `canary`  以下の構成では、Canary バージョンの Microsoft Edge \(Chromium\) を起動します。  

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

## <a name="attaching-to-microsoft-edge"></a>ファイルへのMicrosoft Edge  

\(Visual Studio Code\) Microsoft EdgeにChromiumします。  ターミナルから、次のコマンドを実行します。  

```shell
start msedge --remote-debugging-port=9222
```  

以下の構成をファイルに追加 `launch.json` します。   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

この構成を実行すると、Visual Studio Code \(Microsoft Edge\) にChromiumデバッグを開始します。  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a>拡張機能チームの要素と連絡を取Microsoft Edge Visual Studio Codeする    

拡張機能の repo[で問題を][GithubMicrosoftVscodeEdgeDebug2NewIssue]提出して[GitHubフィードバック][GithubMicrosoftVscodeEdgeDebug2]を送信します。  ディレクトリ内の実行ごとに作成されるデバッグ アダプター ログ ファイルを名前で `%temp%` 含める必要があります `vscode-edge-debug2.txt` 。  このファイルを問題のコメントにドラッグして、問題のコメントにGitHub。  

拡張機能の要素をより良くMicrosoft Edge Visual Studio Code、投稿を歓迎します。  拡張機能の repo で開始するために[GitHubすべてを][GithubMicrosoftVscodeEdgeDebug2]見つける。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "デバッガー for Edge Visual Studio Code拡張機能の動作中"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
