---
description: Microsoft Edge DevTools で使用されていない JavaScript と CSS コードを検索して分析する方法について説明します。
title: Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 08c4daaabd30296b53ad57a81caa0e7b155a4fc9
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125189"
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

# <span data-ttu-id="a5b2b-104">Microsoft Edge DevTools の [カバレッジ] タブで使用されていない JavaScript と CSS コードを見つける</span><span class="sxs-lookup"><span data-stu-id="a5b2b-104">Find Unused JavaScript And CSS Code With The Coverage Tab In Microsoft Edge DevTools</span></span>  

<span data-ttu-id="a5b2b-105">Microsoft Edge の DevTools の [カバレッジ] タブは、使用されていない JavaScript と CSS コードを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-105">The Coverage tab in Microsoft Edge DevTools helps you find unused JavaScript and CSS code.</span></span>  <span data-ttu-id="a5b2b-106">使用されていないコードを削除すると、ページの読み込みが速くなり、モバイルユーザーの携帯電話のデータが保存される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-106">Removing unused code may speed up your page load and save your mobile users cellular data.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage.msft.png":::
   <span data-ttu-id="a5b2b-108">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="a5b2b-108">Analyzing code coverage</span></span>  
:::image-end:::  

> [!WARNING]
> <span data-ttu-id="a5b2b-109">使用されていないコードの検索は比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-109">Finding unused code is relatively easy.</span></span>  <span data-ttu-id="a5b2b-110">ただし、コードベースをリファクタリングして、各ページが必要な JavaScript と CSS を確実に出荷することが難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-110">But refactoring a codebase so that each page only ships the JavaScript and CSS that it needs may be difficult.</span></span>  <span data-ttu-id="a5b2b-111">このガイドでは、コードベースをリファクターして使用されていないコードを回避する方法については説明しません。これらの refactors はテクノロジスタックに依存しているためです。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-111">This guide does not cover how to refactor a codebase to avoid unused code because these refactors depend highly on your technology stack.</span></span>  

## <span data-ttu-id="a5b2b-112">概要</span><span class="sxs-lookup"><span data-stu-id="a5b2b-112">Overview</span></span>  

<span data-ttu-id="a5b2b-113">使用されていない JavaScript または CSS は、web 開発での一般的な問題です。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-113">Shipping unused JavaScript or CSS is a common problem in web development.</span></span>  <span data-ttu-id="a5b2b-114">たとえば、ページで [ブートストラップボタンコンポーネント][BootstrapButtons] を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-114">For example, suppose that you want to use [Bootstrap button component][BootstrapButtons] on your page.</span></span>  <span data-ttu-id="a5b2b-115">Button コンポーネントを使用するには、次のように HTML のブートストラップスタイルシートへのリンクを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-115">To use the button component you need to add a link to the Bootstrap stylesheet in your HTML, like this:</span></span>  

```html
...
<head>
    ...
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    ...
</head>
...
```  

<span data-ttu-id="a5b2b-116">このスタイルシートには、button コンポーネントのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-116">This stylesheet does not just include the code for the button component.</span></span>  <span data-ttu-id="a5b2b-117">このファイルには、 **すべて** のブートストラップコンポーネントの CSS が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-117">It contains the CSS for **all** of the Bootstrap components.</span></span>  <span data-ttu-id="a5b2b-118">ただし、他のブートストラップコンポーネントは使用していません。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-118">But you are not using any of the other Bootstrap components.</span></span>  <span data-ttu-id="a5b2b-119">このため、ページでは不要な CSS をダウンロードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-119">So your page is downloading a bunch of CSS that it does not need.</span></span>  <span data-ttu-id="a5b2b-120">このエクストラ CSS は、次のような理由で問題になります。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-120">This extra CSS is a problem for the following reasons.</span></span>  

*   <span data-ttu-id="a5b2b-121">余分なコードを使用すると、ページの読み込み速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-121">The extra code slows down your page load.</span></span>  <!--See [Render-Blocking CSS][render].  -->  
*   <span data-ttu-id="a5b2b-122">ユーザーがモバイルデバイスでページにアクセスすると、追加のコードによって携帯電話のデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-122">If a user accesses the page on a mobile device, the extra code uses up their cellular data.</span></span>  
    
<!--[render]: /web/fundamentals/performance/critical-rendering-path/render-blocking-css  -->  

## <span data-ttu-id="a5b2b-123">[カバレッジ] タブを開く</span><span class="sxs-lookup"><span data-stu-id="a5b2b-123">Open the Coverage tab</span></span>  

1.  <span data-ttu-id="a5b2b-124">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-124">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="a5b2b-125">入力を開始し、[ `coverage` **カバレッジの表示** ] コマンドを選択して、コマンドを `Enter` 実行します。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-125">Start typing `coverage`, select the **Show Coverage** command, and then select `Enter` to run the command.</span></span>  <span data-ttu-id="a5b2b-126">[ **補充** ] タブが **引き出し**で開きます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-126">The **Coverage** tab opens in the **Drawer**.</span></span>  

    :::image type="complex" source="../media/coverage-console-drawer-coverage-empty.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-console-drawer-coverage-empty.msft.png":::
       <span data-ttu-id="a5b2b-128">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="a5b2b-128">The **Coverage** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a5b2b-129">コードカバレッジの記録</span><span class="sxs-lookup"><span data-stu-id="a5b2b-129">Record code coverage</span></span>  

