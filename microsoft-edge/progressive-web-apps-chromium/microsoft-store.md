---
description: サイトにPWA発行することで、ユーザーのコンテンツをより見Microsoft Store
title: プログレッシブ Web アプリをアプリに発行Microsoft Store
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
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>プログレッシブ Web アプリをアプリに発行Microsoft Store  

プログレッシブ Web アプリ \(PWA\) を[Microsoft Store利点があります][WindowsUwpPublishIndex]。  

:::row:::
   :::column span="1":::
      **見つけやすさ**  
   :::column-end:::
   :::column span="2":::
      ユーザーは当然、アプリ ストアでアプリを探します。  アプリに発行すると、Microsoft Storeのユーザー Windows他のアプリとPWA見Windowsがあります。  ストアでは、カテゴリ、キュアされたコレクションなど、アプリを紹介します。  アプリ検出ポータルは、アプリの潜在的なユーザーに対して簡単な閲覧とショッピング エクスペリエンスを提供します。  スクリーンショット、 [ヒーロー画像、][WindowsUwpPublishAppScreenshotsImages] ビデオトレーラーを使用してストアの登録情報を強化することもできます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **信頼度**  
   :::column-end:::
   :::column span="2":::
      Windows顧客は、厳格な[Microsoft][LegalWindowsAgreementsStorePolicies]の品質と安全基準に準拠Microsoft Store購入とダウンロードを信頼できる可能性があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **簡単なインストール**  
   :::column-end:::
   :::column span="2":::
      このMicrosoft Storeは、すべてのアプリで一貫したユーザーフレンドリーな[インストール エクスペリエンスWindows 10します][MicrosoftStoreAppsWindows]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **アプリ分析**  
   :::column-end:::
   :::column span="2":::
      パートナー [Windowsダッシュボードには][WindowsUwpPublishIndex]、アプリの正常性、使用状況[][WindowsUwpPublishAnalytics]などについての詳細な分析が提供されます。  
   :::column-end:::
:::row-end:::  

アプリケーションをPWAするにはMicrosoft Storeコードを変更する必要はありません。  代わりに、アプリの予約を作成し、PWAをパッケージ化し、パッケージをストアに提出します。  以下のセクションでは、手順について説明します。   

## <a name="create-an-app-reservation"></a>アプリの予約を作成する  

[Windows パートナー センター][MicrosoftPartnerDashboardWindowsOverview]は、アプリをアプリに送信するハブMicrosoft Store。  

アプリの予約を作成するには、次の操作を実行します。  

1.  登録済みプログラムを表示するには、次のアクションを実行します。  
    1.  Microsoft アカウントWindowsパートナー センターにサインインし、パートナー センター[ダッシュボードに移動します][MicrosoftPartnerDashboardHome]。  
    1.  Xbox のWindows &**移動**  
        *   **Xbox Windows &表示**されている場合、アプリは既に登録されています。  
        *   Xbox **Windows &表示**されない場合は、[プログラムの追加]**を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="パートナー センター ダッシュボードにプログラムWindows追加する" lightbox="./media/windows-partner-center-add-program.msft.png":::
       パートナー センター ダッシュボードにプログラムWindows追加する
    :::image-end:::  
    
1.  開発者プログラムに登録するには、次のアクションを実行します。  
    1.  Xbox に移動**Windows &移動します**。  
    1.  [スタート **] を選択します**。  
    1.  画面に表示される指示に従います。  
1.  これで、アカウントがアプリ開発者プログラムに登録されます。 アプリの予約を作成するには、次の操作を実行します。  
    1.  Xbox に移動**Windows &移動します**。  
    1.  [概要 **]**  >  **[新しいアプリの作成] を選択します**。  
    1.  プロンプトにアプリの名前を入力します。  
    1.  を選択します `Reserve product name` 。  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="パートナー センターでアプリの予約Windows作成する" lightbox="./media/windows-partner-center-create-app.msft.png":::
       パートナー センターでアプリの予約Windows作成する  
    :::image-end:::  
    
