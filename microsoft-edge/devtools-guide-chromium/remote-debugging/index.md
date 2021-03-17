---
description: Windows または macOS コンピューターから Android デバイス上のライブ コンテンツをリモート デバッグします。
title: Android デバイスのリモート デバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2beab5bf6d4b58dc93d883f5114e168213053e84
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439569"
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

# <a name="get-started-with-remote-debugging-android-devices"></a>Android デバイスのリモート デバッグを開始する  

Windows または macOS コンピューターから Android デバイス上のライブ コンテンツをリモート デバッグします。  次のチュートリアル ページでは、次のアクションを実行する方法について説明します。  

*   リモート デバッグ用に Android デバイスをセットアップし、開発マシンから検出します。  
*   開発マシンから Android デバイス上のライブ コンテンツを検査およびデバッグします。  
*   Android デバイスから開発マシンの DevTools インスタンスにスクリーンキャストされたコンテンツ。  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> iOS デバイスでの Microsoft Edge アプリのリモート デバッグは現在サポートされていません。  次のガイドは、Android デバイスでの Microsoft Edge のリモート デバッグに特に重点を置きます。
> macOS デバイスがある場合は [、Brightcove Debuging][BrightcoveSupportDebuggingMobileDevices] ガイドに従って、Safari を使用して iOS デバイスで Microsoft Edge をリモートでデバッグします。  Safari の Web インスペクター ツールの詳細については [、「Safari Web 開発ツール」に移動します][AppleDeveloperSafariTools]。  

## <a name="step-1-discover-your-android-device"></a>手順 1: Android デバイスを検出する  

