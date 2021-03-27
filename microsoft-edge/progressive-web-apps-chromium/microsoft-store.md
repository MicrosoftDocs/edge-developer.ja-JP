---
description: Microsoft Store で発行することで PWA の発見を可能にする
title: プログレッシブ Web アプリを Microsoft Store に発行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、Microsoft Store
ms.openlocfilehash: 68471535446a2270a23b32205717da225fd9e4bf
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461536"
---
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>プログレッシブ Web アプリを Microsoft Store に発行する  

プログレッシブ Web アプリ \(PWA\) を [Microsoft Store][WindowsUwpPublishIndex] に発行すると、次のような利点があります。  

:::row:::
   :::column span="1":::
      **見つけやすさ**  
   :::column-end:::
   :::column span="2":::
      ユーザーは当然、アプリ ストアでアプリを探します。  Microsoft Store に発行すると、何百万人もの Windows ユーザーが他の Windows アプリと共に PWA を検出する可能性があります。  ストアでは、カテゴリ、キュアされたコレクションなど、アプリを紹介します。  アプリ検出ポータルは、アプリの潜在的なユーザーに対して簡単な閲覧とショッピング エクスペリエンスを提供します。  スクリーンショット、 [ヒーロー画像、][WindowsUwpPublishAppScreenshotsImages] ビデオトレーラーを使用してストアの登録情報を強化することもできます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **信頼度**  
   :::column-end:::
   :::column span="2":::
      Windows のお客様は、Microsoft Store の厳しい品質と安全基準に従うので、Microsoft Store の購入とダウンロードを信頼できる可能性[があります。][LegalWindowsAgreementsStorePolicies]  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **簡単なインストール**  
   :::column-end:::
   :::column span="2":::
      Microsoft Store は、すべての Windows 10 アプリで一貫性のあるユーザーフレンドリー [なインストール エクスペリエンスを提供します][MicrosoftStoreAppsWindows]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **アプリ分析**  
   :::column-end:::
   :::column span="2":::
      [Windows パートナー センター ダッシュボードには][WindowsUwpPublishIndex]、アプリの正常性、使用状況などについての詳細な分析が提供されます。 [][WindowsUwpPublishAnalytics]  
   :::column-end:::
:::row-end:::  

PWA を Microsoft Store に発行するには、コードの変更は必要ありません。  代わりに、アプリの予約を作成し、PWA をパッケージ化し、パッケージをストアに提出します。  以下のセクションでは、手順について説明します。   

## <a name="create-an-app-reservation"></a>アプリの予約を作成する  

[Windows パートナー センター][MicrosoftPartnerDashboardWindowsOverview] は、アプリを Microsoft Store に提出するハブです。  

アプリの予約を作成するには、次の操作を実行します。  

1.  登録済みプログラムを表示するには、次のアクションを実行します。  
    1.  Microsoft アカウントで Windows パートナー センターにサインインし、パートナー センター [ダッシュボードに移動します][MicrosoftPartnerDashboardHome]。  
    1.  Xbox の **Windows &移動する**  
        *   **Xbox に Windows &が**表示されている場合、アプリは既に登録されています。  
        *   **Windows の Xbox &が**表示されない場合は、[プログラムの追加]**を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="Windows パートナー センター ダッシュボードにプログラムを追加する" lightbox="./media/windows-partner-center-add-program.msft.png":::
       Windows パートナー センター ダッシュボードにプログラムを追加する
    :::image-end:::  
    
1.  開発者プログラムに登録するには、次のアクションを実行します。  
    1.  Xbox の **Windows &移動します**。  
    1.  [スタート **] を選択します**。  
    1.  画面に表示される指示に従います。  
