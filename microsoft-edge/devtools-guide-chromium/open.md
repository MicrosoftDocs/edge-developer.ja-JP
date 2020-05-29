---
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 48f80ea9f85bd3509f2ba3d834f99c25247c0761
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601888"
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
   limitations under the License. -->





# <span data-ttu-id="62a83-103">Microsoft Edge DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="62a83-103">Open Microsoft Edge DevTools</span></span>   



<span data-ttu-id="62a83-104">さまざまなユーザーが DevTools UI のさまざまな部分にすばやくアクセスする必要があるため、Microsoft Edge DevTools を開くにはさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="62a83-104">There are many ways to open Microsoft Edge DevTools, because different users want fast access to different parts of the DevTools UI.</span></span>  

## <span data-ttu-id="62a83-105">[要素] パネルを開いて、DOM または CSS を検査する</span><span class="sxs-lookup"><span data-stu-id="62a83-105">Open the Elements panel to inspect the DOM or CSS</span></span>   

<span data-ttu-id="62a83-106">DOM ノードのスタイルまたは属性を検査する場合は、要素を右クリックして [**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="62a83-106">When you want to inspect the styles or attributes of a DOM node, right-click the element and select **Inspect**.</span></span>  

> ##### <span data-ttu-id="62a83-107">図 1</span><span class="sxs-lookup"><span data-stu-id="62a83-107">Figure 1</span></span>  
> <span data-ttu-id="62a83-108">[**検査**] オプション</span><span class="sxs-lookup"><span data-stu-id="62a83-108">The **Inspect** option</span></span>  
> ![[検査] オプション][ImageInspectOption]  

<span data-ttu-id="62a83-110">または、 `Control` + `Shift` + `C` \ (Windows \) または `Command` + `Option` + `C` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="62a83-110">Or press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Option`+`C` \(macOS\).</span></span>  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## <span data-ttu-id="62a83-111">コンソールパネルを開いて、ログに記録されたメッセージを表示したり、JavaScript を実行したりする</span><span class="sxs-lookup"><span data-stu-id="62a83-111">Open the Console panel to view logged messages or run JavaScript</span></span>   

<span data-ttu-id="62a83-112">`Control` + `Shift` + `J` コンソールパネルに直接ジャンプするには、\ (Windows \) または `Command` + `Option` + `J` \ **Console** (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="62a83-112">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to jump straight into the **Console** panel.</span></span>  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## <span data-ttu-id="62a83-113">開いていた最後のパネルを開く</span><span class="sxs-lookup"><span data-stu-id="62a83-113">Open the last panel you had open</span></span>   

<span data-ttu-id="62a83-114">`Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="62a83-114">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  

## <span data-ttu-id="62a83-115">Microsoft Edge のメインメニューから DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="62a83-115">Open DevTools from the Microsoft Edge main menu</span></span>  

<span data-ttu-id="62a83-116">[**設定とその他] をクリックし (Alt + F \)** `...` 、[**その他のツール**  >  **開発者ツール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="62a83-116">Click **Settings and more \(Alt+F\)** `...` and then select **More Tools** > **Developer Tools**.</span></span>  

> ##### <span data-ttu-id="62a83-117">図 2</span><span class="sxs-lookup"><span data-stu-id="62a83-117">Figure 2</span></span>  
> <span data-ttu-id="62a83-118">Microsoft Edge のメインメニューから DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="62a83-118">Opening DevTools from the Microsoft Edge main menu</span></span>  
> ![Microsoft Edge のメインメニューから DevTools を開く][ImageOpenFromMain]  

## <span data-ttu-id="62a83-120">すべての新しいタブで DevTools を自動で開く</span><span class="sxs-lookup"><span data-stu-id="62a83-120">Auto-open DevTools on every new tab</span></span>   

<span data-ttu-id="62a83-121">コマンドラインから Microsoft Edge を開き、フラグを渡し `--auto-open-devtools-for-tabs` ます。</span><span class="sxs-lookup"><span data-stu-id="62a83-121">Open Microsoft Edge from the command line and pass the `--auto-open-devtools-for-tabs` flag.</span></span>  

<span data-ttu-id="62a83-122">Windows \ (CMD \):</span><span class="sxs-lookup"><span data-stu-id="62a83-122">Windows \(CMD\):</span></span>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

<span data-ttu-id="62a83-123">Windows \ (PowerShell \):</span><span class="sxs-lookup"><span data-stu-id="62a83-123">Windows \(PowerShell\):</span></span>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

<span data-ttu-id="62a83-124">Os</span><span class="sxs-lookup"><span data-stu-id="62a83-124">macOS:</span></span>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

 



<!-- image links -->  

[ImagesMainIcon]: /microsoft-edge/devtools-guide-chromium/media/main-menu-icon.msft.png  

[ImageInspectOption]: /microsoft-edge/devtools-guide-chromium/media/bing-right-click-inspect.msft.png "図 1: [検査] オプション"  
[ImageOpenFromMain]: /microsoft-edge/devtools-guide-chromium/media/bing-customize-more-tools-developer-tools-transparent.msft.png "図 2: Microsoft Edge のメインメニューから DevTools を開く"  

<!-- links -->  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> <span data-ttu-id="62a83-127">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="62a83-127">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="62a83-128">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/open)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="62a83-128">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/open) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="62a83-130">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="62a83-130">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
