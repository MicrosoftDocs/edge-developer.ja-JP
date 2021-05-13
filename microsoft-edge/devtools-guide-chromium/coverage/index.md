---
description: DevTools で使用されていない JavaScript コードと CSS コードをMicrosoft Edgeする方法。
title: DevTools の [カバレッジ] パネルで未使用の JavaScript および CSS コードMicrosoft Edge検索する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b31d14feac13a907ca0c5ce7ef702bcdef375ad5
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564463"
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
# <a name="find-unused-javascript-and-css-code-with-the-coverage-panel-in-microsoft-edge-devtools"></a><span data-ttu-id="6423c-104">DevTools の [カバレッジ] パネルで未使用の JavaScript コードと CSS コードMicrosoft Edge検索する</span><span class="sxs-lookup"><span data-stu-id="6423c-104">Find unused JavaScript and CSS code with the Coverage panel in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="6423c-105">**DevTools**の [Microsoft Edge] パネルを使用すると、使用されていない JavaScript コードと CSS コードを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6423c-105">The **Coverage** panel in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="6423c-106">未使用のコードを削除すると、ページの読み込み速度が上がり、モバイル ユーザーの携帯電話データが保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6423c-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コード 範囲の分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="6423c-108">コード 範囲の分析</span><span class="sxs-lookup"><span data-stu-id="6423c-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="6423c-109">使用されていないコードを見つけるのは比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="6423c-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="6423c-110">ただし、コードベースをリファクタリングして、必要な JavaScript と CSS のみを各ページに提供するのは難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="6423c-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="6423c-111">このガイドでは、これらのリファクタリングがテクノロジ スタックに大きな依存を持つため、コードベースをリファクタリングして未使用のコードを回避する方法については取り上げない。</span><span class="sxs-lookup"><span data-stu-id="6423c-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <a name="overview"></a><span data-ttu-id="6423c-112">概要</span><span class="sxs-lookup"><span data-stu-id="6423c-112">Overview</span></span>  

<span data-ttu-id="6423c-113">未使用の JavaScript または CSS の配布は、Web 開発で一般的な問題です。</span><span class="sxs-lookup"><span data-stu-id="6423c-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="6423c-114">たとえば、ページでブートストラップ ボタン コンポーネントを [使用すると][BootstrapButtons] します。</span><span class="sxs-lookup"><span data-stu-id="6423c-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="6423c-115">ボタン コンポーネントを使用するには、HTML のブートストラップ スタイルシートへのリンクを次のように追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6423c-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="6423c-116">このスタイルシートには、ボタン コンポーネントのコードが含まれるだけではありません。</span><span class="sxs-lookup"><span data-stu-id="6423c-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="6423c-117">すべてのブートストラップ **コンポーネントの** CSS が含まれている。</span><span class="sxs-lookup"><span data-stu-id="6423c-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="6423c-118">ただし、他のブートストラップ コンポーネントは使用していない。</span><span class="sxs-lookup"><span data-stu-id="6423c-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="6423c-119">したがって、ページは必要ない CSS の束をダウンロードしています。</span><span class="sxs-lookup"><span data-stu-id="6423c-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="6423c-120">この追加の CSS は、次の理由で問題です。</span><span class="sxs-lookup"><span data-stu-id="6423c-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="6423c-121">余分なコードを使用すると、ページの読み込み速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="6423c-121">The extra code slows down your page load.</span></span>  <!--Navigate to [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="6423c-122">ユーザーがモバイル デバイス上のページにアクセスした場合、追加のコードは携帯データを使用します。</span><span class="sxs-lookup"><span data-stu-id="6423c-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <a name="open-the-coverage-panel"></a><span data-ttu-id="6423c-123">[カバレッジ] パネルを開く</span><span class="sxs-lookup"><span data-stu-id="6423c-123">Open the Coverage panel</span></span>  

