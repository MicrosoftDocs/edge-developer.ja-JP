---
description: Microsoft Store にエッジ (Chromium) の拡張機能を公開する手順を説明します。
title: 内線番号を発行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/21/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 7b5be511af1e81efd5da4fc4bc0691f317437f94
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607379"
---
# 内線番号を発行する  

Microsoft Edge のアドオンカタログ (Microsoft Edge アドオン \) に拡張機能を公開します。  まず、[パートナーセンター][MicrosoftPartnerCenter]で申請を作成して送信する必要があります。  このドキュメントでは、拡張機能の申請を作成するために提供する必要があるすべての詳細を示します。  

## 始める前に  

*   Microsoft Edge のアドオンで拡張機能を送信するには、[パートナーセンター][MicrosoftPartnerCenter]でアクティブな開発者アカウントが必要です。  まだインストールしていない場合は、[新しい開発者アカウントを作成][MicrosoftPartnerCenter]します。  
*   拡張パッケージの zip ファイルを作成して、次のファイルが含まれていることを確認します。  
    *   マニフェストファイルと、拡張機能の名前とバージョンを定義する必要があります。  
    *   拡張機能に必要な画像やその他のファイル。  


拡張機能の構築を開始していない場合は、「Microsoft Edge Chromium 拡張機能を構築するための[はじめ][ExtensionsGettingStarted]に」チュートリアルを参照してください。  

[パートナーセンター][MicrosoftPartnerCenter]で拡張機能の申請を作成するには、次の手順を実行します。  

## 手順 1: 新しい申請を開始する  

