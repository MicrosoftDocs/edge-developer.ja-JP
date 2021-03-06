---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: b366cfeccafe874bc9e76d3b66659122c5d07c69
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398680"
---
# <a name="experimental-features"></a>試験的機能  

Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできます。  各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。  

実験機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の実験機能を利用できます。  

## <a name="turn-on-experimental-features"></a>実験的な機能を有効にする  

Microsoft Edge で \(or off\) 実験機能を有効にするには、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
    *   `Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevToolsShortcuts]。  
1.  [設定] [ウィンドウを開][DevToolsCustomizeIndexSettings] きます。  
    *   を選択します `Shift` + `?` 。  詳細については [、「Microsoft Edge DevTools キーボード ショートカット」に移動します][DevToolsShortcuts]。  
1.  [設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[設定] の [実験] ページ" lightbox="../media/experiments-devtools.msft.png":::
       [ **設定] の** [実験] **ページ**  
    :::image-end:::  
    
1.  [実験 **] ページで** 、利用可能なすべての実験機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じて再度開きます。  
    
> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。  実験機能をオフにするには、[実験] ページ **を** 開き、無効にする実験機能のチェック ボックスをオフにします。  

## <a name="highlighted-experimental-features"></a>強調表示された実験的な機能  

次のセクションでは、Microsoft Edge で使用できる新しい実験的機能について説明します。  

| 試験的機能 | Microsoft Edge バージョン |  
|:--- |:--- |  
| [Webhint を有効にする](#enable-webhint) | 85 以降 |  
| [ネットワーク コンソールの有効化](#enable-network-console) | 85 以降 |  
| [ソース オーダー ビューアー](#source-order-viewer) | 86 以降 |  
| [キーボード ショートカット エディターを有効にする](#enable-keyboard-shortcut-editor) | 87 以降 |  
| [3D ビューで複合レイヤーを有効にする](#enable-composited-layers-in-3d-view) | 87 以降 |  
| [[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする](#enable-new-font-editor-tool-within-the-styles-pane) | 89 以降 |  
| [CSS Flexbox の新しいデバッグ機能を有効にする](#enable-new-css-flexbox-debugging-features) | 89 以降 |  
| [[+ ボタン] タブ メニューを有効にして、その他のツールを開く](#enable--button-tab-menus-to-open-more-tools) | 89 以降 |  
| [[ようこそ] タブを有効にする](#enable-welcome-tool) | 89 以降 |  

### <a name="enable-new-css-grid-debugging-features"></a>新しい CSS グリッド デバッグ機能を有効にする  

この実験的な機能は、CSS グリッド レイアウトのデバッグに役立つ多数の新しい視覚化を提供します。  最新の実験機能をプレビューするには、この [実験を有効にして](#turn-on-experimental-features) DevTools を再読み込みします。  この実験は、Microsoft Edge バージョン 87 以降で既定で有効になっています。  

#### <a name="viewing-on-hover-grid-overlays-with-the-inspect-tool"></a>[検査] ツールを使用してオンホバー グリッド オーバーレイを表示する  

[ **検査** ] ツールを使用すると、Web サイト内の CSS グリッド レイアウトをマウスでホバーして識別し、視覚化できます。  DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。  次に、デバッグする `Grid` Web ページの要素にマウス ポインターを置きます。  アウトラインはグリッドの周囲に表示され、ハッチングはグリッドギャップが存在する場合の位置を示します。  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="[検査] ツールを使用してグリッドを表示する" lightbox="../media/grid-inspect.msft.png":::
   [検査] ツールを使用してグリッド **を表示** する  
:::image-end:::  

#### <a name="viewing-persistent-grid-overlays"></a>永続的なグリッド オーバーレイの表示  

Microsoft Edge バージョン 86 以降では、実験的な CSS グリッド機能では、永続的なグリッド オーバーレイを有効にするオプションも提供しています。  永続的なオーバーレイには、いくつかの利点があります。  

*   永続的なオーバーレイは、スクロール、マウスの移動、DevTools の他の機能の使用時にページに表示されたままです。  
*   複数の永続的なオーバーレイを同時にオンにすることで、複数のグリッド レイアウトを一度に確認できます。  
*   永続的なオーバーレイには、グリッド領域の名前の非表示や表示、グリッドギャップ、トラックサイズなど、多くの構成オプションがあります。  
    
永続的なグリッド オーバーレイを切り替える 2 つの方法。  

*   要素ツール **の DOM** ツリーに表示される Grid 要素の横にあるグリッド楕円アイコンを **選択** します。  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="要素ツールのグリッド楕円アイコン" lightbox="../media/grid-adorner.msft.png":::
       要素ツールのグリッド **楕円** アイコン  
    :::image-end:::  
    
*   [要素] **ツールにある** 新しいレイアウト パネルを開き、強調表示する各 Grid 要素の横にあるチェック ボックスをオンにします。  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools のレイアウト パネル" lightbox="../media/grid-layout-zoom.msft.png":::
       **** DevTools のレイアウト パネル  
    :::image-end:::  
    
#### <a name="configuring-persistent-overlays"></a>永続的なオーバーレイの構成  

Microsoft Edge バージョン 86 以降では、新しいレイアウト パネルが****[スタイル]**** パネルと [計算] パネルと並んで [要素] ツール**に配置**されます。 ****  レイアウト **パネルは** 、永続的なオーバーレイの構成オプションを表示します。  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="../media/experiments-grid.msft.png":::
   CSS グリッドのデバッグ機能  
:::image-end:::  

### <a name="enable-support-to-move-tabs-between-panels"></a>パネル間でタブを移動するサポートを有効にする  

通常、Elements や******Network**などのツールは、DevTools の上部にあるメイン パネルでのみ開くことができます。  **3D ビュー**や**Issues**のようなツールで、通常は**** DevTools の下部にあるドロワー パネルでのみ開きます。  実験を選択した後、上部パネルと下部パネルの間でツールを移動できます。  ツールを移動するには、タブにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[上へ移動] または [下へ移動]**を選択します**。 ****   この実験では、DevTools レイアウトをカスタマイズできます。  ドロワー パネルを表示または非表示 **にする** 場合は、 を選択します `Escape` 。  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="パネル間でのツールの移動" lightbox="../media/experiments-move-panels.msft.png":::
   パネル間でのツールの移動  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-webhint"></a>Webhint を有効にする  

[webhint][WebhintMain] は、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。  webhint によって提供される [フィードバックの種類][WebhintMain]。  

*   アクセシビリティ  
*   ブラウザー間の互換性  
*   セキュリティ  
*   パフォーマンス  
*   プログレッシブ Web アプリ (PWA)  
*   その他の一般的な Web 開発の問題  
    
[webhint 実験では][WebhintMain]、[問題] パネルに webhint フィードバック[が表示][DevtoolsIssues]されます。  問題を選択して、ソリューションドキュメントと影響を受けるリソースの一覧を Web サイトに表示します。  リソース リンクを選択して、DevTools**で関連する** **[ネットワーク**] 、[ソース] 、または **[要素]** ウィンドウを開きます。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   [問題] パネルの**webhint フィードバック**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### <a name="enable-network-console"></a>ネットワーク コンソールの有効化  

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

### <a name="source-order-viewer"></a>ソース オーダー ビューアー  

**ソース オーダー ビューアー** は、Web ページ ソース内の要素の順序を表示する実験です。  画面の表示順序がソースの順序と異なる場合があります。これはスクリーン リーダーとキーボード のユーザーを混同します。  [ソースオーダー **ビューアー] 実験** を使用して、画面の表示順序とソースの順序の違いを確認します。  

実験を有効にしたら、DevTools を再起動してください。  ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。  

1.  [要素] **ツールを開** きます。  
1.  引き出し \(bottom\) パネルで [アクセシビリティ] ウィンドウを開きます。 ****  
1.  [ソース注文 **ビューアー] セクションで** 、[ソースの順序を **表示する] チェック ボックスをオン** にします。  
1.  任意の HTML 要素を強調表示して、Web ページ ソース内の順序をオーバーレイで表示します。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウの [ソースオーダー ビューアー]" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **[アクセシビリティ] ウィンドウ** の **[ソースオーダー** ビューアー]  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### <a name="enable-keyboard-shortcut-editor"></a>キーボード ショートカット エディターを有効にする

[キーボード **ショートカット エディターの有効化]** 実験を有効にすると、DevTools 内の任意のアクションに合わせてキーボード ショートカットをカスタマイズできます。  特定のアクションのキーボード ショートカットをカスタマイズするには、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
1.  [設定 [] を開きます][DevToolsCustomizeIndexSettings]。  
    *   を選択します `Shift` + `?` 。  
1.  [ショートカット] ページ **に移動** します。  
1.  カスタマイズするアクションを選択します。  
1.  [編集**** \( ![ EditKeyboardShortcut ](../media/edit-keyboard-shortcut-icon.msft.png) \) ] アイコンを選択します。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選択します。" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       [設定] の [ショートカット] ページ **から** カスタマイズするアクションを選択 [します。][DevToolsCustomizeIndexSettings]  
    :::image-end:::  
    
1.  キーボードで、アクションにバインドするキーを選択します。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       アクションに割り当てるキーを選択する  
    :::image-end:::  
    
1.  新しいキーボード ショートカットを保存するには、チェックマーク \(![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)\) アイコン。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="チェックマークアイコンを選択して新しいキーボード ショートカットを保存する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       チェックマークアイコンを選択して新しいキーボード ショートカットを保存する  
    :::image-end:::  
    
1.  新しいキーボード ショートカットを選択して、DevTools でアクションをトリガーします。  
    
[ショートカット **] ページで** 、カスタム **キーボード** ショートカット \( ![ CustomKeyboardShortcut \) アイコンに、カスタマイズした ](../media/custom-keyboard-shortcut-icon.msft.png) キーボード ショートカットが表示されます。  すべてのショートカットをリセットするには、[既定のショートカット **を復元する] を選択します**。  

アクションのキーボード ショートカットの編集中に変更を破棄するには、X \( ![ XKeyboardShortcut ](../media/discard-changes-keyboard-shortcut-icon.msft.png) \) アイコンを選択します。  特定のアクションのショートカットを削除するには、[削除] ショートカット **\(** ![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) アイコンを選択します。  アクションに複数のショートカットを追加するには、[ショートカットの追加 **] を選択します**。  

> [!NOTE]
> キーボード ショートカットが現在別のアクションに割り当てられている場合は、新しいアクションに保存できない場合があります。  最初に、前の操作のキーボード ショートカットを削除してから、新しいアクションに追加する必要があります。  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-composited-layers-in-3d-view"></a>3D ビューで複合レイヤーを有効にする  

z-indexes と Document Object Model \(DOM\) と並んでレイヤーを視覚化できます。  この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。  コンテキスト切り替えの削減が大きな問題だと特定しました。  作成するコードが Web アプリに与える影響は必ずしも明確ではありません。  視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。  

実験を有効にしたら、DevTools を再起動してください。  コンポジット レイヤー **を使用するには、** 次の手順を実行します。  

1.  ドロワーで **、[3D ビュー] ツールを選択** します。  
1.  [複合 **レイヤー] ウィンドウを開** きます。  
1.  アプリのすべてのペイントされたレイヤーが表示されます。  独自の Web アプリでこの機能を試してください。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### <a name="enable-new-font-editor-tool-within-the-styles-pane"></a>[スタイル] ウィンドウ内で新しいフォント エディター ツールを有効にする  

これで、新しいビジュアル フォント エディターを [使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。  フォントとフォントの特性を定義する場合に使用します。  ビジュアル フォント エディター **を使用すると** 、次の操作を実行できます。  

*   さまざまなフォント プロパティの単位を切り替える  
*   異なるフォント プロパティのキーワードを切り替える  
*   単位の変換  
*   正確な CSS コードを生成する  
    
実験を有効にしたら、DevTools を再起動してください。  新しいビジュアル フォント エディターを **使用するには、** 次の手順を実行します。  

1.  [要素] **ツールを開** きます。  
1.  [スタイル] **ウィンドウを開** きます。  
1.  [フォント エディター **] アイコンを** 選択します。  
    
新しいビジュアル フォント エディターの詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントスタイルと設定の編集] に移動します。 ****  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="ビジュアル の [フォント エディター] ウィンドウが強調表示されます" lightbox="../media/font-editor-open.msft.png":::
   ビジュアル の [ **フォント エディター]** ウィンドウが強調表示されます  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-new-css-flexbox-debugging-features"></a>CSS Flexbox の新しいデバッグ機能を有効にする  

この実験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚化を提供します。  最新の実験機能をプレビューするには、 [この実験を有効にし](#turn-on-experimental-features) 、DevTools を再読み込みします。  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a>[検査] ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する  

[ **検査** ] ツールを使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでホバーして識別し、視覚化できます。  DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。  次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="検査ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   検査ツールを使用して Flexbox コンテナー **を表示** する  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a>Flexbox レイアウトに永続的なオーバーレイを表示する  

Microsoft Edge バージョン 89 以降では、実験的な CSS Flexbox 機能では、Flexbox レイアウトで永続的なオーバーレイを有効にするオプションも提供しています。  永続的なオーバーレイには、次の利点があります。  

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

### <a name="enable--button-tab-menus-to-open-more-tools"></a>[+ ボタン] タブ メニューを有効にして、その他のツールを開く  

新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。  [有効にする] **+** [ボタン] タブ メニューをオンにして、さらに多くのツール実験を開き、DevTools を再読み込みすると、DevTools の上部にあるタブ グループの右側にプラス記号 \( \) が表示されます。 `+`  タブ バーに追加できるその他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部ウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   **上部ウィンドウの** [その他のツール]
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### <a name="enable-welcome-tool"></a>ウェルカム ツールを有効にする

この実験では **、What's New ツールを新** しいウェルカム ツール **に置き換** える。  次のコンテンツの更新されたデザインが表示されます。  

*   開発者向けドキュメントへのリンク  
*   最新の機能  
*   リリース ノート  
*   Microsoft Edge DevTools チームに連絡するオプション  
    
ウェルカム **ツールは** 、Microsoft Edge への更新の後に自動的に開きます。  更新後にウェルカム ツール**** が表示されるのを防ぐには、[ようこそ]**** ツールのタイトルの下にある更新の後、[開く] タブの横にあるチェック ボックス**を**オフにします。  

元の [What's **New]** ツールを[][DevtoolsCustomizeIndexSettings]使用する場合は、[設定の実験] に移動し、[ようこそ] タブを有効にするの横にあるチェック  >  ******ボックスをオフにします**。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   **ウェルカム** ツール  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a>以前の実験的な機能  

*   Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能で、既定で有効になっています。  
*   [Microsoft][DevtoolsMoveTabs] Edge バージョン 85 以降では、パネル間でタブを移動するサポートを有効にし、既定で有効になっています。  
*   [Microsoft][DevtoolsCustomKeyboardShortcuts] Edge バージョン 86 以降では、[キーボード ショートカットのカスタマイズ] が使用可能になっていて、既定で有効になっています。  
*   [エミュレーション: Microsoft][DevtoolsDeviceModeDualScreenAndFoldables] Edge バージョン 89 以降では、デュアル スクリーン モードをサポートし、既定で有効になっています。  
*   [新しい CSS グリッド デバッグ機能][DevtoolsCssGrid] を有効にし、Microsoft Edge バージョン 89 以降で既定で有効にしました。  
    
## <a name="providing-feedback-on-experimental-features"></a>実験的な機能に関するフィードバックの提供  

Microsoft Edge DevTools 実験、または DevTools に関連するその他のフィードバックを提供する。  

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

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "Microsoft Edge DevTools サーバーで CSS グリッドを検査|Microsoft Docs"  
[DevtoolsMoveTabs]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードでモバイル デバイスをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools の [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsIssues]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアントの|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
