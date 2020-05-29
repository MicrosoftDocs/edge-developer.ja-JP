---
description: このページでは、Microsoft Edge (Chromium) のトラッキング防止機能に関するドキュメントを提供します。
title: Microsoft Edge でのトラッキング防止 (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、トラッキング防止、トラッカー、cookie、ストレージ、広告ブロック、トラッカーブロック、追跡防止
ms.openlocfilehash: 2648f05c112a00e66eae85ed44adf22632a0524a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570803"
---
# Microsoft Edge でのトラッキング防止 (Chromium)  

Microsoft Edge の追跡防止機能を使用すると、ユーザーは、トラッカーがブラウザーベースのストレージとネットワークにアクセスする機能を制限することによって、オンライントラッキングを防ぐことができます。  この機能は、Microsoft Edge ブラウザーの[プライバシー保証][MicrosoftEdgeBrowserPrivacyPromise]を遵守することを目的としています。また、web サイトの互換性または web の経済の可能性によって既定で影響を受けることはありません。  

Microsoft Edge では、現在、に移動することによって選択されている3つのレベルの追跡防止が提供されてい `edge://settings/privacy` ます。  

![追跡防止の3つの設定][ImageThreeSettingsTrackingPrevention]  

1.  **基本**-カスタマイズされた広告を利用し、web 上での管理を考慮していないユーザー向けに設計された、最も制限の少ないレベルの追跡防止。  基本的には、fingerprinters や cryptominers などの悪質なトラッカーからユーザーを保護します。  
1.  [**均衡 (既定)** ]-web で参照しているときに、creepy の広告を表示したいユーザー向けに設計された、既定のトラッキング防止のレベルです。  バランスを考慮して、ユーザーが関与しないサイトからのトラッカーをブロックし、web 上の互換性の問題のリスクを最小限に抑えます。  
1.  **厳密**-最も制限の厳しい追跡防止レベルで、プライバシーを最大限に活用できるように、メンバーの web サイトに互換性を持たせることができます。  

Microsoft Edge の追跡防止機能は、web サイトの特定のリソースをトラッカーとして分類し、ブロックする必要があるかどうかを判断するために連携して動作する3つの主要なコンポーネントで構成されています。  構成要素は次のとおりです。  

1.  **分類**: Microsoft Edge が、URL がトラッカーに属しているかどうかを判別します。  
1.  **適用**-トラッカーとして分類された Url から Microsoft Edge ユーザーを保護するために実行されるアクション。  
1.  回避**策**: ユーザーが指定したお気に入りのサイトを維持するために提供されているメカニズムは、強力な既定の保護を提供します。  

各コンポーネントについては、このページで詳しく説明します。  

## 分類  

Microsoft Edge のトラッキング防止機能の最初のコンポーネントは、分類です。  Microsoft Edge では、オンラインのトラッカーを分類してカテゴリに分類するため[に、[オープンソース][|::ref1::|Main][トラッキング防止][GitHubDisconnectMeTrackingProtection]] の一覧が使用されます。  リストは、に表示される "信頼保護リスト" コンポーネントによって提供され `edge://components` ます。  ダウンロードが完了すると、リストはディスクに保存され、特定の URL が分類されているかどうかを判断するために使用することができます。  

URL が Microsoft Edge の分類システムによってトラッカーと見なされるかどうかを判断するには、完全に一致する一連のホスト名を確認してから、トップレベルドメイン以外の最大4つのラベルの部分一致を確認します。  

> **例**:  
> 
> URL `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> テストしたホスト名:  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

これらのホスト名が[切断][|::ref2::|Main][リスト][GitHubDisconnectMeTrackingProtection]のホスト名と一致する場合、Microsoft Edge は、ユーザーが追跡されないようにするための強制操作の評価に進みます。  

## 使用停止措置  

Web 上のアクションの追跡を保護するために、Microsoft Edge は分類されたトラッカーに対して2つの強制操作を行います。

*   **記憶域アクセスの制限**-既知の追跡リソースが、ユーザーに関するデータを保持しようとしている可能性がある web 記憶域にアクセスしようとした場合、Microsoft Edge はそのアクセスをブロックします。  これには、cookie を取得または設定する機能、およびなどのアクセス記憶域 Api の制限が含まれ `IndexedDB` `localStorage` ます。  
*   **リソースの読み込みをブロック**する-既知の追跡リソースが web サイトに読み込まれている場合、Microsoft Edge では、負荷の互換性への影響、およびユーザーが設定した追跡防止の設定によって、要求がネットワークに到達する前に、その読み込みがブロックされることがあります。  ブロックされた読み込みには、トラッキングスクリプト、ピクセル、iframe などが含まれる場合があります。  これにより、トラッキングドメインに送信される可能性があるデータが失われることがあります。また、読み込み時間とページのパフォーマンスを改善することもできます。  

ユーザーが、特定のページでブロックされたトラッカーを見つけるには、アドレスバーの左側にある [ページ情報] ポップアップアイコンをクリックします。 

![ページ情報ポップアップのブロックされたトラッカー][ImageBlockedTrackersPageInfoFlyout]  

Enforcements がどのように適用されるかは、ユーザーが選択したトラッキング防止のレベルと、適用される可能性がある回避策によって異なります。  

## 対処方法  

Web の互換性を最大限に維持するために、Microsoft Edge では、特定の状況での enforcements のバランスを考慮して、3つの緩和策を考慮してください。  これらは、[組織の関係の緩和](#org-relationship-mitigation)、[組織の取り組みの軽減](#org-engagement-mitigation)、および CompatExceptions の[一覧](#the-compatexceptions-list)です。  

軽減策を使用する前に、"組織" または "組織" の概念を簡潔に定義しておくことをお勧めします。  [切断][|::ref3::|Main]すると、同じ親組織/会社によって所有されている複数の url を定義する "[会計主体][GitHubDisconnectMeTrackingProtectionEntitiesJson]" と呼ばれるリストも維持されます。  Microsoft Edge の追跡防止機能は、組織の[関係の緩和](#org-relationship-mitigation)と組織の取り組みの[軽減](#org-engagement-mitigation)の両方でこのリストを使用して、組織間要求に対する防止の追跡によって発生した互換性の問題の発生を最小限に抑えます。  

### 組織の関係の緩和  

いくつかの一般的な web サイトは、web サイトとコンテンツ配信ネットワーク (Cdn) を保持し、それらのサイトに対して静的なリソースとコンテンツを提供します。  このような種類のシナリオが追跡防止の影響を受けないようにするために、Microsoft Edge では、サイト[が、同じ][GitHubDisconnectMeTrackingProtectionEntitiesJson]親組織によって所有されている他のサイトに対してサードパーティの要求を行っている場合に、exempts を追跡しないようにします。  これは例として最もよく示されています。  

> **例:**
> 
> Org1 という名前の組織は、ドメインを所有しており、[ `org1.test` `org1-cdn.test` エンティティの[切断] の一覧][GitHubDisconnectMeTrackingProtectionEntitiesJson]で定義されています。  トラッカーと `org1-cdn.test` して分類されていて、通常はトラッキング防止 enforcements が適用されているとします。  ユーザーがアクセス `https://org1.test` してリソースの読み込みを試みると `https://org1-cdn.test` 、Microsoft Edge は、 `org1-cdn.test` そのユーザーが初めてのパーティ URL でない場合でも、要求に対する強制操作を行いません。  ただし、Org1 組織に含まれていない別の URL が同じリソースを読み込む場合は、その要求は同じ組織の一部ではないため、enforcements の対象となります。  
> 
> この relaxes では、同じ組織に所属しているサイトの場合、予防 enforcements を追跡していますが、このような組織は、 `https://org1.test` `https://org1-cdn.test` 内部のバックエンドデータを使用すると同時にアクセスできるサイトとリソースを特定できます。  

### 組織のエンゲージメントの軽減  

組織のエンゲージメントの緩和によって、ユーザーが十分に協力している組織によって所有されているサイトが、引き続き web 上で期待どおりに動作することを確認して、予防措置によって発生した互換性のリスクを最小限に抑えます。  特定のサイトを使用して、ユーザーが継続的なリレーションシップ (4.1 以上のサイト契約によって定義されています) を確立しているときに、[サイト契約][ChromiumDesignDocsSiteEngagement]を使用して、enforcements を緩和します。  これについては、次に例を示します。

> **例:**
> 
> ソーシャル組織という名前の組織は、ドメインとを所有して `social.example` `social-videos.example` います。
> 
> ユーザーは、4.1 のサイト契約の得点、またはソーシャル組織が所有するいずれかのドメインを使用している場合は、ソーシャル組織との関係があると見なされます。
> 
> 別のサイトには、 `https://content-embedder.example` (\ の埋め込みビデオ) という、ソーシャル組織が所有するいずれかのドメインからのサードパーティのコンテンツが含まれています。これは、通常は、enforcements によって制限されますが、そのサイトは、 `social-videos.example` 社会組織が所有するドメインのサイト契約スコアがしきい値を超えて維持されている限り
> 
> サイトが組織に属していない場合は、トラッキング防止によって課されるストレージアクセスとリソース読み込みのブロックが緩和される前に、ユーザーが4.1 のサイト契約のスコアを直接設定する必要があります。

組織のエンゲージメントの軽減は、現時点ではバランスモードでのみ適用されます。これにより、Microsoft Edge では、厳格なユーザーに対して最大限の保護が提供されます。

### CompatExceptions リスト  

Microsoft Edge では、最近受け取ったユーザーのフィードバックに基づき、microsoft Edge では、上記の2つの回避策がある場合でも、変更履歴を追跡することによって中断されたサイトの小さなリストが管理されます。 このリストのサイトは、予防防止 enforcements から除外されます。  一覧は、次に説明する[場所](#determining-whetherhow-a-particular-url-is-classified)のディスクにあります。  の [**ブロック**] オプションを使用して、ユーザーがそのエントリを上書きする可能性があり `edge://settings/content/cookies` ます。

このリストの移動を回避するために、Microsoft は現在、Chromium codebase で[ストレージアクセス API][GitHubMsExplainersStorageAccessApi]を使用しています。  [ストレージアクセス API][GitHubMsExplainersStorageAccessApi]を使うと、サイトの開発者は、ユーザーが直接ユーザーから記憶域にアクセスできるようにする方法が提供されます。また、ユーザーはプライバシー設定が参照エクスペリエンスに影響を与えていることをユーザーに示すことができます。また、サイト開発者は、迅速かつ直感的なブロック解除を行うことができます。

[ストレージアクセス api][GitHubMsExplainersStorageAccessApi]が実装されると、Microsoft は CompatExceptions リストを廃止し、影響を受けるサイトに到達して、それらの問題を認識し、[ストレージアクセス api][GitHubMsExplainersStorageAccessApi]の使用を転送するように要求します。  

## 現在のトラッキング防止動作  

次の表は、Microsoft Edge で分類されたトラッカーの各カテゴリに適用される強制アクションと軽減策を示しています。  

*   上部には、[切断追跡防止リストのカテゴリ][GitHubDisconnectTrackingProtectionCategories]によって定義されたトラッカーのカテゴリがあります。  
*   左側には、Microsoft Edge \ (Basic、均衡、Strict) でのトラッキング防止の3つのレベルがあります。  
*   この文字は、 `S` ストレージアクセスがブロックされていることを示します。  
*   この文字は、 `B` ストレージアクセスとリソースのロード (ネットワーク要求など) の両方がブロックされていることを示します。  
*   ハイフン \ ( `-` \) は、ストレージアクセスまたはリソースの読み込みにはブロックが適用されないことを示します。  

| | 広告 | 分析 | コンテンツ | Cryptomining | フィンガー | Social | Other | 同じ組織のリスク軽減 | 組織のエンゲージメントの軽減 |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **基本** | - | - | - | B | B | - | - | 有効 | なし |  
| **カッコ** | S | - | S | B | B | S | S | 有効 | 有効 |  
| **[高レベル]** | B | B | S | B | B | B | B | 有効 | 無効 |  

> [!NOTE]
> 組織エンゲージメントの軽減は、Cryptomining またはフィンガープリンティングのカテゴリには適用されません。  

> [!TIP]
> Strict モードでは、均衡よりも多くのリソースの読み込みがブロックされます。  さらに多くのリソースの読み込みをブロックすると、要求を行っているトラッカーが読み込まれることがないため、制限付きのトラッキング要求をブロックするようになります。  

> [!NOTE]
> [現在のトラッキング防止動作](#current-tracking-prevention-behavior)のフィンガープリンティング列は、他のリストに加えて、フィンガープリンティングリスト上のトラッカーを指します。  フィンガープリンティングリストのみに表示されるトラッカーは、悪質な fingerprinters と見なされ、ブロックされません。

### InPrivate の動作  

Microsoft Edge 79 では、既定の動作として、InPrivate モードでの Strict モードの保護が適用されました。  Microsoft Edge 80 では、この動作が、のスイッチに置き換えられました。これに `edge://settings/privacy` より、ユーザーは、Strict モードの保護を適用するか、InPrivate ブラウズで通常の設定を維持するかを決定することができます。  

## 特定の URL が分類されているかどうかを判断する  

特定の URL が既知のトラッカーとして分類されているかどうかを判断する最も簡単な方法は、次の手順を実行することです。  

1.  DevTools を開き、[コンソール] タブに移動します。  
1.  ページを再読み込みします。  
    1.  サイト契約のスコアをリセットして完全に消去するには、最初に**cookie やその他のサイトデータ**をクリアする必要があります。  
1.  未読メッセージがあるかどうかを確認 `Tracking Prevention blocked access to storage for <URL>` します。  
    1.  メッセージを展開すると、ブロックされていた個々の Url が表示されることがあります。  
1.  ブロックされた特定のサイトのカテゴリを特定する必要がある場合、そのための最も簡単な方法は、[ [Disconnect services. json] リスト][GitHubDisconnectTrackingProtectionCategories]で検索することです。  エントリはアルファベット順であるため、サイトエントリのブロックの先頭にスクロールすると、特定のサイトの特定のカテゴリを見つけることができます。  

> [!TIP]
> ディスクに保存されている追跡防止リストにアクセスする必要がある場合は、それぞれが2つの場所のいずれかに存在する可能性があります。  
>
> **コンポーネントベースの更新プログラム**-"信頼保護リスト" コンポーネントからダウンロードされたリスト  
>
> 窓 `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> Os `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> **インストールディレクトリ**-Microsoft Edge インストーラーにバンドルされているリスト。  別のインストールディレクトリを選択した場合、正確なパスが異なる可能性があります。  
>
> 窓 `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> Os `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## よく寄せられる質問  

以下のセクションでは、Microsoft Edge の追跡防止機能についてよく寄せられる質問に対する回答を示します。  

**デバッグ目的で特定のトラッカーをブロックまたは許可する方法はありますか?**  

現時点では、Microsoft Edge では、指定されたサイトでのトラッキング防止 enforcements を無効にするオプションを公開しています。  このオプションにアクセスするには、[ページ情報] ポップアップまたはページを使用し `edge://settings/privacy/trackingPreventionExceptions` ます。  

このように、ページの**ブロック**と**許可**のオプションを使用して、 `edge://settings/content/cookies` cookie などのブラウザーストレージメカニズムなどの記憶域への特定のドメインへのアクセスを許可または拒否することができます。  これは、特定のサイトの記憶域へのアクセスをブロックすることによって発生するサイトの問題をデバッグするのに役立ちます enforcements。  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ../media/web-platform/tracking-prevention/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ../media/web-platform/tracking-prevention/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "プライバシー-Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "サイト契約-Chromium プロジェクト"  

[DisconnectMain]: https://disconnect.me "切っ"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "連絡/切断-管理-保護 |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "サービス. json-接続解除-管理-保護 |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "会計主体. json/切断-管理-保護 |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "Storage Access API Explainer-MSEdgeExplainers/StorageAccessAPI |GitHub"
