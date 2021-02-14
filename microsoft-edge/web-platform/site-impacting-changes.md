---
description: サイトの互換性に影響を与える可能性がある影響の大きな変更の概要を示します。
title: Microsoft Edge 向けのサイトの互換性に影響する変更点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, 互換性, Web プラットフォーム
ms.openlocfilehash: 64cdb417e6bd0aa648c7e1225bb6dc522f3873ce
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327506"
---
# Microsoft Edge 向けのサイトの互換性に影響する変更点  

Web は、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させ、常に進化しています。  場合によっては、変更が既存のページの機能に影響を与えるほど重要な場合があります。  次の表は、Microsoft Edge チームが現在追跡している特に影響の大きな変更をまとめたです。  この記事を頻繁に確認してください。Microsoft Edge チームは、考え方が進化し、タイムラインがしっかりと化し、新しい変更が発表されるにつれて、次のページを更新します。  

| 変更点 | Stable チャネル | Experimentation | 追加情報 |  
|:--- |:--- |:--- |:--- |
| Cookie の既定 `SameSite=Lax` の設定 `SameSite=None-requires-Secure` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v82、Dev v82 | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  この変更について Google が計画したタイムラインなど、詳細については [、「Chrome Platform Status」エントリに移動します][ChromePlatformStatus5088147346030592]。  |  
| 参照元ポリシー: 既定の設定 `strict-origin-when-cross-origin` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v79、Dev v79 | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  この変更について Google が計画したタイムラインなど、詳細については [、「Chrome Platform Status」エントリに移動します][ChromePlatformStatus6251880185331712]。  |  
| ページの閉じ `XmlHttpRequest` 込めで同期を禁止する | [Chrome+1](#release-comments) \(Edge v83\) |  | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  Chrome と一致する Microsoft Edge には、Edge v88 までこの変更をオフにするグループ ポリシーが用意されています。  この変更について Google が計画したタイムラインなど、詳細については [、「Chrome Platform Status」エントリに移動します][ChromePlatformStatus4664843055398912]。  |  
| 通知のアクセス許可要求に関する微妙なプロンプトを表示する | Edge v84 |  | Quiet notification requests display a subtle request icon in the address bar for site notification permissions requested using the `Notifications` or `Push` API, replacing the full or standard permission flyout prompt UI.  この機能は現在、すべてのユーザーに対して有効になっています。  Quiet 通知要求をオプトアウトするには、次の場所に移動します `edge://settings/content/notifications` 。  将来、Microsoft Edge チームは、一部のシナリオでフル フライアウト通知プロンプトの有効化を再び有効にするよう考える可能性があります。  |  
| 既定で TLS/1.0 および TLS/1.1 をオフにする | Edge v84 |  | [SSLMinVersion グループ][DeployedgeMicrosoftEdgePoliciesSslversionmin]ポリシーでは、TLS/1.0 および TLS/1.1 の再有効化が許可されます。ポリシーは Edge v90 まで使用可能なままです。  |  
| 混在コンテンツのダウンロードをブロックする | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  この変更について Google が計画したタイムラインを含む詳細については、Google セキュリティブログ [のエントリに移動します][GoogleBlogSecurity20200206]。  警告またはブロックするファイルの種類に関する Microsoft のロールアウト スケジュールは、Chrome の後の 1 つのリリースで計画されています。  |  
| AppCache の廃止 | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  詳細については [、WebDev ドキュメントに移動してください][WebDevAppCacheRemoval]。  Microsoft の非推奨のロールアウト スケジュールは、Chrome の後の 1 つのリリースで計画されています。  [AppCache OriginTrial トークン][ChromeDevelopersOrigintrialsAppCacheOriginTrial]を要求すると、サイトは Edge v90 まで非推奨の API を引き続き使用できます。  |  
| Adobe Flash の削除 | Edge v88  |  | この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  詳細については [、Adobe Flash Chromium ロードマップに移動してください][ChromiumFlashRoadmapSupportRemoved]。  | 
| FTP をオフにし、削除する | Edge v88  | Edge Beta v87 | Edge Beta v87 では、FTP サポートは既定で無効になっています。Edge Stable v87 では有効なままです。  Edge v88 では、FTP サポートは完全に削除されます。  この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。  詳しくは、Chrome プラットフォームの状態 [エントリに移動してください][ChromePlatformStatus6246151319715840]。  まだ FTP サポートが必要なサイトがある企業は、IE モードを使用するサイトを構成することで、FTP を引き続 [き使用できます][DeployedgeEdgeIeMode]。  | 
| 混在コンテンツ イメージの自動アップグレード | Edge v88  |  | 安全でない \(HTTP\) イメージへの参照は、HTTPS に自動的にアップグレードされます。HTTPS 経由で画像を利用できない場合、イメージのダウンロードは失敗します。 この [機能を制御][DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls] するには、グループ ポリシーを使用できます。 この変更は、Microsoft Edge が基づいている Chromium プロジェクトで発生します。 詳しくは、Chrome プラットフォームの状態 [のエントリに移動してください][ChromePlatformStatus4926989725073408]。  | 
| サード パーティの Cookie がブロックされている場合、HTTP 認証は許可されません  | Edge v87  |  | Edge v87 から [、BlockThirdPartyCookies][DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies] ポリシーまたは [エッジの設定] ページを使用してサード パーティの要求に対して Cookie がブロックされる場合、HTTP 認証も許可されません。 この変更は、リストをホスト [する][DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy] エンドポイントが HTTP 認証を使用する必要がある場合Internet Explorerモードのエンタープライズ モード サイト一覧のダウンロードに影響を与える可能性があります。  エンタープライズ モード サイト一覧のダウンロードで Cookie と HTTP 認証の両方を使用するには [、CookieAllowedForURLs][DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls] ポリシーに一致する URL パターンを追加します。  |   

##### コメントをリリースする  

:::row:::
   :::column span="1":::
      Chrome+1  
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、示されている機能または変更は Chrome の後にリリースされます。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome または Chrome+1  
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者のフィードバックに基づいて、示されている機能または変更は Chrome の後に同時に、または 1 つのリリースで出荷されます。  
   :::column-end:::
:::row-end:::

<!-- links -->  

[DeployedgeEdgeIeMode]: /deployedge/edge-ie-mode "IE モードの|Microsoft Docs"  
[DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]: /deployedge/edge-ie-mode-policies#configure-using-the-use-the-enterprise-mode-ie-website-list-policy "[エンタープライズ モードの IE Web サイト一覧を使う] ポリシーを使って構成する - IE モード ポリシーを構成|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]: /deployedge/microsoft-edge-policies#blockthirdpartycookies "BlockThirdPartyCookies - Microsoft Edge - ポリシー|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]: /deployedge/microsoft-edge-policies#cookiesallowedforurls "CookiesAllowedForUrls - Microsoft Edge - ポリシー|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls]:  /deployedge/microsoft-edge-policies#insecurecontentallowedforurls "InsecureContentAllowedForUrls - Microsoft Edge - ポリシー|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesSslversionmin]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin - Microsoft Edge - ポリシー|Microsoft Docs"  

[ChromePlatformStatus4664843055398912]: https://chromestatus.com/feature/4664843055398912 "ページを閉じるために JavaScript を使用して XHR を同期|Chrome プラットフォームの状態"  
[ChromePlatformStatus4926989725073408]: https://chromestatus.com/feature/4926989725073408 "イメージ混在コンテンツ の自動アップグレード|Chrome プラットフォームの状態"  
[ChromePlatformStatus5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookie の既定値は SameSite=Lax |Chrome プラットフォームの状態"  
[ChromePlatformStatus6246151319715840]: https://chromestatus.com/feature/6246151319715840 "FTP サポートの廃止|Chrome プラットフォームの状態"  
[ChromePlatformStatus6251880185331712]: https://chromestatus.com/feature/6251880185331712 "参照元ポリシー: 既定では strict-origin-when-cross-origin |Chrome プラットフォームの状態"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "Chromium からのフラッシュ サポートの削除 (ターゲット: Chrome 88+ - Jan 2021) - Flash ロードマップ |Chromium プロジェクト"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial トークン|Chrome 開発者"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "Google Chrome での安全でないダウンロードからユーザーを保護する - Google Online セキュリティ ブログ" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

<!--todo:  cleanup links  -->  
