---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: ae2058ad2beb2d8d3b19061e0935b92173392f23
ms.sourcegitcommit: c24884cc154d6c4809e05ae37d170cb674c408b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091532"
---
# 試験的機能  

Microsoft Edge DevTools は、開発中の実験的な機能にアクセスできるようにします。  各機能がリリースされる前に、テストして、[フィードバックを提供](#providing-feedback-on-experimental-features) することができます。  

Microsoft Edge のすべてのチャネルで実験的機能を利用できますが、Microsoft Edge カナリアチャネルを使用して、最新の実験的な機能を入手できます。  

## 実験的な機能を有効にする  

Microsoft Edge での試験的な機能 (またはオフ) を有効にするには、次の手順を使用します。  

1.  [DevTools を開き][DevtoolsOpen]ます。  
     *   [ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を選びます。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [ [設定][DevToolsCustomizeSettings] ] ウィンドウを開きます。  
    *   を選択し `Shift` + `?` ます。  詳細については、「 [Microsoft Edge DevTools のキーボードショートカット][DevToolsShortcuts]」を参照してください。  
1.  [ **設定** ] ウィンドウの左側で、[ **実験** ] セクションを選択します。  
    
    :::image type="complex" source="./media/experiments-devtools.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-devtools.msft.png":::
       DevTools の設定での実験の一覧  
    :::image-end:::  
    
1.  [ **実験** ] ページで、利用可能なすべての実験的な機能の一覧をスクロールし、テストする各機能の横にあるチェックボックスをオンにします。  
1.  Microsoft Edge DevTools を閉じてからもう一度開きます。  

> [!NOTE]
> 実験的な機能は常に更新され、パフォーマンスの問題が発生する可能性があります。  実験的な機能を無効にするには、[ **実験** ] ページを開き、無効にする実験的機能のチェックボックスをオフにします。  

## 強調表示された実験的な機能  

以下のセクションでは、Microsoft Edge で利用できる新しい実験的な機能について説明します。  

| 実験的機能 | Microsoft Edge バージョン |  
|:--- |:--- |  
| [エミュレーション: デュアルスクリーンモードのサポート](#emulation-support-dual-screen-mode) | 84以降 |  
| [新しい CSS グリッドのデバッグ機能を有効にする](#enable-new-css-grid-debugging-features) | 85以降 |  
| [パネル間でタブを移動できるようにサポートを有効にする](#enable-support-to-move-tabs-between-panels) | 85以降 |  
| [Web ヒントを有効にする](#enable-webhint) | 85以降 |  
| [ネットワーク本体を有効にする](#enable-network-console) | 85以降 |  
| [ソースオーダービューアー](#source-order-viewer) | 86以降 |  

### エミュレーション: デュアルスクリーンモードのサポート  

Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。  

*   [Surface Duo][SurfaceDevicesDuo]  
*   [Samsung Galaxy Fold][SamsungMobileGalaxyFold]  

デバイスをエミュレートし、次の後処理を切り替えます。  

*   シングルスクリーンまたは折り目  
*   デュアルスクリーンまたは折る  
    
[実験的な Web Platform api を有効](#enable-experimental-apis) にして、 [CSS メディアの画面スパン機能][DualScreenDocsCssMedia] と [JavaScript getwindowsegments API][DualScreenDocsJSAPI] を使用して、デュアルスクリーンデバイスと折りたたみ式デバイス用の web サイト (またはアプリ) を強化します。  

:::image type="complex" source="./media/experiments-surface-duo-emulation.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-surface-duo-emulation.msft.png":::  
   Microsoft Edge で Surface Duo をエミュレートする  
:::image-end:::  

#### 実験的な Api を有効にする  

[CSS メディアの画面スパン機能][DualScreenDocsCssMedia]と[JavaScript GETWINDOWSEGMENTS API][DualScreenDocsJSAPI]を使用するには、 `Experimental Web Platform features` Microsoft Edge でフラグをオンにします。  次の手順を実行します。  

1.  に移動 `edge://flags` します。  
1.  [ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。  
1.  [Microsoft Edge を再起動]。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   実験的な Web Platform 機能のフラグを有効にする  
:::image-end:::  

> [!NOTE]
> [CSS メディアクエリ][DualScreenDocsCssMedia]または[JavaScript WINDOWS セグメント列挙 API][DualScreenDocsJSAPI]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。  
> 
> [デスクトップ][MicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっていて、 [android microsoft edge アプリ][GooglePlayMicrosoftEdge]で無効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。  [デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。  

#### 折りたたみ式とデュアルスクリーンデバイスでのテスト  

Microsoft Edge のデュアル画面の姿勢で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、ユーザーの web サイトまたはアプリ上で、継ぎ目 (2 つの画面間のスペース) が描画されます。  

エミュレートされたディスプレイは、web サイト \ (またはアプリ \) と[Surface Duo][SurfaceDevicesDuo]の[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]での表示方法に一致します。  お客様の web サイト \ (またはアプリ \) を更新して、継ぎ目に合わせて表示を改善しなければならない場合があります。  Web サイトの外観を seam に適合させる方法の詳細については、Surface Duo のドキュメントで [seam を操作する方法][DualScreenIntroductionHowWorkSeam] を参照してください。  

[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。  **Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。 この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。  これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス  
:::image-end:::  

**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。  フラグがオンになっている場合は、アイコンが強調表示されます。  フラグがオフになっている場合、アイコンは強調表示されません。  フラグをオン (またはオフ) にするには、フラグに移動 `edge://flags` して切り替えます。  

<!-- Commenting out until the icon issue is fixed in Edge Canary
The **Experimental Web Platform features** \(![ExperimentalApis][ImageExperimentalApisIcon]\) icon displays the state of the **Experimental Web Platform features** flag.  If the flag is turned on, the icon is highlighted.  If the flag is turned off, the icon is not highlighted.  To turn on \(or off\) the flag, either choose the icon or navigate to `edge://flags` and toggle the flag.   -->  

ここでは、デュアルスクリーンデバイス向けの web サイト (またはアプリ) を強化するために役立つその他のリソースを紹介します。
*   デュアルスクリーンデバイスでの web 開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。  
*   [Surface Duo エミュレーター][DualScreenAndroidUseEmulator]をインストールします。  これは、Microsoft Edge のエミュレーターとは異なり、Android を実行している Surface Duo のエミュレートと [Android Studio][AndroidDeveloperStudio]との統合です。  詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。  

> [!NOTE]
> 次に、現在の既知の問題の一覧を示します。  
> 
> *   [Microsoft リモートデスクトップクライアント][RemoteDesktopClientDocs]を使ってリモート PC に接続し、 [Surface Duo][SurfaceDevicesDuo]または[Samsung Galaxy の折りたたみ][SamsungMobileGalaxyFold]をエミュレートすると、ポインターがシェイクまたは途切れる可能性があります。  この問題が発生した場合は、 [フィードバックを送信](#providing-feedback-on-experimental-features)してください。  

### 新しい CSS グリッドのデバッグ機能を有効にする  

この実験的な機能には、CSS グリッドレイアウトのデバッグに役立つ多くの新しい視覚エフェクトが用意されています。  最新の実験的な機能をプレビューするには、 [この実験を有効に](#turn-on-experimental-features) して、devtools を再読み込みします。  この実験は、Edge 87 以降では既定でオンになっています。  

#### 検査ツールを使用したホバーグリッドのオーバーレイの表示  

**検査**ツールを使うと、マウスをポイントして web サイトの CSS グリッドのレイアウトを簡単に識別して視覚化することができます。  **Inspect** ![ ](./media/inspect-icon.msft.png) Devtools の左上隅にある検査 (検査 \) アイコンを選択します。  次に、デバッグしている web サイトの Grid 要素にマウスポインターを置きます。  グリッドの周りに枠線が表示され、[網かけ] ではグリッドのギャップの位置が示されます (存在する場合)。  

:::image type="complex" source="./media/grid-inspect.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-inspect.msft.png":::
   検査ツールでグリッドを表示する  
:::image-end:::  

#### 永続的なグリッドのオーバーレイの表示  

Edge 86 以降では、実験的な CSS grid 機能で、持続的なグリッドのオーバーレイを有効にするオプションも提供されています。  永続的なオーバーレイにはいくつかの利点があります。  

*   永続的なオーバーレイはスクロールしてもページに表示されたままになり、マウスを動かすと、DevTools のその他の機能を使うことができます。  
*   同時に複数の持続的なオーバーレイを有効にすることができます。複数のグリッドレイアウトを一度に確認することができます。  
*   永続的なオーバーレイには、グリッド領域名の非表示または表示、グリッドのギャップ、トラックサイズなど、さまざまな構成オプションが用意されています。  

永続的なグリッドのオーバーレイを切り替える2つの方法  

*   **要素**ツールの DOM ツリーに表示されている grid 要素の隣にある**grid** lozenge を選びます。  
    
    :::image type="complex" source="./media/grid-adorner.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-adorner.msft.png":::
       要素ツールの Grid lozenge  
    :::image-end:::  
    
*   [要素] ツールにある新しい **レイアウト** パネルを開き、強調表示する各グリッド要素の横にあるチェックボックスをオンにします。  
    
    :::image type="complex" source="./media/grid-layout-zoom.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/grid-layout-zoom.msft.png":::
       レイアウトパネル  
    :::image-end:::  
    
#### 永続的なオーバーレイの構成  

新しい **レイアウト** パネルは、 **要素** ツールの Edge 86 以降の [ **スタイル** ] タブと [ **計算** ] タブに配置されていますが、持続的なオーバーレイの構成オプションが含まれています。  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-grid.msft.png":::
   CSS グリッドのデバッグ機能  
:::image-end:::  

### パネル間でタブを移動できるようにサポートを有効にする  

通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。  **3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。  実験を選択した後、上下のパネル間でツールを移動することができます。  ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。   この実験では、DevTools レイアウトをカスタマイズできます。  **ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-move-panels.msft.png":::
   パネル間でタブを移動する  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Web ヒントを有効にする  

[webhint][WebhintMain] は、web サイトやローカル web ページにリアルタイムでフィードバックを提供するオープンソースツールです。  [Webhint][WebhintMain]によって提供されるフィードバックの種類。  

*   アクセシビリティ  
*   ブラウザー間の互換性  
*   セキュリティ  
*   処理  
*   PWA  
*   その他の一般的な web 開発の問題  

[Webhint][WebhintMain]の実験では、[[問題][DevtoolsIssues]] パネルに webhint のフィードバックが表示されます。  問題を選択すると、ソリューションのドキュメントと web サイト上の影響を受けるリソースの一覧が表示されます。  リソースリンクを選んで、DevTools で関連する **ネットワーク**、 **ソース**、または **要素** のウィンドウを開きます。  

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-webhint.msft.png":::
   [ **問題** ] パネルでの webhint のフィードバック  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ネットワーク本体を有効にする  

**ネットワーク本体** は、HTTP 経由で代理ネットワーク要求を行う実験の作業タイトルです。  **ネットワークコンソール**の実験を使用して、web API 要求を送信することができます。  

実験を有効にした後、DevTools を再起動してください。  **ネットワークコンソール**を使用するには、次の手順を実行します。  

1.  [ **ネットワーク** ] ウィンドウを開きます。  
1.  変更して再送信するネットワーク要求を見つけます。  
1.  コンテキストメニューを開き (\ 右クリック \)、[ **編集と再生**] を選びます。  
1.  **ネットワークコンソール**が開いたら、ネットワーク要求情報を編集します。  
1.  [ **送信**] を選びます。  

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/network-network-console.msft.png":::
   **Console**ドローワの**ネットワーク本体**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ソースオーダービューアー  

**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。  オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。  **ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。  

実験を有効にした後、DevTools を再起動してください。  **ソースオーダービューアー**を使用するには、次の手順を使用します。  

1.  [ **要素** ] ウィンドウを開く。  
1.  [引き出し] \ (下) パネルで [ **アクセシビリティ** ] ウィンドウを開きます。  
1.  [ **ソース注文のビューアー** ] セクションで、[ **ソースの順序を表示** ] チェックボックスをオンにします。  
1.  任意の HTML 要素を強調表示して、ページソースの順序でオーバーレイを表示します。  

:::image type="complex" source="./media/experiments-source-order-viewer.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/experiments-source-order-viewer.msft.png":::
   [**アクセシビリティ**] ウィンドウの**ソースオーダービューアー**  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

## 以前の実験的な機能  

*   Microsoft Edge バージョン83以降では、 [3D ビュー][Devtools3dViewIndex]を使用できるようになり、既定でオンになっています。  
*   Microsoft Edge バージョン86以降では、[ショートカット][DevtoolsCustomKeyboardShortcuts]キーをカスタマイズできるようになりました。  

## 実験的な機能についてフィードバックを提供する  

Microsoft Edge DevTools のテスト、または DevTools に関連するその他の機能についてのフィードバックを提供します。  

*   DevTools のフィードバックの **送信** アイコンを使ってフィードバックを送信する  
*   [@EdgeDevTools][TwitterEdgedevtools]ツイート  

:::image type="complex" source="./media/bing-devtools-send-feedback.msft.png" alt-text="DevTools の設定での実験の一覧" lightbox="./media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  
-->  

<!-- image links -->  

[ImageRotateIcon]: ./media/rotate-dark-icon.msft.png  
[ImageSpanIcon]: ./media/span-dark-icon.msft.png  
[ImageExperimentalApisIcon]: ./media/experimental-apis-dark-icon.msft.png  

<!-- links -->  

[Devtools3dViewIndex]: ./3d-view/index.md "3D ビュー |Microsoft ドキュメント"  
[DevToolsCustomizeSettings]: ./customize/index.md#settings "設定-Microsoft Edge DevTools のカスタマイズ |Microsoft ドキュメント"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ./device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools でデバイスモードを使ってモバイルデバイスをシミュレートする |Microsoft Edge"  
[DevtoolsIssues]: ./issues/index.md "Microsoft Edge DevTools の問題を見つけて解決するツール |Microsoft ドキュメント"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  
[DevtoolsOpen]: ./open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  
[DevtoolsCustomKeyboardShortcuts]: ./customize/shortcuts.md "Microsoft Edge DevTools でキーボードショートカットをカスタマイズする |Microsoft ドキュメント"

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン web エクスペリエンス |Microsoft ドキュメント"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの入手 |Microsoft ドキュメント"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Duo エミュレーターを使用する |Microsoft ドキュメント"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "CSS メディア画面のスパン機能で、デュアルスクリーン検出Microsoft ドキュメント"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーンデバイス用の getWindowSegments JavaScript API |Microsoft ドキュメント"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモートデスクトップクライアント |Microsoft ドキュメント"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折りたたみ |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント"  
