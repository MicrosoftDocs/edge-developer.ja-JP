---
description: Adobe Flash が必要なサイトでシームレスなユーザーエクスペリエンスを提供します。
title: 開発ガイド-Flash
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、flash
ms.openlocfilehash: b3e2efe142142b7cdf233acfc4e915cd320b556d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568834"
---
# フラッシュ

Adobe Flash は、数十年にわたり web の重要な部分であり、HTML5 が導入される前以降、ブラウザーでリッチコンテンツとアニメーションを実現しています。 最新のブラウザーでは、Microsoft、アドビ、Google、Apple、Mozilla などの web 標準 pioneered が、Flash を使用せずに、またパフォーマンスとセキュリティを向上させることができるようになりました。 他のブラウザーベンダーとアドビシステムズ社との連携により、開発者は、[暗号化されたメディア拡張](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions)機能[、メディアソース拡張機能](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions)、[キャンバス](https://developer.microsoft.com/microsoft-edge/platform/status/canvas)、 [Web オーディオ](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)、[リアルタイム通信](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi)などの HTML5 標準に移行することを強くお勧めします。

2018年10月の Windows 10 リリースでは、Microsoft Edge は、2021の後の[Adobe のサポート終了のお知らせ](https://theblog.adobe.com/adobe-flash-update/)の一部として[カバー](https://blogs.windows.com/msedgedev/2017/07/25/flash-on-windows-timeline/#9mCF959eQEK0poo5.97)されていた Flash の廃止の取り組みを継続しています。 10月の2018リリースでは、ユーザーはタブの有効期間中に、サイトでのフラッシュの実行を明示的に許可する必要があります。永続的な [常に許可] オプションは利用できなくなり、ユーザーはタブセッションにわたるサイト内のフラッシュアクセス許可を管理することができなくなります。

HTML5 標準への移行に応じて、Windows 10 の作成者の更新プログラムで、Microsoft Edge を使用して web サイトにアクセスすることができるようにするための簡単な方法がいくつかあります。 

ページで Flash が使用されていても、ユーザーが有効にしていない場合、Microsoft Edge では通常、[このブログ](https://blogs.windows.com/msedgedev/2016/12/14/edge-flash-click-run/#41svu6EMwKIAaigx.97)に示すように、アドレスバーにパズルピースアイコンが表示されます。 ページの読み込み後にフラッシュコントロールを動的に追加している場合は、このパズルのピースアイコンが表示されないことがあります。この場合は、Flash の存在をテストし、次に示すようにリンクを提供することをお勧めします。

すべてのユーザーが適切なエクスペリエンスを実現するには、標準のメカニズムを使用して、フラッシュの有無をテストしてください。 Microsoft Edge で Flash が使用できないという報告があった場合は、[フラッシュダウンロードリンク](http://get.adobe.com/flashplayer)と[フラッシュダウンロードイメージ](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer)をユーザーに提示します。 ユーザーがリンクをクリックすると、Microsoft Edge (およびその他のブラウザー) には、サイトの Flash Player を有効にするために必要なメッセージが表示されます。 Flash を有効にするプライマリドメインにリンクが表示されている必要があります。 他のドメインのページにユーザーをリダイレクトする場合は、この機能は使用できません。  ここでは、提案されたエクスペリエンスと対応する[サンプルコード](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)の[デモを示し](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun/)ます。
