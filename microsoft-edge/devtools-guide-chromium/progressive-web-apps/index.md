---
description: アプリケーション パネルを使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。
title: 段階的な Web アプリのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 79edf4b04c85db33e89d18ec1832138a61f4f884
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234376"
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

# 段階的な Web アプリのデバッグ  

アプリケーション パネル **を使用** して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

このガイドでは、アプリケーション パネルの段階的な Web App 機能についての **み説明** します。  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### まとめ  

*   マニフェスト ウィンドウ **を使用** して、Web アプリマニフェストを検査し、ホーム画面に追加イベントをトリガーします。  
*   サービスワーカー **ウィンドウ** は、サービスの登録解除や更新、プッシュ イベントのモデル化、オフライン化、サービス ワーカーの停止など、サービス ワーカー関連の全範囲のタスクに使用します。  
*   [キャッシュ ストレージ] ウィンドウからサービス ワーカー **キャッシュを表示** します。  
*   サービス ワーカーの登録を解除し、[ストレージのクリア] ウィンドウから 1 回クリックしてすべてのストレージと **キャッシュをクリア** します。  
    
## Web アプリ マニフェスト  

ユーザーがモバイル ホーム画面にアプリを追加するには、Web アプリ マニフェストが必要です。  マニフェストは、アプリがホーム画面に表示される方法、ホーム画面から起動するときにユーザーを指示する場所、アプリの起動時の外観を定義します。  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

マニフェストを設定した後、アプリケーション パネルの **マニフェスト** ウィンドウを使用して **マニフェストを検査** できます。  

:::image type="complex" source="../media/manifest-pane.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/manifest-pane.msft.png":::
   マニフェスト**** ウィンドウ  
:::image-end:::  

*   マニフェスト ソースを確認するには、アプリ マニフェスト**** ラベル \( 前の図の \) の下の `https://airhorner.com/manifest.json` リンクをクリックします。  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   Identity **セクション** と **Presentation セクション** では、マニフェスト ソースのフィールドを、より使い分け的な表示に表示します。  
*   [ **アイコン]** セクションには、指定したアイコンが表示されます。  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="../media/io.msft.png" alt-text="Add to desktop shelf" lightbox="../media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## サービス ワーカー  

サービス ワーカーは、将来の Web プラットフォームの基本的なテクノロジです。  これらは、Web ページとは別に、ブラウザーがバックグラウンドで実行されるスクリプトです。  これらのスクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン エクスペリエンスなど、Web ページやユーザー操作を必要としない機能にアクセスできます。  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

アプリケーション**パネルの [** サービス**** ワーカー] ウィンドウは、サービス ワーカーを検査およびデバッグする DevTools の主要な場所です。  

:::image type="complex" source="../media/service-workers-pane.msft.png" alt-text="[サービス ワーカー] ウィンドウ" lightbox="../media/service-workers-pane.msft.png":::
   [ **サービス ワーカー]** ウィンドウ  
:::image-end:::  

