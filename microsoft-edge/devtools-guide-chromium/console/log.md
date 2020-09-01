---
title: コンソールでのメッセージの記録を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c2cf868e6daaf9dd45c7acc90a71c2154261b9c3
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982694"
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





# <span data-ttu-id="aa7ea-103">コンソールでのメッセージの記録を開始する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-103">Get Started With Logging Messages In The Console</span></span>   



<span data-ttu-id="aa7ea-104">この対話形式のチュートリアルでは、 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] コンソールでメッセージの記録とフィルター処理を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-104">This interactive tutorial shows you how to log and filter messages in the [Microsoft Edge DevTools][MicrosoftEdgeDevTools] console.</span></span>  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="コンソールでのメッセージ" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   <span data-ttu-id="aa7ea-106">**コンソール**でのメッセージ</span><span class="sxs-lookup"><span data-stu-id="aa7ea-106">Messages in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="aa7ea-107">このチュートリアルは順番どおりに完了することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-107">This tutorial is intended to be completed in order.</span></span>  <span data-ttu-id="aa7ea-108">JavaScript を使用してページにインタラクティビティを追加する方法など、web 開発の基礎を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-108">It assumes that you understand the fundamentals of web development, such as how to use JavaScript to add interactivity to a page.</span></span>  

## <span data-ttu-id="aa7ea-109">デモツールと DevTools をセットアップする</span><span class="sxs-lookup"><span data-stu-id="aa7ea-109">Set up the demo and DevTools</span></span>   

<span data-ttu-id="aa7ea-110">このチュートリアルは、デモを開き、すべてのワークフローを自分で試すことができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-110">This tutorial is designed so that you are able to open up the demo and try all the workflows yourself.</span></span>  <span data-ttu-id="aa7ea-111">実際にフォローすると、後でワークフローを覚える可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-111">When you physically follow along, you are more likely to remember the workflows later.</span></span>  

