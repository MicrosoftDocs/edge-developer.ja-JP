---
description: サービスの作業者の機能強化とそれぞれの使い方について説明します。
title: サービスワーカーの機能強化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、service worker、PWA
ms.openlocfilehash: 4e1b43235ccd7b108d2aadd1c803aa3276fa1265
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190039"
---
# サービスワーカーの機能強化  

この記事では、サービスの担当者と、各 [ユーザー][MdnServiceWorkerApi] を通過するネットワーク要求の改善について説明します。  **Service worker の機能強化**は、**ネットワーク**、**アプリケーション**、**ソース**の各ツールに含まれています。  この改善には、次のタスクが含まれます。  

*   サービスワーカーのタイムラインに基づいてデバッグします。  
    *   要求の開始とブートストラップの期間。  
    *   サービスワーカー登録に更新します。  
    *   [Fetch イベント][MdnFetchEvent]ハンドラーを使った要求の実行時。  
    *   クライアントを読み込むすべての fetch イベントのランタイム。  
*   Fetch イベントハンドラーのランタイムの詳細、イベントハンドラーのインストール、イベントハンドラーのアクティブ化について説明します。  
*   [ページスクリプト情報](#sources)を使った fetch イベントハンドラーのステップインとアウト。  

このエクスペリエンスは、3種類の開発者ツールにわたります。  

1.  [ネットワーク](#network)ツール。  サービスワーカーを通じて実行されるネットワーク要求を選択し、 **タイミング** ツールでサービスワーカーの対応するタイムラインにアクセスします。  
1.  [アプリケーション](#application)ツール。  サービスワーカーをデバッグするには、 **サービスワーカー** ツールに移動します。  
1.  [ソース](#sources)ツール。  Fetch イベントハンドラーにステップインするときに、ページのスクリプト情報にアクセスします。  

## ネットワーク  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="ネットワークツールのサービスワーカーのタイムライン" lightbox="../media/sw-network-timeline.msft.png":::
   ネットワークビュー  
:::image-end:::  

**ネットワーク**ツールの service worker デバッグ機能にアクセスするには、次のいずれかの操作を実行します。  

*   **ネットワーク**ツールで直接アクセスする。  
*   **アプリケーション**ツールで開始されました。  
    
### ルーティングを要求する  

要求のルーティングをより簡単にするために、タイムラインでは、サービスワーカーの起動時と fetch イベントが表示されるようになりました `respondWith` 。  サービスワーカーを通じて渡されたネットワーク要求をデバッグし、視覚化するには、次の操作を実行します。  

1.  サービスワーカーを通じて行われたネットワーク要求を選択します。  
1.  **タイミング**ツールを開きます。  
    
### イベントの取得  

Fetch イベントの詳細については、 `respondWith` の左にあるドロップダウン矢印を選択して `respondWith` ください。  受信した **元の要求** と **応答**の詳細については、対応するドロップダウン矢印を参照してください。  

## Application  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="アプリケーションビュー" lightbox="../media/sw-application-timeline.msft.png":::
   アプリケーションビュー  
:::image-end:::  

### サービスワーカーの更新タイムライン  

Microsoft Edge DevTools チームは、サービスワーカーの更新ライフサイクルを反映するために、 **アプリケーション** ツールにタイムラインを追加しました。  インストールイベントとライセンス認証イベントが表示されます。  各イベントには、より詳しい情報を提供するためのドロップダウン矢印があります。  

### ルーティングイベントとフェッチイベントを要求する  

これで、コンソールのドロアーから **ネットワーク** ツールを介してサービスワーカーのタイムラインにアクセスできるようになりました。  この機能は、パフォーマンスを向上させると共に、UI の重複を最小限に抑え、より包括的なデバッグエクスペリエンスを作成します。  

1.  デバッグしているサービスワーカーを開きます。  
1.  [ **ネットワーク** ] ボタンを選んで、 [要求ルーティングエクスペリエンス](#network)を開きます。  
1.  Fetch イベントの要求と応答の情報については、返答 **Dwith** ドロップダウンを使います。  

**ネットワーク**ツールには、デバッグしているサービスワーカーを通じて発生したネットワーク要求が表示されます。  自動フィルターを使用すると、調査を絞り込むことができます。

## Sources  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM ビュー" lightbox="../media/sw-sources.msft.png":::
   DOM ビュー  
:::image-end:::  

さらに多くのスタック情報を見つけるには、fetch ハンドラーにブレークポイントを設定します。  詳細情報は、ページスクリプトでリソースが要求された場所を示します。  デバッガーが fetch ハンドラー内で一時停止すると、パネルの右側にスタック情報がまとめて表示されます。  その後は、スタックフレーム内を移動することができます。  

### 今後の作業  

Microsoft Edge DevTools チームは、キャッシュの詳細をさらに開発することを計画しており、 [プログレッシブ Web アプリケーション][MdnProgressiveWebApps] 開発者向けのサービスワーカーのデバッグエクスペリエンスを向上させるその他の方法について調査しています。  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "プログレッシブ web アプリ (PWAs) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
