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
# <span data-ttu-id="105cb-104">Microsoft Edge DevTools for Visual Studio コード拡張</span><span class="sxs-lookup"><span data-stu-id="105cb-104">Microsoft Edge DevTools for Visual Studio Code extension</span></span>  

<span data-ttu-id="105cb-105">使用</span><span class="sxs-lookup"><span data-stu-id="105cb-105">Use</span></span> <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] --><span data-ttu-id="105cb-106">この拡張機能は、 [Visual Studio コード][VisualstudioCode]内の Microsoft Edge devtools でアクセスするためのものです。</span><span class="sxs-lookup"><span data-stu-id="105cb-106">this extension to access in Microsoft Edge DevTools inside [Visual Studio Code][VisualstudioCode].</span></span>  <span data-ttu-id="105cb-107">Microsoft Edge DevTools の **要素** と **ネットワーク** ツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="105cb-107">You have access to the **Elements** and **Network** tools in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="105cb-108">Microsoft Edge のインスタンスを起動するか、またはそのインスタンスにアタッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="105cb-108">You may either launch or attach to an instance of Microsoft Edge.</span></span>  <span data-ttu-id="105cb-109">接続後、実行時の HTML 構造を表示し、レイアウトを変更し、スタイルの問題を修正し、ネットワークトラフィックを検査することができます。</span><span class="sxs-lookup"><span data-stu-id="105cb-109">After you connect you may display the runtime HTML structure, alter the layout, fix styling issues, and inspect network traffic.</span></span>  

## <span data-ttu-id="105cb-110">要素ツール</span><span class="sxs-lookup"><span data-stu-id="105cb-110">Elements tool</span></span>  

<span data-ttu-id="105cb-111">既定では、拡張機能によって固有のウィンドウでブラウザーインスタンスが起動され、Microsoft Edge DevTools の **要素** 機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="105cb-111">By default, the extension launches a browser instance in a unique window and gives you the **Elements** functionality of Microsoft Edge DevTools.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   <span data-ttu-id="105cb-113">完全なブラウザーウィンドウで実行されている Visual Studio の開発ツール用の Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="105cb-113">Microsoft Edge DevTools for Visual Studio Code running with a full browser window</span></span>  
:::image-end:::  

<span data-ttu-id="105cb-114">拡張機能の設定では、 **ヘッドレスモード** や **ネットワーク**などの機能をさらに有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="105cb-114">In the extension settings, you may enable more functionality like **Headless Mode** and **Network**.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="拡張設定でのヘッドレスモードとネットワーク検査の有効化 (または無効化)" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   <span data-ttu-id="105cb-116">拡張設定で \ (または \) ヘッドレスモードとネットワーク検査を有効にする</span><span class="sxs-lookup"><span data-stu-id="105cb-116">Enabling \(or disabling\) headless mode and Network inspection in the extension settings</span></span>  
:::image-end:::  

## <span data-ttu-id="105cb-117">ヘッドレスモード</span><span class="sxs-lookup"><span data-stu-id="105cb-117">Headless Mode</span></span>  

<span data-ttu-id="105cb-118">ヘッドレスモードでは、この拡張機能はデバッグのための完全なブラウザーインスタンスを起動しません。</span><span class="sxs-lookup"><span data-stu-id="105cb-118">In headless mode, this extension does not launch a full browser instance to debug.</span></span>  <span data-ttu-id="105cb-119">バックグラウンドでインスタンスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="105cb-119">It runs an instance in the background.</span></span>  <span data-ttu-id="105cb-120">エディター内では、埋め込みブラウザーを操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="105cb-120">You may have to stay inside the editor and interact with the embedded browser.</span></span>  <span data-ttu-id="105cb-121">追加のブラウザーアイコンがタスクバーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="105cb-121">An extra browser icon is not be displayed in your task bar.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="ヘッドレスで実行される Visual Studio の Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   <span data-ttu-id="105cb-123">ヘッドレスブラウザーで実行されている Visual Studio DevTools の Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="105cb-123">Microsoft Edge DevTools for Visual Studio Code running with a headless browser</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="105cb-124">MacOS では、優先モードとしてヘッドレスモードを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="105cb-124">On macOS, you should turn on headless mode as your preferred mode.</span></span>  <span data-ttu-id="105cb-125">ヘッドレスモードを使用すると、ウィンドウが表示されていない場合に、ブラウザーウィンドウでそのことが報告される問題を解決する必要があり `Not Active` ます。</span><span class="sxs-lookup"><span data-stu-id="105cb-125">Using headless mode should solve an issue where, if the window is not visible, the browser window reports that it is `Not Active`.</span></span>  

