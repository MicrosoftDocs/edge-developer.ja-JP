---
description: サイトの互換性に影響を与える可能性がある影響の大きな変更の概要を示します。
title: Microsoft Edge 向けのサイトの互換性に影響する変更点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/27/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, 互換性, Web プラットフォーム
ms.openlocfilehash: 815a350dc82d02e77354f3079880df9ce81750b7
ms.sourcegitcommit: 412ec98cd9f57f74af69acad0a317d1dffa3b323
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "11640605"
---
# <a name="site-compatibility-impacting-changes-coming-to-microsoft-edge"></a>Microsoft Edge 向けのサイトの互換性に影響する変更点  

Web プラットフォームは、Web ページの構築に使用されるテクノロジのコレクションです。  このテクノロジには、HTML、CSS、JavaScript、その他多くのオープン標準が含まれます。  Web プラットフォームは、ユーザー エクスペリエンス、セキュリティ、プライバシーを向上させるために絶えず進化しています。  場合によっては、変更が既存の Web ページの機能に影響を与える場合があります。  今後のプロジェクト Web プラットフォームの変更Chromium詳細については、「Chrome プラットフォームの状態リリースのタイムライン[」に移動します][ChromestatusFeaturesSchedule]。  

Microsoft Edgeプロジェクトから Web プラットフォームに対するアップストリームの変更のほぼすべてChromiumします。  その理由には、機能と互換性の理由が含まれます。  Microsoft はブラウザーの完全な制御を維持Microsoft Edge変更を延期または拒否する場合があります。  変更がMicrosoft Edgeユーザーに利益をもたらすかは、ユーザーチームが判断します。  タイミングや動作Microsoft Edge変更をChromiumする機能領域を次の表に示します。  この表では、チームが追跡している影響の大Microsoft Edgeも示しています。  

この記事を頻繁に確認してください。  チームMicrosoft Edge、思考が進化し、タイムラインが固化し、新しい変更が発表されるにつれて、この記事を更新します。  

