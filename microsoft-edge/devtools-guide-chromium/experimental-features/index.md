---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/04/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: 32eaa3e8d41efefa669142297891e7c62cf4eb5b
ms.sourcegitcommit: d53421b7219ad87fa9d58f601d9c61ee44c2e43a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313466"
---
# 試験的機能  

Microsoft Edge DevTools は、まだ開発中の試験的な機能にアクセスできます。  各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。  

試験的な機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の試験的な機能を利用できます。  

## 試験的な機能を有効にする  

Microsoft Edge で実験的な機能 \(またはオフ\) を有効にする場合は、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
    *   `Control` + `Shift` + `I` \(Windows,Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  
1.  [設定] [ウィンドウを開][DevToolsCustomizeIndexSettings] きます。  
    *   選択 `Shift` + `?` します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  
1.  [設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="[設定] の [実験] ページ" lightbox="../media/experiments-devtools.msft.png":::
       [ **設定] の** [実験] **ページ**  
    :::image-end:::  
    
1.  [ **実験] ページで** 、利用可能なすべての試験的な機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じてから再度開きます。  
    
> [!NOTE]
> 試験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。  試験的な機能をオフにする場合は、[ **実験** ] ページを開き、無効にする試験的な機能のチェック ボックスをオフにします。  

## 強調表示された実験的な機能  

次のセクションでは、Microsoft Edge で使用可能な新しい試験的な機能について説明します。  

| 試験的機能 | Microsoft Edge のバージョン |  
|:--- |:--- |  
| [webhint を有効にする](#enable-webhint) | 85 以降 |  
| [ネットワーク コンソールを有効にする](#enable-network-console) | 85 以降 |  
| [ソース オーダー ビューアー](#source-order-viewer) | 86 以降 |  
| [キーボード ショートカット エディターを有効にする](#enable-keyboard-shortcut-editor) | 87 以降 |  
| [3D ビューで複合レイヤーを有効にする](#enable-composited-layers-in-3d-view) | 87 以降 |  
| [[スタイル] ウィンドウで新しいフォント エディター ツールを有効にする](#enable-new-font-editor-tool-within-the-styles-pane) | 89 以降 |  
| [新しい CSS Flexbox デバッグ機能を有効にする](#enable-new-css-flexbox-debugging-features) | 89 以降 |  
| [[+] ボタン タブ メニューを有効にして、その他のツールを開く](#enable--button-tab-menus-to-open-more-tools) | 89 以降 |  
| [[ようこそ] タブを有効にする](#enable-welcome-tool) | 89 以降 |  

### 新しい CSS グリッド デバッグ機能を有効にする  

この試験的な機能は、CSS グリッド レイアウトのデバッグに役立つ新しい視覚エフェクトを多数提供します。  最新の試験的な機能をプレビューするには、 [この実験を有効](#turn-on-experimental-features) にし、DevTools を再読み込みします。  この実験は、Microsoft Edge バージョン 87 以降で既定で有効になっています。  

#### Inspect ツールを使用した、ホバー時のグリッド オーバーレイの表示  

検査 **ツール** を使用すると、Web サイト内の CSS グリッド レイアウトをマウスでポイントすることで、簡単に識別して視覚化できます。  DevTools **の左上隅** にある Inspect ![ \( Inspect ](../media/inspect-icon.msft.png) \) アイコンを選択します。  次に、デバッグする Web サイトの Grid 要素をポイントします。  枠線はグリッドの周囲に表示され、網かけはグリッドのギャップがある場合の位置を示します。  

:::image type="complex" source="../media/grid-inspect.msft.png" alt-text="検査ツールを使用してグリッドを表示する" lightbox="../media/grid-inspect.msft.png":::
   検査ツールを使用してグリッド **を表示** する  
:::image-end:::  

#### 固定グリッド オーバーレイの表示  

Microsoft Edge バージョン 86 以降では、試験的な CSS グリッド機能を使用して、永続的なグリッド オーバーレイを有効にすることもできます。  永続的なオーバーレイには、いくつかの利点があります。  

*   永続的なオーバーレイは、スクロール、マウスの移動、DevTools のその他の機能の使用時にページに表示されたままです。  
*   複数の固定オーバーレイを同時に有効にすることができ、複数のグリッド レイアウトを一度に確認できます。  
*   永続的なオーバーレイには、グリッド領域での名前の非表示や表示、グリッド のギャップ、トラックのサイズなど、多くの構成オプションが用意されています。  
    
固定グリッド オーバーレイを切り替える 2 つの方法。  

*   要素ツール **の DOM** ツリーに表示される Grid 要素の横にある Grid 楕円アイコンを **選択** します。  
    
    :::image type="complex" source="../media/grid-adorner.msft.png" alt-text="要素ツールのグリッド楕円アイコン" lightbox="../media/grid-adorner.msft.png":::
       要素ツールのグリッド楕 **円** アイコン  
    :::image-end:::  
    
*   要素ツール **にある新しいレイアウト** パネルを開き、強調表示する各 Grid 要素の横にあるチェック ボックスをオンにします。  
    
    :::image type="complex" source="../media/grid-layout-zoom.msft.png" alt-text="DevTools のレイアウト パネル" lightbox="../media/grid-layout-zoom.msft.png":::
       **** DevTools のレイアウト パネル  
    :::image-end:::  
    
#### 永続的なオーバーレイの構成  

Microsoft Edge バージョン 86 以降では、新しい**レイアウト**パネルは****[スタイル] タブと [計算] タブと共に**要素ツール****にあります**。  レイアウト **パネルは** 、永続的なオーバーレイの構成オプションを表示します。  

:::image type="complex" source="../media/experiments-grid.msft.png" alt-text="CSS グリッド デバッグ機能" lightbox="../media/experiments-grid.msft.png":::
   CSS グリッド デバッグ機能  
:::image-end:::  

### パネル間でタブを移動するサポートを有効にする  

通常 **、Elements** や **Network** などのツールは、DevTools の上部にあるメイン パネルでのみ開くことができます。  **3D ビュー**や問題**** のようなツール。通常は DevTools**** の下部にあるドロワー パネルでのみ開きます。  実験を選択した後、上部と下部のパネルの間でツールを移動できます。  ツールを移動するには、タブをポイントし、コンテキスト メニュー \(右クリック\) を開**** き、[上へ移動] または [下へ移動] を選択**します**。   この実験では、DevTools レイアウトをカスタマイズできます。  ドロワー パネルを表示または非表示 **にする** 場合は、次を選択します `Escape` 。  

:::image type="complex" source="../media/experiments-move-panels.msft.png" alt-text="パネル間でのタブの移動" lightbox="../media/experiments-move-panels.msft.png":::
   パネル間でのタブの移動  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### webhint を有効にする  

[webhint は][WebhintMain] 、Web サイトとローカル Web ページに対してリアルタイムのフィードバックを提供するオープン ソース ツールです。  Webhint によって提供される [フィードバックの種類][WebhintMain]。  

*   アクセシビリティ  
*   ブラウザー間の互換性  
*   セキュリティ  
*   performance  
*   段階的な Web アプリ (PAS)  
*   その他の一般的な Web 開発の問題  
    
[webhint 実験は][WebhintMain]、[問題] パネルに webhint フィードバック[を表示][DevtoolsIssues]します。  問題を選択して、ソリューション ドキュメントと、Web サイト上の影響を受けるリソースの一覧を表示します。  DevTools で関連する****[ネットワーク] ウィンドウ、[ソース] ウィンドウ、**または**[**要素**] ウィンドウを開くリソース リンクを選択します。  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="[問題] パネル内の webhint のフィードバック" lightbox="../media/experiments-webhint.msft.png":::
   [問題] パネルの **webhint** フィードバック  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ネットワーク コンソールを有効にする  

**ネットワーク コンソール** は、HTTP を使用して合成ネットワーク要求を行う実験の動作タイトルです。  ネットワーク コンソールの実験 **を使用して** 、Web API 要求を送信できます。  

実験を有効にした後、DevTools を再起動してください。  ネットワーク コンソールを **使用するには、次**の手順を実行します。  

1.  [ネットワーク] **ウィンドウを開** きます。  
1.  変更するネットワーク要求を検索し、再送信します。  
1.  コンテキスト メニュー \(右クリック\) を開き、[編集と再生] **を選択します**。  
1.  ネットワーク コンソール **が開いたら** 、ネットワーク要求情報を編集します。  
1.  Choose **Send**.  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="コンソール ドロワーのネットワーク コンソール" lightbox="../media/network-network-console.msft.png":::
   **コンソール ドロワー****のネットワーク**コンソール  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ソース オーダー ビューアー  

**ソース オーダー ビューアーは** 、Web ページ ソース内の要素の順序を表示する実験です。  スクリーン リーダーとキーボード のユーザーを混乱させるソースの順序と、画面の表示順序が異なる場合があります。  ソース オーダー **ビューアーの実験を使用** して、画面の表示順序とソースの順序の違いを確認します。  

実験を有効にした後、DevTools を再起動してください。  ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。  

1.  要素ツール **を開** きます。  
1.  ドロワー **\(** 下\) パネルの [アクセシビリティ] ウィンドウを開きます。  
1.  [ソース オーダー **ビューアー] セクションで** 、[ソース注文の **表示] チェック ボックスをオン** にします。  
1.  任意の HTML 要素を強調表示して、Web ページ ソース内の順序に合ったオーバーレイを表示します。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソース 注文ビューアー" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **[アクセシビリティ] ウィンドウ** のソース **注文** ビューアー  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### キーボード ショートカット エディターを有効にする

キーボード ショートカット **エディターの有効化** 実験を有効にした状態で、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  特定の操作のキーボード ショートカットをカスタマイズするには、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
1.  [設定 [] を開きます][DevToolsCustomizeIndexSettings]。  
    *   選択 `Shift` + `?` します。  
1.  [ショートカット] **ページに移動** します。  
1.  カスタマイズするアクションを選択します。  
1.  [ **編集** \( ![ EditKeyboardShortcut \) ] ](../media/edit-keyboard-shortcut-icon.msft.png) アイコンを選択します。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       [設定] の [ショートカット] ページ **からカスタマイズ** するアクションを選択 [する][DevToolsCustomizeIndexSettings]  
    :::image-end:::  
    
1.  キーボードで、アクションにバインドするキーを選択します。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       アクションに割り当てるキーを選択する  
    :::image-end:::  
    
1.  新しいキーボード ショートカットを保存するには、チェックマーク \(![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)\) アイコン  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する  
    :::image-end:::  
    
1.  DevTools でアクションをトリガーするには、新しいキーボード ショートカットを選択します。  
    
[ショートカット **] ページ** で、ユーザー設定のキーボード ショートカット **\(** CustomKeyboardShortcut \) アイコンに、カスタマイズしたキーボード ![ ](../media/custom-keyboard-shortcut-icon.msft.png) ショートカットが表示されます。  すべてのショートカットをリセットするには、[既定のショートカット **を復元する] を選択します**。  

アクションのキーボード ショートカットの編集中に変更を破棄するには、[X \( ![ XKeyboardShortcut \) ] アイコン ](../media/discard-changes-keyboard-shortcut-icon.msft.png) を選択します。  特定のアクションのショートカットを削除するには、ショートカットの **削除** \( ![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) アイコンを選択します。  1 つのアクションに複数のショートカットを追加するには、[ショートカットの **追加] を選択します**。  

> [!NOTE]
> キーボード ショートカットが別のアクションに現在割り当てられている場合は、新しい操作のためにキーボード ショートカットを保存できない可能性があります。  最初に、前の操作のキーボード ショートカットを削除してから、新しいアクションに追加する必要があります。  

<!--Available in Microsoft Edge version 87 and later.  -->  

### 3D ビューで複合レイヤーを有効にする  

レイヤーを z インデックスとドキュメント オブジェクト モデル \(DOM\) と共に視覚化できます。  この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。  コンテキストの切り替えの削減が大きな問題と見なされました。  作成するコードが Web アプリに与える影響は必ずしも明確ではありません。  視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。  

実験を有効にした後、DevTools を再起動してください。  複合レイヤー **を使用するには、次**の手順を実行します。  

1.  ドロワーで **、3D ビュー ツールを選択** します。  
1.  [コンポジット **レイヤー] ウィンドウを開** きます。  
1.  アプリのすべての塗り付けレイヤーが表示されます。  独自の Web アプリでこの機能を試してみてください。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### [スタイル] ウィンドウで新しいフォント エディター ツールを有効にする  

これで、新しいビジュアル フォント エディター [を使用してフォント][DevtoolsInspectStylesEditFonts] を編集できます。  フォントとフォントの特性を定義するために使用します。  ビジュアル フォント **エディターを使用すると、** 次の操作を実行できます。  

*   さまざまなフォント プロパティの単位を切り替える  
*   さまざまなフォント プロパティのキーワードを切り替える  
*   単位を変換する  
*   正確な CSS コードを生成する  
    
実験を有効にした後、DevTools を再起動してください。  新しいビジュアル フォント エディター **を使用するには、次**の手順を実行します。  

1.  要素ツール **を開** きます。  
1.  [スタイル] **ウィンドウを開** きます。  
1.  [フォント エディター **] アイコンを選択** します。  
    
新しいビジュアル フォント エディター**** の詳細については[、DevTools][DevtoolsInspectStylesEditFonts]の [スタイル] ウィンドウの [CSS フォントのスタイルと設定の編集] に移動します。  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="[Visual Font Editor] ウィンドウが強調表示されている" lightbox="../media/font-editor-open.msft.png":::
   [Visual **Font Editor] ウィンドウ** が強調表示されている  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### 新しい CSS Flexbox デバッグ機能を有効にする  

この試験的な機能は、CSS Flexbox レイアウトのデバッグに役立つ多くの新しい視覚エフェクトを提供します。  最新の試験的な機能をプレビューするには、 [この実験を有効](#turn-on-experimental-features) にし、DevTools を再読み込みします。  

#### Inspect ツールを使用して Flexbox レイアウトに永続的なオーバーレイを表示する  

Inspect **ツール** を使用すると、Web サイト内の CSS Flexbox レイアウトをマウスでポイントすることで、簡単に識別して視覚化できます。  DevTools **の左上隅** にある Inspect ![ \( Inspect ](../media/inspect-icon.msft.png) \) アイコンを選択します。  次に、Web サイトのデバッグ中に、flex コンテナーにカーソルを合わせると、flex コンテナーの周囲にアウトラインが表示されます。  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="Inspect ツールを使用して Flexbox コンテナーを表示する" lightbox="../media/flexbox-hover.msft.png":::
   Inspect ツールを使用して Flexbox コンテナー **を表示** する  
:::image-end:::  

#### Flexbox レイアウトに永続的なオーバーレイを表示する  

Microsoft Edge バージョン 89 以降では、実験的な CSS Flexbox 機能を使用して、Flexbox レイアウトで永続的なオーバーレイを有効にすることもできます。  永続的なオーバーレイには、次の利点があります。  

*   スクロール、マウスの移動、DevTools のその他の機能の使用を行う間、永続的なオーバーレイは Web ページに表示されたままです。
*   複数の永続的なオーバーレイを同時に使用して、一度に複数の Flexbox レイアウトを確認できます。  
*   永続的なオーバーレイは、色構成オプションを提供します。  
    
Flexbox レイアウトで固定オーバーレイを切り替えるには、次のいずれかのアクションを使用します。  

*   Elements ツール **の DOM ツリー** に表示される Flexbox コンテナーの横にある Flexbox 楕円アイコンを **選択** します。  
*   **要素**ツール**にある新しいレイアウト**パネルを開き、強調表示する各 Flexbox コンテナーの横にあるチェック ボックスをオンにします。  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools の Flex アイコンとレイアウト パネル" lightbox="../media/flexbox-overlay.msft.png":::
   DevTools **の Flex** アイコンとレイアウト パネル  
:::image-end:::  

#### 永続的なオーバーレイを構成する  

CSS グリッドまたは Flexbox レイアウトの固定オーバーレイのオプションを構成するには、[レイアウト] ウィンドウ **を使用** します。  [ **レイアウト** ] ウィンドウは、要素 **ツールの** [スタイル] ウィンドウと **[計算** ] ウィンドウ **の横** に配置されます。  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="レイアウト パネル" lightbox="../media/flexbox-layout.msft.png":::
   レイアウト パネル  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### [+] ボタン タブ メニューを有効にして、その他のツールを開く  

新しい [その他のツール] **\(** \) アイコンを使用して、その他のツール `+` を開く場合があります。  [有効 **+** ボタン] タブ メニューをオンにして、他のツールの実験を開き、DevTools を再読み込みした後、DevTools の上部にあるタブ グループの右側にプラス記号 \( \) が表示されます。 `+`  タブ バーに追加できる他のツールの一覧を表示するには、新しい **[** その他のツール] \( `+` \) アイコンを選択します。  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="上部のウィンドウの [その他のツール]" lightbox="../media/experiments-more-tools-button.msft.png":::
   **上部のウィンドウ** の [その他のツール]
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### ウェルカム ツールを有効にする

この実験では、新機能 **ツールが新しいウェルカム** ツールに **置き換** わるものになります。  次のコンテンツの更新されたデザインが表示されます。  

*   開発者向けドキュメントへのリンク  
*   最新機能  
*   リリース ノート  
*   Microsoft Edge DevTools チームに連絡するオプション  
    
Microsoft Edge **を** 更新すると、ウェルカム ツールが自動的に開きます。  更新ごとにウェルカム ツールが**** 表示されるのを防ぐには、ウェルカム ツール**** タイトルの更新後に [開く] タブの横にあるチェック ボックス**を**オフにします。  

元の新機能ツール**が**必要な場合は、[[設定][DevtoolsCustomizeIndexSettings]の実験] に移動し、[ようこそ] タブの横にある  >  **** チェック**ボックスをオフにします**。  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="ウェルカム ツール" lightbox="../media/experiments-welcome.msft.png":::
   **ウェルカム** ツール  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## 以前の試験的な機能  

*   Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能になっていて、既定でオンになっています。  
*   [Microsoft][DevtoolsMoveTabs] Edge バージョン 85 以降では、パネル間でタブを移動するサポートを有効にし、既定で有効になっています。  
*   [Microsoft][DevtoolsCustomKeyboardShortcuts] Edge バージョン 86 以降で、キーボード ショートカットのカスタマイズが使用可能で、既定で有効になっています。  
*   [エミュレーション: Microsoft][DevtoolsDeviceModeDualScreenAndFoldables] Edge バージョン 89 以降で、デュアル スクリーン モードをサポートし、既定で有効になっています。  
*   [Microsoft][DevtoolsCssGrid] Edge バージョン 89 以降で、新しい CSS グリッド デバッグ機能が使用可能になっていて、既定で有効になっている機能を有効にします。  
    
## 試験的な機能に関するフィードバックの提供  

Microsoft Edge DevTools 実験、または DevTools に関連するその他の実験に関するフィードバックを提供する。  

*   DevTools の **[フィードバック** の送信] アイコンを使用してフィードバックを送信する  
*   次の時点 [でツイート@EdgeDevTools][TwitterEdgedevtools]  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の **[フィードバックの送信]** アイコン  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "Microsoft Edge DevTools アプリケーションで CSS グリッドを|Microsoft Docs"  
[DevtoolsMoveTabs]: ../customize/index.md "Microsoft Edge DevTools のカスタマイズ|Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "DevTools プロジェクトの [スタイル] ウィンドウで CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevtoolsIssues]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Emulator エミュレーター を取得|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Emulator エミュレーター を使|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアント|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Surface の |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "Microsoft Edge DevTools アプリケーションでデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレート|Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
