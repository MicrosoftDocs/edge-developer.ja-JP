---
Description: Microsoft Edge DevTools を強制的に配色プレビュー モードにします。
title: Microsoft Edge DevTools を強制的に配色プレビュー モードにする (CSS Prefers Color Scheme)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 29b0121a616a037fa11b61799efeffd201eb1821
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230797"
---
# 濃色または明るい配色のシミュレーション  

オペレーティング システムには、アプリケーションを暗い色または明るい色で表示する方法があります。  濃色モードのオペレーティング システムで淡色テーマの Web 製品を使用すると、問題が発生し、一部のユーザーにとってアクセシビリティの問題になる可能性があります。  Web では [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を濃色または明るい配色で表示することを希望する場合に検出できます。  [Microsoft Edge DevTools を使][DevtoolsGuideChromiumMain]って、オペレーティング システム全体を変更することなく、暗いモードから明るいモードへの変更をシミュレートします。  

1.  コマンド メニュー **を開きます**。  
    1.  `Control` + `Shift` + `P` Windows/Linux または `Command` + `Shift` + `P` macOS で選択します。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンド メニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンド メニュー**  
        :::image-end:::  
        
1.  Type, `emulate color` choose either Emulate CSS **prefers-color-scheme: dark** or Emulate CSS **prefers-color-scheme: light** and then select `Enter` .  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンド メニューの配色オプション" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       コマンド メニューの配 **色** オプション  
    :::image-end:::  
    
    > [!IMPORTANT]
    > `dark` `light` [DevTools][DevtoolsGuideChromiumCustomizeDarkTheme]のテーマを選択する方法も用意されています。  何を選択する必要があるのか疑問に思う場合は、外観メニュー**** 項目ではなく、レンダリング メニュー項目を**選択**してください。  

1.  配色を選択した後、現在のドキュメントを再読み込みし、シミュレートされたモードを確認します。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライト モード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       Microsoft Edge DevTools 内のシミュレートされたライト モード  
    :::image-end:::  
    
    他の Web ページと同様に CSS を表示および変更します。  詳細については、「CSS の表示と変更 [の開始」を参照してください][DevtoolsGuideChromiumCssIndex]。  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools で濃色テーマを有効にする |Microsoft Docs"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "CSS の表示と変更を開始する |Microsoft Docs"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
