---
title: Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システムに統合する
description: Web アプリ マニフェストを使用してプログレッシブ Web アプリをオペレーティング システムに統合する方法について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 0063323b1fde94d84e70df51170726325dd0f2a9
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399100"
---
# <a name="use-the-web-app-manifest-to-integrate-your-progressive-web-app-into-the-operating-system"></a>Web アプリ マニフェストを使用して、プログレッシブ Web アプリをオペレーティング システムに統合する

Web サイトの Web アプリ マニフェストは、デバイスにインストールされた場合のプログレッシブ Web アプリ \(PWA\) の外観と動作を制御します。  最も基本的なレベルでは、マニフェストはアプリの名前、システム メニューでアプリを表すアイコン、およびタイトル バーでオペレーティング システム \(OS\) が使用するテーマの色に関する詳細を提供します。  マニフェストを使用すると、アプリがシステム上の他のネイティブ アプリのように動作する強力な機能のロックを解除することもできます。  

## <a name="use-shortcuts-to-provide-quick-access-to-features"></a>ショートカットを使用して機能にすばやくアクセスする  

ほとんどのオペレーティング システムでは、アプリのアイコンに接続されているコンテキスト メニューのショートカットを使用して、主要なアプリ機能にすばやくアクセスできます。  PWA でショートカットを使用するには、Web `shortcuts` アプリ マニフェストにプロパティを含める必要があります。  次のコード スニペットは、Web アプリ マニフェストでショートカットを定義する方法を示しています。  

```json
"shortcuts": [
    {
        "name": "Play Later",
        "description": "View the list of podcasts you saved for later",
        "url": "/play-later",
        "icons": [
            {
                "src": "/icons/play-later.svg",
                "type": "image/svg+xml",
                "purpose": "any"
            }
        ]
    },
    {
        "name": "Subscriptions",
        "description": "View the list of podcasts available in your subscription",
        "url": "/subscriptions?sort=desc"
    }
]
```  

完全な Web アプリ マニフェストに追加すると、前のコード スニペットを追加すると、アプリのアイコンのコンテキスト メニューで 2 つのショートカットが有効になります。  1 つ目の名前 `Play Later` はカスタム アイコンです。  プロパティは省略可能なので、2 番目の名前は付け `Subscriptions` 、 `icons` アイコンを持つ必要があります。  この `description` プロパティはオプションで、アクセシビリティの目的で追加情報を提供するために使用される場合があります。  

## <a name="identify-your-app-as-a-share-target"></a>アプリを共有ターゲットとして識別する

多くのオペレーティング システムを使用すると、ユーザーはリンクやファイルをネイティブ アプリケーションとすばやく共有できます。 プログレッシブ Web アプリは、Web アプリ マニフェストのメンバーを使用して、この `share_target` 機能にも参加できます。  を `share_target` 使用して、ページ \(form\に似た) と、ページに渡す必要がある `"action"` パラメーターを定義します。  次のコード スニペットは、使用方法の例を表示します `share_target` 。

```json
"share_target": {
    "action": "/share.html",
    "params": {
        "title": "name",
        "text": "description",
        "url": "link"
    }
}
```

Web アプリ マニフェストに追加すると、共有 `"/share.html"` のアクション ページとして確立されます。 さらに、そのアクション ページに渡される 3 つのパラメーターを定義 `"title"` します。 `"text"` `"url"`  これらのパラメーターは `"name"` 、ShareData オブジェクトの `"description"` 、、 `"link"` およびプロパティに [格納][GitHubWicgWebShareDomSharedata] されます。  既定では、アクション ページは GET 要求の一部としてパラメーターを受け取りますが、Web フォームと同様に、要求とエンコード `method` \(\) を `enctype` 指定できます。

## <a name="see-also"></a>関連項目  

Web アプリ マニフェストの詳細については、次の関連トピックの一覧に移動します。  

*   [Web アプリ マニフェスト][MDNWebAppManifests]  
*   [Web 共有ターゲット][GitHubWicgWebShareTarget]
*   [Web 共有][GithubW3cWebShare]
    
<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ のマニフェスト|MDN"  

[GitHubWicgWebShareTarget]: https://wicg.github.io/web-share-target "Web 共有ターゲット API |WICG"
[GitHubWicgWebShareDomSharedata]: https://wicg.github.io/web-share#dom-sharedata "ShareData ディクショナリ - Web Share API |WICG"  

[GithubW3cWebShare]: https://w3c.github.io/web-share/ "Web 共有 API |WICG"
