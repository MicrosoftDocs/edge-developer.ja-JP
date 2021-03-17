---
description: Microsoft Edge DevTools の [ネットワーク] パネルでネットワークの問題を検出する方法について説明します。
title: ネットワーク問題ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 9b92ca7b759fab80d7d829b31f605ccb8062a816
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439620"
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

# <a name="network-issues-guide"></a>ネットワーク問題ガイド  

このガイドでは、Microsoft Edge DevTools の [ネットワーク] パネルでネットワークの問題や最適化の機会を検出する方法について説明します。  

ネットワーク ツールの基本を確認 **するには、[スタート** ] に [移動します][NetworkPerformance]。  

## <a name="queued-or-stalled-requests"></a>キューに入れまたは停止している要求  

**現象**  

6 つの要求が同時にダウンロードされています。  その後、一連の要求がキューに入れられます。または停止します。  最初の 6 つの要求の 1 つが終了すると、キュー内の要求の 1 つが開始されます。  

次の **図のウォーター** フォールでは、アセットの最初の 6 つの要求が `edge-iconx1024.msft.png` 同時に開始されます。  以降の要求は、元の 6 つの要求の 1 つが終了するまで停止します。  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="ネットワーク パネルのキューに入れまたは停止している系列の例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   ネットワーク ツールのキューに入れまたは停止している系列**の例**  
:::image-end:::  

**原因**  

1 つのドメインで要求が多すぎます。  HTTP/1.0 または HTTP/1.1 接続では、Microsoft Edge はホストごとに最大 6 つの同時 TCP 接続を許可します。  

**修正**  

*   HTTP/1.0 または HTTP/1.1 を使用する必要がある場合は、ドメイン シャーディングを実装します。  
*   HTTP/2 を使用します。  HTTP/2 でドメイン シャーディングを使用しない。  
*   重要な要求が以前にダウンロードされるので、不要な要求を削除または延期します。  
    
## <a name="slow-time-to-first-byte-ttfb"></a>最初のバイトへの低速時間 (TTFB)  

**現象**  

要求は、サーバーから最初のバイトを受け取るのを待つのに長い時間を費やします。  

次の図では、ウォーターフォールの長い緑色のバー **は** 、要求が長い時間待っていたかどうかを示しています。  これは、プロファイルを使用してネットワーク速度を制限し、遅延を追加するためにシミュレートされました。  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="時間が遅い最初のバイトの要求の例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   時間が遅い最初のバイトの要求の例  
:::image-end:::  

**原因**  

*   クライアントとサーバー間の接続が遅い。  
*   サーバーの応答が遅い。  サーバーをローカルでホストして、低速の接続またはサーバーかどうかを判断します。  ローカル サーバーにアクセスするときに最初のバイト \(TTFB\) への時間が遅い場合は、サーバーの速度が低下します。  
    
**修正**  

*   接続が遅い場合は、CDN でのコンテンツのホストやホスティング プロバイダーの変更を検討してください。  
*   サーバーの速度が遅い場合は、データベース クエリの最適化、キャッシュの実装、またはサーバー構成の変更を検討してください。  
    
## <a name="slow-content-download"></a>コンテンツのダウンロードが遅い  

**現象**  

要求のダウンロードには長い時間が必要です。  

次の図では、png の横にあるウォーターフォール**** の長い青いバーは、ダウンロードに長い時間がかかったという意味です。  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="ダウンロードに長い時間がかかる要求の例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   ダウンロードに長い時間がかかる要求の例  
:::image-end:::  

**原因**  

*   クライアントとサーバー間の接続が遅い。  
*   多くのコンテンツがダウンロードされています。  
    
**修正**  

*   CDN でのコンテンツのホストやホスティング プロバイダーの変更を検討してください。  
*   要求を最適化して送信するバイト数を少なくします。  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback](../media/smile-icon.msft.png)\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[NetworkPerformance]: ./index.md "Microsoft Edge DevTools サーバーでネットワーク アクティビティを|Microsoft Docs"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新しい問題 - Microsoft Docs/Edge Developer"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/network/issues)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