1.  [パッケージを作成する] セクションで使用する発行元のPWAを表示するには[、[](#package-your-pwa-for-the-store)製品管理製品**ID]**  >  **を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="パートナー センターから発行元情報Windowsコピーする" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       パートナー センターから発行元情報Windowsコピーする  
    :::image-end:::  
    
1.  次の値をコピーして保存します。  
    *   **パッケージ ID**  
    *   **PublisherID**  
    *   **Publisher表示名**  
        
## <a name="package-your-pwa-for-the-store"></a>ストアのPWAパッケージ化 

アプリの発行情報が得たので、アプリのWindowsを生成PWA。

アプリ パッケージを生成するには、次のアクションを実行します。  

1.  [ビルダー] [PWA移動します][PwabuilderMain]。  
1.  ユーザーの URL を入力PWA。  
1.  [**ビルドの**  >  **開始] を選択**  >  **PWA Windows**  >  **オプションを選択します**。  
1.  [アプリの予約の作成] セクションに保存した次 [の値を貼り付](#create-an-app-reservation) けます。  
    *   **パッケージ ID**  
    *   **PublisherID**  
    *   **Publisher表示名**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="PWABuilder に発行元情報を貼り付ける" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       PWABuilder に発行元情報を貼り付ける  
    :::image-end:::  
    
1.  [完了 **] を選択します**。  
1.  アプリ パッケージをWindowsするには、[ダウンロード] を**選択します**。

ダウンロードは、ファイル `.zip` とファイルを含 `.msixbundle` むアーカイブ `.classic.appxbundle` です。  2 つのアプリ パッケージを使用PWAさまざまなバージョンで実行Windowsできます。  詳細については、「クラシック パッケージ [とは」に移動します][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]。  

### <a name="submit-your-app-package-to-the-store"></a>アプリ パッケージをストアに提出する  

アプリをストアに送信するには、次のアクションを実行します。  

1.  [パートナー センター [Windowsに移動します。][MicrosoftPartnerDashboardWindowsOverview] 
1.  アプリを選択します。  
1.  [申請 **の開始] を選択します**。  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="パートナー センターで新しいアプリWindows開始する" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       パートナー センターで新しいアプリWindows開始する  
    :::image-end:::  
    
1.  アプリに関する情報を求めるプロンプトを次に示します。
    *   pricing  
    *   年齢の評価  
    *   およびその他  
        
1.  [パッケージ **] プロンプト**で、[パッケージを作成する] セクションで生成したファイル `.msixbundle` `.classic.appxbundle` [PWA](#package-your-pwa-for-the-store)します。  
    
申請が完了すると、アプリは通常 24 ~ 48 時間以内に確認されます。  承認を受け取った後、PWAのサイトでMicrosoft Store。  

## <a name="see-also"></a>関連項目  

PWABuilder には、ドキュメントを作成するためのドキュメントがPWA提供Microsoft Store。  

*   [アプリ パッケージをテストPWA提出する][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [ストアに新PWAを発行する][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [既存のストア アプリをアプリに更新PWA][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [ストア内の PWA のイメージの推奨事項][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [アプリパッケージの説明者][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Storeポリシー|Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "アプリのパフォーマンス の分析|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "アプリのスクリーンショット、画像、トレーラー|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "アプリWindowsゲームを公開|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "ホーム |Microsoft パートナー センター"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "パートナー向けリソース |Microsoft パートナー センター"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windowsアプリ|Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "ホスト型アプリ モデル |Windows開発者向けブログ"  

[GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/classic-package.md "クラシック パッケージとは何|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/image-recommendations.md "パッケージのイメージWindows PWA|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/next-steps.md "次の手順では、PWAにMicrosoft Store |GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/publish-new-app.md "ストア アプリに新しいアプリを発行|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/update-existing-app.md "ストア アプリで既存のアプリを更新|GitHub"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  
