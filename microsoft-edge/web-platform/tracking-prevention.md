---
description: このページでは、Microsoft Edge (Chromium) 追跡防止機能に関するドキュメントを提供します。
title: Microsoft Edge の追跡防止 (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, 互換性, Web プラットフォーム, 追跡防止, トラッカー, Cookie, ストレージ, 広告のブロック, トラッカーのブロック, 追跡保護
ms.openlocfilehash: a767e55a44c4d416b6d40ca12eb49f2c3a722010
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231155"
---
# Microsoft Edge の追跡防止 (Chromium)  

Microsoft Edge の追跡防止機能は、ブラウザー ベースのストレージとネットワークにアクセスするトラッカーの機能を制限することで、ユーザーをオンライン追跡から保護します。  これは、Microsoft [Edge][MicrosoftEdgeBrowserPrivacyPromise] ブラウザーのプライバシーの約束を守る一方で、Web サイトの互換性や Web の経済的な可能性に対する既定の影響が生じずに残るという保証を行います。  

Microsoft Edge は現在、ユーザーに 3 つのレベルの追跡防止機能を提供しています。このレベルは、次に移動して選択されます `edge://settings/privacy` 。  

![追跡防止の 3 つの設定][ImageThreeSettingsTrackingPrevention]  

1.  **基本** : カスタマイズされた広告を楽しんだユーザーや、Web での追跡を気にしないユーザー向け、最も制限の厳しい追跡防止レベル。  Basic は、フィンガープリントやクリプトミニマーなどの悪意のあるトラッカーからユーザーを保護するのみです。  
1.  **バランス (既定値)** - 閲覧中に Web の周囲で表示される広告の数を減らしたいと考えるユーザー向け、追跡防止の既定のレベルです。  バランスの取れた目的は、ユーザーが関与しないサイトからのトラッカーをブロックし、Web 上の互換性の問題のリスクを最小限に抑えることです。  
1.  **厳密** : プライバシーを最大限に保つ Web サイトの互換性を保つユーザー向けに設計された、最も制限の厳しい追跡防止レベルです。  

Microsoft Edge の追跡防止機能は、3 つの主要なコンポーネントで構成され、Web サイトの特定のリソースをトラッカーとして分類してブロックするかどうかを判断します。  コンポーネントは次のとおりです。  

1.  **分類** - MICROSOFT Edge が URL がトラッカーに属するかどうかを判断する方法。  
1.  **実施** - トラッカーとして分類された URL から Microsoft Edge ユーザーを保護するために実行されるアクション。  
1.  **軽減策** : ユーザーが指定したお気に入りのサイトが引き続き機能し、強力な既定の保護を提供するために提供されるメカニズム。  

各コンポーネントについて説明し、このページで詳しく説明します。  

## 分類  

Microsoft Edge の追跡防止機能の最初のコンポーネントは分類です。  オンライン トラッカーを分類し、カテゴリにグループ化するために、Microsoft [][|::ref1::|Main] Edge ではオープン ソース追跡保護リストを切断[します][GitHubDisconnectMeTrackingProtection]。  リストは、"Trust Protection Lists" コンポーネントを介して配信されます。このコンポーネントは、以下で確認できます `edge://components` 。  ダウンロード後、リストはディスクに格納され、特定の URL の分類方法を判断するために使用できます。  

Microsoft Edge の分類システムによって URL がトラッカーと見なされるかどうかを判断するために、完全一致から始まる一連のホスト名がチェックされ、次に、トップ レベル ドメインを超える最大 4 つのラベルの部分的な一致のチェックに進みます。  

> **例**:  
> 
> URL: `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> テスト済みホスト名:  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

これらのホスト名の 1 つが切断リストの[][|::ref2::|Main][][GitHubDisconnectMeTrackingProtection]ホスト名と一致する場合、Microsoft Edge は実施アクションの評価に進み、ユーザーが追跡されるのを防ぐ。  

## 使用停止措置  

Microsoft Edge は、Web 上のアクションの追跡から保護するために、分類されたトラッカーに対して次の 2 つの実施アクションを実行します。

*   **ストレージ アクセスを** 制限する - 既知の追跡リソースが、ユーザーに関するデータを保持しようとする可能性がある任意の Web ストレージにアクセスしようとすると、Microsoft Edge はそのアクセスをブロックします。  これには、そのトラッカーが Cookie を取得または設定する機能や、次のようなストレージ API へのアクセスを制限する機能が `IndexedDB` 含まれます `localStorage` 。  
*   **リソース** の読み込みブロック - 既知の追跡リソースが Web サイトに読み込まれている場合、Microsoft Edge は、負荷の互換性への影響と、ユーザーが設定した追跡防止設定に応じて、要求がネットワークに到達する前に、その読み込みをブロックする可能性があります。  ブロックされた読み込みには、追跡スクリプト、ピクセル、iframe などがあります。  これにより、追跡ドメインに送信される可能性のあるデータを防ぎ、読み込み時間とページのパフォーマンスを副作用として向上させる可能性があります。  

ユーザーは、アドレス バーの左側にあるページ情報のフライアウト アイコンをクリックして、特定のページでブロックされたトラッカーを確認できます。 

![ページ情報のフライアウトでブロックされたトラッカー][ImageBlockedTrackersPageInfoFlyout]  

強制の適用方法は、ユーザーが選択した追跡防止のレベルと適用される可能性がある軽減策によって異なります。  

## 対処方法  

Web の互換性を可能な限り保持するために、Microsoft Edge には、特定の状況での適用のバランスを取る上で役立つ 3 つの軽減策があります。  これらは、 [組織の関係の軽減策](#org-relationship-mitigation)、 [組織の契約の軽減策](#org-engagement-mitigation)、 [および CompatExceptions リストです](#the-compatexceptions-list)。  

軽減策について説明する前に、"Organization" または "Org" の概念を簡単に定義する価値があります。  [また][|::ref3::|Main]、Disconnect は、同じ[][GitHubDisconnectMeTrackingProtectionEntitiesJson]親entities.js組織/会社が所有する URL のグループを定義するリストを保持します。  Microsoft Edge の追跡防止機能は、組織間の[](#org-relationship-mitigation)要求に影響を与える追跡防止によって発生する互換性の問題を最小限に抑えるために、組織の関係の軽減策と Org [Engagement](#org-engagement-mitigation)軽減策の両方でこのリストを使用します。  

### 組織の関係の軽減策  

いくつかの一般的な Web サイトは、静的なリソースとコンテンツをそれらのサイトに提供するために、Web サイトとコンテンツ配信ネットワーク \(CDNs\) の両方を維持しています。  このような種類のシナリオが追跡防止の影響を受けずに、Microsoft Edge は、サイトが同じ親組織が所有する他のサイト (リスト \の切断 [entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson]で定義されている) に対してサードパーティの要求を行っている場合に、サイトの追跡防止を除外します。  これは、例で示すのが最適です。  

> **例:**
> 
> Org1 という名前の組織はドメインを所有し、リストの [切断] entities.js`org1.test` `org1-cdn.test` [定義されています][GitHubDisconnectMeTrackingProtectionEntitiesJson]。  追跡ツールとして分類され、通常は追跡防止の実施が適用 `org1-cdn.test` されるとします。  ユーザーがアクセスし、サイトがリソースの読み込み先を試みる場合、Microsoft Edge は、ファースト パーティの URL ではないにもかかわらず、要求に対して強制アクションを実行 `https://org1.test` `https://org1-cdn.test` `org1-cdn.test` します。  ただし、Org1 組織の一部ではない別の URL が同じリソースを読み込もうとすると、要求は同じ組織の一部ではないので強制の対象になります。  
> 
> これにより、同じ組織に属するサイトに対する防止の実施の追跡が緩やかになりますが、そのような組織は内部のバック エンド データを使用してアクセスしたサイト/リソースを特定できるので、プライバシー リスクが高い可能性は低いと考えます。 `https://org1.test` `https://org1-cdn.test`  

### 組織のエンゲージメント軽減策  

組織エンゲージメント軽減策は、ユーザーが十分に連携している組織が所有するサイトが Web 全体で期待通り動作し続け、追跡防止によって導入された互換性リスクを最小限に抑えるために作成されました。  ユーザーが特定の[][ChromiumDesignDocsSiteEngagement]サイトとの継続的な関係 \(現在、サイトエンゲージメント スコア 4.1 以上で定義されています\) を確立するたびに強制を緩めるサイト エンゲージメントを利用します。  これは、次の例で示すのが最善です。

> **例:**
> 
> Social Org という名前の組織がドメインを所有 `social.example` し `social-videos.example` 、
> 
> Social Org が所有するドメインの 1 つを使用してサイトエンゲージメント スコア 4.1 以上を確立している場合、ユーザーは Social Org との関係を持っているとみなされます。
> 
> 別のサイトに、Social Org が所有するドメインからのサード パーティコンテンツ \(\からの埋め込みビデオなど) が含まれている場合、通常は防止の実施を追跡することで制限されます。Social Org が所有するドメインとのユーザーのサイトエンゲージメント スコアがしきい値を超える限り、サイトは追跡防止の実施から除外されます。 `https://content-embedder.example` `social-videos.example`
> 
> サイトが組織に属していない場合、ユーザーは、追跡防止によって課される記憶域アクセス/リソース負荷ブロックが緩和される前に、そのサイトエンゲージメント スコアを 4.1 以上に設定する必要があります。

組織のエンゲージメント軽減策は現在、バランス モードでのみ適用され、Microsoft Edge は Strict にオプトインしたユーザーに対して可能な限り高い保護を提供しています。

### CompatExceptions リスト  

Microsoft が最近受け取ったユーザーからのフィードバックに基づいて、Microsoft Edge は、上記の 2 つの軽減策が実施されているにもかかわらず、追跡防止のために壊れたサイトの小さなリスト (そのほとんどはコンテンツの切断カテゴリ\) を維持しています。 このリストのサイトは、追跡防止の実施から除外されます。  この一覧は、以下に示す場所 [のディスク上](#determining-whetherhow-a-particular-url-is-classified) に表示されます。  ユーザーは、ブロック オプションを使用して、そのエントリ **を** 上書きできます `edge://settings/content/cookies` 。

この一覧が今後も維持されるのを避けるため、現在、Microsoft は Chromium コードベースのストレージ アクセス [API][GitHubMsExplainersStorageAccessApi] に取り組み中です。  ストレージ アクセス [API][GitHubMsExplainersStorageAccessApi] を使用すると、サイト開発者は、ユーザーに直接ストレージ アクセスを要求し、プライバシー設定が閲覧エクスペリエンスに与える影響に対する透明性を高め、サイト開発者が自身のブロックをすばやく直感的に解除するためのコントロールを提供できます。

ストレージ アクセス [API][GitHubMsExplainersStorageAccessApi] が実装された後、Microsoft は CompatExceptions リストを廃止し、影響を受けるサイトに連絡して問題を認識し、ストレージ アクセス [API][GitHubMsExplainersStorageAccessApi] の使用を今後要求します。  

## 現在の追跡防止動作  

次の表に、Microsoft Edge の分類されたトラッカーの各カテゴリに適用される強制アクションと軽減策を示します。  

*   上部には、切断追跡保護リストのカテゴリで定義されている [トラッカーのカテゴリがあります][GitHubDisconnectTrackingProtectionCategories]。  
*   左側には、Microsoft Edge \(Basic、Balanced、Strict\ ) の 3 つのレベルの追跡防止があります。  
*   この文字 `S` は、記憶域へのアクセスがブロックされたかどうかを示します。  
*   この文字 `B` は、記憶域アクセスとリソースの読み込み \(ネットワーク要求\など) の両方がブロックされている状態を示します。  
*   ハイフン \( \) は、記憶域アクセスまたはリソースの読み込みにはブロック `-` が適用されません。  

| | タイジング | 分析 | コンテンツ | 暗号化 | 指紋認証 | Social | Other | 同じ組織の軽減策 | 組織のエンゲージメント軽減策 |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **基本** | - | - | - | B | B | - | - | 有効 | 該当せず |  
| **バランス** | S | - | S | B | B | S | S | 有効 | 有効 |  
| **[高レベル]** | B | B | S | B | B | B | B | 有効 | 無効 |  

> [!NOTE]
> 組織のエンゲージメント軽減策は、暗号化カテゴリまたは指紋カテゴリには適用されません。  

> [!TIP]
> 厳密モードでは、残高を超えるリソースの読み込みはブロックされます。  より多くのリソース負荷をブロックすると、要求を行うトラッカーは読み込まれならないので、Strict モードでは Balanced よりも少ない追跡要求をブロックする可能性があります。  

> [!NOTE]
> 現在の追跡防止動作の [[指紋](#current-tracking-prevention-behavior) ] 列は、別のリストに加えて、指紋リストにあるトラッカーを参照します。  指紋リストにのみ表示されるトラッカーは、悪意のある指紋ではないと見なされ、ブロックされません。

### InPrivate の動作  

Microsoft Edge 79 では、既定の動作では、InPrivate で Strict モード保護を適用します。  Microsoft Edge 80 では、この動作は、ユーザーが Strict モード保護を適用するか、InPrivate の閲覧中に通常の設定を保持するかどうかを決定できるスイッチに置き換えされました。 `edge://settings/privacy`  

## 特定の URL が分類されるかどうか/方法を判断する  

特定の URL が既知のトラッカーとして分類されているかどうかを判断する最も簡単な方法は、次の手順を実行する方法です。  

1.  DevTools を開き、[コンソール] タブに移動します。  
1.  ページを再読み込みします。  
    1.  最初に Cookie や他のサイト **データを** クリアして、サイトエンゲージメント スコアをリセットし、完全にクリーンなスレートを確保できます。  
1.  読み取ったメッセージを探します `Tracking Prevention blocked access to storage for <URL>` 。  
    1.  メッセージを展開して、ブロックされた個々の URL を表示できます。  
1.  特定のブロックされたサイトが含まれるカテゴリを特定する必要がある場合、これを行う最も簡単な方法は、リストの [切断] ページで検索 [services.js方法です][GitHubDisconnectTrackingProtectionCategories]。  エントリはアルファベット順に表示されます。したがって、サイト エントリのブロックの一番上にスクロールすると、特定のサイトの特定のカテゴリを検索できます。  

> [!TIP]
> ディスクに格納されている追跡防止リストにアクセスする必要がある場合は、それぞれが 2 つの場所の 1 つにある可能性があります。  
>
> **コンポーネントベースの更新** - "Trust Protection Lists" コンポーネントからダウンロードされるリスト  
>
> Windows: `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> macOS: `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> **インストール ディレクトリ** - Microsoft Edge インストーラーにバンドルされているリスト。  別のインストール ディレクトリを選択した場合、正確なパスが異なる可能性があります。  
>
> Windows: `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> macOS: `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## よく寄せられる質問  

次のセクションでは、Microsoft Edge の追跡防止機能についてよく寄せられる質問に対する回答を示します。  

**デバッグ目的で特定のトラッカーをブロックまたは許可する方法はありますか?**  

現在、Microsoft Edge では、追跡防止の実施が指定したサイトで実行されるのを無効にするオプションのみを公開しています。  このオプションには、ページ情報のフライアウトまたはページ経由でアクセス `edge://settings/privacy/trackingPreventionExceptions` します。  

とは言え、ページ**** 上の****[ブロック] および [許可] オプションを使用して、Cookie や他のブラウザーのストレージ メカニズムなどのストレージへの特定のドメイン アクセスを許可または `edge://settings/content/cookies` 拒否できます。  これは、特定のサイトの記憶域へのアクセスをブロックする防止の実施を追跡することで発生するサイトの問題をデバッグする場合に役立ちます。  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ./media/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ./media/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "プライバシー - Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "Site Engagement - Chromium プロジェクト"  

[DisconnectMain]: https://disconnect.me "Disconnect"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "services.jsオン - disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "entities.jsオン - disconnectme/disconnect-tracking-protection |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "Storage Access API Explainer - MSEdgeExplainers/StorageAccessAPI |GitHub"
