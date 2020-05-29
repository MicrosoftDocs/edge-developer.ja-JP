---
title: Microsoft Edge DevTools の問題を見つけて解決する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: cd6123f235af4ccb87338e1d4db12c03a93a9eaa
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684860"
---
<!-- Copyright Sam Dutton 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  





# <span data-ttu-id="f7826-103">Microsoft Edge DevTools の問題を見つけて解決する</span><span class="sxs-lookup"><span data-stu-id="f7826-103">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>   



<span data-ttu-id="f7826-104">Microsoft Edge DevTools の [**問題**] ツールは、**本体**の通知の疲労と低優先メールを削減します。</span><span class="sxs-lookup"><span data-stu-id="f7826-104">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="f7826-105">Cookie の問題や混在したコンテンツなど、ブラウザーで検出された問題の解決策を見つけるために使います。</span><span class="sxs-lookup"><span data-stu-id="f7826-105">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="f7826-106">Microsoft Edge 84 の**問題**ツールでは、次の3種類の問題がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f7826-106">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="f7826-107">Cookie に関する問題</span><span class="sxs-lookup"><span data-stu-id="f7826-107">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="f7826-108">混在したコンテンツ</span><span class="sxs-lookup"><span data-stu-id="f7826-108">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="f7826-109">COEP の問題</span><span class="sxs-lookup"><span data-stu-id="f7826-109">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="f7826-110">Microsoft edge DevTools チームは、今後のバージョンの Microsoft Edge で、より多くの問題の種類をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="f7826-110">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <span data-ttu-id="f7826-111">DevTools のドローワで問題ツールを開く</span><span class="sxs-lookup"><span data-stu-id="f7826-111">Open the Issues tool in the DevTools drawer</span></span>   

