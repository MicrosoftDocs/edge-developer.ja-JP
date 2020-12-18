---
description: Adobe Flash を必要とするサイトでシームレスなユーザー エクスペリエンスを提供します。
title: Flash - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, フラッシュ
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a81fb0808897e1763a55c3e97bc604d276a7b9f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234899"
---
# Flash  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Adobe Flash は何十年もの間、Web の重要な部分であり、HTML5 が導入される前からブラウザーでリッチ コンテンツとアニメーションを実現してきました。  最新のブラウザーでは、Microsoft、Adobe、Google、Apple、Mozilla などの多くの Web 標準によって、サイトが Flash を使用せずにこれらのエクスペリエンスを超え、パフォーマンスとセキュリティが向上しています。  他のブラウザー ベンダーや Adobe と協力して、開発者が暗号化されたメディア拡張機能、メディア ソース拡張機能、[キャンバス](https://developer.microsoft.com/microsoft-edge/platform/status/canvas)[、Web](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)オーディオ、リアルタイム[](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions)通信などの HTML5 標準に移行するように強く推奨[します。](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi) [](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions)  

Windows 10 Microsoft Edge の 2018 年 10 月[](https://blogs.windows.com/msedgedev/2017/07/25)リリースでは[、Adobe](https://theblog.adobe.com/adobe-flash-update)の 2021 年以降のサポート終了の発表の一環として取り上めた Flash Deprecation の取り組みを継続しています。  Oct 2018 リリースでは、ユーザーはタブの有効期間中、サイトで Flash の実行を明示的に許可する必要があります。 永続的な Always Allow オプションは使用できなくなったので、ユーザーはタブ セッションにわたるサイトごとの Flash アクセス許可を管理できません。  

HTML5 標準に移行する場合、ユーザーが Windows 10 Creators Update の Microsoft Edge を使用して Web サイトにアクセスする前向きなエクスペリエンスを提供するために、いくつかの簡単な操作を実行できます。  

Flash がページで使用されているが、ユーザーが有効にしていない場合、Microsoft Edge は通常、このブログに示すようにアドレス バーにパズルの一部のアイコン [を表示します](https://blogs.windows.com/msedgedev/2016/12/14)。  ページの読み込み後に Flash コントロールを動的に追加する場合は、このパズルの一部のアイコンが表示されない可能性があります。  この場合は、Flash の有無をテストし、以下に示すリンクを提供する方法が最適です。  

すべてのユーザーに優れたエクスペリエンスを提供するには、標準のメカニズムを使用して引き続き Flash の有無をテストします。  Microsoft Edge で Flash が使用できないと報告された場合は [、Flash](http://get.adobe.com/flashplayer) ダウンロード リンクと Flash ダウンロード [イメージをユーザー](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer) に提示します。  ユーザーがリンクをクリックすると、Microsoft Edge \(および他のブラウザー\) がサイトの Flash Player を有効にするように求めるメッセージを表示します。  リンクは、Flash を有効にするプライマリ ドメインに表示する必要があります。  ユーザーを他のドメインのページにリダイレクトしても機能しません。  [推奨されるエクスペリエンスと対応](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun) するサンプル コードのデモを [次に示します](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)。  