| 変更点 | Stable チャネル | Experimentation | 追加情報 |  
|:--- |:--- |:--- |:--- |
| WebRTC のプラン B SDP セマンティクスの廃止 | [Chrome+1](#release-comments) \(Edge v94\)  |  | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。 この変更は、プラン B と呼ばれる従来のセッション記述プロトコル (SDP) の方言を廃止します。仕様に準拠したブラウザー間互換性のある SDP 形式の統合プランに置き換えられる予定です。 詳細については [、「Chrome Platform Status entry][ChromestatusFeature5823036655665152] and [PSA: Timeline for Plan B SDP Deprecation][PSADeprecateWebRTCPlanB]and Removal - Please Migrate to Unified Plan 」に移動してください。 廃止の Microsoft ロールアウト スケジュールは、Chrome の後の 1 つのリリースで計画されています。 [WebRTC プラン B リバース オ][ChromeDevelopersOrigintrialsWebRTCPlanBOriginTrial]リジン試用版トークンを要求すると、サイトは Edge v96 まで廃止された API を引き続き使用できます。 |
| Cookie の既定 `SameSite=Lax` の設定および設定 `SameSite=None-requires-Secure` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v82, Dev v82 | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromestatusFeature5088147346030592]。  |  
| 参照元ポリシー: 既定値から `strict-origin-when-cross-origin` | [Chrome+1](#release-comments) \(Edge v86\)  | Canary v79, Dev v79 | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromestatusFeature6251880185331712]。  |  
| ページの閉じ込 `XmlHttpRequest` めで同期を禁止する | [Chrome+1](#release-comments) \(Edge v83\) |  | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  Chrome に一致Microsoft Edge、Edge v88 までこの変更をオフにするグループ ポリシーが提供されます。  この変更の予定タイムラインを含む詳細については、[Chrome プラットフォームの状態] エントリ [に移動します][ChromestatusFeature4664843055398912]。  |  
| 通知のアクセス許可要求の微妙なプロンプトを表示する | エッジ v84 |  | 通知要求を静かにすると、アドレス バーに、または API を使用して要求されたサイト通知のアクセス許可の微妙な要求アイコンが表示されます。完全または標準のアクセス許可のフライアウト プロンプト UI が `Notifications` `Push` 置き換わります。  この機能は現在、すべてのユーザーに対して有効になっています。  通知の静かな要求をオプトアウトするには、に移動します `edge://settings/content/notifications` 。  今後、一部のシナリオMicrosoft Edge、完全なフライアウト通知プロンプトの再有効化についてチームが確認する場合があります。  |  
| TLS/1.0 と TLS/1.1 をオフにする | エッジ v84 |  |  |  
| 混在コンテンツのダウンロードをブロックする | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  この変更の予定タイムラインを含む詳細については、Google のセキュリティ ブログ エントリ [に移動します][GoogleBlogSecurity20200206]。  警告またはブロックするファイルの種類に関する Microsoft ロールアウトスケジュールは、Chrome の後の 1 つのリリースで計画されています。  |  
| AppCache の非推奨 | [Chrome+1](#release-comments) \(Edge v86\)  |  | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  詳細については [、WebDev のドキュメントに移動します][WebDevAppCacheRemoval]。  廃止の Microsoft ロールアウト スケジュールは、Chrome の後の 1 つのリリースで計画されています。  [AppCache OriginTrial トークンを要求][ChromeDevelopersOrigintrialsAppCacheOriginTrial]すると、サイトは Edge v90 まで廃止された API を引き続き使用できます。  |  
| Adobe Flash の削除 | エッジ v88  |  | この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  詳細については[、「Adobe Flash Chromiumロードマップ」に移動します][ChromiumFlashRoadmapSupportRemoved]。  | 
| FTP サポートの削除 | エッジ v88  | Edge Beta v87 | Edge v88 では、FTP サポートは完全に削除されます。  この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。  詳細については、「Chrome プラットフォームの状態エントリ [」に移動します][ChromestatusFeature6246151319715840]。  FTP サポートが必要なサイトがある企業は、IE モードを使用するサイトを構成することで、FTP を引き続 [き使用できます][DeployedgeEdgeIeMode]。  | 
| 混在コンテンツ イメージの自動アップグレード | エッジ v88  |  | イメージへのセキュリティ保護されていない \(HTTP\) 参照は、HTTPS に自動的にアップグレードされます。イメージが HTTPS 経由で使用できない場合、イメージのダウンロードは失敗します。 この [機能を制御][DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls] するには、グループ ポリシーを使用できます。 この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。 詳細については、「Chrome プラットフォームの状態」 [エントリに移動します][ChromestatusFeature4926989725073408]。  | 
| サードパーティの Cookie がブロックされている場合、HTTP 認証は許可されません  | Edge v87  |  | Edge v87 から、サードパーティの要求に対して Cookie がブロックされている場合[、BlockThirdPartyCookies][DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]ポリシーまたはトグルインを使用すると、HTTP 認証も許可されません。 `edge://settings` この変更は、Enterpriseをホストするエンドポイント[][DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]が HTTP 認証を使用する必要がある場合Internet Explorerモードのサイト 一覧のダウンロードに影響を与える可能性があります。  Cookie と HTTP 認証の両方を Enterpriseモード サイト 一覧のダウンロードに使用するには[、CookieAllowedForURLs][DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]ポリシーに一致する URL パターンを追加します。  |
| TLS での 3DES の削除  | Edge v93  |  | Edge v93 から、暗号化スイートTLS_RSA_WITH_3DES_EDE_CBC_SHAサポートが削除されます。 この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。 詳細については、「Chrome プラットフォームの状態」 [エントリに移動します][ChromestatusFeature6678134168485888]。 さらに、Edge v93 では、古いサーバーとの互換性を維持する必要があるシナリオをサポートするために互換性ポリシーを使用できます。 この互換性ポリシーは廃止され、Edge v95 での動作が停止します。 その前に、影響を受け取ったサーバーを更新してください。 |
| プライベート ネットワーク要求をセキュリティで保護されたコンテキストに制限する  | Edge v93  |  | エッジ v93 から、インターネット上のページからローカル (イントラネット) ネットワーク上のリソースにアクセスするには、それらのページを HTTPS 経由で配信する必要があります。 この変更は、プロジェクトのChromiumプロジェクトでMicrosoft Edge発生します。 詳細については、「Chrome プラットフォームの状態」 [エントリに移動します][ChromestatusFeature5436853517811712]。 セキュリティ保護されていないページとの互換性を維持する必要があるシナリオをサポートするには [、InsecurePrivateNetworkRequestAllowed][DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowed] と [InsecurePrivateNetworkRequestAllowedForUrls][DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowedForUrls]の 2 つの互換性ポリシーを使用できます。 |

##### <a name="release-comments"></a>コメントのリリース  

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
[DeployedgeEdgeIeModePoliciesConfigureUsingUseEnterpriseModeIeWebsiteListPolicy]: /deployedge/edge-ie-mode-policies#configure-using-the-use-the-enterprise-mode-ie-website-list-policy "[ネットワーク モード IE web サイトのEnterpriseポリシーを使用して構成する - IE モード ポリシーを構成|Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesBlockthirdpartycookies]: /deployedge/microsoft-edge-policies#blockthirdpartycookies "BlockThirdPartyCookies - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesCookiesallowedforurls]: /deployedge/microsoft-edge-policies#cookiesallowedforurls "CookieAllowedForUrls - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesInsecurecontentallowedforurls]:  /deployedge/microsoft-edge-policies#insecurecontentallowedforurls "InsecureContentAllowedForUrls - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgePoliciesSslversionmin]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowed]: /deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed "InsecurePrivateNetworkRequestsAllowed - Microsoft Edge - ポリシー |Microsoft Docs"
[DeployEdgeMicrosoftEdgePoliciesInsecurePrivateNetworkRequestAllowedForUrls]: /deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls "InsecurePrivateNetworkRequestsAllowedForUrls - Microsoft Edge - ポリシー |Microsoft Docs"

[ChromestatusFeaturesSchedule]: https://www.chromestatus.com/features/schedule "タイムライン のリリース|Chrome プラットフォームの状態"  
[ChromestatusFeature4664843055398912]: https://chromestatus.com/feature/4664843055398912 "ページの却下 JavaScript サーバーで同期 XHR を許可|Chrome プラットフォームの状態"  
[ChromestatusFeature4926989725073408]: https://chromestatus.com/feature/4926989725073408 "Autoupgrade Image Mixed Content |Chrome プラットフォームの状態"  
[ChromestatusFeature5088147346030592]: https://chromestatus.com/feature/5088147346030592 "Cookie の既定値は SameSite=Lax |Chrome プラットフォームの状態"  
[ChromestatusFeature6246151319715840]: https://chromestatus.com/feature/6246151319715840 "FTP サポートの廃止|Chrome プラットフォームの状態"  
[ChromestatusFeature6251880185331712]: https://chromestatus.com/feature/6251880185331712 "参照元ポリシー: 既定で strict-origin-when-cross-origin |Chrome プラットフォームの状態"  
[ChromestatusFeature6678134168485888]: https://chromestatus.com/feature/6678134168485888 "TLS サーバーで 3DES を削除|Chrome プラットフォームの状態"
[ChromestatusFeature5436853517811712]: https://chromestatus.com/feature/5436853517811712 "サブリソースのプライベート ネットワーク要求を制限して、コンテキストをセキュリティで保護|Chrome プラットフォームの状態"
[ChromestatusFeature5823036655665152]: https://www.chromestatus.com/feature/5823036655665152 "[WebRTC]プラン B の非推奨と削除 (非推奨) |Chrome プラットフォームの状態"
[ChromiumFlashRoadmapSupportRemoved]: https://www.chromium.org/flash-roadmap#TOC-Flash-Support-Removed-from-Chromium-Target:-Chrome-88---Jan-2021- "Flash のサポート Chromium (ターゲット: Chrome 88+ - 2021 年 1 月) - Flash ロードマップ |Chromiumプロジェクト"  

[ChromeDevelopersOrigintrialsAppCacheOriginTrial]: https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673 "AppCache OriginTrial トークン |Chrome 開発者"  
[ChromeDevelopersOrigintrialsWebRTCPlanBOriginTrial]: https://developer.chrome.com/origintrials/#/view_trial/3892235977954951169 "WebRTC プラン B リバース オリジン試用版トークン |Chrome 開発者"

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "Google Chrome の安全でないダウンロードからユーザーを保護する - Google Online セキュリティ ブログ" 

[WebDevAppCacheRemoval]: https://web.dev/appcache-removal "AppCache の削除の準備|web.dev"  

[PSADeprecateWebRTCPlanB]: https://groups.google.com/g/discuss-webrtc/c/UBtZfawdIAA/m/-UVQQcubBQAJ "PSA: 計画 B SDP 非推奨と削除のタイムライン - 統合プランに移行してください"

<!--todo:  cleanup links  -->  
