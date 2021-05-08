---
description: サイトの互換性に影響を与える可能性がある影響の大きな変更の概要を示します。
title: Microsoft Edge 向けのサイトの互換性に影響する変更点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 互換性, Web プラットフォーム
ms.openlocfilehash: 64cdb417e6bd0aa648c7e1225bb6dc522f3873ce
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327506"
---
# Microsoft Edge 向けのサイトの互換性に影響する変更点  

Web は、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させ、常に進化しています。  場合によっては、変更が既存のページの機能に影響を与えるほど重要な場合があります。  次の表に、Microsoft Edge チームが現在追跡している特に影響の大きな変更点を示します。  この記事を頻繁に確認します。Microsoft Edge チームは、思考が進化し、タイムラインが固化し、新しい変更が発表されるにつれて、次のページを更新します。  

| 変更点 | Stable チャネル | Experimentation | 追加情報 |  
|:--- |:--- |:--- |:--- |
| Cookie の既定 `SameSite=Lax` の設定および設定 `SameSite=None-requires-Secure` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v82, Dev v82 | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromePlatformStatus5088147346030592]。  |  
| 参照元ポリシー: 既定値から `strict-origin-when-cross-origin` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v79, Dev v79 | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromePlatformStatus6251880185331712]。  |  
| ページの閉じ込 `XmlHttpRequest` めで同期を禁止する | [Chrome+1](#release-comments) \(Edge v83\) |  | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  Chrome に一致する Microsoft Edge では、Edge v88 までこの変更をオフにするグループ ポリシーが提供されています。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromePlatformStatus4664843055398912]。  |  
| 通知のアクセス許可要求の微妙なプロンプトを表示する | エッジ v84 |  | 通知要求を静かにすると、アドレス バーに、または API を使用して要求されたサイト通知のアクセス許可の微妙な要求アイコンが表示されます。完全または標準のアクセス許可のフライアウト プロンプト UI が `Notifications` `Push` 置き換わります。  この機能は現在、すべてのユーザーに対して有効になっています。  通知の静かな要求をオプトアウトするには、に移動します `edge://settings/content/notifications` 。  将来、Microsoft Edge チームは、一部のシナリオでフル フライアウト通知プロンプトの再有効化について説明する場合があります。  |  
| 既定で TLS/1.0 と TLS/1.1 をオフにする | エッジ v84 |  | [SSLMinVersion グループ][DeployedgeMicrosoftEdgePoliciesSslversionmin]ポリシーでは、TLS/1.0 および TLS/1.1 の再有効化が許可されます。ポリシーは Edge v90 まで使用可能なままです。  |  
| 混在コンテンツのダウンロードをブロックする | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  この変更の予定タイムラインを含む詳細については、Google のセキュリティ ブログ エントリ [に移動します][GoogleBlogSecurity20200206]。  警告またはブロックするファイルの種類に関する Microsoft ロールアウトスケジュールは、Chrome の後の 1 つのリリースで計画されています。  |  
| AppCache の非推奨 | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  詳細については [、WebDev のドキュメントに移動します][WebDevAppCacheRemoval]。  廃止の Microsoft ロールアウト スケジュールは、Chrome の後の 1 つのリリースで計画されています。  [AppCache OriginTrial トークンを要求][ChromeDevelopersOrigintrialsAppCacheOriginTrial]すると、サイトは Edge v90 まで廃止された API を引き続き使用できます。  |  
| Adobe Flash の削除 | エッジ v88  |  | この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  詳細については [、「Adobe Flash Chromium ロードマップ」に移動します][ChromiumFlashRoadmapSupportRemoved]。  | 
| FTP をオフにし、削除する | エッジ v88  | Edge Beta v87 | Edge Beta v87 では、FTP サポートは既定でオフになっています。In Edge Stable v87 それは有効なままです。  Edge v88 では、FTP サポートは完全に削除されます。  この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。  詳細については、「Chrome プラットフォームの状態エントリ [」に移動します][ChromePlatformStatus6246151319715840]。  FTP サポートが必要なサイトがある企業は、IE モードを使用するサイトを構成することで、FTP を引き続 [き使用できます][DeployedgeEdgeIeMode]。  | 
| 混在コンテンツ イメージの自動アップグレード | エッジ v88  |  | イメージへのセキュリティ保護されていない \(HTTP\) 参照は、HTTPS に自動的にアップグレードされます。イメージが HTTPS 経由で使用できない場合、イメージのダウンロードは失敗します。 この [機能を制御][DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls] するには、グループ ポリシーを使用できます。 この変更は、Microsoft Edge が基づいているクロム プロジェクトで発生しています。 詳細については、「Chrome プラットフォームの状態」 [エントリに移動します][ChromePlatformStatus4926989725073408]。  | 
| サードパーティの Cookie がブロックされている場合、HTTP 認証は許可されません  | Edge v87  |  | Edge v87 から [、BlockThirdPartyCookies][DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies] ポリシーを使用するか、[エッジ設定] ページを使用してサードパーティの要求に対して Cookie がブロックされている場合、HTTP 認証も許可されません。 この変更は、リストをホスト [するエンドポイント][DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy] で HTTP 認証を使用する必要がある場合Internet Explorerモードのエンタープライズ モード サイト一覧のダウンロードに影響を与える可能性があります。  エンタープライズ モード サイト 一覧のダウンロードに Cookie と HTTP 認証の両方を使用するには [、CookieAllowedForURLs][DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls] ポリシーに一致する URL パターンを追加します。  |   

##### コメントのリリース  

:::row:::
   :::column span="1":::
      Chrome+1  
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者からのフィードバックに基づいて、示された機能または変更は Chrome の後にリリースされます。  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      Chrome または Chrome+1  
   :::column-end:::
   :::column span="2":::
      ユーザーと開発者からのフィードバックに基づいて、示された機能または変更が Chrome の後に同時または 1 つのリリースで出荷されます。  
   :::column-end:::
:::row-end:::

<!-- links -->  

[DeployedgeEdgeIeMode]: /deployedge/edge-ie-mode "IE モードの|Microsoft Docs"  
[DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]: /deployedge/edge-ie-mode-policies#configure-using-the-use-the-enterprise-mode-ie-website-list-policy "[エンタープライズ モード IE Web サイトの使用] リスト ポリシーを使用して構成する - [IE モード ポリシーの構成] |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]: /deployedge/microsoft-edge-policies#blockthirdpartycookies "BlockThirdPartyCookies - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]: /deployedge/microsoft-edge-policies#cookiesallowedforurls "CookieAllowedForUrls - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls]:  /deployedge/microsoft-edge-policies#insecurecontentallowedforurls "InsecureContentAllowedForUrls - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesSslversionmin]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin - Microsoft Edge - ポリシー |Microsoft Docs"  

[ChromePlatformStatus4664843055398912]: https://chromestatus.com/feature/4664843055398912 "ページの却下 JavaScript サーバーで同期 XHR を許可|Chrome プラットフォームの状態"  
[ChromePlatformStatus4926989725073408]: https://chromestatus.com/feature/4926989725073408 "Autoupgrade Image Mixed Content |Chrome プラットフォームの状態"  
[ChromePlatformStatus5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookie の既定値は SameSite=Lax |Chrome プラットフォームの状態"  
[ChromePlatformStatus6246151319715840]: https://chromestatus.com/feature/6246151319715840 "FTP サポートの廃止|Chrome プラットフォームの状態"  
[ChromePlatformStatus6251880185331712]: https://chromestatus.com/feature/6251880185331712 "参照元ポリシー: 既定で strict-origin-when-cross-origin |Chrome プラットフォームの状態"  

[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "Flash サポートがクロムから削除されました (ターゲット: Chrome 88+ - 2021 年 1 月) - Flash ロードマップ |クロム プロジェクト"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial トークン |Chrome 開発者"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "Google Chrome の安全でないダウンロードからユーザーを保護する - Google Online セキュリティ ブログ" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

<!--todo:  cleanup links  -->  
