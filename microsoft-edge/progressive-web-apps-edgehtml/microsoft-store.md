---
description: Microsoft ストアで PWA を配布して、Windows 10 ユーザーの世界に連絡する
title: Microsoft Store のプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、Microsoft Store、Bing PWA インデックス
ms.openlocfilehash: a4491f19b89e8b0f6fa511f146744499e2074f22
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570761"
---
# Microsoft Store のプログレッシブ Web アプリ

プログレッシブ Web アプリ (PWA) を[Microsoft ストア](https://developer.microsoft.com/store)に公開すると、アプリの対象ユーザーは、約7億のアクティブな月次ユーザーの Windows 10 インストールベース全体に拡張します。 

Microsoft Store では、次のようなさまざまなメリットを享受できます。

- 検索のし**やすさ**-Microsoft Store のアプリは、さまざまなカテゴリ、curated コレクション、検索フィルターによって紹介されており、アプリの潜在的な顧客にとって簡単な閲覧とショッピングエクスペリエンスを提供します。 スクリーンショット、ヒーローの画像、ビデオの予告編を使って、[ストア登録](/windows/uwp/publish/app-screenshots-and-images)情報を拡張することもできます。

- **信頼性**-Windows のお客様は、microsoft の厳密な[品質と安全性の標準](/legal/windows/agreements/store-policies)に準拠しているため、microsoft ストアの購入とダウンロードを信頼できることをご存じです。

- **簡単なインストール**-Microsoft Store は、[すべての Windows 10 アプリ](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)で一貫したユーザーフレンドリなインストールエクスペリエンスを提供します。これにより、すべてのユーザーが、技術的な安心レベルにかかわらず、PWA を簡単にインストールできるようになります。

- **Business insights** -Microsoft Store 用[windows デベロッパーセンターダッシュボード](/windows/uwp/publish/using-the-windows-dev-center-dashboard)では、PWA が使用している windows ユーザーの数や、ユーザーがどのように話しているかについて、[詳細な分析](/windows/uwp/publish/analytics)を行うことができます。 アプリの正常性、広告の使用状況などに関するメトリックとテレメトリデータも見つけることができます。

Microsoft ストアに PWA をダウンロードするには、次の2つのオプションがあります。

1. [手動で送信](#submitting-your-pwa-manually)することもできます。

2. PWA が特定の[条件](#criteria-for-automatic-submission)を満たしている場合は、Bing web クローラーによって[インデックスが自動的に](#automatic-pwa-importing-with-bing)作成されます。 (自動申請の解除を[選択](#opting-out-of-automatic-microsoft-store-import)することもできます)。

申請方法に関係なく、PWA が Microsoft Store に承認されると、上記のすべての特典にアクセスできるようになります。

## 手動で PWA を送信する

Microsoft ストアでアプリを配布および昇格するには、そのアプリを Windows アプリパッケージ (*.appx*ファイル) として提出する必要があります。  PWAs などのサーバーでホストされる web アプリの場合、このパッケージには、アプリのメタデータとホーム画面のアイコン (および実際のアプリケーションコードは含まれません) が含まれます。 これにより、web アプリをホーム画面から他の[Windows 10 アプリ](/windows/uwp/get-started/whats-a-uwp)と共にインストールして起動することができます。これには、Microsoft Edge ブラウザーウィンドウとは別に、軽量のネイティブアプリラッパー (*wwahost*プロセス) で実行します。  

> [!IMPORTANT]
> EdgeHTML web platform engine は、Microsoft Edge (Chromium) ベースの PWA との互換性の違いをもたらす、WWAHost アプリラッパーによって使用されます。  EdgeHTML エンジンが新しい web 標準によって更新されなくなったため、microsoft Edge (EdgeHTML) を使ってアプリケーションの完全なテストパスを作成してください。  

その方法は次のとおりです。

### 前提条件

- **既存の PWA**。 Web アプリがまだ存在しない場合は、次のようにして[PWA に変換](./get-started.md)する方法を説明します。 
- **PWAs 用の WINDOWS APPX パッケージツールがありました**。 Visual Studio を使って[Windows で PWA をビルドして実行](./windows-features.md)する方法を次に示します。 また、 [PWA ビルダー](https://www.pwabuilder.com/)を使用して、Windows パッケージを作成することもできます。
- [**Microsoft ストアアプリの開発者アカウント**](/windows/uwp/publish/opening-a-developer-account)。 選択したアカウントの種類と場所によっては[1 回限りの料金](/windows/uwp/publish/account-types-locations-and-fees)が発生し、登録には有効な[Microsoft アカウント](https://account.microsoft.com/)が必要です。


### *Visual Studio*によるストアの申請 

Visual Studio で PWA の[アプリパッケージアップロードファイルを作成](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file)するには、次の手順を実行します。 このプロセスの一般的な概要については、「 [*UWP アプリで Visual Studio をパッケージ化*](/windows/uwp/packaging/packaging-uwp-apps)する」を参照してください。

この手順では、 [**Windows アプリ認定キット**](https://developer.microsoft.com/windows/develop/app-certification-kit)を実行して、Microsoft ストアの要件に準拠したアプリをテストする方法についても説明します。 これはオプションですが、強くお勧めします。

### *Windows デベロッパーセンター*を使用したストアへの申請

ここでは、 *PWA ビルダー*を使用して、Windows デベロッパーセンターにアップロードするためのアプリパッケージを生成する方法について説明します。

1. Windows 10 アプリを生成します。 [Visual Studio で Windows アプリとして PWA](./windows-features.md)を実行する方法について説明します。 また、 [PWA ビルダー](https://www.pwabuilder.com/)を使用して、Windows 10 アプリを生成することもできます。

2. Microsoft ストアのアプリ名を予約するには、アカウント情報を使用して[Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にログインし、[名前を予約してアプリを作成](/windows/uwp/publish/create-your-app-by-reserving-a-name)する手順に従います。 予約する名前は、Microsoft Store 全体で一意にする必要があります。

3. アプリのパッケージをアップロードするときに、 *package.appxmanifest*ファイルの*DisplayName*、 *Name*、 *Publisher*、および*PublisherDisplayName*の値は、名前を予約するときに、Windows デベロッパーセンターダッシュボードのアプリに割り当てられている値と一致する必要があります。 

    [Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にログインし、[**アプリ管理**] の下の [アプリ id] の値を探し  >  **App identity**ます。

    ![Windows デベロッパーセンターダッシュボードのアプリ id の設定](./media/dashboard-app-identity.png)

    次に、ファイルを見つけ `appxmanifest.xml` て、次の値を Windows デベロッパーセンターダッシュボードに割り当てられているものに置き換えます。

    - **<Identity Name = "** *Package/identity/Name* "
    - **<Identity Publisher = "** *Package/identity/Publisher*
    - **DisplayName<** **>***アプリ用に予約した名前* 
    - **<PublisherDisplayName** **>***Package/Properties/PublisherDisplayName***</PublisherDisplayName>**

4. これで、すべての PWA リソースを1つのファイルにコンパイルして、 `.appx` Microsoft Store にアップロードする準備ができました。 コマンドプロンプトで、web マニフェストのディレクトリに移動し、Windows 10 パッケージを作成します ([オプションのデバッグログ] の下で指定します)。

    ```
    pwabuilder package -p windows10 -l debug
    ```

    この場所に .appx ファイルが生成さ `PWA\Store packages\windows10\package\windows.appx` れます。

5. アプリを Microsoft Store にアップロードする前に、Microsoft ストアのポリシーに準拠するようにアプリをテストすることをお勧めします。 これを行うには、 [**Windows アプリ認定キット**](https://developer.microsoft.com/windows/develop/app-certification-kit)をダウンロードして起動し、アプリの *.appx*ファイルをテスト用に選択します。 すべてのテストが完了すると、対応する領域のレポートが表示されます。

6. パッケージをアップロードし、 [Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にもう一度ログインして申請を完了し、**申請**のサブページを展開し  >  **Submisison 1**ます。 チェックリストに従って、[必要なストア登録情報](/windows/uwp/publish/app-submissions)を入力し、[アプリパッケージをアップロード](/windows/uwp/publish/upload-app-packages)します。

Microsoft Store アプリ開発者が利用できるすべての機能とサービスの詳細については、「 [Windows デベロッパーセンター](https://developer.microsoft.com/windows)で[*Windows アプリを公開*](https://developer.microsoft.com/store/publish-apps)する」を参照してください。

## Bing での自動 PWA インポート

PWA の[web アプリマニフェスト](https://developer.mozilla.org/docs/Web/Manifest)は、アプリがオフラインに対応しており、完全に統合されたアプリエクスペリエンスとして提供する準備ができているプラットフォームをサポートするためのシグナルであるのと同じように、Microsoft Store で自動的に追加することを pwa に考慮する必要があります。 

PWA が以下の要件を満たしている場合、Bing インデックスサービスは、Windows 10 でのインストールに必要な[*.appx*](#submitting-your-pwa-manually)形式で pwa を自動的にパッケージ化し、web アプリマニフェストのメタデータに基づいてアプリのストア製品ページをアセンブルします。 PWA を申請した後は、Windows デベロッパーセンターダッシュボードを使って、ストアページをさらにカスタマイズして、ユーザー分析やその他のアプリ管理ツールにアクセスすることができます。

### 自動提出の条件

自動的に Microsoft ストア用にパッケージ化されて一覧表示されるようにするには、PWA に次のものが必要です。

- [X] 少なくとも次のような、空でない web アプリマニフェストファイル。

  - 名前
  - 説明
  - 512 x 512 ピクセル以上のアプリアイコン

- [X] 固有のコアロジック ([アプリの定型](https://en.wikipedia.org/wiki/Boilerplate_code)入力テンプレートから変更されたコードを最小限にしたものではありません)

- [X] セキュリティで保護された接続 (HTTPS) を介して提供される

- [X] サービスワーカースクリプト

- [X] 法律または[Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)に違反しないようにします。

Microsoft は、これらの条件を満たしているアプリをすべて取り込んではありませんが、プログラムを段階的に展開することで、候補についての考慮事項として含まれています。

### Microsoft Store の自動インポートの無効化

PWA は、次のファイルを提供することにより、Microsoft ストアへの自動インポートを無効にすることができ `robots.txt` ます。

```
User-agent: bingbot
Disallow: /manifest.json
```

これにより、Bing web クローラー (Bingbot) に、PWA インデックス作成のための web マニフェストファイルを無視するように指示されます。 Bing の通常の[web インデックス処理](https://www.bing.com/webmaster/help/help-center-661b2d18)では、サイトの検索のランク付けには影響しません。
