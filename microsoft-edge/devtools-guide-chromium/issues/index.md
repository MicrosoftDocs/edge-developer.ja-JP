---
description: '[問題] ツールを使用して、Web サイトの問題を見つけて修正します。'
title: DevTools の問題ツールの問題Microsoft Edge見つけて修正する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 64954d632416f7d1353269d04c1550ca7a0652b7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564183"
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
# <a name="find-and-fix-problems-with-the-microsoft-edge-devtools-issues-tool"></a><span data-ttu-id="317ff-104">DevTools の問題ツールの問題Microsoft Edge見つけて修正する</span><span class="sxs-lookup"><span data-stu-id="317ff-104">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>  

<span data-ttu-id="317ff-105">**DevTools の**問題ツールMicrosoft Edgeコンソールの通知の疲労と混乱を軽減**します**。</span><span class="sxs-lookup"><span data-stu-id="317ff-105">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="317ff-106">Cookie の問題や混在コンテンツなど、ブラウザーによって検出された問題に対する解決策を見つける場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="317ff-106">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="317ff-107">84 Microsoft Edgeでは **、Issues ツールは**次の 3 種類の問題をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="317ff-107">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="317ff-108">Cookie の問題</span><span class="sxs-lookup"><span data-stu-id="317ff-108">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="317ff-109">混在コンテンツ</span><span class="sxs-lookup"><span data-stu-id="317ff-109">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="317ff-110">COEP の問題</span><span class="sxs-lookup"><span data-stu-id="317ff-110">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="317ff-111">DevTools Microsoft Edgeでは、今後のバージョンの問題の種類をサポートする予定Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="317ff-111">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <a name="open-the-issues-tool-in-the-devtools-drawer"></a><span data-ttu-id="317ff-112">DevTools ドロワーで [問題] ツールを開く</span><span class="sxs-lookup"><span data-stu-id="317ff-112">Open the Issues tool in the DevTools drawer</span></span>  

