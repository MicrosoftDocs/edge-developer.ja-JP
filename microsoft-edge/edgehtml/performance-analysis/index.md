---
description: F12 開発者ツールを使用して、Web サイトの一般的なパフォーマンスを分析します。
title: パフォーマンス分析
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 7a5f9fd0-90a9-43db-b271-178c06da5896
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e585d07ebae547319c16b6eea579ad26ffb84ce3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234838"
---
# <span data-ttu-id="e2733-104">パフォーマンス分析</span><span class="sxs-lookup"><span data-stu-id="e2733-104">Performance Analysis</span></span>  

<span data-ttu-id="e2733-105">パフォーマンスを向上させるのが新しい場合は [、F12 DevTools ガイドを確認してください](../devtools-guide/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e2733-105">If you're new to performance, you should check out the [F12 DevTools guide](../devtools-guide/index.md).</span></span>
<span data-ttu-id="e2733-106">Microsoft Edge [に組み込みの F12](../devtools-guide/index.md) ツールを使用して、Web サイトの一般的なパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-106">The [F12 tools](../devtools-guide/index.md) built into Microsoft Edge can be used to analyze the general performance of a web site.</span></span>  <span data-ttu-id="e2733-107">これは、ブラウザー内から Windows のパフォーマンス と類似した (ただし [Toolkit)](/windows-hardware/test/wpt/index) 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2733-107">It provides similar (but more limited) capabilities to the [Windows Performance Toolkit](/windows-hardware/test/wpt/index) from right within the browser.</span></span>  

<span data-ttu-id="e2733-108">ブラウザーのパフォーマンスの詳細な分析が必要な場合は、Microsoft Edge チームは [Windows Performance Toolkit](/windows-hardware/test/wpt/index) (WPT) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2733-108">If you want a deeper analysis of browser performance, the Microsoft Edge team uses the [Windows Performance Toolkit](/windows-hardware/test/wpt/index) (WPT).</span></span>  <span data-ttu-id="e2733-109">WPT は、プログラムのパフォーマンスを詳細に分析するために Windows チームによって作成されました。</span><span class="sxs-lookup"><span data-stu-id="e2733-109">WPT was created by the Windows team to conduct in-depth program performance analysis.</span></span>  <span data-ttu-id="e2733-110">Web サイトの JavaScript と Microsoft Edge ネイティブ コードの境界をまたがって、両方を同じツール内で表示できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-110">It straddles the boundaries between website JavaScript and Microsoft Edge native code, allowing both to be viewed within the same tool.</span></span>  <span data-ttu-id="e2733-111">WPT は、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-111">WPT can be used to:</span></span>  

*   <span data-ttu-id="e2733-112">ソフトウェアが作業を完了するために必要な CPU 時間を測定する</span><span class="sxs-lookup"><span data-stu-id="e2733-112">Measure CPU time taken for software to complete work</span></span>  
*   <span data-ttu-id="e2733-113">ソフトウェアによって割り当てられたメモリを計算する</span><span class="sxs-lookup"><span data-stu-id="e2733-113">Calculate the memory allocated by software</span></span>  
*   <span data-ttu-id="e2733-114">リモート サーバーからファイルをダウンロードする詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e2733-114">Show the details of downloading files from remote servers</span></span>  
*   <span data-ttu-id="e2733-115">フレーム レートを測定します。</span><span class="sxs-lookup"><span data-stu-id="e2733-115">Measure frame rate.</span></span>  

<span data-ttu-id="e2733-116">Windows Performance Toolkit を使って Web サイトを分析するには、まず [Windows 10 Assessment and Deployment Kit (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)をダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-116">To get started with using the Windows Performance Toolkit to analyze your website, you'll first need to download the [Windows 10 Assessment and Deployment Kit (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span>  <span data-ttu-id="e2733-117">インストール時 *に Windows パフォーマンス Toolkit* オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2733-117">Select the *Windows Performance Toolkit* option during installation:</span></span>  

![ADK インストール オプション](./media/adk-installoptions.png)  

<span data-ttu-id="e2733-119">ここでは、パフォーマンス トレースを記録して分析する方法について取り上けます。</span><span class="sxs-lookup"><span data-stu-id="e2733-119">Here we'll cover how to record and analyze a performance trace.</span></span>  
<span data-ttu-id="e2733-120">Windows Performance Toolkit に含まれる機能の詳細については、WPT の全ドキュメント [を参照してください](/windows-hardware/test/wpt/index)。</span><span class="sxs-lookup"><span data-stu-id="e2733-120">To learn more about what's included in the Windows Performance Toolkit, check out the full [WPT documentation](/windows-hardware/test/wpt/index).</span></span>  

## <span data-ttu-id="e2733-121">トレースの記録</span><span class="sxs-lookup"><span data-stu-id="e2733-121">Recording a trace</span></span>  

<span data-ttu-id="e2733-122">次に、ユーザー シナリオを設定し、Windows Performance Recorder を使用してトレースを収集する準備をします。</span><span class="sxs-lookup"><span data-stu-id="e2733-122">Next, set up your user scenario and prepare to gather a trace using Windows Performance Recorder.</span></span>  
<span data-ttu-id="e2733-123">Windows Performance *Recorder (WPR)* を使用して Web シナリオをプロファイルする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2733-123">Here's how to profile your web scenario with the *Windows Performance Recorder (WPR)*.</span></span>  

### <span data-ttu-id="e2733-124">1. パフォーマンス トレースを収集する環境を準備する</span><span class="sxs-lookup"><span data-stu-id="e2733-124">1.  Prepare your environment to gather a performance trace</span></span>  

<span data-ttu-id="e2733-125">記録するトレースのノイズを回避するために、実行中のプログラムをできる限りシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="e2733-125">Shut down as many running programs as possible to avoid noise in the trace that you're about to record.</span></span>  <span data-ttu-id="e2733-126">理想的には、実行されているソフトウェアは Windows Performance Recorder (WPR) とブラウザーのみです。</span><span class="sxs-lookup"><span data-stu-id="e2733-126">Ideally, the only running software will be Windows Performance Recorder (WPR) and the browser.</span></span>  

### <span data-ttu-id="e2733-127">2. Windows Performance Recorder (WPR) を起動し、オプションを選択する</span><span class="sxs-lookup"><span data-stu-id="e2733-127">2.  Launch Windows Performance Recorder (WPR) and select options</span></span>  

<span data-ttu-id="e2733-128">Windows Performance Recorder を起動し、[その他の **オプション] トグル** が展開されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-128">Launch the Windows Performance Recorder and ensure that **More options** toggle is expanded.</span></span>  <span data-ttu-id="e2733-129">エッジ ブラウザー *と* *HTML の応答性のシナリオ分析* のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2733-129">Select the *Edge Browser* and *HTML Responsiveness* scenario analysis checkboxes.</span></span>  

![Windows パフォーマンス レコードのオプション](./media/wprui-options.png)  

#### <span data-ttu-id="e2733-131">トレース収集のヒントとコツ</span><span class="sxs-lookup"><span data-stu-id="e2733-131">Tips and tricks for gathering traces</span></span>  

*   <span data-ttu-id="e2733-132">バックグラウンド アクティビティは最低限必要な状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-132">Try to keep background activity to an absolute required minimum.</span></span>  <span data-ttu-id="e2733-133">バックグラウンド プロセスでは、認識されるパフォーマンスと実際のパフォーマンス特性の両方が歪み、結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-133">Background processes may skew both perceived performance and actual performance characteristics and affect the results.</span></span>  <span data-ttu-id="e2733-134">ブラウザーと WPR の横に他の実行中のアプリケーションがないのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="e2733-134">Ideally there are no other running applications beside browser and WPR.</span></span>  
*   <span data-ttu-id="e2733-135">分析するシナリオを特定し、できるだけアトミックな状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="e2733-135">Identify the scenarios you're analyzing and try to keep them as atomic as possible.</span></span>  <span data-ttu-id="e2733-136">たとえば、ページの読み込み、スクロール、テーブル内の項目の選択時にサイトのパフォーマンスに問題がある場合は、次の 3 つのシナリオに問題を分け加えます。</span><span class="sxs-lookup"><span data-stu-id="e2733-136">For example, if your site has performance problems when loading the page, scrolling, and selecting something in a table, separate the issues into three scenarios:</span></span>  
    *   <span data-ttu-id="e2733-137">ページの読み込み (ナビゲーションの開始からページの読み込み完了まで)</span><span class="sxs-lookup"><span data-stu-id="e2733-137">Page load (from start of navigation to page load complete)</span></span>  
    *   <span data-ttu-id="e2733-138">Scroll</span><span class="sxs-lookup"><span data-stu-id="e2733-138">Scroll</span></span>  
    *   <span data-ttu-id="e2733-139">表で何かを選択する</span><span class="sxs-lookup"><span data-stu-id="e2733-139">Selecting something in the table</span></span>  
*   <span data-ttu-id="e2733-140">シナリオにサイトへの移動が含まれる場合は、シナリオを about:blank から開始してください。</span><span class="sxs-lookup"><span data-stu-id="e2733-140">If a scenario involves navigating to a site, consider beginning the scenario at about:blank.</span></span>  <span data-ttu-id="e2733-141">about:blank から開始すると、前のページのオーバーヘッドが回避されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-141">Starting at about:blank will avoid the overhead of the previous page.</span></span>  <span data-ttu-id="e2733-142">サイトから移動する必要がある場合は、about:blank に移動してシナリオを完了します。</span><span class="sxs-lookup"><span data-stu-id="e2733-142">If it involves navigating away from a site, navigate to about:blank to complete the scenario.</span></span>  <span data-ttu-id="e2733-143">これにより、調査中のサイト間の特定のやり取りが問題である場合を限り、他のサイトのノイズを追跡し続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-143">This will keep the noise of other sites out of the trace unless the specific interaction between sites is the issue under investigation.</span></span>  

### <span data-ttu-id="e2733-144">3. シナリオを記録する</span><span class="sxs-lookup"><span data-stu-id="e2733-144">3.  Record the scenario</span></span>  

<span data-ttu-id="e2733-145">[スタート **] をクリック** してレコーディングを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2733-145">Click **Start** to begin recording.</span></span>  <span data-ttu-id="e2733-146">ツールは、生成されたファイルのサイズを予測するために使用しているバッファーのサイズを報告します。</span><span class="sxs-lookup"><span data-stu-id="e2733-146">The tool will report the size of the buffer it is using to help you anticipate the size of the generated file.</span></span>  <span data-ttu-id="e2733-147">測定するユーザー シナリオを実行し、[保存]\*\*\*\* をクリックして記録を停止し、トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="e2733-147">Perform the user scenario you want to measure, then click **Save** to stop the recording and save the trace.</span></span>  <span data-ttu-id="e2733-148">シナリオが終了した直後に保存すると、トレース ファイルのサイズを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="e2733-148">Saving immediately after finishing your scenario will help minimize the size of the trace file.</span></span>  

![Windows パフォーマンス レコードの開始 - レコーディング](./media/wprui-recording.png)  

<span data-ttu-id="e2733-150">WPR ツールは、トレース情報が正常に保存されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="e2733-150">The WPR tool will indicate that your trace information was saved successfully:</span></span>  

![Windows パフォーマンス レコードの開始 - 保存完了](./media/wprui-savecomplete.png)  

## <span data-ttu-id="e2733-152">トレースの分析</span><span class="sxs-lookup"><span data-stu-id="e2733-152">Analyzing a trace</span></span>  

<span data-ttu-id="e2733-153">これで、パフォーマンス データを収集し、Windows Performance Analyzer を使用してトレースを分析し、どの最適化を行えるのかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-153">Now that you've gathered your performance data, you can analyze the trace using Windows Performance Analyzer to see what optimizations can be made.</span></span>  
<span data-ttu-id="e2733-154">Web シナリオのパフォーマンス データを分析する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2733-154">Here's how to analyze your web scenario performance data.</span></span>  

### <span data-ttu-id="e2733-155">1. Windows Performance Analyzer (WPA) を開く</span><span class="sxs-lookup"><span data-stu-id="e2733-155">1.  Open Windows Performance Analyzer (WPA)</span></span>  

<span data-ttu-id="e2733-156">Windows Performance Analyzer を起動し、分析するファイル `.etl` (ファイルを開\*\*\*\*  >  **く... ) を開きます**。</span><span class="sxs-lookup"><span data-stu-id="e2733-156">Launch Windows Performance Analyzer and open the `.etl` file to be analyzed (**File** > **Open...**).</span></span>  

### <span data-ttu-id="e2733-157">2. シンボルを読み込み *、HTML 分析プロファイルを適用* する</span><span class="sxs-lookup"><span data-stu-id="e2733-157">2.  Load symbols and apply the *HTML analysis* profile</span></span>  

> [!WARNING]
> <span data-ttu-id="e2733-158">シンボルを初めて読み込むには大量のダウンロードが必要で、一般的なインターネット接続ではかなりの時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2733-158">Loading symbols for the first time will require a large download and will take a significant amount of time on a typical internet connection.</span></span>  

<span data-ttu-id="e2733-159">メニューから [トレース読み込み**記号]** を選択  >  **して、シンボル**を読み込む。</span><span class="sxs-lookup"><span data-stu-id="e2733-159">Load your symbols by selecting **Trace** > **Load Symbols** from the menu.</span></span>  <span data-ttu-id="e2733-160">シンボルはディスクにキャッシュされ、今後のトレースではシンボルの読み込み速度がはるかに速くなります。</span><span class="sxs-lookup"><span data-stu-id="e2733-160">The symbols will be cached to disk and future traces will load symbols much faster.</span></span>  

<span data-ttu-id="e2733-161">Microsoft Edge と Web アプリのホストへの読み込みを制限することで、シンボルの読み込みを大幅に高速化できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-161">You can load symbols significantly faster by restricting the loading to Microsoft Edge and the web apps host.</span></span>  <span data-ttu-id="e2733-162">[**トレースの**  >  **構成シンボル] を選択**し、読み込**み設定のみを**制限 `MicrosoftEdgeCP.exe` します `WWAHost.exe` 。</span><span class="sxs-lookup"><span data-stu-id="e2733-162">Select **Trace** > **Configure Symbols** and restrict the **Load Settings** to only `MicrosoftEdgeCP.exe` and `WWAHost.exe`.</span></span>  

![シンボルの制限](./media/wpa-symbolrestrictions.png)  

<span data-ttu-id="e2733-164">シンボルの読み込みが開始された後 *、Html 分析プロファイル*(**プロファイル**  >  **が適用されます.**  > **カタログを参照します。**  > **HtmlResponsivenessAnalysis.wpaProfile**)</span><span class="sxs-lookup"><span data-stu-id="e2733-164">After symbols begin loading, apply the *Html Analysis Profile* (**Profiles** > **Apply...** > **Browse Catalog...** > **HtmlResponsivenessAnalysis.wpaProfile**)</span></span>  
<span data-ttu-id="e2733-165">プロファイルは、分析用に複数のグラフとテーブルを読み込む。</span><span class="sxs-lookup"><span data-stu-id="e2733-165">The profile will load several graphs and tables for your analysis.</span></span>  <span data-ttu-id="e2733-166">Web サイトの調査のほぼすべてについて、このプロファイルから開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2733-166">For nearly all website investigations, we recommend starting with this profile.</span></span>  

![大きな画像](./media/wpa-bigpicture.png)  

#### <span data-ttu-id="e2733-168">Html の応答性分析プロファイル</span><span class="sxs-lookup"><span data-stu-id="e2733-168">The Html Responsiveness Analysis Profile</span></span>  

<span data-ttu-id="e2733-169">*Html の応答性分析プロファイルには*、次の 4 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="e2733-169">The *Html Responsiveness* analysis profile provides four tabs:</span></span>  

<span data-ttu-id="e2733-170">**大きな** 画像 - これは、CPU アクティビティの予期しないソースが発生せず、ブラウザーが使用可能なすべてのリソースを実際に使用している場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2733-170">**Big Picture** - This is useful for confirming that there are no unexpected sources of CPU activity and the browser is indeed using all available resources.</span></span>  <span data-ttu-id="e2733-171">CPU 使用率を確認し、ブラウザー以外の CPU 使用率に大きく影響するプロセスがないか確認します。</span><span class="sxs-lookup"><span data-stu-id="e2733-171">Check your CPU usage and verify that no processes contribute significantly to CPU usage other than the browser.</span></span>  

<span data-ttu-id="e2733-172">**フレーム分析** - このセクションは基本的な分析に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-172">**Frame Analysis** - This section is used for basic analysis.</span></span>  <span data-ttu-id="e2733-173">CPU *使用率 (属性) グラフを使用* すると、CPU 使用率を担当するサブシステムを一目で把握できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-173">The *CPU Usage (Attributed)* graph enables a quick glance for understanding of the subsystems responsible for CPU usage.</span></span>  <span data-ttu-id="e2733-174">*HTML UI*スレッドの CPU 使用率 *(Sampled)* テーブルのサンプルを分析すると、重大なパフォーマンスのボトルネックを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2733-174">Breaking down the samples in the *CPU Usage (Sampled)* table on the *HTML UI Thread* is helpful for identifying critical performance bottlenecks.</span></span>  

<span data-ttu-id="e2733-175">**トレース マーカー** - このセクションには、コードを測定するための正確なポイントを提供する *msWriteProfilerMark*など、ブラウザー (Microsoft Edge) からのすべてのトレース マーカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-175">**Trace Markers** - This section shows all tracing markers coming from the browser (Microsoft Edge), including *msWriteProfilerMark*, which provides precise points for measuring code.</span></span>  <span data-ttu-id="e2733-176">*msWriteProfilerMark*トレースを表示するには、[Generic *Events]* グラフまでスクロール ダウンし、ドロップダウン メニューから**HTML msWriteProfilerMark**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2733-176">To see *msWriteProfilerMark* tracing, scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.</span></span>  

<span data-ttu-id="e2733-177">**スレッド遅延分析** - このタブは、Microsoft Edge 開発者が、あるスレッドがブロックされ、別のスレッドで待機している状況を調査するためによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-177">**Thread Delay Analysis** - This tab is often used by Microsoft Edge developers to investigate when one thread is blocked and waiting on another.</span></span>  <span data-ttu-id="e2733-178">まれに、Web 開発者にも役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-178">On rare occasions it might also be useful to web developers.</span></span>  

### <span data-ttu-id="e2733-179">3. ズームしてトレースの実行を削除する</span><span class="sxs-lookup"><span data-stu-id="e2733-179">3.  Zoom to remove trace rundown</span></span>  

<span data-ttu-id="e2733-180">グラフの末尾に空の *トレース実行* セクションを削除することで、分析に集中できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-180">You can focus your analysis by removing the empty trailing *Trace Rundown* sections of your graphs.</span></span>  <span data-ttu-id="e2733-181">現在表示されているグラフから:</span><span class="sxs-lookup"><span data-stu-id="e2733-181">From any of the graphs currently showing:</span></span>  
*   <span data-ttu-id="e2733-182">調査するグラフ データの開始時点で左クリック</span><span class="sxs-lookup"><span data-stu-id="e2733-182">Left-click at the start of the graph data you wish to investigate</span></span>  
*   <span data-ttu-id="e2733-183">長押し、ドラッグ アンド リリースして目的の領域を選択する</span><span class="sxs-lookup"><span data-stu-id="e2733-183">Hold, drag and release to select the desired region</span></span>  
*   <span data-ttu-id="e2733-184">右クリックして [ズーム] を選択 **する**</span><span class="sxs-lookup"><span data-stu-id="e2733-184">Right-click and select **Zoom**</span></span>  

<span data-ttu-id="e2733-185">ズームは、アクティブなタブのすべてのグラフとグラフに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2733-185">The zoom will apply to all graphs and charts on the active tab.</span></span>  

![ズーム後](./media/wpa-postzoom.png)  

### <span data-ttu-id="e2733-187">4. CPU サイクルを消費している原因を調査する</span><span class="sxs-lookup"><span data-stu-id="e2733-187">4.  Investigate what's taking up CPU cycles</span></span>  

 <span data-ttu-id="e2733-188">[**フレーム分析] タブの CPU** \*\*\*\* 使用率 (サンプリング) テーブルは、ほとんどの分析が発生する可能性が高い場所です。</span><span class="sxs-lookup"><span data-stu-id="e2733-188">The **CPU Usage (Sampled)** table in the **Frame Analysis** tab is where most of your analysis will likely happen.</span></span>  <span data-ttu-id="e2733-189">さまざまなプロセスを拡張して、最も計算負荷の高い JavaScript とブラウザー コードを特定できます。</span><span class="sxs-lookup"><span data-stu-id="e2733-189">You can expand the various processes to identify the most compute intensive JavaScript and browser code.</span></span>  <span data-ttu-id="e2733-190">多くの場合、1 ビットの JavaScript がパフォーマンスの問題を引き起こします。最適化に時間を取って大きな違いを生み出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2733-190">Often a single bit of JavaScript is responsible for a performance issue, and taking the time to optimize it can make a significant difference.</span></span>  

### <span data-ttu-id="e2733-191">5. 実行が遅い JavaScript コードを詳細に確認する</span><span class="sxs-lookup"><span data-stu-id="e2733-191">5.  Drill into any slow-running JavaScript code</span></span>  

<span data-ttu-id="e2733-192">DOM 呼び出しの下位分析は、シナリオ中に大部分の時間を占める JavaScript を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2733-192">Bottom up DOM call analysis can be useful for identifying the JavaScript responsible for taking up the majority of time during the scenario.</span></span>  <span data-ttu-id="e2733-193">これは、多くのトップ レベル呼び出しで同じ JavaScript ライブラリを再使用する場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e2733-193">This is especially helpful when many top level calls are re-using the same JavaScript libraries.</span></span>  

<span data-ttu-id="e2733-194">まず、プロセス、スレッド、アクティビティ、スタック別の CPU 使用率 *(サンプリング) の内訳を見て説明します*。</span><span class="sxs-lookup"><span data-stu-id="e2733-194">Start by looking at *CPU Usage (Sampled) Breakdown by Process, Thread, Activity, Stack*.</span></span>  <span data-ttu-id="e2733-195">スタック列の任意のセル **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e2733-195">Click on any cell in **Stack** column.</span></span>  <span data-ttu-id="e2733-196">Ctrl *+ F キーを押* し *、ExternalFunctionThunk を検索します*。</span><span class="sxs-lookup"><span data-stu-id="e2733-196">Press *Ctrl+F* and search for *ExternalFunctionThunk*.</span></span>  

> [!NOTE] 
> <span data-ttu-id="e2733-197">これは、シンボルが正常に読み込まれた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e2733-197">This only works if you have successfully loaded symbols.</span></span>  

![ExternalFunctionThunk の検索](./media/wpa-externalfunctionthunk.png)  

<span data-ttu-id="e2733-199">*ExternalFunctionThunk を使用して行を調査します*。</span><span class="sxs-lookup"><span data-stu-id="e2733-199">Investigate any lines with *ExternalFunctionThunk*.</span></span>  <span data-ttu-id="e2733-200">これは、Chakra JavaScript エンジンから Microsoft Edge エンジンへのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e2733-200">This is the interface from the Chakra JavaScript engine to the Microsoft Edge engine.</span></span>  <span data-ttu-id="e2733-201">コードがブラウザーから JavaScript の実行にブリッジされる場所を示します。</span><span class="sxs-lookup"><span data-stu-id="e2733-201">It shows where code bridges from the browser to JavaScript execution.</span></span>  <span data-ttu-id="e2733-202">行を右クリックし、[モジュールで呼び出し先を**表示**] を選択して、実行中のブラウザー エンジン関数の重み付けリスト  >  \*\*\*\* を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2733-202">Right-click on the line and select **View Callees** > **By Module** to see a weighted list of longest running browser engine functions.</span></span>  

![呼び出し者の表示](./media/wpa-viewcallees.png)  

<span data-ttu-id="e2733-204">特定の API を呼び出しているすべての JavaScript を特定するには\*\*\*\*、その API を右クリックして [関数別に呼び出し元を表示] を選択し、ツリーを展開して相対的な重みを表示および  >  \*\*\*\* 比較します。</span><span class="sxs-lookup"><span data-stu-id="e2733-204">To identify all the JavaScript calling a specific API, right-click on it and select **View Callers** > **By Function** and expand the tree to view and compare the relative weights.</span></span>  
