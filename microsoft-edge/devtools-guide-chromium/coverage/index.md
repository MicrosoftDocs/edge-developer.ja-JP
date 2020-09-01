---
title: Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1c03140199b26bca39e69cdfbe33cd1c524257fe
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10981871"
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





# <span data-ttu-id="d6156-103">Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける</span><span class="sxs-lookup"><span data-stu-id="d6156-103">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="d6156-104">Microsoft Edge の DevTools の [カバレッジ] タブは、使用されていない JavaScript と CSS コードを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6156-104">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="d6156-105">使用されていないコードを削除すると、ページの読み込みが速くなり、モバイルユーザーの携帯電話のデータが保存される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6156-105">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="d6156-107">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="d6156-107">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="d6156-108">使用されていないコードの検索は比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="d6156-108">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="d6156-109">ただし、コードベースをリファクタリングして、各ページが必要な JavaScript と CSS を確実に出荷することが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6156-109">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="d6156-110">このガイドでは、コードベースをリファクターして使用されていないコードを回避する方法については説明しません。これらの refactors はテクノロジスタックに依存しているためです。</span><span class="sxs-lookup"><span data-stu-id="d6156-110">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <span data-ttu-id="d6156-111">概要</span><span class="sxs-lookup"><span data-stu-id="d6156-111">Overview</span></span>   

<span data-ttu-id="d6156-112">使用されていない JavaScript または CSS は、web 開発での一般的な問題です。</span><span class="sxs-lookup"><span data-stu-id="d6156-112">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="d6156-113">たとえば、ページで [ブートストラップボタンコンポーネント][BootstrapButtons] を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="d6156-113">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="d6156-114">Button コンポーネントを使用するには、次のように HTML のブートストラップスタイルシートへのリンクを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6156-114">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="d6156-115">このスタイルシートには、button コンポーネントのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d6156-115">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="d6156-116">このファイルには、 **すべて** のブートストラップコンポーネントの CSS が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6156-116">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="d6156-117">ただし、他のブートストラップコンポーネントは使用していません。</span><span class="sxs-lookup"><span data-stu-id="d6156-117">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="d6156-118">このため、ページでは不要な CSS をダウンロードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="d6156-118">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="d6156-119">このエクストラ CSS は、次のような理由で問題になります。</span><span class="sxs-lookup"><span data-stu-id="d6156-119">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="d6156-120">余分なコードを使用すると、ページの読み込み速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="d6156-120">The extra code slows down your page load.</span></span>  <!--See [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="d6156-121">ユーザーがモバイルデバイスでページにアクセスすると、追加のコードによって携帯電話のデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6156-121">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <span data-ttu-id="d6156-122">[カバレッジ] タブを開く</span><span class="sxs-lookup"><span data-stu-id="d6156-122">Open the Coverage tab</span></span>   

1.  <span data-ttu-id="d6156-123">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="d6156-123">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="d6156-124">入力を開始し、[ `coverage` **カバレッジの表示** ] コマンドを選択して、キーを押してコマンドを `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="d6156-124">Start typing `coverage`, select the **Show Coverage** command, and then press `Enter` to run the command.</span></span>  <span data-ttu-id="d6156-125">[ **補充** ] タブが **引き出し**で開きます。</span><span class="sxs-lookup"><span data-stu-id="d6156-125">The **Coverage** tab opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="d6156-127">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="d6156-127">The **Coverage** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d6156-128">コードカバレッジの記録</span><span class="sxs-lookup"><span data-stu-id="d6156-128">Record code coverage</span></span>   

1.  <span data-ttu-id="d6156-129">[ **カバレッジ** ] タブで、次のいずれかのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6156-129">Click one of the following buttons in the **Coverage** tab:</span></span>  
    *   <span data-ttu-id="d6156-130">ページの読み込みに必要なコードを確認したい場合は、[ **インストルメントの開始] をクリックし、ページを再読み込み** し ![ ます (インストルメント化とページの再読み込みの開始 ][ImageReloadIcon] )。</span><span class="sxs-lookup"><span data-stu-id="d6156-130">Click **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="d6156-131">**Instrument Coverage** ![ ][ImageRecordIcon] ページを操作した後に使用されたコードを確認する場合は、[音色の範囲 \ (インストルメント化の対象)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6156-131">Click **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="d6156-132">**Stop Instrumenting Coverage And Show Results** ![ ][ImageStopIcon] コードカバレッジの記録を停止する場合は、[インストルメントのインストルメンテーションを停止し、結果を表示します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6156-132">Click **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span></span>  
    
## <span data-ttu-id="d6156-133">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="d6156-133">Analyze code coverage</span></span>   

<span data-ttu-id="d6156-134">[ **カバレッジ** ] タブの表には、分析されたリソースと、各リソース内で使用されているコードの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6156-134">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="d6156-135">[ **ソース** ] パネルで行をクリックしてそのリソースを開き、使用されているコードと未使用コードの行ごとの内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="d6156-135">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コードカバレッジレポート" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="d6156-137">コードカバレッジレポート</span><span class="sxs-lookup"><span data-stu-id="d6156-137">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="d6156-138">**Url**列は、分析されたリソースの url です。</span><span class="sxs-lookup"><span data-stu-id="d6156-138">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="d6156-139">[ **Type** ] 列には、リソースに CSS、JavaScript、またはその両方が含まれているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="d6156-139">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="d6156-140">**Total bytes**列は、リソースの合計サイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="d6156-140">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="d6156-141">**未使用バイト**列は、使用されなかったバイト数です。</span><span class="sxs-lookup"><span data-stu-id="d6156-141">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="d6156-142">最後の名前が付いていない列は、[ **合計のバイト** 数] 列と [ **未使用のバイト数** ] 列の視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="d6156-142">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="d6156-143">バーの赤い部分は未使用のバイトです。</span><span class="sxs-lookup"><span data-stu-id="d6156-143">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="d6156-144">緑のセクションは、バイトを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d6156-144">The green section is used bytes.</span></span>  
    
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
> <span data-ttu-id="d6156-147">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6156-147">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d6156-148">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="d6156-148">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="d6156-150">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="d6156-150">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
