---
description: 開発マシン Web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。
title: ローカル サーバーにアクセスする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/25/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 51ef0d951d587d310b6474698924d9f87cf68607
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461263"
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
# <a name="access-local-servers"></a>ローカル サーバーにアクセスする  

開発マシン Web サーバーでサイトをホストし、Android デバイスからコンテンツにアクセスします。  

USB ケーブルと Microsoft Edge DevTools を使用して、開発マシンからサイトを実行し、Android デバイスでサイトを表示します。  

### <a name="summary"></a>要約  

*   ポート転送を使用すると、Android デバイス上の開発マシンで実行されている Web サーバーによってホストされるコンテンツを表示できます。  
*   Web サーバーがカスタム ドメインを使用している場合は、カスタム ドメイン マッピングを使用してそのドメインのコンテンツにアクセスする Android デバイスをセットアップします。  

## <a name="set-up-port-forwarding"></a>ポート転送のセットアップ  

ポート転送を使用すると、開発マシンで実行されている Web サーバーでホストされているコンテンツに Android デバイスがアクセスできます。  ポート転送は、開発マシン上の TCP ポートにマップするリッスン TCP ポートを Android デバイスに作成することで動作します。  ポート間のトラフィックは、Android デバイスと開発マシン間の USB 接続を介して移動します。そのため、接続はネットワーク構成に依存しません。  

ポート転送を有効にするには、次の方法を実行します。  

1.  開発マシン [と Android デバイス][RemoteDebuggingGettingStarted] の間でリモート デバッグをセットアップします。  完了したら、[デバイスの検査] ダイアログボックスの左側のメニューと [接続済み**** 状態] インジケーターに Android デバイス**が**表示されます。  
1.  DevTools **の [デバイスの** 検査] ダイアログで、[ポート転送] **を有効にします**。  
1.  [ルール **の追加] を選択します**。  
    
    :::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png" alt-text="ポート転送ルールの追加" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-add-rule.msft.png":::
       ポート転送ルールの追加  
    :::image-end:::  
    
1.  左側の **[デバイス ポート** ] テキスト ボックスに、Android デバイス上のサイトにアクセスできるポート番号 `localhost` を入力します。  たとえば、Enter からサイトにアクセスする場合 `localhost:5000` `5000` です。  
1.  右側の **[ローカル アドレス** ] テキスト ボックスに、開発マシンで実行されている Web サーバーでサイトがホストされている IP アドレスまたはホスト名を入力し、その後にポート番号を入力します。  たとえば、サイトが Enter で実行されている `localhost:7331` 場合 `localhost:7331` です。  
1.  **追加** を選びます。  
    
ポート転送がセットアップされます。  [デバイスの検査] ダイアログボックス内のデバイスのタブで、ポート転送の状態インジケーター **を確認** します。  

:::image type="complex" source="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png" alt-text="ポート転送の状態" lightbox="../media/remote-debugging-remote-devices-devices-port-forwarding-5000-edge-user-agent.msft.png":::
   ポート転送の状態  
:::image-end:::  

コンテンツを表示するには、Android デバイスで Microsoft Edge を開き、[デバイス ポート] フィールドで指定したポート `localhost` **に移動** します。  たとえば、フィールドに入力した `5000` 場合は、 を参照してください `localhost:5000` 。  

## <a name="map-to-custom-local-domains"></a>カスタム ローカル ドメインへのマップ  

カスタム ドメイン マッピングを使用すると、カスタム ドメインを使用している開発マシン上の Web サーバーから Android デバイス上のコンテンツを表示できます。  

たとえば、サイトがドメインでのみ動作するサードパーティの JavaScript ライブラリを使用するとします `microsoft-edge.devtools` 。  そのため、開発マシン上のファイルにエントリを作成して、このドメインを `hosts` `localhost` \(たとえば\) にマップ `127.0.0.1 microsoft-edge.devtools` します。  カスタム ドメイン マッピングとポート転送を設定した後、URL で Android デバイス上のサイトを表示します `microsoft-edge.devtools` 。  

### <a name="set-up-port-forwarding-to-proxy-server"></a>プロキシ サーバーへのポート転送のセットアップ  

カスタム ドメインをマップするには、開発マシンでプロキシ サーバーを実行する必要があります。  プロキシ サーバーの例は[、Charles、Squid、][CharlesWebDebuggingProxy][および Fiddler です][FiddlerWebDebuggingProxy]。 [][SquidOptimisingWebDelivery]  

プロキシへのポート転送を設定するには、次の方法を実行します。  

1.  プロキシ サーバーを実行し、使用しているポートを記録します。  
    
    > [!NOTE]
    > プロキシ サーバーと Web サーバーは、異なるポートで実行する必要があります。  
    
1.  Android デバイス [へのポート転送](#set-up-port-forwarding) を設定します。  [ローカル **アドレス] フィールド** に、プロキシ サーバーが `localhost:` 実行されているポートを入力します。  たとえば、ポートで実行されている場合は `8000` 、 に移動します `localhost:8000` 。  [デバイス **ポート]** フィールドに、Android デバイスでリッスンする番号 (など) を入力します `3333` 。  
    
### <a name="configure-proxy-settings-on-your-device"></a>デバイスでプロキシ設定を構成する  

次に、プロキシ サーバーと通信するために Android デバイスを構成する必要があります。  

1.  Android デバイスで、[設定] ****  >  **Wi-Fi に移動します**。  
1.  現在接続しているネットワークの名前を長押しします。  
    
    > [!NOTE]
    > プロキシ設定はネットワークごとに適用されます。  
    
1.  [ネットワーク **の変更] を選択します**。  
1.  [詳細設定 **] を選択します**。  プロキシ設定が表示されます。  
1.  [プロキシ] **メニューを選択** し、[手動] を **選択します**。  
1.  [プロキシの **ホスト名] フィールド** に「 」 と入力 `localhost` します。  
1.  [プロキシ **ポート] フィールド** に、前のセクションでデバイス ポートに入力した **ポート番号** を入力します。  
1.  [保存 **] を選択します**。  
    
これらの設定を使用すると、デバイスは、すべての要求を開発マシン上のプロキシに転送します。  プロキシはデバイスに代わって要求を行うので、カスタマイズしたローカル ドメインへの要求は適切に解決されます。  

開発マシンと同様に、Android デバイス上のカスタム ドメインにアクセスします。  

Web サーバーが標準以外のポートから実行されている場合は、Android デバイスからコンテンツを要求するときにポートを指定してください。  たとえば、Web サーバーがポートでカスタム ドメインを使用している場合、Android デバイスからサイトを表示するときに `microsoft-edge.devtools` `7331` URL を使用する必要があります `microsoft-edge.devtools:7331` 。  

> [!TIP]
> 通常の閲覧を再開するには、開発マシンから切断した後、Android デバイスのプロキシ設定を元に戻してください。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[RemoteDebuggingGettingStarted]: ./index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  

[CharlesWebDebuggingProxy]: https://www.charlesproxy.com "Charles Web デバッグ プロキシ"  

[SquidOptimisingWebDelivery]: https://www.squid-cache.org "squid : Web 配信の最適化"  

[FiddlerWebDebuggingProxy]: https://www.telerik.com/fiddler "Fiddler - 無料の Web デバッグ プロキシ"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/local-server)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
