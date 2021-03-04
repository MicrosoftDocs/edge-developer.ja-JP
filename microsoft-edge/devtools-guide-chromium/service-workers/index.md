---
description: Service Worker の機能強化とそれぞれの使い方について説明します。
title: サービス ワーカーの機能強化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, service worker, PWA
ms.openlocfilehash: 2f32155d1d28d1e65ad29abfe58a414f3e3c6ed7
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387278"
---
# <a name="service-worker-improvements"></a>サービス ワーカーの機能強化  

この記事では、サービス ワーカーを操作するための開発者ツールの改善[][MdnServiceWorkerApi]と、各サービス ワーカーを通過するネットワーク要求について説明します。  サービス**ワーカーの機能強化は、[** ネットワーク **]、[****アプリケーション**]、および [ソース]**ツールにあります**。  この機能強化により、以下のタスクが簡略化されます。  

*   サービス ワーカーのタイムラインに基づいてデバッグします。  
    *   ブートストラップの要求の開始と期間。  
    *   サービス ワーカー登録に更新します。  
    *   フェッチ イベント ハンドラーを使用した [要求の][MdnFetchEvent] ランタイム。  
    *   クライアントを読み込むすべてのフェッチ イベントのランタイム。  
*   フェッチ イベント ハンドラーの実行時の詳細を確認し、イベント ハンドラーをインストールし、イベント ハンドラーをアクティブ化します。  
*   ページ スクリプト情報を使用してフェッチ イベント ハンドラーにステップ [アウトします](#sources)。  
    
エクスペリエンスは、3 つの異なる開発者ツールにまたがっています。  

1.  ネットワーク [ツール](#network) 。  サービス ワーカーを介して実行されるネットワーク要求を選択し、タイミング ツールでサービス ワーカーの対応するタイムラインに **アクセス** します。  
1.  アプリケーション [ツール](#application) 。  サービス ワーカーをデバッグするには、サービス ワーカー **ツールに移動** します。  
1.  [ [ソース]](#sources) ツール。  フェッチ イベント ハンドラーにステップ インするときにページ スクリプト情報にアクセスします。  
    
## <a name="network"></a>ネットワーク  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="ネットワーク ツールのサービス ワーカー タイムライン" lightbox="../media/sw-network-timeline.msft.png":::
   ネットワーク ビュー  
:::image-end:::  

ネットワーク ツールでサービス ワーカーのデバッグ機能に **アクセスするには** 、次のいずれかの操作を実行します。  

*   ネットワーク ツールで **直接アクセス** します。  
*   アプリケーション ツール **で開始** します。  
    
### <a name="request-routing"></a>要求ルーティング  

要求ルーティングを視覚化しやすくするために、タイムラインにサービス ワーカーの起動とフェッチ イベントが `respondWith` 表示されます。  サービス ワーカーを介して渡されたネットワーク要求をデバッグおよび視覚化するには、次のアクションを実行します。  

1.  サービス ワーカーを経由したネットワーク要求を選択します。  
1.  タイミング ツール **を開** きます。  
    
### <a name="fetch-events"></a>イベントのフェッチ  

フェッチ イベントの詳細 `respondWith` については、左側のドロップダウン矢印を選択します `respondWith` 。  元の要求と **受信した応答** の詳細については **、対応する**ドロップダウン矢印を使用します。  

## <a name="application"></a>Application  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="アプリケーション ビュー" lightbox="../media/sw-application-timeline.msft.png":::
   アプリケーション ビュー  
:::image-end:::  

### <a name="service-worker-update-timeline"></a>サービス ワーカーの更新タイムライン  

Microsoft Edge DevTools チームは、サービス**** ワーカーの更新ライフサイクルを反映するために、アプリケーション ツールにタイムラインを追加しました。  インストールイベントとライセンス認証イベントが表示されます。  各イベントには、詳細を示す対応するドロップダウン矢印があります。  

### <a name="request-routing-and-fetch-events"></a>ルーティングイベントとフェッチ イベントの要求  

これで、コンソール ドロワーのネットワーク ツールを**** 使用してサービス ワーカーのタイムラインにアクセスできます。  この機能は、パフォーマンスを向上し、UI の重複を最小限に抑え、より包括的なデバッグ エクスペリエンスを作成します。  

1.  デバッグ中のサービス ワーカーを開きます。  
1.  [ネットワーク] **ボタンを** 選択して、要求ルーティング [エクスペリエンスを開きます](#network)。  
1.  イベント要求と **応答情報をフェッチするには、respondWith** ドロップダウンを使用します。  

ネットワーク **ツール** には、デバッグ中のサービス ワーカーを経由したネットワーク要求が表示されます。  自動フィルターは、探索を絞り込む方法です。

## <a name="sources"></a>Sources  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM ビュー" lightbox="../media/sw-sources.msft.png":::
   DOM ビュー  
:::image-end:::  

スタック情報の詳細を見つけるには、フェッチ ハンドラーでブレーク ポイントを設定します。  詳細は、ページ スクリプトでリソースが要求される場所につながる。  デバッガーがフェッチ ハンドラー内で一時停止すると、結合されたスタック情報が右側のパネルに表示されます。  その後、スタック フレーム内を移動できます。  

### <a name="future-work"></a>今後の作業  

Microsoft Edge DevTools チームは、キャッシュの詳細をさらに開発し、 [プログレッシブ Web][MdnProgressiveWebApps] アプリケーション開発者向けのサービス ワーカー デバッグ エクスペリエンスを向上させる方法を検討しています。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "プログレッシブ Web アプリ (PWAs) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