1.  これで、アプリはアプリ開発者プログラムに登録されます。 アプリの予約を作成するには、次の操作を実行します。  
    1.  Xbox の **Windows &移動します**。  
    1.  [概要 **]**  >  **[新しいアプリの作成] を選択します**。  
    1.  プロンプトに PWA 名を入力します。  
    1.  を選択します `Reserve product name` 。  
    
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="Windows パートナー センターでアプリの予約を作成する" lightbox="./media/windows-partner-center-create-app.msft.png":::
       Windows パートナー センターでアプリの予約を作成する  
    :::image-end:::  

1.  [[PWA](#package-your-pwa)のパッケージ化] セクションで使用する発行元の詳細を表示するには、[製品管理**製品 ID]**  >  **を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="発行元情報を Windows パートナー センターからコピーする" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       発行元情報を Windows パートナー センターからコピーする  
    :::image-end:::  

1.  次の値をコピーして保存します。  
    *   **パッケージ ID**  
    *   **Publisher ID**  
    *   **Publisher の表示名**  
        
## <a name="package-your-pwa"></a>PWA のパッケージ化  

PWA 用の Windows アプリ パッケージを生成します。  

アプリ パッケージは、名前、説明、アイコンなど、アプリのメタデータを含む `.msixbundle` ファイルです。  ホスト型アプリ [モデルを使用し][WindowsBlogWindowsdeveloperHostedAppModel]、Microsoft Edge が PWA に電力を供給します。  このモデルでは、PWA は Windows アプリとして機能しながら、最新の Web 機能を使用します。  最新の Web 機能には、サービス ワーカー、オフライン、プッシュ通知、バッドなどがあります。  

アプリ パッケージを生成するには、次のアクションを実行します。  

1.  [PWA ビルダーに移動します][PwabuilderMain]。  
1.  PWA の URL を入力します。  
1.  [ビルド**の**  >  **開始] [PWA**  >  **Windows オプション]**  >  **を選択します**。  
1.  [アプリの予約の作成] セクションに保存した次 [の値を貼り付](#create-an-app-reservation) けます。  
    *   **パッケージ ID**  
    *   **Publisher ID**  
    *   **Publisher の表示名**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="PWABuilder に発行元情報を貼り付ける" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       PWABuilder に発行元情報を貼り付ける  
    :::image-end:::  
    
1.  [完了 **] を選択します**。  
1.  Windows アプリ パッケージをダウンロードするには、[ダウンロード] を **選択します**。  ダウンロードは、ファイル `.zip` を含むアーカイブ `.msixbundle` です。  [アプリ `.msixbundle` パッケージを [ストアに送信する] セクションのファイルを使用](#submit-your-app-package-to-the-store) します。  

### <a name="submit-your-app-package-to-the-store"></a>アプリ パッケージをストアに提出する  

これで、アプリ パッケージ `.msixbundle` が作成されます。  アプリ パッケージをストアに送信するには、次のアクションを実行します。  

1.  Windows パートナー [センターに移動する][MicrosoftPartnerDashboardWindowsOverview] 
1.  アプリを選択します。  
1.  [申請 **の開始] を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="Windows パートナー センターで新しいアプリの申請を開始する" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       Windows パートナー センターで新しいアプリの申請を開始する  
    :::image-end:::  
    
1.  アプリに関する情報を求めるプロンプトを次に示します。
    *   pricing  
    *   年齢の評価  
    *   およびその他  
        
1.  [パッケージ **] プロンプト** で、[PWA のパッケージ化] セクション `.msixbundle` で生成 [したファイルを選択](#package-your-pwa) します。  

申請が完了すると、アプリは通常 24 ~ 48 時間以内に確認されます。  承認を受け取った後、PWA は Microsoft Store で利用できます。  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store ポリシー |Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "アプリのパフォーマンス の分析|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "アプリのスクリーンショット、画像、トレーラー|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "Windows アプリとゲーム を公開|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "ホーム |Microsoft パートナー センター"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "パートナー向けリソース |Microsoft パートナー センター"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows Apps |Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "ホスト型アプリ モデル |Windows 開発者ブログ"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  

