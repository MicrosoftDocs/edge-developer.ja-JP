---
description: Microsoft Edge (クロム) と Visual Studio
title: Visual Studio
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, vs, visual studio, デバッガー
ms.openlocfilehash: 562952ef238c05922e468501706ab75e1976273d
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387272"
---
# <a name="visual-studio"></a><span data-ttu-id="406ca-104">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-104">Visual Studio</span></span>  

<span data-ttu-id="406ca-105">Microsoft [Visual Studio][MicrosoftVisualstudioVs] は、統合された開発環境 \(IDE\) です。</span><span class="sxs-lookup"><span data-stu-id="406ca-105">Microsoft [Visual Studio][MicrosoftVisualstudioVs] is an integrated development environment \(IDE\).</span></span>   <span data-ttu-id="406ca-106">Web アプリの編集、デバッグ、ビルド、発行に使用します。</span><span class="sxs-lookup"><span data-stu-id="406ca-106">Use it to edit, debug, build, and publish your web apps.</span></span>  <span data-ttu-id="406ca-107">これは、Web 開発の多くの側面で使用できる機能豊富なプログラムです。</span><span class="sxs-lookup"><span data-stu-id="406ca-107">It is a feature-rich program that may be used for many aspects of your web development.</span></span>  <span data-ttu-id="406ca-108">ほとんどの ID が提供する標準エディターとデバッガーの上に、Visual Studio機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="406ca-108">Over and above the standard editor and debugger that most IDEs provide, Visual Studio includes the following features to ease your development process.</span></span>  

*   <span data-ttu-id="406ca-109">コンパイラ</span><span class="sxs-lookup"><span data-stu-id="406ca-109">compilers</span></span>  
*   <span data-ttu-id="406ca-110">コード補完ツール</span><span class="sxs-lookup"><span data-stu-id="406ca-110">code completion tools</span></span>  
*   <span data-ttu-id="406ca-111">グラフィカル デザイナー</span><span class="sxs-lookup"><span data-stu-id="406ca-111">graphical designers</span></span>  
*   <span data-ttu-id="406ca-112">より多くの</span><span class="sxs-lookup"><span data-stu-id="406ca-112">many more</span></span>  
    
<span data-ttu-id="406ca-113">ファイルをまだ使用していない場合はVisual Studioに移動 [し][MicrosoftVisualstudioDownloads] 、Visual Studioダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="406ca-113">If you are not already using Visual Studio, navigate to [Download Visual Studio][MicrosoftVisualstudioDownloads] to download it.</span></span>  

<span data-ttu-id="406ca-114">現在、Visual Studio 2019 では、Microsoft Edge での JavaScript のデバッグがサポートされ、ASP.NET Core アプリASP.NETサポートされています。</span><span class="sxs-lookup"><span data-stu-id="406ca-114">Currently, Visual Studio 2019 supports debugging JavaScript in Microsoft Edge for your ASP.NET Framework and ASP.NET Core apps.</span></span>  <span data-ttu-id="406ca-115">Microsoft Edge のデバッグに使用するVisual Studio手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="406ca-115">Complete the following steps to use Visual Studio to debug Microsoft Edge.</span></span>  

## <a name="launch-microsoft-edge"></a><span data-ttu-id="406ca-116">Microsoft Edge の起動</span><span class="sxs-lookup"><span data-stu-id="406ca-116">Launch Microsoft Edge</span></span>  

<span data-ttu-id="406ca-117">Visual Studioボタンを使用して次のワークフローを完了します。</span><span class="sxs-lookup"><span data-stu-id="406ca-117">Visual Studio completes the following workflow using a single button.</span></span>  

1.  <span data-ttu-id="406ca-118">コア アプリASP.NETとASP.NET作成します。</span><span class="sxs-lookup"><span data-stu-id="406ca-118">Builds your ASP.NET and ASP.NET Core app.</span></span>  
1.  <span data-ttu-id="406ca-119">Web サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="406ca-119">Starts your web server.</span></span>  
1.  <span data-ttu-id="406ca-120">Microsoft Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="406ca-120">Launches Microsoft Edge.</span></span>  
1.  <span data-ttu-id="406ca-121">デバッガーをVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="406ca-121">Connects the Visual Studio debugger.</span></span>  
    
