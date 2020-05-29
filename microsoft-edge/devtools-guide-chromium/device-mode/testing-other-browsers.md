---
title: 他のブラウザーをエミュレートしてテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 65ad10ff89d3e4c27abc97cea0eb18b15853dd2e
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607314"
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





# <span data-ttu-id="758a1-103">他のブラウザーをエミュレートしてテストする</span><span class="sxs-lookup"><span data-stu-id="758a1-103">Emulate and Test Other Browsers</span></span>   




<span data-ttu-id="758a1-104">Microsoft Edge と Android でサイトが適切に動作するように、ジョブが終了することはありません。</span><span class="sxs-lookup"><span data-stu-id="758a1-104">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="758a1-105">デバイスモードでは、iPhones などのさまざまなデバイスをシミュレートできますが、他のブラウザーで提供されているエミュレーションのためのソリューションを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="758a1-105">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <span data-ttu-id="758a1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="758a1-106">Summary</span></span>  

*   <span data-ttu-id="758a1-107">特定のデバイスを持っていない場合、または何らかの点でスポットチェックを実行する場合は、ブラウザー内でデバイスをエミュレートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="758a1-107">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="758a1-108">デバイスエミュレーターとシミュレータを使用すると、開発者向けサイトをワークステーションのさまざまなデバイスで模倣できます。</span><span class="sxs-lookup"><span data-stu-id="758a1-108">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="758a1-109">クラウドベースのエミュレーターを使用すると、さまざまなプラットフォームでサイトの単体テストを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="758a1-109">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <span data-ttu-id="758a1-110">ブラウザーエミュレーター</span><span class="sxs-lookup"><span data-stu-id="758a1-110">Browser emulators</span></span>  

<span data-ttu-id="758a1-111">ブラウザーエミュレーターは、サイトの応答性をテストするのに適していますが、API、CSS のサポート、モバイルブラウザーで表示される特定の動作の違いをエミュレートすることはありません。</span><span class="sxs-lookup"><span data-stu-id="758a1-111">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that you see on a mobile browser.</span></span>  <span data-ttu-id="758a1-112">実際のデバイスで実行されているブラウザーでサイトをテストして、すべてが予期したとおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="758a1-112">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <span data-ttu-id="758a1-113">Firefox の応答性の高いデザインビュー</span><span class="sxs-lookup"><span data-stu-id="758a1-113">Firefox Responsive Design View</span></span>  

<span data-ttu-id="758a1-114">Firefox には、特定のデバイスについて検討することをお勧めする、[応答性の高いデザインビュー][MDNResponsiveDesignMode]が用意されています。また、端をドラッグすることで、一般的な画面サイズまたは独自のサイズでデザインがどのように変化するかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="758a1-114">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <span data-ttu-id="758a1-115">EdgeHTML エミュレーション</span><span class="sxs-lookup"><span data-stu-id="758a1-115">EdgeHTML Emulation</span></span>  

<span data-ttu-id="758a1-116">Windows Phone をエミュレートするには、Microsoft Edge \ (EdgeHTML \)[ビルトインエミュレーション][DevToolsEdgeHtmlEmulation]を使用します。</span><span class="sxs-lookup"><span data-stu-id="758a1-116">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][DevToolsEdgeHtmlEmulation].</span></span>  

<span data-ttu-id="758a1-117">Internet Explorer の以前のバージョンでページがどのように表示されるかをシミュレートするには、 [IE 11 エミュレーション][Ie11DevToolsEmulation]を使用します。</span><span class="sxs-lookup"><span data-stu-id="758a1-117">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <span data-ttu-id="758a1-118">デバイスエミュレーターとシミュレータ</span><span class="sxs-lookup"><span data-stu-id="758a1-118">Device emulators and simulators</span></span>  

<span data-ttu-id="758a1-119">デバイスシミュレータとエミュレーターは、ブラウザー環境だけでなく、デバイス全体をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="758a1-119">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="758a1-120">各機能は、OS の統合を必要とするものをテストするのに役立ちます。たとえば、仮想キーボードを使用したフォーム入力です。</span><span class="sxs-lookup"><span data-stu-id="758a1-120">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <span data-ttu-id="758a1-121">Android エミュレーター</span><span class="sxs-lookup"><span data-stu-id="758a1-121">Android Emulator</span></span>  

<!--
> ##### Figure old 1  
> Stock Browser in Android Emulator  
> ![Stock Browser in Android Emulator][ImageAndroidEmulatorStockBrowser]  
-->

