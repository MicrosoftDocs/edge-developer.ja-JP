---
description: Visual Studio コードから Microsoft Edge (Chromium) の要素を使う方法
title: Visual Studio コードからの Microsoft Edge (Chromium) の要素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、vs コード、visual studio コード、要素
ms.openlocfilehash: 81488c08a76a16b80a415cbd17cd0617df916f54
ms.sourcegitcommit: 1cfcf2c8970a6c2221cfbf09a23d36b08bd60690
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135496"
---
# Microsoft Edge DevTools for Visual Studio コード拡張  

使用 <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] -->この拡張機能は、 [Visual Studio コード][VisualstudioCode]内の Microsoft Edge devtools でアクセスするためのものです。  Microsoft Edge DevTools の **要素** と **ネットワーク** ツールにアクセスできます。  Microsoft Edge のインスタンスを起動するか、またはそのインスタンスにアタッチすることができます。  接続後、実行時の HTML 構造を表示し、レイアウトを変更し、スタイルの問題を修正し、ネットワークトラフィックを検査することができます。  

## 要素ツール  

既定では、拡張機能によって固有のウィンドウでブラウザーインスタンスが起動され、Microsoft Edge DevTools の **要素** 機能が提供されます。  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools  
:::image-end:::  

拡張機能の設定では、 **ヘッドレスモード** や **ネットワーク**などの機能をさらに有効にすることができます。  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   拡張設定で \ (または \) ヘッドレスモードとネットワーク検査を有効にする  
:::image-end:::  

## ヘッドレスモード  

ヘッドレスモードでは、この拡張機能はデバッグのための完全なブラウザーインスタンスを起動しません。  バックグラウンドでインスタンスが実行されます。  エディター内では、埋め込みブラウザーを操作する必要があります。  追加のブラウザーアイコンがタスクバーに表示されません。  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   ヘッドレスブラウザーで実行されている Visual Studio DevTools の Microsoft Edge DevTools  
:::image-end:::  

> [!NOTE]
> MacOS では、優先モードとしてヘッドレスモードを有効にする必要があります。  ヘッドレスモードを使用すると、ウィンドウが表示されていない場合に、ブラウザーウィンドウでそのことが報告される問題を解決する必要があり `Not Active` ます。  

## ネットワークツール  

アプリケーションのネットワークトラフィックも検査する場合は、[設定] を開き、[ **ネットワーク** ] タブを有効にします。  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-network.png":::
    Microsoft Edge DevTools for Visual Studio コードでのネットワーク検査  
:::image-end:::  

## 内線番号から Microsoft Edge を起動する  

**アクティビティバー**の Microsoft Edge ツールに移動します。  [ **Microsoft Edge ツール: ターゲット]** と表示されている場所に、アプリのブラウザーを開くプラス記号が付いています。  [ **バージョン情報:** ] オプションを選択した場合、ブラウザーで web アプリに移動して、Visual Studio コードの [ **要素** ] パネルに表示されるようにする必要があります。  

## デバッグビューから Microsoft Edge を起動する  

Visual Studio のコードでデバッグビューを使うことに慣れている場合は、Microsoft Edge DevTools にアクセスしてください。  

1.  Visual Studio のコードで、[デバッグ] ビューに移動します。 
    *   `Ctrl` + `Shift` + `D` Windows/Linux \ (macOS) でを選択 `Command` + `Shift` + `D` します。  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  Visual Studio コードにいずれの構成も含まれていない場合は、次のいずれかの操作を実行します。  
>     *   を選択し `F5` ます。  
>     *   [ **再生** ] (緑) ボタンを選択します。  
> 1.  ドロップダウンで、ドロップダウンで [ **Edge** ] を選びます。  
> 1.  `launch.json`次の構成を含むファイルを表示する必要があります。  
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
> 正しい構成を読み込んだ後、次の操作を実行します。  

1.  Visual Studio コードから **要素** ツールを起動するには、次のいずれかの操作を実行します。 
    *   を選択し `F5` ます。  
    *   [ **再生** ] (緑) ボタンを選択します。  
         
これで、次の操作を実行できるようになります。  

*   ブラウザーの screencast にアクセスします。  
*   DOM とページ上のコンポーネントのスタイルを検査します。  

## Microsoft Edge へのアタッチ  

ブラウザーを開き、Visual Studio コードにインスタンスを添付するには、次の手順を実行します。 

1.  Microsoft Edge \ (Chromium \) のインスタンスを開くには、次のコマンドをコピーして実行します。  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  インスタンスが起動したら、次のコードスニペットをファイルにコピーして貼り付け `launch.json` ます。  
    
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
    
1.  Visual Studio コードで、[ **デバッガー** ] ドロップダウンメニューを開き、[ **Microsoft Edge にアタッチ**] を選択して、[開発者ツール] を開きます。  
1.  Visual Studio コードから **要素** ツールを起動するには、次のいずれかの操作を実行します。 
    *   を選択し `F5` ます。  
    *   [ **再生** ] (緑) ボタンを選択します。  
         
これで、次の操作を実行できるようになります。  

*   ブラウザーの screencast にアクセスします。  
*   DOM とページ上のコンポーネントのスタイルを検査します。  
    
## Microsoft Edge DevTools for Visual Studio コード拡張チームに連絡する  

拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]に[関する問題を整理][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]して、フィードバックを送信します。  

お手伝いしたい場合 <!--the Microsoft Edge DevTools for Visual Studio Code -->この拡張機能は、お客さまのご協力をお待ちしています。  拡張機能の [GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools] を使い始めるのに必要なものをすべて見つけます。  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新しい問題-microsoft/vscode-edge tools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for VS コード"  
