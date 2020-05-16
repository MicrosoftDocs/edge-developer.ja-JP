---
title: Web アプリマニフェストを使ってプログレッシブ Web アプリをオペレーティングシステムに統合する
description: Web アプリマニフェストを使って、プログレッシブ Web アプリをオペレーティングシステムに統合する方法について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: f493ae0c3cef3a1950b2207d66fef65055b2d959
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659294"
---
# Web アプリマニフェストを使ってプログレッシブ Web アプリをオペレーティングシステムに統合する

Web サイトの Web アプリマニフェストは、プログレッシブ Web アプリ \ (PWA) がデバイスにインストールされたときの外観と動作を制御します。  最も基本的なレベルでは、マニフェストは、アプリの名前、システムメニューでアプリを表すために使用するアイコン、オペレーティングシステム \ (OS \) がタイトルバーに使用するテーマの色について詳しく説明します。  マニフェストでは、システム上の他のネイティブアプリと同じようにアプリを動作させることができる強力な機能のロックを解除することもできます。  

## ショートカットを使用して機能にすばやくアクセスする  

ほとんどのオペレーティングシステムでは、アプリのアイコンに接続されたコンテキストメニューのショートカットを使用して、主要なアプリの機能にすばやくアクセスできます。  PWA のショートカットを使用するには、 `shortcuts` Web アプリマニフェストにプロパティを追加します。  次のコードスニペットは、web アプリマニフェストでショートカットを定義する方法を示しています。  

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

完全な Web アプリマニフェストに追加された場合、前のコードスニペットを追加すると、アプリのアイコンのコンテキストメニューで2つのショートカットが有効になります。  最初の名前には、 `Play Later` カスタムアイコンが付いています。  2番目の引数には、 `Subscriptions` `icons` プロパティが省略可能であるため、という名前が付けられ、アイコンはありません。  この `description` プロパティはオプションでもあり、アクセシビリティのために追加情報を提供するために使うことができます。  

## アプリを共有ターゲットとして識別する

多くのオペレーティングシステムでは、ネイティブアプリケーションでリンクやファイルを簡単に共有できます。 プログレッシブ Web アプリは、 `share_target` Web アプリマニフェストのメンバーを通じて、この機能にも参加できます。 Share_target を使って、"アクション" ページ (フォームと同様) と、それに渡す必要があるパラメーターを定義します。 次のコードスニペットは、の使い方の例を示して `share_target` います。

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

Web アプリマニフェストに追加されると、共有の操作ページとして "/¥ .html" が確立されます。 さらに、アクションページに渡される3つのパラメーターを定義します。これには、"title"、"text"、"url" があります。 これらのパラメーターは、"name"、"description"、"link [" の各](https://wicg.github.io/web-share#dom-sharedata)プロパティに保存されます。 既定では、アクションページは GET 要求の一部としてこれらのパラメーターを受け取りますが、web フォームの場合と同様に、要求 `method` とエンコードは \ (as) を指定でき `enctype` ます。

## 関連項目  

Web アプリマニフェストの詳細については、次の関連するトピックの一覧を参照してください。  

* [Web App マニフェスト][MDNWebAppManifests]  
* [Web 共有ターゲット][WICGShareTarget]
* [Web 共有][WICGShare]

<!-- links -->  

[MDNWebAppManifests]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  
[WICGShareTarget]: https://wicg.github.io/web-share-target/ "Web 共有ターゲット API |WICG"
[WICGShare]: https://w3c.github.io/web-share/ "Web Share API |WICG"