## <span data-ttu-id="105cb-126">ネットワークツール</span><span class="sxs-lookup"><span data-stu-id="105cb-126">Network tool</span></span>  

<span data-ttu-id="105cb-127">アプリケーションのネットワークトラフィックも検査する場合は、[設定] を開き、[ **ネットワーク** ] タブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="105cb-127">If you also want to inspect the network traffic of your application, open the settings and turn on the **Network** tab.</span></span>  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools for Visual Studio コードでのネットワーク検査" lightbox="./media/edge-devtools-for-vscode-network.png":::
    <span data-ttu-id="105cb-129">Microsoft Edge DevTools for Visual Studio コードでのネットワーク検査</span><span class="sxs-lookup"><span data-stu-id="105cb-129">Network inspection in Microsoft Edge DevTools for Visual Studio Code</span></span>  
:::image-end:::  

## <span data-ttu-id="105cb-130">内線番号から Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="105cb-130">Launching Microsoft Edge From the extension</span></span>  

<span data-ttu-id="105cb-131">**アクティビティバー**の Microsoft Edge ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="105cb-131">Navigate to Microsoft Edge Tools in the **Activity Bar**.</span></span>  <span data-ttu-id="105cb-132">[ **Microsoft Edge ツール: ターゲット]** と表示されている場所に、アプリのブラウザーを開くプラス記号が付いています。</span><span class="sxs-lookup"><span data-stu-id="105cb-132">Next to where it says **Microsoft Edge Tools: Targets,** there is a plus sign that opens the browser for your app.</span></span>  <span data-ttu-id="105cb-133">[ **バージョン情報:** ] オプションを選択した場合、ブラウザーで web アプリに移動して、Visual Studio コードの [ **要素** ] パネルに表示されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="105cb-133">If you choose the **about:blank** option, you must navigate to your web app in the browser for it to appear in the **Elements** panel in Visual Studio Code.</span></span>  

## <span data-ttu-id="105cb-134">デバッグビューから Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="105cb-134">Launching Microsoft Edge from the Debug view</span></span>  

<span data-ttu-id="105cb-135">Visual Studio のコードでデバッグビューを使うことに慣れている場合は、Microsoft Edge DevTools にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="105cb-135">If you are accustomed to using the Debug view in Visual Studio Code, access Microsoft Edge DevTools from it.</span></span>  

1.  <span data-ttu-id="105cb-136">Visual Studio のコードで、[デバッグ] ビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="105cb-136">In Visual Studio Code, navigate to the Debug view</span></span> 
    *   <span data-ttu-id="105cb-137">`Ctrl` + `Shift` + `D` Windows/Linux \ (macOS) でを選択 `Command` + `Shift` + `D` します。</span><span class="sxs-lookup"><span data-stu-id="105cb-137">Select `Ctrl`+`Shift`+`D` on Windows/Linux  \(`Command`+`Shift`+`D` on macOS\).</span></span>  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  <span data-ttu-id="105cb-138">Visual Studio コードにいずれの構成も含まれていない場合は、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-138">If you do not have any configurations in Visual Studio Code, complete one of the following actions.</span></span>  
>     *   <span data-ttu-id="105cb-139">を選択し `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="105cb-139">Select `F5`.</span></span>  
>     *   <span data-ttu-id="105cb-140">[ **再生** ] (緑) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="105cb-140">Choose the **Play** \(green\) button.</span></span>  
> 1.  <span data-ttu-id="105cb-141">ドロップダウンで、ドロップダウンで [ **Edge** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="105cb-141">In the dropdown, choose **Edge** in the dropdown.</span></span>  
> 1.  <span data-ttu-id="105cb-142">`launch.json`次の構成を含むファイルを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="105cb-142">A `launch.json` file should be displayed that contains the following configuration.</span></span>  
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
> <span data-ttu-id="105cb-143">正しい構成を読み込んだ後、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-143">After you load the correct configuration, complete the following action.</span></span>  

1.  <span data-ttu-id="105cb-144">Visual Studio コードから **要素** ツールを起動するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-144">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="105cb-145">を選択し `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="105cb-145">Select `F5`.</span></span>  
    *   <span data-ttu-id="105cb-146">[ **再生** ] (緑) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="105cb-146">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="105cb-147">これで、次の操作を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="105cb-147">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="105cb-148">ブラウザーの screencast にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="105cb-148">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="105cb-149">DOM とページ上のコンポーネントのスタイルを検査します。</span><span class="sxs-lookup"><span data-stu-id="105cb-149">Inspect the DOM and the styling of the components on your page.</span></span>  

