---
description: DevTools 内からライトハウスを使用してアクセシビリティをテストします。
title: ライトハウスを使用してアクセシビリティをテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bb158085eb516c8d4ce37a22f6b612784db51461
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597558"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
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

# <a name="test-accessibility-using-lighthouse"></a><span data-ttu-id="eb966-104">ライトハウスを使用してアクセシビリティをテストする</span><span class="sxs-lookup"><span data-stu-id="eb966-104">Test accessibility using Lighthouse</span></span>

<span data-ttu-id="eb966-105">DevTools 内のライトハウスを使用して、ページのアクセシビリティを監査し、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-105">You can use Lighthouse from within DevTools to audit the accessibility of a page and generate a report.</span></span> <span data-ttu-id="eb966-106">ライトハウス ツールを使用して、次の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="eb966-106">You can use the Lighthouse tool to determine:</span></span>

*   <span data-ttu-id="eb966-107">ページがスクリーン リーダー用に適切にマークされているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb966-107">Whether a page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="eb966-108">ページ上のテキスト要素に、カラー ピッカーを使用して十分なコントラスト比を設定するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb966-108">Whether the text elements on a page have sufficient contrast ratios using the Color Picker.</span></span> <span data-ttu-id="eb966-109">詳細については、「Color Picker を使用 [してテキストと色のコントラストをテストする」に移動します](color-picker.md)。</span><span class="sxs-lookup"><span data-stu-id="eb966-109">For more information, navigate to [Test text-color contrast using the Color Picker](color-picker.md).</span></span>   

> [!NOTE]
> <span data-ttu-id="eb966-110">ライト **ハウス ツール** は、サードパーティの Web サイトでホストされているコンテンツへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="eb966-110">The **Lighthouse** tool provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="eb966-111">Microsoft は、これらのサイトのコンテンツおよび収集される可能性があるデータについて責任を負いません。</span><span class="sxs-lookup"><span data-stu-id="eb966-111">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="eb966-112">ライトハウス ツールを使用してページを監査するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb966-112">To audit a page using the Lighthouse tool, perform the following steps.</span></span>

1.  <span data-ttu-id="eb966-113">監査する URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb966-113">Navigate to the URL that you want to audit.</span></span>
1.  <span data-ttu-id="eb966-114">DevTools で、ライトハウス ツール **を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="eb966-114">In DevTools, select the **Lighthouse** tool.</span></span>  <span data-ttu-id="eb966-115">構成オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-115">Configuration options are displayed.</span></span>
    
    :::image type="complex" source="../media/accessibility-lighthouse.msft.png" alt-text="ライトハウスの構成オプション" lightbox="../media/accessibility-lighthouse.msft.png":::
       <span data-ttu-id="eb966-117">ライトハウスの構成オプション</span><span class="sxs-lookup"><span data-stu-id="eb966-117">Lighthouse configuration options</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="eb966-118">[**デバイス]\*\*\*\*で、モバイル**デバイスをシミュレートする場合は、[モバイル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb966-118">For **Device**, select **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="eb966-119">このオプションは、ユーザー エージェントの文字列を変更し、ビューポートのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="eb966-119">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="eb966-120">このオプションは、監査結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb966-120">This option can affect the audit results.</span></span>
1.  <span data-ttu-id="eb966-121">[カテゴリ] **セクションで** 、[アクセシビリティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb966-121">In the **Categories** section, select **Accessibility**.</span></span>
1.  <span data-ttu-id="eb966-122">[レポート **の生成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb966-122">Select **Generate report**.</span></span> <span data-ttu-id="eb966-123">10 ~ 30 秒後、DevTools はレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-123">After 10 to 30 seconds, DevTools displays a report.</span></span>  <span data-ttu-id="eb966-124">このレポートには、ページのアクセシビリティを向上させる方法に関するヒントが示されています。</span><span class="sxs-lookup"><span data-stu-id="eb966-124">The report gives tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result.msft.png" alt-text="アクセシビリティ カテゴリのライトハウス レポート" lightbox="../media/accessibility-lighthouse-result.msft.png":::
       <span data-ttu-id="eb966-126">アクセシビリティ カテゴリの **ライトハウス** レポート</span><span class="sxs-lookup"><span data-stu-id="eb966-126">A Lighthouse report for the **Accessibility** category</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="eb966-127">レポート内のアイテムを選択して、詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="eb966-127">Select an item in the report to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result-issue-expanded.msft.png" alt-text="ライトハウス レポートの拡張された問題" lightbox="../media/accessibility-lighthouse-result-issue-expanded.msft.png":::
       <span data-ttu-id="eb966-129">ライトハウス レポートの拡張された問題</span><span class="sxs-lookup"><span data-stu-id="eb966-129">An expanded issue in a Lighthouse report</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="eb966-130">[詳細] **リンクを選択** して、問題のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="eb966-130">Select the **Learn more** link to view the documentation of the issue.</span></span>
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="問題のドキュメントを表示する" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="eb966-132">問題のドキュメントを表示する</span><span class="sxs-lookup"><span data-stu-id="eb966-132">View the documentation of an issue</span></span>
    :::image-end:::  

1.  <span data-ttu-id="eb966-133">構成オプションに戻る場合は、DevTools で [監査の実行 ] () **を選択** します `+` 。</span><span class="sxs-lookup"><span data-stu-id="eb966-133">To return to the configuration options, in DevTools, select **Perform an audit** (`+`).</span></span>    


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="eb966-134">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="eb966-134">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="eb966-135">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb966-135">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="eb966-136">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="eb966-136">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="eb966-138">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="eb966-138">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->  
[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web アクセシビリティ テスト - Chrome ウェブストア"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
