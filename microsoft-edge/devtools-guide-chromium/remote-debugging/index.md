---
description: Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。
title: Android デバイスのリモートデバッグの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c6bdb48460fb8f6ff26cbb02872e33cb50dd6e12
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125364"
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

Windows または macOS コンピューターから Android デバイス上のリモートデバッグライブコンテンツ。  次のチュートリアルページでは、次の操作を実行する方法について説明します。  

*   リモートデバッグ用に Android デバイスをセットアップし、開発用コンピューターから検出します。  
*   開発用コンピューターから Android デバイスのライブコンテンツを検査およびデバッグします。  
*   Android デバイスのコンテンツを開発用コンピューターの DevTools インスタンスに Screencast します。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> IOS デバイスでの Microsoft Edge アプリのリモートデバッグは、現在サポートされていません。  次のガイドでは、特に Android デバイスでの Microsoft Edge のリモートデバッグに重点を置いています。
> MacOS デバイスをお使いの場合は、 [Brightcove のデバッグガイド][BrightcoveSupportDebuggingMobileDevices] に従って、Safari を使用して iOS デバイスで Microsoft Edge をリモートでデバッグしてください。  Safari の Web 検査ツールの詳細については、「 [Safari Web 開発ツール][AppleDeveloperSafariTools]」を参照してください。  

## 手順 1: Android デバイスを見つける  

以下のワークフローは、ほとんどのユーザーに適しています。  詳細については、「開発 [ツールで Android デバイスが検出されない](#troubleshooting-devtools-is-not-detecting-the-android-device) 」を参照してください。  

1.  Android で [ **開発者向けオプション** ] 画面を開きます。  詳細については、「 [デバイス開発者向けオプションを構成][AndroidDeveloperStudioDevOptions]する」を参照してください。  
1.  [ **USB デバッグを有効にする**] を選びます。  
1.  開発用コンピューターで、Microsoft Edge を開きます。  
1.  `edge://inspect`Microsoft Edge でページに移動します。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       図 1.   `edge://inspect`Microsoft Edge のページ  
    :::image-end:::  
    
1.  USB ケーブルを使って、Android デバイスを開発用コンピューターに直接接続します。  初めて接続しようとしたときに、不明なデバイスを検出する DevTools についてのプロンプトが表示されます。  Android デバイスで [ **USB のデバッグを許可** ] プロンプトを承諾します。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       図 2.   Android デバイスでの **USB デバッグ** の許可プロンプト  
    :::image-end:::  
    
1.  Android デバイスのモデル名が表示されている場合は、Microsoft Edge でデバイスへの接続が正常に確立されています。  [手順 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)のセクションに進みます。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### トラブルシューティング: DevTools で Android デバイスが検出されない  

以下のヒントは、お使いのハードウェアの適切な設定のトラブルシューティングに役立ちます。  

*   USB ハブを使っている場合は、Android デバイスを開発用コンピューターに直接接続してみてください。  
*   Android デバイスと開発マシンの間で USB ケーブルを外して、USB ケーブルを再接続してみてください。  Android および開発マシンの画面のロックが解除されている状態で、タスクを完了します。  
*   USB ケーブルが動作していることを確認してください。  開発用コンピューターから Android デバイスのファイルを検査できる必要があります。  

ソフトウェアが正しく設定されているかどうかを確認するには、次のヒントを参考にしてください。  

*   開発用コンピューターで Windows を実行している場合は、Android デバイスの USB ドライバーを手動でインストールしてみてください。  詳細については、「 [OEM USB ドライバーをインストール][AndroidDeveloperToolsOemUsb]する」を参照してください。  
*   Windows と Android デバイスの組み合わせ (特に Samsung \) には、追加の設定が必要です。  詳細については、「 [デバイスに接続してもデバイスが検出されない][Stackoverflow21925992]」を参照してください。  

Android デバイスで [ **USB デバッグを許可** する] プロンプトが表示されない場合のトラブルシューティングについては、次のヒントを参照してください。  

*   DevTools が開発用コンピューターに集中していて、Android のホーム画面が表示されているときに、USB ケーブルを切断してから接続し直す。  
    
    > [!NOTE]
    > このメッセージは、Android または開発用コンピューターの画面がロックされている場合に表示されます。  

*   Android デバイスと開発用コンピューターの表示設定を更新して、それぞれがスリープ状態にならないようにします。  
*   Android の USB モードを PTP に設定します。  詳細については、「 [Galaxy S4 で [USB デバッグの承認] ダイアログボックスが表示されない」][StackexchangeAndroid101933]を参照してください。  
*   Android デバイスの [**開発者オプション**] 画面で [ **USB デバッグ承認の取り消し**] を選択して、新しい状態にリセットします。  

このページに記載されていない解決策を見つけた場合や、Devtools デバイスでスタックオーバーフローに接続しても [デバイスが検出][Stackoverflow21925992] されない場合は、スタックオーバーフローの質問にソリューションを追加してください。<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->!  

## 手順 2: 開発用コンピューターから Android デバイスのコンテンツをデバッグする  

1.  Android デバイスで Microsoft Edge を開きます。  
1.  に移動すると、 `edge://inspect` Android デバイスのモデル名が表示され、その後にデバイスのシリアル番号が表示されます。  その下では、デバイス上で実行されている Microsoft Edge のバージョン番号がかっこで囲まれています。  各開いている Microsoft Edge タブには、一意のセクションがあります。  セクションからそのタブを操作できます。  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       図 3.   接続されているリモートデバイス  
    :::image-end:::  
    
1.  [ **開く] タブ** の [url] テキストボックスに url を入力し、[ **開く**] を選択します。  Android デバイスの新しいタブにページが表示されます。  
1.  直前に開いた URL の横にある [ **検査** ] を選びます。  新しい DevTools インスタンスが開きます。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### その他のアクション: タブにフォーカス、再読み込み、または閉じる  

フォーカスタブ、再読み込み、または閉じるタブの横にある [ **フォーカス] タブ**、[ **再読み込み**]、または [ **閉じる** ] を選択します。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   図 4:   タブをフォーカス、再読み込み、または閉じるためのボタン  
:::image-end:::  

### 要素を検査する  

DevTools インスタンスの **要素** パネルに移動し、要素の上にマウスポインターを置いて、Android デバイスのビューポートでその要素を強調表示します。  

Android デバイスの画面で要素を選択して、[ **要素** ] パネルで選ぶこともできます。  DevTools インスタンスで [ **要素の選択** ] ( ![ 要素の選択) アイコンを選択し、 ][ImageSelectElementIcon] Android デバイス画面で要素を選択します。  

> [!NOTE]
> 最初の選択の後に **[要素の選択]** が無効になっているため、この機能を使うたびに有効にする必要があります。  

### Android の画面を開発用コンピューターに Screencast  

**Toggle Screencast** ![ ][ImageToggleScreencastIcon] Devtools インスタンスで Android デバイスのコンテンツを表示するには、[トグル Screencast \ (トグル Screencast \)] を選びます。  

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

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "デバイス開発者向けオプションを構成する |Android 開発者"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストールする |Android 開発者"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 開発ツール |Apple 開発者"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "モバイルデバイスでのデバッグ |Brightcove サポート"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb-Android ファンスタック交換"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "デバイスが電源に接続されているときにデバイスが検出されない"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
