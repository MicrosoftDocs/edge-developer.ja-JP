---
title: Microsoft Edge DevTools を開く
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 06e547d2d413535a6f14d829d30dc4d7b11ac92b
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844006"
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

# <span data-ttu-id="67696-103">Microsoft Edge DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="67696-103">Open Microsoft Edge DevTools</span></span>  

<span data-ttu-id="67696-104">さまざまなユーザーが DevTools UI のさまざまな部分にすばやくアクセスする必要があるため、Microsoft Edge DevTools を開くにはさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="67696-104">There are many ways to open Microsoft Edge DevTools, because different users want fast access to different parts of the DevTools UI.</span></span>  

## <span data-ttu-id="67696-105">[要素] パネルを開いて、DOM または CSS を検査する</span><span class="sxs-lookup"><span data-stu-id="67696-105">Open the Elements panel to inspect the DOM or CSS</span></span>  

<span data-ttu-id="67696-106">次の各タスクによって、DOM ノードのスタイルまたは属性を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="67696-106">Each of the following tasks enable you to inspect the styles or attributes of a DOM node.</span></span>

*   <span data-ttu-id="67696-107">要素にマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67696-107">Hover on the element, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
*   <span data-ttu-id="67696-108">`Control` + `Shift` + `C` \ (Windows \) または `Command` + `Option` + `C` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="67696-108">Press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Option`+`C` \(macOS\).</span></span>  <span data-ttu-id="67696-109">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67696-109">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  

:::image type="complex" source="./media/bing-right-click-inspect.msft.png" alt-text="\* \* 検査 \* \* オプション" lightbox="./media/bing-right-click-inspect.msft.png":::
   <span data-ttu-id="67696-111">[**検査**] オプション</span><span class="sxs-lookup"><span data-stu-id="67696-111">The **Inspect** option</span></span>  
:::image-end:::  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## <span data-ttu-id="67696-112">コンソールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="67696-112">Open the Console panel</span></span>  

<span data-ttu-id="67696-113">次の各タスクを使用すると、[コンソール][DevToolsConsoleIndex]ウィンドウを開いて、ログに記録されたメッセージを表示したり、JavaScript を実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="67696-113">Each of the following tasks enable you to open the [Console][DevToolsConsoleIndex] pane to view logged messages or run JavaScript.</span></span>  

*   <span data-ttu-id="67696-114">[コンソール][DevToolsConsoleIndex]ウィンドウを開くには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67696-114">Use the following steps to open [Console][DevToolsConsoleIndex] pane.</span></span>  
    
    1.  <span data-ttu-id="67696-115">[DevTools を開き](#open-microsoft-edge-devtools)ます。</span><span class="sxs-lookup"><span data-stu-id="67696-115">[Open DevTools](#open-microsoft-edge-devtools).</span></span>  
    1.  <span data-ttu-id="67696-116">[[コンソール][DevToolsConsoleIndex]] ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="67696-116">Select the [Console][DevToolsConsoleIndex] pane.</span></span>  

*   <span data-ttu-id="67696-117">[コンソール][DevToolsConsoleIndex]ウィンドウに直接ジャンプするには、 `Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="67696-117">To jump straight into the [Console][DevToolsConsoleIndex] pane, press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="67696-118">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67696-118">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## <span data-ttu-id="67696-119">前のパネルを開く</span><span class="sxs-lookup"><span data-stu-id="67696-119">Open the previous panel</span></span>  

<span data-ttu-id="67696-120">開いていた前のパネルにジャンプするに `Control` + `Shift` + `I` は、\ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="67696-120">To jump to the previous panel that you had open, press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="67696-121">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67696-121">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  

## <span data-ttu-id="67696-122">Microsoft Edge DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="67696-122">Open Microsoft Edge DevTools</span></span>  

<span data-ttu-id="67696-123">次の各タスクを使用すると、DevTools を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="67696-123">Each of the following tasks enable you to open DevTools.</span></span>  

*   <span data-ttu-id="67696-124">Microsoft Edge DevTools を開くには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="67696-124">Use the following steps to open Microsoft Edge DevTools.</span></span>  
    
    1.  <span data-ttu-id="67696-125">`...`アイコン (**設定など**のアイコン) を選びます。</span><span class="sxs-lookup"><span data-stu-id="67696-125">Select the  `...` icon \(the **Settings and more** icon\).</span></span>  
    1.  <span data-ttu-id="67696-126">[**その他のツール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67696-126">Select **More Tools**.</span></span>  
    1.  <span data-ttu-id="67696-127">[**開発者ツール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67696-127">Select **Developer Tools**.</span></span>  
    
*   <span data-ttu-id="67696-128">Microsoft Edge devtools を開くに `F12` は、または `Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="67696-128">To open Microsoft Edge DevTools, press `F12` or `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="67696-129">詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67696-129">For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].</span></span>  

:::image type="complex" source="./media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="Microsoft Edge のメインメニューから DevTools を開く" lightbox="./media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   <span data-ttu-id="67696-131">Microsoft Edge のメインメニューから DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="67696-131">Open DevTools from the Microsoft Edge main menu</span></span>  
:::image-end:::  

## <span data-ttu-id="67696-132">すべての新しいタブで DevTools を自動で開く</span><span class="sxs-lookup"><span data-stu-id="67696-132">Auto-open DevTools on every new tab</span></span>  

<span data-ttu-id="67696-133">すべての新しいタブで DevTools を自動的に開くには、コマンドラインから Microsoft Edge を開き、 `--auto-open-devtools-for-tabs` フラグを渡します。</span><span class="sxs-lookup"><span data-stu-id="67696-133">To auto-open DevTools on every new tab, open Microsoft Edge from the command-line and pass the `--auto-open-devtools-for-tabs` flag.</span></span>  

#### [<span data-ttu-id="67696-134">CMD (Windows)</span><span class="sxs-lookup"><span data-stu-id="67696-134">CMD (Windows)</span></span>](#tab/cmd-windows/)  

<a id="selenium-tools-install"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

#### [<span data-ttu-id="67696-135">PowerShell (Windows)</span><span class="sxs-lookup"><span data-stu-id="67696-135">PowerShell (Windows)</span></span>](#tab/powershell-windows/)  

<a id="selenium-tools-install"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

#### [<span data-ttu-id="67696-136">bash (macOS)</span><span class="sxs-lookup"><span data-stu-id="67696-136">bash (macOS)</span></span>](#tab/bash-macos/)  

<a id="selenium-tools-install"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

* * *  

<!-- links -->  

[DevToolsConsoleIndex]: ./console/index.md "本体の概要 |Microsoft ドキュメント"  
[DevtoolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット-Microsoft ドキュメント"  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> <span data-ttu-id="67696-139">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="67696-139">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="67696-140">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/open)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="67696-140">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/open) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="67696-142">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="67696-142">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
