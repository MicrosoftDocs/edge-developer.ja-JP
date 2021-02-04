---
description: Microsoft Edge の仮想デバイスを使用して、デュアルスクリーンと折りたたみ可能なデバイス向け Web サイトを強化します。
title: Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, エミュレーション, デバイス, シミュレーション, モバイル, デュアルスクリーン, 折りたたみ可能, Surface Galaxy, Samsung Galaxy Fold
ms.openlocfilehash: bc91c0b7c917d82f169dc7d47e047a587d505353
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313282"
---
# Microsoft Edge DevTools でデュアルスクリーンデバイスと折りたたみ可能なデバイスをエミュレートする  

Microsoft Edge バージョン 89 以降では、次のデュアルスクリーン デバイスと折りたたみ可能なデバイスをエミュレートできます。  

*   [Surface の一方][SurfaceDevicesDuo]  
*   [Samsung Galaxy Fold][SamsungMobileGalaxyFold]  
    
デバイスをエミュレートし、次の状態を切り替えます。  

*   単一画面または折りたたまれた状態  
*   デュアルスクリーンまたは展開された体勢  
    
試験的[な Web プラットフォーム API](#turn-on-experimental-apis)を有効にし[、CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用して、デュアルスクリーンと折りたたみ可能なデバイス向けの Web サイト \(または app\) を強化します。  

:::image type="complex" source="../media/experiments-surface-duo-emulation.msft.png" alt-text="Microsoft Edge で Surface のデュオをエミュレートする" lightbox="../media/experiments-surface-duo-emulation.msft.png":::  
   Microsoft Edge で Surface のデュオをエミュレートする  
:::image-end:::  

## 試験的な API を有効にする  

[CSS][DualScreenDocsCssMedia]メディア画面スパン機能と[JavaScript getWindowSegments API][DualScreenDocsJSAPI]を使用するには、Microsoft Edge でフラグ `Experimental Web Platform features` をオンにします。  次の手順を実行します。  

1.  に移動します `edge://flags` 。  
1.  [検索フラグ **] ボックスに**、「試験的な Web プラットフォーム機能」フラグを入力し、[無効] を [有効] `Experimental Web Platform features` に**変更します**。 **** ****  
1.  [Microsoft Edge を再起動]。  
    
:::image type="complex" source="../media/experiments-dual-screen-emulation-edge-flags.msft.png" alt-text="[試験的な Web プラットフォーム機能] フラグをオンにする" lightbox="../media/experiments-dual-screen-emulation.msft.png":::
   [試験的な **Web プラットフォーム機能] フラグをオン** にする  
:::image-end:::  

> [!NOTE]
> [CSS][DualScreenDocsCssMedia]メディア クエリまたは[JavaScript Windows セグメント][DualScreenDocsJSAPI]列挙 API を使用して Surface Surface の Web サイトまたはアプリを強化する場合は[、Surface Surface][SurfaceDevicesDuo][デバイス][SurfaceDevicesDuo]の Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリで試験的な**Web**プラットフォーム機能フラグもオンにする必要があります。  
> 
> デスクトップの[Microsoft][MicrosoftEdge] [Edge][SurfaceDevicesDuo]で試験的**な Web**プラットフォーム機能のフラグがオンになっていて[、Android Microsoft Edge][GooglePlayMicrosoftEdge]アプリでオフになっている場合、デスクトップの Surface Emulator の Web サイトまたはアプリの動作が、Microsoft Edge デスクトップの Android [Microsoft Edge][GooglePlayMicrosoftEdge]アプリと一致しません。  フラグが Android とデスクトップの Microsoft Edge で一致し、デスクトップの Microsoft Edge で Surface Emulator エミュレーターが正常に使用 [されたことを確認します][MicrosoftEdge]。  

## 折りたたみ可能なデバイスとデュアルスクリーン デバイスでのテスト  

Microsoft Edge でデュアルスクリーンの位置で [Surface Over][SurfaceDevicesDuo] をエミュレートすると、Web サイトまたはアプリの上に、"2 つの画面の間のスペース\" が描画されます。  

エミュレートされたディスプレイは[、Surface Surface の合][SurfaceDevicesDuo]図での実行中に Microsoft Edge [Android][GooglePlayMicrosoftEdge]アプリで Web サイト \(または app\) がレンダリングされる方法と一致します。  Web サイト \(または app\) を更新して、より良い画面を表示する必要がある場合があります。  For more information about adapting your website \(or app\) to the work [with the windows.][DualScreenIntroductionHowWorkSeam]  

デバイス [ツール バーには、][DevtoolsDeviceModeIndexSimulateMobileViewport] 複数の位置と向きで Web サイトまたはアプリをテストするのに役立つ追加機能があります。  ビューポート **を横向** きに回転するには、回転 ![ ](../media/rotate-dark-icon.msft.png) \( Rotate \) を選択します。 機能を Span \( **Span** \) と組み合わせて、単一画面または折りたたまれた状態とデュアルスクリーンの状態、または展開された状態を切り ![ ](../media/span-dark-icon.msft.png) 替える。  これらの機能を組み合わせて、4 つの考えられるすべての位置と向きで Web サイトまたはアプリをテストできます。  

:::image type="complex" source="../media/experiments-dual-screen-emulation-rotate-span.msft.png" alt-text="デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス" lightbox="../media/experiments-dual-screen-emulation-rotate-span.msft.png":::
   デュアルスクリーンおよび折りたたみ可能なデバイスの位置と向きのマトリックス  
:::image-end:::  

Experimental **Web Platform features** \( ExperimentalApis \) アイコンには、Experimental Web Platform 機能フラグの ![ ](../media/experimental-apis-dark-icon.msft.png) **状態が表示** されます。  フラグがオンの場合、アイコンが強調表示されます。  フラグがオフの場合、アイコンは強調表示されません。  フラグを \(or off\) に切り替えるには、アイコンを選択するか、フラグに移動して `edge://flags` 切り替えます。  

> [!NOTE]
> 現在の既知の問題の一覧を次に示します。  
> 
> *   [Microsoft][RemoteDesktopClientDocs]リモート デスクトップ クライアントを使ってリモート PC に接続し[、Surface Galaxy][SurfaceDevicesDuo]や Samsung [Galaxy Fold][SamsungMobileGalaxyFold]をエミュレートすると、ポインターが動き、つまずく可能性があります。  If you run into the issue, [send feedback](#getting-in-touch-with-the-microsoft-edge-devtools-team).  

## その他のリソース  

ここでは、デュアルスクリーン デバイス用に Web サイト \(または app\) を強化するのに役立つ可能性があるその他のリソースを示します。  

*   デュアルスクリーン デバイスでの Web 開発の詳細については、「デュアルスクリーン Web [エクスペリエンス」に移動してください][DualScreenWebIndex]。  
*   Surface [Emulator エミュレーターをインストールします][DualScreenAndroidUseEmulator]。  Surface Emulator エミュレーターは、Microsoft Edge のエミュレーターとは異なります。Android を実行し [、Android Studio と統合します][AndroidDeveloperStudio]。  詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "Microsoft Edge DevTools アプリケーションでデバイス モードを使用してモバイル デバイスをシミュレート|Microsoft Edge"  

[DualScreenWebIndex]: /dual-screen/web/index "デュアルスクリーン Web エクスペリエンス|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Emulator エミュレーター を取得|Microsoft Docs"  
[DualScreenIntroductionHowWorkSeam]: /dual-screen/introduction#how-to-work-with-the-seam "シームを処理する方法 - デュアルスクリーン デバイスの概要 | Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface Emulator エミュレーター を使|Microsoft Docs"  
[DualScreenDocsCssMedia]: /dual-screen/web/css-media-spanning "デュアルスクリーン検出のための CSS メディアのスクリーンスパニング機能 | Microsoft Docs"  
[DualScreenDocsJSAPI]: /dual-screen/web/javascript-getwindowsegments "デュアルスクリーン デバイスのための getWindowSegments JavaScript API | Microsoft Docs"  

[RemoteDesktopClientDocs]: /windows-server/remote/remote-desktop-services/clients/remote-desktop-clients "リモート デスクトップ クライアントの|Microsoft Docs"

[MicrosoftEdge]: https://www.microsoft.com/edge "Microsoft Edge"  

[SurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Surface の |Microsoft Surface"  

[AndroidDeveloperStudio]: https://developer.android.com/studio/ "Android Studio"  

[GooglePlayMicrosoftEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge |Google Play"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/mobile/galaxy-fold/ "Galaxy Fold |Samsung"  
