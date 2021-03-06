---
description: コードから Microsoft Edge (Chromium) の要素を使用Visual Studio方法
title: Microsoft Edge の要素 (クロム) Visual Studio コード
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs code, visual studio code, elements
ms.openlocfilehash: 83bac187fa2a9b1766a52f3f2cd176f171846e02
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398456"
---
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a>Microsoft Edge DevTools for Visual Studio コード拡張機能  

使用 <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] -->Microsoft Edge DevTools 内の Microsoft Edge DevTools にアクセスするこの拡張機能は、microsoft Visual Studio [コードです][VisualstudioCode]。  Microsoft Edge DevTools の **[** 要素と **ネットワーク** ] ツールにアクセスできます。  Microsoft Edge のインスタンスを起動またはアタッチできます。  接続後に、ランタイム HTML 構造を表示し、レイアウトを変更し、スタイルの問題を修正し、ネットワーク トラフィックを検査することができます。  

## <a name="elements-tool"></a>要素ツール  

既定では、拡張機能は一意のウィンドウでブラウザー インスタンスを起動し、Microsoft Edge DevTools の **Elements** 機能を提供します。  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="完全なブラウザー ウィンドウで実行Visual Studio Microsoft Edge DevTools for Visual Studio コード" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   完全なブラウザー ウィンドウで実行Visual Studio Microsoft Edge DevTools for Visual Studio コード  
:::image-end:::  

拡張機能の設定では、ヘッドレス モードやネットワークなど、 **より多くの機能を** 有効 **にできます**。  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="拡張機能の設定でヘッドレス モードとネットワーク検査を有効にする (または無効にする)" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   拡張機能の設定で \(または無効にする)ヘッドレス モードとネットワーク検査を有効にする  
:::image-end:::  

## <a name="headless-mode"></a>ヘッドレス モード  

ヘッドレス モードでは、この拡張機能はデバッグする完全なブラウザー インスタンスを起動しません。  バックグラウンドでインスタンスを実行します。  エディター内にとどまり、埋め込みブラウザーを操作する必要がある場合があります。  追加のブラウザー アイコンはタスク バーに表示されません。  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="ヘッドレスで実行Visual Studio Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   ヘッドレス ブラウザーで実行Visual Studio Microsoft Edge DevTools  
:::image-end:::  

> [!NOTE]
> macOS では、優先モードとしてヘッドレス モードを有効にする必要があります。  ヘッドレス モードを使用すると、ウィンドウが表示されない場合、ブラウザー ウィンドウからそれが表示されるという問題が解決されます `Not Active` 。  

## <a name="network-tool"></a>ネットワーク ツール  

アプリケーションのネットワーク トラフィックも検査する場合は、設定を開き、[ネットワーク] タブを **オン** にします。  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools for Visual Studio コードのネットワーク検査" lightbox="./media/edge-devtools-for-vscode-network.png":::
    Microsoft Edge DevTools for Visual Studio コードのネットワーク検査  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a>Microsoft Edge の起動 拡張機能から  

アクティビティ バーの [Microsoft Edge Tools] **に移動します**。  [Microsoft Edge **Tools: Targets]** と表示される場所の横に、アプリのブラウザーを開くプラス記号があります。  **about:blank**オプションを選択した場合は、ブラウザーの Web アプリに移動して、ブラウザーの [**** コード] の [要素] パネルに表示Visual Studioがあります。  

## <a name="launching-microsoft-edge-from-the-debug-view"></a>デバッグ ビューからの Microsoft Edge の起動  

コード内のデバッグ ビューの使用に慣れている場合Visual Studioから Microsoft Edge DevTools にアクセスします。  

1.  [Visual Studio コード] で、[デバッグ] ビューに移動します。 
    *   `Ctrl` + `Shift` + `D` Windows/Linux \( `Command` + `Shift` + `D` on macOS\) で選択します。  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  コードに構成が含Visual Studio、次のいずれかの操作を実行します。  
>     *   `F5` を選択します。  
>     *   [Play **** \(green\)] ボタンを選択します。  
> 1.  ドロップダウンで、ドロップダウンで **[エッジ]** を選択します。  
> 1.  次 `launch.json` の構成を含むファイルを表示する必要があります。  
>     
>     ```json
>     {
>       "version": "0.2.0",
>       "configurations": [
>         {
>           "name": "Launch Microsoft Edge and open the Edge DevTools",
>           "request": "launch",
>           "type": "vscode-edge-devtools.debug",
>           "url": "http://localhost:8080"
>         }
>       ]
>     }
>     ```  
>     
> 正しい構成を読み込み、次のアクションを実行します。  

1.  コードから **要素** ツールを起動Visual Studio、次のいずれかの操作を実行します。 
    *   `F5` を選択します。  
    *   [Play **** \(green\)] ボタンを選択します。  
         
次に、次の操作を実行できます。  

*   ブラウザーのスクリーンキャストにアクセスします。  
*   ページ上のコンポーネントの DOM とスタイルを調します。  

## <a name="attaching-to-microsoft-edge"></a>Microsoft Edge への接続  

ブラウザーを開き、インスタンスをコードにVisual Studioするには、次の手順を実行します。 

1.  Microsoft Edge \(Chromium\) のインスタンスを開く場合は、次のコマンドをコピーして実行します。  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  インスタンスが起動した後、次のコード スニペットをコピーしてファイルに貼り付 `launch.json` けます。  
    
    ```json
    {
        "type": "vscode-edge-devtools.debug",
        "request": "attach",
        "name": "Attach to Microsoft Edge and open the developer tools",
        "url": "http://localhost:3000/",
        "webRoot": "${workspaceFolder}/out",
        "port": 9222
    }
    ```  
    
1.  [Visual Studioコード] で、[ **デバッガー** ] ドロップダウン メニューを開き、[Microsoft Edge に接続] を選択し **、開発者ツールを開きます**。  
1.  コードから **要素** ツールを起動Visual Studio、次のいずれかの操作を実行します。 
    *   `F5` を選択します。  
    *   [Play **** \(green\)] ボタンを選択します。  
         
次に、次の操作を実行できます。  

*   ブラウザーのスクリーンキャストにアクセスします。  
*   ページ上のコンポーネントの DOM とスタイルを調します。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a>Microsoft Edge DevTools for the microsoft Edge DevTools for Visual Studio コード拡張機能チームへの連絡  

拡張機能の GitHub リポジトリ [に対][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] して問題を提出して [、フィードバック][GithubMicrosoftVscodeEdgeDevtools] を送信します。  

作成を支援する場合 <!--the Microsoft Edge DevTools for Visual Studio Code -->この拡張機能を使用すると、投稿が歓迎されます。  拡張機能の GitHub リポジトリで、開始 [するために必要なすべてを][GithubMicrosoftVscodeEdgeDevtools] 見つけることができます。  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studioコード"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新しい問題 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード"  
