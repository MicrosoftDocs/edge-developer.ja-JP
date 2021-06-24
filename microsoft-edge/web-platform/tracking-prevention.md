---
description: このページでは、Microsoft Edge (Chromium) 追跡防止機能に関するドキュメントを提供します。
title: '[追跡防止] Microsoft Edge (Chromium)'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, compatibility, Web プラットフォーム, 追跡防止, トラッカー, Cookie, ストレージ, 広告ブロック, トラッカーブロック, 追跡保護
ms.openlocfilehash: 24c410beba34b992cf01b973e79c1247fdc26fee
ms.sourcegitcommit: b5acfd4dd7f57991d659715e4621edd786d44052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "11614636"
---
# <a name="tracking-prevention-in-microsoft-edge-chromium"></a>[追跡防止] Microsoft Edge (Chromium)  

Microsoft Edgeの追跡防止機能は、トラッカーがブラウザー ベースのストレージとネットワークにアクセスする機能を制限することで、オンライン追跡からユーザーを保護します。  これは、ブラウザーのプライバシー Microsoft Edge約束を守[][MicrosoftEdgeBrowserPrivacyPromise]り、Web サイトの互換性や Web の経済的な実行可能性に対する既定の影響を与えかねずに構築されています。  

Microsoft Edgeユーザーには、3 つのレベルの追跡防止が提供されています。これは、に移動して選択されます `edge://settings/privacy` 。  

![追跡防止の 3 つの設定][ImageThreeSettingsTrackingPrevention]  

1.  **Basic** - カスタマイズされた広告を楽しみ、Web 上で追跡されるのを気にしないユーザー向けに設計された、最も制限の少ない追跡防止レベル。  Basic は、フィンガープリントやクリプトミナーなどの悪意のあるトラッカーからユーザーを保護します。  
1.  **バランス (既定値)** - Web を参照する場合の互換性の問題のリスクを最小限に抑えながら、パーソナライズされた広告を表示するユーザー向けに設計された既定の追跡防止レベル。  バランスの取れた目的は、ユーザーが関与しないサイトからのトラッカーをブロックします。  
1.  **Strict** - プライバシーを最大限に高め、Web サイトの互換性を保つユーザー向けに設計された、追跡防止の最も制限的なレベルです。  

Microsoft Edge の追跡防止機能は、3 つの主要なコンポーネントで構成され、Web サイトの特定のリソースをトラッカーとして分類してブロックするかどうかを判断します。  コンポーネントは次のとおりです。  

1.  **分類**- URL がMicrosoft Edgeに属するかどうかを判断する方法。  
1.  **強制**- トラッカーとして分類された URL からMicrosoft Edgeユーザーを保護するために実行されるアクション。  
1.  **軽減策** - ユーザーが指定したお気に入りのサイトが引き続き機能し、強力な既定の保護を提供するために提供されるメカニズム。  

各コンポーネントについては、このページで詳しく説明します。  

## <a name="classification"></a>分類  

追跡防止機能の 1 つ目のコンポーネントはMicrosoft Edge分類です。  オンライン トラッカーを分類し、カテゴリにグループ化するには、Microsoft Edgeオープンソース追跡保護[][|::ref1::|Main]リストを[使用します][GitHubDisconnectMeTrackingProtection]。  リストは、"信頼保護リスト" コンポーネントを介して配信されます。これはで表示できます `edge://components` 。  ダウンロード後、リストはディスクに保存され、特定の URL が分類されるかどうかを判断するために使用できます。  

Microsoft Edge の分類システムによって URL がトラッカーと見なされるかどうかを判断するために、一連のホスト名がチェックされ、完全一致以降、トップ レベル ドメインを超える最大 4 つのラベルの部分一致を確認します。  

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

これらのホスト名が [切断] リストのホスト名[][|::ref2::|Main][][GitHubDisconnectMeTrackingProtection]と一致する場合は、Microsoft Edgeを評価して、ユーザーが追跡されるのを防ぐ必要があります。  

## <a name="enforcement"></a>使用停止措置  

Web 上のアクションの追跡から保護するために、Microsoft Edge追跡者に対して 2 つの強制アクションを実行します。

