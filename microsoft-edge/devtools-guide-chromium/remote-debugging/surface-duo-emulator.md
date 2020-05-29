---
title: リモートデバッグ Surface Duo エミュレーターの使用を開始する
author: zoherghadyali
ms.author: zoghadya
ms.date: 04/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、リモートデバッグ、android、surface duo
ms.openlocfilehash: af6fa6433b0bc6bba0599e6e9a805235504caadd
ms.sourcegitcommit: 966bfc60040acc794b6ee20eb2084bc8264a4852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "10621503"
---
# リモートデバッグ Surface Duo エミュレーターの使用を開始する

この記事では、 [microsoft][DesktopEdge]edge のデスクトップインスタンスから[Surface Duo][SurfaceDuo]エミュレーター上の[microsoft edge アプリ][AndroidEdge]の web コンテンツをリモートでデバッグするプロセスについて説明します。 Surface Duo デバイスでのデバッグについては、「 [Android デバイスのリモートデバッグ][RemoteDebuggingAndroid]のガイド」を参照してください。

## 始める前に

Surface [duo エミュレーター][DuoEmulator]を実行する前に[surface duo SDK][DuoSdk]をインストールします。 詳しくは、「 [Surface DUO SDK の入手][DuoSdkdocs]」をご覧ください。

## 手順 1: edge://inspect に移動する

[Microsoft Edge][DesktopEdge]のデスクトップインスタンスを開き、に移動し `edge://inspect` ます。

