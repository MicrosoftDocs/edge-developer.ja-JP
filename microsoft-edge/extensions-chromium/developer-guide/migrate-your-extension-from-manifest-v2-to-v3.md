---
description: マニフェスト V2 から V3 への拡張機能の更新について説明します。
title: マニフェスト V2 から V3 に拡張機能を更新するための準備をする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: エッジ chromium、拡張機能開発、edge extensions、ブラウザー拡張機能、アドオン、開発者、マニフェスト v3、マニフェスト v3 への移行
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117831"
---
# マニフェスト v2 から v3 に拡張機能を更新するための準備をする 

このドキュメントでは、Chromium Extensions プラットフォームの次のバージョンである、マニフェスト v3 の一部として実装されている重要な変更を示します。 このドキュメントは、実装の進行に応じて更新されます。 拡張機能をマニフェスト v3 に移行する方法の詳細については、「 [マニフェスト v3 への移行][Google_Migrate_to_MV3]」を参照してください。 

## リモートでホストされるコード  

現時点では、拡張機能は、コードの一部をリモートでホストすることができます。また、検証プロセス中に拡張機能パッケージの一部として含めることはできません。 この方法では、拡張機能をストアに再送信せずにコードを変更する柔軟性が提供されますが、インストール後にコードを悪用することができます。 [Microsoft Edge アドオン][EdgeAddons]に、検証済みの拡張機能を表示させるには、リモートでホストされているコードの使用を禁止します。 この変更により、拡張機能が強化されます。 開発者は、検証のために拡張機能によって使用されるすべてのコードをパッケージ化して送信する必要があります。 または、開発者は、 [サンドボックス環境][sandboxingEval]で eval () 関数を使うことができます。 

## 実行時のホストのアクセス許可  

インストール時に、拡張機能で、すべてのサイトとコンテンツにアクセスするための一括アクセス許可を要求することができます。 これらのアクセス許可では、最小限の操作で拡張機能を使用し、ユーザーのプライバシーとセキュリティに対するリスクを作成することができます。 透過性を高めるために、ユーザーが実行時に web サイトへのアクセスを許可または制限するためのコントロールを提供しています。 

## コンテンツスクリプトでの cross-origin 要求  

今日のコンテンツスクリプトでは、web サイトで許可されていない元のものを含む、任意の起点へのアクセスを要求することができます。 この動作により、クロスオリジンの原則が中断します。 今後は、コンテンツスクリプトが挿入されたページと同じアクセス許可を持つようにする必要があります。これにより、潜在的なセキュリティ loophole が終了します。 クロスオリジン要求を実行するには、バックグラウンドスクリプトを使用して、応答をコンテンツスクリプトに戻す必要があります。 これらの変更は、フラグと共に使用できます。 詳細については、この [ドキュメント][CORS]に移動してください。 

## Web 要求 API  

[Web 要求 api][WebRequestAPI]は[宣言型のネット要求 api][DeclarativeNetRequestAPI]に置き換えていますが、引き続き web 要求 api の observational 機能は維持されます。 ただし、Web 要求 API の observational 機能が拡張機能で必要となる特定のシナリオについては、「Api のみを使うことをお勧めします。 この変更は、機能豊富な宣言機能を使用する拡張機能に対してプラスの影響を与えると思われます。 この変更により、この変更によって、拡張機能の使用に対する信頼が強化され、ユーザーのプライバシーが向上します。
エンタープライズポリシーによって管理される拡張機能については、企業は引き続き Web 要求 API のブロッキング動作を使うことができます。 拡張ポリシーの詳細については、「 [Microsoft Edge –ポリシー][MicrosoftEdgePolicies]」を参照してください。 

## バックグラウンドサービスのワーカー  
 
サービスワーカーは、カナリアでテストできます。 拡張機能をバックグラウンドページからサービスワーカーに移行する方法については、「 [バックグラウンドページからサービスワーカーへの移行][ServiceWorkers]」を参照してください。 この変更が開発者とユーザーの両方にもたらす影響を調査 & 検討しています。 この変更についての詳細は、今後このドキュメントに追加します。 

## Microsoft Edge でこれらの変更を利用できるようになるのはいつですか?

現在の宣言型の net 要求 API の実装は、microsoft の安定性とベータチャネルで利用できます。 開発者は、これらの変更をテストし、フィードバックを提供できます。 開発作業に貢献し、さらに変更を調査します。 

| チャネル名 | 説明 |
|:--- |:--- |  
| Microsoft Edge 84 (安定) | 確認のためのお勧め API を使用できます |  
| Microsoft Edge 85 ベータ版 | ヘッダー変更のサポートを利用できます| 

Chromium に変更が加えられた場合は、タイムラインを共有して、開発者がコードを更新したり、ストアの拡張機能を再発行したりできるようにします。 

引き続き、弊社のブログに更新プログラムを公開します。 このような変更については、「」 [コミュニティ][TechCommunity]を通じてお客様にご意見をお寄せください。

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edge アドオン"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技術コミュニティ"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "Chrome の拡張機能で eval を使います。なく."
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "拡張コンテンツスクリプトでの cross-origin 要求の変更"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 要求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "宣言型ネットワーク要求 API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