*   **記憶域へのアクセスを制限**する - 既知の追跡リソースが、ユーザーに関するデータを保持しようとする Web ストレージにアクセスしようとすると、そのアクセスMicrosoft Edgeブロックされます。  これには、そのトラッカーが Cookie を取得または設定する機能を制限したり、ストレージ API (など) にアクセスしたりする機能が含 `IndexedDB` まれます `localStorage` 。  
*   **リソース**の読み込みブロック - 既知の追跡リソースが Web サイトに読み込まれている場合、Microsoft Edge は、ユーザーが設定した負荷と追跡防止設定の互換性の影響に応じて、要求がネットワークに到達する前に、その読み込みをブロックする場合があります。  ブロックされた読み込みには、追跡スクリプト、ピクセル、iframe などがあります。  これにより、追跡ドメインに送信される可能性のあるデータが防止され、読み込み時間とページパフォーマンスが副作用として向上する可能性があります。  

ユーザーは、アドレス バーの左側にあるページ情報の飛び出しアイコンを選択して、特定のページでブロックされたトラッカーを確認できます。 

![ページ情報のフライアウトでブロックされたトラッカー][ImageBlockedTrackersPageInfoFlyout]  

適用方法は、ユーザーが選択した追跡防止のレベルと適用される可能性がある軽減策によって異なります。  

## <a name="mitigations"></a>対処方法  

