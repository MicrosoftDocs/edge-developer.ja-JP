---
description: Microsoft Store で発行することで PWA の発見を可能にする
title: プログレッシブ Web アプリを Microsoft Store に発行する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ Web アプリ、PWA、Edge、Windows、Microsoft Store
ms.openlocfilehash: 5e78e909187408566219ffe80779bb9221b585fa
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "11527073"
---
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>プログレッシブ Web アプリを Microsoft Store に発行する  

プログレッシブ Web アプリ \(PWA\) を [Microsoft Store][WindowsUwpPublishIndex] に発行すると、次のような利点があります。  

:::row:::
   :::column span="1":::
      **見つけやすさ**  
   :::column-end:::
   :::column span="2":::
      ユーザーは当然、アプリ ストアでアプリを探します。  Microsoft Store に発行すると、何百万人もの Windows ユーザーが他の Windows アプリと共に PWA を検出する場合があります。  ストアでは、カテゴリ、キュアされたコレクションなど、アプリを紹介します。  アプリ検出ポータルは、アプリの潜在的なユーザーに対して簡単な閲覧とショッピング エクスペリエンスを提供します。  スクリーンショット、 [ヒーロー画像、][WindowsUwpPublishAppScreenshotsImages] ビデオトレーラーを使用してストアの登録情報を強化することもできます。  
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
1.  これで、アカウントがアプリ開発者プログラムに登録されます。 アプリの予約を作成するには、次の操作を実行します。  
    1.  Xbox の **Windows &移動します**。  
    1.  [概要 **]**  >  **[新しいアプリの作成] を選択します**。  
    1.  プロンプトにアプリの名前を入力します。  
    1.  を選択します `Reserve product name` 。  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="Windows パートナー センターでアプリの予約を作成する" lightbox="./media/windows-partner-center-create-app.msft.png":::
       Windows パートナー センターでアプリの予約を作成する  
    :::image-end:::  
    
1.  [[PWA](#package-your-pwa-for-the-store)のパッケージ化] セクションで使用する発行元の詳細を表示するには、[製品管理**製品 ID]**  >  **を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="発行元情報を Windows パートナー センターからコピーする" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       発行元情報を Windows パートナー センターからコピーする  
    :::image-end:::  
    
1.  次の値をコピーして保存します。  
    *   **パッケージ ID**  
    *   **Publisher ID**  
    *   **Publisher の表示名**  
        
## <a name="package-your-pwa-for-the-store"></a>PWA をストア用にパッケージ化する 

アプリの発行情報が得たので、PWA 用の Windows アプリ パッケージを生成します。

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
1.  Windows アプリ パッケージをダウンロードするには、[ダウンロード] を **選択します**。

ダウンロードは、ファイル `.zip` とファイルを含 `.msixbundle` むアーカイブ `.classic.appxbundle` です。  2 つのアプリ パッケージを使用すると、PWA をさまざまな Windows バージョンで実行できます。  詳細については、「クラシック パッケージ [とは」に移動します][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]。  

### <a name="submit-your-app-package-to-the-store"></a>アプリ パッケージをストアに提出する  

アプリをストアに送信するには、次のアクションを実行します。  

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
        
1.  [パッケージ **] プロンプト** で、[PWA のパッケージ化] セクションで生成した `.msixbundle` `.classic.appxbundle` ファイル [とファイルを選択](#package-your-pwa-for-the-store) します。  
    
申請が完了すると、アプリは通常 24 ~ 48 時間以内に確認されます。  承認を受け取った後、PWA は Microsoft Store で利用できます。  

## <a name="see-also"></a>関連項目  

PWABuilder には、Microsoft Store で PWA を取得するのに役立つその他のドキュメントが含まれています。  

*   [PWA アプリ パッケージをテストして提出する][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [新しい PWA をストアに発行する][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [既存のストア アプリを PWA に更新する][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [ストア内の PWA のイメージの推奨事項][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [アプリパッケージの説明者][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store ポリシー |Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "アプリのパフォーマンス の分析|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "アプリのスクリーンショット、画像、トレーラー|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "Windows アプリとゲーム を公開|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "ホーム |Microsoft パートナー センター"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "パートナー向けリソース |Microsoft パートナー センター"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows Apps |Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "ホスト型アプリ モデル |Windows 開発者ブログ"  

[GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/classic-package.md "クラシック パッケージとは何|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/image-recommendations.md "Windows PWA パッケージのイメージ|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/next-steps.md "Microsoft Store サーバーに PWA を取得するための次の|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/publish-new-app.md "ストア アプリに新しいアプリを発行|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/update-existing-app.md "ストア アプリで既存のアプリを更新|GitHub"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  