<span data-ttu-id="406ca-122">簡略化されたワークフローを使用すると、MICROSOFT Edge で実行される JavaScript を IDE から直接デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="406ca-122">The simplified workflow allows you to debug JavaScript that run in Microsoft Edge directly from your IDE.</span></span>  

### <a name="create-a-new-aspnet-core-web-app"></a><span data-ttu-id="406ca-123">コア Web アプリASP.NET作成する</span><span class="sxs-lookup"><span data-stu-id="406ca-123">Create a new ASP.NET Core web app</span></span>  

<span data-ttu-id="406ca-124">2019 Visual Studio開き、[新しいプロジェクトの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-124">Open Visual Studio 2019 and choose **Create a new project**.</span></span>  <span data-ttu-id="406ca-125">次の画面で、[コア Web アプリ**ASP.NET] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-125">On the next screen, choose **ASP.NET Core Web app** > **Next**.</span></span>  

:::image type="complex" source="./media/create-new-project.png" alt-text="コア Web アプリASP.NET作成する" lightbox="./media/create-new-project.png":::
   <span data-ttu-id="406ca-127">コア Web アプリASP.NET作成する</span><span class="sxs-lookup"><span data-stu-id="406ca-127">Create a new ASP.NET Core Web app</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-128">新しいプロジェクト **のプロジェクト名を** 指定し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-128">Provide a **Project name** for your new project and choose **Create**.</span></span>  <span data-ttu-id="406ca-129">この例では、テンプレートとして  [React.js]  を選択し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-129">For the purposes of the example, choose **React.js** as the template, and choose **Create**.</span></span>  <span data-ttu-id="406ca-130">この **React.js** テンプレートは、コア アプリにReact.jsをASP.NETします。</span><span class="sxs-lookup"><span data-stu-id="406ca-130">The **React.js** template specifies how to integrate React.js with an ASP.NET Core app.</span></span>  

### <a name="launch-microsoft-edge-from-visual-studio"></a><span data-ttu-id="406ca-131">Microsoft Edge をアプリから起動Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-131">Launch Microsoft Edge from Visual Studio</span></span>  

<span data-ttu-id="406ca-132">プロジェクトを作成した後、開きます `ClientApp/src/components/Counter.js` 。</span><span class="sxs-lookup"><span data-stu-id="406ca-132">After you create your project, open `ClientApp/src/components/Counter.js`.</span></span>  <span data-ttu-id="406ca-133">ここで、JavaScript をデバッグVisual Studioするには、緑色の [再生] ボタンと[IIS Express] の横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="406ca-133">Now, to use Visual Studio to debug JavaScript, choose the dropdown next to the green **Play** button and **IIS Express**.</span></span>  

:::image type="complex" source="./media/vs-dropdown.png" alt-text="緑の [再生] ボタンと IIS Express の横にあるドロップダウン" lightbox="./media/vs-dropdown.png":::
   <span data-ttu-id="406ca-135">緑の [再生] ボタンと **IIS** Express の横 **にあるドロップダウン**</span><span class="sxs-lookup"><span data-stu-id="406ca-135">The dropdown next to the green **Play** button and **IIS Express**</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-136">[スクリプト**のデバッグが有効]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-136">Choose **Script Debugging** > **Enabled**.</span></span>  

:::image type="complex" source="./media/enable-script-debugging.png" alt-text="スクリプトのデバッグを有効にする方法をVisual Studio" lightbox="./media/enable-script-debugging.png":::
   <span data-ttu-id="406ca-138">スクリプトのデバッグを有効にする方法をVisual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-138">Turn on script debugging in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-139">同じドロップダウンで **、[Web ブラウザー** ] > Microsoft Edge のプレビュー チャネル (Microsoft Edge Canary、Dev、Beta など) を起動する Visual Studio を選択します。</span><span class="sxs-lookup"><span data-stu-id="406ca-139">In the same dropdown, choose **Web Browser** > the preview channel of Microsoft Edge that you want Visual Studio to launch, such as Microsoft Edge Canary, Dev, or Beta.</span></span>  <span data-ttu-id="406ca-140">Microsoft Edge プレビュー チャネルをまだ使用していない場合は [、[Microsoft Edge Insider][MicrosoftedgeinsiderDownload] チャネルのダウンロード] に移動してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="406ca-140">If you are not already using one of the Microsoft Edge preview channels, navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload] to download one.</span></span>  

