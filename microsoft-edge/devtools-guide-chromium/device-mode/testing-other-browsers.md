---
description: 仕事は、サイトのパフォーマンスがユーザーと Android の間でMicrosoft Edge終わるものではありません。  デバイス モードでは、iPhone などの他のデバイスの範囲をシミュレートすることができますが、他のブラウザーが提供するエミュレーションのソリューションを確認してください。
title: 他のブラウザーをエミュレートしてテストする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f2ca56c2e15f578a970e6ceb84b1554bfda53862
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564281"
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
# <a name="emulate-and-test-other-browsers"></a><span data-ttu-id="fdb19-105">他のブラウザーをエミュレートしてテストする</span><span class="sxs-lookup"><span data-stu-id="fdb19-105">Emulate and test other browsers</span></span>  

<span data-ttu-id="fdb19-106">仕事は、サイトのパフォーマンスがユーザーと Android の間でMicrosoft Edge終わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="fdb19-106">Your job does not end with ensuring your site runs great across Microsoft Edge and Android.</span></span>  <span data-ttu-id="fdb19-107">デバイス モードでは、iPhone などの他のデバイスの範囲をシミュレートすることができますが、他のブラウザーが提供するエミュレーションのソリューションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fdb19-107">Even though Device Mode is able to simulate a range of other devices like iPhones, we encourage you to check out solutions for emulation provided by other browsers.</span></span>  

### <a name="summary"></a><span data-ttu-id="fdb19-108">要約</span><span class="sxs-lookup"><span data-stu-id="fdb19-108">Summary</span></span>  

*   <span data-ttu-id="fdb19-109">特定のデバイスがない場合や、何かのスポット チェックを行う場合は、ブラウザーの内部でデバイスをエミュレートする方法が最適です。</span><span class="sxs-lookup"><span data-stu-id="fdb19-109">When you do not have a particular device, or want to do a spot check on something, the best option is to emulate the device right inside your browser.</span></span>  
*   <span data-ttu-id="fdb19-110">デバイス エミュレーターとシミュレーターを使用すると、ワークステーションからさまざまなデバイスで開発サイトを模倣できます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-110">Device emulators and simulators enable you to mimic your development site on a range of devices from your workstation.</span></span>  
*   <span data-ttu-id="fdb19-111">クラウドベースのエミュレーターを使用すると、さまざまなプラットフォーム間でサイトの単体テストを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-111">Cloud-based emulators enable you to automate unit tests for your site across different platforms.</span></span>  

## <a name="browser-emulators"></a><span data-ttu-id="fdb19-112">ブラウザー エミュレーター</span><span class="sxs-lookup"><span data-stu-id="fdb19-112">Browser emulators</span></span>  

<span data-ttu-id="fdb19-113">ブラウザー エミュレーターは、サイトの応答性をテストする場合に最適ですが、モバイル ブラウザーに表示される API、CSS サポート、および特定の動作の違いをエミュレートしません。</span><span class="sxs-lookup"><span data-stu-id="fdb19-113">Browser emulators are great for testing the responsiveness of a site, but each does not emulate differences in API, CSS support, and certain behaviors that is displayed on a mobile browser.</span></span>  <span data-ttu-id="fdb19-114">実際のデバイスで実行されているブラウザーでサイトをテストし、すべてが期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-114">Test your site on browsers running on real devices to be certain everything behaves as expected.</span></span>  

### <a name="firefox-responsive-design-view"></a><span data-ttu-id="fdb19-115">Firefox レスポンシブ デザイン ビュー</span><span class="sxs-lookup"><span data-stu-id="fdb19-115">Firefox Responsive Design View</span></span>  

<span data-ttu-id="fdb19-116">Firefox には[][MDNResponsiveDesignMode]応答性の高いデザイン ビューが用意されています。これは、特定のデバイスに関する考え方を停止し、代わりに、エッジをドラッグして、一般的な画面サイズや独自のサイズでデザインがどのように変化するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-116">Firefox has a [responsive design view][MDNResponsiveDesignMode] that encourages you to stop thinking in terms of specific devices and instead explore how your design changes at common screen sizes or your own size by dragging the edges.</span></span>  

### <a name="edgehtml-emulation"></a><span data-ttu-id="fdb19-117">EdgeHTML エミュレーション</span><span class="sxs-lookup"><span data-stu-id="fdb19-117">EdgeHTML emulation</span></span>  