1.  <span data-ttu-id="a5b2b-130">[ **カバレッジ** ] タブで、次のいずれかのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-130">Click one of the following buttons in the **Coverage** tab:</span></span>  
    *   <span data-ttu-id="a5b2b-131">**Start Instrumenting Coverage And Reload Page** ![ ][ImageReloadIcon] ページの読み込みに必要なコードを確認するには、[インストルメント化の開始] と [ページの再読み込み] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-131">Choose **Start Instrumenting Coverage And Reload Page** \(![Start Instrumenting Coverage And Reload Page][ImageReloadIcon]\) if you want to see what code is needed to load the page.</span></span>  
    *   <span data-ttu-id="a5b2b-132">**Instrument Coverage** ![ ][ImageRecordIcon] ページを操作した後で使用されるコードを確認する場合は、[インストルメント化の対象] ([インストルメントのカバレッジ]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-132">Choose **Instrument Coverage** \(![Instrument Coverage][ImageRecordIcon]\) if you want to see what code is used after interacting with the page.</span></span>  
1.  <span data-ttu-id="a5b2b-133">コードカバレッジの記録を停止する場合は **、[インストルメントの実装を停止し、結果を表示** する ( ![ インストルメント化の停止と結果の表示)] を選び ][ImageStopIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-133">Choose **Stop Instrumenting Coverage And Show Results** \(![Stop Instrumenting Coverage And Show Results][ImageStopIcon]\) when you want to stop recording code coverage.</span></span>  
    
## <span data-ttu-id="a5b2b-134">コードカバレッジの分析</span><span class="sxs-lookup"><span data-stu-id="a5b2b-134">Analyze code coverage</span></span>  

<span data-ttu-id="a5b2b-135">[ **カバレッジ** ] タブの表には、分析されたリソースと、各リソース内で使用されているコードの量が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-135">The table in the **Coverage** tab shows you what resources were analyzed, and how much code is used within each resource.</span></span>  <span data-ttu-id="a5b2b-136">[ **ソース** ] パネルで行をクリックしてそのリソースを開き、使用されているコードと未使用コードの行ごとの内訳を確認します。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-136">Click a row to open that resource in the **Sources** panel and see a line-by-line breakdown of used code and unused code.</span></span>  

:::image type="complex" source="../media/coverage-sources-resource-drawer-coverage-selected.msft.png" alt-text="コードカバレッジの分析" lightbox="../media/coverage-sources-resource-drawer-coverage-selected.msft.png":::
   <span data-ttu-id="a5b2b-138">コードカバレッジレポート</span><span class="sxs-lookup"><span data-stu-id="a5b2b-138">A code coverage report</span></span>  
:::image-end:::  

*   <span data-ttu-id="a5b2b-139">**Url**列は、分析されたリソースの url です。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-139">The **URL** column is the URL of the resource that was analyzed.</span></span>  
*   <span data-ttu-id="a5b2b-140">[ **Type** ] 列には、リソースに CSS、JavaScript、またはその両方が含まれているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-140">The **Type** column says whether the resource contains CSS, JavaScript, or both.</span></span>  
*   <span data-ttu-id="a5b2b-141">**Total bytes**列は、リソースの合計サイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-141">The **Total Bytes** column is the total size of the resource in bytes.</span></span>  
*   <span data-ttu-id="a5b2b-142">**未使用バイト**列は、使用されなかったバイト数です。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-142">The **Unused Bytes** column is the number of bytes that were not used.</span></span>  
*   <span data-ttu-id="a5b2b-143">最後の名前が付いていない列は、[ **合計のバイト** 数] 列と [ **未使用のバイト数** ] 列の視覚エフェクトです。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-143">The last, unnamed column is a visualization of the **Total Bytes** and **Unused Bytes** columns.</span></span>  <span data-ttu-id="a5b2b-144">バーの赤い部分は未使用のバイトです。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-144">The red section of the bar is unused bytes.</span></span>  <span data-ttu-id="a5b2b-145">緑のセクションは、バイトを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-145">The green section is used bytes.</span></span>  
    
## <span data-ttu-id="a5b2b-146">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a5b2b-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageReloadIcon]: ../media/reload-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png  
[ImageStopIcon]: ../media/stop-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  

[BootstrapButtons]: https://getbootstrap.com/docs/4.3/components/buttons "ボタン-ブートストラップ"  

> [!NOTE]
> <span data-ttu-id="a5b2b-149">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-149">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a5b2b-150">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/coverage/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-150">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/coverage/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a5b2b-152">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-152">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