<span data-ttu-id="758a1-122">現時点では、Android エミュレーターに Microsoft Edge をインストールする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="758a1-122">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="758a1-123">ただし、Android ブラウザー、Chromium Content Shell、Android 用 Firefox は、このガイドの後半で確認することができます。</span><span class="sxs-lookup"><span data-stu-id="758a1-123">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="758a1-124">Chromium Content Shell は Microsoft Edge と同じ Chromium レンダリングエンジンを実行しますが、ブラウザー固有の機能はありません。</span><span class="sxs-lookup"><span data-stu-id="758a1-124">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="758a1-125">Android エミュレーターには、android [Studio][AndroidStudioDownload]の一部としてダウンロードする必要がある android SDK が付属しています。</span><span class="sxs-lookup"><span data-stu-id="758a1-125">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="758a1-126">次に、指示に従って[仮想デバイス][AndroidStudioCreateManageVirtualDevices]をセットアップし、[エミュレーターを開始][AndroidStudioRunAppsAndroidEmulator]します。</span><span class="sxs-lookup"><span data-stu-id="758a1-126">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="758a1-127">エミュレーターが起動したら、ブラウザーアイコンをクリックして、Android 用の古いストックブラウザーでサイトをテストします。</span><span class="sxs-lookup"><span data-stu-id="758a1-127">Once your emulator is booted, click on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <span data-ttu-id="758a1-128">Android での Chromium コンテンツシェル</span><span class="sxs-lookup"><span data-stu-id="758a1-128">Chromium Content Shell on Android</span></span>  

<!--
> ##### Figure old 2  
> Android Emulator Content Shell  
> ![Android Emulator Content Shell][ImageAndroidEmulatorContentShell]  
-->

<span data-ttu-id="758a1-129">Android 用の Chromium Content Shell をインストールするには、エミュレーターを実行したまま、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="758a1-129">To install the Chromium Content Shell for Android, leave your emulator running and run the following commands at a command prompt:</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="758a1-130">これで、Chromium Content Shell を使ってサイトをテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="758a1-130">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <span data-ttu-id="758a1-131">Android の Firefox</span><span class="sxs-lookup"><span data-stu-id="758a1-131">Firefox on Android</span></span>  

<!--
> ##### Figure old 3  
> Firefox Icon on Android Emulator  
> ![Firefox Icon on Android Emulator][ImageAndroidEmulatorFirefoxBrowser]  
-->

<span data-ttu-id="758a1-132">Chromium Content Shell と同様に、Firefox をエミュレーターにインストールするための APK を取得できます。</span><span class="sxs-lookup"><span data-stu-id="758a1-132">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="758a1-133">[適切な apk ファイルをダウンロード][MozillaFirefoxDownload]します。</span><span class="sxs-lookup"><span data-stu-id="758a1-133">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="758a1-134">ここでは、次のコマンドを使用して、開いているエミュレーターまたは接続されている Android デバイスにファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="758a1-134">From here, you are able to install the file onto an open emulator or connected Android device with the following command:</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <span data-ttu-id="758a1-135">iOS シミュレータ</span><span class="sxs-lookup"><span data-stu-id="758a1-135">iOS Simulator</span></span>  

