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
# <a name="debugger-for-microsoft-edge-visual-studio-code-extension"></a><span data-ttu-id="15a86-104">デバッガー For Microsoft Edge Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="15a86-104">Debugger For Microsoft Edge Visual Studio Code Extension</span></span>  

<span data-ttu-id="15a86-105">Microsoft [Edge 用デバッガー Visual Studio][VisualstudioMarketplaceDebuggerMicrosoftEdge] コード拡張機能を使用して、フロントエンド JavaScript コード行を 1 行でデバッグし、コードから直接ステートメント `console.log()` [Visual Studioします][VisualstudioCode]。</span><span class="sxs-lookup"><span data-stu-id="15a86-105">With the [Debugger for Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge] Visual Studio Code extension, debug your front-end JavaScript code line by line and see `console.log()` statements directly from [Visual Studio Code][VisualstudioCode]!</span></span>  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="動作中のエッジ Visual Studio コード拡張機能のデバッガー" lightbox="./media/debugger-for-edge.gif":::
   <span data-ttu-id="15a86-107">動作中のエッジ Visual Studio コード拡張機能のデバッガー</span><span class="sxs-lookup"><span data-stu-id="15a86-107">Debugger for Edge Visual Studio Code extension at work</span></span>  
:::image-end:::

<!--![Debugger for Edge Visual Studio Code extension at work][ImageGifDebuggerEdge]  -->  

## <a name="launching-microsoft-edge"></a><span data-ttu-id="15a86-108">Microsoft Edge の起動</span><span class="sxs-lookup"><span data-stu-id="15a86-108">Launching Microsoft Edge</span></span>  

<span data-ttu-id="15a86-109">アクティビティ バーのデバッグ ビュー \( on Windows または `Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS\) に**移動します**。</span><span class="sxs-lookup"><span data-stu-id="15a86-109">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\) in the **Activity Bar**.</span></span>  <span data-ttu-id="15a86-110">コードに構成が含Visual Studio場合は、Windows または macOS で選択するか、緑色の [再生] `F5` ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="15a86-110">If you do not have any configurations in Visual Studio Code, select `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="15a86-111">ドロップダウン **で [エッジ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="15a86-111">Select **Edge** in the dropdown.</span></span>  <span data-ttu-id="15a86-112">次の構成の `launch.json` ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15a86-112">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="15a86-113">Windows または macOS で選択するか、もう一度緑色の [再生] ボタンを選択すると、Visual Studio コードによって `F5` Microsoft Edge  \(EdgeHTML\) が起動され、Visual Studio Code からポートで実行している Web `8080` プロジェクトを直接デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="15a86-113">If you select `F5` on Windows or macOS or select the green **Play** button again, Visual Studio Code launches Microsoft Edge \(EdgeHTML\) and you are able to debug any web project you have running on port `8080` directly from Visual Studio Code!</span></span>  

### <a name="microsoft-edge-chromium"></a><span data-ttu-id="15a86-114">Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="15a86-114">Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="15a86-115">Microsoft Edge \(Chromium\) を起動する場合は、Microsoft Edge \(EdgeHTML\) の代わりに、新しい Microsoft Edge を起動する Microsoft Edge \(Chromium\) のバージョンを使用して既存の構成に属性を追加するだけで `version` 、\( `dev` `beta` `canary` 、\) を起動できます。</span><span class="sxs-lookup"><span data-stu-id="15a86-115">If you want to launch Microsoft Edge \(Chromium\), the new Microsoft Edge, instead of Microsoft Edge \(EdgeHTML\), simply add a `version` attribute to your existing configuration with the version of Microsoft Edge \(Chromium\) you want to launch \(`dev`, `beta`, or `canary`\).</span></span>  <span data-ttu-id="15a86-116">次の構成では、Microsoft Edge \(Chromium\) の Canary バージョンを起動します。</span><span class="sxs-lookup"><span data-stu-id="15a86-116">The following configuration below launches the Canary version of Microsoft Edge \(Chromium\).</span></span>  

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

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="15a86-117">Microsoft Edge への接続</span><span class="sxs-lookup"><span data-stu-id="15a86-117">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="15a86-118">Microsoft edge Visual Studioコード \(Chromium\) を添付します。</span><span class="sxs-lookup"><span data-stu-id="15a86-118">Attach Visual Studio Code to Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="15a86-119">ターミナルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="15a86-119">From your terminal, run the following command.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="15a86-120">以下の構成をファイルに追加 `launch.json` します。</span><span class="sxs-lookup"><span data-stu-id="15a86-120">Add the configuration below to your `launch.json` file.</span></span>   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

<span data-ttu-id="15a86-121">この構成を実行すると、Visual Studioコードが Microsoft Edge \(Chromium\) に接続され、デバッグが開始されます。</span><span class="sxs-lookup"><span data-stu-id="15a86-121">If you now run this configuration, Visual Studio Code attaches to Microsoft Edge \(Chromium\) and start debugging.</span></span>  

## <a name="getting-in-touch-with-the-elements-for-microsoft-edge-visual-studio-code-extension-team"></a><span data-ttu-id="15a86-122">Microsoft Edge Visual Studio 拡張機能チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="15a86-122">Getting in touch with the Elements for Microsoft Edge Visual Studio Code extension team</span></span>    

<span data-ttu-id="15a86-123">拡張機能の[GitHub][GithubMicrosoftVscodeEdgeDebug2]リポジトリ[で][GithubMicrosoftVscodeEdgeDebug2NewIssue]問題を提出して、フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="15a86-123">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDebug2NewIssue] against in the [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  <span data-ttu-id="15a86-124">ディレクトリ内の実行ごとに作成されるデバッグ アダプター ログ ファイルを名前で `%temp%` 含める必要があります `vscode-edge-debug2.txt` 。</span><span class="sxs-lookup"><span data-stu-id="15a86-124">Please include the debug adapter log file, which is created for each run in the `%temp%` directory with the name `vscode-edge-debug2.txt`.</span></span>  <span data-ttu-id="15a86-125">このファイルを問題コメントにドラッグして GitHub にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="15a86-125">Drag this file into an issue comment to upload it to GitHub.</span></span>  

<span data-ttu-id="15a86-126">Microsoft Edge 用の要素をコード拡張機能Visual Studioするには、投稿を歓迎します。</span><span class="sxs-lookup"><span data-stu-id="15a86-126">To help make the Elements for Microsoft Edge Visual Studio Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="15a86-127">拡張機能の [GitHub リポジトリで、開始するために必要なすべてを][GithubMicrosoftVscodeEdgeDebug2] 見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="15a86-127">Find everything you need to get started in [GitHub repo][GithubMicrosoftVscodeEdgeDebug2] of the extension.</span></span>  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge Visual Studio Code extension in action"  -->  
[ImagePngDebuggerEdge]: ./media/debugger-for-edge.png "デバッガー for Edge Visual Studio コード拡張 in action"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studioコード"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新しい問題 - microsoft/vscode-edge-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge アプリケーションのデバッガー|Visual Studio Marketplace"  