*   サービス ワーカーが現在開いているページにインストールされている場合、このウィンドウに表示されます。  たとえば、前の図では、次の範囲のサービス ワーカーがインストールされています `https://weather-pwa-sample.firebaseapp.com` 。  
*   [ **オフライン]** チェック ボックスをオンにすると、DevTools はオフライン モードになります。  これは、[ネットワーク] パネルから使用できるオフライン**** モード、またはコマンド メニュー `Go offline` のオプションと[同じです][DevtoolsCommandMenuIndex]。  
*   [再 **読み込み時に** 更新] チェック ボックスをオンにすると、サービス ワーカーはページの読み込みごとに強制的に更新されます。  
*   [ **ネットワークのバイパス] チェック** ボックスは、サービス ワーカーをバイパスし、要求されたリソースのネットワークにブラウザーを強制的に移動します。  
*   [ **更新]** ボタンは、指定したサービス ワーカーの 1 回の更新を実行します。  
*   プッシュ **ボタン** は、ペイロード \(ティック \ とも呼ばれる) なしでプッシュ通知 **をエミュレート**します。  
*   [ **同期]** ボタンは、バックグラウンド同期イベントをエミュレートします。  
*   [ **登録解除]** ボタンは、指定したサービス ワーカーの登録を解除します。  サービス ワーカー [の登録を](#clear-storage) 解除し、1 回のボタン クリックでストレージとキャッシュをワイプする方法については、「ストレージのクリア」を参照してください。  
*   [ **ソース]** 行は、現在実行中のサービス ワーカーがインストールされた時間を示します。  リンクは、サービス ワーカーのソース ファイルの名前です。  リンクをクリックすると、サービス ワーカーのソースに送信されます。  
*   [ **状態]** 行は、サービス ワーカーの状態を示します。  緑色のステータス インジケーター \( 前の図\) の横にある ID 番号は、現在アクティブ `#36` なサービス ワーカー用です。  状態の横には、開始ボタン \(サービス ワーカーが停止している場合\) または停止ボタン**** \(サービス ワーカーが実行中の場合\) が表示されます。 ****  サービス ワーカーは、いつでもブラウザーによって停止および開始するように設計されています。  停止ボタンを使用してサービス ワーカーを明示的に **停止** すると、その動作をシミュレートできます。  サービス ワーカーを停止すると、サービス ワーカーが再び起動するときにコードがどのように動作するのかをテストできます。  永続的なグローバル状態に関する誤った前提により、バグが頻繁に明らかになります。  
*   [ **クライアント]** 行は、サービス ワーカーのスコープが設定されている発生元を示します。  フォーカス **ボタンは** 、[すべての表示] チェック ボックスを有効にした場合 **に最も便利** です。  このチェック ボックスを有効にすると、登録されているサービス ワーカーすべてが一覧表示されます。  別のタブで実行**** されているサービス ワーカーの横にあるフォーカス ボタンをクリックすると、Microsoft Edge ではそのタブに焦点が当てられています。  
    
サービス ワーカーがエラーを発生すると、Errors という新しいラベル **が** 表示されます。  

<!--  
:::image type="complex" source="../media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="../media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## サービス ワーカー キャッシュ  

[ **キャッシュ ストレージ]** ウィンドウには、\(サービス ワーカー\) キャッシュ API を使用してキャッシュされたリソースの読み取り専用リストが [表示されます][MDNWebCacheAPI]。  

:::image type="complex" source="../media/cache-pane-cache-storage-resources.msft.png" alt-text="[キャッシュストレージ] ウィンドウ" lightbox="../media/cache-pane-cache-storage-resources.msft.png":::
   [ **キャッシュストレージ]** ウィンドウ  
:::image-end:::  

> [!NOTE]
> 初めてキャッシュを開いてリソースを追加すると、DevTools が変更を検出しない可能性があります。  ページを再読み込みすると、キャッシュが表示されます。  

2 つ以上のキャッシュを開いている場合は、[キャッシュ ストレージ] ドロップダウンの下にキャッシュ **が表示** されます。  

:::image type="complex" source="../media/cache-pane-cache-storage.msft.png" alt-text="[キャッシュ ストレージ] ドロップダウン" lightbox="../media/cache-pane-cache-storage.msft.png":::
   [ **キャッシュ ストレージ]** ドロップダウン  
:::image-end:::  

## クォータの使用状況  

[キャッシュ ストレージ] ウィンドウ **内の一部の** 応答は、"不透明" としてフラグが設定される場合があります。  これは[、CORS][FetchHttpCorsProtocol]が有効になっていない場合に **、CDN**やリモート API など、別の配信元から取得された応答を指します。  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

クロスドメイン情報の漏洩を回避するために、ストレージ クォータの制限 \(例外がスローされたかどうかなど) を計算するために使用される不透明な応答のサイズに大幅なパディングが追加され `QuotaExceeded` 、API によって報告されます。 `navigator.storage`  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge の場合、単**** 一キャッシュされた不透明な応答が記憶域全体の使用量に与える最小サイズは約[7 MB][ChromiumIssues796060#c17]です。  これは、キャッシュする不透明な応答の数を決定する際に念頭に置く必要があります。これは、ストレージ クォータの制限を、不透明なリソースの実際のサイズに基づいて予想するよりもずっと早く簡単に超過する可能性があるからです。  

関連ガイド:  

*   [スタック オーバーフロー: 不透明な応答に適用される制限][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## ストレージのクリア  

[ **ストレージのクリア]** ウィンドウは、段階的な Web アプリを開発するときに非常に便利な機能です。  このウィンドウでは、サービス ワーカーの登録を解除し、ボタンを 1 回クリックしてすべてのキャッシュとストレージをクリアできます。  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニューを使用してコマンドを実行する |Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium の問題 796060: 分析コードが html 内にある場合、更新ごとにキャッシュ ストレージの値が増加する"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ - Web API |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "スタック オーバーフロー: 不透明な応答に適用される制限"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
