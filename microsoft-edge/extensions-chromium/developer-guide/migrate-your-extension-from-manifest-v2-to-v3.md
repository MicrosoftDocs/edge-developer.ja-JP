---
description: マニフェスト V2 から V3 への拡張機能の更新の詳細
title: マニフェスト V2 から V3 への拡張機能の更新の準備
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, edge extensions, browser extensions, addons, developer, manifest v3, migrate to manifest v3
ms.openlocfilehash: 5aa1aa7446a312d581bacc4fa19ba7362c6c2a3e
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564617"
---
# <a name="prepare-to-update-your-extensions-from-manifest-v2-to-v3"></a>マニフェスト v2 から v3 に拡張機能を更新する準備をする  

このドキュメントでは、マニフェスト v3 の一部として実装されている重要な変更点を示します。これは、Chromium拡張機能プラットフォームの次のバージョンです。  拡張機能Microsoft Edge、実装の進行に合わせ、このドキュメントを更新します。  マニフェスト v3 への拡張機能の移行に関する詳細なガイダンスについては、「マニフェスト V3 への移行」 [に移動します][ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]。  

## <a name="remotely-hosted-code"></a>リモートでホストされるコード  

現在、拡張機能コードの一部はリモートでホストされ、検証プロセス中に拡張機能パッケージの一部として含めることはできません。  これにより、拡張機能をストアに再送信せずにコードを柔軟に変更することができますが、インストール後にコードが悪用される可能性があります。  アドオンが[Microsoft Edge検証][MicrosoftMicrosoftedgeAddons]済み拡張機能を一覧表示するために、Microsoft Edge 拡張機能チームは、リモートでホストされたコードを使用して拡張機能を禁止します。  この変更により、拡張機能のセキュリティが高くなっています。  開発者は、検証のために拡張機能で使用されるコードをパッケージ化して提出する必要があります。  または、サンドボックス環境で `eval()` 関数 [を使用できます][ChromeDeveloperDocsExtensionsMv2Sandboxingeval]。  

## <a name="run-time-host-permissions"></a>実行時ホストのアクセス許可  

インストール時に、拡張機能がすべてのサイトとコンテンツにアクセスするための一括アクセス許可を要求する場合があります。  これらのアクセス許可により、拡張機能は最小限の介入で動作し、ユーザーのプライバシーとセキュリティに対するリスクを生み出します。  透明性を向上させるために、Microsoft Edge拡張機能チームは、ユーザーが実行時に Web サイトへのアクセスを許可または制限するためのコントロールを提供します。  

## <a name="cross-origin-requests-in-content-scripts"></a>コンテンツ スクリプトでのクロスオリジン要求  

今日、コンテンツ スクリプトは、Web サイトで許可されていないオリジンを含む任意のオリジンへのアクセスを要求しています。  この動作は、クロスオリジンの原則を壊します。  今後、Microsoft Edge拡張機能チームは、コンテンツ スクリプトがスクリプトを挿入する Web ページと同じアクセス許可を持つ必要があります。セキュリティの抜け穴を閉じます。  クロスオリジン要求を実行するには、バックグラウンド スクリプトを使用して応答をコンテンツ スクリプトに中継する必要があります。  これらの変更は使用可能で、フラグの背後に表示されます。  詳細については、このドキュメントに移動 [します][ChromiumHomeChromiumSecurityExtensionContentScriptFetches]。  

## <a name="web-request-api"></a>Web 要求 API  

拡張機能Microsoft Edgeチームは[、Web 要求 API][ChromeDeveloperDocsExtensionsReferenceWebrequest]を[Declarative Net Request API][ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]に置き換えるが、Web 要求 API の観測機能を維持し続ける。  拡張機能で Web 要求 API の観測機能が必要な特定のシナリオを除き、Microsoft Edge 拡張機能チームは DNR API のみを使用するようにお勧めします。  拡張機能Microsoft Edgeチームは、この変更が機能豊富な宣言型機能を使用する拡張機能にプラスの影響を与える可能性を考えます。  より多くの拡張機能が DNR API に移行すると、この変更によりユーザーのプライバシーが向上し、拡張機能の使用に対する信頼が向上します。  
企業は、エンタープライズ ポリシーによって管理される拡張機能に対して Web 要求 API のブロック動作を引き続き使用する場合があります。  拡張機能ポリシーの詳細については、「Microsoft Edge –[ポリシー」 に移動します][DeployedgeMicrosoftEdgePoliciesExtensions]。  

## <a name="background-service-workers"></a>バックグラウンド サービスワーカー  
 
サービス ワーカーは、Canary でテストできます。  拡張機能をバックグラウンド ページからサービス ワーカーに移行するには、「バックグラウンド ページからサービス ワーカーへの移行 [」を参照してください][ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]。  拡張機能Microsoft Edgeチームは、この変更が開発者とユーザーの両方に与える影響を評価および調査しています。  拡張機能Microsoft Edgeチームは、このドキュメントの変更に関する詳細を今後追加します。  

## <a name="when-are-these-changes-available-in-microsoft-edge"></a>これらの変更が変更された場合は、Microsoft Edge  

現在の宣言型ネット要求 API の実装は、Stable チャネルと Beta チャネルで利用できます。  変更をテストし、フィードバックを提供します。  拡張機能Microsoft Edgeは、開発の取り組みとさらなる変更の調査に貢献します。  

| チャネル名 | 詳細 |  
|:--- |:--- |  
| Microsoft Edge 84 Stable | DNR API はテストに使用できます |  
| Microsoft Edge 85 Beta | ヘッダー変更のサポートが利用可能|  

Chromium に変更が加わると、Microsoft Edge 拡張機能チームはタイムラインを共有し、コードを更新してストアに拡張機能を再発行できます。  

拡張機能Microsoft Edgeチームは、ブログで更新プログラムの発行を続行します。  変更に関するフィードバックは、Tech Community を[通じて提供できます][MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]。

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesExtensions]: /deployedge/microsoft-edge-policies#extensions "拡張機能 - Microsoft Edge - ポリシー |Microsoft Docs"  

[MicrosoftMicrosoftedgeAddons]: https://microsoftedge.microsoft.com/addons "Microsoft Edge アドオン"  

[MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "マニフェスト V3 の変更は、次のMicrosoft Edge |Microsoft Tech Community"  

[ChromeDeveloperDocsExtensionsMv2Sandboxingeval]: https://developer.chrome.com/docs/extensions/mv2/sandboxingEval "Chrome 拡張機能で eval を使用|Chrome 開発者"  
[ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]:  https://developer.chrome.com/docs/extensions/mv3/migrating_to_service_workers "バックグラウンド ページからサービス ワーカーへの移行|Chrome 開発者"  
[ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]: https://developer.chrome.com/docs/extensions/mv3/mv3-migration-checklist "マニフェスト V3 移行チェックリスト |Chrome 開発者"    

[ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]: https://developer.chrome.com/docs/extensions/reference/declarativeNetRequest "chrome.declarativeNetRequest |Chrome 開発者"  
[ChromeDeveloperDocsExtensionsReferenceWebrequest]: https://developer.chrome.com/docs/extensions/reference/webRequest "chrome.webRequest |Chrome 開発者"  

[ChromiumHomeChromiumSecurityExtensionContentScriptFetches]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "Chrome 拡張機能コンテンツ スクリプトのクロスオリジン要求に対する変更点|The Chromium プロジェクト"  
