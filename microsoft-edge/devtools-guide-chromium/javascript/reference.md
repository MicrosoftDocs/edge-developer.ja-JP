---
description: DevTools デバッグ機能のこの包括的な参照で、新Microsoft Edgeワークフローを確認します。
title: デバッガー機能の使用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6b15d317d4c720ab5ad76b7047532df101f69376
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564127"
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
# <a name="use-the-debugger-features"></a><span data-ttu-id="a697c-104">デバッガー機能の使用</span><span class="sxs-lookup"><span data-stu-id="a697c-104">Use the debugger features</span></span>

<span data-ttu-id="a697c-105">この記事では、コード行ブレークポイントを設定する方法Microsoft Edge DevTools でデバッガーを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a697c-105">This article covers how to use the debugger in Microsoft Edge DevTools, including how to set a line-of-code breakpoint.</span></span>  <span data-ttu-id="a697c-106">他の種類のブレークポイントを設定するには、「ブレークポイントでコードを一 [時停止する」を参照してください][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="a697c-106">To set other types of breakpoints, see [Pause your code with breakpoints][DevToolsJavascriptBreakpoints].</span></span>  

<span data-ttu-id="a697c-107">デバッグの基本については[、「Microsoft Edge DevTools][DevToolsJavascriptGetStarted]での JavaScript のデバッグの開始」に移動します。これは、既存のフォーム ベースの Web ページを使用するチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="a697c-107">To learn the basics of debugging, navigate to [Get started with debugging JavaScript in Microsoft Edge DevTools][DevToolsJavascriptGetStarted], which is a tutorial that uses an existing, form-based webpage.</span></span>  <span data-ttu-id="a697c-108">チュートリアルには画面キャプチャが含め、ススキミングできます。</span><span class="sxs-lookup"><span data-stu-id="a697c-108">The tutorial has screen captures, so you can skim it.</span></span>  <span data-ttu-id="a697c-109">デモ Web ページを使用すると、デバッガー機能を簡単に試してみます。</span><span class="sxs-lookup"><span data-stu-id="a697c-109">You can easily try out the debugger features by using the demo webpage.</span></span>

## <a name="view-and-edit-javascript-code"></a><span data-ttu-id="a697c-110">JavaScript コードの表示と編集</span><span class="sxs-lookup"><span data-stu-id="a697c-110">View and edit JavaScript code</span></span>

<span data-ttu-id="a697c-111">バグを修正する場合は、JavaScript コードに対する変更を試してみる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a697c-111">When fixing a bug, you often want to try out some changes to your JavaScript code.</span></span>  <span data-ttu-id="a697c-112">外部エディターまたは IDE で変更を加え、ファイルをサーバーに再アップロードしてから、ページを更新する必要があります。代わりに、変更をテストするために、DevTools で JavaScript コードを直接編集し、結果をすぐに確認できます。</span><span class="sxs-lookup"><span data-stu-id="a697c-112">You don't need to make the changes in an external editor or IDE, re-upload the file to the server, and then refresh the page; instead, to test changes, you can edit your JavaScript code directly in DevTools and see the result immediately.</span></span>  

<span data-ttu-id="a697c-113">JavaScript ファイルを表示および編集するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a697c-113">To view and edit a JavaScript file:</span></span>  

1.  <span data-ttu-id="a697c-114">[ソース] **ツールに移動** します。</span><span class="sxs-lookup"><span data-stu-id="a697c-114">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="a697c-115">[ナビゲーター **] ウィンドウ** でファイルを選択し、[エディター] ウィンドウで **開** きます。</span><span class="sxs-lookup"><span data-stu-id="a697c-115">In the **Navigator** pane, select your file, to open it in the **Editor** pane.</span></span>
1.  <span data-ttu-id="a697c-116">[エディター **] ウィンドウ** で、ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="a697c-116">In the **Editor** pane, edit your file.</span></span>  
1.  <span data-ttu-id="a697c-117">`Ctrl` + `S` \(Windows Linux\) または `Command` + `S` \(macOS\) を選択して保存します。</span><span class="sxs-lookup"><span data-stu-id="a697c-117">Select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="a697c-118">その後、DevTools は JavaScript ファイルを JavaScript ファイルの JavaScript エンジンに読み込Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a697c-118">DevTools then loads the JavaScript file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="[エディター] ウィンドウ" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="a697c-120">[ **エディター]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a697c-120">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <a name="reformat-a-minified-javascript-file-with-pretty-print"></a><span data-ttu-id="a697c-121">美しい印刷で、ミニマ化された JavaScript ファイルを再フォーマットする</span><span class="sxs-lookup"><span data-stu-id="a697c-121">Reformat a minified JavaScript file with pretty-print</span></span>

