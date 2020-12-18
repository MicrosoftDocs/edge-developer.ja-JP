---
description: Surface Emulator エミュレーターのリモート デバッグを開始します。
title: Surface Emulator エミュレーターのリモート デバッグの開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, Web 開発, f12 ツール, devtools, リモート デバッグ, android, surface の数
ms.openlocfilehash: f44c85c468de3bdd7727695e3f33269584966231
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230647"
---
# Surface Emulator エミュレーターのリモート デバッグの開始  

この記事では[、Microsoft Edge][MicrosoftSurfaceDevicesSurfaceDuo]のデスクトップ インスタンスから Surface Emulator の[Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx]アプリで Web コンテンツをリモートでデバッグするプロセスについて[説明します][MicrosoftEdge]。  Surface Duo デバイスでのデバッグの詳細については、Android デバイスのリモート デバッグに関する [ガイドに従ってください][DevtoolsRemoteDebuggingMain]。  

## 始める前に

Surface Emulator エミュレーター [を実行する][MicrosoftDownload100847] 前に [、Surface Sdk をインストールします][DualScreenAndroidUseEmulator]。  詳しくは [、Surface Sdk の取得に関するページをご覧ください][DualScreenAndroidGetDuoSdk]。  

## 手順 1: フォルダーに移動edge://inspect  

Microsoft Edge のデスクトップ インスタンス [を開き][MicrosoftEdge]、次に移動します `edge://inspect` 。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page.msft.png" alt-text="デスクトップedge://inspect Microsoft Edge のページ" lightbox="../media/remote-debugging-surface-duo-inspect-page.msft.png":::
   デスクトップ `edge://inspect` 上の Microsoft Edge のページ  
:::image-end:::

> [!NOTE]
> ページで `edge://inspect` Surface Emulator エミュレーターが認識されない場合 [は、][DualScreenAndroidUseEmulator]エミュレーターを再起動します。  

## 手順 2: Surface Emulator エミュレーターを起動する  

Surface [Emulator エミュレーターを起動します][DualScreenAndroidUseEmulator]。  エミュレーターで実行されている 2 つの異なる画面がエミュレーターに表示されます。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator.msft.png" alt-text="Surface Emulator" lightbox="../media/remote-debugging-surface-duo-emulator.msft.png":::
   Surface Emulator  
:::image-end:::  

## 手順 3: Surface Emulator エミュレーターで Microsoft Edge に Web コンテンツを読み込む  

どちらの画面でも [、Surface Emulator][DualScreenAndroidUseEmulator] エミュレーターのお気に入りトレイを上にスワイプして、アプリ ドロワーを表示します。  **[Edge] を**選択して[Microsoft Edge アプリを起動します][GooglePlayStoreAppsComMicrosoftEmmx]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-emulator-edge.msft.png" alt-text="Surface Emulator エミュレーター上の Microsoft Edge アプリ" lightbox="../media/remote-debugging-surface-duo-emulator-edge.msft.png":::
   Surface Emulator エミュレーター上の Microsoft Edge アプリ  
:::image-end:::  

Microsoft Edge アプリでデバッグする Web サイトまたはアプリに [移動します][GooglePlayStoreAppsComMicrosoftEmmx]。  

## 手順 4: Surface Emulator エミュレーターから Web コンテンツをデバッグする  

Microsoft Edge のデスクトップ インスタンスに切り [替えます][MicrosoftEdge]。  このページには、Surface Emulator エミュレーターで実行されている開いているタブまたは PAS の一覧が表示された `edge://inspect` [][ProgressiveWebAppsIndex]**SurfaceDwrEmulator** [が表示されます][DualScreenAndroidUseEmulator]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png" alt-text="次edge://inspect、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。" lightbox="../media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png":::
   この `edge://inspect` ページには、エミュレーターで実行されている Microsoft Edge アプリで開いているタブの一覧が表示されます。  
:::image-end:::  

> [!NOTE]
> ページに**SurfaceD emulatorEmulator**が表示されない場合は、Surface Emulator エミュレーターの Microsoft Edge アプリでタブを開くまたは閉 `edge://inspect` [じしてみてください][DualScreenAndroidUseEmulator]。 [][GooglePlayStoreAppsComMicrosoftEmmx]  その他のトラブルシューティング手順については [、Android デバイスのトラブルシューティングのセクションを参照してください][DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]。  

