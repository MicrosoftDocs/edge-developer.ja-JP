---
title: Microsoft Edge DevTools を配色のプレビューモードに強制する (CSS は配色パターンを優先)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a83284b676ad388114a4a0ddb7ebdf2203ebcb90
ms.sourcegitcommit: d7fdb67df0fe73fa5ae96e5a69a847d07941d0a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10758117"
---
# <span data-ttu-id="e9816-103">暗い色または簡易カラースキームのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="e9816-103">Dark or Light Color Scheme simulation</span></span>  

<span data-ttu-id="e9816-104">オペレーティングシステムには、すべてのアプリケーションを暗い色または明るい色で表示する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e9816-104">Operating systems have a way to display any application in darker or lighter colors.</span></span>  <span data-ttu-id="e9816-105">ダークモードのオペレーティングシステムで、淡色テーマの web 製品を使用している場合、一部のユーザーのアクセシビリティに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9816-105">Having a web product that has a light theme in a dark mode operating system is grating and can be an accessibility issue for some users.</span></span>  <span data-ttu-id="e9816-106">Web 上では、ユーザーがより濃い色または薄い色の配色で製品を表示するかどうかを検出するために、[優先カラースキーム][MDNPrefersColorScheme]CSS メディアクエリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e9816-106">On the web, you may use the [prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query to detect if users prefer to see your product in a darker or lighter colour scheme.</span></span>  <span data-ttu-id="e9816-107">[Microsoft Edge DevTools][DevtoolsGuideChromiumMain]を使って、オペレーティングシステム全体を変更せずに、ダークモードから簡易モードに変更することをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e9816-107">Use [Microsoft Edge DevTools][DevtoolsGuideChromiumMain] to simulate a change from dark to light mode without having to change the entire operating system.</span></span>  

1.  <span data-ttu-id="e9816-108">**コマンドメニュー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e9816-108">Open the **Command Menu**.</span></span>  
    1.  <span data-ttu-id="e9816-109">`Control` + `Shift` + `P` Windows または macOS を押し `Command` + `Shift` + `P` ます。</span><span class="sxs-lookup"><span data-stu-id="e9816-109">Press `Control`+`Shift`+`P`  on Windows or `Command`+`Shift`+`P` on macOS.</span></span>  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           <span data-ttu-id="e9816-111">**コマンドメニュー**</span><span class="sxs-lookup"><span data-stu-id="e9816-111">The **Command Menu**</span></span>  
        :::image-end:::   
        
1.  <span data-ttu-id="e9816-112">`emulate color`[ **Css の優先**] を選ぶか、[css の優先] を選択します。暗いまたはエミュレートされた**css の優先カラースキーム: light**で、を押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e9816-112">Type `emulate color`, select either **Emulate CSS prefers-color-scheme: dark** or **Emulate CSS prefers-color-scheme: light**  and then press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンドメニューからの配色パターンの選択" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       <span data-ttu-id="e9816-114">**コマンド**メニューからの配色パターンの選択</span><span class="sxs-lookup"><span data-stu-id="e9816-114">Color scheme selection from **Command** Menu</span></span>  
    :::image-end:::  
    
    > [!IMPORTANT]
    > <span data-ttu-id="e9816-115">`dark` `light` [Devtools のテーマを選択][DevtoolsGuideChromiumCustomizeDarkTheme]する方法もあるため、単純に入力するか、適切なツールを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="e9816-115">Simply typing `dark` or `light` does not reveal the right tool, since there is also a way to [choose a theme for DevTools][DevtoolsGuideChromiumCustomizeDarkTheme].</span></span>  <span data-ttu-id="e9816-116">何を選ぶべきかわからない場合は、**アピアランス**メニュー項目ではなく、**レンダリング**メニュー項目を選択していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9816-116">If you are wondering what to choose, make sure that you are selecting a **rendering** menu item, not an **appearance** menu item.</span></span>  

1.  <span data-ttu-id="e9816-117">配色を選択したら、現在の文書をもう一度読み込んで、シミュレートされたモードを表示します。</span><span class="sxs-lookup"><span data-stu-id="e9816-117">After you select a color scheme, reload the current document to see the simulated mode.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライトモード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       <span data-ttu-id="e9816-119">Microsoft Edge DevTools 内のシミュレートされたライトモード</span><span class="sxs-lookup"><span data-stu-id="e9816-119">Simulated light mode inside Microsoft Edge DevTools</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="e9816-120">他の web ページと同様に、CSS を表示して変更します。</span><span class="sxs-lookup"><span data-stu-id="e9816-120">View and change your CSS like any other web page.</span></span>  <span data-ttu-id="e9816-121">詳細については、「 [CSS の表示と変更の概要][DevtoolsGuideChromiumCssIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9816-121">For more information, see [Get Started With Viewing And Changing CSS][DevtoolsGuideChromiumCssIndex].</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール Microsoft |Microsoft ドキュメント"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools でダークテーマを有効にする |Microsoft ドキュメント"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "優先配色-配色 |MDN"  
