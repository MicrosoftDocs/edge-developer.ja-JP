---
title: ローカルサーバーへのアクセス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c038e8b7f612f4c2185ae1c62a08d32b72f8aa0d
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611827"
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





# ローカルサーバーへのアクセス   




開発用コンピューターの web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。  

USB ケーブルと Microsoft Edge DevTools を使用して、開発用コンピューターからサイトを実行し、Android デバイスでサイトを表示します。  

### まとめ  

*   ポート転送を使用すると、開発用コンピューターで実行されている web サーバーによってホストされているコンテンツを Android デバイスで表示することができます。  
*   Web サーバーでカスタムドメインを使用している場合は、カスタムドメインマッピングを使って、そのドメインのコンテンツにアクセスできるように Android デバイスをセットアップします。  

## ポート転送を設定する   

ポート転送を使用すると、Android デバイスは、開発用コンピューターで実行されている web サーバーでホストされているコンテンツにアクセスできます。  ポート転送は、開発用コンピューターの TCP ポートにマップされている、Android デバイスでリスニング TCP ポートを作成することによって機能します。  ポート間のトラフィックは、Android デバイスと開発マシン間の USB 接続を通じて移動するため、接続はネットワーク構成に依存しません。  

ポート転送を有効にするには:  

1.  開発用コンピューターと Android デバイスの間で[リモートデバッグ][RemoteDebuggingGettingStarted]をセットアップします。  完了すると、[**デバイスの検査**] ダイアログボックスと [**接続**状態] インジケーターの左側のメニューに Android デバイスが表示されます。  
1.  DevTools の [**デバイスの検査**] ダイアログで、**ポート転送**を有効にします。  
1.  [**ルールの追加**] を選びます。  
    
    > ##### 図 1  
    > ポート転送ルールを追加する  
    > ![ポート転送ルールを追加する][ImageAddRule]  
    
1.  左側の [**デバイスポート**] ボックスに、 `localhost` Android デバイスでサイトにアクセスできるようにするポート番号を入力します。  たとえば、enter からサイトにアクセスする必要があるとし `localhost:5000` `5000` ます。  
1.  右側の [**ローカルアドレス**] ボックスに、開発用コンピューターで実行されている web サーバーでサイトがホストされる IP アドレスまたはホスト名を入力し、その後にポート番号を入力します。  たとえば、サイトが enter で実行されている場合です `localhost:7331` `localhost:7331` 。  
1.  **[追加]** をクリックします。  

ポート転送が設定されました。  [**デバイスの検査**] ダイアログボックスで、デバイスのタブの [ポートフォワード] のステータスインジケーターを確認します。  

> ##### 図 2  
> ポート転送の状態  
> ![ポート転送の状態][ImagePortForwardingStatus]  

コンテンツを表示するには、Android デバイスで Microsoft Edge を開き、[ `localhost` **デバイスポート**] フィールドに指定したポートに移動します。  たとえば、フィールドに入力した場合は、に `5000` アクセス `localhost:5000` します。  

## カスタムのローカルドメインにマップする   

カスタムドメインマッピングを使用すると、カスタムドメインを使用している開発用コンピューター上の web サーバーから Android デバイスのコンテンツを表示できます。  

たとえば、ドメインでのみ動作するサードパーティの JavaScript ライブラリをサイトで使用しているとし `microsoft-edge.devtools` ます。  このため、 `hosts` 開発用コンピューター上のファイルに、このドメインをマッピングするためのエントリを作成し `localhost` ます (例 `127.0.0.1 microsoft-edge.devtools` \)。  カスタムドメインマッピングとポート転送を設定した後、URL で Android デバイスのサイトを表示し `microsoft-edge.devtools` ます。  

### プロキシサーバーへのポート転送を設定する  

カスタムドメインを対応付けるには、開発用コンピューターでプロキシサーバーを実行する必要があります。  プロキシサーバーの例としては、[チャールズ][CharlesWebDebuggingProxy]、 [Squid][SquidOptimisingWebDelivery]、 [Fiddler][FiddlerWebDebuggingProxy]があります。  

プロキシへのポート転送を設定するには、次の操作を行います。  

1.  プロキシサーバーを実行して、使用しているポートを記録します。  
    
    > [!NOTE]
    > プロキシサーバーと web サーバーは、異なるポートで実行されている必要があります。  
    
1.  Android デバイスへの[ポート転送](#set-up-port-forwarding)を設定します。  [**ローカルアドレス**] フィールドに「」と入力し、 `localhost:` その後にプロキシサーバーが実行されているポートを入力します。  たとえば、ポートで実行されている場合は、に `8000` アクセス `localhost:8000` します。  [**デバイスポート**] フィールドに、Android デバイスでリッスンする番号 (など) を入力し `3333` ます。  

### デバイスのプロキシ設定を構成する  

次に、プロキシサーバーと通信するために Android デバイスを構成する必要があります。  

1.  Android デバイスの場合は、[**設定**] に移動  >  **Wi-Fi**します。  
1.  Long-現在接続しているネットワークの名前を押します。  
    
    > [!NOTE]
    > プロキシ設定はネットワークごとに適用されます。  
    
1.  [**ネットワークの変更**] を選びます。  
1.  [**詳細オプション**] を選択します。  プロキシ設定が表示されます。  
1.  [**プロキシ**] メニューを選択し、[**手動**] を選択します。  
1.  [ **Proxy hostname** ] フィールドに、「」と入力し `localhost` ます。  
1.  [**プロキシポート**] フィールドに、前のセクションの「**デバイスポート**」に入力したポート番号を入力します。  
1.  **[保存]** を選びます。  

これらの設定を使用すると、デバイスは、開発用コンピューター上のプロキシにすべての要求を転送します。  プロキシによってデバイスの代わりに要求が行われるため、カスタマイズしたローカルドメインへの要求が適切に解決されます。  

開発用コンピューターの場合と同様に、Android デバイスでカスタムドメインにアクセスできるようになりました。  

Web サーバーが標準以外のポートを使用している場合は、Android デバイスからコンテンツを要求するときに必ずポートを指定してください。  たとえば、web サーバーがポートでカスタムドメインを使用している場合 `microsoft-edge.devtools` `7331` 、Android デバイスからサイトを表示すると、その URL を使用する必要があり `microsoft-edge.devtools:7331` ます。  

> [!TIP]
> 通常の閲覧を再開するには、開発用コンピューターから切断した後で、Android デバイスのプロキシ設定を元に戻してください。  

<!--  -->  



<!-- image links -->  

[ImageAddRule]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png "図 1: ポート転送ルールを追加する"  
[ImagePortForwardingStatus]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png "図 2: ポート転送の状態"  

<!-- links -->  

[RemoteDebuggingGettingStarted]: /microsoft-edge/devtools-guide-chromium/remote-debugging/index "Android デバイスのリモートデバッグの概要"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "チャールズ Web デバッグプロキシ"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid: Optimising Web 配信"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler Free Web デバッギングプロキシ"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server)にあり、 [Kayce basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) および[Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
