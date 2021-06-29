---
description: DevTools の最新のMicrosoft Edge機能
title: 試験的な機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
no-loc:
- Enable webhint
- Enable Network Console
- Source Order Viewer
- Enable Composited Layers in 3D View
- Enable new Font Editor tool within the Styles pane
- Enable new CSS Flexbox debugging features
- Enable + button tab menus to open more tools
- Enable Welcome tab
- 3D View
- Turn on support to move tabs between panels
- Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code
- Edit keyboard shortcuts for any action in the DevTools
- Turn on new CSS grid debugging features
- 'Emulation: Support dual screen mode'
ms.openlocfilehash: dec4b4d111c0eb8dc9cc3963bac7339df1d9b6f6
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624753"
---
# <a name="experimental-features"></a>試験的な機能  

Microsoft EdgeDevTools は、開発中の実験的な機能にアクセスできます。  各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。  

試験的な機能は、Microsoft Edgeのすべてのチャネルで利用できる一方で、Microsoft Edge Canary チャネル を使用して最新の実験機能を取得できます。  

## <a name="turn-on-experimental-features"></a>実験的な機能を有効にする  

\(or off\) の実験機能をオンにMicrosoft Edge手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenIndex]。  
    *   `Control` + `Shift` + `I` \(Windows Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については、「DevTools キーボード[ショートカットMicrosoft Edgeに移動します][DevtoolsShortcutsIndex]。  
1.  [ウィンドウ][ウィンドウ設定][DevToolsCustomizeIndexSettings]開きます。  
    *   を選択します `Shift` + `?` 。  詳細については、「DevTools キーボード[ショートカットMicrosoft Edgeに移動します][DevtoolsShortcutsIndex]。  
1.  [テスト] ウィンドウの**左側設定[** 実験]**セクションを選択**します。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[テスト] ページ (設定" lightbox="../media/experiments-devtools.msft.png":::
       [**テスト]** ページ **(設定**  
    :::image-end:::  
    
1.  [実験 **] ページで** 、利用可能なすべての実験機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。  
1.  DevTools を閉じてMicrosoft Edge開きます。  
    
> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。  実験機能をオフにするには、[実験] ページ **を** 開き、無効にする実験機能のチェック ボックスをオフにします。  

## <a name="highlighted-experimental-features"></a>強調表示された実験的な機能  

次のセクションでは、新しい実験機能について説明します。この機能は、Microsoft Edge。  

| 試験的機能 | Microsoft Edgeバージョン |  
|:--- |:--- |  
| [Enable webhint](#enable-webhint) | 85 以降 |  
| [Enable Network Console](#enable-network-console) | 85 以降 |  
| [Source Order Viewer](#source-order-viewer) | 86 以降 |  
| [Enable Composited Layers in 3D View](#enable-composited-layers-in-3d-view) | 87 以降 |  
| [Enable new Font Editor tool within the Styles pane](#enable-new-font-editor-tool-within-the-styles-pane) | 89 以降 |  
| [Enable new CSS Flexbox debugging features](#enable-new-css-flexbox-debugging-features) | 89 以降 |  
| [Enable + button tab menus to open more tools](#enable--button-tab-menus-to-open-more-tools) | 89 以降 |  
| [Enable Welcome tab](#enable-welcome-tab) | 89 以降 |  

### Enable webhint  

[webhint][WebhintMain] は、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。  webhint によって提供される [フィードバックの種類][WebhintMain]。  

*   アクセシビリティ  
*   ブラウザー間の互換性  
*   セキュリティ  
*   パフォーマンス  
*   プログレッシブ Web アプリ (PWA)  
*   その他の一般的な Web 開発の問題  
    
[webhint 実験では][WebhintMain]、[問題] パネルに webhint フィードバック[が表示][DevtoolsIssuesIndex]されます。  問題を選択して、ソリューションドキュメントと影響を受けるリソースの一覧を Web サイトに表示します。  リソース リンクを選択して、DevTools**で関連する** **[ネットワーク**] 、[ソース] 、または **[要素]** ウィンドウを開きます。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   [問題] パネルの**webhint フィードバック**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Enable Network Console  

**ネットワーク コンソール** は、HTTP を使用してネットワークの代理要求を行う実験の作業タイトルです。  ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。  

実験を有効にしたら、DevTools を再起動してください。  ネットワーク コンソールを **使用するには、** 次の手順を実行します。  

1.  [ネットワーク] **ウィンドウを開** きます。  
1.  変更するネットワーク要求を見つけて再送信します。  
1.  コンテキスト メニュー \(右クリック\) を開き、[編集] と [ **再生] を選択します**。  
1.  ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。  
1.  [送信 **] を選択します**。  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   **コンソール ドロワー****のネットワーク**コンソール  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Source Order Viewer  

**Source Order Viewer** は、Web ページ ソース内の要素の順序を表示する実験です。  画面の表示順序がソースの順序と異なる場合があります。これはスクリーン リーダーとキーボード のユーザーを混同します。  実験を使用して、画面の表示順序とソースの順序の違 **Source Order Viewer** いを見つける。  

実験を有効にしたら、DevTools を再起動してください。  使用するには **Source Order Viewer** 、次の手順を実行します。  

1.  [要素] **ツールを開** きます。  
1.  [スタイル] タブの **右側にある** [アクセシビリティ] **タブを選択** します。  
1.  セクションの **Source Order Viewer** 下で、[ソースの順序を **表示する] チェック ボックスをオン** にします。  
1.  任意の HTML 要素を強調表示して、Web ページ ソース内の順序をオーバーレイで表示します。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="Source Order Viewer in the アクセシビリティ ペイン" lightbox="../media/experiments-source-order-viewer.msft.png"::: **Source Order Viewer** [**アクセシビリティ] ウィンドウ**  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### Enable Composited Layers in 3D View  

z-indexes と Document Object Model \(DOM\) と並んでレイヤーを視覚化できます。  この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。  コンテキスト切り替えの削減が大きな問題だと特定しました。  作成するコードが Web アプリに与える影響は必ずしも明確ではありません。  包括的な視覚的なデバッグ エクスペリエンスのために、複合 3D View レイヤーと複合レイヤーが組み合わされました。  

実験を有効にしたら、DevTools を再起動してください。  コンポジット レイヤー **を使用するには、** 次の手順を実行します。  

1.  ドロワーで、ツールを選択 **3D View** します。  
1.  [複合 **レイヤー] ウィンドウを開** きます。  
1.  アプリのすべてのペイントされたレイヤーが表示されます。  独自の Web アプリでこの機能を試してください。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### Enable new Font Editor tool within the Styles pane  

これで、新しいビジュアル フォント エディターを [使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。  フォントとフォントの特性を定義する場合に使用します。  ビジュアル フォント エディター **を使用すると** 、次の操作を実行できます。  

*   異なるフォント プロパティの単位を切り替える  
*   異なるフォント プロパティのキーワードを切り替える  
*   単位を変換  
*   正確な CSS コードを生成  
    
実験を有効にしたら、DevTools を再起動してください。  新しいビジュアル フォント エディターを **使用するには、** 次の手順を実行します。  

1.  [要素] **ツールを開** きます。  
1.  [スタイル] **ウィンドウを開** きます。  
1.  [フォント エディター **] アイコンを** 選択します。  
    
新しいビジュアル フォント エディターの詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。 ****  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="ビジュアル の [フォント エディター] ウィンドウが強調表示されます" lightbox="../media/font-editor-open.msft.png":::
   ビジュアル の [ **フォント エディター]** ウィンドウが強調表示されます  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable new CSS Flexbox debugging features  

この実験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚化を提供します。  最新の実験機能をプレビューするには、 [この実験を有効にし](#turn-on-experimental-features) 、DevTools を再読み込みします。  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a>[検査] ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する  

[ **検査** ] ツールを使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでホバーして識別し、視覚化できます。  DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。  次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="検査ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   検査ツールを使用して Flexbox コンテナー **を表示** する  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a>Flexbox レイアウトに永続的なオーバーレイを表示する  

バージョン 89 以降Microsoft Edge、実験的な CSS Flexbox 機能では、Flexbox レイアウトで永続的なオーバーレイを有効にするオプションも提供しています。  永続的なオーバーレイには、次の利点があります。  

*   永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時に Web ページに表示されたままです。
*   複数の永続的なオーバーレイを同時に使用して、複数の Flexbox レイアウトを一度に確認できます。  
*   永続的なオーバーレイは、色構成オプションを提供します。  
    
Flexbox レイアウトの永続的なオーバーレイを切り替えるには、次のいずれかのアクションを使用します。  

*   要素ツール **の DOM ツリー** に表示される Flexbox コンテナーの横にある [Flexbox 楕円] アイコン **を選択** します。  
*   [要素] **ツールにある** 新しい [レイアウト] パネルを **開** き、強調表示する各 Flexbox コンテナーの横にあるチェック ボックスをオンにします。  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools の Flex アイコンとレイアウト パネル" lightbox="../media/flexbox-overlay.msft.png":::
   DevTools **の** Flex アイコンとレイアウト パネル  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a>永続的なオーバーレイを構成する  

CSS グリッドまたは Flexbox レイアウトの永続的オーバーレイのオプションを構成するには、[レイアウト] ウィンドウ **を使用** します。  [ **レイアウト** ] ウィンドウは、[スタイル] ウィンドウと **[** 計算] ウィンドウの横にある **[** 要素] **ツールに** 配置されます。  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="レイアウト パネル" lightbox="../media/flexbox-layout.msft.png":::
   レイアウト パネル  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable + button tab menus to open more tools  

新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。  実験を有効にし、DevTools を再読み込みすると、DevTools の上部にあるタブ グループの右側にプラス記号 **Enable + button tab menus to open more tools** `+` \( \) が表示されます。  タブ バーに追加できるその他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部ウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   **上部ウィンドウの** [その他のツール]
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable Welcome tab

この実験では **、What's New ツールを新** しいウェルカム ツール **に置き換** える。  次のコンテンツの更新されたデザインが表示されます。  

*   開発者向けドキュメントへのリンク  
*   最新の機能  
*   リリース ノート  
*   DevTools チームにMicrosoft Edgeするオプション  
    
ウェルカム**ツールは**、更新後に自動的に開Microsoft Edge。  更新後にウェルカム ツール**** が表示されるのを防ぐには、[ようこそ]**** ツールのタイトルの下にある更新の後、[開く] タブの横にあるチェック ボックス**を**オフにします。  

元の **[What's New]** ツールを使用する場合は、[テスト] 設定に移動し、[テスト][の横にある][DevtoolsCustomizeIndexSettings]チェック  >  **** ボックスをオフにします **Enable Welcome tab** 。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   **ウェルカム** ツール  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a>以前の実験的な機能  

*   [3D View][Devtools3dViewIndex]バージョン 83 以降で既定Microsoft Edge有効になっています。  
*   [Turn on support to move tabs between panels][DevtoolsCustomizeIndex]バージョン 85 以降で既定Microsoft Edge有効になっています。  
*   [Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]バージョン 86 以降で既定Microsoft Edge有効になっています。  
*   [Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]バージョン 89 以降で既定Microsoft Edge有効になっています。  
*   [Turn on new CSS grid debugging features][DevtoolsCssGrid]バージョン 89 以降で既定Microsoft Edge有効になっています。  
*   [Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables]バージョン 90 以降で既定Microsoft Edge有効になっています。  

## <a name="providing-feedback-on-experimental-features"></a>実験的な機能に関するフィードバックの提供  

DevTools 実験に関Microsoft Edgeフィードバックを提供する場合、または DevTools に関連するその他の情報を提供する。  

*   DevTools の [フィードバック **の送信** ] アイコンを使用してフィードバックを送信する  
*   ツイートの [@EdgeDevTools][TwitterEdgedevtools]  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の **[フィードバックの送信]** アイコン  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  
[Devtools3dViewIndex]: ../3d-view/index.md "3D View |Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "DevTools ページで CSS グリッドMicrosoft Edgeを調|Microsoft Docs"  
[DevtoolsCustomizeIndex]: ../customize/index.md "DevTools Microsoft Edgeのカスタマイズ|Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools "DevTools 内の任意のアクションのキーボード ショートカットを編集する |Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code "DevTools のキーボード ショートカットをコードMicrosoft Visual Studio一致 |Microsoft Docs"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみMicrosoft Edgeエミュレート|Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "DevTools アプリケーションでデバイス モードでモバイル Microsoft Edgeをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "[問題] ツール を使用して問題を見つけて修正|Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft EdgeDevTools キーボード ショートカット |Microsoft Docs"  
<!-- external links: -->
[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  
[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft EdgeDevTools |Twitter"  
[WebhintMain]: https://webhint.io "webhint"  