<span data-ttu-id="fdb19-118">電話をWindowsするには、\(EdgeHTML\) 組み込Microsoft Edgeエミュレーションを[使用します][ArchiveMicrosoftEdgeDevtoolsEmulation]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-118">To emulate Windows Phones, use the Microsoft Edge \(EdgeHTML\) [built-in emulation][ArchiveMicrosoftEdgeDevtoolsEmulation].</span></span>  

<span data-ttu-id="fdb19-119">[IE 11 エミュレーションを使用][Ie11DevToolsEmulation]して、以前のバージョンのページでのページの外観をシミュレートInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="fdb19-119">Use [IE 11 Emulation][Ie11DevToolsEmulation] to simulate how your page may look in older versions of Internet Explorer.</span></span>  

## <a name="device-emulators-and-simulators"></a><span data-ttu-id="fdb19-120">デバイス エミュレーターとシミュレーター</span><span class="sxs-lookup"><span data-stu-id="fdb19-120">Device emulators and simulators</span></span>  

<span data-ttu-id="fdb19-121">デバイス シミュレーターとエミュレーターは、ブラウザー環境だけでなく、デバイス全体をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="fdb19-121">Device simulators and emulators simulate not just the browser environment but the entire device.</span></span>  <span data-ttu-id="fdb19-122">それぞれは、仮想キーボードを使用したフォーム入力など、OS の統合が必要なことをテストする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-122">Each are useful to test things that require OS integration, for example form input with virtual keyboards.</span></span>  

### <a name="android-emulator"></a><span data-ttu-id="fdb19-123">Android エミュレーター</span><span class="sxs-lookup"><span data-stu-id="fdb19-123">Android emulator</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-emulator-stock-browser.msft.png" alt-text="Stock Browser in Android Emulator" lightbox="../media/device-mode-android-emulator-stock-browser.msft.png":::
   Stock Browser in Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="fdb19-124">現時点では、Android エミュレーターにMicrosoft Edgeをインストールする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="fdb19-124">At the moment, there is no way to install Microsoft Edge on an Android emulator.</span></span>  <span data-ttu-id="fdb19-125">ただし、このガイドで後で確認する Android ブラウザー、Chromiumコンテンツ シェル、および Firefox for Android を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-125">However, you may use the Android Browser, the Chromium Content Shell, and Firefox for Android which we review later in this guide.</span></span>  <span data-ttu-id="fdb19-126">Chromiumコンテンツ シェルは、Chromiumレンダリング エンジンMicrosoft Edge実行しますが、ブラウザー固有の機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="fdb19-126">Chromium Content Shell runs the same Chromium rendering engine as Microsoft Edge, but comes without any of the browser specific features.</span></span>  

<span data-ttu-id="fdb19-127">Android エミュレーターには、Android Studio の一部としてダウンロードする必要がある [Android SDK が付属しています][AndroidStudioDownload]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-127">The Android emulator comes with the Android SDK which you need to download as part of [Android Studio][AndroidStudioDownload].</span></span>  <span data-ttu-id="fdb19-128">次に、指示に従って [仮想デバイスをセットアップし][AndroidStudioCreateManageVirtualDevices] 、エミュレーター [を起動します][AndroidStudioRunAppsAndroidEmulator]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-128">Then follow the instructions to [set up a virtual device][AndroidStudioCreateManageVirtualDevices] and [start the emulator][AndroidStudioRunAppsAndroidEmulator].</span></span>  
<span data-ttu-id="fdb19-129">エミュレーターが起動したら、[ブラウザー] アイコンを選択し、Android 用の古いストック ブラウザーでサイトをテストします。</span><span class="sxs-lookup"><span data-stu-id="fdb19-129">Once your emulator is booted, choose on the Browser icon, and test your site on the old Stock Browser for Android.</span></span>  

#### <a name="chromium-content-shell-on-android"></a><span data-ttu-id="fdb19-130">Chromium Android のコンテンツ シェル</span><span class="sxs-lookup"><span data-stu-id="fdb19-130">Chromium content shell on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-android-avd-contentshell.msft.png" alt-text="Android Emulator Content Shell" lightbox="../media/device-mode-android-avd-contentshell.msft.png":::
   Android Emulator Content Shell  
