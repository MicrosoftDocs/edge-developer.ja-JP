---
ms.assetid: 7a5f9fd0-90a9-43db-b271-178c06da5896
description: F12 開発者ツールを使用して、web サイトの全般的なパフォーマンスを分析します。
title: パフォーマンスの分析
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/08/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: 7bf71744298502c9edf8ee1262fceff5640bedf1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570749"
---
# <span data-ttu-id="d6174-104">パフォーマンスの分析</span><span class="sxs-lookup"><span data-stu-id="d6174-104">Performance Analysis</span></span>

<span data-ttu-id="d6174-105">パフォーマンスを初めて使用する場合は、 [F12 DevTools のガイド](./devtools-guide.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6174-105">If you're new to performance, you should check out the [F12 DevTools guide](./devtools-guide.md).</span></span>
<span data-ttu-id="d6174-106">Microsoft Edge に組み込まれている[F12 ツール](./devtools-guide.md)を使って、web サイトの全般的なパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="d6174-106">The [F12 tools](./devtools-guide.md) built into Microsoft Edge can be used to analyze the general performance of a web site.</span></span> <span data-ttu-id="d6174-107">これにより、ブラウザー内で、 [Windows パフォーマンスツールキット](https://docs.microsoft.com/windows-hardware/test/wpt/index)の機能が (さらに制限されています) 機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-107">It provides similar (but more limited) capabilities to the [Windows Performance Toolkit](https://docs.microsoft.com/windows-hardware/test/wpt/index) from right within the browser.</span></span>



<span data-ttu-id="d6174-108">ブラウザーのパフォーマンスをさらに詳しく分析する場合は、Microsoft Edge チームは[Windows Performance Toolkit](https://docs.microsoft.com/windows-hardware/test/wpt/index) (WPT) を使います。</span><span class="sxs-lookup"><span data-stu-id="d6174-108">If you want a deeper analysis of browser performance, the Microsoft Edge team uses the [Windows Performance Toolkit](https://docs.microsoft.com/windows-hardware/test/wpt/index) (WPT).</span></span> <span data-ttu-id="d6174-109">WPT は、Windows チームによって作成され、詳細なプログラムパフォーマンス分析を実施しました。</span><span class="sxs-lookup"><span data-stu-id="d6174-109">WPT was created by the Windows team to conduct in-depth program performance analysis.</span></span> <span data-ttu-id="d6174-110">Web サイトの JavaScript と Microsoft Edge のネイティブコードの間の境界を straddles することで、同じツール内で両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d6174-110">It straddles the boundaries between website JavaScript and Microsoft Edge native code, allowing both to be viewed within the same tool.</span></span> <span data-ttu-id="d6174-111">WPT は、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6174-111">WPT can be used to:</span></span>
 - <span data-ttu-id="d6174-112">ソフトウェアが作業を完了するのに要した CPU 時間を測定する</span><span class="sxs-lookup"><span data-stu-id="d6174-112">Measure CPU time taken for software to complete work</span></span>
 - <span data-ttu-id="d6174-113">ソフトウェアによって割り当てられたメモリを計算する</span><span class="sxs-lookup"><span data-stu-id="d6174-113">Calculate the memory allocated by software</span></span>
 - <span data-ttu-id="d6174-114">リモートサーバーからのファイルのダウンロードの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="d6174-114">Show the details of downloading files from remote servers</span></span>
 - <span data-ttu-id="d6174-115">フレームレートを測定します。</span><span class="sxs-lookup"><span data-stu-id="d6174-115">Measure frame rate.</span></span>


<span data-ttu-id="d6174-116">Windows パフォーマンスツールキットを使って web サイトを分析する方法については、まず[windows 10 評価と展開キット (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)をダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6174-116">To get started with using the Windows Performance Toolkit to analyze your website, you'll first need to download the [Windows 10 Assessment and Deployment Kit (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="d6174-117">インストール中に*Windows パフォーマンスツールキット*オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d6174-117">Select the *Windows Performance Toolkit* option during installation:</span></span>

![ADK インストールオプション](./media/adk-installoptions.png)

<span data-ttu-id="d6174-119">ここでは、パフォーマンストレースを記録して分析する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6174-119">Here we'll cover how to record and analyze a performance trace.</span></span> <span data-ttu-id="d6174-120">Windows Performance Toolkit の詳細については、 [WPT のドキュメント](https://docs.microsoft.com/windows-hardware/test/wpt/index)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6174-120">To learn more about what's included in the Windows Performance Toolkit, check out the full [WPT documentation](https://docs.microsoft.com/windows-hardware/test/wpt/index).</span></span>

## <span data-ttu-id="d6174-121">トレースの記録</span><span class="sxs-lookup"><span data-stu-id="d6174-121">Recording a trace</span></span>
<span data-ttu-id="d6174-122">次に、ユーザーシナリオをセットアップして、Windows パフォーマンスレコーダーを使ってトレースを収集する準備をします。</span><span class="sxs-lookup"><span data-stu-id="d6174-122">Next, set up your user scenario and prepare to gather a trace using Windows Performance Recorder.</span></span>
<span data-ttu-id="d6174-123">ここでは、 *Windows パフォーマンスレコーダー (WPR)* を使って web シナリオのプロファイリングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6174-123">Here's how to profile your web scenario with the *Windows Performance Recorder (WPR)*.</span></span>

### <span data-ttu-id="d6174-124">1. パフォーマンス追跡を収集するための環境の準備</span><span class="sxs-lookup"><span data-stu-id="d6174-124">1. Prepare your environment to gather a performance trace</span></span>
<span data-ttu-id="d6174-125">記録しようとしているトレースのノイズを回避するため、できるだけ多くの実行プログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="d6174-125">Shut down as many running programs as possible to avoid noise in the trace that you're about to record.</span></span> <span data-ttu-id="d6174-126">理想的には、実行されている唯一のソフトウェアが Windows Performance レコーダー (WPR) とブラウザーです。</span><span class="sxs-lookup"><span data-stu-id="d6174-126">Ideally, the only running software will be Windows Performance Recorder (WPR) and the browser.</span></span>

### <span data-ttu-id="d6174-127">2. Windows パフォーマンスレコーダー (WPR) を起動し、オプションを選択する</span><span class="sxs-lookup"><span data-stu-id="d6174-127">2. Launch Windows Performance Recorder (WPR) and select options</span></span>
<span data-ttu-id="d6174-128">Windows パフォーマンスレコーダーを起動し、[**その他のオプション]** トグルが展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6174-128">Launch the Windows Performance Recorder and ensure that **More options** toggle is expanded.</span></span> <span data-ttu-id="d6174-129">[ *Edge Browser* ] および [ *HTML 応答性*のシナリオ分析] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d6174-129">Select the *Edge Browser* and *HTML Responsiveness* scenario analysis checkboxes.</span></span>

![Windows のパフォーマンスレコードのオプション](./media/wprui-options.png)

#### <span data-ttu-id="d6174-131">トレースを収集するためのヒント</span><span class="sxs-lookup"><span data-stu-id="d6174-131">Tips and tricks for gathering traces</span></span>
- <span data-ttu-id="d6174-132">バックグラウンドアクティビティを絶対に必要最小限に抑えてください。</span><span class="sxs-lookup"><span data-stu-id="d6174-132">Try to keep background activity to an absolute required minimum.</span></span> <span data-ttu-id="d6174-133">バックグラウンドプロセスは、体感されているパフォーマンスと実際のパフォーマンスの特性の両方をスキューし、結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6174-133">Background processes may skew both perceived performance and actual performance characteristics and affect the results.</span></span> <span data-ttu-id="d6174-134">ブラウザーと WPR の間に他のアプリケーションが実行されていないことが理想的です。</span><span class="sxs-lookup"><span data-stu-id="d6174-134">Ideally there are no other running applications beside browser and WPR.</span></span>
- <span data-ttu-id="d6174-135">分析するシナリオを特定し、できるだけアトミックな状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="d6174-135">Identify the scenarios you're analyzing and try to keep them as atomic as possible.</span></span> <span data-ttu-id="d6174-136">たとえば、ページの読み込み時にパフォーマンスの問題が発生したり、表内の何かを選択したりすると、問題が次の3つのシナリオに分類されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-136">For example, if your site has performance problems when loading the page, scrolling, and selecting something in a table, separate the issues into three scenarios:</span></span>
  - <span data-ttu-id="d6174-137">ページの読み込み (ナビゲーションの最初からページの読み込み完了まで)</span><span class="sxs-lookup"><span data-stu-id="d6174-137">Page load (from start of navigation to page load complete)</span></span>
  - <span data-ttu-id="d6174-138">Scroll</span><span class="sxs-lookup"><span data-stu-id="d6174-138">Scroll</span></span>
  - <span data-ttu-id="d6174-139">表の内容を選択する</span><span class="sxs-lookup"><span data-stu-id="d6174-139">Selecting something in the table</span></span>
- <span data-ttu-id="d6174-140">シナリオによってサイトへの移動が必要な場合は、[詳細情報] からシナリオを開始することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d6174-140">If a scenario involves navigating to a site, consider beginning the scenario at about:blank.</span></span> <span data-ttu-id="d6174-141">[About: blank] から開始すると、前のページのオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="d6174-141">Starting at about:blank will avoid the overhead of the previous page.</span></span> <span data-ttu-id="d6174-142">サイトから移動する必要がある場合は、[about: blank] に移動してシナリオを完了します。</span><span class="sxs-lookup"><span data-stu-id="d6174-142">If it involves navigating away from a site, navigate to about:blank to complete the scenario.</span></span> <span data-ttu-id="d6174-143">これにより、サイト間の特定の操作が調査の問題である場合を除いて、他のサイトのトレースが不要になります。</span><span class="sxs-lookup"><span data-stu-id="d6174-143">This will keep the noise of other sites out of the trace unless the specific interaction between sites is the issue under investigation.</span></span>

### <span data-ttu-id="d6174-144">3. シナリオを記録する</span><span class="sxs-lookup"><span data-stu-id="d6174-144">3. Record the scenario</span></span>
<span data-ttu-id="d6174-145">[**開始**] をクリックして録音を開始します。</span><span class="sxs-lookup"><span data-stu-id="d6174-145">Click **Start** to begin recording.</span></span> <span data-ttu-id="d6174-146">このツールは、生成されたファイルのサイズを予測するのに役立つように、使用しているバッファーのサイズを報告します。</span><span class="sxs-lookup"><span data-stu-id="d6174-146">The tool will report the size of the buffer it is using to help you anticipate the size of the generated file.</span></span> <span data-ttu-id="d6174-147">測定するユーザーシナリオを実行し、[**保存**] をクリックして記録を停止し、トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="d6174-147">Perform the user scenario you want to measure, then click **Save** to stop the recording and save the trace.</span></span> <span data-ttu-id="d6174-148">シナリオを終了した直後に保存することで、トレースファイルのサイズを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-148">Saving immediately after finishing your scenario will help minimize the size of the trace file.</span></span>

![Windows パフォーマンスレコードの開始](./media/wprui-recording.png)

<span data-ttu-id="d6174-150">WPR ツールは、トレース情報が正常に保存されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="d6174-150">The WPR tool will indicate that your trace information was saved successfully:</span></span>

![Windows パフォーマンスレコードの開始](./media/wprui-savecomplete.png)


## <span data-ttu-id="d6174-152">トレースの分析</span><span class="sxs-lookup"><span data-stu-id="d6174-152">Analyzing a trace</span></span>
<span data-ttu-id="d6174-153">パフォーマンスデータを収集したので、Windows Performance Analyzer を使ってトレースを分析し、最適化できることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-153">Now that you've gathered your performance data, you can analyze the trace using Windows Performance Analyzer to see what optimizations can be made.</span></span>
<span data-ttu-id="d6174-154">ここでは、web シナリオのパフォーマンスデータを分析する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6174-154">Here's how to analyze your web scenario performance data.</span></span>

### <span data-ttu-id="d6174-155">1. Windows Performance Analyzer (WPA) を開く</span><span class="sxs-lookup"><span data-stu-id="d6174-155">1. Open Windows Performance Analyzer (WPA)</span></span>
<span data-ttu-id="d6174-156">Windows Performance Analyzer を起動して、分析するファイルを開きます `.etl` (**File**  >  **[** ファイル])。</span><span class="sxs-lookup"><span data-stu-id="d6174-156">Launch Windows Performance Analyzer and open the `.etl` file to be analyzed (**File** > **Open...**).</span></span>

### <span data-ttu-id="d6174-157">2. シンボルを読み込み、 *HTML 分析*プロファイルを適用する</span><span class="sxs-lookup"><span data-stu-id="d6174-157">2. Load symbols and apply the *HTML analysis* profile</span></span>

>[!WARNING]
> <span data-ttu-id="d6174-158">シンボルを初めて読み込むときには、大規模なダウンロードが必要となり、通常のインターネット接続ではかなりの時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="d6174-158">Loading symbols for the first time will require a large download and will take a significant amount of time on a typical internet connection.</span></span>

<span data-ttu-id="d6174-159">メニューから [**トレース**  >  ] [**シンボルの読み込み**] を選択して、シンボルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d6174-159">Load your symbols by selecting **Trace** > **Load Symbols** from the menu.</span></span> <span data-ttu-id="d6174-160">シンボルはディスクにキャッシュされ、将来のトレースではシンボルの読み込みが大幅に高速化されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-160">The symbols will be cached to disk and future traces will load symbols much faster.</span></span>

<span data-ttu-id="d6174-161">Microsoft Edge と web apps ホストへの読み込みを制限することで、シンボルを大幅に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-161">You can load symbols significantly faster by restricting the loading to Microsoft Edge and the web apps host.</span></span> <span data-ttu-id="d6174-162">[**トレース**の設定] を選択し  >  **Configure Symbols** 、[**読み込みの設定**] のみを [] に制限し `MicrosoftEdgeCP.exe` `WWAHost.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="d6174-162">Select **Trace** > **Configure Symbols** and restrict the **Load Settings** to only `MicrosoftEdgeCP.exe` and `WWAHost.exe`.</span></span>

![記号の制限](./media/wpa-symbolrestrictions.png)

<span data-ttu-id="d6174-164">記号の読み込みが開始されたら、 *Html 分析プロファイル*を適用します (**プロファイル**が適用されます..  >  **.**  > **カタログを参照...**  > **HtmlResponsivenessAnalysis プロファイル**は、分析用にいくつかのグラフとテーブルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d6174-164">After symbols begin loading, apply the *Html Analysis Profile* (**Profiles** > **Apply...** > **Browse Catalog...** > **HtmlResponsivenessAnalysis.wpaProfile**) The profile will load several graphs and tables for your analysis.</span></span> <span data-ttu-id="d6174-165">ほぼすべての web サイトの調査で、このプロフィールから始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6174-165">For nearly all website investigations, we recommend starting with this profile.</span></span>

![全体像](./media/wpa-bigpicture.png)


#### <span data-ttu-id="d6174-167">Html 応答解析プロファイル</span><span class="sxs-lookup"><span data-stu-id="d6174-167">The Html Responsiveness Analysis Profile</span></span>
<span data-ttu-id="d6174-168">*Html 応答*解析プロファイルには、次の4つのタブが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d6174-168">The *Html Responsiveness* analysis profile provides four tabs:</span></span>

<span data-ttu-id="d6174-169">**大きな画像**-これは、CPU アクティビティの予期しないソースがなく、ブラウザーが利用可能なすべてのリソースを実際に使用していることを確認するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6174-169">**Big Picture** - This is useful for confirming that there are no unexpected sources of CPU activity and the browser is indeed using all available resources.</span></span> <span data-ttu-id="d6174-170">CPU 使用量を確認して、ブラウザー以外の CPU 使用量に対して大幅に影響するプロセスがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6174-170">Check your CPU usage and verify that no processes contribute significantly to CPU usage other than the browser.</span></span>

<span data-ttu-id="d6174-171">**フレームの分析**-このセクションは基本的な分析に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-171">**Frame Analysis** - This section is used for basic analysis.</span></span> <span data-ttu-id="d6174-172">[ *Cpu 使用量]* グラフでは、cpu 使用量を把握するサブシステムについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="d6174-172">The *CPU Usage (Attributed)* graph enables a quick glance for understanding of the subsystems responsible for CPU usage.</span></span> <span data-ttu-id="d6174-173">*HTML UI スレッド*の*CPU 使用率 (サンプリング)* テーブルでサンプルを分解すると、重大なパフォーマンスのボトルネックを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6174-173">Breaking down the samples in the *CPU Usage (Sampled)* table on the *HTML UI Thread* is helpful for identifying critical performance bottlenecks.</span></span>

<span data-ttu-id="d6174-174">**トレースマーカー** -このセクションには、ブラウザー (Microsoft Edge) からのすべてのトレースマーカーが表示されます。これにより、 *msWriteProfilerMark*が含まれます。これにより、コードの正確な測定方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-174">**Trace Markers** - This section shows all tracing markers coming from the browser (Microsoft Edge), including *msWriteProfilerMark*, which provides precise points for measuring code.</span></span> <span data-ttu-id="d6174-175">*MsWriteProfilerMark*トレースを表示するには、[*汎用イベント*] グラフまで下にスクロールして、ドロップダウンメニューから [ **HTML msWriteProfilerMark** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d6174-175">To see *msWriteProfilerMark* tracing, scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.</span></span>

<span data-ttu-id="d6174-176">**スレッド遅延分析**-このタブは、あるスレッドがブロックされ、別のスレッドが待機しているときに、Microsoft Edge 開発者によって調査されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d6174-176">**Thread Delay Analysis** - This tab is often used by Microsoft Edge developers to investigate when one thread is blocked and waiting on another.</span></span> <span data-ttu-id="d6174-177">まれに、web 開発者にとっても便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6174-177">On rare occasions it might also be useful to web developers.</span></span>


### <span data-ttu-id="d6174-178">3. トレースの停止を削除するためのズームダウン</span><span class="sxs-lookup"><span data-stu-id="d6174-178">3. Zoom to remove trace rundown</span></span>
<span data-ttu-id="d6174-179">グラフの空の末尾の*トレースダウン*セクションを削除することで、分析に焦点を合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-179">You can focus your analysis by removing the empty trailing *Trace Rundown* sections of your graphs.</span></span> <span data-ttu-id="d6174-180">現在表示されているグラフから:</span><span class="sxs-lookup"><span data-stu-id="d6174-180">From any of the graphs currently showing:</span></span>
 - <span data-ttu-id="d6174-181">調べるグラフデータの先頭を左クリックします。</span><span class="sxs-lookup"><span data-stu-id="d6174-181">Left-click at the start of the graph data you wish to investigate</span></span>
 - <span data-ttu-id="d6174-182">ホールドし、ドラッグして解放し、目的の地域を選びます。</span><span class="sxs-lookup"><span data-stu-id="d6174-182">Hold, drag and release to select the desired region</span></span>
 - <span data-ttu-id="d6174-183">右クリックして、[**ズーム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6174-183">Right-click and select **Zoom**</span></span>

<span data-ttu-id="d6174-184">ズームは、アクティブなタブ上のすべてのグラフとグラフに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-184">The zoom will apply to all graphs and charts on the active tab.</span></span>

![ズーム後](./media/wpa-postzoom.png)


### <span data-ttu-id="d6174-186">4. CPU サイクルの消費を調査する</span><span class="sxs-lookup"><span data-stu-id="d6174-186">4. Investigate what's taking up CPU cycles</span></span>
 <span data-ttu-id="d6174-187">[**フレーム分析**] タブの [ **CPU 使用率 (サンプリング)** ] テーブルには、ほとんどの分析が行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6174-187">The **CPU Usage (Sampled)** table in the **Frame Analysis** tab is where most of your analysis will likely happen.</span></span> <span data-ttu-id="d6174-188">さまざまなプロセスを展開して、最も負荷の高い JavaScript とブラウザーコードを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-188">You can expand the various processes to identify the most compute intensive JavaScript and browser code.</span></span> <span data-ttu-id="d6174-189">多くの場合、JavaScript の1ビットはパフォーマンスの問題に対応しており、そのために時間をかけて最適化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d6174-189">Often a single bit of JavaScript is responsible for a performance issue, and taking the time to optimize it can make a significant difference.</span></span>

### <span data-ttu-id="d6174-190">5. 実行速度が遅い JavaScript コードを詳しく調べる</span><span class="sxs-lookup"><span data-stu-id="d6174-190">5. Drill into any slow-running JavaScript code</span></span>
<span data-ttu-id="d6174-191">ボトムアップ DOM 呼び出しの分析は、シナリオ中に多くの時間を取る JavaScript を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6174-191">Bottom up DOM call analysis can be useful for identifying the JavaScript responsible for taking up the majority of time during the scenario.</span></span> <span data-ttu-id="d6174-192">これは、多くのトップレベルの呼び出しが同じ JavaScript ライブラリを再利用する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="d6174-192">This is especially helpful when many top level calls are re-using the same JavaScript libraries.</span></span>

<span data-ttu-id="d6174-193">まず *、プロセス、スレッド、アクティビティ、スタックで CPU 使用率 (サンプリング*された) の内訳を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="d6174-193">Start by looking at *CPU Usage (Sampled) Breakdown by Process, Thread, Activity, Stack*.</span></span> <span data-ttu-id="d6174-194">[**スタック**] 列の任意のセルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6174-194">Click on any cell in **Stack** column.</span></span> <span data-ttu-id="d6174-195">Ctrl キーを押し*ながら F*キーを押し、 *externalfunctionthunk*を検索します。</span><span class="sxs-lookup"><span data-stu-id="d6174-195">Press *Ctrl+F* and search for *ExternalFunctionThunk*.</span></span>

>[!NOTE] 
><span data-ttu-id="d6174-196">この操作は、正常にシンボルが読み込まれている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d6174-196">This only works if you have successfully loaded symbols.</span></span>

![ExternalFunctionThunk を検索する](./media/wpa-externalfunctionthunk.png)

<span data-ttu-id="d6174-198">*Externalfunctionthunk*を使って、任意の行を調査します。</span><span class="sxs-lookup"><span data-stu-id="d6174-198">Investigate any lines with *ExternalFunctionThunk*.</span></span> <span data-ttu-id="d6174-199">これは、Chakra JavaScript エンジンから Microsoft Edge エンジンへのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d6174-199">This is the interface from the Chakra JavaScript engine to the Microsoft Edge engine.</span></span> <span data-ttu-id="d6174-200">ブラウザーから JavaScript 実行へのコードブリッジの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="d6174-200">It shows where code bridges from the browser to JavaScript execution.</span></span> <span data-ttu-id="d6174-201">線を右クリックして、[**呼び出し**先の一覧を表示] を選択すると、実行時間が  >  **By Module**長いブラウザーエンジン関数の加重リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6174-201">Right-click on the line and select **View Callees** > **By Module** to see a weighted list of longest running browser engine functions.</span></span>

![呼び出し先の表示](./media/wpa-viewcallees.png)

<span data-ttu-id="d6174-203">特定の API を呼び出すすべての JavaScript を特定するには、その API を右クリックし、[関数別の**呼び出し元の表示**] を選択して、  >  **By Function**相対的な重みを表示して比較します。</span><span class="sxs-lookup"><span data-stu-id="d6174-203">To identify all the JavaScript calling a specific API, right-click on it and select **View Callers** > **By Function** and expand the tree to view and compare the relative weights.</span></span>
