---
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a9002ca82e6e0dcaf7f174b336e5c640929a561b
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611820"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  




<!--
<style>
.devtools-inline {
  max-height: 1em;
  vertical-align: middle;
}
</style>
-->  
# Android デバイスのリモートデバッグの概要   



Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。  このチュートリアルでは、次の方法について説明します。  

*   リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。  
*   開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。  
*   Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。  

<!--
> ##### Figure 1  
> Remote Debugging lets you inspect a page running on an Android device from your development machine  
> ![Remote Debugging lets you inspect a page running on an Android device from your development machine][ImageRemoteDebugging]  -->

## 手順 1: Android デバイスを見つける   

以下のワークフローは、ほとんどのユーザーに適しています。  詳細について[は、「開発ツールで Android デバイスが検出されない](#troubleshooting-devtools-is-not-detecting-the-android-device)」を参照してください。  

1.  Android で [**開発者向けオプション**] 画面を開きます。  「[デバイス開発者向けオプションを構成する」を](https://developer.android.com/studio/debug/dev-options.html)参照してください。  
1.  [ **USB デバッグを有効にする**] を選びます。  
1.  開発用コンピューターで、Microsoft Edge を開きます。  
1.  [DevTools を開き][DevToolsOpen]ます。  
1.  Devtools で、**メインメニュー**を選択して、 `...` 「**その他のツール**」「  >  **リモートデバイス**」を選択します。  
    
    > ##### 図 1  
    > **メインメニュー**から [**リモートデバイス**] タブを開く  
    > ![リモートデバイス] タブを開くには、メインメニューから[ImageOpenRemoteDevices]  

1.  DevTools で、[**設定**] タブを開きます。  

1.  [ **USB デバイスの検出**] チェックボックスがオンになっていることを確認します。  
    
    > ##### 図 2  
    > [ **USB デバイスの検出**] チェックボックスがオンになっている  
    > ![USB デバイスの検出] チェックボックスがオンになっている[ImageDiscoverUSBDevices]  

1.  USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。  この操作を初めて行うときは、DevTools で不明なデバイスが検出されたことを確認してください。  Android デバイスのモデル名の下に緑色のドットとテキストが**接続さ**れている場合は、devtools でデバイスへの接続が正常に確立されています。  [手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)に進みます。  
    <!--
    > ##### Figure 4  
    > The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    > ![The Remote Devices tab has successfully detected an unknown device that is pending authorization][ImageUnknownDevice]  -->

1.  デバイスが**不明**と表示されている場合は、Android デバイスで [ **USB デバッグの許可**] プロンプトを受け入れます。  

### トラブルシューティング: DevTools で Android デバイスが検出されない   

ハードウェアが正しく設定されていることを確認してください。  

*   USB ハブを使っている場合は、代わりに Android デバイスを開発用コンピューターに直接接続してみてください。  
*   Android デバイスと開発マシンの間で USB ケーブルを外してから、もう一度接続してみてください。  Android および開発マシンの画面のロックが解除されている間に、この操作を行います。  
*   USB ケーブルが動作していることを確認してください。  開発用コンピューターから Android デバイスのファイルを検査できる必要があります。  

ソフトウェアが正しく設定されていることを確認してください。  

*   開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。  「 [OEM USB ドライバーをインストール][AndroidUSBDrivers]する」を参照してください。  
    
*   Windows と Android デバイス (特に Samsung) の一部の組み合わせでは、追加の設定が必要です。  「[StackOverflowDevicesNotDetected] に接続してもデバイスが検出されない」を参照してください。  
    
Android デバイスで**USB のデバッグを許可**するかどうかを確認するメッセージが表示されない場合は、次の操作を行います。  

*   DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。  つまり、Android または開発機の画面がロックされているときに、プロンプトが表示されないことがあります。
*   Android デバイスと開発用コンピューターの表示設定を更新して、スリープ状態に移動しないようにします。  
*   Android の USB モードを PTP に設定します。  「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない」を][StackExchangeGalaxyS4DoesNotShowDialogBox]参照してください。  
*   Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。  

このセクションで説明されていない解決策、または [StackOverflowDevicesNotDetected] に接続しているときに、デバイスがデバイスを検出しない場合、またはそのスタックオーバーフローの質問に回答を追加してください。<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->!  

## 手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする   

1.  Android デバイスで Microsoft Edge を開きます。  

1.  [**リモートデバイス**] タブで、Android デバイスモデル名に一致するタブを選択します。  
    このページの上部には、Android デバイスのモデル名に続いて、そのシリアル番号が表示されています。  その下で、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれていることが確認できます。  開かれている Microsoft Edge タブごとに、独自のセクションが表示されます。  このセクションでは、このタブを操作できます。  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->
    <!--
    > ##### Figure 5  
    > A connected remote device  
    > ![A connected remote device][ImageConnectedRemoteDevice]  -->

1.  [**新しいタブ**テキスト] ボックスに URL を入力し、[**開く**] を選択します。  Android デバイスの新しいタブにページが表示されます。  

1.  直前に開いた URL の横にある [**検査**] を選択します。  新しい DevTools インスタンスが開きます。  Android デバイス上で実行されている Microsoft Edge のバージョンによって、開発用コンピューターで開く DevTools のバージョンが決まります。  
    Android デバイスで古いバージョンの Microsoft Edge が実行されている場合、DevTools インスタンスは、使用しているものとは大幅に異なる場合があります。  

### その他のアクション: タブを再読み込み、フォーカス、または閉じる   

**More Options** `...` 再読み込み、フォーカス、または閉じるタブの隣にある [その他のオプション] を選択します。  
<!--
> ##### Figure 6  
> The menu for reloading, focusing, or closing a tab  
> ![The menu for reloading, focusing, or closing a tab][ImageReload]  -->

### 要素を検査する   

DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。  

Android デバイスの画面で要素を選択して、[**要素**] パネルで選ぶこともできます。  DevTools インスタンスで [**要素**の選択] を選択し ![ ][ImageSelectElementIcon] 、Android デバイス画面で要素を選択します。  

> [!NOTE]
> 最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。  

### Android の画面を開発用コンピューターに Screencast   

[**トグル Screencast**トグル Screencast] を選択して、 ![ ][ImageToggleScreencastIcon] Devtools インスタンスで Android デバイスのコンテンツを表示します。  

Screencast はさまざまな方法で操作できます。  

*   クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。  
*   コンピューターのキーボード操作がデバイスに送信されます。  
*   ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。  
*   スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。

スクリーンキャストに関する注意事項:  

*   スクリーンキャストは、ページコンテンツを表示します。  Screencast の透明部分は、Microsoft Edge のアドレスバー、Android ステータスバー、Android キーボードなどのデバイスインターフェイスを表します。  
*   スクリーンキャストはフレームレートに悪影響を与えます。  スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。  
*   Android デバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。  Android デバイスの画面のロックを解除して、screencast を自動的に再開します。  





<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
[ImageOpenRemoteDevices]:/microsoft-edge/devtools-guide-chromium/media/remote-debugging-more-tools-remote-devices.msft.png "図 1: メインメニューから [リモートデバイス] タブを開く"  
[ImageDiscoverUSBDevices]:/microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-tab.msft.png "図 2: [USB デバイスの検出] チェックボックスがオンになっている  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--connected-remote-device.msft.png "old Figure 5:  A connected remote device"  -->
<!--[ImageReload]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--reload.msft.png "old Figure 6: The menu for reloading, focusing, or closing a tab"  -->

<!-- links -->  

[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "Microsoft Edge DevTools を開く"  

[AndroidUSBDrivers]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストールする |Android 開発者"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  
[StackOverflowDevicesNotDetected]: https://stackoverflow.com/questions/21925992 "devtools デバイスで、電源に接続されているときにデバイスが検出されません"-スタックオーバーフロー "  

[StackExchangeGalaxyS4DoesNotShowDialogBox]: https://android.stackexchange.com/questions/101933 "adb-Android ファンスタック交換"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
