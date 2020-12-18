---
description: Microsoft Edge DevTools の最新の実験的機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, 実験
ms.openlocfilehash: fbdeeb08599285a9cfa6edd467282cfbabbadd74
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234705"
---
# 試験的機能  

Microsoft Edge DevTools は、まだ開発中の試験的な機能にアクセスできます。  各機能がリリースされる [前に、テストして](#providing-feedback-on-experimental-features) フィードバックを提供することができます。  

試験的な機能は Microsoft Edge のすべてのチャネルで利用できます。Microsoft Edge Canary チャネルを使用すると、最新の試験的な機能を利用できます。  

## 試験的な機能を有効にする  

Microsoft Edge で実験的な機能 \(またはオフ\) を有効にする場合は、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
    *   `Control` + `Shift` + `I` \(Windows,Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  
1.  [設定] [ウィンドウを開][DevToolsCustomizeSettings] きます。  
    *   選択します `Shift` + `?` 。  詳細については [、Microsoft Edge DevTools のキーボード ショートカットに移動します][DevToolsShortcuts]。  
1.  [設定] ウィンドウの左側 **で** 、[実験] **セクションを選択** します。  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text="DevTools の設定の実験の一覧" lightbox="../media/experiments-devtools.msft.png":::
       DevTools の設定の実験の **一覧**  
    :::image-end:::  
    
1.  [ **実験] ページで** 、利用可能なすべての試験的な機能の一覧をスクロールし、テストする各機能の横にあるチェック ボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じてから再度開きます。  
    
> [!NOTE]
> 試験的な機能は常に更新され、パフォーマンスの問題を引き起こす可能性があります。  試験的な機能をオフにする場合は、[ **実験** ] ページを開き、無効にする試験的な機能のチェック ボックスをオフにします。  

## 強調表示された実験的な機能  

次のセクションでは、Microsoft Edge で使用可能な新しい試験的な機能について説明します。  

| 試験的機能 | Microsoft Edge のバージョン |  
|:--- |:--- |  
| [エミュレーション: デュアル スクリーン モードのサポート](#emulation-support-dual-screen-mode) | 84 以降 |  
| [新しい CSS グリッド デバッグ機能を有効にする](#enable-new-css-grid-debugging-features) | 85 以降 |  
| [パネル間でタブを移動するサポートを有効にする](#enable-support-to-move-tabs-between-panels) | 85 以降 |  
| [webhint を有効にする](#enable-webhint) | 85 以降 |  
| [ネットワーク コンソールを有効にする](#enable-network-console) | 85 以降 |  
| [ソース オーダー ビューアー](#source-order-viewer) | 86 以降 |  
| [キーボード ショートカット エディターを有効にする](#enable-keyboard-shortcut-editor) | 87 以降 |  
| [3D ビューで複合レイヤーを有効にする](#turn-on-composited-layers-in-3d-view) | 87 以降 |  

### エミュレーション: デュアル スクリーン モードのサポート  

Microsoft Edge で 2 つの新しいデュアルスクリーン デバイスと折りたたみ可能なデバイスを適用する追加機能を提供します。  

*   [Surface の一方][SurfaceDevicesDuo]  
*   [Samsung Galaxy Fold][SamsungMobileGalaxyFold]  
    
デバイスをエミュレートし、次の状態を切り替えます。  

*   単一画面または折りたたまれた状態  
*   デュアルスクリーンまたは展開された体勢  
    
試験[的な Web プラットフォーム API](#enable-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンと折りたたみ可能なデバイス向けの Web サイト \(または app\) を強化します。  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface をエミュレートする" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   Microsoft Edge で Surface をエミュレートする  
:::image-end:::  

#### 試験的な API を有効にする  

[CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、Microsoft Edge でフラグ `Experimental Web Platform features` をオンにします。  次の手順を実行します。  

1.  に移動します `edge://flags` 。  
1.  [検索フラグ **] ボックスに**、「試験的な Web プラットフォーム機能」フラグを入力し、[無効] を [有効] `Experimental Web Platform features` に**変更します**。 **** ****  
1.  [Microsoft Edge を再起動]。  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[試験的な Web プラットフォーム機能] フラグを有効にする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   [試験的な Web プラットフォーム機能] フラグを有効にする  
:::image-end:::  

> [!NOTE]
> [CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows セグメント][DualScreenDocsJSAPI]列挙 API を使用して、Surface Surface の Web サイトまたはアプリを強化する場合は[、Surface Surface][SurfaceDevicesDuo] [デバイス][SurfaceDevicesDuo]の Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリで試験的な**Web**プラットフォーム機能フラグも有効にする必要があります。  
> 
> デスクトップの[Microsoft][MicrosoftEdge] [Edge][SurfaceDevicesDuo]で試験**的な Web**プラットフォーム機能のフラグが有効になっている場合[、Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリで無効になっている場合、デスクトップの Surface Emulator の Web サイトまたはアプリの動作が、Microsoft Edge のデスクトップの Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリと一致しません。  フラグが Android とデスクトップの Microsoft Edge で一致し、デスクトップの Microsoft Edge で Surface Emulator エミュレーターが正常に使用 [されたことを確認します][MicrosoftEdge]。  

#### 折りたたみ可能なデュアルスクリーン デバイスでのテスト  

Microsoft Edge でデュアルスクリーンの位置で [Surface Over][SurfaceDevicesDuo] をエミュレートすると、Web サイトまたはアプリの上に、"2 つの画面の間のスペース\" という円が描画されます。  

エミュレートされた表示は、Surface Surface で実行されている [Microsoft Edge Android][GooglePlayMicrosoftEdge] アプリで Web サイト \(または app\) がレンダリングされる方法と [一致します][SurfaceDevicesDuo]。  Web サイト \(または app\) を更新して、より良い画面を表示する必要がある場合があります。  For more information about adapting your website \(or app\) to the navigate to [How to work with the windows.][DualScreenIntroductionHowWorkSeam]  

デバイス [ツール バーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の位置と向きで Web サイトまたはアプリをテストするのに役立つ追加機能があります。  ビューポート **を横向** きに回転するには、回転 ![ ][ImageRotateIcon] \( Rotate \) を選択します。 機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた状態とデュアルスクリーンまたは展開された状態を ![ 切り ][ImageSpanIcon] 替える。  これらの機能を組み合わせて、4 つの考えられるすべての位置と向きで Web サイトまたはアプリをテストできます。  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス  
:::image-end:::  

Experimental **Web プラットフォーム機能** \( ExperimentalApis \) アイコンには、Experimental Web Platform 機能 ![ フラグの ][ImageExperimentalApisIcon] **状態が表示** されます。  フラグがオンの場合、アイコンが強調表示されます。  フラグがオフの場合、アイコンは強調表示されません。  フラグを \(または off\) に切り替えるには、フラグに移動 `edge://flags` して切り替えます。  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

ここでは、デュアルスクリーン デバイス用に Web サイト \(または app\) を強化するのに役立つ可能性があるその他のリソースを示します。  

*   デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web [エクスペリエンス」に移動してください][DualScreenWebIndex]。  
*   Surface [Emulator エミュレーターをインストールします][DualScreenAndroidUseEmulator]。  Microsoft Edge のエミュレーターとは異なるので、Android を実行している Surface Surface をエミュレートし [、Android Studio と統合します][AndroidDeveloperStudio]。  詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。  
    
> [!NOTE]
> 現在の既知の問題の一覧を次に示します。  
> 
> *   [Microsoft][RemoteDesktopClientDocs]リモート デスクトップ クライアントを使用してリモート PC に接続し[、Surface Galaxy][SurfaceDevicesDuo]または Samsung Galaxy [Fold][SamsungMobileGalaxyFold]をエミュレートする場合、ポインターが動く可能性があります。  If you run into the issue, [send feedback](#providing-feedback-on-experimental-features).  

### 新しい CSS グリッド デバッグ機能を有効にする  

この試験的な機能は、CSS グリッド レイアウトのデバッグに役立つ新しい視覚エフェクトを多数提供します。  最新の試験的な機能をプレビューするには、 [この実験を有効に](#turn-on-experimental-features) し、DevTools を再読み込みします。  この実験は、Microsoft Edge バージョン 87 以降で既定で有効になっています。  

#### 検査ツールを使用した、ホバー時のグリッド オーバーレイの表示  

検査 **ツール** を使用すると、Web サイト内の CSS グリッド レイアウトをマウスでポイントすることで、簡単に識別して視覚化できます。  DevTools **の左上隅** にある Inspect ![ \( Inspect ][ImageInspectIcon] \) アイコンを選択します。  次に、デバッグする Web サイトの Grid 要素をポイントします。  枠線はグリッドの周囲に表示され、網かけはグリッドのギャップがある場合の位置を示します。  

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

[webhint は][WebhintMain] 、Web サイトとローカル Web ページにリアルタイムのフィードバックを提供するオープン ソース ツールです。  Webhint によって提供される [フィードバックの種類][WebhintMain]。  

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

**ソース オーダー ビューアーは** 、ページ ソース内の要素の順序を表示する実験です。  スクリーン リーダーとキーボード のユーザーを混乱させるソースの順序と、画面の表示順序が異なる場合があります。  ソース オーダー **ビューアーの実験を** 使用して、画面の表示順序とソースの順序の違いを確認します。  

実験を有効にした後、DevTools を再起動してください。  ソース オーダー **ビューアーを使用するには、** 次の手順を実行します。  

1.  [要素] **ウィンドウを開** きます。  
1.  ドロワー **\(** 下部\) パネルの [アクセシビリティ] ウィンドウを開きます。  
1.  [ソース オーダー **ビューアー] セクションで** 、[ソース注文の **表示] チェック ボックスをオン** にします。  
1.  HTML 要素を強調表示して、ページ ソース内の順序に合ったオーバーレイを表示します。  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text="[アクセシビリティ] ウィンドウのソース 注文ビューアー" lightbox="../media/experiments-source-order-viewer.msft.png":::
   **[アクセシビリティ] ウィンドウ** のソース **注文** ビューアー  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### キーボード ショートカット エディターを有効にする

キーボード ショートカット **エディターの** 有効化実験を有効にすると、DevTools 内の任意のアクションのキーボード ショートカットをカスタマイズできます。  特定の操作のキーボード ショートカットをカスタマイズするには、次の手順を実行します。  

1.  [DevTools を開きます][DevtoolsOpenMain]。  
1.  [設定 [] を開きます][DevToolsCustomizeSettings]。
    *   選択します `Shift` + `?` 。  
1.  [ショートカット] **ページに移動** します。  
1.  カスタマイズするアクションを選択します。  
1.  [ **編集** \( ![ EditKeyboardShortcut \) ] ][ImageEditKeyboardShortcutIcon] アイコンを選択します。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="[設定] の [ショートカット] ページからカスタマイズするアクションを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       [設定] の [ショートカット] ページ **からカスタマイズ** するアクションを選択 [する][DevToolsCustomizeSettings]
    :::image-end:::  
    
1.  キーボードで、アクションにバインドするキーを選択します。
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="アクションに割り当てるキーを選択する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       アクションに割り当てるキーを選択する
    :::image-end:::  
    
1.  新しいキーボード ショートカットを保存するには、チェックマーク \(![CheckmarkKeyboardShortcut][ImageCheckmarkKeyboardShortcutIcon]\) アイコン
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       チェックマーク アイコンを選択して新しいキーボード ショートカットを保存する
    :::image-end:::  
    
1.  DevTools でアクションをトリガーするには、新しいキーボード ショートカットを選択します。  
    
[ショートカット **] ページ** で、ユーザー設定のキーボード ショートカット **\(** CustomKeyboardShortcut \) アイコンに、カスタマイズしたキーボード ショートカット ![ ][ImageCustomKeyboardShortcutIcon] が表示されます。  すべてのショートカットをリセットするには、[既定のショートカット **を復元する] を選択します**。  

When you are editing the keyboard shortcuts for an action, to discard your changes, choose the X \( ![ XKeyboardShortcut ][ImageXKeyboardShortcutIcon] \) icon.  特定のアクションのショートカットを削除するには、ショートカットの **削除** \( ![ DeleteKeyboardShortcut ][ImageDeleteKeyboardShortcutIcon] \) アイコンを選択します。  1 つのアクションに複数のショートカットを追加するには、[ショートカットの **追加] を選択します**。

> [!NOTE]
> キーボード ショートカットが別のアクションに現在割り当てられている場合は、新しい操作のためにキーボード ショートカットを保存できない。  最初に、前の操作のキーボード ショートカットを削除してから、新しいアクションに追加する必要があります。  

<!--Available in Microsoft Edge version 87 and later.  -->

### 3D ビューで複合レイヤーを有効にする

レイヤーを z インデックスとドキュメント オブジェクト モデル \(DOM\) と共に視覚化できます。  この機能は、コンテキストを頻繁に切り替えることなくデバッグするのに役立ちます。  コンテキストの切り替えの削減が大きな問題と見なされました。  作成するコードが Web アプリに与える影響は必ずしも明確ではありません。  視覚的なデバッグを総合的に行う目的で、3D ビューレイヤーと複合レイヤーが結合されました。  実験を有効にした後、DevTools を再起動してください。  複合レイヤー **を使用するには、次**の手順を実行します。  

1.  ドロワーで **、3D ビュー ツールを選択** します。  
1.  [コンポジット **レイヤー] ウィンドウを開** きます。  
1.  アプリのすべての塗り付けレイヤーが表示されます。  独自の Web アプリでこの機能を試してみてください。  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="[コンポジット レイヤー] ウィンドウ" lightbox="../media/experiments-layers.msft.png":::
   **[コンポジット レイヤー]** ウィンドウ  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

## 以前の試験的な機能  

*   Microsoft Edge バージョン 83 以降では[、3D][Devtools3dViewIndex]ビューが使用可能になっていて、既定でオンになっています。  
*   [Microsoft][DevtoolsCustomKeyboardShortcuts] Edge バージョン 86 以降で、キーボード ショートカットのカスタマイズが使用可能で、既定で有効になっています。  

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

<!-- image links -->  

[ImageCheckmarkKeyboardShortcutIcon]: ../media/checkmark-keyboard-shortcut-icon.msft.png  
[ImageCustomKeyboardShortcutIcon]: ../media/custom-keyboard-shortcut-icon.msft.png  
[ImageDeleteKeyboardShortcutIcon]: ../media/delete-keyboard-shortcut-icon.msft.png  
[ImageEditKeyboardShortcutIcon]: ../media/edit-keyboard-shortcut-icon.msft.png  
[ImageExperimentalApisIcon]: ../media/experimental-apis-dark-icon.msft.png  
[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageRotateIcon]: ../media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ../media/span-dark-icon.msft.png  
[ImageXKeyboardShortcutIcon]: ../media/discard-changes-keyboard-shortcut-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "3D ビュー | Microsoft Docs"  
[DevToolsCustomizeSettings]: ../customize/index.md#settings "設定 - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools のデバイス モードでモバイル デバイスをシミュレートする |Microsoft Edge"  
[DevtoolsIssues]: ../issues/index.md "Microsoft Edge DevTools の問題ツールに関する問題を見つけて修正する | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools のキーボード ショートカット |Microsoft Docs"  
[DevtoolsCustomKeyboardShortcuts]: ../customize/shortcuts.md "Microsoft Edge DevTools でキーボード ショートカットをカスタマイズする | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Emulator エミュレーターを取得する |Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Emulator エミュレーターを使用する |Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアント |Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface の一方 |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
