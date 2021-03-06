---
description: Microsoft Edge (Chromium) と Microsoft Edge (EdgeHTML) をコードコードからデバッグVisual Studioする方法
title: Microsoft Edge (Chromium) をコードからVisual Studioする
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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a>デバッガー For Microsoft Edge Visual Studio コード拡張機能  

Microsoft [Edge 用デバッガー Visual Studio][VisualstudioMarketplaceDebuggerMicrosoftEdge] コード拡張機能を使用して、フロントエンド JavaScript コード行を 1 行でデバッグし、コードから直接ステートメント `console.log()` [Visual Studioします][VisualstudioCode]。  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="動作中のエッジ Visual Studio コード拡張機能のデバッガー" lightbox="./media/debugger-for-edge.gif":::
   動作中のエッジ Visual Studio コード拡張機能のデバッガー  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a>Microsoft Edge の起動  

アクティビティ バーのデバッグ ビュー \( on Windows または `Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS\) に**移動します**。  コードに構成が含Visual Studio場合は、Windows または macOS で選択するか、緑色の [再生] `F5` ボタン **を選択** します。  ドロップダウン **で [エッジ** ] を選択します。  次の構成の `launch.json` ファイルが表示されます。  

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

Windows または macOS で選択するか、もう一度緑色の [再生] ボタンを選択すると、Visual Studio コードによって `F5` Microsoft Edge **** \(EdgeHTML\) が起動され、Visual Studio Code からポートで実行している Web `8080` プロジェクトを直接デバッグできます。  

### <a name="microsoft-edge-chromium"></a>Microsoft Edge (Chromium)  

Microsoft Edge \(Chromium\) を起動する場合は、Microsoft Edge \(EdgeHTML\) の代わりに、新しい Microsoft Edge を起動する Microsoft Edge \(Chromium\) のバージョンを使用して既存の構成に属性を追加するだけで `version` 、\( `dev` `beta` `canary` 、\) を起動できます。  次の構成では、Microsoft Edge \(Chromium\) の Canary バージョンを起動します。  

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

## <a name="attaching-to-microsoft-edge"></a>Microsoft Edge への接続  

Microsoft edge Visual Studioコード \(Chromium\) を添付します。  ターミナルから、次のコマンドを実行します。  

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

この構成を実行すると、Visual Studioコードが Microsoft Edge \(Chromium\) に接続され、デバッグが開始されます。  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a>Microsoft Edge Visual Studio 拡張機能チームと連絡を取り合う    

拡張機能の[GitHub][GithubMicrosoftVscodeEdgeDebug2]リポジトリ[で][GithubMicrosoftVscodeEdgeDebug2NewIssue]問題を提出して、フィードバックを送信します。  ディレクトリ内の実行ごとに作成されるデバッグ アダプター ログ ファイルを名前で `%temp%` 含める必要があります `vscode-edge-debug2.txt` 。  このファイルを問題コメントにドラッグして GitHub にアップロードします。  

Microsoft Edge 用の要素をコード拡張機能Visual Studioするには、投稿を歓迎します。  拡張機能の [GitHub リポジトリで、開始するために必要なすべてを][GithubMicrosoftVscodeEdgeDebug2] 見つけることができます。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "デバッガー for Edge Visual Studio コード拡張 in action"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studioコード"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge アプリケーションのデバッガー|Visual Studio Marketplace"  
