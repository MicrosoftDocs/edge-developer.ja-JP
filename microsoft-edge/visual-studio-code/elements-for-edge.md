---
description: VS コードから Microsoft Edge (Chromium) の要素を使う方法
title: VS コードからの Microsoft Edge (Chromium) の要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、要素
ms.openlocfilehash: ef516d8364c68b550f889bcad0fe762a73ce5f99
ms.sourcegitcommit: 652009c5cea9e75c22b077f0cbcdc0d96bd337ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "10694863"
---
# Microsoft Edge VS コード拡張の要素  

Microsoft Edge VS コード拡張[の要素][VisualstudioMarketplaceElementsMicrosoftEdgeChromium]を使って、 [Visual Studio コード][VisualstudioCode]内から Microsoft edge ブラウザーの要素ツールを使用します。  起動またはアタッチのどちらでも、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造が表示され、レイアウトの変更やスタイルの問題の修正を行うことができます。  

:::image type="complex" source="./media/elements-for-edge.gif" alt-text="エッジと作業でのコード拡張の要素":::
   エッジと作業でのコード拡張の要素  
:::image-end:::

<!--![Elements for Edge VS Code extension at work][ImageGifElementsEdge]  -->  

## 要素の拡張機能から Microsoft Edge を起動する  

**アクティビティバー**の要素に移動します。  [ **Microsoft Edge: ターゲット] の要素**が表示される場所の横に、アプリのブラウザーを開くプラス記号が付いています。  [**バージョン情報:** ] オプションを選んだ場合は、ブラウザーで web アプリに移動して、VS コードの要素パネルに表示されるようにする必要があります。  

## デバッグビューから Microsoft Edge を起動する  

Visual Studio コードでデバッグビューを使うことに慣れている場合は、そのツールの要素にアクセスします。  ( `Ctrl` + `Shift` + `D` Windows または macOS 上の) デバッグビューに移動 `Command` + `Shift` + `D` します。  

VS コードにまだ構成がない場合 `F5` は、Windows または macOS を押すか、緑色の**再生**ボタンを選択します。 ドロップダウンで [**エッジ**] を選択します。 `launch.json`次の構成のファイルが表示されます。  

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            
            "name": "Launch Microsoft Edge and open the Elements tool",
            "request": "launch",
            "type": "vscode-edge-devtools.debug",
            "url": "http://localhost:3000"
        
        }
    ]
}
```  

これで正しい構成が読み込まれたので、 `F5` Windows または macOS を押すか、緑色の**再生**ボタンを選択します。 Microsoft Edge ブラウザーでは、ユーザーにとって使い慣れた要素ツールが VS コードで起動し、ブラウザーの screencast にアクセスして、ページのコンポーネントを調べることができます。  

## Microsoft Edge へのアタッチ  

Microsoft Edge \ (Chromium \) のインスタンスに VS コードをアタッチするには、ターミナルから次のコマンドを実行して、ブラウザーを起動する必要があります。  

`start msedge --remote-debugging-port=9222`  

アプリが起動したら、次の構成を起動の**json**ファイルに追加します。  

```json
{
    "type": "vscode-edge-devtools.debug",
    "request": "attach",
    "name": "Attach to Microsoft Edge and open the Elements tool",
    "url": "http://localhost:3000/",
    "webRoot": "${workspaceFolder}/out",
    "port": 9222
}
```  

[ **Microsoft Edge に添付**] を選択し、[デバッガー] ドロップダウンメニューから [要素] ツールを開きます。  次に、 `F5` Windows または macOS を押すか、緑色の「**再生**」ボタンを選択します。  VS コード要素ツールを起動して、ブラウザーの screencast にアクセスしたり、DOM を検査したり、ページ上のコンポーネントのスタイルを確認したりします。  

## Microsoft Edge VS コード拡張チームの要素に連絡する  

拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]に[関する問題を整理][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]して、フィードバックを送信します。  

Microsoft Edge VS のコード拡張の要素を改善したい場合は、ご協力をお待ちください。  拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]を使い始めるのに必要なものをすべて見つけます。  

<!-- image links -->  

<!--[ImageGifElementsEdge]: ./media/elements-for-edge.gif "Elements for Edge VS Code extension in action"  -->  
[ImagePngElementsEdge]:/media/elements-for-edge.png "Edge VS Code extension の要素  

<!--links -->  

[VscodeElementsEdge]: ./elements-for-edge.md "Microsoft Edge VS コード拡張の要素 |Microsoft ドキュメント"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新しい問題-microsoft/vscode-edge tools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge の要素 (Chromium) |Visual Studio Marketplace"  
