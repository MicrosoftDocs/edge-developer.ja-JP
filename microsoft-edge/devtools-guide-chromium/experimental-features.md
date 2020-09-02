---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: 4915c909921bb4c5eaa8d727ab7a08493b941445
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986123"
---
# 試験的機能  

Microsoft Edge DevTools でまだ開発中の実験的な機能を使って、各リリース前に [フィードバック](#providing-feedback-on-experimental-features) をテストして提供することができます。  

Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。  

## 実験的な機能を有効にする  

Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。  

1.  [DevTools を開き][DevtoolsOpen]ます。  
     *   [ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。  
    *   を選択し `Shift` + `?` ます。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.png":::
       DevTools の設定での実験の一覧  
    :::image-end:::  
    
1.  [ **実験** ] ページで、使用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じてからもう一度開きます。  

> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。  実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。  

## 強調表示された実験的な機能  

以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。  

| 実験的機能 | Microsoft Edge バージョン |  
|:--- |:--- |  
| [カスタムキーボードショートカットの [設定] タブを有効にする](#enable-custom-keyboard-shortcuts-settings-tab) | 84以降 |
| [新しい CSS グリッドのデバッグ機能を有効にする](#enable-new-css-grid-debugging-features) | 85以降 |  
| [パネル間でタブを移動できるようにサポートを有効にする](#enable-support-to-move-tabs-between-panels) | 85以降 |  
| [Web ヒントを有効にする](#enable-webhint) | 85以降 |  
| [ネットワーク本体を有効にする](#enable-network-console) | 85以降 |  
| [ソースオーダービューアーを有効にする](#enable-source-order-viewer) | 86以降 |  

### カスタムキーボードショートカットの [設定] タブを有効にする  

Devtools の [[設定][DevToolsCustomizeSettings]] で新しい [**ショートカット**] ページが用意されています。これにより、devtools での[キーボードショートカット][DevToolsShortcuts]を[Microsoft Visual Studio コード][VisualstudioCode]に対応付けることができます。  

実験を有効にしたら、[選択] を使用して[Devtools の設定][DevToolsCustomizeSettings]をもう一度開き `Shift` + `?` ます。  [新しい **ショートカット** ] ページに移動します。  [**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。  DevTools のキーボードショートカットは、Visual Studio コードで同等のアクションのショートカットと一致するようになりました。  

:::image type="complex" source="./media/experiments-keyboard-shortcut.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="./media/experiments-keyboard-shortcut.png":::
   DevTools for Visual Studio コードのキーボードショートカットを一致させる  
:::image-end:::  

たとえば、Windows では、 [Visual Studio コード][VisualstudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは `F5` です。  **Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットを使うことが `F8` できます。  **Visual Studio コード**の事前設定を使用すると、ショートカットも表示され `F5` ます。  

### 新しい CSS グリッドのデバッグ機能を有効にする  

CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。  DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.png":::
   CSS グリッドのデバッグ機能  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### パネル間でタブを移動できるようにサポートを有効にする  

通常、 **要素** や **ネットワーク** などのツールは、devtools のメイン \ (トップ) パネルでのみ開くことができます。  同様に、 **3D ビュー** や **問題** などのツールは、devtools のドローワ \ (ボトム \) パネルでのみ開くことができます。  実験を選択した場合、タブ上でマウスポインターを移動し、コンテキストメニューを開き (\ 右クリック \)、[ **上へ移動** ] または [ **下へ移動**] を選びます。   この実験では、DevTools レイアウトをカスタマイズできます。  下部パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.png":::
   パネル間でタブを移動する  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Web ヒントを有効にする  

[webhint][WebhintMain] は、アクセシビリティ、クロスブラウザーの互換性、セキュリティ、パフォーマンス、pwas、web サイトのその他の一般的な web 開発の問題に関するフィードバックをリアルタイムで提供するオープンソースツールです。  [Webhint][WebhintMain]の実験では、webhint のフィードバックが、[[問題][DevtoolsIssues]] パネルの devtools に取り込まれます。  この問題を選択すると、問題の解決方法と、web サイト上の影響を受けるリソースの一覧についてのドキュメントが表示されます。  リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。  

:::image type="complex" source="./media/experiments-webhint.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.png":::
   [ **問題** ] パネルでの webhint のフィードバック  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ネットワーク本体を有効にする  

**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。  **ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。  

実験を有効にした後、DevTools を再起動してください。  ネットワークコンソールを使用するには:  

1.  [ **ネットワーク** ] ウィンドウを開きます。  
1.  変更して再送信するネットワーク要求を見つけます。  
1.  コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。  
1.  **ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。  
1.  [ **送信**] を選びます。  

:::image type="complex" source="./media/network-network-console.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.png":::
   **Console**ドローワの**ネットワーク本体**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  --> 

### ソースオーダービューアーを有効にする  

**ソースオーダービューアー** は、実験の作業タイトルであり、ページソース内の要素の順序を表示します。  **ソース注文ビューアー**を使って、ページ内のアクセシビリティの問題を見つけることができます。これは、画面の表示順序がソースの順序とは異なる場合があります。これは、混乱させるスクリーンリーダーのユーザーであるためです。  

実験を有効にした後、DevTools を再起動してください。  ソースオーダービューアーを使用するには:  

1.  [ **要素** ] ウィンドウを開く。  
1.  [引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。  
1.  [ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。  
1.  任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソースオーダービューアー" lightbox="./media/experiments-source-order-viewer.msft.png":::
   [**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## 以前の実験的な機能  

*   Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。  

## 実験的な機能についてフィードバックを提供する  

Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。  

*   DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する  
*   [@EdgeDevTools][TwitterEdgedevtools]ツイート   

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[VisualstudioCode]: https://code.visualstudio.com "Microsoft Visual Studio コード"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio のコードのキーボードショートカット (Windows |) |Microsoft Visual Studio コード"  

[WebhintMain]: https://webhint.io "web ヒント" 
