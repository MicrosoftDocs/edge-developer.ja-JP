---
description: Microsoft Edge DevTools で使用されていない JavaScript と CSS コードを検索して分析する方法について説明します。
title: Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 19bc15578e00e5a9f3389529f589e9790280a0e4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993094"
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





# <span data-ttu-id="fc5bf-104">Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける</span><span class="sxs-lookup"><span data-stu-id="fc5bf-104">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="fc5bf-105">Microsoft Edge の DevTools の [カバレッジ] タブは、使用されていない JavaScript と CSS コードを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-105">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="fc5bf-106">使用されていないコードを削除すると、ページの読み込みが速くなり、モバイルユーザーの携帯電話のデータが保存される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="fc5bf-108">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="fc5bf-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="fc5bf-109">使用されていないコードの検索は比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="fc5bf-110">ただし、コードベースをリファクタリングして、各ページが必要な JavaScript と CSS を確実に出荷することが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="fc5bf-111">このガイドでは、コードベースをリファクターして使用されていないコードを回避する方法については説明しません。これらの refactors はテクノロジスタックに依存しているためです。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <span data-ttu-id="fc5bf-112">概要</span><span class="sxs-lookup"><span data-stu-id="fc5bf-112">Overview</span></span>   

<span data-ttu-id="fc5bf-113">使用されていない JavaScript または CSS は、web 開発での一般的な問題です。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="fc5bf-114">たとえば、ページで [ブートストラップボタンコンポーネント][BootstrapButtons] を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="fc5bf-115">Button コンポーネントを使用するには、次のように HTML のブートストラップスタイルシートへのリンクを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="fc5bf-116">このスタイルシートには、button コンポーネントのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="fc5bf-117">このファイルには、 **すべて** のブートストラップコンポーネントの CSS が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="fc5bf-118">ただし、他のブートストラップコンポーネントは使用していません。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="fc5bf-119">このため、ページでは不要な CSS をダウンロードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="fc5bf-120">このエクストラ CSS は、次のような理由で問題になります。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="fc5bf-121">余分なコードを使用すると、ページの読み込み速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-121">The extra code slows down your page load.</span></span>  <!--See [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="fc5bf-122">ユーザーがモバイルデバイスでページにアクセスすると、追加のコードによって携帯電話のデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <span data-ttu-id="fc5bf-123">[カバレッジ] タブを開く</span><span class="sxs-lookup"><span data-stu-id="fc5bf-123">Open the Coverage tab</span></span>   

1.  <span data-ttu-id="fc5bf-124">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="fc5bf-125">入力を開始し、[ `coverage` **カバレッジの表示** ] コマンドを選択して、キーを押してコマンドを `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-125">Start typing `coverage`, select the **Show Coverage** command, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="fc5bf-126">[ **補充** ] タブが **引き出し**で開きます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-126">The **Coverage** tab opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="fc5bf-128">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="fc5bf-128">The **Coverage** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fc5bf-129">コードカバレッジの記録</span><span class="sxs-lookup"><span data-stu-id="fc5bf-129">Record code coverage</span></span>   

1.  <span data-ttu-id="fc5bf-130">[ **カバレッジ** ] タブで、次のいずれかのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-130">Click one of the following buttons in the **Coverage** tab:</span></span>  
    *   <span data-ttu-id="fc5bf-131">ページの読み込みに必要なコードを確認したい場合は、[ **インストルメントの開始] をクリックし、ページを再読み込み** し ![ ます (インストルメント化とページの再読み込みの開始 ][ImageReloadIcon] )。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-131">Click **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="fc5bf-132">**Instrument Coverage** ![ ][ImageRecordIcon] ページを操作した後に使用されたコードを確認する場合は、[音色の範囲 \ (インストルメント化の対象)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-132">Click **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="fc5bf-133">**Stop Instrumenting Coverage And Show Results** ![ ][ImageStopIcon] コードカバレッジの記録を停止する場合は、[インストルメントのインストルメンテーションを停止し、結果を表示します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-133">Click **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span></span>  
    
## <span data-ttu-id="fc5bf-134">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="fc5bf-134">Analyze code coverage</span></span>   

<span data-ttu-id="fc5bf-135">[ **カバレッジ** ] タブの表には、分析されたリソースと、各リソース内で使用されているコードの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-135">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="fc5bf-136">[ **ソース** ] パネルで行をクリックしてそのリソースを開き、使用されているコードと未使用コードの行ごとの内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-136">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コードカバレッジレポート" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="fc5bf-138">コードカバレッジレポート</span><span class="sxs-lookup"><span data-stu-id="fc5bf-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="fc5bf-139">**Url**列は、分析されたリソースの url です。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="fc5bf-140">[ **Type** ] 列には、リソースに CSS、JavaScript、またはその両方が含まれているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="fc5bf-141">**Total bytes**列は、リソースの合計サイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="fc5bf-142">**未使用バイト**列は、使用されなかったバイト数です。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="fc5bf-143">最後の名前が付いていない列は、[ **合計のバイト** 数] 列と [ **未使用のバイト数** ] 列の視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="fc5bf-144">バーの赤い部分は未使用のバイトです。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="fc5bf-145">緑のセクションは、バイトを使用しています。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-145">The green section is used bytes.</span></span>  
    
<!--  
 


-->  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "ボタン-ブートストラップ"  

> [!NOTE]
> <span data-ttu-id="fc5bf-148">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-148">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fc5bf-149">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-149">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="fc5bf-151">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="fc5bf-151">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