:::image type="complex" source="./media/set-web-browser.png" alt-text="起動する Microsoft Edge のプレビュー チャネルVisual Studio選択する" lightbox="./media/set-web-browser.png":::
   <span data-ttu-id="406ca-142">起動する Microsoft Edge のプレビュー チャネルVisual Studio選択する</span><span class="sxs-lookup"><span data-stu-id="406ca-142">Choose the preview channel of Microsoft Edge that you want Visual Studio to launch</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="406ca-143">[Microsoft Edge\(EdgeHTML\] ) を選択した場合、Visual Studio代わりに Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="406ca-143">If you choose Microsoft Edge \(EdgeHTML\), Visual Studio launches it instead of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="406ca-144">[Microsoft Edge のプレビュー][MicrosoftedgeinsiderDownload] チャネルの 1 つをインストールするか、コンピューターにインストールされている Microsoft Edge のバージョンが Microsoft Edge \(Chromium\) であり、Microsoft Edge \(EdgeHTML\) ではインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="406ca-144">[Install the one of the preview channels of Microsoft Edge][MicrosoftedgeinsiderDownload] or ensure that the version of Microsoft Edge installed on your machine is Microsoft Edge \(Chromium\) and not Microsoft Edge \(EdgeHTML\).</span></span>  

<span data-ttu-id="406ca-145">これで、Visual Studioが正しく構成されたので、緑色の [再生] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="406ca-145">Now that Visual Studio is correctly configured, choose the green **Play** button.</span></span>  <span data-ttu-id="406ca-146">Visual Studioをビルドし、Web サーバーを起動し、Microsoft Edge を起動し、に指定されているポートに移動します `https://localhost:44362/` `launchSettings.json` 。</span><span class="sxs-lookup"><span data-stu-id="406ca-146">Visual Studio builds your app, start the web server, launch Microsoft Edge, and navigate to `https://localhost:44362/` or whatever port is specified in `launchSettings.json`.</span></span>  

:::image type="complex" source="./media/edge-launch.png" alt-text="Microsoft Edge がアプリから起動Visual Studio" lightbox="./media/edge-launch.png":::
   <span data-ttu-id="406ca-148">Microsoft Edge がアプリから起動Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-148">Microsoft Edge launches from Visual Studio</span></span>  
:::image-end:::  

### <a name="debug-javascript-running-in-microsoft-edge"></a><span data-ttu-id="406ca-149">Microsoft Edge で実行されている JavaScript のデバッグ</span><span class="sxs-lookup"><span data-stu-id="406ca-149">Debug JavaScript running in Microsoft Edge</span></span>  

<span data-ttu-id="406ca-150">再び Visual Studio に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="406ca-150">Switch back to Visual Studio.</span></span>  <span data-ttu-id="406ca-151">で `Counter.js` 、13 行目にブレークポイントを設定するには、行の横にあるガターを選択します。</span><span class="sxs-lookup"><span data-stu-id="406ca-151">In `Counter.js`, to set a breakpoint on Line 13, choose the gutter next to the line.</span></span>  