## <span data-ttu-id="105cb-150">Microsoft Edge へのアタッチ</span><span class="sxs-lookup"><span data-stu-id="105cb-150">Attaching to Microsoft Edge</span></span>  

<span data-ttu-id="105cb-151">ブラウザーを開き、Visual Studio コードにインスタンスを添付するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-151">To open a browser and attach the instance to Visual Studio Code, complete the following steps.</span></span> 

1.  <span data-ttu-id="105cb-152">Microsoft Edge \ (Chromium \) のインスタンスを開くには、次のコマンドをコピーして実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-152">To open an instance of Microsoft Edge \(Chromium\), copy and run the following command.</span></span>  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  <span data-ttu-id="105cb-153">インスタンスが起動したら、次のコードスニペットをファイルにコピーして貼り付け `launch.json` ます。</span><span class="sxs-lookup"><span data-stu-id="105cb-153">After the instance launches, copy and paste the following code snippet into your `launch.json` file.</span></span>  
    
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
    
1.  <span data-ttu-id="105cb-154">Visual Studio コードで、[ **デバッガー** ] ドロップダウンメニューを開き、[ **Microsoft Edge にアタッチ**] を選択して、[開発者ツール] を開きます。</span><span class="sxs-lookup"><span data-stu-id="105cb-154">In Visual Studio Code, open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.</span></span>  
1.  <span data-ttu-id="105cb-155">Visual Studio コードから **要素** ツールを起動するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="105cb-155">To launch the **Elements** tool from Visual Studio Code, complete one of the following actions.</span></span> 
    *   <span data-ttu-id="105cb-156">を選択し `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="105cb-156">Select `F5`.</span></span>  
    *   <span data-ttu-id="105cb-157">[ **再生** ] (緑) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="105cb-157">Choose the **Play** \(green\) button.</span></span>  
         
<span data-ttu-id="105cb-158">これで、次の操作を実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="105cb-158">Now, you may do the following actions.</span></span>  

*   <span data-ttu-id="105cb-159">ブラウザーの screencast にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="105cb-159">Access a screencast of your browser.</span></span>  
*   <span data-ttu-id="105cb-160">DOM とページ上のコンポーネントのスタイルを検査します。</span><span class="sxs-lookup"><span data-stu-id="105cb-160">Inspect the DOM and the styling of the components on your page.</span></span>  
    
## <span data-ttu-id="105cb-161">Microsoft Edge DevTools for Visual Studio コード拡張チームに連絡する</span><span class="sxs-lookup"><span data-stu-id="105cb-161">Getting in touch with the Microsoft Edge DevTools for Visual Studio Code extension team</span></span>  

<span data-ttu-id="105cb-162">拡張機能の[GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools]に[関する問題を整理][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]して、フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="105cb-162">Send your feedback by [filing an issue][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] against the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<span data-ttu-id="105cb-163">お手伝いしたい場合</span><span class="sxs-lookup"><span data-stu-id="105cb-163">If you want to help make</span></span> <!--the Microsoft Edge DevTools for Visual Studio Code --><span data-ttu-id="105cb-164">この拡張機能は、お客さまのご協力をお待ちしています。</span><span class="sxs-lookup"><span data-stu-id="105cb-164">this extension better, your contributions are welcome.</span></span>  <span data-ttu-id="105cb-165">拡張機能の [GitHub リポジトリ][GithubMicrosoftVscodeEdgeDevtools] を使い始めるのに必要なものをすべて見つけます。</span><span class="sxs-lookup"><span data-stu-id="105cb-165">Find everything you need to get started in the [GitHub repo][GithubMicrosoftVscodeEdgeDevtools] of the extension.</span></span>  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "ドキュメント |Visual Studio コード"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新しい問題-microsoft/vscode-edge tools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for VS コード"  