1.  <span data-ttu-id="317ff-113">修正する問題を含む web [ページ][GlitchSamesiteSandbox](samesite-sandbox.glitch.me など) に移動します。</span><span class="sxs-lookup"><span data-stu-id="317ff-113">Navigate to a webpage, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="317ff-114">[DevTools を開きます][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="317ff-114">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="317ff-115">黄色の **警告バーの [問題に移動** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="317ff-115">Choose the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="問題が検出された場合は、黄色の警告バーの [問題] ボタンに移動します。" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="317ff-117">問題 **が検出された場合** 、黄色の警告バーの [問題に移動] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="317ff-117">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="317ff-118">または、[その他のツール **] メニュー** から [問題 **] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="317ff-118">Alternatively, choose **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="[その他のツール] メニューの [問題] ツール" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="317ff-120">**[その他** のツール] **メニューの [問題]** ツール</span><span class="sxs-lookup"><span data-stu-id="317ff-120">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="317ff-121">必要に応 **じて、[ページの再読み込** み] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="317ff-121">Choose the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="[ページの再読み込み] ボタンを使用した DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="317ff-123">**[ページの**再読み込み] ボタンを使用した DevTools**ドロワーの問題ツール**</span><span class="sxs-lookup"><span data-stu-id="317ff-123">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="317ff-124">コンソールで報告 **された問題は** 、次の図の Cookie の警告など、理解が非常に難しいです。</span><span class="sxs-lookup"><span data-stu-id="317ff-124">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="317ff-125">報告された問題に基づいて、何を行う必要があるのかはっきりしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="317ff-125">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="3 つの Cookie の問題を持つ DevTools ドロワーの問題ツール" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="317ff-127">**3 つの** Cookie の問題を持つ DevTools ドロワーの問題ツール</span><span class="sxs-lookup"><span data-stu-id="317ff-127">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <a name="view-items-in-the-issues-tool"></a><span data-ttu-id="317ff-128">[問題] ツールでアイテムを表示する</span><span class="sxs-lookup"><span data-stu-id="317ff-128">View items in the Issues tool</span></span>  

<span data-ttu-id="317ff-129">**DevTools**ドロワーの Issues ツールは、構造化、集約、および操作可能な方法で警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="317ff-129">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="317ff-130">問題を解決し、影響 **を** 受けるリソースを見つける方法に関するガイダンスを取得するには、[問題] ツールでアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="317ff-130">Choose an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="クロスサイト Cookie を [問題] ツールで開いているセキュリティで保護された問題としてマークする" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="317ff-132">**クロスサイト Cookie を [問題] ツールで開** いているセキュリティで保護された **問題としてマーク** する</span><span class="sxs-lookup"><span data-stu-id="317ff-132">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="317ff-133">各アイテムには、次の 4 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="317ff-133">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="317ff-134">問題を説明する見出し。</span><span class="sxs-lookup"><span data-stu-id="317ff-134">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="317ff-135">コンテキストとソリューションを提供する説明。</span><span class="sxs-lookup"><span data-stu-id="317ff-135">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="317ff-136">ネットワーク **パネルなどの適切** な DevTools コンテキスト内のリソースにリンクする、影響を受けるリソース セクション。</span><span class="sxs-lookup"><span data-stu-id="317ff-136">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="317ff-137">詳細なガイダンスへのリンク。</span><span class="sxs-lookup"><span data-stu-id="317ff-137">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="317ff-138">詳細を表示するには **、[影響を受けるリソース] で** アイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="317ff-138">Choose items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="317ff-139">次の例では、 **セキュリティで保護された問題としてクロスサイト** Cookie をマークすると、1 つの Cookie と 2 つの要求に影響します。</span><span class="sxs-lookup"><span data-stu-id="317ff-139">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="問題ツールで開いている影響を受けるリソース" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="317ff-141">DevTools ドロワーの **Issues** ツールで開く影響を受けるリソース</span><span class="sxs-lookup"><span data-stu-id="317ff-141">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <a name="view-issues-in-context"></a><span data-ttu-id="317ff-142">コンテキストで問題を表示する</span><span class="sxs-lookup"><span data-stu-id="317ff-142">View issues in context</span></span>  

1.  <span data-ttu-id="317ff-143">DevTools 内の適切なコンテキストでアイテムを表示するには、リソース リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="317ff-143">Choose a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="317ff-144">次の例では、[要求] `samesite-sandbox.glitch.me` を **選択** して、その要求に添付された Cookie を表示します。</span><span class="sxs-lookup"><span data-stu-id="317ff-144">In the following example, choose `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="DevTools ネットワーク ツールで影響を受ける Cookie を表示する" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="317ff-146">DevTools ネットワーク ツールで影響を受ける Cookie を **表示** する</span><span class="sxs-lookup"><span data-stu-id="317ff-146">View the affected cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="317ff-147">スクロールして、問題のあるアイテムを表示します。次の例では `ck02` 、Cookie です。</span><span class="sxs-lookup"><span data-stu-id="317ff-147">Scroll to view the item with a problem:  for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="317ff-148">SameSite 列 **にカーソルを** 合わせると、問題 `None` が検出された値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="317ff-148">Hover on the **SameSite** column to review the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools ネットワーク ツールの ck02 Cookie の SameSite 列の値なし" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` <span data-ttu-id="317ff-150">DevTools**ネットワーク**ツールの `ck02` Cookie の SameSite 列の値\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="317ff-150">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="317ff-151">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="317ff-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite Cookie のテスト|Glitch"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混在コンテンツ |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "クロスオリジン エンベダー ポリシー |Web インキュベーター Community グループ"  

> [!NOTE]
> <span data-ttu-id="317ff-157">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="317ff-157">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="317ff-158">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/issues/index) つかり [、Sam Dutton][SamDutton] \(Developer Advocate\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="317ff-158">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="317ff-160">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="317ff-160">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[SamDutton]: https://developers.google.com/web/resources/contributors#sam-dutton  
