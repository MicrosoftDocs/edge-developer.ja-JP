---
description: 仕事は、サイトのパフォーマンスがユーザーと Android の間でMicrosoft Edge終わるものではありません。  デバイス モードでは、iPhone などの他のデバイスの範囲をシミュレートすることができますが、他のブラウザーが提供するエミュレーションのソリューションを確認してください。
title: 他のブラウザーをエミュレートしてテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 22153a54df7c5b92236a745be8e3bbac9a52d247
ms.sourcegitcommit: fa8bedfc83fbd1c4ce7bda8c69586c4f24007beb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11481367"
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
# <a name="emulate-and-test-other-browsers"></a>他のブラウザーをエミュレートしてテストする  

仕事は、サイトのパフォーマンスがユーザーと Android の間でMicrosoft Edge終わるものではありません。  デバイス モードでは、iPhone などの他のデバイスの範囲をシミュレートすることができますが、他のブラウザーが提供するエミュレーションのソリューションを確認してください。  

### <a name="summary"></a>まとめ  

*   特定のデバイスがない場合や、何かのスポット チェックを行う場合は、ブラウザーの内部でデバイスをエミュレートする方法が最適です。  
*   デバイス エミュレーターとシミュレーターを使用すると、ワークステーションからさまざまなデバイスで開発サイトを模倣できます。  
*   クラウドベースのエミュレーターを使用すると、さまざまなプラットフォーム間でサイトの単体テストを自動化できます。  

## <a name="browser-emulators"></a>ブラウザー エミュレーター  

ブラウザー エミュレーターは、サイトの応答性をテストする場合に最適ですが、モバイル ブラウザーに表示される API、CSS サポート、および特定の動作の違いをエミュレートしません。  実際のデバイスで実行されているブラウザーでサイトをテストし、すべてが期待どおりに動作することを確認します。  

### <a name="firefox-responsive-design-view"></a>Firefox レスポンシブ デザイン ビュー  

Firefox には[][MDNResponsiveDesignMode]応答性の高いデザイン ビューが用意されています。これは、特定のデバイスに関する考え方を停止し、代わりに、エッジをドラッグして、一般的な画面サイズや独自のサイズでデザインがどのように変化するかについて説明します。  

### <a name="edgehtml-emulation"></a>EdgeHTML エミュレーション  

電話をWindowsするには、\(EdgeHTML\) 組み込Microsoft Edgeエミュレーションを[使用します][ArchiveMicrosoftEdgeDevtoolsEmulation]。  

[IE 11 エミュレーションを使用][Ie11DevToolsEmulation]して、以前のバージョンのページでのページの外観をシミュレートInternet Explorer。  

## <a name="device-emulators-and-simulators"></a>デバイス エミュレーターとシミュレーター  

デバイス シミュレーターとエミュレーターは、ブラウザー環境だけでなく、デバイス全体をシミュレートします。  それぞれは、仮想キーボードを使用したフォーム入力など、OS の統合が必要なことをテストする場合に役立ちます。  

### <a name="android-emulator"></a>Android エミュレーター  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

現時点では、Android エミュレーターにMicrosoft Edgeをインストールする方法はありません。  ただし、このガイドで後で確認する Android ブラウザー、Chromiumコンテンツ シェル、および Firefox for Android を使用できます。  Chromiumコンテンツ シェルは、Chromiumレンダリング エンジンMicrosoft Edge実行しますが、ブラウザー固有の機能は提供されません。  

Android エミュレーターには、Android Studio の一部としてダウンロードする必要がある [Android SDK が付属しています][AndroidStudioDownload]。  次に、指示に従って [仮想デバイスをセットアップし][AndroidStudioCreateManageVirtualDevices] 、エミュレーター [を起動します][AndroidStudioRunAppsAndroidEmulator]。  
エミュレーターが起動したら、[ブラウザー] アイコンを選択し、Android 用の古いストック ブラウザーでサイトをテストします。  

#### <a name="chromium-content-shell-on-android"></a>Chromium Android のコンテンツ シェル  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

Android 用コンテンツ Chromiumをインストールするには、エミュレーターを実行したままにし、次のコマンドを実行します。  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

これで、コンテンツ シェルを使用してサイトChromiumできます。  

#### <a name="firefox-on-android"></a>Android の Firefox  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

コンテンツ シェルChromium同様に、APK を取得して Firefox をエミュレーターにインストールできます。  

[正しい .apk ファイルをダウンロードします][MozillaFirefoxDownload]。  

開いているエミュレーターまたは接続されている Android デバイスにファイルをインストールするには、次のコマンドを実行します。  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <a name="ios-simulator"></a>iOS シミュレーター  

