---
description: コンソールにメッセージを記録する方法について説明します。
title: コンソールでのメッセージのログ記録の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2f91f1847bf5469e8106edc21553172fc06db9ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231112"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="c8b29-104">コンソールでのメッセージのログ記録の開始</span><span class="sxs-lookup"><span data-stu-id="c8b29-104">Get Started With Logging Messages In The Console</span></span>  

<span data-ttu-id="c8b29-105">この対話型のチュートリアルでは、Microsoft Edge DevTools コンソールでメッセージをログに記録して [フィルター処理する方法を示][MicrosoftEdgeDevTools] します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-105">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="コンソール内のメッセージ" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="c8b29-107">コンソール内の **メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c8b29-107">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="c8b29-108">このチュートリアルは、順番に完了することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="c8b29-108">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="c8b29-109">JavaScript を使用してページに対話機能を追加する方法など、Web 開発の基本を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-109">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="c8b29-110">デモと DevTools をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c8b29-110">Set up the demo and DevTools</span></span>  

<span data-ttu-id="c8b29-111">このチュートリアルは、デモを開いて、すべてのワークフローを自分で試しに行くことができる設計です。</span><span class="sxs-lookup"><span data-stu-id="c8b29-111">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="c8b29-112">物理的に作業を行う場合は、後でワークフローを思い出す可能性が高い。</span><span class="sxs-lookup"><span data-stu-id="c8b29-112">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="c8b29-113">`Control`\(Windows, Linux\) または \(macOS\) を保持し、[コンソール ログの例] を選択して新しい `Command` タブで開きます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8b29-113">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="c8b29-114">コンソール ログの例</span><span class="sxs-lookup"><span data-stu-id="c8b29-114">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="c8b29-115">デモにフォーカスを移動し `Control` + `Shift` + `J` 、\(Windows、Linux\) または `Command` + `Option` + `J` \(macOS\) を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-115">Focus the demo and then select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="c8b29-116">既定では、DevTools はデモの右側に開きます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-116">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="デモの右側に DevTools が開きます" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="c8b29-118">デモの右側に DevTools が開きます</span><span class="sxs-lookup"><span data-stu-id="c8b29-118">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="c8b29-119">[DevTools をウィンドウの下部にドッキングします][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="c8b29-119">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="デモの下部にドッキングされた DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="c8b29-121">デモの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="c8b29-121">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="c8b29-122">[DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="c8b29-122">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="別ウィンドウのブラウザー" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="c8b29-124">別ウィンドウのブラウザー</span><span class="sxs-lookup"><span data-stu-id="c8b29-124">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="c8b29-125">[DevTools を別のウィンドウにドッキング解除します][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="c8b29-125">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="DevTools が別のウィンドウでドッキング解除されている" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="c8b29-127">DevTools が別のウィンドウでドッキング解除されている</span><span class="sxs-lookup"><span data-stu-id="c8b29-127">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="c8b29-128">JavaScript からログに記録されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c8b29-128">View messages logged from JavaScript</span></span>  

<span data-ttu-id="c8b29-129">コンソールに表示されるほとんどのメッセージは **、ページ** の JavaScript を作成した Web 開発者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="c8b29-129">Most messages that are displayed in the **Console** come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="c8b29-130">このセクションの目的は、コンソールで確認する可能性が高いさまざまなメッセージの種類を紹介し、それぞれの\*\*\*\* メッセージの種類を自分の JavaScript から自分で記録する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-130">The goal of this section is to introduce you to the different message types that you are likely to review in the **Console**, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="c8b29-131">デモの **[ログ情報]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-131">Choose the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="c8b29-132">がコンソールに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-132">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="[ログ情報] を選択した後のコンソール" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="c8b29-134">[ **ログ情報** ] を選択した **後のコンソール**</span><span class="sxs-lookup"><span data-stu-id="c8b29-134">The **Console** after you choose **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-135">コンソールのメッセージ `Hello, Console!` の横にある \*\* [log.js:2 ] を選択します\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8b29-135">Next to the `Hello, Console!` message in the Console choose **log.js:2**.</span></span>  <span data-ttu-id="c8b29-136">[ソース] パネルが開き、メッセージがコンソールに記録される原因となるコード行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-136">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="c8b29-137">メッセージは、ページの JavaScript が実行された際にログに記録されます `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-137">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="DevTools は、次の操作を選択した後、[ソース] log.js開きます。" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="c8b29-139">DevTools は、選択 **した後に [ソース** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-139">DevTools opens the **Sources** panel after you choose</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-140">次のワークフローを **使用して** 、コンソールに戻る。</span><span class="sxs-lookup"><span data-stu-id="c8b29-140">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="c8b29-141">[コンソール] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-141">Choose the **Console** tab.</span></span>  
    *   <span data-ttu-id="c8b29-142">コンソール `Control` + `[` パネルにフォーカスが置かれるまで `Command` + `[` \(Windows,Linux\) または \(macOS\) を選択します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8b29-142">Select `Control`+`[` \(Windows, Linux\) or `Command`+`[` \(macOS\) until the **Console** panel is in focus.</span></span>  
    *   <span data-ttu-id="c8b29-143">[コマンド メニューを開き、「][DevToolsCommandMenu]コンソール パネルの表示」コマンドを入力して、次 `Console` に選択\*\*\*\* します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-143">[Open the Command Menu][DevToolsCommandMenu], type `Console`, choose the **Show Console Panel** command, and then select `Enter`.</span></span>  
    
1.  <span data-ttu-id="c8b29-144">デモで **[警告のログ** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-144">Choose the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="c8b29-145">コンソールに記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-145">gets logged to the **Console**.</span></span>  <span data-ttu-id="c8b29-146">このような形式のメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="c8b29-146">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="[警告のログ] を選択した後のコンソール" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="c8b29-148">[ **警告のログ** ] を選択 **した後のコンソール**</span><span class="sxs-lookup"><span data-stu-id="c8b29-148">The **Console** after you choose **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="c8b29-149">メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト `log.js:12` \(\など) を選択して、メッセージが書式設定される原因となったコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-149">If you want to display the code that caused a message to get logged a certain way, choose on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="c8b29-150">Choose the **Expand** \( ![ Expand ][ImageExpandIcon] \) icon in front of `Abandon Hope All Ye Who Enter` .</span><span class="sxs-lookup"><span data-stu-id="c8b29-150">Choose the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="c8b29-151">DevTools は、呼 [び出しに至る][WikiStackTrace] スタック トレースを示します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-151">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="スタック トレース" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="c8b29-153">スタック トレース</span><span class="sxs-lookup"><span data-stu-id="c8b29-153">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="c8b29-154">スタック トレースは、名前付きの関数が実行され、その関数が実行 `logWarning` されたことを示しています `quoteDante` 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-154">The stack trace is telling you that a function named `logWarning` is run, which in turn runs a function named `quoteDante`.</span></span>  <span data-ttu-id="c8b29-155">つまり、最初に発生した要求はスタック トレースの一番下になります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-155">In other words, the request that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="c8b29-156">スタック トレースは、実行中にいつでも記録できます `console.trace()` 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-156">You may log stack traces at any time by running `console.trace()`.</span></span>  

1.  <span data-ttu-id="c8b29-157">[ログ **エラー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-157">Choose **Log Error**.</span></span>  <span data-ttu-id="c8b29-158">次のエラー メッセージがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-158">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="エラー メッセージ" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="c8b29-160">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="c8b29-160">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-161">[ログ **テーブル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-161">Choose **Log Table**.</span></span>  <span data-ttu-id="c8b29-162">アーティストに関するテーブルがコンソールに記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-162">A table about famous artists gets logged to the **Console**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c8b29-163">列 `birthday` には、1 行分のみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-163">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="c8b29-164">その理由を判断するには、コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-164">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="コンソール内のテーブル" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="c8b29-166">コンソール内の **テーブル**</span><span class="sxs-lookup"><span data-stu-id="c8b29-166">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-167">[ログ **グループ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-167">Choose **Log Group**.</span></span>  <span data-ttu-id="c8b29-168">4 つの犯罪に対する暴力的な部下の名前がラベルの下にグループ化 `Adolescent Irradiated Espionage Tortoises` されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-168">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="コンソール内のメッセージのグループ" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="c8b29-170">コンソール内のメッセージの **グループ**</span><span class="sxs-lookup"><span data-stu-id="c8b29-170">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-171">Choose **Log Custom**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-171">Choose **Log Custom**.</span></span>  <span data-ttu-id="c8b29-172">赤い枠線と青い背景のメッセージがコンソールに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-172">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="コンソール内のカスタム書式設定を含むメッセージ" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="c8b29-174">コンソール内のカスタム書式設定を含む **メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c8b29-174">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="c8b29-175">ここでの主な考え方は、JavaScript からコンソールにメッセージを記録する場合は、メソッドの 1 つを `console` 使用するという考え方です。</span><span class="sxs-lookup"><span data-stu-id="c8b29-175">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="c8b29-176">各メソッドは、メッセージの書式を異なります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-176">Each method formats messages differently.</span></span>  

<span data-ttu-id="c8b29-177">このセクションで説明したメソッドよりも多くのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-177">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="c8b29-178">このチュートリアルでは、残りのメソッドを参照する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-178">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="c8b29-179">ブラウザーによってログに記録されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="c8b29-179">View messages logged by the browser</span></span>  

<span data-ttu-id="c8b29-180">ブラウザーもコンソールにメッセージをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-180">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="c8b29-181">これは通常、ページに問題がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-181">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="c8b29-182">Choose **Cause 404**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-182">Choose **Cause 404**.</span></span>  <span data-ttu-id="c8b29-183">ページの JavaScript が存在しないファイルをフェッチしようとしたため、ブラウザーはネットワーク エラーの HTTP 状態コード `404` をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-183">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="コンソールの 404 エラー" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="c8b29-185">コンソール `404` の **エラー**</span><span class="sxs-lookup"><span data-stu-id="c8b29-185">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-186">Choose **Cause Error**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-186">Choose **Cause Error**.</span></span>  <span data-ttu-id="c8b29-187">JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーはキャッチされていないログ `TypeError` を記録します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-187">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="コンソールの TypeError" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="c8b29-189">コンソール `TypeError` 内の\*\*\*\* A</span><span class="sxs-lookup"><span data-stu-id="c8b29-189">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-190">[ログ **レベル] ドロップダウンを** 選択し、無効になっている場合は [ **詳細** ] オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c8b29-190">Choose the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="c8b29-191">フィルター処理の詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b29-191">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="c8b29-192">これを行って、ログに記録する次のメッセージが表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-192">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c8b29-193">[既定のレベル] ドロップダウンが無効になっている場合は、コンソール サイドバーを閉じる **必要があります** 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-193">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="c8b29-194">コンソール サイドバーの詳細については、以下のメッセージ ソースで **フィルター** 処理します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-194">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="詳細ログ レベルの有効化" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="c8b29-196">詳細ログ レベルの有効化</span><span class="sxs-lookup"><span data-stu-id="c8b29-196">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-197">Choose **Cause Violation**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-197">Choose **Cause Violation**.</span></span>  <span data-ttu-id="c8b29-198">ページが数秒応答しなくなると、ブラウザーはメッセージをコンソール `[Violation] 'click' handler took 3000ms` に記録します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-198">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="c8b29-199">正確な期間は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-199">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="コンソールでの違反" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="c8b29-201">コンソールでの違反\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8b29-201">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c8b29-202">メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-202">Filter messages</span></span>  

<span data-ttu-id="c8b29-203">一部の Web ページでは、コンソールに **メッセージ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-203">On some webpages you review the **Console** get flooded with messages.</span></span>  <span data-ttu-id="c8b29-204">DevTools には、該当するタスクに関係ないメッセージをフィルター処理するさまざまな方法が提供されています。</span><span class="sxs-lookup"><span data-stu-id="c8b29-204">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="c8b29-205">ログ レベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-205">Filter by log level</span></span>  

<span data-ttu-id="c8b29-206">各 `console` メソッドには、次の重大度レベルが `Verbose` 割 `Info` り当 `Warning` てられます `Error` 。</span><span class="sxs-lookup"><span data-stu-id="c8b29-206">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="c8b29-207">たとえば、 `console.log()` レベルレベルの `Info` メッセージはレベルレベルのメッセージ `console.error()` `Error` ですが、レベルの高いメッセージです。</span><span class="sxs-lookup"><span data-stu-id="c8b29-207">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="c8b29-208">[ログ レベル **] ドロップダウンを選択し** 、[エラー] を **無効にします**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-208">Choose the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="c8b29-209">レベルの横にチェック マークが表示されなくなった場合、レベルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-209">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="c8b29-210">レベル `Error` のメッセージは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-210">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="コンソールでエラー レベルのメッセージを無効にする" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="c8b29-212">コンソールでエラー レベルのメッセージを無効 **にする**</span><span class="sxs-lookup"><span data-stu-id="c8b29-212">Disable Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-213">[ログ レベル **] ドロップダウンを** 再び選択し、エラーを再度 **有効にしてください**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-213">Choose the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="c8b29-214">レベル `Error` のメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-214">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="c8b29-215">テキストでフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c8b29-215">Filter by text</span></span>  

<span data-ttu-id="c8b29-216">正確な文字列を含むメッセージのみを表示する場合は、その文字列を [フィルター] テキスト ボックス **に** 入力します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-216">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="c8b29-217">`Dave` を **フィルター処理** テキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-217">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="c8b29-218">文字列を含めないメッセージはすべて `Dave` 非表示になります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-218">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="c8b29-219">ラベルを確認 `Adolescent Irradiated Espionage Tortoises` する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-219">You may also review the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="c8b29-220">これはバグです。</span><span class="sxs-lookup"><span data-stu-id="c8b29-220">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Dave を含めないメッセージをフィルター処理する" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="c8b29-222">含めないメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-222">Filter out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-223">[ `Dave` フィルター] **テキスト ボックスから** 削除します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-223">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="c8b29-224">すべてのメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-224">All the messages reappear.</span></span>  

### <span data-ttu-id="c8b29-225">正規表現によるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c8b29-225">Filter by regular expression</span></span>  

<span data-ttu-id="c8b29-226">特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、正規表現を [使用します][MDNRegularExpressions]。</span><span class="sxs-lookup"><span data-stu-id="c8b29-226">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="c8b29-227">`/^[AH]/` を **フィルター処理** テキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-227">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="c8b29-228">このパターンを [RegExr に入力][|::ref1::|Main] して、実行内容を説明します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-228">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="パターンに一致しないメッセージをフィルター処理する" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="c8b29-230">パターンに一致しないメッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-230">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-231">[ `/^[AH]/` フィルター] **テキスト ボックスから** 削除します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-231">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="c8b29-232">すべてのメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-232">All messages are visible again.</span></span>  

### <span data-ttu-id="c8b29-233">メッセージ ソースでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-233">Filter by message source</span></span>  

<span data-ttu-id="c8b29-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-234">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="c8b29-235">Choose **Show Console Sidebar** \( Show Console Sidebar ![ ][ImageShowConsoleSidebarIcon] \).</span><span class="sxs-lookup"><span data-stu-id="c8b29-235">Choose **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="サイドバー" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="c8b29-237">サイドバー</span><span class="sxs-lookup"><span data-stu-id="c8b29-237">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-238">Choose the **Expand** \( ![ Expand ][ImageExpandIcon] \) icon next to the number of messages.</span><span class="sxs-lookup"><span data-stu-id="c8b29-238">Choose the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="c8b29-239">次の図では、メッセージの数は **13**メッセージとして示されています。</span><span class="sxs-lookup"><span data-stu-id="c8b29-239">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="c8b29-240">サイドバー **には** 、メッセージのログ記録の原因となる URL の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-240">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="c8b29-241">たとえば `log.js` 、11 件のメッセージが発生したとします。</span><span class="sxs-lookup"><span data-stu-id="c8b29-241">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="サイドバーでメッセージのソースを表示する" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="c8b29-243">サイドバーでメッセージのソースを表示する</span><span class="sxs-lookup"><span data-stu-id="c8b29-243">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="c8b29-244">ユーザー メッセージでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c8b29-244">Filter by user messages</span></span>  

<span data-ttu-id="c8b29-245">以前は、[ログ情報] **を選択**すると、コンソールにメッセージを記録するために名前 `console.log('Hello, Console!')` が付けられたスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="c8b29-245">Earlier, when you choose **Log Info**, a script named `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="c8b29-246">このような JavaScript からログに記録されるメッセージは、名前付き **ユーザー メッセージです**。</span><span class="sxs-lookup"><span data-stu-id="c8b29-246">Messages logged from JavaScript like this are named **user messages**.</span></span>  <span data-ttu-id="c8b29-247">これに対し、原因 **404 を**選択すると、要求されたリソースが見つからないことを示すレベルのメッセージがブラウザー `Error` に記録されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-247">In contrast, when you choose **Cause 404**, the browser logs an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="c8b29-248">ブラウザー メッセージと見なされる、のような **メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="c8b29-248">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="c8b29-249">サイドバーを **使用して** ブラウザー メッセージをフィルター処理し、ユーザー メッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-249">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="c8b29-250">Choose **9 User Messages**.</span><span class="sxs-lookup"><span data-stu-id="c8b29-250">Choose **9 User Messages**.</span></span>  <span data-ttu-id="c8b29-251">ブラウザー メッセージは非表示になります。</span><span class="sxs-lookup"><span data-stu-id="c8b29-251">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="ブラウザー メッセージのフィルター処理" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="c8b29-253">ブラウザー メッセージのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="c8b29-253">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c8b29-254">**[13 メッセージ] を選択**して、すべてのメッセージを再び表示します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-254">Choose **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="c8b29-255">他のパネルと一緒にコンソールを使用する</span><span class="sxs-lookup"><span data-stu-id="c8b29-255">Use the Console alongside any other panel</span></span>  

<span data-ttu-id="c8b29-256">スタイルを編集しているが、コンソール ログで何かすばやく確認する必要がある場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c8b29-256">What if you are editing styles, but you need to quickly check the Console log for something?</span></span>  <span data-ttu-id="c8b29-257">ドロワーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-257">Use the Drawer.</span></span>  

1.  <span data-ttu-id="c8b29-258">[要素] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-258">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="c8b29-259">`Escape` を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b29-259">Select `Escape`.</span></span>  <span data-ttu-id="c8b29-260">ドロ **ワーの [** コンソール] **タブが開** きます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-260">The **Console** tab of the **Drawer** opens.</span></span>  <span data-ttu-id="c8b29-261">このチュートリアルでは、コンソール パネルのすべての機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c8b29-261">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="ドロワーの [コンソール] タブ" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="c8b29-263">ドロ **ワーの** [コンソール] **タブ**</span><span class="sxs-lookup"><span data-stu-id="c8b29-263">The **Console** tab in the **Drawer**</span></span>  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   Navigate to [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   Navigate to [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

## <span data-ttu-id="c8b29-264">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c8b29-264">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) 開発者ツール |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使ってコマンドを実行する |Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "コンソール リファレンス |Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージのログ記録の概要 |Glitch"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタック トレース - Wikipedia"  
> [!NOTE]
> <span data-ttu-id="c8b29-274">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8b29-274">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c8b29-275">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/log) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c8b29-275">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c8b29-277">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c8b29-277">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
