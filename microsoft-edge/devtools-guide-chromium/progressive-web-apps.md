---
title: プログレッシブ Web アプリをデバッグする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6733d7823348bc02dd6f29ec218a33ab4073dbfc
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984962"
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





# プログレッシブ Web アプリをデバッグする   



**アプリケーション**パネルを使用して、web アプリマニフェスト、サービスワーカー、service worker キャッシュを検査、変更、およびデバッグします。  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

このガイドでは、 **アプリケーション** パネルのプログレッシブ Web アプリ機能についてのみ説明します。  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### まとめ  

*   **マニフェスト**ウィンドウを使って web アプリマニフェストを検査し、トリガーをホーム画面イベントに追加します。  
*   サービスの利用状況に関するタスクの一部 (サービスの登録解除または更新、プッシュイベントのエミュレート、オフラインへの移動、サービスワーカーの停止など) を行うには、[ **Service worker** ] ウィンドウを使います。  
*   [ **キャッシュ記憶域** ] ウィンドウからサービスワーカーキャッシュを表示します。  
*   サービスワーカーの登録を解除し、[ **記憶域のクリア** ] ウィンドウから1回ボタンをクリックして、すべての記憶域とキャッシュをクリアします。  
    
## Web アプリマニフェスト   

ユーザーが自分のモバイル homescreens にアプリを追加できるようにするには、web アプリマニフェストが必要です。  マニフェストは、アプリがホーム画面にどのように表示されるかを定義します。ここでは、ホーム画面からの起動時にユーザーに指示し、アプリが起動時にどのように見えるかを示します。  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

マニフェストの設定が完了したら、**アプリケーション**パネルの**マニフェスト**ウィンドウを使ってマニフェストを検査できます。  

:::image type="complex" source="./media/manifest-pane.msft.png" alt-text="マニフェストウィンドウ" lightbox="./media/manifest-pane.msft.png":::
   **マニフェスト**ウィンドウ  
:::image-end:::  

*   マニフェストのソースを確認するには、(前の図 \ の) **アプリマニフェスト** ラベルの下にあるリンクをクリックし `https://airhorner.com/manifest.json` ます。  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   [ **Id** ] セクションと [ **プレゼンテーション** ] セクションには、マニフェストソースからのフィールドが、わかりやすい表示で表示されます。  
*   [ **アイコン** ] セクションには、指定したすべてのアイコンが表示されます。  
    
<!--### Simulate Add to Homescreen events   -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="./media/io.msft.png" alt-text="Add to desktop shelf" lightbox="./media/io.msft.png":::
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

## サービス員   

サービスワーカーは、今後の web プラットフォームの基本的なテクノロジです。  これは、ブラウザーで web ページとは別にバックグラウンドで実行されるスクリプトです。  これらのスクリプトを使用すると、プッシュ通知、バックグラウンド同期、オフライン操作など、web ページまたはユーザーの操作を必要としない機能にアクセスできます。  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

**アプリケーション**パネルの [ **service worker** ] ウィンドウは、サービスワーカーを検査およびデバッグするための devtools の主要な場所です。  

:::image type="complex" source="./media/service-workers-pane.msft.png" alt-text="[Service Worker] ウィンドウ" lightbox="./media/service-workers-pane.msft.png":::
   [ **Service worker** ] ウィンドウ  
:::image-end:::  