Mac OS X 用の iOS シミュレーターには、アプリ ストアからインストールする Xcode [が付属しています][MacAppStoreXcode]。  

作業が完了したら、Apple Developer のドキュメントを使用してシミュレーターを使用 [する方法について説明します][AppleSimulatorHelp]。  

> [!NOTE]
> iOS シミュレーターを使用する度に Xcode を開く必要を回避するには、それを開き、ドックの iOS シミュレーター アイコンにカーソルを合わせると、コンテキスト メニュー **** \(右クリック\) を開き、[ドックで保持] を選択します。  必要なときにいつでもアイコンを選択します。  

###  <a name="microsoft-edge-edgehtml"></a>Microsoft Edge (EdgeHTML)  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="最新の IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   最新の IE VM  
:::image-end:::  

Microsoft Edge \(EdgeHTML\) 仮想マシン \(VM\) を使用すると、VirtualBox \(または VMWare\) を介して、コンピューター上のさまざまなバージョンの EdgeHTML と IE にアクセスできます。  ダウンロード ページ [で仮想マシンを選択します][MicrosoftDeveloperEdgeVms]。  

## <a name="cloud-based-emulators-and-simulators"></a>クラウドベースのエミュレーターとシミュレーター  

エミュレーターを使用できない場合、実際のデバイスにアクセスできない場合は、クラウドベースのエミュレーターが次に最適です。  実際のデバイスやローカル エミュレーターに対するクラウドベースのエミュレーターの大きな利点は、さまざまなプラットフォーム間でサイトの単体テストを自動化できるという利点があります。  

*   [BrowserStack (商用) は][|::ref1::|] 、手動テストで最も簡単に使用できます。  オペレーティング システムを選択し、ブラウザーのバージョンとデバイスの種類を選択し、参照する URL を選択すると、操作できるホストされた仮想マシンがスピンアップされます。  同じ画面で複数のエミュレーターを実行して、複数のデバイス間でアプリの外観を同時にテストすることもできます。  
*   [SauceLabs (商用)][SauceLabs] を使用すると、エミュレーター内で単体テストを実行できます。これは、サイト内のフローをスクリプト化し、その後、さまざまなデバイスでビデオ録画を見る場合に役立ちます。  また、サイトで手動テストを行う方法もあります。  
*   [Device Anywhere (商用) は][AppExperience] エミュレーターを使用しませんが、リモートで制御できる実際のデバイスを使用します。  これは、特定のデバイスで問題を再現する必要がある場合や、前のガイドのオプションを使用してバグを表示しない場合に非常に便利です。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[ArchiveMicrosoftEdgeDevtoolsEmulation]: /archive/microsoft-edge/legacy/developer/devtools-guide/emulation "エミュレーション |Microsoft Docs"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "ブラウザー、画面サイズ、および GPS の場所をエミュレート|Microsoft Docs"  

[MicrosoftDeveloperEdgeVms]: https://developer.microsoft.com/microsoft-edge/tools/vms "仮想マシンのダウンロード"  

[AndroidStudioCreateManageVirtualDevices]: https://developer.android.com/tools/devices/managing-avds.html "仮想デバイスの作成と管理|Android 開発者"  
[AndroidStudioDownload]:  https://developer.android.com/sdk/installing/studio.html "Android Studio および SDK ツールをダウンロード|Android 開発者"  
[AndroidStudioRunAppsAndroidEmulator]: https://developer.android.com/tools/devices/emulator.html "Android エミュレーター でアプリを実行|Android 開発者"  

[AppExperience]: https://www.sigos.com/app-experience/ "アプリ エクスペリエンス"  
[AppleSimulatorHelp]: https://help.apple.com/simulator/mac/current "シミュレーター のヘルプ - 現在の|Apple"  
[BrowserStack]: https://www.browserstack.com/automate "BrowserStack"  
[MacAppStoreXcode]: https://itunes.apple.com/app/xcode/id497799835 "Mac アプリ ストアの Xcode"  
[MDNResponsiveDesignMode]: https://developer.mozilla.org/docs/Tools/Responsive_Design_View "レスポンシブ デザイン モードの|MDN"  
[MozillaFirefoxDownload]: https://www.mozilla.org/firefox/all/#product-android-beta "Firefox ブラウザーをダウンロードする"  
[SauceLabs]: https://saucelabs.com "ソース ラボ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)見つかり[、Meggin Kearney][MegginKearney] \(Tech Writer\) と[Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google |ツール、パフォーマンス、アニメーション、UX\)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