エミュレーターで実行されている開いているタブの一覧から、**** デバッグする Web コンテンツを含むタブの検査を選択します。  Microsoft [Edge DevTools が][DevtoolsIndex] 新しいウィンドウで開きます。  [Toggle **Screencast** \( Toggle Screencast \) ] を選択して、Surface Emulator エミュレーターの Web コンテンツを ![ ][ImageToggleScreencastIcon] DevTools ウィンドウに表示します。 [][DualScreenAndroidUseEmulator]  これで、Microsoft Edge DevTools を使用して、Surface Emulator エミュレーターで Web コンテンツ [をデバッグできます][DualScreenAndroidUseEmulator]。  

:::image type="complex" source="../media/remote-debugging-surface-duo-devtools.msft.png" alt-text="Microsoft Edge DevTools を使用して Surface Emulator エミュレーター上の Microsoft Edge アプリで Bing をデバッグする" lightbox="../media/remote-debugging-surface-duo-devtools.msft.png":::
   Microsoft Edge DevTools を使用して Surface Emulator エミュレーター上の Microsoft Edge アプリで Bing をデバッグする  
:::image-end:::  

> [!NOTE]
> エミュレーターの両方の画面 [に Microsoft Edge][GooglePlayStoreAppsComMicrosoftEmmx] アプリをまたがっている場合、スクリーンキャストにはアプリの新しいサイズが反映されますが、画面は反映されません。  この問題が Web コンテンツのレイアウトに与える影響を理解するには、スクリーンキャストの代わりに [Surface Emulator][DualScreenAndroidUseEmulator] エミュレーターを使用します。  

## その他のリソース  

この Web は、HTML、CSS、JavaScript を 1 回記述して、単一画面、デュアルスクリーン、折りたたみ可能なデバイスで見た目が良いため、折りたたみ可能なデュアルスクリーン デバイスの新しいクラスに最適なプラットフォームです。  詳細については、これらの新しいデバイスの Web コンテンツの構築を開始するために、以下のその他のリソースを参照してください。  

*   [デュアルスクリーン デバイスでアプリを作成するためのドキュメント][DualScreenIndex]  
*   [折りたたみ可能なデュアルスクリーン デバイスで Web エクスペリエンスを構築するための新しい API に関する Microsoft Edge Web プラットフォームの説明][GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]  
*   [Microsoft 365 Developer Day セッションのレコーディング: Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法][YoutubeDxrzwsqxpvc]  

<!-- image links -->  

[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[ProgressiveWebAppsIndex]: ../../progressive-web-apps-chromium/index.md "Windows での段階的な Web アプリ |Microsoft Docs"  
[DevtoolsRemoteDebuggingMain]: ./index.md "Android デバイスのリモート デバッグの概要 |Microsoft Docs"  
[DevtoolsRemoteDebuggingIndexTroubleshootingDevtoolsIsNotDetectingAndroidDevice]: ./index.md#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools が Android デバイスを検出しない - Android デバイスのリモート デバッグの概要 |Microsoft Docs"  

[DualScreenIndex]: /dual-screen/index "デュアルスクリーン デバイス用のアプリを作成する |Microsoft Docs"  
[DualScreenAndroidUseEmulator]: /dual-screen/android/use-emulator "Surface D Emulator を使う |Microsoft Docs"  
[DualScreenAndroidGetDuoSdk]: /dual-screen/android/get-duo-sdk "Surface Sdk を取得する |Microsoft Docs"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge の導入"  
[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新しい Surface の組み合わせ |Microsoft Surface"  
[MicrosoftDownload100847]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Sdk プレビュー リリースをダウンロードする |Microsoft ダウンロード センター"  

[GooglePlayStoreAppsComMicrosoftEmmx]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge: Web ブラウザー |GooglePlay"  

[GithubMicrosoftedgeMsedgeexplainersFoldablesExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ可能なデバイスでの対応エクスペリエンスのための Web プラットフォーム プリミティブ - MicrosoftEdge/MSEdgeExplainers |GitHub"  

[YoutubeDxrzwsqxpvc]: https://youtu.be/DXrZWsqXPVc "Web サイトと Web アプリのデュアルスクリーン エクスペリエンスを構築する方法 |YouTube"  