*   現在開いているページに service worker がインストールされている場合は、このウィンドウに一覧表示されます。  たとえば、上の図のように、のスコープとして service worker がインストールされてい `https://weather-pwa-sample.firebaseapp.com` ます。  
*   [ **オフライン** ] チェックボックスをオンにすると、devtools がオフラインモードになります。  これは、 **ネットワーク** パネルから利用できるオフラインモードまたは `Go offline` [コマンドメニュー][DevtoolsCommandMenuIndex]のオプションに相当します。  
*   **[再読み込み時の更新**] チェックボックスをオンにすると、すべてのページの読み込み時にサービスワーカーの更新が強制されます。  
*   [ **ネットワーク用にバイパス** ] チェックボックスをオンにすると、サービスワーカーが無視され、要求されたリソースについてブラウザーがネットワークに移動します。  
*   [ **更新** ] ボタンをクリックすると、指定したサービスワーカーの1回限りの更新が実行されます。  
*   **プッシュ**ボタンは、ペイロード ( **tickle**とも呼ばれます) なしでプッシュ通知をエミュレートします。  
*   [ **同期** ] ボタンは、バックグラウンド同期イベントをエミュレートします。  
*   **登録解除**ボタンは、指定されたサービスワーカーの登録を解除します。  1回のボタンクリックで、サービスワーカーの登録を解除し、ストレージとキャッシュをワイプする方法については、「 [記憶域をクリア](#clear-storage) する」を参照してください。  
*   **ソース**行は、現在実行されているサービスワーカーがインストールされたことを示します。  リンクは、サービスワーカーのソースファイルの名前です。  リンクをクリックすると、サービスワーカーのソースに送信されます。  
*   **ステータス**行は、サービスワーカーの状態を示します。  緑のステータスインジケーター (前の図) の横にある ID 番号 `#36` は、現在アクティブになっているサービスワーカーに対応しています。  状態の横には、[ **スタート** ] ボタン (サービスワーカーが停止されている場合) または [ **停止** ] ボタン (サービスワーカーが実行されている場合) が表示されます。  サービスワーカーは、ブラウザーでいつでも停止して開始するように設計されています。  [ **停止** ] ボタンを使用してサービスワーカーを明示的に停止すると、そのことがシミュレートされます。  サービスワーカーを停止することは、サービスワーカーが再起動したときにコードがどのように動作するかをテストする優れた方法です。  永続的なグローバル状態についての前提条件に不備があるため、多くの場合、バグが明らかになります。  
*   **クライアント**の行には、サービスワーカーのスコープが指定されている起点が示されます。  **フォーカス**ボタンは、ほとんどの場合、[**すべて表示**] チェックボックスをオンにしておくと便利です。  このチェックボックスがオンになっていると、登録されているすべてのサービスワーカーが一覧表示されます。  別のタブで実行されているサービスワーカーの横にある [ **フォーカス** ] ボタンをクリックすると、Microsoft Edge ではそのタブにフォーカスが移動します。  
    
サービスワーカーからエラーが発生した場合、[ **エラー** ] という名前の新しいラベルが表示されます。  

<!--  
:::image type="complex" source="./media/sw-error.msft.png" alt-text="Service worker with errors" lightbox="./media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## Service worker キャッシュ 

[ **キャッシュ記憶域** ] ウィンドウには、\ (service Worker) [キャッシュ API][MDNWebCacheAPI]を使用してキャッシュされたリソースの読み取り専用リストが表示されます。  

:::image type="complex" source="./media/cache-pane-cache-storage-resources.msft.png" alt-text="[キャッシュの記憶域] ウィンドウ" lightbox="./media/cache-pane-cache-storage-resources.msft.png":::
   [ **キャッシュの記憶域** ] ウィンドウ  
:::image-end:::  

> [!NOTE]
> 初めてキャッシュを開いてリソースを追加するときに、DevTools で変更が検出されないことがあります。  ページを再度読み込むと、キャッシュが表示されます。  

2つ以上のキャッシュを開いている場合は、[ **キャッシュストレージ** ] ドロップダウンの下に一覧表示されます。  

:::image type="complex" source="./media/cache-pane-cache-storage.msft.png" alt-text="[キャッシュ記憶域] ドロップダウン" lightbox="./media/cache-pane-cache-storage.msft.png":::
   [ **キャッシュ記憶域** ] ドロップダウン  
:::image-end:::  

## クォータ使用量 

[ **キャッシュ記憶域** ] ウィンドウ内の一部の応答は、"不透明" としてマークされることがあります。  これは、 [CORS][FetchHttpCorsProtocol]が有効になっていない場合に、 **CDN**やリモート API などの別の起点から取得された応答を指します。  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

クロスドメイン情報の漏えいを防ぐため、記憶域のクォータ制限 (例外がスローされる場合など) を計算するために使用される不透明応答のサイズに大きなパディングが追加され、 `QuotaExceeded` API によって報告され `navigator.storage` ます。  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

このパディングの詳細はブラウザーによって異なりますが、Microsoft Edge では、単一のキャッシュされた不透明応答の **最小サイズ** は [約 7 mb][ChromiumIssues796060#c17]になります。  キャッシュする不透明な応答の数を決定する際には、非透過リソースの実際のサイズに基づいて、より早く記憶域のクォータの制限を超えてしまうため、この点を念頭に置いておく必要があります。  

関連ガイド:  

*   [スタックオーバーフロー: 不透明な応答に適用される制限は何ですか?][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## 記憶域をクリアする 

[ **記憶域のクリア** ] ウィンドウは、プログレッシブ web アプリを開発するときに便利な機能です。  このウィンドウでは、サービスワーカーの登録を解除し、1回のボタンクリックですべてのキャッシュとストレージをクリアすることができます。  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides 

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
<!--TODO  -->

<!--  
 


-->  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ./command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium の問題 796060: 分析コードが html に含まれているときに、キャッシュ記憶域の値が更新されるたびに発生します。"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ-Web Api |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "スタックオーバーフロー: 不透明な応答に適用される制限は何ですか?"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
