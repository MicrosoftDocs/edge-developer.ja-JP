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
# 暗い色または簡易カラースキームのシミュレーション  

オペレーティングシステムには、すべてのアプリケーションを暗い色または明るい色で表示する方法が用意されています。  ダークモードのオペレーティングシステムで、淡色テーマの web 製品を使用している場合、一部のユーザーのアクセシビリティに問題が発生する可能性があります。  Web 上では、ユーザーがより濃い色または薄い色の配色で製品を表示するかどうかを検出するために、[優先カラースキーム][MDNPrefersColorScheme]CSS メディアクエリを使用することができます。  [Microsoft Edge DevTools][DevtoolsGuideChromiumMain]を使って、オペレーティングシステム全体を変更せずに、ダークモードから簡易モードに変更することをシミュレートします。  

1.  **コマンドメニュー**を開きます。  
    1.  `Control` + `Shift` + `P` Windows または macOS を押し `Command` + `Shift` + `P` ます。  
        
        :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="コマンドメニュー" lightbox="../media/css-console-command-menu-rendering.msft.png":::
           **コマンドメニュー**  
        :::image-end:::   
        
1.  `emulate color`[ **Css の優先**] を選ぶか、[css の優先] を選択します。暗いまたはエミュレートされた**css の優先カラースキーム: light**で、を押し `Enter` ます。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png" alt-text="コマンドメニューからの配色パターンの選択" lightbox="../media/css-elements-styles-qs-select-renderingmode-command-menu.msft.png":::
       **コマンド**メニューからの配色パターンの選択  
    :::image-end:::  
    
    > [!IMPORTANT]
    > `dark` `light` [Devtools のテーマを選択][DevtoolsGuideChromiumCustomizeDarkTheme]する方法もあるため、単純に入力するか、適切なツールを表示しないようにします。  何を選ぶべきかわからない場合は、**アピアランス**メニュー項目ではなく、**レンダリング**メニュー項目を選択していることを確認してください。  

1.  配色を選択したら、現在の文書をもう一度読み込んで、シミュレートされたモードを表示します。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="Microsoft Edge DevTools 内のシミュレートされたライトモード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       Microsoft Edge DevTools 内のシミュレートされたライトモード  
    :::image-end:::  
    
    他の web ページと同様に、CSS を表示して変更します。  詳細については、「 [CSS の表示と変更の概要][DevtoolsGuideChromiumCssIndex]」を参照してください。  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール Microsoft |Microsoft ドキュメント"  
[DevtoolsGuideChromiumCustomizeDarkTheme]: ../customize/dark-theme.md "Microsoft Edge DevTools でダークテーマを有効にする |Microsoft ドキュメント"
[DevtoolsGuideChromiumCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "優先配色-配色 |MDN"  
