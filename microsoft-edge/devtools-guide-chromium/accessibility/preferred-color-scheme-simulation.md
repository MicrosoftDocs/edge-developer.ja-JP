---
description: DevTools Microsoft Edge配色プレビュー モードに切り替えます。
title: DevTools Microsoft Edgeを配色プレビュー モードに強制する (CSS 優先配色)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: dc2911ce7a7fcbeef7763099541822b5cd6cf053
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597063"
---
# <a name="dark-or-light-color-scheme-simulation"></a><span data-ttu-id="9d8f4-104">暗いまたは明るい配色のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="9d8f4-104">Dark or light color scheme simulation</span></span>  

<span data-ttu-id="9d8f4-105">多くのオペレーティング システムでは、アプリケーションを暗い色または明るい色で表示できます。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-105">Many operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="9d8f4-106">暗いモードのオペレーティング システムで明るいテーマを持つ Web 製品はグレーティングであり、一部のユーザーにとってアクセシビリティの問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-106">Having a web product that has a light theme in a dark-mode operating system is grating and can be an accessibility issue for some users.</span></span>  

<span data-ttu-id="9d8f4-107">Web ページでは [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を暗色または明るい配色で表示することを好むかどうかを検出できます。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-107">For a webpage, you can use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect whether the user prefers to display your product in a darker or lighter color scheme.</span></span>  <span data-ttu-id="9d8f4-108">次に、結果をテストするには、Microsoft Edge [DevTools][DevtoolsIndex]を使用して、オペレーティング システム全体の設定を変更することなく、暗いモードから明るいモードへの変更をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-108">Then to test the result, use [Microsoft Edge DevTools][DevtoolsIndex] to simulate a change from dark to light mode, without having to change the setting for your entire operating system.</span></span>  

**<span data-ttu-id="9d8f4-109">暗いテーマまたは明るいテーマをエミュレートするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-109">To emulate dark or light theme:</span></span>**

1.  <span data-ttu-id="9d8f4-110">**コマンド メニュー** を開きます。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-110">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="9d8f4-111">`Ctrl` + `Shift` + `P` \(Windows/Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-111">Select `Ctrl`+`Shift`+`P` \(Windows/Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="9d8f4-113">**コマンド メニュー**</span><span class="sxs-lookup"><span data-stu-id="9d8f4-113">The **Command Menu**</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="9d8f4-114">[種類] を選択し、[CSS の優先する配色をエミュレートする: 濃い色] または [CSS を優先する配色をエミュレートする: 明るい] を選択し、 を `emulate color` 選択します\*\*\*\*\*\*\*\* `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-114">Type `emulate color`, choose either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light** and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンド メニューの配色オプション" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="9d8f4-116">コマンド メニューの配 **色** オプション</span><span class="sxs-lookup"><span data-stu-id="9d8f4-116">Color scheme option from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="9d8f4-117">`dark` `light` [DevTools][DevtoolsCustomizeDarkTheme]のテーマを選択する方法も用意されています。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-117">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsCustomizeDarkTheme].</span></span>  <span data-ttu-id="9d8f4-118">何を選ぶか疑問に思う場合は、外観メニュー項目ではなく、\*\*\*\* レンダリング メニュー項目を**選択してください**。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-118">If you are wondering what to choose, make sure that you are choosing a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="9d8f4-119">配色を選択した後、現在のドキュメントを更新してシミュレートモードを表示します。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-119">After you choose a color scheme, refresh the current document to display the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="DevTools 内のシミュレートされたMicrosoft Edgeモード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="9d8f4-121">DevTools 内のシミュレートされたMicrosoft Edgeモード</span><span class="sxs-lookup"><span data-stu-id="9d8f4-121">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9d8f4-122">他の Web ページと同様に CSS を表示および変更します。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-122">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="9d8f4-123">詳細については、「CSS の表示と変更 [を開始する」に移動します][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="9d8f4-123">For more information, navigate to [Get started with viewing and changing CSS][DevtoolsCssIndex].</span></span>  


## <a name="see-also"></a><span data-ttu-id="9d8f4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d8f4-124">See also</span></span>

* [<span data-ttu-id="9d8f4-125">暗いテーマと明るいテーマのコントラストの問題を確認する</span><span class="sxs-lookup"><span data-stu-id="9d8f4-125">Check for contrast issues with dark theme and light theme</span></span>](test-dark-mode.md)


<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "DevTools サーバーで暗いMicrosoft Edgeを有効|Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "CSS ファイルの表示と変更の|Microsoft Docs"  
<!-- external links -->
[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
