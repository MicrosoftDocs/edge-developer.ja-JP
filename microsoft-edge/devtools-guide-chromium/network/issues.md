---
description: Microsoft Edge DevTools のネットワークパネルでネットワークの問題を検出する方法について説明します。
title: ネットワーク問題ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ccd78c34a50bf235416df58aad28df9253b1b24e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993374"
---
<!-- Copyright Kayce Basques and Jonathan Garbee

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# ネットワークの問題に関するガイド   




このガイドでは、Microsoft Edge DevTools のネットワークパネルでネットワークの問題や最適化の機会を検出する方法について説明します。  

詳しく [は、「][NetworkPerformance] **ネットワーク** パネルの基本」をご覧ください。  

## キューに入っているまたは停止している要求   

**現象**  

6つの要求が同時にダウンロードされます。  その後、一連の要求はキューまたは停止されます。  最初の6つの要求のいずれかが完了したら、キュー内のいずれかの要求が開始されます。  

次の図の **ウォーターフォール** では、資産の最初の6つの要求が同時に開始され `edge-iconx1024.msft.png` ます。  それ以降の要求は、元の6つの処理が完了するまで停止します。  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="[ネットワーク] パネルのキューに入っている、または停止しているシリーズの例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   [ **ネットワーク** ] パネルのキューに入っている、または停止しているシリーズの例  
:::image-end:::  

**原因**  

1つのドメインで実行されている要求が多すぎます。  HTTP/1.0 または HTTP/1.1 接続の場合、Microsoft Edge では、ホストあたり最大6つの同時 TCP 接続を許可します。  

**修正**  

*   HTTP/1.0 または HTTP/1.1 を使用する必要がある場合は、ドメイン sharding を実装します。  
*   HTTP/2 を使用します。  HTTP/2 では domain sharding を使用しないでください。  
*   重要な要求が事前にダウンロードされるように、不要な要求を削除または保留します。  
    
## 最初のバイトまでの時間が遅い (TTFB)   

**現象**  

要求は、サーバーから最初のバイトを受信するまでに長い時間がかかります。  

次の図では、 **ウォーターフォール** の長い緑色のバーは、要求が長い時間待機していたことを示します。  これは、ネットワークの速度を制限し、遅延を追加するためにプロファイルを使用してシミュレートされました。  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="最初のバイトまでの時間が遅い要求の例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   最初のバイトまでの時間が遅い要求の例  
:::image-end:::  

**原因**  

*   クライアントとサーバー間の接続速度が遅い。  
*   サーバーの応答が遅くなります。  サーバーをローカルにホストして、接続またはサーバーが低速であるかどうかを確認します。  ローカルサーバーにアクセスしようとしても、最初のバイト \ (TTFB \) に時間がかかる場合は、サーバーの速度が遅くなります。  
    
**修正**  

*   接続速度が遅い場合は、CDN でコンテンツをホストするか、ホスティングプロバイダーを変更することを検討してください。  
*   サーバーの速度が遅い場合は、データベースクエリの最適化、キャッシュの実装、またはサーバー構成の変更を検討してください。  
    
## コンテンツのダウンロードが遅い   

**現象**  

リクエストのダウンロードには時間がかかります。  

次の図では、png の隣にある **ウォーターフォール** の長い青色のバーは、ダウンロードに時間がかかることを意味します。  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="ダウンロードに時間がかかる要求の例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   ダウンロードに時間がかかる要求の例  
:::image-end:::  

**原因**  

*   クライアントとサーバー間の接続速度が遅い。  
*   多くのコンテンツがダウンロードされています。  
    
**修正**  

*   コンテンツを CDN でホストするか、ホスティングプロバイダーを変更することを検討してください。  
*   要求を最適化して、送信するバイト数を減らします。  
    
## 知識の投稿  

このガイドに追加する必要があるネットワークの問題はありますか?  

*   [@EdgeDevTools][MicrosoftEdgeTweet]にツイートを送信します。  
*   **Send Feedback** ![ ][ImageSendFeedbackIcon] フィードバックや機能のリクエストについては、devtools で [フィードバックの送信 \ (フィードバックを送信 \)] または [\ (Windows \)] または [ `Alt` + `Shift` + `I` `Option` + `Shift` + `I` \ (macOS \)] を選択します。  
*   Docs リポジトリで[問題を開き][WebFundamentalsIssue]ます。  
    
<!--  
  


-->  

<!-- image links -->  

[ImageSendFeedbackIcon]: ../media/smile-icon.msft.png  

<!-- links -->  

[NetworkPerformance]: ./index.md "Microsoft Edge DevTools でネットワークアクティビティを検査する |Microsoft ドキュメント"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新しい問題-Microsoft のドキュメント/エッジ-開発者"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/network/issues) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Jonathan Garbee][JonathanGarbee] \ (Google Developer Expert for Web テクノロジ \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
