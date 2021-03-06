---
description: Microsoft Edge DevTools を配色プレビュー モードに強制します。
title: Microsoft Edge DevTools を配色プレビュー モードに強制する (CSS 優先配色)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 84f482605acd6edab6829e00d5fa31f927ebc032
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398302"
---
# <a name="dark-or-light-color-scheme-simulation"></a>濃色または明るい配色のシミュレーション  

オペレーティング システムでは、アプリケーションを暗い色または明るい色で表示できます。  暗いモードのオペレーティング システムで明るいテーマを持つ Web 製品はグレーティングであり、一部のユーザーにとってアクセシビリティの問題になる可能性があります。  Web では [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を暗色または明るい配色で表示することを好む場合を検出できます。  [Microsoft Edge DevTools を使用][DevtoolsIndex]すると、オペレーティング システム全体を変更することなく、暗いモードから明るいモードへの変更をシミュレートできます。  

1.  コマンド メニュー **を開きます**。  
    1.  `Control` + `Shift` + `P` \(Windows/Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンド メニュー**  
        :::image-end:::  
        
1.  [種類] を選択し、[CSS の優先する配色をエミュレートする: 濃い色] または [CSS を優先する配色をエミュレートする: 明るい] を選択し、 を `emulate color` 選択します******** `Enter` 。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンド メニューの配色オプション" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       コマンド メニューの配 **色** オプション  
    :::image-end:::  
    
    > [!IMPORTANT]
    > `dark` `light` [DevTools][DevtoolsCustomizeDarkTheme]のテーマを選択する方法も用意されています。  何を選ぶか疑問に思う場合は、外観メニュー項目ではなく、**** レンダリング メニュー項目を**選択してください**。  

1.  配色を選択した後、現在のドキュメントを更新してシミュレートモードを表示します。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライト モード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       Microsoft Edge DevTools 内のシミュレートされたライト モード  
    :::image-end:::  
    
    他の Web ページと同様に CSS を表示および変更します。  詳細については、「CSS の表示と変更 [を開始する」に移動します][DevtoolsCssIndex]。  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools サーバーで暗いテーマを有効|Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の開始|Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