以下のワークフローは、ほとんどのユーザーに対して機能します。  詳細については、「トラブルシューティング: [DevTools](#troubleshooting-devtools-is-not-detecting-the-android-device) で Android デバイスが検出されない」セクションに移動します。  

1.  Android の **[開発者オプション]** 画面を開きます。  詳細については、「Configure [On-Device Developer Options」に移動します][AndroidDeveloperStudioDevOptions]。  
1.  [USB **デバッグを有効にする] を選択します**。  
1.  開発マシンで、Microsoft Edge を開きます。  
1.  Microsoft Edge の `edge://inspect` ページに移動します。  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge edge://inspect ページ" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       図 1.   `edge://inspect`Microsoft Edge のページ  
    :::image-end:::  
    
1.  USB ケーブルを使用して、Android デバイスを開発マシンに直接接続します。  初めて接続を試みた場合は、不明なデバイスを検出する DevTools に関するプロンプトが表示されます。  Android デバイスで **[USB デバッグを許可する** ] アクセス許可のプロンプトに同意します。  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android デバイスで [USB デバッグを許可する] アクセス許可のプロンプト" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       図 2.   Android **デバイスで [USB デバッグを** 許可する] アクセス許可のプロンプト  
    :::image-end:::  
    
1.  Android デバイスのモデル名が表示されている場合、Microsoft Edge はデバイスへの接続を正常に確立しました。  [手順 [2] セクションに進](#step-2-debug-content-on-your-android-device-from-your-development-machine) みます。  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a>トラブルシューティング: DevTools が Android デバイスを検出していない  

ハードウェアの正しい設定のトラブルシューティングに役立つヒントを次に示します。  

*   USB ハブを使用している場合は、Android デバイスを開発マシンに直接接続してみてください。  
*   Android デバイスと開発コンピューターの間で USB ケーブルを抜いてから、USB ケーブルを再接続してみてください。  Android と開発コンピューターの画面のロックが解除されている間にタスクを完了します。  
*   USB ケーブルが動作する必要があります。  開発マシンから Android デバイス上のファイルを検査できる必要があります。  

ソフトウェアが正しくセットアップされていることを確認するには、次のヒントを使用します。  

*   開発マシンで Windows が実行されている場合は、Android デバイス用の USB ドライバーを手動でインストールしてみてください。  詳細については [、「OEM USB ドライバーのインストール」に移動します][AndroidDeveloperToolsOemUsb]。  
*   Windows デバイスと Android デバイスの一部の組み合わせ \(特に Samsung\) では、追加の設定が必要です。  詳細については、「DevTools Devices に移動しても、接続時 [にデバイスが検出されない」に移動します][Stackoverflow21925992]。  

次のヒントを使用して、Android デバイスに **[USB** デバッグを許可する] プロンプトが表示されない場合のトラブルシューティングに役立ちます。  

*   DevTools が開発マシンに焦点を当て、Android のホームスクリーンが表示されている間に、USB ケーブルを切断してから再接続します。  
    
    > [!NOTE]
    > Android または開発コンピューターの画面がロックされている場合、プロンプトが表示されます。  

*   Android デバイスと開発マシンの表示設定を更新して、それぞれがスリープ状態になじむのを行います。  
*   Android の USB モードを PTP に設定します。  詳細については、[Usb デバッグの承認] ダイアログ ボックスが表示されない [[Galaxy S4] に移動します][StackexchangeAndroid101933]。  
*   Android**デバイスの [開発者オプション]** 画面から [USB デバッグの承認を取り消す] を選択して、新しい状態にリセットします。 ****  

このページまたは [DevTools デバイス][Stackoverflow21925992] でスタック オーバーフローに接続してもデバイスが検出されないソリューションを見つけた場合は、ソリューションをスタック オーバーフローの質問に追加してください<!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]-->.  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a>手順 2: 開発マシンから Android デバイスのコンテンツをデバッグする  

1.  Android デバイスで Microsoft Edge を開きます。  
1.  に移動 `edge://inspect` すると、Android デバイスのモデル名が表示され、その後にデバイスのシリアル番号が表示されます。  その下に、デバイスで実行されている Microsoft Edge のバージョンが表示され、バージョン番号がかっこで囲まれている必要があります。  開いている Microsoft Edge タブごとに、一意のセクションが表示されます。  セクションからそのタブを操作できます。  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="接続されたリモート デバイス" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       図 3.   接続されたリモート デバイス  
    :::image-end:::  
    
1.  [URL を **指定して開く] タブ** で URL を入力し、[開く] を **選択します**。  ページが Android デバイスの新しいタブで開きます。  
1.  開 **いた URL** の横にある [検査] を選択します。  新しい DevTools インスタンスが開きます。  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a>その他のアクション: フォーカス、更新、またはタブを閉じる  

フォーカス **、更新、****または****閉じるタブ**の横にある [フォーカス] タブ、再読み込み、または閉じるを選択します。  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="タブのフォーカス、更新、または閉じるボタン" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   図 4:   タブのフォーカス、更新、または閉じるボタン  
:::image-end:::  

### <a name="inspect-elements"></a>要素を検査する  

DevTools **インスタンスの Elements** ツールに移動し、要素にカーソルを合わせると、Android デバイスのビューポートで強調表示されます。  

Android デバイス画面で要素を選択して、[要素] **ツールで選択** することもできます。  DevTools **インスタンス** で [Select Element \( Select Element \) ] アイコンを選択し、Android デバイス画面で要素 ![ ](../media/select-element-icon.msft.png) を選択します。  

> [!NOTE]
> **最初の** 選択後に Select Element が無効になっているので、機能を使用する度に再び有効にする必要があります。  

### <a name="screencast-your-android-screen-to-your-development-machine"></a>開発マシンに Android 画面をスクリーンキャストする  

DevTools **インスタンスで** Android デバイスのコンテンツを表示するには、[画面キャストの切り替え \( 画面キャスト \) の切り替え] アイコン ![ ](../media/toggle-screencast-icon.msft.png) を選択します。  

スクリーンキャストを操作するには、次の方法を使用します。  

*   選択はタップに変換され、デバイスで適切なタッチ イベントが発生します。  
*   コンピューター上のキーストロークがデバイスに送信されます。  
*   ピンチ ジェスチャをシミュレートするには、ドラッグ中 `Shift` に保持します。  
*   スクロールするには、トラックパッドまたはマウス ホイールを使用するか、マウス ポインターを使用します。

> [!NOTE]
> スクリーンキャストに役立つヒントを次に示します。  
> 
> *   スクリーンキャストは、ページコンテンツのみを表示します。  スクリーンキャストの透明な部分は、Microsoft Edge アドレス バー、Android ステータス バー、Android キーボードなどのデバイス インターフェイスを表します。  
> *   スクリーンキャストはフレーム レートに悪影響を及ぼします。  スクロールやアニメーションの測定中にスクリーンキャストを無効にして、ページのパフォーマンスをより正確に把握します。  
> *   Android デバイスの画面がロックされている場合、スクリーンキャストのコンテンツは消えます。  Android デバイス画面のロックを解除して、スクリーンキャストを自動的に再開します。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "デバイス上の開発者向けオプションを構成|Android 開発者"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "OEM USB ドライバーをインストール|Android 開発者"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 開発ツール |Apple Developer"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "モバイル デバイス のデバッグ |Brightcove サポート"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android の熱狂スタック Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "DevTools デバイスは、接続時にデバイスを検出しません - スタック オーバーフロー"  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
