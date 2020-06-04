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
# <span data-ttu-id="7d21e-104">Microsoft Edge VS コード拡張の要素</span><span class="sxs-lookup"><span data-stu-id="7d21e-104">Elements For Microsoft Edge VS Code Extension</span></span>  

<span data-ttu-id="7d21e-105">Microsoft Edge VS コード拡張[の要素][VisualstudioMarketplaceElementsMicrosoftEdgeChromium]を使って、 [Visual Studio コード][VisualstudioCode]内から Microsoft edge ブラウザーの要素ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-105">With the [Elements for Microsoft Edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] VS Code extension, use the Elements tool of the Microsoft Edge browser from within [Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="7d21e-106">起動またはアタッチのどちらでも、要素ツールは Microsoft Edge のインスタンスに接続され、ランタイム HTML 構造が表示され、レイアウトの変更やスタイルの問題の修正を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7d21e-106">By either launching or attaching, the Elements tool connects to an instance of Microsoft Edge, displays the runtime HTML structure, and allows you to alter the layout or fix styling issues.</span></span>  

:::image type="complex" source="./media/elements-for-edge.gif" alt-text="エッジと作業でのコード拡張の要素":::
   <span data-ttu-id="7d21e-108">エッジと作業でのコード拡張の要素</span><span class="sxs-lookup"><span data-stu-id="7d21e-108">Elements for Edge VS Code extension at work</span></span>  
:::image-end:::

<!--![Elements for Edge VS Code extension at work][ImageGifElementsEdge]  -->  

## <span data-ttu-id="7d21e-109">要素の拡張機能から Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="7d21e-109">Launching Microsoft Edge From the Elements extension</span></span>  

<span data-ttu-id="7d21e-110">**アクティビティバー**の要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-110">Navigate to Elements in the **Activity Bar**.</span></span>  <span data-ttu-id="7d21e-111">[ **Microsoft Edge: ターゲット] の要素**が表示される場所の横に、アプリのブラウザーを開くプラス記号が付いています。</span><span class="sxs-lookup"><span data-stu-id="7d21e-111">Next to where it says **Elements for Microsoft Edge: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="7d21e-112">[**バージョン情報:** ] オプションを選んだ場合は、ブラウザーで web アプリに移動して、VS コードの要素パネルに表示されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d21e-112">If you selected the **about:blank** option, you must navigate to your web app in the browser for it to appear in the Elements panel in VS Code.</span></span>  

## <span data-ttu-id="7d21e-113">デバッグビューから Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="7d21e-113">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="7d21e-114">Visual Studio コードでデバッグビューを使うことに慣れている場合は、そのツールの要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7d21e-114">If you are accustomed to using the Debug view in Visual Studio Code, access Elements from that tool.</span></span>  <span data-ttu-id="7d21e-115">( `Ctrl` + `Shift` + `D` Windows または macOS 上の) デバッグビューに移動 `Command` + `Shift` + `D` します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-115">Navigate to the Debug view \(`Ctrl`+`Shift`+`D` on Windows or `Command`+`Shift`+`D` on macOS\).</span></span>  

<span data-ttu-id="7d21e-116">VS コードにまだ構成がない場合 `F5` は、Windows または macOS を押すか、緑色の**再生**ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-116">If you do not have any configurations in VS Code, press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="7d21e-117">ドロップダウンで [**エッジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-117">Select **Edge** in the dropdown.</span></span> <span data-ttu-id="7d21e-118">`launch.json`次の構成のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d21e-118">You should see a `launch.json` file with the following configuration.</span></span>  

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

<span data-ttu-id="7d21e-119">これで正しい構成が読み込まれたので、 `F5` Windows または macOS を押すか、緑色の**再生**ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-119">Now that you have loaded the correct configuration, either press `F5` on Windows or macOS or select the green **Play** button.</span></span> <span data-ttu-id="7d21e-120">Microsoft Edge ブラウザーでは、ユーザーにとって使い慣れた要素ツールが VS コードで起動し、ブラウザーの screencast にアクセスして、ページのコンポーネントを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7d21e-120">The Elements tool, that is familiar to you, from the Microsoft Edge browser launches in VS Code, allowing you to access a screencast of your browser and examine the components of your page.</span></span>  

## <span data-ttu-id="7d21e-121">Microsoft Edge へのアタッチ</span><span class="sxs-lookup"><span data-stu-id="7d21e-121">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="7d21e-122">Microsoft Edge \ (Chromium \) のインスタンスに VS コードをアタッチするには、ターミナルから次のコマンドを実行して、ブラウザーを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d21e-122">To attach VS Code to an instance of Microsoft Edge\(Chromium\), you must start the browser by running the following command from your terminal.</span></span>  

`start msedge --remote-debugging-port=9222`  

<span data-ttu-id="7d21e-123">アプリが起動したら、次の構成を起動の**json**ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-123">Once the app has launched, add the configuration below to your **launch.json** file:</span></span>  

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

<span data-ttu-id="7d21e-124">[ **Microsoft Edge に添付**] を選択し、[デバッガー] ドロップダウンメニューから [要素] ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7d21e-124">Select **Attach to Microsoft Edge and open the Elements tool** from the Debugger drop-down menu.</span></span>  <span data-ttu-id="7d21e-125">次に、 `F5` Windows または macOS を押すか、緑色の「**再生**」ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-125">Next, either press `F5` on Windows or macOS or select the green **Play** button.</span></span>  <span data-ttu-id="7d21e-126">VS コード要素ツールを起動して、ブラウザーの screencast にアクセスしたり、DOM を検査したり、ページ上のコンポーネントのスタイルを確認したりします。</span><span class="sxs-lookup"><span data-stu-id="7d21e-126">VS Code launches the Elements tool, allowing you to access a screencast of your browser, inspect the DOM, and the styling of the components on your page.</span></span>  

## <span data-ttu-id="7d21e-127">Microsoft Edge VS コード拡張チームの要素に連絡する</span><span class="sxs-lookup"><span data-stu-id="7d21e-127">Getting in touch with the Elements for Microsoft Edge VS Code extension team</span></span>  

<span data-ttu-id="7d21e-128">拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]に[関する問題を整理][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]して、フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="7d21e-128">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="7d21e-129">Microsoft Edge VS のコード拡張の要素を改善したい場合は、ご協力をお待ちください。</span><span class="sxs-lookup"><span data-stu-id="7d21e-129">If you want to help make the Elements for Microsoft Edge VS Code extension better, your contributions are welcome!</span></span>  <span data-ttu-id="7d21e-130">拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]を使い始めるのに必要なものをすべて見つけます。</span><span class="sxs-lookup"><span data-stu-id="7d21e-130">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

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