:::image-end:::  
-->  

<span data-ttu-id="fdb19-131">Android 用コンテンツ Chromiumをインストールするには、エミュレーターを実行したままにし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-131">To install the Chromium Content Shell for Android, leave your emulator running and run the following command.</span></span>  

```shell
git clone https://github.com/PaulKinlan/chromium-android-installer.git
chmod u+x ./chromium-android-installer/*.sh
./chromium-android-installer/install-chromeandroid.sh
```  

<span data-ttu-id="fdb19-132">これで、コンテンツ シェルを使用してサイトChromiumできます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-132">Now you are able to test your site with the Chromium Content Shell.</span></span>  

#### <a name="firefox-on-android"></a><span data-ttu-id="fdb19-133">Android の Firefox</span><span class="sxs-lookup"><span data-stu-id="fdb19-133">Firefox on Android</span></span>  

<!--  
:::image type="complex" source="../media/device-mode-ff-on-android-emulator.msft.png" alt-text="Firefox Icon on Android Emulator" lightbox="../media/device-mode-ff-on-android-emulator.msft.png":::
   Firefox Icon on Android Emulator  
:::image-end:::  
-->  

<span data-ttu-id="fdb19-134">コンテンツ シェルChromium同様に、APK を取得して Firefox をエミュレーターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-134">Similar to the Chromium Content Shell, you are able to get an APK to install Firefox onto the emulator.</span></span>  

<span data-ttu-id="fdb19-135">[正しい .apk ファイルをダウンロードします][MozillaFirefoxDownload]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-135">[Download the correct .apk file][MozillaFirefoxDownload].</span></span>  

<span data-ttu-id="fdb19-136">開いているエミュレーターまたは接続されている Android デバイスにファイルをインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-136">To install the file onto an open emulator or connected Android device, run the following command.</span></span>  

```shell
adb install <path_to_APK>/fennec-XX.X.XX.android-arm.apk
```  

### <a name="ios-simulator"></a><span data-ttu-id="fdb19-137">iOS シミュレーター</span><span class="sxs-lookup"><span data-stu-id="fdb19-137">iOS simulator</span></span>  

<span data-ttu-id="fdb19-138">Mac OS X 用の iOS シミュレーターには、アプリ ストアからインストールする Xcode [が付属しています][MacAppStoreXcode]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-138">The iOS simulator for Mac OS X comes with Xcode, which you [install from the App Store][MacAppStoreXcode].</span></span>  

<span data-ttu-id="fdb19-139">作業が完了したら、Apple Developer のドキュメントを使用してシミュレーターを使用 [する方法について説明します][AppleSimulatorHelp]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-139">When you are done, learn how to work with the simulator through [Apple Developer documentation][AppleSimulatorHelp].</span></span>  

> [!NOTE]
> <span data-ttu-id="fdb19-140">iOS シミュレーターを使用する度に Xcode を開く必要を回避するには、それを開き、ドックの iOS シミュレーター アイコンにカーソルを合わせると、コンテキスト メニュー \*\*\*\* \(右クリック\) を開き、[ドックで保持] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-140">To avoid having to open Xcode every time you want to use the iOS Simulator, open it, hover on the iOS Simulator icon in your dock, open the contextual menu \(right-click\), and choose **Keep in Dock**.</span></span>  <span data-ttu-id="fdb19-141">必要なときにいつでもアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-141">Now just choose the icon whenever you need it.</span></span>  

###  <a name="microsoft-edge-edgehtml"></a><span data-ttu-id="fdb19-142">Microsoft Edge (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="fdb19-142">Microsoft Edge (EdgeHTML)</span></span>  

:::image type="complex" source="../media/device-mode-modern-ie-vm.msft.png" alt-text="最新の IE VM" lightbox="../media/device-mode-modern-ie-vm.msft.png":::
   <span data-ttu-id="fdb19-144">最新の IE VM</span><span class="sxs-lookup"><span data-stu-id="fdb19-144">Modern IE VM</span></span>  
:::image-end:::  