1.  <span data-ttu-id="aa7ea-112">`Control`[\ (Windows \)] または `Command` [\ (macOS \)] を押したまま、新しいタブで開くための**コンソールログの例**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-112">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **Console Log Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="aa7ea-113">コンソールログの例</span><span class="sxs-lookup"><span data-stu-id="aa7ea-113">Console Log Examples</span></span>][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  <span data-ttu-id="aa7ea-114">デモにフォーカスを置いて、 `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押すと、devtools を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-114">Focus the demo and then press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open DevTools.</span></span>  <span data-ttu-id="aa7ea-115">既定では、DevTools がデモの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-115">By default DevTools opens to the right of the demo.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="デモの右側に DevTools が開きます。" lightbox="../media/console-example-devtools-right-console.msft.png":::
             <span data-ttu-id="aa7ea-117">デモの右側に DevTools が開きます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-117">DevTools opens to the right of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="aa7ea-118">[ウィンドウの下部に DevTools をドッキング][DevToolsCustomizePlacement]します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-118">[Dock DevTools to the bottom of the window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="デモの下部にドッキングされた DevTools" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             <span data-ttu-id="aa7ea-120">デモの下部にドッキングされた DevTools</span><span class="sxs-lookup"><span data-stu-id="aa7ea-120">DevTools docked to the bottom of the demo</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="aa7ea-121">[DevTools を別のウィンドウにドッキング解除][DevToolsCustomizePlacement]します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-121">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="別のウィンドウに表示されるブラウザー" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             <span data-ttu-id="aa7ea-123">別のウィンドウに表示されるブラウザー</span><span class="sxs-lookup"><span data-stu-id="aa7ea-123">Browser in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > <span data-ttu-id="aa7ea-124">[DevTools を別のウィンドウにドッキング解除][DevToolsCustomizePlacement]します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-124">[Undock DevTools into a separate window][DevToolsCustomizePlacement].</span></span>  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="別のウィンドウでアンドックされる DevTools" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             <span data-ttu-id="aa7ea-126">別のウィンドウでアンドックされる DevTools</span><span class="sxs-lookup"><span data-stu-id="aa7ea-126">DevTools undocked in a separate window</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="aa7ea-127">JavaScript から記録されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-127">View messages logged from JavaScript</span></span>   

<span data-ttu-id="aa7ea-128">本体に表示されるほとんどのメッセージは、ページの JavaScript を作成した web 開発者から提供されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-128">Most messages that you see in the Console come from the web developers who wrote the JavaScript of the page.</span></span>  <span data-ttu-id="aa7ea-129">このセクションの目標は、コンソールに表示される可能性のあるさまざまなメッセージの種類について説明し、各メッセージの種類を自分の JavaScript から自分でログに記録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-129">The goal of this section is to introduce you to the different message types that you are likely to see in the Console, and explain how you may log each message type yourself from your own JavaScript.</span></span>  

1.  <span data-ttu-id="aa7ea-130">デモの [ **ログ情報** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-130">Click the **Log Info** button in the demo.</span></span>  `Hello, Console!` <span data-ttu-id="aa7ea-131">コンソールにログインします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-131">gets logged to the Console.</span></span>
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="ログ情報をクリックした後の本体" lightbox="../media/console-log-info.msft.png":::
       <span data-ttu-id="aa7ea-133">**ログ情報**をクリックした後の**本体**</span><span class="sxs-lookup"><span data-stu-id="aa7ea-133">The **Console** after clicking **Log Info**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-134">コンソールのメッセージの横にある `Hello, Console!` [ **log.js: 2**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-134">Next to the `Hello, Console!` message in the Console click **log.js:2**.</span></span>  <span data-ttu-id="aa7ea-135">[ソース] パネルが開き、メッセージがコンソールに記録される原因となったコード行が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-135">The Sources panel opens and highlights the line of code that caused the message to get logged to the Console.</span></span>  <span data-ttu-id="aa7ea-136">ページの JavaScript の実行時にメッセージが記録されました `console.log('Hello, Console!')` 。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-136">The message was logged when the JavaScript of the page ran `console.log('Hello, Console!')`.</span></span>
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="[log.js] をクリックすると、[ソース] パネルが開きます。2" lightbox="../media/console-sources-logjs.msft.png":::
       <span data-ttu-id="aa7ea-138">[DevTools] をクリックすると、[ **ソース** ] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-138">DevTools opens the **Sources** panel after you click</span></span> `log.js:2`  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-139">次のいずれかのワークフローを使用して、 **コンソール** に移動します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-139">Navigate back to the **Console** using any of the following workflows:</span></span>  
    
    *   <span data-ttu-id="aa7ea-140">[ **コンソール** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-140">Click the **Console** tab.</span></span>  
    *   <span data-ttu-id="aa7ea-141">`Control` + `[` `Command` + `[` コンソールパネルがフォーカスされるまで、\ (Windows \) または \ (macOS \) キーを押します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-141">Press `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) until the Console panel is in focus.</span></span>  
    *   <span data-ttu-id="aa7ea-142">[コマンドメニューを開き][DevToolsCommandMenu]、入力を開始して `Console` 、[ **コンソールパネルを表示** ] コマンドを選択し、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-142">[Open the Command Menu][DevToolsCommandMenu], start typing `Console`, select the **Show Console Panel** command, and then press `Enter`.</span></span>  
    
1.  <span data-ttu-id="aa7ea-143">デモの [ **ログの警告** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-143">Click the **Log Warning** button in the demo.</span></span>  `Abandon Hope All Ye Who Enter` <span data-ttu-id="aa7ea-144">コンソールにログインします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-144">gets logged to the Console.</span></span>  <span data-ttu-id="aa7ea-145">次のように書式設定されたメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-145">Messages formatted like this are warnings.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="[ログ警告] をクリックした後の本体" lightbox="../media/console-log-warning.msft.png":::
       <span data-ttu-id="aa7ea-147">[**ログ警告**] をクリックした後の**本体**</span><span class="sxs-lookup"><span data-stu-id="aa7ea-147">The **Console** after you click **Log Warning**</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="aa7ea-148">メッセージが特定の方法でログに記録される原因となったコードを表示する場合は、スクリプト (\ など) をクリックして、 `log.js:12` メッセージの書式設定を引き起こしたコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-148">If you want to see the code that caused a message to get logged a certain way, click on a script \(such as `log.js:12`\) to view the code that caused the message to get formatted.</span></span>  

1.  <span data-ttu-id="aa7ea-149">**Expand** ![ の前にある展開 \ (展開 ][ImageExpandIcon] \) アイコンをクリックし `Abandon Hope All Ye Who Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-149">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon in front of `Abandon Hope All Ye Who Enter`.</span></span>  <span data-ttu-id="aa7ea-150">DevTools は、呼び出しにつながる [スタックトレース][WikiStackTrace] を示します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-150">DevTools shows the [stack trace][WikiStackTrace] leading up to the call.</span></span>  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="スタックトレース" lightbox="../media/console-log-warning-expanded.msft.png":::
       <span data-ttu-id="aa7ea-152">スタックトレース</span><span class="sxs-lookup"><span data-stu-id="aa7ea-152">A stack trace</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="aa7ea-153">スタックトレースでは、という名前の関数が呼び出されたことが通知され `logWarning` ます。これは、という名前の関数が呼び出され `quoteDante` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-153">The stack trace is telling you that a function named `logWarning` was called, which in turn called a function named `quoteDante`.</span></span>  <span data-ttu-id="aa7ea-154">つまり、最初に発生した通話はスタックトレースの一番下にあります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-154">In other words, the call that happened first is at the bottom of the stack trace.</span></span>  <span data-ttu-id="aa7ea-155">スタックトレースの記録は、いつでも呼び出すことができ `console.trace()` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-155">You may log stack traces at any time by calling `console.trace()`.</span></span>  

1.  <span data-ttu-id="aa7ea-156">[ **ログエラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-156">Click **Log Error**.</span></span>  <span data-ttu-id="aa7ea-157">次のエラーメッセージが記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-157">The following error message gets logged:</span></span> `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="エラーメッセージ" lightbox="../media/console-log-error.msft.png":::
       <span data-ttu-id="aa7ea-159">エラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="aa7ea-159">An error message</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-160">[ **Log Table**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-160">Click **Log Table**.</span></span>  <span data-ttu-id="aa7ea-161">有名なアーティストについての表が本体に記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-161">A table about famous artists gets logged to the Console.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="aa7ea-162">`birthday`列は1つの行にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-162">The `birthday` column is only populated for one row.</span></span>  <span data-ttu-id="aa7ea-163">コードを確認して、その理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-163">Review the code to determine why that is.</span></span>
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="コンソールの表" lightbox="../media/console-log-table.msft.png":::
       <span data-ttu-id="aa7ea-165">**コンソール**の表</span><span class="sxs-lookup"><span data-stu-id="aa7ea-165">A table in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-166">[ **Log Group**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-166">Click **Log Group**.</span></span>  <span data-ttu-id="aa7ea-167">4つの有名、犯罪 turtles の名前はラベルの下にグループ化されてい `Adolescent Irradiated Espionage Tortoises` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-167">The names of 4 famous, crime-fighting turtles are grouped under the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="コンソールのメッセージのグループ" lightbox="../media/console-log-group.msft.png":::
       <span data-ttu-id="aa7ea-169">**コンソール**のメッセージのグループ</span><span class="sxs-lookup"><span data-stu-id="aa7ea-169">A group of messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-170">[ **Custom Custom**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-170">Click **Log Custom**.</span></span>  <span data-ttu-id="aa7ea-171">赤い境界線の付いたメッセージと青色の背景が本体に記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-171">A message with a red border and blue background gets logged to the Console.</span></span>  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="コンソールでのカスタム書式設定を含むメッセージ" lightbox="../media/console-log-custom.msft.png":::
       <span data-ttu-id="aa7ea-173">**コンソール**でのカスタム書式設定を含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="aa7ea-173">A message with custom formatting in the **Console**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="aa7ea-174">ここでの主なアイデアは、JavaScript からコンソールにメッセージを記録するときに、メソッドの1つを使うことです `console` 。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-174">The main idea here is that when you want to log messages to the Console from your JavaScript, you use one of the `console` methods.</span></span>  <span data-ttu-id="aa7ea-175">各メソッドは、異なる形式のメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-175">Each method formats messages differently.</span></span>  

<span data-ttu-id="aa7ea-176">このセクションで説明されている方法よりも、さらに多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-176">There are even more methods than what has been demonstrated in this section.</span></span>  <span data-ttu-id="aa7ea-177">このチュートリアルでは、残りのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-177">This tutorial shows you how to explore the rest of the methods.</span></span>  

## <span data-ttu-id="aa7ea-178">ブラウザーでログに記録されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-178">View messages logged by the browser</span></span>   

<span data-ttu-id="aa7ea-179">ブラウザーでも、コンソールにメッセージが記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-179">The browser logs messages to the Console, too.</span></span>  <span data-ttu-id="aa7ea-180">これは通常、ページに問題がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-180">This usually happens when there is a problem with the page.</span></span>  

1.  <span data-ttu-id="aa7ea-181">[ **原因 404**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-181">Click **Cause 404**.</span></span>  <span data-ttu-id="aa7ea-182">`404`ページの JavaScript が存在しないファイルを取得しようとしたため、ブラウザーは、HTTP 状態コード (ネットワークエラー) をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-182">The browser logs an HTTP status code of `404` network error because the JavaScript of the page tried to fetch a file that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="本体の404エラー" lightbox="../media/console-cause-404.msft.png":::
       <span data-ttu-id="aa7ea-184">`404`**本体**のエラー</span><span class="sxs-lookup"><span data-stu-id="aa7ea-184">A `404` error in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-185">[ **原因エラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-185">Click **Cause Error**.</span></span>  <span data-ttu-id="aa7ea-186">`TypeError`JavaScript が存在しない DOM ノードを更新しようとしているため、ブラウザーは不明なログを記録します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-186">The browser logs an uncaught `TypeError` because the JavaScript is trying to update a DOM node that does not exist.</span></span>  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="本体の TypeError" lightbox="../media/console-cause-error.msft.png":::
       <span data-ttu-id="aa7ea-188">`TypeError`**コンソール**の A</span><span class="sxs-lookup"><span data-stu-id="aa7ea-188">A `TypeError` in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-189">[ **ログレベル** ] ドロップダウンをクリックし、[ **詳細** ] オプションが無効になっている場合はそれを有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-189">Click the **Log Levels** dropdown and enable the **Verbose** option if it is disabled.</span></span>  <span data-ttu-id="aa7ea-190">フィルター処理の詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-190">You learn more about filtering in the next section.</span></span>  <span data-ttu-id="aa7ea-191">次のメッセージが表示されるようにするには、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-191">You need to do this to make sure that the next message you log is visible.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="aa7ea-192">[既定のレベル] ドロップダウンが無効になっている場合は、 **コンソール** サイドバーを閉じる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-192">If the Default Levels dropdown is disabled, you may need to close the **Console** Sidebar.</span></span>  <span data-ttu-id="aa7ea-193">**コンソール**サイドバーの詳細については、以下の「メッセージソースでフィルター処理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-193">Filter by Message Source below for more information about the **Console** Sidebar.</span></span>
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="詳細ログレベルを有効にする" lightbox="../media/console-cause-error-log-levels.msft.png":::
       <span data-ttu-id="aa7ea-195">詳細ログレベルを有効にする</span><span class="sxs-lookup"><span data-stu-id="aa7ea-195">Enabling the Verbose log level</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-196">[ **原因違反**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-196">Click **Cause Violation**.</span></span>  <span data-ttu-id="aa7ea-197">ページが数秒間応答しなくなった後、ブラウザーで本体にメッセージが記録され `[Violation] 'click' handler took 3000ms` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-197">The page becomes unresponsive for a few seconds and then the browser logs the message `[Violation] 'click' handler took 3000ms` to the Console.</span></span>  <span data-ttu-id="aa7ea-198">正確な期間は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-198">The exact duration may vary.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="本体の違反" lightbox="../media/console-cause-violation.msft.png":::
       <span data-ttu-id="aa7ea-200">**本体**の違反</span><span class="sxs-lookup"><span data-stu-id="aa7ea-200">A violation in the **Console**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="aa7ea-201">メッセージをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-201">Filter messages</span></span>   

<span data-ttu-id="aa7ea-202">一部のページでは、コンソールにメッセージがあふれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-202">On some pages you see the Console get flooded with messages.</span></span>  <span data-ttu-id="aa7ea-203">DevTools には、現在のタスクに関連しないメッセージをフィルター処理するさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-203">DevTools provides many different ways to filter out messages that are not relevant to the task at hand.</span></span>  

### <span data-ttu-id="aa7ea-204">ログレベルでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-204">Filter by log level</span></span>   

<span data-ttu-id="aa7ea-205">各 `console` メソッドには、、、、 `Verbose` `Info` `Warning` またはなどの重大度レベルが割り当てられます `Error` 。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-205">Each `console` method is assigned a severity level: `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="aa7ea-206">たとえば、はレベルのメッセージです。のように、 `console.log()` `Info` レベルのメッセージです `console.error()` `Error` 。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-206">For example, `console.log()` is an `Info`-level message, whereas `console.error()` is an `Error`-level message.</span></span>  

1.  <span data-ttu-id="aa7ea-207">[ **ログレベル** ] ドロップダウンをクリックして **エラー**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-207">Click the **Log Levels** dropdown and disable **Errors**.</span></span>  <span data-ttu-id="aa7ea-208">横にチェックマークが表示されなくなった場合、レベルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-208">A level is disabled when there is no longer a checkmark next to it.</span></span>  <span data-ttu-id="aa7ea-209">レベルのメッセージが表示さ `Error` れなくなります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-209">The `Error`-level messages disappear.</span></span>  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="コンソールでエラーレベルのメッセージを無効にする" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       <span data-ttu-id="aa7ea-211">**コンソール**でエラーレベルのメッセージを無効にする</span><span class="sxs-lookup"><span data-stu-id="aa7ea-211">Disabling Error-level messages in the **Console**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-212">[ **ログレベル** ] ドロップダウンをもう一度クリックし、 **エラー**を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-212">Click the **Log Levels** dropdown again and re-enable **Errors**.</span></span>  <span data-ttu-id="aa7ea-213">レベルのメッセージが再び表示さ `Error` れます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-213">The `Error`-level messages reappear.</span></span>  

### <span data-ttu-id="aa7ea-214">テキストでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-214">Filter by text</span></span>   

<span data-ttu-id="aa7ea-215">正確な文字列を含むメッセージのみを表示する場合は、その文字列を [ **フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-215">When you want to only view messages that include an exact string, type that string into the **Filter** text box.</span></span>  

1.  <span data-ttu-id="aa7ea-216">`Dave`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-216">Type `Dave` into the **Filter** text box.</span></span>  <span data-ttu-id="aa7ea-217">文字列を含まないすべてのメッセージ `Dave` は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-217">All messages that do not include the string `Dave` are hidden.</span></span>  <span data-ttu-id="aa7ea-218">また、ラベルが表示される場合もあり `Adolescent Irradiated Espionage Tortoises` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-218">You might also see the `Adolescent Irradiated Espionage Tortoises` label.</span></span>  <span data-ttu-id="aa7ea-219">これはバグです。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-219">That is a bug.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="Dave が含まれていないメッセージをフィルターで除外する" lightbox="../media/console-all-messages-text-filter.msft.png":::
       <span data-ttu-id="aa7ea-221">含まれていないメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-221">Filtering out any message that does not include</span></span> `Dave`  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-222">`Dave`[**フィルター** ] テキストボックスから削除します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-222">Delete `Dave` from the **Filter** text box.</span></span>  <span data-ttu-id="aa7ea-223">すべてのメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-223">All the messages reappear.</span></span>  

### <span data-ttu-id="aa7ea-224">正規表現によるフィルター</span><span class="sxs-lookup"><span data-stu-id="aa7ea-224">Filter by regular expression</span></span>   

<span data-ttu-id="aa7ea-225">特定の文字列ではなく、テキストのパターンを含むすべてのメッセージを表示する場合は、 [正規表現][MDNRegularExpressions]を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-225">When you want to show all messages that include a pattern of text, rather than a specific string, use a [regular expression][MDNRegularExpressions].</span></span>  

1.  <span data-ttu-id="aa7ea-226">`/^[AH]/`[**フィルター** ] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-226">Type `/^[AH]/` into the **Filter** text box.</span></span>  <span data-ttu-id="aa7ea-227">このパターンを [RegExr][|::ref1::|Main] に入力して、実行内容の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-227">Type this pattern into [RegExr][|::ref1::|Main] for an explanation of what it is doing.</span></span>  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="パターンに一致しないメッセージをフィルターで除外する" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       <span data-ttu-id="aa7ea-229">パターンに一致しないメッセージをフィルターで除外する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-229">Filtering out any message that does not match the pattern</span></span> `/^[AH]/`  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-230">`/^[AH]/`[**フィルター** ] テキストボックスから削除します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-230">Delete `/^[AH]/` from the **Filter** text box.</span></span>  <span data-ttu-id="aa7ea-231">すべてのメッセージが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-231">All messages are visible again.</span></span>  

### <span data-ttu-id="aa7ea-232">メッセージソース別にフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-232">Filter by message source</span></span>   

<span data-ttu-id="aa7ea-233">特定の URL のメッセージのみを表示するには、 **サイドバー**を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-233">When you want to only view the messages that came from a certain URL, use the **Sidebar**.</span></span>  

1.  <span data-ttu-id="aa7ea-234">[ **コンソールサイドバーの表示** ] をクリックします ([ ![ コンソールサイドバーを表示] をクリック ][ImageShowConsoleSidebarIcon] します)。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-234">Click **Show Console Sidebar** \(![Show Console Sidebar][ImageShowConsoleSidebarIcon]\).</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="サイドバー" lightbox="../media/console-sidebar-all-messages.msft.png":::
       <span data-ttu-id="aa7ea-236">サイドバー</span><span class="sxs-lookup"><span data-stu-id="aa7ea-236">The Sidebar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-237">メッセージ数の隣にある **展開** \ ( ![ 展開 ][ImageExpandIcon] \) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-237">Click the **Expand** \(![Expand][ImageExpandIcon]\) icon next to the number of messages.</span></span>  <span data-ttu-id="aa7ea-238">次の図は、メッセージの数が **13 のメッセージ**であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-238">In the following figure, the number of messages is indicated as **13 Messages**.</span></span>  <span data-ttu-id="aa7ea-239">**サイドバー**には、メッセージが記録される原因となった url の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-239">The **Sidebar** shows a list of URLs that caused messages to be logged.</span></span>  <span data-ttu-id="aa7ea-240">たとえば、11個のメッセージが発生しました `log.js` 。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-240">For example, `log.js` caused 11 messages.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="サイドバーでのメッセージのソースの表示" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       <span data-ttu-id="aa7ea-242">サイドバーでのメッセージのソースの表示</span><span class="sxs-lookup"><span data-stu-id="aa7ea-242">Viewing the source of messages in the Sidebar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="aa7ea-243">ユーザーメッセージでフィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-243">Filter by user messages</span></span>   

<span data-ttu-id="aa7ea-244">以前は、[ **ログ情報**] をクリックしたときに、 `console.log('Hello, Console!')` メッセージをコンソールにログするためのスクリプトが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-244">Earlier, when you clicked **Log Info**, a script called `console.log('Hello, Console!')` in order to log the message to the Console.</span></span>  <span data-ttu-id="aa7ea-245">このような JavaScript から記録されるメッセージは、「 **ユーザメッセージ**」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-245">Messages logged from JavaScript like this are called **user messages**.</span></span>  <span data-ttu-id="aa7ea-246">これに対して、[ **原因 404**] をクリックすると、 `Error` 要求されたリソースが見つからなかったことを示すレベルのメッセージがブラウザーでログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-246">In contrast, when you clicked **Cause 404**, the browser logged an `Error`-level message stating that the requested resource could not be found.</span></span>  <span data-ttu-id="aa7ea-247">そのようなメッセージは、 **ブラウザーメッセージ**とみなされます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-247">Messages like that are considered **browser messages**.</span></span>  <span data-ttu-id="aa7ea-248">**サイドバー**を使用して、ブラウザーメッセージをフィルター処理し、ユーザーメッセージのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-248">Use the **Sidebar** to filter out browser messages and only show user messages.</span></span>  

1.  <span data-ttu-id="aa7ea-249">[ **9 ユーザーメッセージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-249">Click **9 User Messages**.</span></span>  <span data-ttu-id="aa7ea-250">ブラウザーのメッセージが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-250">The browser messages are hidden.</span></span>  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="ブラウザーメッセージのフィルター処理" lightbox="../media/console-sidebar-user-messages.msft.png":::
       <span data-ttu-id="aa7ea-252">ブラウザーメッセージのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="aa7ea-252">Filtering out browser messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="aa7ea-253">[ **13** 個のメッセージ] をクリックすると、再びすべてのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-253">Click **13 Messages** to show all messages again.</span></span>  

## <span data-ttu-id="aa7ea-254">他のパネルと共に本体を使用する</span><span class="sxs-lookup"><span data-stu-id="aa7ea-254">Use the Console alongside any other panel</span></span>   

<span data-ttu-id="aa7ea-255">スタイルを編集していても、コンソールログの何かをすばやく確認する必要がある場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-255">What if you are editing styles, but you need to quickly check the Console log for something?</span></span> <span data-ttu-id="aa7ea-256">引き出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-256">Use the Drawer.</span></span>  

1.  <span data-ttu-id="aa7ea-257">[ **要素** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-257">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="aa7ea-258">キーを押し `Escape` ます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-258">Press `Escape`.</span></span>  <span data-ttu-id="aa7ea-259">**ドロワー**の [コンソール] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-259">The Console tab of the **Drawer** opens.</span></span>  <span data-ttu-id="aa7ea-260">このチュートリアルで使用しているコンソールパネルのすべての機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-260">It has all of the features of the Console panel that you have been using throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="ドローワの [コンソール] タブ" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         <span data-ttu-id="aa7ea-262">**ドローワ**の [**コンソール**] タブ</span><span class="sxs-lookup"><span data-stu-id="aa7ea-262">The **Console** tab in the **Drawer**</span></span>  
    :::image-end:::  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

<!--
 


-->  

<!-- image links -->  

[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: ../media/show-console-sidebar-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する |Microsoft ドキュメント"  
[DevToolsConsoleApi]: ./api.md "コンソール API リファレンス |Microsoft ドキュメント"  
[DevToolsConsoleReference]: ./reference.md "コンソールリファレンス |Microsoft ドキュメント"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "メッセージの記録を開始する |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正規表現 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "スタックトレース-Wikipedia"  


> [!NOTE]
> <span data-ttu-id="aa7ea-272">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-272">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="aa7ea-273">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/console/log) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-273">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/log) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="aa7ea-275">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="aa7ea-275">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
