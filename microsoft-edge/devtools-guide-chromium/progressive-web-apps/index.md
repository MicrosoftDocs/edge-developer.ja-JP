---
description: '[アプリケーション] パネルを使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。'
title: プログレッシブ Web アプリのデバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: aea01d25474a030e78ac0eaeaef3954ab7f4539f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398540"
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

# <a name="debug-progressive-web-apps"></a>プログレッシブ Web アプリのデバッグ  

[アプリケーション **] パネル** を使用して、Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグします。  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

このガイドでは、[アプリケーション] パネルのプログレッシブ Web アプリ機能についてのみ **説明** します。  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### <a name="summary"></a>まとめ  

*   [マニフェスト] **ウィンドウを** 使用して Web アプリ マニフェストを検査し、[ホーム画面に追加] イベントをトリガーします。  
*   サービスの **登録** 解除や更新、プッシュ イベントの表示、オフライン化、サービス ワーカーの停止など、サービス ワーカー関連のタスクの範囲全体に対して、[サービス ワーカー] ウィンドウを使用します。  
*   [キャッシュ] ウィンドウからサービス ワーカー**キャッシュStorage**します。  
*   サービス ワーカーの登録を解除し、[ストレージのクリア] ウィンドウから選択した 1 つのボタンですべての記憶域と **キャッシュをクリア** します。  
    
## <a name="web-app-manifest"></a>Web アプリ マニフェスト  

ユーザーがモバイル ホームスクリーンにアプリを追加するには、Web アプリ マニフェストが必要です。  マニフェストは、アプリがホームスクリーンに表示される方法、ホーム画面から起動するときにユーザーを指示する場所、およびアプリの起動時の外観を定義します。  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

マニフェストをセットアップした後、アプリケーション パネルの **[マニフェスト**] ウィンドウ**** を使用して検査できます。  

:::image type="complex" source="../media/manifest-pane.msft.png" alt-text="マニフェスト ウィンドウ" lightbox="../media/manifest-pane.msft.png":::
   マニフェスト**ウィンドウ**  
:::image-end:::  

*   マニフェスト ソースを確認するには、前の図の**** アプリ マニフェスト ラベル \( の下 `https://airhorner.com/manifest.json` にあるリンクを選択します\)。  
<!-- *   Choose the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   **[Id]** セクション**と [プレゼンテーション]** セクションでは、マニフェスト ソースのフィールドをユーザーフレンドリーな表示に表示します。  
*   [ **アイコン]** セクションには、指定したアイコンが表示されます。  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app may only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, the criteria is potentially inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You may test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Choosing on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="../media/io.msft.png" alt-text="Add to desktop shelf" lightbox="../media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature may not yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you may successfully add your app to your desktop shelf, then it works for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you may connect a real mobile device to DevTools via **remote debugging**, and then choose the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## <a name="service-workers"></a>サービス ワーカー  

サービス ワーカーは、将来の Web プラットフォームの基本的なテクノロジです。  これらは、Web ページとは別に、ブラウザーがバックグラウンドで実行するスクリプトです。  スクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン エクスペリエンスなど、Web ページやユーザー操作を必要とせずに機能にアクセスできます。  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

[ **アプリケーション] パネルの** [ **サービス** ワーカー] ウィンドウは、サービス ワーカーを検査およびデバッグする DevTools の主要な場所です。  

:::image type="complex" source="../media/service-workers-pane.msft.png" alt-text="[サービス ワーカー] ウィンドウ" lightbox="../media/service-workers-pane.msft.png":::
   [ **サービス ワーカー]** ウィンドウ  
:::image-end:::  