:::image type="complex" source="./media/set-breakpoint.png" alt-text="[13 行目] の横にあるCounter.jsを選択して、ブレークポイントを設定Visual Studio" lightbox="./media/set-breakpoint.png":::
   <span data-ttu-id="406ca-153">[13 行目] の横にあるガターを選択して、ブレークポイントを設定 `Counter.js` Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-153">Choose the gutter next to Line 13 in `Counter.js` to set a breakpoint in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-154">次に、起動した Microsoft Edge のインスタンスVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="406ca-154">Now switch back to the instance of Microsoft Edge that Visual Studio launched.</span></span>  <span data-ttu-id="406ca-155">Web ページ **の左側** にある NavMenu の [カウンター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="406ca-155">Choose on **Counter** in the NavMenu on the left of the webpage.</span></span>  <span data-ttu-id="406ca-156">次に、[増分] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-156">Now choose **Increment**.</span></span>  

:::image type="complex" source="./media/edge-counter.png" alt-text="コア Web アプリの [ASP.NET] ページ" lightbox="./media/edge-counter.png":::
   <span data-ttu-id="406ca-158">コア Web アプリの [ASP.NET] ページ</span><span class="sxs-lookup"><span data-stu-id="406ca-158">The Counter page in our ASP.NET Core web app</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-159">このページの JavaScript デバッガー Visual Studioで設定したブレークポイントにヒットします `Counter.js` 。</span><span class="sxs-lookup"><span data-stu-id="406ca-159">The JavaScript debugger in Visual Studio hits the breakpoint you set in `Counter.js`.</span></span>  <span data-ttu-id="406ca-160">Visual Studio、Microsoft Edge で実行されている JavaScript のランタイムを一時停止し、スクリプトを 1 行に 1 行で実行できます。</span><span class="sxs-lookup"><span data-stu-id="406ca-160">Visual Studio now pauses the runtime of the JavaScript running in Microsoft Edge and you may step through the script line-by-line.</span></span>  

:::image type="complex" source="./media/hit-breakpoint.png" alt-text="Visual Studioが Microsoft Edge で実行されている JavaScript を一時停止する" lightbox="./media/hit-breakpoint.png":::
   <span data-ttu-id="406ca-162">Visual Studioが Microsoft Edge で実行されている JavaScript を一時停止する</span><span class="sxs-lookup"><span data-stu-id="406ca-162">Visual Studio pauses JavaScript running in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-163">この例は、ユーザーが使用できる機能の小さなデモンストレーションVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="406ca-163">The example was just a minor demonstration of the functionality available in Visual Studio.</span></span>  <span data-ttu-id="406ca-164">2019 の機能の詳細については、Visual Studioドキュメントに [Visual Studioしてください][VisualStudioWindowsIndex]。</span><span class="sxs-lookup"><span data-stu-id="406ca-164">For more information about the functionality in Visual Studio 2019, navigate to [Visual Studio documentation][VisualStudioWindowsIndex].</span></span>  

## <a name="attach-to-microsoft-edge"></a><span data-ttu-id="406ca-165">Microsoft Edge に接続する</span><span class="sxs-lookup"><span data-stu-id="406ca-165">Attach to Microsoft Edge</span></span>  

<span data-ttu-id="406ca-166">以前は、Microsoft Edge をアプリから起動する必要Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="406ca-166">Previously, you had to launch Microsoft Edge from Visual Studio.</span></span>  <span data-ttu-id="406ca-167">これで、実行中の Microsoft Edge Visual Studioデバッガーを接続できます。</span><span class="sxs-lookup"><span data-stu-id="406ca-167">Now, you are able to attach the Visual Studio debugger to an already running instance of Microsoft Edge.</span></span>  

<span data-ttu-id="406ca-168">最初に、Microsoft Edge の実行中のインスタンスが含めずに確認します。</span><span class="sxs-lookup"><span data-stu-id="406ca-168">First, ensure that there are no running instances of Microsoft Edge.</span></span>  <span data-ttu-id="406ca-169">次に、コマンド ラインから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="406ca-169">Now, from your command line, run the following command.</span></span>  

```console
start msedge –remote-debugging-port=9222
```  

<span data-ttu-id="406ca-170">[Visual Studio] メニューを**開**き、[プロセスに添付]**を選択**するか、 を選択します `Ctrl` + `Alt` + `P` 。</span><span class="sxs-lookup"><span data-stu-id="406ca-170">From Visual Studio, open the **Debug** menu and choose **Attach to Process** or select `Ctrl`+`Alt`+`P`.</span></span>  

:::image type="complex" source="./media/attach-to-process.png" alt-text="[プロセスに添付] を選択Visual Studio" lightbox="./media/attach-to-process.png":::
   <span data-ttu-id="406ca-172">[ **プロセスに添付]** を選択Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-172">Choose **Attach to Process** in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-173">[プロセス**に接続] ダイアログで、[接続の**種類] を **[Chrome devtools プロトコル websocket] (認証なし) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-173">From the **Attach to Process** dialog, set **Connection type** to **Chrome devtools protocol websocket (no authentication)**.</span></span>  <span data-ttu-id="406ca-174">[接続先 **] テキスト ボックス** で、と入力して `http://localhost:9222/` 選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="406ca-174">In the **Connecting target** textbox, type `http://localhost:9222/` and select `Enter`.</span></span>  <span data-ttu-id="406ca-175">[プロセスに添付] ダイアログボックスに表示されている Microsoft Edge にある開いているタブ **の一覧を確認** します。</span><span class="sxs-lookup"><span data-stu-id="406ca-175">Review the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog.</span></span>  

:::image type="complex" source="./media/attach-to-process-dialog.png" alt-text="[プロセスに添付] ダイアログ ボックスを構成Visual Studio" lightbox="./media/attach-to-process-dialog.png":::
   <span data-ttu-id="406ca-177">[プロセスに **添付] ダイアログ ボックス** を構成Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-177">Configure the **Attach to Process** dialog in Visual Studio</span></span>  
:::image-end:::  

<span data-ttu-id="406ca-178">**[Select...] を選択>** **JavaScript (Microsoft Edge – Chromium) の**横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="406ca-178">Choose **Select...** > the checkbox next to **JavaScript (Microsoft Edge – Chromium)**.</span></span>  <span data-ttu-id="406ca-179">タブを追加するには、新しいタブに移動し、タブを閉じて、[プロセスに添付] ダイアログに反映された変更を表示するには、[更新] ボタン**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="406ca-179">To add tabs, navigate to new tabs, and close tabs and display the changes reflected in the **Attach to Process** dialog, choose the **Refresh** button.</span></span>  <span data-ttu-id="406ca-180">デバッグするタブを選択し、[アタッチ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="406ca-180">Choose the tab you want to debug and choose **Attach**.</span></span>  

<span data-ttu-id="406ca-181">これでVisual Studioデバッガーが Microsoft Edge に接続されました。</span><span class="sxs-lookup"><span data-stu-id="406ca-181">The Visual Studio debugger is now attached to Microsoft Edge.</span></span>  <span data-ttu-id="406ca-182">JavaScript の実行を一時停止し、ブレークポイントを設定し、ステートメントを確認するには、次のページの [デバッグ出力] ウィンドウで直接 `console.log()` Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="406ca-182">You may pause the running of JavaScript, set breakpoints, and review `console.log()` statements directly in the Debug Output window in Visual Studio.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-visual-studio-team"></a><span data-ttu-id="406ca-183">Microsoft のチームと連絡を取Visual Studioする</span><span class="sxs-lookup"><span data-stu-id="406ca-183">Getting in touch with the Microsoft Visual Studio team</span></span>  

<span data-ttu-id="406ca-184">Microsoft Visual Studioおよび Microsoft Edge チームは、JavaScript を使用する方法の詳細について、Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="406ca-184">The Microsoft Visual Studio and Microsoft Edge teams wants to learn more about how you work with JavaScript in Visual Studio.</span></span>  <span data-ttu-id="406ca-185">フィードバックを送信するには、[フィードバックの 送信] アイコンをVisual Studioまたはツイート@VisualStudio[を@EdgeDevTools。][TwitterIntentTweetViualstudioEdgdevtools]</span><span class="sxs-lookup"><span data-stu-id="406ca-185">To send your feedback, choose the **Send Feedback** icon in Visual Studio or tweet [@VisualStudio and @EdgeDevTools][TwitterIntentTweetViualstudioEdgdevtools].</span></span>  

:::image type="complex" source="./media/feedback-icon.png" alt-text="[フィードバックの送信] Visual Studio" lightbox="./media/feedback-icon.png":::
   <span data-ttu-id="406ca-187">[ **フィードバックの送信** ] Visual Studio</span><span class="sxs-lookup"><span data-stu-id="406ca-187">The **Send Feedback** icon in Visual Studio</span></span>  
:::image-end:::  

<!-- links -->  

[VisualStudioWindowsIndex]: /visualstudio/windows/index "Visual Studioドキュメント|Microsoft Docs"  

[MicrosoftVisualstudioDownloads]: https://visualstudio.microsoft.com/downloads "ダウンロード Visual Studio"  
[MicrosoftVisualstudioVs]: https://visualstudio.microsoft.com/vs "Visual Studio IDE"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[TwitterIntentTweetViualstudioEdgdevtools]: https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools "ツイートして@VisualStudioと@EdgeDevTools |Twitter"  