<span data-ttu-id="758a1-136">IOS シミュレータ for Mac OS X には Xcode が付属しています。このアプリは、 [App Store からインストール][MacAppStoreXcode]します。</span><span class="sxs-lookup"><span data-stu-id="758a1-136">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="758a1-137">完了したら、 [Apple 開発者向けドキュメント][AppleSimulatorHelp]でシミュレータを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="758a1-137">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="758a1-138">IOS シミュレータを使用するたびに Xcode を開く必要がないようにするには、そのまま開き、dock の iOS シミュレータアイコンを右クリックして、[ **dock に保持**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="758a1-138">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, then right-click the iOS Simulator icon in your dock and select **Keep in Dock**.</span></span>  <span data-ttu-id="758a1-139">次に、必要なときにこのアイコンをクリックするだけです。</span><span class="sxs-lookup"><span data-stu-id="758a1-139">Now just click this icon whenever you need it.</span></span>  

###  <span data-ttu-id="758a1-140">Microsoft Edge (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="758a1-140">Microsoft Edge (EdgeHTML)</span></span>  

> ##### <span data-ttu-id="758a1-141">図 1</span><span class="sxs-lookup"><span data-stu-id="758a1-141">Figure 1</span></span>  
> <span data-ttu-id="758a1-142">モダン IE VM</span><span class="sxs-lookup"><span data-stu-id="758a1-142">Modern IE VM</span></span>  
> <span data-ttu-id="758a1-143">![モダン IE VM][ImageVMModernIe]</span><span class="sxs-lookup"><span data-stu-id="758a1-143">![Modern IE VM][ImageVMModernIe]</span></span>  

<span data-ttu-id="758a1-144">Microsoft Edge \ (EdgeHTML \) 仮想マシン \ (Vm \) を使用すると、VirtualBox \ (または VMWare \) を介してコンピューター上のさまざまなバージョンの EdgeHTML と IE にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="758a1-144">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="758a1-145">[ダウンロードページで仮想マシン][MicrosoftDeveloperEdgeVms]を選択します。</span><span class="sxs-lookup"><span data-stu-id="758a1-145">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <span data-ttu-id="758a1-146">クラウドベースのエミュレーターとシミュレータ</span><span class="sxs-lookup"><span data-stu-id="758a1-146">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="758a1-147">エミュレーターを使うことができず、実際のデバイスにアクセスできない場合は、クラウドベースのエミュレーターを使用するのが最適です。</span><span class="sxs-lookup"><span data-stu-id="758a1-147">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="758a1-148">実際のデバイスとローカルエミュレーターによるクラウドベースのエミュレーターの大きな利点は、さまざまなプラットフォームでサイトの単体テストを自動化できることです。</span><span class="sxs-lookup"><span data-stu-id="758a1-148">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="758a1-149">[Browserstack (商用)][|::ref1::|]は、手動テストで最も簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="758a1-149">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="758a1-150">オペレーティングシステムを選択して、使用しているブラウザーのバージョンとデバイスの種類を選択します。参照する URL を選択すると、対話できるホストされた仮想マシンが回転します。</span><span class="sxs-lookup"><span data-stu-id="758a1-150">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="758a1-151">また、同じ画面で複数のエミュレーターを実行できるため、複数のデバイスで同時にアプリの外観をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="758a1-151">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="758a1-152">[SauceLabs (商用)][SauceLabs]では、エミュレーターの内部で単体テストを実行できます。この機能は、サイト内でのフローのスクリプトを作成し、後でさまざまなデバイスでその後のビデオ録画を監視する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="758a1-152">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="758a1-153">サイトで手動テストを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="758a1-153">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="758a1-154">[任意のデバイス (商用)][AppExperience]では、リモートで制御できるエミュレーターである実際のデバイスは使用されません。</span><span class="sxs-lookup"><span data-stu-id="758a1-154">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="758a1-155">これは、特定のデバイスで問題を再現する必要があり、前のガイドに記載されているオプションを使用してもバグを確認できないというイベントで非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="758a1-155">This is very useful in the event where you need to reproduce a problem on a specific device and are not able to see the bug using any of the options in the previous guides.</span></span>  

 



<!-- image links -->  

<!--[ImageAndroidEmulatorStockBrowser]: /microsoft-edge/devtools-guide-chromium/media/device-mode-android-emulator-stock-browser.msft.png "Figure old 1: Stock Browser in Android Emulator"  -->  
<!--[ImageAndroidEmulatorContentShell]: /microsoft-edge/devtools-guide-chromium/media/device-mode-android-avd-contentshell.msft.png "Figure old 2: Android Emulator Content Shell"  -->  
<!--[ImageAndroidEmulatorFirefoxBrowser]: /microsoft-edge/devtools-guide-chromium/media/device-mode-ff-on-android-emulator.msft.png "Figure old 3: Firefox Icon on Android Emulator"  -->  
[ImageVMModernIe]:/microsoft-edge/devtools-guide-chromium/media/device-mode-modern-ie-vm.msft.png "図 1: モダン IE VM"  

<!-- links -->  

[DevToolsEdgeHtmlEmulation]: /microsoft-edge/devtools-guide/emulation "DevTools (EdgeHTML)-エミュレーション"  

[Ie11DevToolsEmulation]: /previous-versions/windows/internet-explorer/ie-developer/samples/dn255001(v=vs.85) "ブラウザー、画面サイズ、GPS 位置をエミュレートする"  

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
> <span data-ttu-id="758a1-170">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="758a1-170">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="758a1-171">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と[Paul Bakaus][PaulBakaus] \ (開いている Web 開発者が Google で支持しています) によって作成されています。ツール、パフォーマンス、アニメーション、UX \)。</span><span class="sxs-lookup"><span data-stu-id="758a1-171">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="758a1-173">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="758a1-173">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors/pbakaus  