<span data-ttu-id="a697c-122">ファイルを人間が読み取り可能にするには、[エディター] ウィンドウの下部にある [ **書式]** ![ ](../media/format-icon.msft.png) \( Format \) ボタンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="a697c-122">To make a minified file human-readable, choose the **Format** \(![Format](../media/format-icon.msft.png)\) button at the bottom of the **Editor** pane.</span></span>

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="[書式] ボタン" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="a697c-124">[ **書式]** ボタン</span><span class="sxs-lookup"><span data-stu-id="a697c-124">The **Format** button</span></span>  
:::image-end:::  

## <a name="set-a-breakpoint-to-pause-code"></a><span data-ttu-id="a697c-125">ブレークポイントを設定し、コードを一時停止する</span><span class="sxs-lookup"><span data-stu-id="a697c-125">Set a breakpoint, to pause code</span></span>

<span data-ttu-id="a697c-126">ランタイムの途中でコードを一時停止するには、ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a697c-126">To pause your code in the middle of the runtime, set a breakpoint.</span></span>  <span data-ttu-id="a697c-127">最も基本的で既知の種類のブレークポイントは、コード行ブレークポイントです。</span><span class="sxs-lookup"><span data-stu-id="a697c-127">The most basic and well-known type of breakpoint is a line-of-code breakpoint.</span></span>

<span data-ttu-id="a697c-128">調査する必要があるコードの正確な領域を知っている場合は、コード行ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a697c-128">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="a697c-129">DevTools は、指定したコード行で実行する前に常に一時停止します。</span><span class="sxs-lookup"><span data-stu-id="a697c-129">DevTools always pauses at the specified line of code, before running it.</span></span>

<span data-ttu-id="a697c-130">コード行ブレークポイントを設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a697c-130">To set a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="a697c-131">[ソース] **ツールに移動** します。</span><span class="sxs-lookup"><span data-stu-id="a697c-131">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="a697c-132">コード行を含むファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a697c-132">Open the file that contains the line of code.</span></span>  
1.  <span data-ttu-id="a697c-133">コード行の行番号の左側にある領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-133">Select the area to the left of the line number for the line of code.</span></span>  <span data-ttu-id="a697c-134">または、行番号を右クリックし、[ブレークポイントの追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a697c-134">Or, right-click the line number and then choose **Add breakpoint**.</span></span>  <span data-ttu-id="a697c-135">次に、行番号の横に赤い円が表示され、ブレークポイントが示されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-135">A red circle then appears next to the line number, indicating a breakpoint.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="コード行ブレークポイント" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="a697c-137">コード行ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="a697c-137">A line-of-code breakpoint</span></span>  
    :::image-end:::  

<span data-ttu-id="a697c-138">コード行のブレークポイントは、特に場所が正確に分からない場合や、コードベースが大きい場合は、設定が非効率的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a697c-138">Line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if your codebase is large.</span></span>  <span data-ttu-id="a697c-139">デバッグの時間を節約するには、他の種類のブレークポイントを使用する方法と使用時期について説明します。</span><span class="sxs-lookup"><span data-stu-id="a697c-139">To save time when debugging, learn how and when to use the other types of breakpoints.</span></span>  <span data-ttu-id="a697c-140">詳細については、「ブレークポイントを使用してコード [を一時停止する」に移動します][DevToolsJavascriptBreakpoints]。</span><span class="sxs-lookup"><span data-stu-id="a697c-140">For more information, navigate to [Pause your code with breakpoints][DevToolsJavascriptBreakpoints].</span></span>

## <a name="step-through-code"></a><span data-ttu-id="a697c-141">コードのステップスルー</span><span class="sxs-lookup"><span data-stu-id="a697c-141">Step through code</span></span>  

<span data-ttu-id="a697c-142">ブレークポイントでコードを一時停止した後、一度に 1 行のコードをステップ実行し、その途中で制御フローとプロパティ値を調査します。</span><span class="sxs-lookup"><span data-stu-id="a697c-142">After your code is paused at a breakpoint, step through the code, one line at a time, investigating control flow and property values along the way.</span></span>  