<span data-ttu-id="fdb19-145">Microsoft Edge \(EdgeHTML\) 仮想マシン \(VM\) を使用すると、VirtualBox \(または VMWare\) を介して、コンピューター上のさまざまなバージョンの EdgeHTML と IE にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-145">Microsoft Edge \(EdgeHTML\) Virtual Machines \(VMs\) enable you to access different versions of EdgeHTML and IE on your computer via VirtualBox \(or VMWare\).</span></span>  <span data-ttu-id="fdb19-146">ダウンロード ページ [で仮想マシンを選択します][MicrosoftDeveloperEdgeVms]。</span><span class="sxs-lookup"><span data-stu-id="fdb19-146">Choose a [virtual machine on the download page][MicrosoftDeveloperEdgeVms].</span></span>  

## <a name="cloud-based-emulators-and-simulators"></a><span data-ttu-id="fdb19-147">クラウドベースのエミュレーターとシミュレーター</span><span class="sxs-lookup"><span data-stu-id="fdb19-147">Cloud-based emulators and simulators</span></span>  

<span data-ttu-id="fdb19-148">エミュレーターを使用できない場合、実際のデバイスにアクセスできない場合は、クラウドベースのエミュレーターが次に最適です。</span><span class="sxs-lookup"><span data-stu-id="fdb19-148">If you are not able to use the emulators and do not have access to real devices, then cloud-based emulators are the next best thing.</span></span>  <span data-ttu-id="fdb19-149">実際のデバイスやローカル エミュレーターに対するクラウドベースのエミュレーターの大きな利点は、さまざまなプラットフォーム間でサイトの単体テストを自動化できるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="fdb19-149">A big advantage of cloud-based emulators over real devices and local emulators is that you are able to automate unit tests for your site across different platforms.</span></span>  

*   <span data-ttu-id="fdb19-150">[BrowserStack (商用) は][|::ref1::|] 、手動テストで最も簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-150">[BrowserStack (commercial)][|::ref1::|] is the easiest to use for manual testing.</span></span>  <span data-ttu-id="fdb19-151">オペレーティング システムを選択し、ブラウザーのバージョンとデバイスの種類を選択し、参照する URL を選択すると、操作できるホストされた仮想マシンがスピンアップされます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-151">You select an operating system, select your browser version and device type, select a URL to browse, and it spins up a hosted virtual machine with which you may interact.</span></span>  <span data-ttu-id="fdb19-152">同じ画面で複数のエミュレーターを実行して、複数のデバイス間でアプリの外観を同時にテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-152">You are able to also run multiple emulators in the same screen, enabling you to test the look and feel of your app across multiple devices at the same time.</span></span>  
*   <span data-ttu-id="fdb19-153">[SauceLabs (商用)][SauceLabs] を使用すると、エミュレーター内で単体テストを実行できます。これは、サイト内のフローをスクリプト化し、その後、さまざまなデバイスでビデオ録画を見る場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fdb19-153">[SauceLabs (commercial)][SauceLabs] enables you to run unit tests inside of an emulator, which may be really useful for scripting a flow through your site and watching the video recording of this afterwards on various devices.</span></span>  <span data-ttu-id="fdb19-154">また、サイトで手動テストを行う方法もあります。</span><span class="sxs-lookup"><span data-stu-id="fdb19-154">You are also able to do manual testing with your site.</span></span>  
*   <span data-ttu-id="fdb19-155">[Device Anywhere (商用) は][AppExperience] エミュレーターを使用しませんが、リモートで制御できる実際のデバイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fdb19-155">[Device Anywhere (commercial)][AppExperience] does not use emulators but real devices which you are able to control remotely.</span></span>  <span data-ttu-id="fdb19-156">これは、特定のデバイスで問題を再現する必要がある場合や、前のガイドのオプションを使用してバグを表示しない場合に非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="fdb19-156">This is very useful in the event where you need to reproduce a problem on a specific device and may not display the bug using any of the options in the previous guides.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="fdb19-157">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="fdb19-157">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="fdb19-171">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="fdb19-171">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fdb19-172">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers)見つかり[、Meggin Kearney][MegginKearney] \(Tech Writer\) と[Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google |ツール、パフォーマンス、アニメーション、UX\)。</span><span class="sxs-lookup"><span data-stu-id="fdb19-172">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/testing-other-browsers) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Paul Bakaus][PaulBakaus] \(Open Web Developer Advocate at Google | Tools, Performance, Animation, UX\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="fdb19-174">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="fdb19-174">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
[PaulBakaus]: https://developers.google.com/web/resources/contributors#paul-bakaus  
