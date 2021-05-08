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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a><span data-ttu-id="f231b-104">デバッガーの拡張機能Microsoft Edge Visual Studio Codeする</span><span class="sxs-lookup"><span data-stu-id="f231b-104">Debugger For Microsoft Edge Visual Studio Code Extension</span></span>  

<span data-ttu-id="f231b-105">デバッガーを[使用Microsoft Edge Visual Studio Code、][VisualstudioMarketplaceDebuggerMicrosoftEdge]フロントエンド JavaScript コード行を 1 行に 1 行でデバッグし、アプリケーションから `console.log()` 直接ステートメント[をVisual Studio Code!][VisualstudioCode]</span><span class="sxs-lookup"><span data-stu-id="f231b-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="動作中のエッジ Visual Studio Codeデバッガー" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="f231b-107">動作中のエッジ Visual Studio Codeデバッガー</span><span class="sxs-lookup"><span data-stu-id="f231b-107">Debugger for Edge Visual Studio Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a><span data-ttu-id="f231b-108">起動Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f231b-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="f231b-109">アクティビティ バーの [デバッグ] ビュー \( `Ctrl` + `Shift` + `D` Windows `Command` + `Shift` + `D` macOS\) に**移動します**。</span><span class="sxs-lookup"><span data-stu-id="f231b-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="f231b-110">構成が設定されていない場合は、Visual Studio Codeまたは macOS Windowsを選択するか、緑色の [再生] `F5` ボタン**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="f231b-110">If you do not have any configurations in Visual Studio Code, select `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="f231b-111">ドロップダウン **で [エッジ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f231b-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="f231b-112">次の構成の `launch.json` ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f231b-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="f231b-113">Windows または macOS で選択するか、緑色の [再生] ボタンを再度選択すると、Visual Studio Code は `F5` Microsoft Edge \(EdgeHTML\) を起動し、ポートで実行している Web プロジェクトを Visual Studio Code から直接\*\*\*\* `8080` デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="f231b-113">If you select `F5` on Windows or macOS or select the green **Play** button again, Visual Studio Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from Visual Studio Code!</span></span>  

### <a name="microsoft-edge-chromium"></a><span data-ttu-id="f231b-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="f231b-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="f231b-115">Microsoft Edge \(Chromium\) を起動する場合は、Microsoft Edge \(EdgeHTML\) の代わりに新しい Microsoft Edge を起動する場合は、\( 、、\) を起動する `version` Microsoft Edge \(Chromium\) のバージョンで既存の構成に属性を追加します `dev` 。 `beta` `canary`</span><span class="sxs-lookup"><span data-stu-id="f231b-115">If you want to launch Microsoft Edge \(Chromium\), the new Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span>  <span data-ttu-id="f231b-116">以下の構成では、Canary バージョンの Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="f231b-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="f231b-117">ファイルへのMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="f231b-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="f231b-118">\(Visual Studio Code\) Microsoft EdgeにChromiumします。</span><span class="sxs-lookup"><span data-stu-id="f231b-118">Attach Visual Studio Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="f231b-119">ターミナルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f231b-119">From your terminal, run the following command.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="f231b-120">以下の構成をファイルに追加 `launch.json` します。</span><span class="sxs-lookup"><span data-stu-id="f231b-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="f231b-121">この構成を実行すると、Visual Studio Code \(Microsoft Edge\) にChromiumデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="f231b-121">If you now run this configuration, Visual Studio Code attaches to Microsoft Edge \(Chromium\) and start debugging.</span></span>  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a><span data-ttu-id="f231b-122">拡張機能チームの要素と連絡を取Microsoft Edge Visual Studio Codeする</span><span class="sxs-lookup"><span data-stu-id="f231b-122">Getting in touch with the Elements for Microsoft Edge Visual Studio Code extension team</span></span>    

<span data-ttu-id="f231b-123">拡張機能の repo[で問題を][GithubMicrosoftVscodeEdgeDebug2NewIssue]提出して[GitHubフィードバック][GithubMicrosoftVscodeEdgeDebug2]を送信します。</span><span class="sxs-lookup"><span data-stu-id="f231b-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="f231b-124">ディレクトリ内の実行ごとに作成されるデバッグ アダプター ログ ファイルを名前で `%temp%` 含める必要があります `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="f231b-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="f231b-125">このファイルを問題のコメントにドラッグして、問題のコメントにGitHub。</span><span class="sxs-lookup"><span data-stu-id="f231b-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="f231b-126">拡張機能の要素をより良くMicrosoft Edge Visual Studio Code、投稿を歓迎します。</span><span class="sxs-lookup"><span data-stu-id="f231b-126">To help make the Elements for Microsoft Edge Visual Studio Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="f231b-127">拡張機能の repo で開始するために[GitHubすべてを][GithubMicrosoftVscodeEdgeDebug2]見つける。</span><span class="sxs-lookup"><span data-stu-id="f231b-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "デバッガー for Edge Visual Studio Code拡張機能の動作中"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 用デバッガー |Visual Studio Marketplace"  