> ##### 図 1  
> デスクトップ `edge://inspect` 上の Microsoft edge のページデスクトップ上の ![ microsoft edge の edge://inspect ページ][ImageEdgeInspect]

> [!NOTE]
> ページで `edge://inspect` [Surface Duo エミュレーター][DuoEmulator]が認識されない場合は、エミュレーターを再起動します。

## 手順 2: Surface Duo エミュレーターを起動する

[Surface Duo エミュレーター][DuoEmulator]を起動します。 エミュレーターでは、2つの異なる画面がエミュレーターで実行されていることに注意してください。

> ##### 図 2
> Surface duo エミュレーター ![ の Surface duo エミュレーター][ImageDuoEmulator]  

## 手順 3: Surface Duo エミュレーターで Microsoft Edge に web コンテンツを読み込む

どちらの画面でも、 [Surface Duo エミュレーター][DuoEmulator]のお気に入りトレイを上にスワイプして、[アプリ] ドローワを表示します。 [ **Edge** ] を選択して、 [Microsoft edge アプリ][AndroidEdge]を起動します。

> ##### 図 3
> Surface duo エミュレーター上の Microsoft edge アプリ (surface duo エミュレーター上の microsoft edge ![ アプリ)][ImageDuoEmulatorEdge]  

[Microsoft Edge アプリ][AndroidEdge]でデバッグする web サイトまたはアプリに移動します。

## 手順 4: Surface Duo エミュレーターから web コンテンツをデバッグする 

[Microsoft Edge][DesktopEdge]のデスクトップインスタンスに切り替えます。 この `edge://inspect` ページには、 [Surface Duo エミュレーター][DuoEmulator]で実行されている、開いているタブまたは[pwas][PwaDocs]の一覧が表示された**SurfaceDuoEmulator**が表示されるようになりました。

> ##### 図 4
> このページには、 `edge://inspect` エミュレーターで実行されている Microsoft edge アプリの開いているタブの一覧が表示され ![ ます。 Edge://inspect ページには、エミュレーターで実行されている microsoft edge アプリの開いているタブの一覧が表示されます。][ImageEdgeInspectTargets]  

> [!NOTE]
> ページに**SurfaceDuoEmulator**が表示されない場合は `edge://inspect` 、 [Surface Duo エミュレーター][DuoEmulator]で[Microsoft Edge アプリ][AndroidEdge]のタブを開くか、または閉じてみてください。 その他のトラブルシューティング手順については、「 [Android デバイスのトラブルシューティング」][TroubleshootingAndroid]を参照してください。

エミュレーターで実行されている開いているタブの一覧から、デバッグする web コンテンツがあるタブで [**検査**] を選びます。 [Microsoft Edge DevTools][DevToolsDocs]が新しいウィンドウで開きます。 「ツール」「**切り替え Screencast** ![ トグル Screencast を選択して ][ImageToggleScreencastIcon] 、「Devtools」ウィンドウで[Surface Duo エミュレーター][DuoEmulator]の web コンテンツを表示します。 [Surface Duo エミュレーター][DuoEmulator]で、Microsoft Edge devtools を使って web コンテンツをデバッグできるようになりました。

> ##### 図 5
> Microsoft edge DevTools を使って Surface Duo エミュレーター上の Microsoft Edge アプリで Bing をデバッグします。 ![ surface duo エミュレーター上の Microsoft edge アプリで bing をデバッグします。][ImageDevTools]  

> [!NOTE]
> エミュレーターの両方の画面で[Microsoft Edge アプリ][AndroidEdge]をスパンしている場合、screencast には、アプリケーションの新しいサイズが反映されますが、ヒンジは表示されません。 ヒンジが web コンテンツのレイアウトに与える影響を理解するには、screencast ではなく[Surface Duo エミュレーター][DuoEmulator]を使用します。

## その他のリソース

Web は、HTML、CSS、JavaScript を1回作成でき、1画面、2画面、折りたたみ式デバイスで適切に表示されるようにするため、折りたたみ式とデュアルスクリーンデバイスの新しいクラスの優れたプラットフォームです。 詳細については、以下の追加リソースを参照してください。これらの新しいデバイスの web コンテンツの構築を開始します。

- [デュアルスクリーンデバイスでのアプリの作成に関するドキュメント][DualScreenDocs]
- [Microsoft Edge web platform explainer は、新しい Api を使用して、折りたたみ式デバイスとデュアルスクリーンデバイスで web エクスペリエンスを構築します。][WebPlatformExplainer]
- [Microsoft 365 Developer Day セッションの記録: web サイトと web アプリのためのデュアルスクリーンエクスペリエンスの構築方法][DeveloperDay]

<!-- image links -->  
[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page.msft.png "図 1: デスクトップ上の Microsoft Edge の edge://inspect ページ"
[ImageDuoEmulator]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator.msft.png "図 2: Surface Duo エミュレーター"
[ImageDuoEmulatorEdge]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-emulator-edge.msft.png "図 3: Surface Duo エミュレーター上の Microsoft Edge アプリ"
[ImageEdgeInspectTargets]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-inspect-page-with-targets.msft.png "図 4: edge://inspect ページには、エミュレーターで実行されている Microsoft Edge アプリの開いているタブの一覧が表示されます。"
[ImageToggleScreencastIcon]: images/toggle-screencast-icon.msft.png
[ImageDevTools]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-surface-duo-devtools.msft.png "図 5: Surface Duo エミュレーター上の Microsoft Edge アプリで Bing をデバッグするための Microsoft Edge DevTools の使用"

<!-- links -->  
[RemoteDebuggingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの概要"
[PwaDocs]: /microsoft-edge/progressive-web-apps-chromium/index "Windows のプログレッシブ Web アプリ"
[DevToolsDocs]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール"
[TroubleshootingAndroid]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index#troubleshooting-devtools-is-not-detecting-the-android-device "トラブルシューティング: DevTools で Android デバイスが検出されない"

[AndroidEdge]: https://play.google.com/store/apps/details?id=com.microsoft.emmx "Microsoft Edge Android アプリ"
[SurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "Surface Duo の概要"
[DesktopEdge]: https://www.microsoft.com/edge/ "新しい Microsoft Edge の紹介"
[DuoEmulator]: https://docs.microsoft.com/dual-screen/android/use-emulator "Surface DUo エミュレーターを使う"
[DuoSdk]: https://www.microsoft.com/download/details.aspx?id=100847 "Surface Duo SDK Preview リリース"
[DuoSdkDocs]: https://docs.microsoft.com/dual-screen/android/get-duo-sdk "Surface Duo SDK の入手"
[DualScreenDocs]: https://docs.microsoft.com/dual-screen/ "デュアルスクリーンデバイス用のアプリを作成する"
[WebPlatformExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/Foldables/explainer.md "折りたたみ式デバイスでの対応エクスペリエンスのための Web Platform プリミティブ"
[DeveloperDay]: https://youtu.be/DXrZWsqXPVc "Web サイトと web アプリのためのデュアルスクリーンエクスペリエンスを構築する方法"
