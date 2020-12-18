---
description: Microsoft Edge (Chromium) と Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs, visual studio, debugger
ms.openlocfilehash: f3796a040fe6c658211b4009445b5c179ab9b077
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231210"
---
# <span data-ttu-id="aeaa4-104">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aeaa4-104">Visual Studio</span></span>

<span data-ttu-id="aeaa4-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) は、Web アプリケーションの編集、デバッグ、ビルド、発行に使用できる統合された開発環境 (IDE) です。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-105">Microsoft [Visual Studio](https://visualstudio.microsoft.com/vs/) is an integrated development environment (IDE) that you can use to edit, debug, build, and publish your web applications.</span></span> <span data-ttu-id="aeaa4-106">これは、Web 開発の多くの側面に使用できる豊富な機能を備えるプログラムです。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-106">It is a feature-rich program that can be used for many aspects of your web development.</span></span> <span data-ttu-id="aeaa4-107">Visual Studio には、ほとんどの ID で提供される標準のエディターとデバッガー以上の機能が用意されています。Visual Studio には、開発プロセスを容易にするためのコンパイラ、コード完了ツール、グラフィカル デザイナー、その他の多くの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-107">Over and above the standard editor and debugger that most IDEs provide, Visual Studio includes compilers, code completion tools, graphical designers, and many more features to ease your development process.</span></span> <span data-ttu-id="aeaa4-108">まだ使用 [していない場合](https://visualstudio.microsoft.com/downloads/) は、Visual Studioページにアクセスしてダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-108">Head to [this page](https://visualstudio.microsoft.com/downloads/) to download Visual Studio if you aren't using it yet.</span></span>

<span data-ttu-id="aeaa4-109">現在、Visual Studio 2019 では、ASP\.NET Framework および ASP\.NET Core アプリケーションの Microsoft Edge での JavaScript のデバッグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-109">Currently, Visual Studio 2019 supports debugging JavaScript in Microsoft Edge for your ASP\.NET Framework and ASP\.NET Core applications.</span></span> <span data-ttu-id="aeaa4-110">次の手順に従って、Microsoft Edge をVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-110">Follow the steps below to debug Microsoft Edge from Visual Studio.</span></span>

## <span data-ttu-id="aeaa4-111">Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="aeaa4-111">Launch Microsoft Edge</span></span>
<span data-ttu-id="aeaa4-112">Visual Studio ASP\.NET と ASP\.NET Core アプリケーションをビルドし、Web サーバーを起動し、Microsoft Edge を起動して、1 つのボタンをクリックすると Visual Studio デバッガーを接続します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-112">Visual Studio builds your ASP\.NET and ASP\.NET Core application, starts your web server, launches Microsoft Edge, and connects the Visual Studio debugger all at the click of a single button.</span></span> <span data-ttu-id="aeaa4-113">これにより、MICROSOFT Edge で実行されている JavaScript を IDE から直接デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-113">This enables you to debug JavaScript running in Microsoft Edge directly from your IDE!</span></span>

### <span data-ttu-id="aeaa4-114">新しい ASP.NET Core Web アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="aeaa4-114">Create a new ASP.NET Core web application</span></span>

<span data-ttu-id="aeaa4-115">2019 Visual Studio開き、[新しいプロジェクトの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-115">Open Visual Studio 2019 and select **Create a new project**.</span></span> <span data-ttu-id="aeaa4-116">次の画面で **、[ASP\.NET Core Web アプリケーション** ] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-116">On the next screen, select **ASP\.NET Core Web Application** and click **Next**.</span></span>

> ##### <span data-ttu-id="aeaa4-117">図 1</span><span class="sxs-lookup"><span data-stu-id="aeaa4-117">Figure 1</span></span>  
> <span data-ttu-id="aeaa4-118">新しい ASP.NET Core Web アプリケーションを作成する 新しい ASP.NET ![ Core Web アプリケーションを作成する](./media/create-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-118">Create a new ASP.NET Core Web Application ![Create a new ASP.NET Core Web Application](./media/create-new-project.png)</span></span>  

<span data-ttu-id="aeaa4-119">新しいプロジェクト **のプロジェクト名を** 入力し、[作成] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-119">Provide a **Project name** for your new project and click **Create**.</span></span> <span data-ttu-id="aeaa4-120">この例の目的上、React.jsを\*\*\*\* React.js Core アプリケーションと統合する方法を示すテンプレートとして ASP.NET を選択し、[作成] をクリック**します**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-120">For the purposes of this example, select **React.js** as the template which shows you how to integrate React.js with an ASP.NET Core application and click **Create**.</span></span>

### <span data-ttu-id="aeaa4-121">Microsoft Edge をアプリから起動Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aeaa4-121">Launch Microsoft Edge from Visual Studio</span></span>

<span data-ttu-id="aeaa4-122">プロジェクトを作成したら \*\*、ClientApp/src/components/Counter.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="aeaa4-122">Once your project has been created, open **ClientApp/src/components/Counter.js**.</span></span> <span data-ttu-id="aeaa4-123">次に、Visual Studio再生ボタンと**IIS Express**の横にあるドロップダウンを選択して、JavaScript をデバッグする必要があります。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="aeaa4-123">Now, tell Visual Studio to debug JavaScript by selecting the dropdown next to the green **Play** button and **IIS Express**.</span></span> 

> ##### <span data-ttu-id="aeaa4-124">図 2</span><span class="sxs-lookup"><span data-stu-id="aeaa4-124">Figure 2</span></span>  
> <span data-ttu-id="aeaa4-125">緑色の [再生]\*\*\*\* ボタンと **[IIS Express]** ドロップダウンの横にある、緑色の再生ボタンと IIS Express の横にある 
> ![ ドロップダウン](./media/vs-dropdown.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-125">The dropdown next to the green **Play** button and **IIS Express**
![The dropdown next to the green Play button and IIS Express](./media/vs-dropdown.png)</span></span>  

<span data-ttu-id="aeaa4-126">[スクリプト **のデバッグ] を選択し、[** 有効] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-126">Select **Script Debugging** and click **Enabled**.</span></span>

> ##### <span data-ttu-id="aeaa4-127">図 3</span><span class="sxs-lookup"><span data-stu-id="aeaa4-127">Figure 3</span></span>  
> <span data-ttu-id="aeaa4-128">[スクリプトのデバッグを有効にする] Visual Studio ![ でスクリプトのデバッグを有効Visual Studio](./media/enable-script-debugging.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-128">Enable script debugging in Visual Studio ![Enable script debugging in Visual Studio](./media/enable-script-debugging.png)</span></span>  

<span data-ttu-id="aeaa4-129">同じドロップダウンで **、[Web ブラウザー** ] を選択し、Visual Studio起動する Microsoft Edge のプレビュー チャネル (Microsoft Edge Canary、Dev、Beta) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-129">In the same dropdown, select **Web Browser** and click the preview channel of Microsoft Edge that you want Visual Studio to launch: Microsoft Edge Canary, Dev, or Beta.</span></span> <span data-ttu-id="aeaa4-130">まだインストールしていない場合は、この [ページにアクセス](https://www.microsoftedgeinsider.com/download) して Microsoft Edge プレビュー チャネルをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-130">If you haven't already, head to [this page](https://www.microsoftedgeinsider.com/download) to install the Microsoft Edge preview channels.</span></span>

> ##### <span data-ttu-id="aeaa4-131">図 4</span><span class="sxs-lookup"><span data-stu-id="aeaa4-131">Figure 4</span></span>  
> <span data-ttu-id="aeaa4-132">起動する Microsoft Edge のプレビュー チャネルをVisual Studio Microsoft Edge のプレビュー チャネルを選択し、Visual Studio ![ します。](./media/set-web-browser.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-132">Select the preview channel of Microsoft Edge that you want Visual Studio to launch ![Select the preview channel of Microsoft Edge that you want Visual Studio to launch](./media/set-web-browser.png)</span></span>  

> [!NOTE]
> <span data-ttu-id="aeaa4-133">Microsoft Edge (EdgeHTML) を選択するとVisual Studio Microsoft Edge (Chromium) の代わりに起動します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-133">If you select Microsoft Edge (EdgeHTML), Visual Studio will launch that instead of Microsoft Edge (Chromium).</span></span> <span data-ttu-id="aeaa4-134">[Microsoft Edge の](https://www.microsoftedgeinsider.com/download) プレビュー チャネルをインストールし、それらを選択するか、コンピューターにインストールされている Microsoft Edge のバージョンが Microsoft Edge (Chromium) であり、Microsoft Edge (EdgeHTML) ではインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-134">[Install the preview channels of Microsoft Edge](https://www.microsoftedgeinsider.com/download) and select them or ensure that the version of Microsoft Edge installed on your machine is Microsoft Edge (Chromium) and not Microsoft Edge (EdgeHTML).</span></span>

<span data-ttu-id="aeaa4-135">これで、Visual Studio構成が完了しました。緑色の [再生] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-135">Now that Visual Studio is correctly configured, click the green **Play** button.</span></span> <span data-ttu-id="aeaa4-136">Visual Studioアプリケーションを構築し、Web サーバーを起動し、Microsoft Edge を起動して、そのアプリケーションで指定されているポートまたはポートに `https://localhost:44362/` **launchSettings.jsします**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-136">Visual Studio will build your application, start the web server, launch Microsoft Edge, and navigate to `https://localhost:44362/` or whatever port is specified in **launchSettings.json**.</span></span>

> ##### <span data-ttu-id="aeaa4-137">図 5</span><span class="sxs-lookup"><span data-stu-id="aeaa4-137">Figure 5</span></span>  
> <span data-ttu-id="aeaa4-138">Microsoft Edge は、microsoft Edge Visual Studio ![ から起動された Microsoft Edge からVisual Studio](./media/edge-launch.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-138">Microsoft Edge launched from Visual Studio ![Microsoft Edge launched from Visual Studio](./media/edge-launch.png)</span></span>  

### <span data-ttu-id="aeaa4-139">Microsoft Edge で実行されている JavaScript のデバッグ</span><span class="sxs-lookup"><span data-stu-id="aeaa4-139">Debug JavaScript running in Microsoft Edge</span></span>

<span data-ttu-id="aeaa4-140">再び Visual Studio に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-140">Switch back to Visual Studio.</span></span> <span data-ttu-id="aeaa4-141">次 **Counter.js**行 13 のブレークポイントを設定するには、その行の横にあるとじしろをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-141">In **Counter.js**, set a breakpoint on Line 13 by clicking in the gutter next to that line.</span></span>

> ##### <span data-ttu-id="aeaa4-142">図 6</span><span class="sxs-lookup"><span data-stu-id="aeaa4-142">Figure 6</span></span>
> <span data-ttu-id="aeaa4-143">Visual Studio にブレークポイントを設定するには、Counter.jsの行 13 の横にあると\*\*\*\* じしろをクリックし、Visual Studio の行 13 の横にあるとじしろをクリック 
> ![ Counter.js](./media/set-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-143">Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in **Counter.js**
![Setting a breakpoint in Visual Studio by clicking on the gutter next to Line 13 in Counter.js](./media/set-breakpoint.png)</span></span>  

<span data-ttu-id="aeaa4-144">起動した Microsoft Edge のインスタンスにVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-144">Now switch back to the instance of Microsoft Edge that Visual Studio launched.</span></span> <span data-ttu-id="aeaa4-145">ページの **左側にある** NavMenu の [カウンター] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-145">Click on **Counter** in the NavMenu on the left of the page.</span></span> <span data-ttu-id="aeaa4-146">ここで、[増分] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-146">Now click **Increment**.</span></span>

> ##### <span data-ttu-id="aeaa4-147">図 7</span><span class="sxs-lookup"><span data-stu-id="aeaa4-147">Figure 7</span></span>
> <span data-ttu-id="aeaa4-148">ASP.NET Core Web アプリケーションの ASP.NET ページの [ ![ カウンター] ページ](./media/edge-counter.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-148">The Counter page in our ASP.NET Core web application ![The Counter page in our ASP.NET Core web application](./media/edge-counter.png)</span></span>  

<span data-ttu-id="aeaa4-149">JavaScript debugger in Visual Studio is going to hit the breakpoint we set in **Counter.js**.</span><span class="sxs-lookup"><span data-stu-id="aeaa4-149">The JavaScript debugger in Visual Studio is going to hit the breakpoint we set in **Counter.js**.</span></span> <span data-ttu-id="aeaa4-150">Visual Studio Microsoft Edge で実行されている JavaScript の実行を一時停止し、スクリプトを 1 行に 1 行ステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-150">Visual Studio has now paused execution of the JavaScript running in Microsoft Edge and you can step through the script line-by-line.</span></span>

> ##### <span data-ttu-id="aeaa4-151">図 8</span><span class="sxs-lookup"><span data-stu-id="aeaa4-151">Figure 8</span></span>
> <span data-ttu-id="aeaa4-152">Visual Studio Microsoft Edge で実行されている JavaScript の一時停止Visual Studio Microsoft Edge で ![ 実行されている JavaScript の一時停止](./media/hit-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-152">Visual Studio pausing JavaScript running in Microsoft Edge ![Visual Studio pausing JavaScript running in Microsoft Edge](./media/hit-breakpoint.png)</span></span>  

<span data-ttu-id="aeaa4-153">この例は、次の例で使用できる機能の簡単なVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-153">This example was just a minor demonstration of the functionality available in Visual Studio.</span></span> <span data-ttu-id="aeaa4-154">2019 年 1 月 2019 年にVisual Studio詳細については、ドキュメントを [参照してください](/visualstudio/windows/?view=vs-2019&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-154">Learn more about all the things you can do in Visual Studio 2019 by reading [their documentation](/visualstudio/windows/?view=vs-2019&preserve-view=true).</span></span>

## <span data-ttu-id="aeaa4-155">Microsoft Edge に接続する</span><span class="sxs-lookup"><span data-stu-id="aeaa4-155">Attach to Microsoft Edge</span></span>
<span data-ttu-id="aeaa4-156">前のワークフローでは、Microsoft Edge Visual Studio起動します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-156">In the previous workflow, Visual Studio launches Microsoft Edge.</span></span> <span data-ttu-id="aeaa4-157">このワークフローを使用すると、既に実行されている Microsoft Edge Visual Studioデバッガーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-157">With this workflow, you will be able to attach the Visual Studio debugger to an already running instance of Microsoft Edge.</span></span> 

<span data-ttu-id="aeaa4-158">最初に、Microsoft Edge の実行中のインスタンスが含めずに確認します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-158">First, ensure that there are no running instances of Microsoft Edge.</span></span> <span data-ttu-id="aeaa4-159">次に、ターミナルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-159">Now, from your terminal, run the following command:</span></span>

```console
start msedge –remote-debugging-port=9222
```

<span data-ttu-id="aeaa4-160">次Visual Studio、[デバッグ] メニュー**を開**き、[プロセスにアタッチ **] を**選択するか、押します `Ctrl`  +  `Alt`  +  `P` 。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-160">From Visual Studio, open the **Debug** menu and select **Attach to Process** or press `Ctrl` + `Alt` + `P`.</span></span>

> ##### <span data-ttu-id="aeaa4-161">図 9</span><span class="sxs-lookup"><span data-stu-id="aeaa4-161">Figure 9</span></span>
> <span data-ttu-id="aeaa4-162">Selecting **Attach to Process** in Visual Studio ![ Selecting **Attach to Process** in Visual Studio](./media/attach-to-process.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-162">Selecting **Attach to Process** in Visual Studio ![Selecting **Attach to Process** in Visual Studio](./media/attach-to-process.png)</span></span>  

<span data-ttu-id="aeaa4-163">[プロセス **にアタッチ]** ダイアログで、[接続の **種類** ] を **Chrome devtools プロトコル websocket (認証なし) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-163">From the **Attach to Process** dialog, set **Connection type** to **Chrome devtools protocol websocket (no authentication)**.</span></span> <span data-ttu-id="aeaa4-164">[接続先 **] テキストボックスに** 、入力して `http://localhost:9222/` 押 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-164">In the **Connecting target** textbox, type in `http://localhost:9222/` and press `Enter`.</span></span> <span data-ttu-id="aeaa4-165">Microsoft Edge で開いているタブの一覧が 、[プロセスにアタッチ] ダイアログ **ボックスに一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-165">You should see the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog.</span></span>

> ##### <span data-ttu-id="aeaa4-166">図 10</span><span class="sxs-lookup"><span data-stu-id="aeaa4-166">Figure 10</span></span>
> <span data-ttu-id="aeaa4-167">[プロセスに **アタッチ]** ダイアログボックスをVisual Studioの [プロセスにアタッチ] ![ ダイアログ ボックスをVisual Studio](./media/attach-to-process-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-167">Configuring the **Attach to Process** dialog in Visual Studio ![Configuring the Attach to Process dialog in Visual Studio](./media/attach-to-process-dialog.png)</span></span>  

<span data-ttu-id="aeaa4-168">**[Select...] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="aeaa4-168">Click **Select…**</span></span> <span data-ttu-id="aeaa4-169">JavaScript **(Microsoft Edge – Chromium) を確認します**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-169">and check **JavaScript (Microsoft Edge – Chromium)**.</span></span> <span data-ttu-id="aeaa4-170">[最新の情報に更新] ボタンをクリックすると、タブの追加、新しいタブへの\*\*\*\* 移動、およびタブの終了を行い、[プロセスにアタッチ] ダイアログに反映された変更**を確認**できます。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-170">You can add tabs, navigate to new tabs, and close tabs and see those changes reflected in the **Attach to Process** dialog by clicking the **Refresh** button.</span></span> <span data-ttu-id="aeaa4-171">デバッグするタブを選択し、[アタッチ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-171">Select the tab you want to debug and click **Attach**.</span></span>

<span data-ttu-id="aeaa4-172">これでVisual Studioデバッガーが Microsoft Edge にアタッチされました。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-172">The Visual Studio debugger is now attached to Microsoft Edge!</span></span> <span data-ttu-id="aeaa4-173">JavaScript の実行を一時停止し、ブレークポイントを設定し、次のコマンドの [デバッグ出力] ウィンドウでステートメント `console.log()` を直接Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-173">You can pause execution of JavaScript, set breakpoints, and see `console.log()` statements directly in the Debug Output window in Visual Studio.</span></span>

## <span data-ttu-id="aeaa4-174">Microsoft Visual Studio チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="aeaa4-174">Getting in touch with the Microsoft Visual Studio team</span></span>  

<span data-ttu-id="aeaa4-175">JavaScript を使用する方法の詳細については、このページVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="aeaa4-175">We're eager to learn more about how you work with JavaScript in Visual Studio!</span></span>  <span data-ttu-id="aeaa4-176">Please send us feedback by clicking the **Feedback** icon in Visual Studio or by twittering [ @VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text= @VisualStudio+@EdgeDevTools).</span><span class="sxs-lookup"><span data-stu-id="aeaa4-176">Please send us feedback by clicking the **Feedback** icon in Visual Studio or by tweeting [@VisualStudio and @EdgeDevTools](https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools).</span></span>  

> ##### <span data-ttu-id="aeaa4-177">図 11</span><span class="sxs-lookup"><span data-stu-id="aeaa4-177">Figure 11</span></span>
> <span data-ttu-id="aeaa4-178">[ **フィードバック** ] アイコンVisual Studioの ![ [フィードバック] アイコンVisual Studio](./media/feedback-icon.png)</span><span class="sxs-lookup"><span data-stu-id="aeaa4-178">The **Feedback** icon in Visual Studio ![The Feedback icon in Visual Studio](./media/feedback-icon.png)</span></span>  
