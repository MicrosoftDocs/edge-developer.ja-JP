---
description: リモート デバッグ Surface Duo エミュレーターの使用を開始します。
title: リモート デバッグ Surface Duo エミュレーターの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, リモート デバッグ, android, surface duo
ms.openlocfilehash: 61f903a5b929b7ee7b924938cf6ddc21a9783ca7
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439330"
---
# <a name="get-started-with-remote-debugging-surface-duo-emulators"></a>リモート デバッグ Surface Duo エミュレーターの使用を開始する  

この記事では [、Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] のデスクトップ インスタンスから Surface Duo エミュレーター上の Microsoft [Edge][MicrosoftSurfaceDevicesSurfaceDuo] アプリで Web コンテンツをリモートでデバッグするプロセスについて [説明します][MicrosoftEdge]。  Surface Duo デバイスでのデバッグの詳細については、Android デバイスのリモート デバッグに関するガイド [に従ってください][DevtoolsRemoteDebuggingMain]。  

## <a name="before-you-begin"></a>開始する前に

Surface Duo [エミュレーターを実行する前][MicrosoftDownload100847] に Surface Duo SDK [をインストールします][DualScreenAndroidUseEmulator]。  詳細については [、「Get the Surface Duo SDK」に移動します][DualScreenAndroidGetDuoSdk]。  

## <a name="step-1-navigate-to-edgeinspect"></a>手順 1: [手順 1] に移動 edge://inspect  

Microsoft Edge のデスクトップ インスタンスを [開き][MicrosoftEdge]、に移動します `edge://inspect` 。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="デスクトップ edge://inspect Microsoft Edge の [新しいページ] ページ" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   デスクトップ `edge://inspect` 上の Microsoft Edge のページ  
:::image-end:::

> [!NOTE]
> ページで `edge://inspect` Surface Duo エミュレーターが認識されない場合 [は、][DualScreenAndroidUseEmulator]エミュレーターを再起動します。  

## <a name="step-2-launch-the-surface-duo-emulator"></a>手順 2: Surface Duo エミュレーターを起動する  

Surface [Duo エミュレーターを起動します][DualScreenAndroidUseEmulator]。  エミュレーターで実行されている 2 つの異なる画面がエミュレーターに表示されます。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Duo エミュレーター" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   Surface Duo エミュレーター  
:::image-end:::  

## <a name="step-3-load-your-web-content-in-microsoft-edge-on-the-surface-duo-emulator"></a>手順 3: Surface Duo エミュレーターで Microsoft Edge に Web コンテンツを読み込む  

どちらの画面でも [、Surface Duo][DualScreenAndroidUseEmulator] エミュレーターの [お気に入り] トレイを上にスワイプして、[アプリの引き出し] を表示します。  [ **エッジ] を** 選択して [Microsoft Edge アプリを起動します][GooglePlayStoreAppsComMicrosoftEmmx]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Duo エミュレーターの Microsoft Edge アプリ" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   Surface Duo エミュレーターの Microsoft Edge アプリ  
:::image-end:::  

Microsoft Edge アプリでデバッグする Web サイトまたはアプリ [に移動します][GooglePlayStoreAppsComMicrosoftEmmx]。  

## <a name="step-4-debug-your-web-content-from-the-surface-duo-emulator"></a>手順 4: Surface Duo エミュレーターから Web コンテンツをデバッグする  

Microsoft Edge のデスクトップ インスタンスに切り [替えます][MicrosoftEdge]。  このページには、Surface Duo エミュレーターで実行されている開いているタブまたは PWA の一覧が表示された `edge://inspect` **SurfaceDuoEmulator**が[表示されます][DualScreenAndroidUseEmulator]。 [][ProgressiveWebAppsIndex]  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="[edge://inspect] ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   この `edge://inspect` ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。  
:::image-end:::  

> [!NOTE]
> **SurfaceDuoEmulator**がページに表示されない場合は、Surface Duo エミュレーターの Microsoft Edge アプリでタブを開くまたは閉 `edge://inspect` [じ直してみてください][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]  その他のトラブルシューティング手順については [、Android デバイスのトラブルシューティング セクションに移動します][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。  

エミュレーターで実行されている開いているタブの一覧から、**** デバッグする Web コンテンツを含むタブで [検査] を選択します。  Microsoft [Edge DevTools が][DevtoolsIndex] 新しいウィンドウで開きます。  [ **画面キャストの切り替え** \( 画面キャスト \) の切り替え] を ![ ](../media/toggle-screencast-icon.msft.png) 選択して [、[DevTools]][DualScreenAndroidUseEmulator] ウィンドウで Surface Duo エミュレーターから Web コンテンツを表示します。  これで、Microsoft Edge DevTools を使用して Surface Duo エミュレーターで Web コンテンツを [デバッグできます][DualScreenAndroidUseEmulator]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="Surface Duo エミュレーターで Microsoft Edge アプリで Microsoft Edge DevTools を使用して Bing をデバッグする" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   Surface Duo エミュレーターで Microsoft Edge アプリで Microsoft Edge DevTools を使用して Bing をデバッグする  
:::image-end:::  

> [!NOTE]
> エミュレーターの両方の [画面に Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] アプリをまたがっている場合、スクリーンキャストはアプリの新しいサイズを反映しますが、ヒンジは反映されません。  ヒンジが Web コンテンツのレイアウトに与える影響を理解するには、スクリーンキャストではなく [Surface Duo エミュレーター][DualScreenAndroidUseEmulator] を使用します。  

## <a name="additional-resources"></a>その他のリソース  

WEB は、HTML、CSS、JavaScript を 1 回書き込み、シングルスクリーン、デュアルスクリーン、および折りたたみ可能なデバイス全体で見た目が良い可能性があるため、折りたたみおよびデュアルスクリーン デバイスの新しいクラスに最適なプラットフォームです。  詳細については、次の追加リソースに移動して、これらの新しいデバイスの Web コンテンツの構築を開始します。  

*   [デュアルスクリーン デバイスでアプリを作成するためのドキュメント][DualScreenIndex]  
*   [折りたたみおよびデュアルスクリーン デバイスで Web エクスペリエンスを構築するための新しい API の Microsoft Edge Web プラットフォームの説明者][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [Microsoft 365 Developer Day セッションの記録: Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法][YoutubeDxrzwsqxpvc]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows 上のプログレッシブ Web アプリ |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools が Android デバイスを検出していない - Android デバイスのリモート デバッグを開始する方法|Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "デュアルスクリーン デバイス向けアプリを作成|Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface DUo エミュレーターを使用|Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Duo SDK を取得|Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge の導入"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo の新しい|Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Duo SDK プレビュー リリース のダウンロード |Microsoft ダウンロード センター"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web ブラウザー |GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ可能なデバイスでの啓蒙エクスペリエンスのための Web プラットフォーム プリミティブ - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する|YouTube"  
