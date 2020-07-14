---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: 6824b09ffc3c1f00c4a2f3000d84bf2c1be743d0
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866044"
---
# 試験的機能  

Microsoft Edge DevTools でまだ開発中の実験的な機能を使って、各リリース前に[フィードバック](#providing-feedback-on-experimental-features)をテストして提供することができます。  

Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。  

## 実験的な機能を有効にする  

Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。  

1.  [DevTools を開き][DevtoolsOpen]ます。  
     *   `Control` + `Shift` + `I` \ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を押します。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [[設定][DevToolsCustomizeSettings]] ウィンドウを開きます。  
    *   キーを押し `Shift` + `?` ます。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [**設定**] ウィンドウの左側で、[**実験**] セクションを選択します。  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.png":::
       DevTools の設定での実験の一覧  
    :::image-end:::  
    
1.  [**実験**] ページで、使用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じてからもう一度開きます。  

> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。  実験的な機能を無効にするには、[**実験**] ページを開き、無効にする実験的機能のチェックボックスをオフにします。  

## 強調表示された実験的な機能  

以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。  

| 実験的機能 | Microsoft Edge バージョン |  
|:--- |:--- |  
| [カスタムキーボードショートカットの [設定] タブを有効にする](#enable-custom-keyboard-shortcuts-settings-tab) | 84以降 |
| [新しい CSS グリッドのデバッグ機能を有効にする](#enable-new-css-grid-debugging-features) | 85以降 |  
| [パネル間でタブを移動できるようにサポートを有効にする](#enable-support-to-move-tabs-between-panels) | 85以降 |  
| [Web ヒントを有効にする](#enable-webhint) | 85以降 | 

### カスタムキーボードショートカットの [設定] タブを有効にする

Devtools での開発ツールでの[キーボードショートカット][DevToolsShortcuts]の[一致を有効][VisualstudioCode]にするための新しい**ショートカット**ページが用意さ[れてい][DevToolsCustomizeSettings]ます。  

この実験を有効にしたら、を押して、[ [Devtools][DevToolsCustomizeSettings] ] の設定をもう一度開き `Shift` + `?` ます。  [新しい**ショートカット**] ページに移動します。  [**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。  DevTools のキーボードショートカットは、VS コードで同等のアクションのショートカットと一致するようになりました。  

:::image type="complex" source="./media/experiments-keyboard-shortcut.png" alt-text="開発ツールのキーボードショートカットを VS コードに一致させる" lightbox="./media/experiments-keyboard-shortcut.png":::
   開発ツールのキーボードショートカットを VS コードに一致させる
:::image-end:::  

たとえば、Windows では、 [VS コード][VisualstudioCodeShortcutsKeyboardWindows]でスクリプトを一時停止または実行し続けるためのキーボードショートカットが `F5` あります。  **Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットが `F8` **Visual Studio のコード**プリセットでも使用できるようになりました `F5` 。  

### 新しい CSS グリッドのデバッグ機能を有効にする  

CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。  DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.png":::
   CSS グリッドのデバッグ機能  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### パネル間でタブを移動できるようにサポートを有効にする  

通常、**要素**や**ネットワーク**などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。  同様に、 **3D ビュー**や**問題**などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。  この実験が選択されている場合は、タブ上でマウスをポイントし、コンテキストメニューを開き (右クリック \)、[**上へ移動**] または [**下へ移動] を**選択して、ツールを上下のパネル間で移動することができます。   この実験では、DevTools レイアウトをカスタマイズできます。  下部パネルの表示と非表示を切り替えるには、キーを押し `Escape` ます。  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.png":::
   パネル間でタブを移動する  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Web ヒントを有効にする  

[webhint][WebhintMain]は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。  この実験では、[[問題][DevtoolsIssues]] パネルの devtools に対する webhint のフィードバックを提供します。  この問題を選択すると、問題の解決方法と、web サイト上の影響を受けるリソースの一覧についてのドキュメントが表示されます。  リソースリンクを選んで、DevTools で関連する**ネットワーク**、**ソース**、または**要素**のウィンドウを開きます。  

:::image type="complex" source="./media/experiments-webhint.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.png":::
   [問題] パネルでの webhint のフィードバック  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

## 以前の実験的な機能  

*   Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。  

## 実験的な機能についてフィードバックを提供する  

Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。  

*   DevTools のフィードバックアイコンを使ってフィードバックを送信する  
*   [@EdgeDevTools][TwitterEdgedevtools]ツイート  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン" lightbox="./media/devtools-feedback.png":::
   Microsoft Edge DevTools のフィードバックアイコン  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio コード"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio のコードのキーボードショートカット (Windows |) |Visual Studio コード"  

[WebhintMain]: https://webhint.io "web ヒント" 
