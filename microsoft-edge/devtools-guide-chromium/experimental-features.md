---
description: Microsoft Edge DevTools の最新の実験的な機能
title: 試験的機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、実験
ms.openlocfilehash: c78e9aa5e0b4d808dd67d607a954b185ddcf54e7
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004031"
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
| [カスタムキーボードショートカットの [設定] タブを有効にする](#enable-custom-keyboard-shortcuts-settings-tab) | 84以降 |
| [エミュレーション: デュアルスクリーンモードのサポート](#emulation-support-dual-screen-mode) | 84以降 |  
| [新しい CSS グリッドのデバッグ機能を有効にする](#enable-new-css-grid-debugging-features) | 85以降 |  
| [パネル間でタブを移動できるようにサポートを有効にする](#enable-support-to-move-tabs-between-panels) | 85以降 |  
| [Web ヒントを有効にする](#enable-webhint) | 85以降 |  
| [ネットワーク本体を有効にする](#enable-network-console) | 85以降 |  
| [ソースオーダービューアーを有効にする](#enable-source-order-viewer) | 86以降 |  

### カスタムキーボードショートカットの [設定] タブを有効にする  

Devtools の [[設定][DevToolsCustomizeSettings]] に新しい [**ショートカット**] ページが用意されており、開発ツールの[キーボードショートカット][DevToolsShortcuts]と[Microsoft Visual Studio のコード][VisualstudioCode]の対応を示しています。  

実験を有効にした後、[選択] を使用して、[ [Devtools][DevToolsCustomizeSettings] ] の設定をもう一度開き `Shift` + `?` ます。  [新しい **ショートカット** ] ページに移動します。  [**標準のショートカットキー**の選択] ドロップダウンで [ **Devtools (既定値)** ] を選び、[ **Visual Studio コード**] を選びます。  DevTools のキーボードショートカットは、Visual Studio コードで同等のアクションのショートカットと一致するようになりました。  

:::image type="complex" source="./media/experiments-keyboard-shortcut.msft.png" alt-text="DevTools for Visual Studio コードのキーボードショートカットを一致させる" lightbox="./media/experiments-keyboard-shortcut.msft.png":::
   DevTools for Visual Studio コードのキーボードショートカットを一致させる  
:::image-end:::  

たとえば、Windows では、 [Visual Studio コード][VisualstudioCodeShortcutsKeyboardWindows] でスクリプトを一時停止または実行し続けるためのキーボードショートカットは `F5` です。  **Devtools (既定)** の事前設定を使用すると、devtools の同じショートカットを使うことが `F8` できます。  **Visual Studio コード**の事前設定を使用すると、ショートカットも表示され `F5` ます。  

### エミュレーション: デュアルスクリーンモードのサポート  

Microsoft Edge で2つの新しいデュアル画面と折りたたみ式デバイスをエミュレートするための追加機能を提供します。  

*   [Surface Duo][SurfaceDevicesDuo]  
*   [Samsung Galaxy Fold][SamsungMobileGalaxyFold]  

デバイスをエミュレートし、次の後処理を切り替えます。  

*   シングルスクリーンまたは折り目  
*   デュアルスクリーンまたは折る  

[ [実験的な api を有効](#enable-experimental-apis) にする] を使って、デバイスの web サイトを拡張します (またはアプリ \)。  [CSS メディアクエリと JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]を使用することもできます。  

<!-- This image was taken in Chromium Canary since we don't yet have an Edge Canary that has Stan's changes -->  

:::image type="complex" source="./media/experiments-dual-screen-emulation.msft.png" alt-text="Microsoft Edge で Surface Duo をエミュレートする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::  
   Microsoft Edge で Surface Duo をエミュレートする  
:::image-end:::  

#### 実験的な Api を有効にする  

Microsoft Edge DevTools で [この実験を有効](#turn-on-experimental-features) にするには、次の手順を実行します。  

1.  に移動 `edge://flags` します。  
1.  [ **検索フラグ** ] ボックスに、「 `Experimental Web Platform features` 実験的な **Web Platform 機能** 」というフラグを選択して、[ **無効** ] を [ **有効**] に変更します。  
1.  [Microsoft Edge を再起動]。  

デュアルスクリーンおよび折りたたみ式デバイス向けの web サイトやアプリを改善するには、「 [CSS メディアクエリ」と「JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]」を参照してください。

Microsoft Edge DevTools で[この実験をオン](#turn-on-experimental-features)にします。  

1.  Microsoft Edge で新しいタブを開き、に移動し `edge://flags` ます。  
1.  **検索フラグ**のテキストボックスで、「 `Experimental Web Platform features` **実験的な Web プラットフォーム機能**」を選択して、[**無効**] を [**有効**] に変更します。  
1.  [Microsoft Edge を再起動]。  

デュアルスクリーンデバイスと折りたたみ式デバイス向けの web サイトを拡張する方法の詳細については、「 [CSS メディアクエリ」および「JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]」を参照してください。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="実験的な Web Platform 機能のフラグを有効にする" lightbox="./media/experiments-dual-screen-emulation.msft.png":::
   実験的な Web Platform 機能のフラグを有効にする  
:::image-end:::  

> [!NOTE]
> [CSS メディアクエリまたは JavaScript Windows セグメント列挙 API][GitHubMicrosoftedgeMsedgeexplainerFoldables]を使用して[surface duo][SurfaceDevicesDuo]の web サイトまたはアプリを強化する場合は、 [Surface Duo][SurfaceDevicesDuo]デバイス上の[Android Microsoft Edge アプリ][GooglePlayMicrosoftEdge]の試用版の**Web プラットフォーム機能**フラグも有効にする必要があります。
> 
> [Microsoft edge][MicrosoftEdge] [アプリの android][GooglePlayMicrosoftEdge]microsoft Edge で**実験的な Web Platform 機能**のフラグが有効になっている場合、デスクトップ microsoft edge の surface duo エミュレーターの web サイトまたはアプリの動作は[surface duo][SurfaceDevicesDuo]の[Android microsoft edge アプリ][GooglePlayMicrosoftEdge]と一致しません。  [デスクトップ Microsoft edge][MicrosoftEdge]で Surface Duo エミュレーターを正常に使用するために、Android とデスクトップの microsoft edge の間でフラグが一致していることを確認します。  

#### 折りたたみ式とデュアルスクリーンデバイスでのテスト  

Microsoft Edge のデュアル画面で [Surface Duo][SurfaceDevicesDuo] をエミュレートすると、この **継ぎ目** は、web サイトまたはアプリの上に描画されます。  

> [!NOTE]
> **継ぎ目**は、2つの画面間の間隔です。  

Web サイト \ (またはアプリ \) のエミュレートされたディスプレイが正しい表現です。  [Surface Duo][SurfaceDevicesDuo]の[Microsoft Edge Android アプリ][GooglePlayMicrosoftEdge]の表示と一致します。  **継ぎ目**に合わせて表示されるようにコンテンツを更新します。  Web サイトの外観を **seam**に適合させる方法の詳細については、Surface Duo のドキュメントで [seam を操作する方法][DualScreenIntroductionHowWorkSeam] を参照してください。  

[デバイスツールバー][DevtoolsDeviceModeIndexSimulateMobileViewport]には、web サイトまたはアプリを複数の方法でテストするための追加機能が用意されています。  **Rotate** ![ ][ImageRotateIcon] ビューポートを横方向に回転するには、[回転 \ (回転 \)] を選びます。 この機能を **スパン** \ ( ![ スパン \) と組み合わせると、シングル画面で、または折る、または折り目を切り替えることが ][ImageSpanIcon] できます。  これらの機能により、web サイトやアプリを4つのすべての方法でテストできます。  

:::image type="complex" source="./media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス" lightbox="./media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   デュアルスクリーンデバイスと折りたたみ式デバイスの事後の姿勢と向きのマトリックス  
:::image-end:::  

**実験的な Web platform 機能**\ ( ![ ExperimentalApis ][ImageExperimentalApisIcon] \) アイコンは、**実験的な web プラットフォーム機能**のフラグの状態を表示します。  フラグがオンになっている場合は、アイコンが強調表示されます。  フラグがオフになっている場合、アイコンは強調表示されません。  フラグをオンまたはオフにするには、アイコンを選択するか、または `edge://flags` フラグを移動して切り替えます。  

#### その他の資料  
*   開発の詳細については、「 [デュアルスクリーン web エクスペリエンス][DualScreenWebIndex]」を参照してください。  
*   Surface Duo エミュレーターをインストールします。  これは、Microsoft Edge のエミュレーターとは異なります。  Android を実行している Surface Duo をエミュレートし、 [Android Studio][AndroidDeveloperStudio]と統合します。  詳細については、「 [Surface DUO SDK の入手][DualScreenAndroidGetDuoSdk]」を参照してください。  

### 新しい CSS グリッドのデバッグ機能を有効にする  

CSS グリッドレイアウトを含む web サイトをデバッグするときに、ページの視覚エフェクトを向上させます。  DevTools の設定では、オーバーレイをさらにカスタマイズすることができます。  

:::image type="complex" source="./media/experiments-grid.msft.png" alt-text="CSS グリッドのデバッグ機能" lightbox="./media/experiments-grid.msft.png":::
   CSS グリッドのデバッグ機能  
:::image-end:::  

最新の実験的な機能をプレビューするには、次の操作を実行します。  

1.  [ **実験** ] セクションで、[ **新しい CSS グリッドのデバッグ機能を有効にする] チェックボックスをオンにします (再起動後に、レイアウトサイドバーウィンドウで使用可能な構成オプション)** 。  

<!--Available in Microsoft Edge version 85 and later.  -->  

### パネル間でタブを移動できるようにサポートを有効にする  

通常、 **要素** や **ネットワーク** などのツールは、devtools の上部にあるメインパネルでのみ開くことができます。  **3D ビュー**などのツール、および devtools の下部にある**引き出し**パネルで通常のみ開かれる**問題**。  実験を選択した後、上下のパネル間でツールを移動することができます。  ツールを移動するには、タブの上にマウスポインターを合わせて、コンテキストメニューの [ **先頭へ移動** ] または [ **下へ移動**] を選択します。   この実験では、DevTools レイアウトをカスタマイズできます。  **ドロワー**パネルの表示と非表示を切り替えるには、を選択し `Escape` ます。  

:::image type="complex" source="./media/experiments-move-panels.msft.png" alt-text="パネル間でタブを移動する" lightbox="./media/experiments-move-panels.msft.png":::
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

:::image type="complex" source="./media/experiments-webhint.msft.png" alt-text="[問題] パネルでの webhint のフィードバック" lightbox="./media/experiments-webhint.msft.png":::
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

:::image type="complex" source="./media/network-network-console.msft.png" alt-text="Console ドローワのネットワーク本体" lightbox="./media/network-network-console.msft.png":::
   **Console**ドローワの**ネットワーク本体**  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### ソースオーダービューアーを有効にする  

**ソースオーダービューアー** は、ページソース内の要素の順序を表示する実験です。  オンスクリーン表示の順序は、ソースの順序とは異なる場合があります。これには、スクリーンリーダーとキーボードのユーザーが混乱させるます。  **ソース注文ビューアー**を使用して、画面上の表示順序とソースの順序の違いを確認します。  

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

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン web エクスペリエンス |Microsoft ドキュメント"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo エミュレーターの入手 |Microsoft ドキュメント"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "Seam の操作方法-デュアルスクリーンデバイスの概要 |Microsoft ドキュメント"  

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo |Microsoft Surface"  

[VisualstudioCode]: https://code.visualstudio.com "Microsoft Visual Studio コード"  
[VisualstudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio のコードのキーボードショートカット (Windows |) |Microsoft Visual Studio コード"  

[GitHubMicrosoftedgeMsedgeexplainerFoldables]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ式デバイスでの対応エクスペリエンスのための Web プラットフォームプリミティブGitHub"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy 折りたたみ |Samsung"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "web ヒント"  
