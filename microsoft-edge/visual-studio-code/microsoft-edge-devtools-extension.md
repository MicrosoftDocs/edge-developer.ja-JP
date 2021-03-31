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
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a><span data-ttu-id="42927-104">Microsoft Edge DevTools for Visual Studio コード拡張機能</span><span class="sxs-lookup"><span data-stu-id="42927-104">Microsoft Edge DevTools for Visual Studio Code extension</span></span>  

<span data-ttu-id="42927-105">使用</span><span class="sxs-lookup"><span data-stu-id="42927-105">Use</span></span> <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] --><span data-ttu-id="42927-106">Microsoft Edge DevTools 内の Microsoft Edge DevTools にアクセスするこの拡張機能は、microsoft Visual Studio [コードです][VisualstudioCode]。</span><span class="sxs-lookup"><span data-stu-id="42927-106">this extension to access in Microsoft Edge DevTools inside [Microsoft Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="42927-107">Microsoft Edge DevTools の **[** 要素と **ネットワーク** ] ツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="42927-107">You have access to the **Elements** and **Network** tools in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="42927-108">Microsoft Edge のインスタンスを起動またはアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="42927-108">You may either launch or attach to an instance of Microsoft Edge.</span></span>  <span data-ttu-id="42927-109">接続後に、ランタイム HTML 構造を表示し、レイアウトを変更し、スタイルの問題を修正し、ネットワーク トラフィックを検査することができます。</span><span class="sxs-lookup"><span data-stu-id="42927-109">After you connect you may display the runtime HTML structure, alter the layout, fix styling issues, and inspect network traffic.</span></span>  

## <a name="elements-tool"></a><span data-ttu-id="42927-110">要素ツール</span><span class="sxs-lookup"><span data-stu-id="42927-110">Elements tool</span></span>  

<span data-ttu-id="42927-111">既定では、拡張機能は一意のウィンドウでブラウザー インスタンスを起動し、Microsoft Edge DevTools の **Elements** 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="42927-111">By default, the extension launches a browser instance in a unique window and gives you the **Elements** functionality of Microsoft Edge DevTools.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="完全なブラウザー ウィンドウで実行Visual Studio Microsoft Edge DevTools for Visual Studio コード" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   <span data-ttu-id="42927-113">完全なブラウザー ウィンドウで実行Visual Studio Microsoft Edge DevTools for Visual Studio コード</span><span class="sxs-lookup"><span data-stu-id="42927-113">Microsoft Edge DevTools for Visual Studio Code running with a full browser window</span></span>  
:::image-end:::  

<span data-ttu-id="42927-114">拡張機能の設定では、ヘッドレス モードやネットワークなど、 **より多くの機能を** 有効 **にできます**。</span><span class="sxs-lookup"><span data-stu-id="42927-114">In the extension settings, you may enable more functionality like **Headless Mode** and **Network**.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="拡張機能の設定でヘッドレス モードとネットワーク検査を有効にする (または無効にする)" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   <span data-ttu-id="42927-116">拡張機能の設定で \(または無効にする)ヘッドレス モードとネットワーク検査を有効にする</span><span class="sxs-lookup"><span data-stu-id="42927-116">Enabling \(or disabling\) headless mode and Network inspection in the extension settings</span></span>  
:::image-end:::  

## <a name="headless-mode"></a><span data-ttu-id="42927-117">ヘッドレス モード</span><span class="sxs-lookup"><span data-stu-id="42927-117">Headless Mode</span></span>  

<span data-ttu-id="42927-118">ヘッドレス モードでは、この拡張機能はデバッグする完全なブラウザー インスタンスを起動しません。</span><span class="sxs-lookup"><span data-stu-id="42927-118">In headless mode, this extension does not launch a full browser instance to debug.</span></span>  <span data-ttu-id="42927-119">バックグラウンドでインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-119">It runs an instance in the background.</span></span>  <span data-ttu-id="42927-120">エディター内にとどまり、埋め込みブラウザーを操作する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="42927-120">You may have to stay inside the editor and interact with the embedded browser.</span></span>  <span data-ttu-id="42927-121">追加のブラウザー アイコンはタスク バーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="42927-121">An extra browser icon is not be displayed in your task bar.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="ヘッドレスで実行Visual Studio Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   <span data-ttu-id="42927-123">ヘッドレス ブラウザーで実行Visual Studio Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="42927-123">Microsoft Edge DevTools for Visual Studio Code running with a headless browser</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="42927-124">macOS では、優先モードとしてヘッドレス モードを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42927-124">On macOS, you should turn on headless mode as your preferred mode.</span></span>  <span data-ttu-id="42927-125">ヘッドレス モードを使用すると、ウィンドウが表示されない場合、ブラウザー ウィンドウからそれが表示されるという問題が解決されます `Not Active` 。</span><span class="sxs-lookup"><span data-stu-id="42927-125">Using headless mode should solve an issue where, if the window is not visible, the browser window reports that it is `Not Active`.</span></span>  

## <a name="network-tool"></a><span data-ttu-id="42927-126">ネットワーク ツール</span><span class="sxs-lookup"><span data-stu-id="42927-126">Network tool</span></span>  

<span data-ttu-id="42927-127">アプリケーションのネットワーク トラフィックも検査する場合は、設定を開き、[ネットワーク] タブを **オン** にします。</span><span class="sxs-lookup"><span data-stu-id="42927-127">If you also want to inspect the network traffic of your application, open the settings and turn on the **Network** tab.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools for Visual Studio コードのネットワーク検査" lightbox="./media/edge-devtools-for-vscode-network.png":::
    <span data-ttu-id="42927-129">Microsoft Edge DevTools for Visual Studio コードのネットワーク検査</span><span class="sxs-lookup"><span data-stu-id="42927-129">Network inspection in Microsoft Edge DevTools for Visual Studio Code</span></span>  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a><span data-ttu-id="42927-130">Microsoft Edge の起動 拡張機能から</span><span class="sxs-lookup"><span data-stu-id="42927-130">Launching Microsoft Edge From the extension</span></span>  

<span data-ttu-id="42927-131">アクティビティ バーの [Microsoft Edge Tools] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="42927-131">Navigate to Microsoft Edge Tools in the **Activity Bar**.</span></span>  <span data-ttu-id="42927-132">[Microsoft Edge **Tools: Targets]** と表示される場所の横に、アプリのブラウザーを開くプラス記号があります。</span><span class="sxs-lookup"><span data-stu-id="42927-132">Next to where it says **Microsoft Edge Tools: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="42927-133">**about:blank**オプションを選択した場合は、ブラウザーの Web アプリに移動して、ブラウザーの [ コード] の [要素] パネルに表示Visual Studioがあります。</span><span class="sxs-lookup"><span data-stu-id="42927-133">If you choose the **about:blank** option, you must navigate to your web app in the browser for it to appear in the **Elements** panel in Visual Studio Code.</span></span>  

## <a name="launching-microsoft-edge-from-the-debug-view"></a><span data-ttu-id="42927-134">デバッグ ビューからの Microsoft Edge の起動</span><span class="sxs-lookup"><span data-stu-id="42927-134">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="42927-135">コード内のデバッグ ビューの使用に慣れている場合Visual Studioから Microsoft Edge DevTools にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="42927-135">If you are accustomed to using the Debug view in Visual Studio Code, access Microsoft Edge DevTools from it.</span></span>  

1.  <span data-ttu-id="42927-136">[Visual Studio コード] で、[デバッグ] ビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="42927-136">In Visual Studio Code, navigate to the Debug view</span></span> 
    *   <span data-ttu-id="42927-137">`Ctrl` + `Shift` + `D` Windows/Linux \( `Command` + `Shift` + `D` on macOS\) で選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-137">Select `Ctrl`+`Shift`+`D` on Windows/Linux  \(`Command`+`Shift`+`D` on macOS\).</span></span>  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  <span data-ttu-id="42927-138">コードに構成が含Visual Studio、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-138">If you do not have any configurations in Visual Studio Code, complete one of the following actions.</span></span>  
>     *   <span data-ttu-id="42927-139">`F5` を選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-139">Select `F5`.</span></span>  
>     *   <span data-ttu-id="42927-140">[Play  \(green\)] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-140">Choose the **Play** \(green\) button.</span></span>  
> 1.  <span data-ttu-id="42927-141">ドロップダウンで、ドロップダウンで **[エッジ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-141">In the dropdown, choose **Edge** in the dropdown.</span></span>  
> 1.  <span data-ttu-id="42927-142">次 `launch.json` の構成を含むファイルを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42927-142">A `launch.json` file should be displayed that contains the following configuration.</span></span>  
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
> <span data-ttu-id="42927-143">正しい構成を読み込み、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-143">After you load the correct configuration, complete the following action.</span></span>  

1.  <span data-ttu-id="42927-144">コードから **要素** ツールを起動Visual Studio、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-144">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="42927-145">`F5` を選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-145">Select `F5`.</span></span>  
    *   <span data-ttu-id="42927-146">[Play  \(green\)] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-146">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="42927-147">次に、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="42927-147">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="42927-148">ブラウザーのスクリーンキャストにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="42927-148">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="42927-149">ページ上のコンポーネントの DOM とスタイルを調します。</span><span class="sxs-lookup"><span data-stu-id="42927-149">Inspect the DOM and the styling of the components on your page.</span></span>  

## <a name="attaching-to-microsoft-edge"></a><span data-ttu-id="42927-150">Microsoft Edge への接続</span><span class="sxs-lookup"><span data-stu-id="42927-150">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="42927-151">ブラウザーを開き、インスタンスをコードにVisual Studioするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-151">To open a browser and attach the instance to Visual Studio Code, complete the following steps.</span></span> 

1.  <span data-ttu-id="42927-152">Microsoft Edge \(Chromium\) のインスタンスを開く場合は、次のコマンドをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-152">To open an instance of Microsoft Edge \(Chromium\), copy and run the following command.</span></span>  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="42927-153">インスタンスが起動した後、次のコード スニペットをコピーしてファイルに貼り付 `launch.json` けます。</span><span class="sxs-lookup"><span data-stu-id="42927-153">After the instance launches, copy and paste the following code snippet into your `launch.json` file.</span></span>  
    
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
    
1.  <span data-ttu-id="42927-154">[Visual Studioコード] で、[ **デバッガー** ] ドロップダウン メニューを開き、[Microsoft Edge に接続] を選択し **、開発者ツールを開きます**。</span><span class="sxs-lookup"><span data-stu-id="42927-154">In Visual Studio Code, open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span></span>  
1.  <span data-ttu-id="42927-155">コードから **要素** ツールを起動Visual Studio、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="42927-155">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="42927-156">`F5` を選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-156">Select `F5`.</span></span>  
    *   <span data-ttu-id="42927-157">[Play  \(green\)] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="42927-157">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="42927-158">次に、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="42927-158">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="42927-159">ブラウザーのスクリーンキャストにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="42927-159">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="42927-160">ページ上のコンポーネントの DOM とスタイルを調します。</span><span class="sxs-lookup"><span data-stu-id="42927-160">Inspect the DOM and the styling of the components on your page.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a><span data-ttu-id="42927-161">Microsoft Edge DevTools for the microsoft Edge DevTools for Visual Studio コード拡張機能チームへの連絡</span><span class="sxs-lookup"><span data-stu-id="42927-161">Getting in touch with the Microsoft Edge DevTools for Visual Studio Code extension team</span></span>  

<span data-ttu-id="42927-162">拡張機能の GitHub リポジトリ [に対][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] して問題を提出して [、フィードバック][GithubMicrosoftVscodeEdgeDevtools] を送信します。</span><span class="sxs-lookup"><span data-stu-id="42927-162">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="42927-163">作成を支援する場合</span><span class="sxs-lookup"><span data-stu-id="42927-163">If you want to help make</span></span> <!--the Microsoft Edge DevTools for Visual Studio Code --><span data-ttu-id="42927-164">この拡張機能を使用すると、投稿が歓迎されます。</span><span class="sxs-lookup"><span data-stu-id="42927-164">this extension better, your contributions are welcome.</span></span>  <span data-ttu-id="42927-165">拡張機能の GitHub リポジトリで、開始 [するために必要なすべてを][GithubMicrosoftVscodeEdgeDevtools] 見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="42927-165">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studioコード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studioコード"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新しい問題 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio コード"  