[開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。  [概要] ページで、[**新しい拡張機能の作成**] をクリックします。  

## 手順 2: 拡張機能 Zip ファイルをアップロードする  

[**パッケージ**] ページでは、拡張機能の申請用に zip ファイルをアップロードします。  パッケージは一度に1つしかアップロードできないため、拡張機能が完了していない場合は、進行中のパッケージをアップロードしてから公開するまでの間に更新することができます。  パッケージにファイルが含まれて `manifest.json` おり、アップロードする前に Microsoft Edge で正常に動作していることを確認してください。  
[アップロード] フィールドにパッケージをドラッグするか、[**ファイルの参照**] を選択して、パッケージをアップロードします。  [パッケージ] ページでは、Extensions zip ファイルが検証され、**アップロードの成功または失敗の状態**が表示されます。  パッケージが検証に合格した場合正常にアップロードされ、成功メッセージが表示されます。  パッケージの検証に失敗した場合パッケージは受け入れられず、エラーメッセージが表示されます。  パッケージにエラーがある場合は、問題を解決して、もう一度アップロードしてみてください。  

アップロードが正常に完了したら、拡張機能の詳細を確認し、[**次へ**] をクリックして続行します。  

## 手順 3: 空き時間情報を入力する  

### 表示の定義  

**表示**オプションを選んで、内線番号を検出して入手できる参加者を定義します。  これにより、ユーザーが Microsoft Edge のアドオンで拡張機能を検索するかどうかを指定したり、一覧を見ることができます。  現在、[表示] には2つのオプションがあります。  

*   `Public`  
    これは既定のオプションです。  
    を選択する `Public` と、拡張機能が使用可能になり、Microsoft Edge のアドオンのすべてのユーザーが検出できるようになります。  ユーザーが検索、参照、内線番号の直接リンクを使用して検索できるようにする場合は、このオプションを選択したままにしておきます。  

*   `Hidden`  
    を選択した場合 `Hidden` 、拡張機能は、ユーザーが検索または参照したときの Microsoft Edge アドオンでは表示されません。拡張機能を配布するには、リストの URL を共有する必要があります。  このリストへの直接リンクを持っているユーザーは、Microsoft Edge にダウンロードすることができます (この情報は、「拡張**機能の概要」** ページに表示されています)。  

> [!NOTE]
> 内線番号を**公開**し、後で [**非公開**] に変更した場合、内線番号が公開されているユーザーは、今後の更新プログラムにアクセスして受け取ることができます。  

### 市場の定義  

内線番号を提供する特定の市場を定義する必要があります。 [**利用可能状況**] ページの [**市場**] セクションで、[**オプションの表示**] を選択します。  市場選択のポップアップウィンドウが表示され、そこで市場を選ぶことができます。  既定では、後で追加される可能性がある**将来の市場**も含めて、すべての市場が選択されます。  個々の市場の選択を解除して除外することができます。または、[**すべて選択解除**] をクリックし、選択した個々の市場を追加することもできます。  

> [!NOTE]
> ユーザーが既に特定の市場に内線番号を持っていて、その市場でその市場を削除した場合、その市場の内線番号を既に持っているユーザーはその市場を引き続き使用できますが、提出した後の更新プログラムは取得できません。  

[**保存**] をクリックして、[**プロパティ**] セクションに進みます。  

## 手順 4: 拡張機能のプロパティを選択する  

### 拡張機能のプロパティ  

*   [カテゴリ](#category)  
*   [プライバシーポリシーの要件](#privacy-policy-requirements)  
*   [プライバシー ポリシーの URL](#privacy-policy-url)  
*   [Web サイトの URL](#website-url)  
*   [サポート URL/メールアドレス](#support-urlemail-address)  
*   [内線番号の評価](#extension-rating)  

#### カテゴリ  

適切なカテゴリに拡張機能を登録すると、ユーザーは拡張機能を簡単に見つけて理解することができます。  拡張機能に最も適したカテゴリを選択します。  

指定**可能な値**:  

*   `Accessibility`  
*   `Blogging`  
*   `Developer Tools`  
*   `Fun`  
*   `News & Weather`  
*   `Photos`  
*   `Productivity`  
*   `Search Tools`  
*   `Shopping`  
*   `Social & Communication`  
*   `Sports`  

#### プライバシーポリシーの要件  

拡張機能で個人情報へのアクセス、収集、または送信を行うかどうかを指定します。  

> [!NOTE]
> お客さまの内線番号にプライバシーポリシーが必要であり、提供されていない場合は、申請が認定に合格しない可能性があります。  

指定**可能な値**:  

*   `No`: プライバシーポリシーの URL は省略可能です。  
*   `Yes`: プライバシーポリシー URL が必要です。  

#### プライバシー ポリシーの URL  

お客様は、お客様がお客様の内線番号とプライバシーポリシーに準拠していること、および必要に応じて有効なプライバシーポリシー URL を提供する責任を負います。  個人情報が、内線番号によってアクセス、送信、または収集される場合は、プライバシーポリシー URL を指定する必要があります。  
拡張機能にプライバシーポリシーが必要かどうかを判断するには、 [Microsoft Edge Developer Agreement][MicrosoftAppDeveloperAgreement]と[Microsoft Edge アドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]を確認してください。  

指定**可能な値**:  

*   `{url}`  

#### Web サイトの URL  

このプロパティは省略可能です。  
拡張機能の web ページの URL です。  この URL は、お客様の web サイトのページを指している必要があります。 Microsoft Edge アドオンの内線番号の web サイトではありません。  

指定**可能な値**:  

*   `{url}`  

#### サポート URL/メールアドレス  

このプロパティは省略可能です。  
ユーザーが拡張機能をサポートするために使用する web ページの URL、またはサポートのために連絡するメールアドレス。  すべての申請のサポート情報が含まれているので、ユーザーが自分のサポートを受ける方法を知ることができます。  

指定**可能な値**:  

*   `{email_address}`  
*   `{url}`  

#### 内線番号の評価  

拡張評価は、お客様の内線番号の対象ユーザーの年齢を決定するのに役立ちます。  
拡張機能に成熟したコンテンツがあるかどうかを判断するには、 [Microsoft Edge のアドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]を確認してください。  

指定**可能な値**:  

*   成熟した \ (チェックボックス \): 拡張機能に成熟したコンテンツが含まれている場合は、このチェックボックスをオンにします。  拡張機能として「成熟」を選択した場合、その登録情報には、拡張機能に成熟したコンテンツが含まれていることを示す個別のタグが表示されます。  

[**保存**] をクリックして、セクションの一覧に進みます。  

## 手順 5: 拡張機能の一覧情報を追加する  

これは、Microsoft Edge のアドオンで登録情報を表示するときにユーザーに表示される情報です。  リスト内の多くのフィールドはオプションですが、リストを目立たせるためにできるだけ多くの情報を提供することをお勧めします。 Microsoft Edge のアドオンの完了と見なされるために必要な最低限の情報は、拡張機能パッケージで指定された各言語の[テキスト説明](#description)、[拡張ロゴ](#store-logo)、および[小さいプロモーションタイル](#small-promotional-tile)です。  

### ストア登録情報フィールド  

*   [ストア登録情報の言語](#store-listing-languages)  
*   [ストアの表示名](#store-display-name)  
*   [説明](#description)  
*   [ストアロゴ](#store-logo)  
*   [小規模のプロモーションタイル](#small-promotional-tile)  
*   [メディア](#media)  
*   [簡単な説明](#short-description)  
*   [検索語句](#search-terms)  

#### ストア登録情報の言語  

拡張機能パッケージで複数の言語がサポートされている場合は、各言語の登録情報ページが必要です。  
言語ごとに同じコンテンツを使用している場合は、各言語のリストの詳細 \ (テキストの説明、画像など) を個別に入力する必要があります。  拡張機能が複数の言語でローカライズされている場合、これらの言語は、一覧ページの上部に表示されます。  

1.  [**言語] ドロップダウン**リストから1つの言語名を選択します。  
1.  登録情報を入力します。  
1.  **[保存]** をクリックします。  
1.  サポートされているすべての言語について同じ手順を繰り返します。  

> [!NOTE]
> Microsoft Edge アドオンで登録する言語を追加または削除するには、拡張機能パッケージでサポートされている言語の一覧を変更してから、もう一度アップロードする必要があります。  

指定**可能な値**:  

*   `English (United States)`: これは既定値です。  パッケージの言語について説明していない場合は、既定の言語を英語 (米国) に設定し、英語 (米国) で登録する必要があります。  
*   `{language}` \(`{Country}`\)  

#### ストアの表示名  

拡張機能パッケージマニフェストで示されている拡張子の名前。  

> [!NOTE]
> 名前を編集するには、拡張機能パッケージのマニフェストを更新して、もう一度アップロードする必要があります。  

#### 説明  

このフィールドは必須です。  
拡張機能のユーザーについての説明。  

指定**可能な値**:  

*   {plain_text}: 1万文字未満  

#### ストアロゴ  

このフィールドは必須です。  
拡張ロゴの1:1 画像。  

指定**可能な値**:  

*   128px x 128px、PNG \ (.png \)  
*   150px x 140px、PNG \ (.png \)  
*   300px x 300px、PNG \ (.png \): 推奨サイズ。  

#### 小規模のプロモーションタイル  

このフィールドは必須です。  
小さいサイズのプロモーションタイル。  このタイルには、登録情報が表示されます。  

指定**可能な値**:  

*   440px x 280x, PNG \ (.png \)  

#### メディア  

このフィールドは省略可能です。  
製品をより効果的に表示するために、これらのアセットを提供する必要があります。  

*   スクリーンショット  
    拡張機能について説明する拡張機能の画像。  
    
*   大きなプロモーションタイル  
    大きなプロモーションタイルは、Microsoft Edge のアドオンで拡張機能をより目立つようにするためのものです。  
    
*   YouTube ビデオの URL  
    [内線番号の有効な YouTube ビデオ URL][MicrosoftEdgeAddonsUploadYouTubeVideo]。  ビデオの品質と最小の長さは、適切である必要があります。  Microsoft Edge のアドオンで、内線番号を公開する前に、YouTube ビデオが認定に合格している必要があります。  YouTube ビデオが[Microsoft Edge アドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]に準拠していることを確認します。  

指定**可能な値**:  

*   最大10個のスクリーンショット。  
    *   640 px x 480px、PNG \ (.png \): スクリーンショット。  
    *   1280px x 800px、PNG \ (.png \): スクリーンショット。  
*   1400px x 560px、PNG \ (.png \): 大きなプロモーションタイル。  
*   60秒または短い間の YouTube ビデオ URL。  

#### 簡単な説明  

Catchy の簡単な説明。製品の一覧の一番上に表示されることがあります。  指定しない場合は、長い説明の最初の数行が代わりに使用されます。  説明はこのテキストの下にも表示されているため、リストが繰り返されないように、別のテキストの短い説明を入力する必要があります。  拡張機能の短い説明は、パッケージのマニフェストファイルから直接選択されます。  

> [!NOTE]
> 短い説明を編集するには、拡張機能パッケージのマニフェストを更新して、もう一度アップロードする必要があります。  

#### 検索語句  

検索用語は、ユーザーには表示されない1つの単語または短いフレーズですが、ユーザーがこれらの用語を使用して検索するときに、Microsoft Edge のアドオンで拡張機能を見つけることができます。  

**要件**:  

*   7つ以下の検索語句  
*   検索用語あたり30文字以下  
*   検索語句の合計が21以下である  

[**保存**] をクリックして、リストセクションの保存に進みます。  [**発行**] をクリックして、申請の詳細を入力します。  

## 手順 6: 申請を完了し、[発行] をクリックします。  

拡張機能の申請プロセスの [申請オプション] ページでは、製品を適切にテストするための詳細情報を提供しています。  これは省略可能な手順ですが、多くの申請にお勧めします。  

### 公開の保留オプション  

既定では、申請は認定に合格するとすぐに公開されます。  特定の日付まで申請を発行することを保留にすることができます。  ここでは、このセクションのオプションについて説明します。  

*   **認定に合格するとすぐに申請を公開する**  

    これは既定の選択です。  これは、申請が認定に合格するとすぐに、発行プロセスを開始することを意味します。  

*   **特定の日に申請の公開を開始する**  

    [特定の**日付に提出の発行を開始**する] を選択して、申請が特定の日付まで公開されないようにします。  このオプションを使用すると、指定した日付以降に、できるだけ早く申請がリリースされます。  日付は 24 時間以上先の日付にする必要があります。  日付と共に、提出を開始する時刻を指定することができます。  

### 認定の注意書き  

内線番号を申請するときに、[認定のメモ] ページを使用して、認定テスト担当者に追加情報を提供するオプションがあります。  この情報は、拡張機能が正しくテストされていることを確認するために役立ちます。  申請を完全にテストできない場合は、認定が不合格になることがあります。  

以下の \ (内線番号に該当する場合) を必ず含めてください。  

*   テストアカウントのユーザー名とパスワード。  
*   非表示の機能やロックされた機能にアクセスする手順。  
*   地域またはその他のユーザー設定に基づいて、動作の違いが予測されます。  
*   アプリの更新プログラムで変更された内容に関する情報。  
*   テスターが申請について理解していると思われるその他のもの。  

上記の詳細を完了したら、[**発行**] をクリックして、Microsoft Edge のアドオンで拡張機能を送信します。  

拡張機能の申請の作成が完了し、[**公開**] をクリックすると、申請が認定手順に入ります。  通常、このプロセスは数日以内に完了します。ただし、場合によっては、最大7営業日かかる場合があります。  申請が認定に合格すると、特定の日付までリリースされないように指定するために、[公開保留] オプションを選択していない限り、拡張機能が Microsoft Edge のアドオンに公開されます。  申請が公開され、ダッシュボードの内線番号がに変更されたときに通知され `In the Store` ます。  

<!-- image links -->  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge \ (Chromium \) Extensions の概要 |Microsoft ドキュメント"  

[MicrosoftEdgeAddonsUploadYouTubeVideo]: ./upload-video.md "YouTube のビデオをアップロードする |Microsoft ドキュメント"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge アドオンカタログ開発者ポリシー |Microsoft ドキュメント"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "アプリ開発者契約 |Microsoft ドキュメント"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  