1.  <span data-ttu-id="6423c-124">[コマンド メニューを開きます][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="6423c-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="6423c-125">入力を開始 `coverage` し、[カバレッジの表示] コマンド **を** 選択し、コマンド `Enter` を実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6423c-125">Start typing `coverage`, select the **Show Coverage** command, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="6423c-126">[ **引き出** し] に [カバレッジ] パネルが **開きます**。</span><span class="sxs-lookup"><span data-stu-id="6423c-126">The **Coverage** panel opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="[カバレッジ] パネル" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="6423c-128">[ **カバレッジ]** パネル</span><span class="sxs-lookup"><span data-stu-id="6423c-128">The **Coverage** panel</span></span>  
    :::image-end:::  
    
## <a name="record-code-coverage"></a><span data-ttu-id="6423c-129">レコード コード範囲</span><span class="sxs-lookup"><span data-stu-id="6423c-129">Record code coverage</span></span>  

1.  <span data-ttu-id="6423c-130">[カバレッジ] パネルで、次のいずれかのボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6423c-130">Choose one of the following buttons in the **Coverage** panel.</span></span>  
    *   <span data-ttu-id="6423c-131">ページ **の読み込みに** 必要なコードを確認する場合は、[インストルメントカバレッジの開始とページの再読み込み]\(インストルメントカバレッジの開始とページの再読み込み ![ ](../media/reload-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6423c-131">Choose **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page](../media/reload-icon.msft.png)\) if you want to review what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="6423c-132">ページ **を操作した** 後に使用するコードを確認する場合は、[Instrument Coverage \( Instrument ![ Coverage ](../media/record-icon.msft.png) \) ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6423c-132">Choose **Instrument Coverage** \(![Instrument Coverage](../media/record-icon.msft.png)\) if you want to review what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="6423c-133">コード **カバレッジの記録を停止する場合は、[** インストルメントカバレッジの停止と結果の表示] \( Stop Instrumenting Coverage and Show Results ![ ](../media/stop-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6423c-133">Choose **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results](../media/stop-icon.msft.png)\) when you want to stop recording code coverage.</span></span>  
    
## <a name="analyze-code-coverage"></a><span data-ttu-id="6423c-134">コード範囲の分析</span><span class="sxs-lookup"><span data-stu-id="6423c-134">Analyze code coverage</span></span>  

<span data-ttu-id="6423c-135">[カバレッジ] パネル **の表** には、分析されたリソースと、各リソース内で使用されるコードの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6423c-135">The table in the **Coverage** panel displays the resources that were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="6423c-136">[ソース] ツールでリソースを開\*\*\*\* く行を選択し、使用されているコードと未使用のコードの 1 行に 1 行の内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="6423c-136">Choose a row to open that resource in the **Sources** tool and review a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コード カバレッジ レポート" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="6423c-138">コード カバレッジ レポート</span><span class="sxs-lookup"><span data-stu-id="6423c-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="6423c-139">**[URL]** 列は、分析されたリソースの URL です。</span><span class="sxs-lookup"><span data-stu-id="6423c-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="6423c-140">**[Type]** 列には、リソースに CSS、JavaScript、または両方が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6423c-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="6423c-141">[ **合計バイト数]** 列は、リソースの合計サイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="6423c-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="6423c-142">[ **未使用のバイト数** ] 列は、使用されていないバイト数です。</span><span class="sxs-lookup"><span data-stu-id="6423c-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="6423c-143">最後の名前のない列は、[合計バイト数]\*\*\*\* 列と [未使用バイト] 列**を視覚化**します。</span><span class="sxs-lookup"><span data-stu-id="6423c-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="6423c-144">バーの赤いセクションは未使用のバイトです。</span><span class="sxs-lookup"><span data-stu-id="6423c-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="6423c-145">緑色のセクションはバイト数を使用します。</span><span class="sxs-lookup"><span data-stu-id="6423c-145">The green section is used bytes.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6423c-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6423c-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "[DevTools コマンド] メニューの [Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "ボタン - ブートストラップ"  

> [!NOTE]
> <span data-ttu-id="6423c-149">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6423c-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6423c-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="6423c-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6423c-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6423c-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
