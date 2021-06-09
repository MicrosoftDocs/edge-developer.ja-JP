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
# <a name="dark-or-light-color-scheme-simulation"></a>暗いまたは明るい配色のシミュレーション  

多くのオペレーティング システムでは、アプリケーションを暗い色または明るい色で表示できます。  暗いモードのオペレーティング システムで明るいテーマを持つ Web 製品はグレーティングであり、一部のユーザーにとってアクセシビリティの問題になる可能性があります。  

Web ページでは [、prefers-color-scheme][MDNPrefersColorScheme] CSS Media Query を使用して、ユーザーが製品を暗色または明るい配色で表示することを好むかどうかを検出できます。  次に、結果をテストするには、Microsoft Edge [DevTools][DevtoolsIndex]を使用して、オペレーティング システム全体の設定を変更することなく、暗いモードから明るいモードへの変更をシミュレートします。  

**暗いテーマまたは明るいテーマをエミュレートするには、次の方法を使用します。**

1.  **コマンド メニュー** を開きます。  
    1.  `Ctrl` + `Shift` + `P` \(Windows/Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。  
        
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
    
    :::image type="complex" source="../media/css-elements-styles-qs-simulated-light-mode.msft.png" alt-text="DevTools 内のシミュレートされたMicrosoft Edgeモード" lightbox="../media/css-elements-styles-qs-simulated-light-mode.msft.png":::
       DevTools 内のシミュレートされたMicrosoft Edgeモード  
    :::image-end:::  
    
    他の Web ページと同様に CSS を表示および変更します。  詳細については、「CSS の表示と変更 [を開始する」に移動します][DevtoolsCssIndex]。  


## <a name="see-also"></a>関連項目

* [暗いテーマと明るいテーマのコントラストの問題を確認する](test-dark-mode.md)


<!-- links -->  
[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[DevtoolsCustomizeDarkTheme]: ../customize/dark-theme.md "DevTools サーバーで暗いMicrosoft Edgeを有効|Microsoft Docs"
[DevtoolsCssIndex]: ../css/index.md "CSS ファイルの表示と変更の|Microsoft Docs"  
<!-- external links -->
[MDNPrefersColorScheme]: https://developer.mozilla.org/docs/Web/CSS/@media/prefers-color-scheme "prefers-color-scheme |MDN"  