Web の互換性を可能な限り維持するために、Microsoft Edge状況での強制のバランスを取るのに役立つ 3 つの軽減策があります。  これらは、[組織の関係の軽減、](#org-relationship-mitigation)[組織のエンゲージメント軽減、](#org-engagement-mitigation)[および CompatExceptions リストです](#the-compatexceptions-list)。  

軽減策に取り組む前に、"Organization" または "Org" の概念を定義する価値があります。  [Disconnect][|::ref3::|Main] は、同じ親組織 [ /][GitHubDisconnectMeTrackingProtectionEntitiesJson] 会社entities.jsURL のグループを定義するリストを管理します。  Microsoft Edge の追跡防止機能は、組織間の要求に影響を[](#org-relationship-mitigation)与える追跡防止によって[](#org-engagement-mitigation)引き起こされる互換性の問題の発生を最小限に抑えるために、組織関係の軽減と組織のエンゲージメント軽減の両方でこのリストを使用します。  

### <a name="org-relationship-mitigation"></a>組織の関係の軽減  

いくつかの一般的な Web サイトでは、静的なリソースとコンテンツをそれらのサイトに提供するために、Web サイトとコンテンツ配信ネットワーク \(CDN\) の両方を維持しています。  これらの種類のシナリオが追跡防止の影響を受けずに、Microsoft Edge は、サイトが同じ親組織が所有する他のサイトに対してサード パーティの要求を行っているときに、サイトを追跡防止から除外します (リスト \の切断[entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson]で定義されている)。  これは、例によって最も良く示されています。  

> **例:**
> 
> Org1 という名前の組織は、ドメインを所有し、リストの [切断] entities.js`org1.test` `org1-cdn.test` [で定義されています][GitHubDisconnectMeTrackingProtectionEntitiesJson]。  Imagineとして分類され、通常は追跡防止の適用が適用される `org1-cdn.test` 場合があります。  ユーザーがアクセスし、サイトがリソースを読み込もうとした場合、Microsoft Edge はファースト パーティの URL ではないにもかかわらず、要求に対して強制アクションを実行 `https://org1.test` `https://org1-cdn.test` `org1-cdn.test` しない。  ただし、Org1 組織の一部ではない別の URL が同じリソースを読み込もうとすると、要求は同じ組織の一部ではないので、強制の対象になります。  
> 
> これにより、同じ組織に属するサイトに対する追跡防止の実施が緩む一方で、アクセスしたサイトやリソースを特定したり、内部のバック エンド データを使用したりできる組織では、高いプライバシー リスクが発生する可能性は低いです。 `https://org1.test` `https://org1-cdn.test`  

### <a name="org-engagement-mitigation"></a>組織のエンゲージメントの軽減  

組織の関与の軽減策は、ユーザーが十分に関与している組織が所有するサイトが、Web 全体で期待通り動作し続け、追跡防止によって導入される互換性リスクを最小限に抑えるために作成されました。  サイトエンゲージメントを利用[][ChromiumDesignDocsSiteEngagement]して、ユーザーが特定のサイトとの継続的な関係 \(現在は 4.1 以上のサイトエンゲージメント スコアで定義されている)を確立するたびに、適用を緩める。  これは、次の例で示す最適な方法です。

> **例:**
> 
> Social Org という名前の組織がドメインを所有しています `social.example` `social-videos.example` 。
> 
> ソーシャル組織が所有するドメインの 1 つとサイト エンゲージメント スコアが 4.1 以上である場合、ユーザーはソーシャル組織との関係を持つとみなされます。
> 
> 別のサイトに、ソーシャル組織が所有するドメインからの埋め込みビデオ `https://content-embedder.example` \(\) が含まれている場合、通常は追跡防止の実施によって制限される可能性があります。ソーシャル組織が所有するドメインとのユーザーのサイトエンゲージメント スコアがしきい値を超える限り、サイトは追跡防止の実施から除外されます。 `social-videos.example`
> 
> サイトが組織に属していない場合、ユーザーは、追跡防止によって課されるストレージ アクセス/リソース負荷ブロックが緩和される前に、サイトエンゲージメント スコア 4.1 以上を直接確立する必要があります。

組織のエンゲージメント軽減は現在、バランス モードでのみ適用され、Microsoft Edgeが Strict にオプトインしたユーザーに対して可能な限り最高の保護を提供します。

### <a name="the-compatexceptions-list"></a>CompatExceptions リスト  

Microsoft が受け取った最近のユーザーフィードバックに基づいて、Microsoft Edge は、上記の 2 つの軽減策が実施されているにもかかわらず、追跡防止のために壊れたサイト \(そのほとんどは Disconnect Content category\) の小さなリストを保持します。 このリストのサイトは、追跡防止の実施から除外されます。  リストは、以下に示す場所にある [ディスク上に](#determining-whetherhow-a-particular-url-is-classified) 表示されます。  ユーザーは、 の [ブロック] オプションを使用して、その **エントリを** 上書きできます `edge://settings/content/cookies` 。

このリストを今後も維持しないように、Microsoft は現在、Storage[コード][GitHubMsExplainersStorageAccessApi]ベースの Chromiumしています。  [Storage Access API][GitHubMsExplainersStorageAccessApi]を使用すると、サイト開発者はユーザーから直接ストレージ アクセスを要求し、ユーザーのプライバシー設定が閲覧エクスペリエンスに与える影響の透明性を高め、サイト開発者が自分のブロックを迅速かつ直感的に解除するためのコントロールを提供します。

Storage [Access API][GitHubMsExplainersStorageAccessApi]が実装された後、Microsoft は CompatExceptions リストを廃止し、影響を受けるサイトに連絡して問題を認識し、Storage [Access API][GitHubMsExplainersStorageAccessApi]の使用を今後要求します。  

## <a name="current-tracking-prevention-behavior"></a>現在の追跡防止の動作  

次の表に、アプリ内の分類されたトラッカーの各カテゴリに適用される適用アクションと軽減策をMicrosoft Edge。  

*   上部には、切断追跡保護リスト カテゴリで定義されている [トラッカーのカテゴリがあります][GitHubDisconnectTrackingProtectionCategories]。  
*   左側には、\(Basic、Balanced、Strict\) の 3 つのMicrosoft Edge追跡防止があります。  
*   この文字 `S` は、ストレージ アクセスがブロックされた状態を示します。  
*   この文字 `B` は、記憶域アクセスとリソースの読み込み \(ネットワーク要求\など) の両方がブロックされた状態を示します。  
*   ハイフン \( \) は、ストレージ アクセスまたはリソース負荷にブロックが適用 `-` されません。  

| | 広告を表示する | 分析 | コンテンツ | Cryptomining | フィンガープリント | Social | Other | 同じ組織の軽減策 | 組織のエンゲージメントの軽減 |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **基本** | - | - | - | B | B | - | - | 有効 | 該当なし |  
| **バランス** | S | - | S | B | B | S | S | 有効 | 有効 |  
| **[高レベル]** | B | B | S | B | B | B | B | 有効 | 無効 |  

> [!NOTE]
> 組織のエンゲージメントの軽減策は、Cryptomining カテゴリまたはフィンガープリント カテゴリには適用されません。  

> [!TIP]
> Strict モードでは、Balanced よりも多くのリソース負荷がブロックされます。  リソース負荷が多くブロックされると、要求を行うトラッカーが読み込まれならず、Balanced よりも少ない追跡要求をブロックする厳密モードが表示される場合があります。  

> [!NOTE]
> [現在の追跡防止動作] [の [フィンガー](#current-tracking-prevention-behavior) プリント] 列は、別のリストに加えて、フィンガープリント リストにあるトラッカーを参照します。  フィンガープリント リストにのみ表示されるトラッカーは、悪意のあるフィンガープリントではないと見なされ、ブロックされません。

### <a name="inprivate-behavior"></a>InPrivate の動作  

79 Microsoft Edgeでは、InPrivate で Strict モード保護を適用する既定の動作でした。  80 Microsoft Edgeでは、この動作は、ユーザーが InPrivate の閲覧中に厳密なモード保護を適用するか、通常の設定を維持するかどうかを決定できるスイッチに置き換えされました。 `edge://settings/privacy`  

## <a name="determining-whetherhow-a-particular-url-is-classified"></a>特定の URL を分類するかどうかを決定する  

特定の URL が既知のトラッカーとして分類されているかどうかを判断する最も簡単な方法は、次の手順を実行します。  

1.  DevTools を開き、[コンソール] タブに移動します。  
1.  Web ページを更新します。  
    1.  サイトエンゲージメントスコアをリセットし、 **完全** にクリーンなスレートを確保するために、最初に Cookie や他のサイト データをクリアする必要があります。  
1.  読んだメッセージを探します `Tracking Prevention blocked access to storage for <URL>` 。  
    1.  メッセージを展開して、ブロックされた個々の URL を表示できます。  
1.  特定のブロックされたサイトが含まれるカテゴリを特定する必要がある場合、これを行う最も簡単な方法は、[切断] ボックスの一覧で検索services.js[です][GitHubDisconnectTrackingProtectionCategories]。  エントリはアルファベット順に表示され、サイト エントリのブロックの上部までスクロールすると、特定のサイトの特定のカテゴリを検索できます。  

> [!TIP]
> ディスクに保存されている追跡防止リストにアクセスする必要がある場合は、それぞれ 2 つの場所の 1 つで見つかる場合があります。  
>
> **コンポーネントベースの更新** - "信頼保護リスト" コンポーネントからダウンロードされるリスト  
>
> Windows: `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> macOS: `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> **インストール ディレクトリ**- インストーラーにバンドルされているMicrosoft Edgeします。  別のインストール ディレクトリを選択した場合、正確なパスが異なる場合があります。  
>
> Windows: `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> macOS: `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## <a name="frequently-asked-questions"></a>よく寄せられる質問  

次のセクションでは、追跡防止機能に関してよく寄せられる質問に対する回答について説明します。Microsoft Edge。  

**特定のトラッカーをデバッグ目的でブロックまたは許可する方法はありますか?**  

現在、Microsoft Edgeは、追跡防止の実施が指定されたサイトで実行されるのを無効にするオプションのみを公開しています。  このオプションには、ページ情報のフライアウトまたはページからアクセス `edge://settings/privacy/trackingPreventionExceptions` します。  

つまり、ページの **[ブロック** ] オプションと **[** 許可] オプションを使用して、Cookie などのストレージへの特定のドメイン アクセスを許可または拒否できます `edge://settings/content/cookies` 。  これは、特定のサイトのストレージへのアクセスをブロックする防止の強制を追跡することで発生するサイトの問題をデバッグする場合に役立ちます。  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ./media/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ./media/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "プライバシー - Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "Site Engagement - Chromium プロジェクト"  

[DisconnectMain]: https://disconnect.me "切断"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "services.js- disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "entities.js- disconnectme/disconnect-tracking-protection |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "StorageAccess API Explainer - MSEdgeExplainers/StorageAccessAPI |GitHub"