*   サービス ワーカーが現在開いているページにインストールされている場合は、このウィンドウに表示されます。  たとえば、前の図では、 のスコープにサービス ワーカーがインストールされています `https://weather-pwa-sample.firebaseapp.com` 。  
*   [ **オフライン]** チェック ボックスをオンにすると、DevTools はオフライン モードになります。  これは、ネットワーク ツールで使用できるオフライン**** モード、またはコマンド `Go offline` メニューのオプションと[同じです][DevtoolsCommandMenuIndex]。  
*   [再 **読み込み時に更新** ] チェック ボックスをオンにすると、サービス ワーカーはページの読み込みごとに強制的に更新されます。  
*   [ **ネットワークのバイパス]** チェック ボックスは、サービス ワーカーをバイパスし、要求されたリソースのネットワークにブラウザーを強制的に移動します。  
*   [ **更新]** ボタンは、指定したサービス ワーカーの 1 回の更新を実行します。  
*   プッシュ **ボタン** は、ペイロード \(くすぐり \とも呼ばれる) なしでプッシュ通知を **エミュレート**します。  
*   [ **同期]** ボタンは、バックグラウンド同期イベントをエミュレートします。  
*   [ **登録解除** ] ボタンは、指定したサービス ワーカーの登録を解除します。  サービス ワーカー [の登録を](#clear-storage) 解除し、1 つのボタンでストレージとキャッシュをワイプする方法については、「ストレージをクリアする」を参照してください。  
*   [ **ソース]** 行は、現在実行中のサービス ワーカーがインストールされた時間を示します。  リンクは、サービス ワーカーのソース ファイルの名前です。  リンクを選択すると、サービス ワーカーのソースに送信されます。  
*   [ **状態]** 行には、サービス ワーカーの状態が表示されます。  緑の状態インジケーター \( 前の図\) の横にある ID 番号は、現在アクティブ `#36` なサービス ワーカー用です。  状態の横には、開始**** ボタン \(サービス ワーカーが停止している場合\) または**** 停止ボタン \(サービス ワーカーが実行されている場合\) が表示されます。  サービス ワーカーは、いつでもブラウザーによって停止および開始するように設計されています。  停止ボタンを使用してサービス ワーカーを明示的に **停止** すると、その操作をシミュレートできます。  サービス ワーカーを停止すると、サービス ワーカーが再びバックアップを開始するときにコードがどのように動作するのかをテストできます。  これは、永続的なグローバル状態に関する誤った仮定によるバグを頻繁に明らかにします。  
*   [ **クライアント]** 行には、サービス ワーカーのスコープが設定されている起点が示されます。  フォーカス **ボタンは** 、[すべて表示] チェック ボックスを有効にした場合 **に主に便利** です。  このチェック ボックスを有効にすると、登録されているサービス ワーカーすべてが一覧表示されます。  別のタブで実行**されている**サービス ワーカーの横にあるフォーカス ボタンを選択した場合は、そのMicrosoft Edgeにフォーカスを当てる必要があります。  
    
サービス ワーカーがエラーを発生すると、Errors という名前の新しいラベル **が** 表示されます。  

<!--  
:::image type="complex" source="../media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="../media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## <a name="service-worker-caches"></a>サービス ワーカー キャッシュ  

[**キャッシュ Storage]** ウィンドウには、\(service worker\) キャッシュ API を使用してキャッシュされたリソースの読み取り専用[リストが表示されます][MDNWebCacheAPI]。  

:::image type="complex" source="../media/cache-pane-cache-storage-resources.msft.png" alt-text="[キャッシュ] ウィンドウStorageウィンドウ" lightbox="../media/cache-pane-cache-storage-resources.msft.png":::
   [**キャッシュ] ウィンドウStorage**ウィンドウ  
:::image-end:::  

> [!NOTE]
> キャッシュを初めて開いてリソースを追加すると、DevTools によって変更が検出されない場合があります。  ページを更新し、キャッシュを表示します。  

2 つ以上のキャッシュを開いている場合は、次の [キャッシュ] ドロップダウンの下**Storage**表示されます。  

:::image type="complex" source="../media/cache-pane-cache-storage.msft.png" alt-text="[キャッシュ] Storageドロップダウン" lightbox="../media/cache-pane-cache-storage.msft.png":::
   [**キャッシュ] Storage**ドロップダウン  
:::image-end:::  

## <a name="quota-usage"></a>クォータ使用量  

[キャッシュ] ウィンドウ内の**一部Storage**が "不透明" としてフラグ付けされる場合があります。  これは[、CORS][FetchHttpCorsProtocol]が有効になっていない場合に、別のオリジン **(CDN** API やリモート API など) から取得された応答を指します。  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

クロスドメイン情報の漏洩を回避するために、ストレージ クォータ制限の計算に使用される不透明な応答のサイズに大きな埋め込み (たとえば、例外がスロー `QuotaExceeded` されるかどうか\) が `navigator.storage` 追加され、API によって報告されます。  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge の場合、キャッシュされた 1**** 回の不透明応答がストレージ全体の使用量に与える最小サイズは約[7 メガバイト][ChromiumIssues796060#c17]です。  キャッシュする不透明な応答の数を決定する場合は、不透明なリソースの実際のサイズに基づいて、ストレージ クォータの制限をはるかに早く超える可能性があります。  

関連ガイド:  

*   [スタック オーバーフロー: 不透明な応答に適用される制限][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## <a name="clear-storage"></a>ストレージのクリア  

[Clear **Storage]** ウィンドウは、プログレッシブ Web アプリを開発するときに非常に便利な機能です。  このウィンドウでは、サービス ワーカーの登録を解除し、1 つのボタンですべてのキャッシュとストレージをクリアできます。  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium問題 796060: Analytics コードが html 内にあるStorage更新ごとにキャッシュの値が上昇する"  

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
