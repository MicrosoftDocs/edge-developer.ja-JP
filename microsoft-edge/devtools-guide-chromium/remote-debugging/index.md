---
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fc7450ba2b088eee8f4005216374980096cbb067
ms.sourcegitcommit: ba9f0ed77e84174b03262b17e62c6a7e26cfeb3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2020
ms.locfileid: "10688160"
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

# Android デバイスのリモートデバッグの概要  

Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。  このチュートリアルページでは、次の操作を実行する方法について説明します。  

*   リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。  
*   開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。  
*   Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

## 手順 1: Android デバイスを見つける  

以下のワークフローは、ほとんどのユーザーに適しています。  詳細について[は、「開発ツールで Android デバイスが検出されない](#troubleshooting-devtools-is-not-detecting-the-android-device)」を参照してください。  

1.  Android で [**開発者向けオプション**] 画面を開きます。  詳細については、「[デバイスの開発者向けオプションを構成する](https://developer.android.com/studio/debug/dev-options.html)」を参照してください。  
1.  [ **USB デバッグを有効にする**] を選びます。  
1.  開発用コンピューターで、Microsoft Edge を開きます。  
1.  `edge://inspect`Microsoft Edge でページに移動します。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge の [edge://inspect] ページ" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       図 1.   `edge://inspect`Microsoft Edge のページ  
    :::image-end:::  
    
1.  USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。  初めて接続しようとしたときに、一般的に、不明なデバイスを検出するための DevTools のプロンプトが表示されます。  Android デバイスで [ **USB のデバッグを許可**] プロンプトを承諾します。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android デバイスでの USB デバッグの許可プロンプト" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       図 2.   Android デバイスでの**USB デバッグ**の許可プロンプト  
    :::image-end:::  
    
1.  Android デバイスのモデル名が表示される場合は、Microsoft Edge でデバイスへの接続が正常に確立されていることを確認します。  [手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)に進みます。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### トラブルシューティング: DevTools で Android デバイスが検出されない  

以下のヒントは、お使いのハードウェアの適切な設定のトラブルシューティングに役立ちます。  

*   USB ハブを使っている場合は、Android デバイスを開発用コンピューターに直接接続してみてください。  
*   Android デバイスと開発マシンの間で USB ケーブルを外して、USB ケーブルを再接続してみてください。  Android および開発マシンの画面のロックが解除されている状態で、タスクを完了します。  
*   USB ケーブルが動作していることを確認してください。  開発用コンピューターから Android デバイスのファイルを検査できる必要があります。  

ソフトウェアが正しく設定されているかどうかを確認するには、次のヒントを参考にしてください。  

*   開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。  詳細については、「 [OEM USB ドライバーをインストール][AndroidUSBDrivers]する」を参照してください。  
*   Windows と Android デバイスの組み合わせ (特に Samsung \) には、追加の設定が必要です。  詳細については、「[デバイスが接続されるときにデバイスが検出されない] [StackOverflowDevicesNotDetected]」を参照してください。  

Android デバイスで**USB デバッグを許可**するかどうかを確認するには、次のヒントを参照してください。  

*   DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。  
    
    > [!NOTE]
    > Android または開発用コンピューターの画面がロックされている場合、このプロンプトが表示されないことがあります。  

*   Android デバイスと開発用コンピューターの表示設定を更新して、それぞれがスリープ状態にならないようにします。  
*   Android の USB モードを PTP に設定します。  詳細については、「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない][StackExchangeGalaxyS4DoesNotShowDialogBox]」を参照してください。  
*   Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。  

このページに記載されていない解決策を見つけた場合、または [DevTools デバイスで、スタックオーバーフロー時にデバイスが接続されています] [StackOverflowDevicesNotDetected] が検出されない場合は、スタックオーバーフローの質問にソリューションを追加してください。<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->!  

## 手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする  

1.  Android デバイスで Microsoft Edge を開きます。  
1.  ページから `edge://inspect` 、Android デバイスのモデル名の後にデバイスのシリアル番号が表示されます。  その下で、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれていることが確認できます。  各開いている Microsoft Edge タブには、一意のセクションがあります。  セクションからそのタブを操作できます。  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="接続されているリモートデバイス" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       図 3.   接続されているリモートデバイス  
    :::image-end:::  
    
1.  [**開く] タブ**の [url] テキストボックスに url を入力し、[**開く**] を選択します。  Android デバイスの新しいタブにページが表示されます。  
1.  直前に開いた URL の横にある [**検査**] を選択します。  新しい DevTools インスタンスが開きます。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### その他のアクション: タブにフォーカス、再読み込み、または閉じる  

フォーカスタブ、再読み込み、または閉じるタブの横にある [**フォーカス] タブ**、[**再読み込み**]、または [**閉じる**] を選択します。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="タブをフォーカス、再読み込み、または閉じるためのボタン" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   図 4:   タブをフォーカス、再読み込み、または閉じるためのボタン  
:::image-end:::  

### 要素を検査する  

DevTools インスタンスの**要素**パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。  

Android デバイスの画面で要素を選択して、[**要素**] パネルで選ぶこともできます。  DevTools インスタンスで [**要素**の選択] アイコンを選択し、 ![ ][ImageSelectElementIcon] Android デバイス画面で要素を選択します。  

> [!NOTE]
> 最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。  

### Android の画面を開発用コンピューターに Screencast  

[ **Screencast** ![ トグル Screencast] を選択し ][ImageToggleScreencastIcon] て、Devtools インスタンスで Android デバイスのコンテンツを表示します。  

Screencast は次の方法で操作できます。  

*   クリックは、デバイスで適切なタッチイベントを発生させるために、タップに変換されます。  
*   コンピューターのキーボード操作がデバイスに送信されます。  
*   ピンチジェスチャをシミュレートするには、 `Shift` ドラッグ中にホールドします。  
*   スクロールするには、トラックパッドまたはマウスホイール、またはマウスポインターでフリックを使用します。

> [!NOTE]
> 次のヒントを使用して、screencast を支援してください。  
> 
> *   スクリーンキャストは、ページコンテンツを表示します。  Screencast の透明部分は、Microsoft Edge のアドレスバー、Android ステータスバー、Android キーボードなどのデバイスインターフェイスを表します。  
> *   スクリーンキャストはフレームレートに悪影響を与えます。  スクロールまたはアニメーションの計測中に screencasting を無効にすると、ページのパフォーマンスがより正確に表示されます。  
> *   Android デバイスの画面がロックされている場合、screencast のコンテンツは表示されなくなります。  Android デバイスの画面のロックを解除して、screencast を自動的に再開します。  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
<!--[ImageEdgeInspect]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-no-targets.msft.png "Figure 1: The edge://inspect page in Microsoft Edge"  -->  
<!--[ImageAndroidPermissionPrompt]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-android-permissions-prompt.msft.png "Figure 2: The Allow USB Debugging permission prompt on an Android device"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-with-targets.msft.png "Figure 3: A connected remote device"  -->  
<!-- [ImageReload]:  /microsoft-edge/devtools-guide-chromium/media/remote-debugging-edge-inspect-with-targets-buttons.msft.png "Figure 4: The buttons for focusing, reloading, or closing a tab"  -->  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  

<!-- links -->  

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
