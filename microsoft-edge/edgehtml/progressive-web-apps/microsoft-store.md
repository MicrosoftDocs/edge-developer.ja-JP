---
description: Microsoft Store を通じて PWA を配布して、Windows 10 ユーザーの世界に到達する
title: Microsoft Store の段階的な Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ、PWA、Edge、Windows、Microsoft Store、Bing PWA インデックス
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dae25bcdf37a2496e181ab915d1686fe5d3a4985
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234670"
---
# Microsoft Store の段階的な Web アプリ

段階的な Web アプリ (PWA) を [Microsoft Store](https://developer.microsoft.com/store)に公開すると、アプリの対象ユーザーは、アクティブな毎月約 7 億人のユーザーの Windows 10 インストール ベース全体に拡大されます。 

Microsoft Store の PAS には、次のような多くの利点があります。

-   **検出可能性** - Microsoft Store のアプリは、さまざまなカテゴリ、選択されたコレクション、検索フィルターを通じて紹介され、アプリの潜在的なユーザーに簡単な閲覧とショッピングエクスペリエンスを提供します。 スクリーンショット、 [ヒーロー画像、](/windows/uwp/publish/app-screenshots-and-images) ビデオ トレーラーを使って、ストア登録情報を強化することもできます。
-   **信頼性 -** Windows のお客様は、Microsoft Store の厳格な品質と安全性の基準に従っているため、Microsoft Store の購入とダウンロードを信頼できると [知っています](/legal/windows/agreements/store-policies)。
-   **簡単な** インストール - Microsoft Store は、 [すべての Windows 10](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)アプリで一貫したユーザー フレンドリーなインストール エクスペリエンスを提供します。技術的な快適度に関係なく、すべてのユーザーが PWA を簡単にインストールできます。
-   **ビジネス**の分析情報 - Microsoft Store の Windows デベロッパー[](/windows/uwp/publish/analytics)センター ダッシュボードでは、PWA がアクセスした[Windows](/windows/uwp/publish/using-the-windows-dev-center-dashboard)ユーザーの数から、そのユーザーの使い方やユーザーの言い分まで、すべての詳細な分析が提供されます。 また、アプリの正常性や広告の使用状況に関する指標やテレメトリ データを確認することもできます。
    
PWA を Microsoft Store に取り込むには、次の 2 つのオプションがあります。

1.  手動で [送信するか](#submitting-your-pwa-manually)、または
2.  PWA が特定の条件を[満たしている](#criteria-for-automatic-submission)場合は[](#automatic-pwa-importing-with-bing)、Bing Web クローラーによって自動的にインデックスを作成できます。 (自動送信を [オプトアウト](#opting-out-of-automatic-microsoft-store-import) することもできます)。
    
申請方法に関係なく、PWA が Microsoft Store に受け入れられると、上記のすべての特典にアクセスできます。

## PWA を手動で提出する

Microsoft Store を通じてアプリを配布して販売促進するには、Windows アプリ パッケージ ( .appx ファイル) としてアプリを*提出する必要* があります。  PAS などのサーバーホスト型 Web アプリの場合、このパッケージにはアプリのメタデータとホーム画面のアイコン (実際のアプリケーション コードは含めなし) が含まれます。 これにより、Microsoft Edge のブラウザー ウィンドウから独立して、軽量なネイティブ アプリ ラッパー* (WWAHost.exe*プロセス) で実行することで、Web アプリを他の[Windows 10](/windows/uwp/get-started/whats-a-uwp)アプリと共にホーム画面からインストールして起動できます。  

> [!IMPORTANT]
> EdgeHTML Web プラットフォーム エンジンは、Microsoft Edge (Chromium) ベースの PWA の互換性の違いを生み出す可能性がある WWAHost アプリ ラッパーによって使用されます。  EdgeHTML エンジンが新しい Web 標準で更新されなくなったので、Microsoft Store にアプリを提出する前に、Microsoft Edge (EdgeHTML) を使用してアプリケーションの完全なテスト パスを実行してください。  

これを行う方法を次に示します。

### 前提条件

-   **既存の PWA 。** Web アプリを [PWA](./get-started.md) に変換していない場合の変換方法を次に示します。 
-   **PAS 用の Windows APPX パッケージ ツール**。 Windows で [PWA をビルドして実行する方法は次](./windows-features.md) Visual Studio。 PWA Builder [を使用して Windows](https://www.pwabuilder.com/) パッケージをビルドすることもできます。
-   [**Microsoft Store アプリの開発者アカウント**](/windows/uwp/publish/opening-a-developer-account)。 選択したアカウント [の種類と](/windows/uwp/publish/account-types-locations-and-fees) 場所に応じて 1 回払い料金が発生し、登録には有効な Microsoft アカウントが [必要です](https://account.microsoft.com/)。
    
### ストアでの申請の *Visual Studio* 

以下の手順に従 [って、PWA](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) 用のアプリ パッケージ アップロード ファイルを作成Visual Studio。 この [*プロセスの一般的な概要については*](/windows/uwp/packaging/packaging-uwp-apps) 、「Visual Studio UWP アプリをパッケージ化する」をご覧ください。

手順では、Windows アプリ認定キットを実行して [**、Microsoft**](https://developer.microsoft.com/windows/develop/app-certification-kit) Store の要件に準拠するためにアプリをテストする方法も説明します。 これはオプションですが、強くお勧めします。

### Windows デベロッパー センターを *使ったストア申請*

*PWA*ビルダーを使って、Windows デベロッパー センターにアップロードするアプリ パッケージを生成する方法を次に示します。

1.  Windows 10 アプリを生成します。 PWA を Windows アプリとして実行する [方法は次](./windows-features.md)Visual Studio。 PWA Builder [を使用して Windows](https://www.pwabuilder.com/) 10 アプリを生成することもできます。
2.  アカウント情報を使って [Windows デベロッパー](https://developer.microsoft.com/dashboard/windows/overview) センター ダッシュボードにログインし、名前を予約してアプリを作成する手順に従って、Microsoft Store 用のアプリ名 [を予約します](/windows/uwp/publish/create-your-app-by-reserving-a-name)。 予約する名前は、Microsoft Store 全体で一意にする必要があります。
3.  アプリのパッケージをアップロードする場合 *、.appxmanifest*ファイルの DisplayName、Name、Publisher、PublisherDisplayName の値は、名前の予約時に Windows デベロッパー センター ダッシュボードでアプリに割り当てられた値と一致する必要があります。 ** ** ** ** 
    
    Windows デベロッパー センター[ダッシュボードにログインし、](https://developer.microsoft.com/dashboard/windows/overview)アプリ管理アプリ ID の下でアプリ ID**の値**  >  **を探します**。
    
    ![Windows デベロッパー センター ダッシュボード、アプリ ID 設定](./media/dashboard-app-identity.png)
    
    次に、ファイルを見つけて、次の値を Windows デベロッパー センター ダッシュボードで割り当てられた `appxmanifest.xml` 値に置き換します。
    
    -   **<Identity Name="** *Package/Identity/Name*
    -   **<Identity Publisher="** *Package/Identity/Publisher*
    -   **<DisplayName** **>***アプリ用に予約した名前* 
    -   **<PublisherDisplayName** **>***Package/Properties/PublisherDisplayName***</PublisherDisplayName>**
        
4.  これで、すべての PWA リソースを Microsoft Store にアップロードできる 1 つのファイルにコンパイル `.appx` する準備ができました。 コマンド プロンプトで、Web マニフェストのディレクトリに移動し、Windows 10 パッケージを作成します (以下に、オプションのデバッグ ログを示します)。
    
    ```shell
    pwabuilder package -p windows10 -l debug
    ```  
    
    .appx ファイルは次の場所に生成されます `PWA\Store packages\windows10\package\windows.appx` 。
    
5.  Microsoft Store にアプリをアップロードする前に、Microsoft Store ポリシーに準拠するためにアプリをテストしてください。 これを行うには [**、Windows アプリ**](https://developer.microsoft.com/windows/develop/app-certification-kit)認定キットをダウンロードして起動し、テスト用にアプリ *の .appx* ファイルを選択します。 すべてのテストが完了すると、対処する領域のレポートが表示されます。
6.  パッケージをアップロードし[、Windows](https://developer.microsoft.com/dashboard/windows/overview)デベロッパー センター ダッシュボードにログインし **、[Submissions**  >  **Submisison 1]** パネルを展開して申請を完了します。 チェックリストに従って、必要な[ストア登録情報を入力し、](/windows/uwp/publish/app-submissions)[アプリ パッケージをアップロードします](/windows/uwp/publish/upload-app-packages)。
    
Microsoft Store アプリ開発者が利用できるすべての機能とサービスについて詳しくは、Windows デベロッパー センターで [*Windows*](https://developer.microsoft.com/store/publish-apps) アプリを公開するをご [覧ください](https://developer.microsoft.com/windows)。

## Bing による自動 PWA インポート

PWA の [Web](https://developer.mozilla.org/docs/Web/Manifest) アプリ マニフェストが、アプリがオフライン対応であり、完全に統合されたアプリ エクスペリエンスとして表示できる状態にあるプラットフォームをサポートするためのシグナルであるのと同様に、PWA が Microsoft Store に自動的に含まれると見なされる必要がある Bing Web クローラーへのヒントにもなります。 

PWA が以下の要件を満たしている場合、Bing インデックス サービスは、Windows 10 へのインストールに必要な [*.appx*](#submitting-your-pwa-manually) 形式で PWA を自動的にパッケージ化し、Web アプリ マニフェストのメタデータに基づいてアプリのストア製品ページを組み立てます。 PWA を要求すると、ストア ページをさらにカスタマイズし、Windows デベロッパー センター ダッシュボードからユーザー分析や他のアプリ管理ツールにアクセスできます。

### 自動送信の条件

Microsoft Store 用に自動的にパッケージ化および一覧表示するには、PWA で次の項目が必要です。

-   少なくとも次の条件を満たした、空でない Web アプリ マニフェスト ファイル:
    
    -   名前
    -   説明
    -   512 x 512 ピクセル以上のアプリ アイコン
        
-   固有のコア ロジック (アプリの定型テンプレートから最小限に変更 [された](https://en.wikipedia.org/wiki/Boilerplate_code) コードではない)
-   セキュリティで保護された接続 (HTTPS) 経由で提供するには
-   サービス ワーカー スクリプト
-   法律または Microsoft Store のポリシーに [違反しない](/legal/windows/agreements/store-policies)。
    
これらの条件を満たすすべてのアプリを取り込むのではなく、プログラムを段階的に拡張する際の候補の検討事項に含まれます。

### Microsoft Store の自動インポートをオプトアウトする

PWA は、次のファイルを提供することで、Microsoft Store への自動インポート `robots.txt` をオプトアウトできます。

```text
User-agent: bingbot
Disallow: /manifest.json
```  

これにより、Bing Web クローラー (Bingbot) は、PWA インデックス作成用の Web マニフェスト ファイルを無視します。 これは、Bing の通常の Web インデックス処理でのサイトの検索ランク付 [けには影響を与えいません](https://www.bing.com/webmaster/help/help-center-661b2d18)。
