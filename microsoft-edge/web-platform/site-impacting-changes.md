---
description: このページでは、サイトの互換性に影響を与える可能性の高い変更の概要を示します。
title: Microsoft Edge 向けのサイトの互換性に影響する変更点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム
ms.openlocfilehash: 7a443b36c554439c70017aeee52c92f591c566b8
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866051"
---
# Microsoft Edge 向けのサイトの互換性に影響する変更点  

Web は、ユーザーエクスペリエンス、セキュリティ、プライバシーを向上させるために絶えず進化しています。  場合によっては、既存のページの機能に影響を与えるために変更が重要になることがあります。  次の表は、Microsoft Edge チームが現在追跡している、特に大きな影響を与える変更をまとめたものです。  定期的にご確認ください。Microsoft Edge チームでは、次のページが、考え方の変化、タイムラインの定着、および新しい変更が発表されたときに更新されます。  

| 変更点 | Stable チャネル | Experimentation | 追加情報 |  
|:--- |:--- |:--- |:--- |
| Cookie の既定値 `SameSite=Lax` | [Chrome または Chrome + 1](#release-comments)  | カナリア v82、Dev v82 | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome Platform Status エントリ][ChromePlatformStatus5088147346030592]を確認してください。  |  
| 参照元ポリシー: 既定値 `strict-origin-when-cross-origin` | [Chrome または Chrome + 1](#release-comments)  | カナリア v79、Dev v79 | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome Platform Status エントリ][ChromePlatformStatus6251880185331712]を確認してください。  |  
| ページを離れる際の同期 XmlHttpRequest の禁止 | [Chrome + 1](#release-comments) \ (Edge v83 \) |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  Chrome では、Microsoft Edge には、Edge 88 までこの変更を無効にするグループポリシーが用意されています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [Chrome Platform Status エントリ][ChromePlatformStatus4664843055398912]を確認してください。  |  
| 通知のアクセス許可要求に関する微妙なプロンプトを表示する |  | カナリア v83、Dev v83 | ユーザーは、の通知要求を Quiet 状態にすることができるようになりました `edge://settings/content/notifications` 。  この設定を有効にすると、Microsoft Edge に、または API を使って今後の通知をユーザーに送信するよう要求する、サイトのアドレスバーに微妙な要求アイコンが表示され `Notifications` `Push` ます。  この微妙なアイコンは、ポップアップアクセス許可のプロンプトに代わるものです。  この動作は、通知のアクセス許可を要求するすべてのサイトの一部のユーザーに対して、カナリアと Dev では既定でオンになっています。  ユーザーはを無効にすることがあり `edge://settings/content/notifications` ます。  今後、Microsoft edge チームは、ユーザーの動作やその他の入力に基づいて、特定の状況でポップアップのプロンプトを表示することができます。  |  
| TLS/1.0 と TLS/1.1 を既定で無効にする | Edge v84 |  | 影響を受けるサイトを見つけるために、フラグを設定することで、 `edge://flags/#display-legacy-tls-warnings` Microsoft Edge で従来の TLS プロトコルを必要とするページを読み込むときに、ブロックしない "セキュリティで保護されていない" という通知を表示することができます。  [Sslminversion][DeployedEdgePoliciesSSLMinVersion]グループポリシーでは、tls/1.0 および tls/1.1 の再有効化が許可されています。ポリシーは、Edge 88 まで利用できます。  |  
| 混在したコンテンツのダウンロードをブロックする | [Chrome + 1](#release-comments) \ (Edge v86 \)  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  この変更に関する Google の計画されたタイムラインを含む詳細については、 [google セキュリティのブログエントリ][GoogleBlogSecurity20200206]を確認してください。  注意またはブロックするファイルの種類に関する Microsoft ロールアウトのスケジュールは、Chrome 後の1回のリリースで計画されています。  |  
| AppCache の廃止 | [Chrome + 1](#release-comments) \ (Edge v86 \)  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  詳細については、 [Web dev のドキュメント][WebDevAppCacheRemoval]を参照してください。  廃止の Microsoft ロールアウトスケジュールは、Chrome 以降のリリース1回で計画されています。  [Appcache OriginTrial Token][AppCacheOriginTrial]を要求すると、サイトはエッジ v90 まで廃止された API を引き続き使うことができます。 |  
| Adobe Flash の削除 | Edge v88  |  | この変更は、Microsoft Edge が基づく Chromium プロジェクトで行われています。  詳細については、[アドビ Flash Chromium のロードマップ][ChromiumFlashRoadmapSupportRemoved]を確認してください。  | 
##### リリースコメント  

:::row:::
   :::column span="1":::
      Chrome + 1
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、指示された機能や変更が Chrome の後に1回リリースされます。
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome または Chrome + 1
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、指定された機能を同時に、または Chrome の後に1つずつ解放します。
   :::column-end:::
:::row-end:::


<!-- image links -->  

<!-- links -->  

[DeployedEdgePoliciesSSLMinVersion]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-ポリシー"  

[ChromePlatformStatus4664843055398912]: https://www.chromestatus.com/feature/4664843055398912 "ページ強制的での同期 XHR の許可を無効にする JavaScript-Chrome プラットフォームの状態"  
[ChromePlatformStatus5088147346030592]: https://www.chromestatus.com/feature/5088147346030592 "Cookie の既定値は SameSite = 甘い。 Chrome プラットフォームの状態"  
[ChromePlatformStatus6251880185331712]: https://www.chromestatus.com/feature/6251880185331712 "参照元ポリシー: 既定では、クロスオリジン-Chrome プラットフォームの状態"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "フラッシュのサポートが Chromium から削除されました (Target: Chrome 88 +-Jan 2021)-フラッシュロードマップ |Chromium プロジェクト"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "Google Chrome での安全でないダウンロードからのユーザーの保護-Google Online セキュリティブログ" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal/ "AppCache の削除"
[AppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial token"
