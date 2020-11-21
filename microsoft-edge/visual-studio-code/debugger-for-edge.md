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
# <span data-ttu-id="57f46-104">Microsoft Edge Visual Studio コード拡張用デバッガー</span><span class="sxs-lookup"><span data-stu-id="57f46-104">Debugger For Microsoft Edge Visual Studio Code Extension</span></span>  

<span data-ttu-id="57f46-105">Microsoft Edge Visual Studio コード拡張機能 [のデバッガー][VisualstudioMarketplaceDebuggerMicrosoftEdge] を使って、フロントエンド JavaScript コードを1行ずつデバッグし、 `console.log()` [Visual Studio コード][VisualstudioCode]からステートメントを直接表示します。</span><span class="sxs-lookup"><span data-stu-id="57f46-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="勤務先の Edge Visual Studio コード拡張用デバッガー" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="57f46-107">勤務先の Edge Visual Studio コード拡張用デバッガー</span><span class="sxs-lookup"><span data-stu-id="57f46-107">Debugger for Edge Visual Studio Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <span data-ttu-id="57f46-108">Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="57f46-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="57f46-109">`Ctrl` + `Shift` + `D` アクティビティバーの (Windows または macOS 上の `Command` + `Shift` + `D` ) **Activity Bar**デバッグビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="57f46-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="57f46-110">Visual Studio コードにいずれの構成も含まれていない場合 `F5` は、Windows または macOS を押すか、緑色の **再生** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="57f46-110">If you do not have any configurations in Visual Studio Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="57f46-111">ドロップダウンで [ **エッジ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57f46-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="57f46-112">`launch.json`次の構成のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57f46-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="57f46-113">`F5`Windows または macOS を押すか、緑色の [**再生**] ボタンをもう一度選択すると、visual Studio コードが Microsoft Edge \ (EdgeHTML \) を起動し、ポートで実行している Web プロジェクトを `8080` visual studio コードから直接デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="57f46-113">If you press `F5` on Windows or macOS or select the green **Play** button again, Visual Studio Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from Visual Studio Code!</span></span>  

### <span data-ttu-id="57f46-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="57f46-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="57f46-115">Microsoft edge \ (EdgeHTML \) ではなく、microsoft edge \ (Chromium \) を起動するには、microsoft edge \ ( `version` Chromium \) を起動するバージョンの microsoft edge \ (\) を使って、既存の構成に属性を追加するだけ `dev` `beta` `canary` です。</span><span class="sxs-lookup"><span data-stu-id="57f46-115">If you want to launch Microsoft Edge \(Chromium\), the new Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span>  <span data-ttu-id="57f46-116">以下の構成では、Microsoft Edge \ (Chromium) のカナリアバージョンが起動されます。</span><span class="sxs-lookup"><span data-stu-id="57f46-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <span data-ttu-id="57f46-117">Microsoft Edge へのアタッチ</span><span class="sxs-lookup"><span data-stu-id="57f46-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="57f46-118">Visual Studio コードを Microsoft Edge \ (Chromium) に添付します。</span><span class="sxs-lookup"><span data-stu-id="57f46-118">Attach Visual Studio Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="57f46-119">ターミナルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57f46-119">From your terminal, run the following command.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="57f46-120">以下の構成をファイルに追加し `launch.json` ます。</span><span class="sxs-lookup"><span data-stu-id="57f46-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="57f46-121">この構成を現在実行している場合、Visual Studio コードは Microsoft Edge \ (Chromium \) にアタッチされ、デバッグが開始されます。</span><span class="sxs-lookup"><span data-stu-id="57f46-121">If you now run this configuration, Visual Studio Code attaches to Microsoft Edge \(Chromium\) and start debugging.</span></span>  

## <span data-ttu-id="57f46-122">Microsoft Edge Visual Studio コード拡張チームの要素に連絡する</span><span class="sxs-lookup"><span data-stu-id="57f46-122">Getting in touch with the Elements for Microsoft Edge Visual Studio Code extension team</span></span>    

<span data-ttu-id="57f46-123">拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2]で[問題を整理][GithubMicrosoftVscodeEdgeDebug2NewIssue]して、フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="57f46-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="57f46-124">`%temp%`名前の付いたディレクトリの各実行に対して作成された debug adapter ログファイルを含めてください `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="57f46-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="57f46-125">このファイルを問題のコメントにドラッグして、GitHub にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="57f46-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="57f46-126">Microsoft Edge Visual Studio のコード拡張機能の要素を向上させるために、投稿は歓迎されます。</span><span class="sxs-lookup"><span data-stu-id="57f46-126">To help make the Elements for Microsoft Edge Visual Studio Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="57f46-127">拡張機能の [GitHub リポジトリ][GithubMicrosoftVscodeEdgeDebug2] で始めるのに必要なものをすべて見つけます。</span><span class="sxs-lookup"><span data-stu-id="57f46-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]:/media/debugger-for-edge.png "Edge Visual Studio のコード拡張機能が動作しています"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題-microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