### <a name="step-over-line-of-code"></a><span data-ttu-id="a697c-143">一行のコードをステップ オーバーする</span><span class="sxs-lookup"><span data-stu-id="a697c-143">Step over line of code</span></span>  

<span data-ttu-id="a697c-144">デバッグ中の問題に関係のない関数を含むコード行で一時停止した場合は、[ステップ オーバー ] \( Step **over** ![ \) ボタンを選択して、ステップ インせずに関数を実行します。 ](../media/step-over-icon.msft.png)</span><span class="sxs-lookup"><span data-stu-id="a697c-144">When paused on a line of code containing a function that isn't relevant to the problem you are debugging, choose the **Step over** \(![Step over](../media/step-over-icon.msft.png)\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="[ステップ オーバー] を選択する" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="a697c-146">[ステップ **オーバー] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a697c-146">Choose **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="a697c-147">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="a697c-147">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

<span data-ttu-id="a697c-148">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-148">You are paused on `A`.</span></span>  <span data-ttu-id="a697c-149">[ステップ オーバー **] を選択した**後、DevTools は、ステップ オーバーする関数内のすべてのコードを実行します。つまり `B` 、 `C` です。</span><span class="sxs-lookup"><span data-stu-id="a697c-149">After you choose **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="a697c-150">DevTools は次に一時停止します `D` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-150">DevTools then pauses on `D`.</span></span>  

### <a name="step-into-line-of-code"></a><span data-ttu-id="a697c-151">コード行へのステップ</span><span class="sxs-lookup"><span data-stu-id="a697c-151">Step into line of code</span></span>  

