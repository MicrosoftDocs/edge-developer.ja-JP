---
description: マニフェスト V2 から V3 への拡張機能の更新の詳細
title: マニフェスト V2 から V3 への拡張機能の更新の準備
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, edge extensions, browser extensions, addons, developer, manifest v3, migrate to manifest v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117831"
---
# マニフェスト v2 から v3 に拡張機能を更新する準備をする 

このドキュメントでは、マニフェスト v3 の一部として実装されている重要な変更点を示します。これは、Chromium拡張機能プラットフォームの次のバージョンです。 実装の進行に合わせ、このドキュメントを更新します。 マニフェスト v3 への拡張機能の移行に関する詳細なガイダンスについては、「マニフェスト V3 への移行」 [に移動します][Google_Migrate_to_MV3]。 

## リモートでホストされるコード  

現在、拡張機能はコードの一部をリモートでホストし、検証プロセス中に拡張パッケージの一部として含めることはできません。 これにより、拡張機能をストアに再送信せずにコードを柔軟に変更することができますが、インストール後にコードを利用できます。 アドオンリスト[Microsoft Edge検証][EdgeAddons]済み拡張機能を確認するために、拡張機能がリモートでホストされたコードを使用するのを禁止しています。 この変更により、拡張機能のセキュリティが高くなっています。 開発者は、拡張機能で検証のために使用されるコードをパッケージ化して提出する必要があります。 または、開発者はサンドボックス環境で eval() 関数 [を使用できます][sandboxingEval]。 

## 実行時ホストのアクセス許可  

インストール時に、拡張機能がすべてのサイトとコンテンツにアクセスするための一括アクセス許可を要求する場合があります。 これらのアクセス許可により、拡張機能は最小限の介入で動作し、ユーザーのプライバシーとセキュリティに対するリスクを生み出します。 透明性を向上させるために、ユーザーが実行時に Web サイトへのアクセスを許可または制限するためのコントロールを提供しています。 

## コンテンツ スクリプトでのクロスオリジン要求  

今日のコンテンツ スクリプトでは、Web サイトで許可されていないオリジンを含む任意のオリジンへのアクセスを要求できます。 この動作は、クロスオリジンの原則を壊します。 今後は、コンテンツ スクリプトが挿入するページと同じアクセス許可を持つ必要が生じ、潜在的なセキュリティの抜け穴を閉じます。 クロスオリジン要求を実行するには、バックグラウンド スクリプトを使用して応答をコンテンツ スクリプトに中継する必要があります。 これらの変更は使用可能で、フラグの背後に表示されます。 詳細については、このドキュメントに移動 [します][CORS]。 

## Web 要求 API  

Web 要求 API を[Declarative Net Request][DeclarativeNetRequestAPI] [API][WebRequestAPI]に置き換える予定ですが、引き続き Web 要求 API の観測機能を維持します。 拡張機能で Web 要求 API の観測機能が必要な特定のシナリオを除き、DNR API のみを使用することをお勧めします。 この変更は、機能豊富な宣言型機能を使用する拡張機能にプラスの影響を及ぼすと考えます。 より多くの拡張機能が DNR API に移行すると、この変更によりユーザーのプライバシーが向上し、拡張機能の使用に対する信頼が向上します。
企業は、エンタープライズ ポリシーによって管理される拡張機能に対して Web 要求 API のブロック動作を引き続き使用できます。 拡張機能ポリシーの詳細については、「Microsoft Edge –[ポリシー」 に移動します][MicrosoftEdgePolicies]。 

## バックグラウンド サービスワーカー  
 
サービス ワーカーは、Canary でテストできます。 拡張機能をバックグラウンド ページからサービス ワーカーに移行するには、「バックグラウンド ページからサービス ワーカーへの移行 [」を参照してください][ServiceWorkers]。 この変更が開発者&に与える影響を調査するために、この変更を評価しています。 この変更に関する詳細は、今後このドキュメントに追加されます。 

## これらの変更は、このサイトでいつMicrosoft Edge。

現在の宣言型ネット要求 API の実装は、Stable チャネルと Beta チャネルで利用できます。 開発者は、これらの変更をテストし、フィードバックを提供できます。 開発作業に貢献し、さらなる変更を調査します。 

| チャネル名 | 説明 |
|:--- |:--- |  
| Microsoft Edge 84 Stable | DNR API はテストに使用できます |  
| Microsoft Edge 85 Beta | ヘッダー変更のサポートが利用可能| 

この変更が変更されたChromium、開発者がコードを更新し、ストアに拡張機能を再発行できるよう、タイムラインを共有します。 

引き続きブログで更新プログラムを公開します。 これらの変更に関するフィードバックは [、TechCommunity を通じて提供できます][TechCommunity]。

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edgeアドオン"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技術Community"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "Chrome 拡張機能で eval を使用する。安全に。"
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "拡張機能コンテンツ スクリプトでのクロスオリジン要求への変更"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 要求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "宣言型 Net Request API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