1.  <span data-ttu-id="f7826-112">修正する問題が含まれているページ ( [samesite-sandbox.glitch.me][GlitchSamesiteSandbox]など) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f7826-112">Visit a page, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="f7826-113">[DevTools を開き][DevtoolsOpen]ます。</span><span class="sxs-lookup"><span data-stu-id="f7826-113">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="f7826-114">黄色の警告バーの [**問題に移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7826-114">Select the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="問題が検出されたときに黄色の警告バーにある [懸案事項] ボタンに移動する" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="f7826-116">図 1. </span><span class="sxs-lookup"><span data-stu-id="f7826-116">Figure 1.</span></span>  <span data-ttu-id="f7826-117">問題が検出されたときの黄色の警告バーの **[問題に移動**] ボタン。</span><span class="sxs-lookup"><span data-stu-id="f7826-117">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="f7826-118">または、[**その他のツール**] メニューから [**問題**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7826-118">Alternatively, select **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="[その他のツール] メニューの [問題] ツール" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="f7826-120">図 2. </span><span class="sxs-lookup"><span data-stu-id="f7826-120">Figure 2.</span></span>  <span data-ttu-id="f7826-121">[**その他のツール**] メニューの [**問題**] ツール</span><span class="sxs-lookup"><span data-stu-id="f7826-121">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="f7826-122">必要に応じて、[**ページの再読み込み**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7826-122">Select the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="[ページの再読み込み] ボタンがある DevTools ドローワの問題ツール" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="f7826-124">図 3. </span><span class="sxs-lookup"><span data-stu-id="f7826-124">Figure 3.</span></span>  <span data-ttu-id="f7826-125">[**ページの再読み込み**] ボタンがある Devtools ドローワの**問題**ツール</span><span class="sxs-lookup"><span data-stu-id="f7826-125">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="f7826-126">**コンソール**で報告される問題は、次の画像の cookie の警告など、非常に理解しにくくなります。</span><span class="sxs-lookup"><span data-stu-id="f7826-126">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="f7826-127">報告された問題に基づいて、何を行う必要があるかが明確でない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7826-127">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="3つの cookie の問題が発生した DevTools の [問題] ツール" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="f7826-129">図 4: </span><span class="sxs-lookup"><span data-stu-id="f7826-129">Figure 4.</span></span>  <span data-ttu-id="f7826-130">3つの cookie の問題が発生した DevTools の [**問題**] ツール</span><span class="sxs-lookup"><span data-stu-id="f7826-130">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f7826-131">懸案事項ツールのアイテムを表示する</span><span class="sxs-lookup"><span data-stu-id="f7826-131">View items in the Issues tool</span></span>   

<span data-ttu-id="f7826-132">DevTools のドローワの**問題**ツールでは、構造化され、集計され、実行可能な方法で警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7826-132">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="f7826-133">問題を修正し、影響を受けるリソースを見つける方法についてのガイダンスを表示するには、[**案件**] ツールのアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7826-133">Select an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="[問題] ツールで、クロスサイト cookie をセキュリティで保護された問題としてマークする" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="f7826-135">図 5: </span><span class="sxs-lookup"><span data-stu-id="f7826-135">Figure 5.</span></span>  <span data-ttu-id="f7826-136">[**問題**] ツールで、**クロスサイト Cookie をセキュリティで保護された問題としてマーク**する</span><span class="sxs-lookup"><span data-stu-id="f7826-136">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="f7826-137">各項目には、次の4つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="f7826-137">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="f7826-138">問題を説明するヘッドライン。</span><span class="sxs-lookup"><span data-stu-id="f7826-138">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="f7826-139">コンテキストとソリューションを提供する説明。</span><span class="sxs-lookup"><span data-stu-id="f7826-139">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="f7826-140">[ネットワーク] パネルなどの適切な DevTools コンテキスト内のリソースにリンクしている、**影響を受けるリソース**セクション。</span><span class="sxs-lookup"><span data-stu-id="f7826-140">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="f7826-141">詳しいガイダンスへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="f7826-141">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="f7826-142">[影響を**受けるリソース**] 内のアイテムを選択して、詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7826-142">Select items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="f7826-143">次の例では、1つの cookie と2つの要求が**セキュリティで保護された問題としてマークさ**れています。</span><span class="sxs-lookup"><span data-stu-id="f7826-143">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="[問題の引き出し] タブで表示される影響を受けるリソース" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="f7826-145">図 6. </span><span class="sxs-lookup"><span data-stu-id="f7826-145">Figure 6.</span></span>  <span data-ttu-id="f7826-146">DevTools のドローワの [**問題**] ツールで、影響を受けるリソースが開かれる</span><span class="sxs-lookup"><span data-stu-id="f7826-146">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f7826-147">コンテキストの問題を表示する</span><span class="sxs-lookup"><span data-stu-id="f7826-147">View issues in context</span></span>   

1.  <span data-ttu-id="f7826-148">リソースリンクを選んで、DevTools 内の適切なコンテキストで項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7826-148">Select a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="f7826-149">次の例では、 `samesite-sandbox.glitch.me` [**要求**] の下で、その要求に関連付けられている cookie を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7826-149">In the following example, select `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="DevTools ネットワークパネルで影響を受ける cookie を表示する" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="f7826-151">図 7.</span><span class="sxs-lookup"><span data-stu-id="f7826-151">Figure 7.</span></span>  <span data-ttu-id="f7826-152">DevTools ネットワークパネルで影響を受ける cookie を表示する</span><span class="sxs-lookup"><span data-stu-id="f7826-152">View the affected cookie in the DevTools Network panel</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="f7826-153">スクロールして、問題のあるアイテムを表示します。次の例では、cookie が表示されます。 `ck02`</span><span class="sxs-lookup"><span data-stu-id="f7826-153">Scroll to view the item with a problem: for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="f7826-154">**SameSite**列の上にマウスポインターを移動すると、 `None` 問題が検出された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7826-154">Hover over the **SameSite** column to see the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools ネットワークパネルの ck02 cookie の SameSite 列の値なし" lightbox="../media/issues-tab-view-issue.msft.png":::
       <span data-ttu-id="f7826-156">図 8.</span><span class="sxs-lookup"><span data-stu-id="f7826-156">Figure 8.</span></span>  `None` <span data-ttu-id="f7826-157">**SameSite** `ck02` devtools**ネットワーク**パネルの cookie の [SameSite] 列の値</span><span class="sxs-lookup"><span data-stu-id="f7826-157">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** panel</span></span>  
    :::image-end:::  

<!--## Feedback  -->  



<!-- image links -->  

<!-- links -->  

[DevtoolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie のテスト |故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite クッキー |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混在したコンテンツ |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "Embedder のクロスオリジンのポリシー |Web Incubator コミュニティグループ"  

> [!NOTE]
> <span data-ttu-id="f7826-163">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7826-163">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f7826-164">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/issues/index)にあり、 [Sam Dutton][SamDutton] \ (開発者向け) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="f7826-164">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="f7826-166">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="f7826-166">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  