<span data-ttu-id="a697c-152">デバッグ中の問題に関連する関数呼び出しを含むコード行で一時停止した場合は、[\( Step **to** ![ \) ] ボタンを選択して、その関数をさらに調査します ](../media/step-into-icon.msft.png) 。</span><span class="sxs-lookup"><span data-stu-id="a697c-152">When paused on a line of code containing a function call that is related to the problem you are debugging, choose the **Step into** \(![Step into](../media/step-into-icon.msft.png)\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="[ステップ の実行] を選択します。" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="a697c-154">[ステップ **の実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="a697c-154">Choose **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="a697c-155">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="a697c-155">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

<span data-ttu-id="a697c-156">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-156">You are paused on `A`.</span></span>  <span data-ttu-id="a697c-157">[ステップ イン **] を選択すると**、DevTools はコード行を実行し、次に一時停止します `B` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-157">After you choose **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <a name="step-out-of-line-of-code"></a><span data-ttu-id="a697c-158">コード行からステップアウトする</span><span class="sxs-lookup"><span data-stu-id="a697c-158">Step out of line of code</span></span>  

<span data-ttu-id="a697c-159">デバッグ中の問題に関連しない関数の内部で一時停止した場合は、[ステップ アウト\( Step **out** \) ] ボタンを選択して、関数の残りのコードを ![ ](../media/step-out-icon.msft.png) 実行します。</span><span class="sxs-lookup"><span data-stu-id="a697c-159">When paused inside of a function that isn't related to the problem you are debugging, choose the **Step out** \(![Step out](../media/step-out-icon.msft.png)\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="[ステップ アウト] を選択する" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="a697c-161">[ステップ **アウト] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a697c-161">Choose **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="a697c-162">たとえば、次のコード スニペットをデバッグするとします。</span><span class="sxs-lookup"><span data-stu-id="a697c-162">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

<span data-ttu-id="a697c-163">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-163">You are paused on `A`.</span></span>  <span data-ttu-id="a697c-164">[ステップ アウト **] を選択**すると、DevTools はコードの残りの部分を実行します 。これは、この例に示すだけで、次に `getName()` `B` 一時停止します `C` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-164">After you choose **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <a name="run-all-code-up-to-a-specific-line"></a><span data-ttu-id="a697c-165">特定の行まですべてのコードを実行する</span><span class="sxs-lookup"><span data-stu-id="a697c-165">Run all code up to a specific line</span></span>  

<span data-ttu-id="a697c-166">長い関数をデバッグする場合、デバッグ中の問題に関連しないコードが多い場合があります。</span><span class="sxs-lookup"><span data-stu-id="a697c-166">When debugging a long function, there may be a lot of code that isn't related to the problem you are debugging.</span></span>  

<span data-ttu-id="a697c-167">すべての行をステップスルーすることを選択できますが、これは時間のかかっています。</span><span class="sxs-lookup"><span data-stu-id="a697c-167">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="a697c-168">必要な行にコード行ブレークポイントを設定し、[スクリプトの実行を再開する]\( スクリプト実行の\*\*\*\* 再開 \) ボタンを選択することもできますが、より高速な方法 ![ ](../media/resume-script-run-icon.msft.png) があります。</span><span class="sxs-lookup"><span data-stu-id="a697c-168">You may choose to set a line-of-code breakpoint on the line in which you are interested and then choose the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button, but there is a faster way.</span></span>  

<span data-ttu-id="a697c-169">目的のコード行にカーソルを合わせると、コンテキスト メニュー \(右クリック\) を開き、[続行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a697c-169">Hover on the line of code in which you are interested, open the contextual menu \(right-click\), and choose **Continue to here**.</span></span>  <span data-ttu-id="a697c-170">DevTools は、その時点まですべてのコードを実行し、その行で一時停止します。</span><span class="sxs-lookup"><span data-stu-id="a697c-170">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="[次へ] を選択します。" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="a697c-172">[次 **へ] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="a697c-172">Choose **Continue to here**</span></span>  
:::image-end:::  

### <a name="restart-the-top-function-of-the-call-stack"></a><span data-ttu-id="a697c-173">呼び出し履歴のトップ関数を再起動する</span><span class="sxs-lookup"><span data-stu-id="a697c-173">Restart the top function of the call stack</span></span>  

<span data-ttu-id="a697c-174">呼び出し履歴のトップ関数の最初の行で一時停止し、コード行で一時停止している間は、[通話履歴]\*\*\*\* ウィンドウの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \*\*\*\* \(右クリック\) を開き、[フレームの再起動] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-174">To pause on the first line of the top function in your call stack, while paused on a line of code, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Restart frame**.</span></span>  <span data-ttu-id="a697c-175">トップ関数は、最後に実行された関数です。</span><span class="sxs-lookup"><span data-stu-id="a697c-175">The top function is the last function that was run.</span></span>  

<span data-ttu-id="a697c-176">次のコード スニペットは、手順を実行する例です。</span><span class="sxs-lookup"><span data-stu-id="a697c-176">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="a697c-177">一時停止中です `A` 。</span><span class="sxs-lookup"><span data-stu-id="a697c-177">You are paused on `A`.</span></span>  <span data-ttu-id="a697c-178">[フレームの **再起動] を**選択した後は、ブレークポイントを設定したり、[スクリプトの実行の再開] を選択したりせずに、一 `B` **時停止する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="a697c-178">After choosing **Restart frame**, you should be paused on `B`, without ever setting a breakpoint or choosing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="[フレームの再起動] を選択する" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="a697c-180">[フレーム **の再起動] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a697c-180">Choose **Restart frame**</span></span>  
:::image-end:::  

### <a name="resume-script-runtime"></a><span data-ttu-id="a697c-181">スクリプト ランタイムの再開</span><span class="sxs-lookup"><span data-stu-id="a697c-181">Resume script runtime</span></span>  

<span data-ttu-id="a697c-182">スクリプトの一時停止後にランタイムを続行するには、[スクリプトの実行を **再開する** ]\( Resume script ![ execution ](../media/resume-script-run-icon.msft.png) \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-182">To continue the runtime after a pause of your script, choose the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button.</span></span>  <span data-ttu-id="a697c-183">DevTools は、次のブレークポイントがある場合は、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a697c-183">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="[スクリプトの実行の再開] を選択します。" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="a697c-185">[スクリプト **の実行の再開] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="a697c-185">Choose **Resume script execution**</span></span>  
:::image-end:::  

#### <a name="force-script-runtime"></a><span data-ttu-id="a697c-186">強制スクリプト ランタイム</span><span class="sxs-lookup"><span data-stu-id="a697c-186">Force script runtime</span></span>  

<span data-ttu-id="a697c-187">すべてのブレークポイントを無視し、スクリプトを強制的に実行し続けるには、[スクリプトの\*\*\*\* 実行を再開する]\( スクリプト実行の再開 \) ボタンを選択し、次に [スクリプト実行の強制] \( 強制スクリプト実行 ![ ](../media/resume-script-run-icon.msft.png) \*\*\*\* ![ ](../media/force-script-run-icon.msft.png) \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-187">To ignore all breakpoints and force your script to continue to run, choose and hold the **Resume script execution** \(![Resume script execution](../media/resume-script-run-icon.msft.png)\) button and then choose the **Force script execution** \(![Force script execution](../media/force-script-run-icon.msft.png)\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="[スクリプトの実行を強制する] を選択する" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="a697c-189">[スクリプト **の実行を強制する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a697c-189">Choose **Force script execution**</span></span>  
:::image-end:::  

### <a name="change-thread-context"></a><span data-ttu-id="a697c-190">スレッド コンテキストの変更</span><span class="sxs-lookup"><span data-stu-id="a697c-190">Change thread context</span></span>  

<span data-ttu-id="a697c-191">Web ワーカーまたはサービス ワーカーを操作する場合は、[スレッド] ウィンドウに表示\*\*\*\* されているコンテキストを選択して、そのコンテキストに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a697c-191">When working with web workers or service workers, choose on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="a697c-192">青い矢印アイコンは、現在選択されているコンテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="a697c-192">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="[スレッド] ウィンドウ" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="a697c-194">[ **スレッド]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a697c-194">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="a697c-195">たとえば、メイン スクリプトとサービス ワーカー スクリプトの両方のブレークポイントで一時停止したとします。</span><span class="sxs-lookup"><span data-stu-id="a697c-195">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="a697c-196">サービス ワーカー コンテキストのローカル プロパティとグローバル プロパティを表示する場合\*\*\*\* は、ソース ツールにメイン スクリプト コンテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-196">You want to view the local and global properties for the service worker context, but the **Sources** tool is showing the main script context.</span></span>  <span data-ttu-id="a697c-197">サービス ワーカー コンテキストに切り替える場合は、[ **スレッド** ] ウィンドウでサービス ワーカー エントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-197">To switch to the service worker context, in the **Threads** pane, choose the service worker entry.</span></span>  

## <a name="view-and-edit-properties-and-variables"></a><span data-ttu-id="a697c-198">プロパティと変数の表示と編集</span><span class="sxs-lookup"><span data-stu-id="a697c-198">View and edit properties and variables</span></span>

<span data-ttu-id="a697c-199">コード行で一時停止中に、[スコープ]\*\*\*\* ウィンドウを使用して、ローカル スコープ、クロージャ スコープ、およびグローバル スコープ内のプロパティと変数の値を表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="a697c-199">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="a697c-200">プロパティ値をダブルクリックして変更します。</span><span class="sxs-lookup"><span data-stu-id="a697c-200">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="a697c-201">列挙できないプロパティは灰色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-201">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="[スコープ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="a697c-203">[ **スコープ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a697c-203">The **Scope** pane</span></span>  
:::image-end:::  

## <a name="watch-the-values-of-javascript-expressions"></a><span data-ttu-id="a697c-204">JavaScript 式の値を確認する</span><span class="sxs-lookup"><span data-stu-id="a697c-204">Watch the values of JavaScript expressions</span></span>  

<span data-ttu-id="a697c-205">[ウォッチ **] ウィンドウを** 使用して、カスタム式の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a697c-205">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="a697c-206">有効な JavaScript 式を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a697c-206">You can watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="[ウォッチ] ウィンドウ" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="a697c-208">[ **ウォッチ]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a697c-208">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="a697c-209">新しいウォッチ式を作成するには、ウォッチ **式の** 追加 \( ![ Add watch expression ](../media/add-expression-icon.msft.png) \) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-209">To create a new watch expression, select the **Add watch expression** \(![Add watch expression](../media/add-expression-icon.msft.png)\) button.</span></span>  
*   <span data-ttu-id="a697c-210">すべての既存の式の値を更新するには、[\( **Refresh** ![ \) ] ](../media/refresh-icon.msft.png) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-210">To refresh the values of all existing expressions, select the **Refresh** \(![Refresh](../media/refresh-icon.msft.png)\) button.</span></span>  <span data-ttu-id="a697c-211">コードをステップ実行すると、値が自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-211">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="a697c-212">ウォッチ式を削除するには、式を右クリックし、[ウォッチ式の **削除]** \( [ウォッチ式の削除] ![ \) を ](../media/delete-expression-icon.msft.png) 選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-212">To delete a watch expression, right-click the expression and then select **Delete watch expression** \(![Delete watch expression](../media/delete-expression-icon.msft.png)\).</span></span>  

## <a name="view-the-call-stack"></a><span data-ttu-id="a697c-213">呼び出し履歴の表示</span><span class="sxs-lookup"><span data-stu-id="a697c-213">View the call stack</span></span>  

<span data-ttu-id="a697c-214">コード行で一時停止中に、[呼び出\*\*\*\* し履歴] ウィンドウを使用して、この時点に移動した通話履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="a697c-214">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="a697c-215">その関数が呼び出されたコード行にジャンプするエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="a697c-215">Choose an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="a697c-216">青い矢印アイコンは、DevTools が現在強調表示している関数を表します。</span><span class="sxs-lookup"><span data-stu-id="a697c-216">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="[通話履歴] ウィンドウ" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="a697c-218">[ **通話履歴]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a697c-218">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="a697c-219">コード行で一時停止しない場合、[呼び出 **し履歴]** ウィンドウは空です。</span><span class="sxs-lookup"><span data-stu-id="a697c-219">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <a name="copy-stack-trace"></a><span data-ttu-id="a697c-220">スタック トレースのコピー</span><span class="sxs-lookup"><span data-stu-id="a697c-220">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="a697c-221">現在の通話履歴をクリップボードにコピーするには、[通話履歴] ウィンドウ\*\*\*\* の任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[スタック トレースのコピー] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="a697c-221">To copy the current call stack to the clipboard, hover anywhere in the **Call Stack** pane, open the contextual menu \(right-click\), and choose **Copy stack trace**.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="[スタック トレースのコピー] を選択する" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="a697c-223">[スタック **トレースのコピー] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a697c-223">Choose **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="a697c-224">次のコード スニペットは、出力の例です。</span><span class="sxs-lookup"><span data-stu-id="a697c-224">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onChoose (get-started.js:15)
```  

## <a name="ignore-a-script-or-pattern-of-scripts"></a><span data-ttu-id="a697c-225">スクリプトまたはスクリプトのパターンを無視する</span><span class="sxs-lookup"><span data-stu-id="a697c-225">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="a697c-226">デバッグ中にスクリプトを無視する場合は、スクリプトをライブラリ コードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a697c-226">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="a697c-227">ライブラリ コードとしてマークされている場合、スクリプトは [呼び\*\*\*\* 出し履歴] ウィンドウで見えなされ、コードをステップ実行するときにスクリプトの機能にステップ インする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a697c-227">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="a697c-228">たとえば、次のコード スニペットでは、サードパーティ ライブラリ `A` `lib` である行が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-228">For example, in the following code snippet, line `A` uses `lib`, which is a third-party library.</span></span>  <span data-ttu-id="a697c-229">デバッグ中の問題がサード パーティ製ライブラリに関連していないと確信している場合は、スクリプトをライブラリ コードとしてマークする方 **が理にかなっています**。</span><span class="sxs-lookup"><span data-stu-id="a697c-229">If you are confident that the problem you are debugging is not related to that third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

### <a name="mark-a-script-as-library-code-from-the-editor-pane"></a><span data-ttu-id="a697c-230">エディター ウィンドウからスクリプトをライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="a697c-230">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="a697c-231">エディター ウィンドウからスクリプトを **ライブラリ コード** としてマークするには、 **次の操作を行** います。</span><span class="sxs-lookup"><span data-stu-id="a697c-231">To mark a script as **Library code** from the **Editor** pane:</span></span>  

1.  <span data-ttu-id="a697c-232">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a697c-232">Open the file.</span></span>  
1.  <span data-ttu-id="a697c-233">任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a697c-233">Hover anywhere and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="a697c-234">[ **スクリプトの追加] を選択してリスト** を無視します (以前は [ライブラリ コードとして **マーク] と表示されています**)。</span><span class="sxs-lookup"><span data-stu-id="a697c-234">Choose **Add script to ignore list** (previously shown as **Mark as Library code**).</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="エディター ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="a697c-236">エディター ウィンドウからスクリプト **をライブラリ コード** として **マーク** する</span><span class="sxs-lookup"><span data-stu-id="a697c-236">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-the-call-stack-pane"></a><span data-ttu-id="a697c-237">[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする</span><span class="sxs-lookup"><span data-stu-id="a697c-237">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="a697c-238">[呼び出し履歴] **ウィンドウからスクリプトをライブラリ** コード **としてマークするには、次の操作を行** います。</span><span class="sxs-lookup"><span data-stu-id="a697c-238">To mark a script as **Library code** from the **Call Stack** pane:</span></span>  

1.  <span data-ttu-id="a697c-239">スクリプトから関数にカーソルを移動し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a697c-239">Hover on a function from the script and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="a697c-240">[ **スクリプトの追加] を選択してリスト** を無視します (以前は [ライブラリ コードとして **マーク] と表示されています**)。</span><span class="sxs-lookup"><span data-stu-id="a697c-240">Choose **Add script to ignore list** (previously shown as **Mark as Library code**).</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="[呼び出し履歴] ウィンドウからスクリプトをライブラリ コードとしてマークする" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="a697c-242">[呼び出し履歴] **ウィンドウからスクリプトを** ライブラリ **コードとしてマーク** する</span><span class="sxs-lookup"><span data-stu-id="a697c-242">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <a name="mark-a-script-as-library-code-from-settings"></a><span data-ttu-id="a697c-243">スクリプトをライブラリ コードとしてマーク設定</span><span class="sxs-lookup"><span data-stu-id="a697c-243">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="a697c-244">スクリプトの 1 つのスクリプトまたはパターンを次のコマンドからマーク**設定。**</span><span class="sxs-lookup"><span data-stu-id="a697c-244">To mark a single script or pattern of scripts from **Settings**:</span></span>  

1.  <span data-ttu-id="a697c-245">[ファイル[設定] を開きます][DevToolsCustomize]。</span><span class="sxs-lookup"><span data-stu-id="a697c-245">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="a697c-246">[ライブラリ コード **] 設定に移動** します。</span><span class="sxs-lookup"><span data-stu-id="a697c-246">Navigate to the **Library code** setting.</span></span>  
1.  <span data-ttu-id="a697c-247">[パターン **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a697c-247">Choose **Add pattern**.</span></span>  
1.  <span data-ttu-id="a697c-248">ライブラリ コードとしてマークするスクリプト名またはスクリプト名の正規表現パターンを **入力します**。</span><span class="sxs-lookup"><span data-stu-id="a697c-248">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="a697c-249">**追加** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a697c-249">Choose **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="スクリプトをライブラリ コードとしてマーク設定" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="a697c-251">スクリプトをライブラリ コード\*\*としてマーク設定\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a697c-251">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <a name="run-snippets-of-debug-code-from-any-page"></a><span data-ttu-id="a697c-252">任意のページからデバッグ コードのスニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="a697c-252">Run snippets of debug code from any page</span></span>  

<span data-ttu-id="a697c-253">コンソールで同じデバッグ コードを実行している場合は、スニペットを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a697c-253">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="a697c-254">スニペットは、DevTools 内で作成、保存、および実行するランタイム スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="a697c-254">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="a697c-255">「 [任意の Web ページで JavaScript のスニペットを実行する」を参照してください][DevToolsJavascriptSnippets]。</span><span class="sxs-lookup"><span data-stu-id="a697c-255">See [Run snippets of JavaScript on any webpage][DevToolsJavascriptSnippets].</span></span>  

## <a name="see-also"></a><span data-ttu-id="a697c-256">関連項目</span><span class="sxs-lookup"><span data-stu-id="a697c-256">See also</span></span>  

*   <span data-ttu-id="a697c-257">[はじめにデバッグ JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] - 画面キャプチャを使用して、既存のコードを使用した簡単で短いチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="a697c-257">[Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] - A simple, short tutorial using existing code, with screen captures.</span></span>
*   <span data-ttu-id="a697c-258">[ソース ツールの概要][DevToolsSourcesIndex] - ソース **ツールには** JavaScript デバッガーとエディターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a697c-258">[Sources tool overview][DevToolsSourcesIndex] - The **Sources** tool includes the JavaScript debugger and editor.</span></span>
*   <span data-ttu-id="a697c-259">[DevTools を使用して JavaScript Microsoft Edge無効にします][DevToolsJavascriptDisable]。</span><span class="sxs-lookup"><span data-stu-id="a697c-259">[Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="a697c-260">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a697c-260">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "DevTools アプリケーションでブレークポイントを使用してコードMicrosoft Edgeする|Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "DevTools サーバーを使用Microsoft Edge JavaScript を|Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "DevTools を使用して任意のページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  
[DevToolsSourcesIndex]: ../sources/index.md "ソース ツールの概要|Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "DevTools Microsoft Edgeのカスタマイズ|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="a697c-267">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a697c-267">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a697c-268">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="a697c-268">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a697c-270">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a697c-270">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
