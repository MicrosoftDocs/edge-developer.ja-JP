---
description: Adobe Flash を必要とするサイトでシームレスなユーザー エクスペリエンスを提供します。
title: フラッシュ - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Edge、Web 開発、フラッシュ
ms.openlocfilehash: 33ee1c782fc969b2251ed075a59d8fa61bf61831
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942035"
---
# Flash  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Adobe Flash は Web の一部で整合性が高い一部で、HTML5 が導入される前にブラウザーでリッチ コンテンツとアニメーションを有効にしています。  最新のブラウザーでは、Microsoft、Adobe、Google、Apple、Mozilla、その他の多くの他の多くは、Flash およびパフォーマンスとセキュリティが向上したサイトを有効にしています。  他のブラウザー ベンダーや Adobe とのパートナーシップを使用して、暗号化された[メ](https://developer.microsoft.com/microsoft-edge/platform/status/encryptedmediaextensions)ディア拡張機能、[メ](https://developer.microsoft.com/microsoft-edge/platform/status/mediasourceextensions)ディア ソース拡張機能、キャンバス[、Web オーディオ、リ](https://developer.microsoft.com/microsoft-edge/platform/status/webaudioapi)アルタイム通信など、HTML5[Canvas](https://developer.microsoft.com/microsoft-edge/platform/status/canvas)標準に移行することを強くおす[すめします](https://developer.microsoft.com/microsoft-edge/platform/status/webrtcobjectrtcapi)。  

Windows 10 Microsoft Edge の 2018 年 10 月リリースでは、2021 年[10 月以降にサポート](https://theblog.adobe.com/adobe-flash-update)終了の一部として取り上げている Flash Deprecation の取りを中止しています。 [covered](https://blogs.windows.com/msedgedev/2017/07/25)  2018 年 10 月リリースユーザーは、ポートの有効期限についてサイトで Flash を実行できるような必要があります。 [常に許可] オプションは使用できなくなり、ユーザーは、タブ セッションをまたいるサイト フラッシュ アクセス許可によって管理できなくなります。  

HTML5 標準に移行する場合、ユーザーが Windows 10 Creators Update の Microsoft Edge で Web サイトにアクセスした Web サイトを引き続き使用できるように、簡単な操作をいくつか実行できます。  

ページで Flash を使用していて、ユーザーがフラッシュを有効にしていない場合、通常、Microsoft Edge では、通常、アドレス バーに puzzle piece [アイコンが表示されます](https://blogs.windows.com/msedgedev/2016/12/14)。このブログに示されます。  ページの読み込み後に Flash コントロールを動的に追加する場合は、このピズル 円のアイコンが表示されない場合があります。  この場合は、Flash のプレゼンスをテストし、以下で説明するリンクを提供するのが最も有効です。  

すべてのユーザーが良いエクスペリエンスを得るために、標準的なメカニズムを使用してフラッシュのプレゼンスをテストします。  Microsoft Edge で Flash が利用できないことを報告する場合は [、Flash ダウンロード](http://get.adobe.com/flashplayer) リンクと [Flash ダウンロード画像を](http://www.adobe.com/legal/permissions/icons-web-logos.html#flashplayer) ユーザーに表示します。  ユーザーがリンクをクリックすると、Microsoft Edge \(および他のブラウザー\) がサイトで Flash Player を有効にするよう求められます。  Flash を有効にするプライマリ ドメインにリンクが表示されている必要があります。  ユーザーを他のドメインのページにリダイレクトしても、この機能は動作しません。  [推案されるエクスペリエ](https://microsoftedge.github.io/MicrosoftEdge-Documentation/flashclicktorun) ンスと対応するサンプル コードのデモ [を次に示します](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/docs/flashclicktorun)。  
