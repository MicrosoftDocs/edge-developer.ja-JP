---
description: Microsoft Edge と Android でサイトが適切に動作するように、ジョブが終了することはありません。  デバイスモードでは、iPhones などのさまざまなデバイスをシミュレートできますが、他のブラウザーで提供されているエミュレーションのためのソリューションを確認することをお勧めします。
title: 他のブラウザーをエミュレートしてテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1a7cc1c7e0a49760f30afdc16921824372b3a1aa
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124944"
---
<!-- Copyright Meggin Kearney and Paul Bakaus

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# 他のブラウザーをエミュレートしてテストする  

Microsoft Edge と Android でサイトが適切に動作するように、ジョブが終了することはありません。  デバイスモードでは、iPhones などのさまざまなデバイスをシミュレートできますが、他のブラウザーで提供されているエミュレーションのためのソリューションを確認することをお勧めします。  

### まとめ  

*   特定のデバイスを持っていない場合、または何らかの点でスポットチェックを実行する場合は、ブラウザー内でデバイスをエミュレートすることをお勧めします。  
*   デバイスエミュレーターとシミュレータを使用すると、開発者向けサイトをワークステーションのさまざまなデバイスで模倣できます。  
*   クラウドベースのエミュレーターを使用すると、さまざまなプラットフォームでサイトの単体テストを自動化できます。  

## ブラウザーエミュレーター  

ブラウザーエミュレーターは、サイトの応答性をテストするのに適していますが、API、CSS のサポート、モバイルブラウザーで表示される特定の動作の違いをエミュレートすることはありません。  実際のデバイスで実行されているブラウザーでサイトをテストして、すべてが予期したとおりに動作することを確認します。  

### Firefox の応答性の高いデザインビュー  

Firefox には、特定のデバイスについて検討することをお勧めする、 [応答性の高いデザインビュー][MDNResponsiveDesignMode] が用意されています。また、端をドラッグすることで、一般的な画面サイズまたは独自のサイズでデザインがどのように変化するかを調べることができます。  

### EdgeHTML エミュレーション  

Windows Phone をエミュレートするには、Microsoft Edge \ (EdgeHTML \) [ビルトインエミュレーション][DevToolsEdgeHtmlEmulation]を使用します。  

Internet Explorer の以前のバージョンでページがどのように表示されるかをシミュレートするには、 [IE 11 エミュレーション][Ie11DevToolsEmulation] を使用します。  

## デバイスエミュレーターとシミュレータ  

デバイスシミュレータとエミュレーターは、ブラウザー環境だけでなく、デバイス全体をシミュレートします。  各機能は、OS の統合を必要とするものをテストするのに役立ちます。たとえば、仮想キーボードを使用したフォーム入力です。  

### Android エミュレーター  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

現時点では、Android エミュレーターに Microsoft Edge をインストールする方法はありません。  ただし、Android ブラウザー、Chromium Content Shell、Android 用 Firefox は、このガイドの後半で確認することができます。  Chromium Content Shell は Microsoft Edge と同じ Chromium レンダリングエンジンを実行しますが、ブラウザー固有の機能はありません。  

Android エミュレーターには、android [Studio][AndroidStudioDownload]の一部としてダウンロードする必要がある android SDK が付属しています。  次に、指示に従って [仮想デバイス][AndroidStudioCreateManageVirtualDevices] をセットアップし、 [エミュレーターを開始][AndroidStudioRunAppsAndroidEmulator]します。  
エミュレーターが起動したら、ブラウザーアイコンをクリックして、Android 用の古いストックブラウザーでサイトをテストします。  

#### Android での Chromium コンテンツシェル  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

Android 用の Chromium Content Shell をインストールするには、エミュレーターを実行したままにして、次のコマンドを実行します。  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

これで、Chromium Content Shell を使ってサイトをテストできるようになりました。  

#### Android の Firefox  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

Chromium Content Shell と同様に、Firefox をエミュレーターにインストールするための APK を取得できます。  

[適切な apk ファイルをダウンロード][MozillaFirefoxDownload]します。  

ファイルを開いているエミュレーターまたは接続されている Android デバイスにインストールするには、次のコマンドを実行します。  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### iOS シミュレータ  

IOS シミュレータ for Mac OS X には Xcode が付属しています。このアプリは、 [App Store からインストール][MacAppStoreXcode]します。  

完了したら、 [Apple 開発者向けドキュメント][AppleSimulatorHelp]でシミュレータを操作する方法について説明します。  

> [!NOTE]
> IOS シミュレータを使用するたびに Xcode を開く必要がないようにするには、そのまま開き、dock の iOS シミュレータアイコンを右クリックして、[ **dock に保持**] を選びます。  次に、必要なときにこのアイコンをクリックするだけです。  

###  Microsoft Edge (EdgeHTML)  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   モダン IE VM  
:::image-end:::  

Microsoft Edge \ (EdgeHTML \) 仮想マシン \ (Vm \) を使用すると、VirtualBox \ (または VMWare \) を介してコンピューター上のさまざまなバージョンの EdgeHTML と IE にアクセスできます。  [ダウンロードページで仮想マシン][MicrosoftDeveloperEdgeVms]を選択します。  

## クラウドベースのエミュレーターとシミュレータ  

エミュレーターを使うことができず、実際のデバイスにアクセスできない場合は、クラウドベースのエミュレーターを使用するのが最適です。  実際のデバイスとローカルエミュレーターによるクラウドベースのエミュレーターの大きな利点は、さまざまなプラットフォームでサイトの単体テストを自動化できることです。  

*   [Browserstack (商用)][|::ref1::|] は、手動テストで最も簡単に使用できます。  オペレーティングシステムを選択して、使用しているブラウザーのバージョンとデバイスの種類を選択します。参照する URL を選択すると、対話できるホストされた仮想マシンが回転します。  また、同じ画面で複数のエミュレーターを実行できるため、複数のデバイスで同時にアプリの外観をテストすることができます。  
*   [SauceLabs (商用)][SauceLabs] では、エミュレーターの内部で単体テストを実行できます。この機能は、サイト内でのフローのスクリプトを作成し、後でさまざまなデバイスでその後のビデオ録画を監視する場合に特に便利です。  サイトで手動テストを行うこともできます。  
*   [任意のデバイス (商用)][AppExperience] では、リモートで制御できるエミュレーターである実際のデバイスは使用されません。  これは、特定のデバイスで問題を再現する必要があり、前のガイドに記載されているオプションを使用してもバグを確認できないというイベントで非常に便利です。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools (EdgeHTML)-エミュレーション |Microsoft ドキュメント"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "ブラウザー、画面サイズ、GPS 位置をエミュレートするMicrosoft ドキュメント"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシンをダウンロードする"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "仮想デバイスを作成して管理するAndroid 開発者"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "Android Studio と SDK ツールのダウンロード |Android 開発者"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "Android エミュレーターでアプリを実行する |Android 開発者"  

[AppExperience]: https://www.sigos.com/app-experience/ "アプリのエクスペリエンス"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "シミュレータヘルプ-現在のところ |アップル"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Mac App Store の Xcode"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "応答性の高いデザインモード |MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "Firefox ブラウザーをダウンロードする"  
[SauceLabs]: https://saucelabs.com "ソースラボ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と [Paul Bakaus][PaulBakaus] \ (開いている Web 開発者が Google で支持しています) によって作成されています。ツール、パフォーマンス、アニメーション、UX \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
