---
description: デュアルスクリーンおよび折りたたみMicrosoft Edgeの Web サイトを強化するには、仮想デバイスを使用します。
title: DevTools でデュアルスクリーンデバイスと折りたたみMicrosoft Edgeエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル, デュアルスクリーン, 折りたたみ式, Surface Duo, Samsung Galaxy Fold
ms.openlocfilehash: c3bd3296afa86d9d2c90c164bc3e9088bc043c3c
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564344"
---
# <a name="emulate-dual-screen-and-foldable-devices-in-microsoft-edge-devtools"></a>DevTools でデュアルスクリーンデバイスと折りたたみMicrosoft Edgeエミュレートする  

バージョン Microsoft Edge 89 以降では、次のデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートできます。  

*   [Surface Duo][SurfaceDevicesDuo]  
*   [Samsung Galaxy Fold][SamsungMobileGalaxyFold]  
    
デバイスをエミュレートし、次のポスチャを切り替えます。  

*   1 画面または折りたたまれた姿勢  
*   デュアルスクリーンまたは展開された姿勢  
    
実験的な[Web プラットフォーム API](#turn-on-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面にまたがる機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンおよび折りたたみ可能なデバイス用の Web サイト \(または app\) を強化します。  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="[Surface Duo のエミュレート] Microsoft Edge" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   [Surface Duo のエミュレート] Microsoft Edge  
:::image-end:::  

## <a name="turn-on-experimental-apis"></a>実験的な API を有効にする  

[CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、次のページでフラグ `Experimental Web Platform features` をMicrosoft Edge。  次の手順を実行します。  

1.  `edge://flags` に移動します。  
1.  [検索フラグ **] テキスト**ボックスに「実験 Web プラットフォーム機能フラグ」と入力し、[無効] を [有効] `Experimental Web Platform features` **に****変更します**。 ****  
1.  [Microsoft Edge を再起動]。  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[実験用 Web プラットフォームの機能] フラグをオンにする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   [実験用 **Web プラットフォームの機能] フラグをオン** にする  
:::image-end:::  

> [!NOTE]
> [CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows][DualScreenDocsJSAPI]セグメント列挙 API を使用して[Surface Duo][SurfaceDevicesDuo]の Web サイトまたはアプリを強化する場合**** は、Surface [Duo][SurfaceDevicesDuo]デバイスの[Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリの [実験用 Web プラットフォーム機能] フラグもオンにする必要があります。  
> 
> デスクトップ****[Microsoft Edge][MicrosoftEdge]で実験的 Web プラットフォーム機能フラグがオンになっていて[、Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリでオフになっている場合、デスクトップ Microsoft Edge の Surface Duo エミュレーターでの Web サイトまたはアプリの動作が Surface [Duo][SurfaceDevicesDuo]の[Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリと一致しません。  フラグが Android とデスクトップ の間で一致Microsoft Edgeデスクトップ アプリで Surface Duo エミュレーターを正常に使用[Microsoft Edge。][MicrosoftEdge]  

## <a name="test-on-foldable-and-dual-screen-devices"></a>折りたたみおよびデュアルスクリーン デバイスでのテスト  

Microsoft Edge のデュアルスクリーンの姿勢で[Surface Duo][SurfaceDevicesDuo]をエミュレートすると、web サイトまたはアプリの上にシーム \(2 つの画面の間のスペース\) が描画されます。  

エミュレートされた表示は、Surface Duo での実行中に web サイト \(または app\) が Microsoft Edge [Android][GooglePlayMicrosoftEdge]アプリでレンダリングする方法と[一致します][SurfaceDevicesDuo]。  縫い目に沿って表示するには、Web サイト \(または app\) を更新する必要があります。  Web サイト \(または app\) を継ぎ目に合わせる方法の詳細については、「縫い目を操作する方法」 [を参照してください][DualScreenIntroductionHowWorkSeam]。  

デバイス [ツールバーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の姿勢と向きで Web サイトやアプリをテストするのに役立つ追加機能があります。  ビューポート **を横向** き ![ に回転 ](../media/rotate-dark-icon.msft.png) するには、[回転]\(回転\) を選択します。 機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた姿勢とデュアルスクリーンまたは展開された姿勢を ![ ](../media/span-dark-icon.msft.png) 切り替えてください。  この機能を組み合わせて、4 つの可能なすべての姿勢と向きで Web サイトまたはアプリをテストできます。  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの姿勢と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   デュアルスクリーンおよび折りたたみ可能なデバイスの姿勢と向きのマトリックス  
:::image-end:::  

実験 **Web プラットフォーム機能** \( ExperimentalApis \) アイコンは、実験 Web プラットフォーム機能フラグの状態 ![ ](../media/experimental-apis-dark-icon.msft.png) **を表示** します。  フラグをオンにすると、アイコンが強調表示されます。  フラグがオフの場合、アイコンは強調表示されません。  \(or off\) フラグを有効にするには、アイコンを選択するか、フラグに移動して `edge://flags` 切り替えます。  

> [!NOTE]
> 現在の既知の問題の一覧を次に示します。  
> 
> *   リモート PC に接続[Microsoft リモート デスクトップ][RemoteDesktopClientDocs]クライアントを使用して Surface Duo または[Samsung Galaxy][SurfaceDevicesDuo] [Fold][SamsungMobileGalaxyFold]をエミュレートすると、ポインターが揺れや吃音を発生する可能性があります。  問題が発生した場合は、フィードバック [を送信します](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

## <a name="additional-resources"></a>その他のリソース  

デュアルスクリーン デバイスの Web サイト \(または app\) の強化に役立つその他のリソースを次に示します。  

*   デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web エクスペリエンス [」に移動します][DualScreenWebIndex]。  
*   Surface [Duo エミュレーターをインストールします][DualScreenAndroidUseEmulator]。  Surface Duo エミュレーターは、Microsoft Edgeのエミュレーターとは異なって、Android を実行し[、Android Studio と統合します][AndroidDeveloperStudio]。  詳細については [、「Get the Surface Duo SDK」に移動します][DualScreenAndroidGetDuoSdk]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "DevTools アプリケーションでデバイス モードでモバイル Microsoft Edgeをシミュレート|Microsoft Edge"  

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

[SamsungMobileGalaxyFold]: https://www.samsung.com/global/galaxy/galaxy-fold "Galaxy Fold |Samsung"  
