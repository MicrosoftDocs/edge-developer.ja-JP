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
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a><span data-ttu-id="389e5-104">プログレッシブ Web アプリを Microsoft Store に発行する</span><span class="sxs-lookup"><span data-stu-id="389e5-104">Publish your Progressive Web App to the Microsoft Store</span></span>  

<span data-ttu-id="389e5-105">プログレッシブ Web アプリ \(PWA\) を [Microsoft Store][WindowsUwpPublishIndex] に発行すると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="389e5-105">Publishing your Progressive Web App \(PWA\) to the [Microsoft Store][WindowsUwpPublishIndex] brings the following advantages.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="389e5-106">見つけやすさ</span><span class="sxs-lookup"><span data-stu-id="389e5-106">Discoverability</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="389e5-107">ユーザーは当然、アプリ ストアでアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="389e5-107">Users naturally look for apps in the app store.</span></span>  <span data-ttu-id="389e5-108">Microsoft Store に発行すると、何百万人もの Windows ユーザーが他の Windows アプリと共に PWA を検出する場合があります。</span><span class="sxs-lookup"><span data-stu-id="389e5-108">When you publish to the Microsoft Store, millions of Windows users may discover your PWA alongside other Windows apps.</span></span>  <span data-ttu-id="389e5-109">ストアでは、カテゴリ、キュアされたコレクションなど、アプリを紹介します。</span><span class="sxs-lookup"><span data-stu-id="389e5-109">The Store showcases apps through categories, curated collections, and more.</span></span>  <span data-ttu-id="389e5-110">アプリ検出ポータルは、アプリの潜在的なユーザーに対して簡単な閲覧とショッピング エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="389e5-110">The app discovery portals provide an easy browsing and shopping experience for potential users of your app.</span></span>  <span data-ttu-id="389e5-111">スクリーンショット、 [ヒーロー画像、][WindowsUwpPublishAppScreenshotsImages] ビデオトレーラーを使用してストアの登録情報を強化することもできます。</span><span class="sxs-lookup"><span data-stu-id="389e5-111">You may even [enhance your Store listing][WindowsUwpPublishAppScreenshotsImages] with screenshots, a hero image, and video trailers.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="389e5-112">信頼度</span><span class="sxs-lookup"><span data-stu-id="389e5-112">Trustworthiness</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="389e5-113">Windows のお客様は、Microsoft Store の厳しい品質と安全基準に従うので、Microsoft Store の購入とダウンロードを信頼できる可能性[があります。][LegalWindowsAgreementsStorePolicies]</span><span class="sxs-lookup"><span data-stu-id="389e5-113">Windows customers know they may trust their Microsoft Store purchases and downloads, because they adhere to the rigorous Microsoft [quality and safety standards][LegalWindowsAgreementsStorePolicies].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="389e5-114">簡単なインストール</span><span class="sxs-lookup"><span data-stu-id="389e5-114">Easy install</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="389e5-115">Microsoft Store は、すべての Windows 10 アプリで一貫性のあるユーザーフレンドリー [なインストール エクスペリエンスを提供します][MicrosoftStoreAppsWindows]。</span><span class="sxs-lookup"><span data-stu-id="389e5-115">The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="389e5-116">アプリ分析</span><span class="sxs-lookup"><span data-stu-id="389e5-116">App analytics</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="389e5-117">[Windows パートナー センター ダッシュボードには][WindowsUwpPublishIndex]、アプリの正常性、使用状況などについての詳細な分析が提供されます。 [][WindowsUwpPublishAnalytics]</span><span class="sxs-lookup"><span data-stu-id="389e5-117">The [Windows Partner Center dashboard][WindowsUwpPublishIndex] provides you with [detailed analytics][WindowsUwpPublishAnalytics] about your app health, usage, and more.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="389e5-118">PWA を Microsoft Store に発行するには、コードの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="389e5-118">To publish your PWA to the Microsoft Store, no code changes are required.</span></span>  <span data-ttu-id="389e5-119">代わりに、アプリの予約を作成し、PWA をパッケージ化し、パッケージをストアに提出します。</span><span class="sxs-lookup"><span data-stu-id="389e5-119">Instead, you create an app reservation, package your PWA, and submit your package to the Store.</span></span>  <span data-ttu-id="389e5-120">以下のセクションでは、手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="389e5-120">The following sections explain the steps.</span></span>   

## <a name="create-an-app-reservation"></a><span data-ttu-id="389e5-121">アプリの予約を作成する</span><span class="sxs-lookup"><span data-stu-id="389e5-121">Create an app reservation</span></span>  

<span data-ttu-id="389e5-122">[Windows パートナー センター][MicrosoftPartnerDashboardWindowsOverview] は、アプリを Microsoft Store に提出するハブです。</span><span class="sxs-lookup"><span data-stu-id="389e5-122">[Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview] is the hub for you to submit your app to the Microsoft Store.</span></span>  

<span data-ttu-id="389e5-123">アプリの予約を作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-123">To create an app reservation, complete the following actions.</span></span>  

1.  <span data-ttu-id="389e5-124">登録済みプログラムを表示するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-124">To display your enrolled programs, complete the following actions.</span></span>  
    1.  <span data-ttu-id="389e5-125">Microsoft アカウントで Windows パートナー センターにサインインし、パートナー センター [ダッシュボードに移動します][MicrosoftPartnerDashboardHome]。</span><span class="sxs-lookup"><span data-stu-id="389e5-125">Sign into Windows Partner Center with your Microsoft account and navigate to the [Partner Center Dashboard][MicrosoftPartnerDashboardHome].</span></span>  
    1.  <span data-ttu-id="389e5-126">Xbox の **Windows &移動する**</span><span class="sxs-lookup"><span data-stu-id="389e5-126">Navigate to **Windows & Xbox**</span></span>  
        *   <span data-ttu-id="389e5-127">**Xbox に Windows &が**表示されている場合、アプリは既に登録されています。</span><span class="sxs-lookup"><span data-stu-id="389e5-127">If **Windows & Xbox** is displayed, your app is already enrolled.</span></span>  
        *   <span data-ttu-id="389e5-128">**Windows の Xbox &が**表示されない場合は、[プログラムの追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-128">If **Windows & Xbox** isn't displayed, choose **Add program**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="Windows パートナー センター ダッシュボードにプログラムを追加する" lightbox="./media/windows-partner-center-add-program.msft.png":::
       <span data-ttu-id="389e5-130">Windows パートナー センター ダッシュボードにプログラムを追加する</span><span class="sxs-lookup"><span data-stu-id="389e5-130">Add a program in the Windows Partner Center dashboard</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="389e5-131">開発者プログラムに登録するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-131">To enroll in the developer program, complete the following actions.</span></span>  
    1.  <span data-ttu-id="389e5-132">Xbox の **Windows &移動します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-132">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="389e5-133">[スタート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-133">Choose **Get started**.</span></span>  
    1.  <span data-ttu-id="389e5-134">画面に表示される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="389e5-134">Follow the prompts.</span></span>  
1.  <span data-ttu-id="389e5-135">これで、アカウントがアプリ開発者プログラムに登録されます。</span><span class="sxs-lookup"><span data-stu-id="389e5-135">Now, your account is enrolled in the app developer program.</span></span> <span data-ttu-id="389e5-136">アプリの予約を作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-136">To create an app reservation, complete the following actions.</span></span>  
    1.  <span data-ttu-id="389e5-137">Xbox の **Windows &移動します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-137">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="389e5-138">[概要 **]**  >  **[新しいアプリの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-138">Choose **Overview** > **Create a new app**.</span></span>  
    1.  <span data-ttu-id="389e5-139">プロンプトにアプリの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="389e5-139">Type the name of your app in the prompt.</span></span>  
    1.  <span data-ttu-id="389e5-140">を選択します `Reserve product name` 。</span><span class="sxs-lookup"><span data-stu-id="389e5-140">Choose `Reserve product name`.</span></span>  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="Windows パートナー センターでアプリの予約を作成する" lightbox="./media/windows-partner-center-create-app.msft.png":::
       <span data-ttu-id="389e5-142">Windows パートナー センターでアプリの予約を作成する</span><span class="sxs-lookup"><span data-stu-id="389e5-142">Create an app reservation in Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="389e5-143">[[PWA](#package-your-pwa-for-the-store)のパッケージ化] セクションで使用する発行元の詳細を表示するには、[製品管理**製品 ID]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-143">To display your publisher details for use in the [Package your PWA](#package-your-pwa-for-the-store) section, choose **Product management** > **Product Identity**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="発行元情報を Windows パートナー センターからコピーする" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       <span data-ttu-id="389e5-145">発行元情報を Windows パートナー センターからコピーする</span><span class="sxs-lookup"><span data-stu-id="389e5-145">Copy your publisher information from Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="389e5-146">次の値をコピーして保存します。</span><span class="sxs-lookup"><span data-stu-id="389e5-146">Copy and save the following values.</span></span>  
    *   **<span data-ttu-id="389e5-147">パッケージ ID</span><span class="sxs-lookup"><span data-stu-id="389e5-147">Package ID</span></span>**  
    *   **<span data-ttu-id="389e5-148">Publisher ID</span><span class="sxs-lookup"><span data-stu-id="389e5-148">Publisher ID</span></span>**  
    *   **<span data-ttu-id="389e5-149">Publisher の表示名</span><span class="sxs-lookup"><span data-stu-id="389e5-149">Publisher Display Name</span></span>**  
        
## <a name="package-your-pwa-for-the-store"></a><span data-ttu-id="389e5-150">PWA をストア用にパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="389e5-150">Package your PWA for the Store</span></span> 

<span data-ttu-id="389e5-151">アプリの発行情報が得たので、PWA 用の Windows アプリ パッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="389e5-151">Now that you have your app publishing information, generate a Windows app package for your PWA.</span></span>

<span data-ttu-id="389e5-152">アプリ パッケージを生成するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-152">To generate an app package, complete the following actions.</span></span>  

1.  <span data-ttu-id="389e5-153">[PWA ビルダーに移動します][PwabuilderMain]。</span><span class="sxs-lookup"><span data-stu-id="389e5-153">Navigate to [PWA Builder][PwabuilderMain].</span></span>  
1.  <span data-ttu-id="389e5-154">PWA の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="389e5-154">Type the URL of your PWA.</span></span>  
1.  <span data-ttu-id="389e5-155">[ビルド**の**  >  **開始] [PWA**  >  **Windows オプション]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-155">Choose **Start** > **Build My PWA** > **Windows** > **Options**.</span></span>  
1.  <span data-ttu-id="389e5-156">[アプリの予約の作成] セクションに保存した次 [の値を貼り付](#create-an-app-reservation) けます。</span><span class="sxs-lookup"><span data-stu-id="389e5-156">Paste the following values that you saved in the [Create an app reservation](#create-an-app-reservation) section.</span></span>  
    *   **<span data-ttu-id="389e5-157">パッケージ ID</span><span class="sxs-lookup"><span data-stu-id="389e5-157">Package ID</span></span>**  
    *   **<span data-ttu-id="389e5-158">Publisher ID</span><span class="sxs-lookup"><span data-stu-id="389e5-158">Publisher ID</span></span>**  
    *   **<span data-ttu-id="389e5-159">Publisher の表示名</span><span class="sxs-lookup"><span data-stu-id="389e5-159">Publisher Display Name</span></span>**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="PWABuilder に発行元情報を貼り付ける" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       <span data-ttu-id="389e5-161">PWABuilder に発行元情報を貼り付ける</span><span class="sxs-lookup"><span data-stu-id="389e5-161">Paste publisher information into PWABuilder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="389e5-162">[完了 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-162">Choose **Done**.</span></span>  
1.  <span data-ttu-id="389e5-163">Windows アプリ パッケージをダウンロードするには、[ダウンロード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-163">To download your Windows app package, choose **Download**.</span></span>

<span data-ttu-id="389e5-164">ダウンロードは、ファイル `.zip` とファイルを含 `.msixbundle` むアーカイブ `.classic.appxbundle` です。</span><span class="sxs-lookup"><span data-stu-id="389e5-164">Your download is a `.zip` archive that contains an `.msixbundle` file and a `.classic.appxbundle` file.</span></span>  <span data-ttu-id="389e5-165">2 つのアプリ パッケージを使用すると、PWA をさまざまな Windows バージョンで実行できます。</span><span class="sxs-lookup"><span data-stu-id="389e5-165">The two app packages allow your PWA to run on a wide variety of Windows versions.</span></span>  <span data-ttu-id="389e5-166">詳細については、「クラシック パッケージ [とは」に移動します][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]。</span><span class="sxs-lookup"><span data-stu-id="389e5-166">For more information, navigate to [What is a classic package?][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd].</span></span>  

### <a name="submit-your-app-package-to-the-store"></a><span data-ttu-id="389e5-167">アプリ パッケージをストアに提出する</span><span class="sxs-lookup"><span data-stu-id="389e5-167">Submit your app package to the Store</span></span>  

<span data-ttu-id="389e5-168">アプリをストアに送信するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="389e5-168">To submit your app to the Store, complete the following actions.</span></span>  

1.  <span data-ttu-id="389e5-169">Windows パートナー [センターに移動する][MicrosoftPartnerDashboardWindowsOverview]</span><span class="sxs-lookup"><span data-stu-id="389e5-169">Navigate to [Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview]</span></span> 
1.  <span data-ttu-id="389e5-170">アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="389e5-170">Choose your app.</span></span>  
1.  <span data-ttu-id="389e5-171">[申請 **の開始] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="389e5-171">Choose **Start your Submission**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="Windows パートナー センターで新しいアプリの申請を開始する" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       <span data-ttu-id="389e5-173">Windows パートナー センターで新しいアプリの申請を開始する</span><span class="sxs-lookup"><span data-stu-id="389e5-173">Start a new app submission on Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="389e5-174">アプリに関する情報を求めるプロンプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="389e5-174">Complete the following prompts for information about your app.</span></span>
    *   <span data-ttu-id="389e5-175">pricing</span><span class="sxs-lookup"><span data-stu-id="389e5-175">pricing</span></span>  
    *   <span data-ttu-id="389e5-176">年齢の評価</span><span class="sxs-lookup"><span data-stu-id="389e5-176">age rating</span></span>  
    *   <span data-ttu-id="389e5-177">およびその他</span><span class="sxs-lookup"><span data-stu-id="389e5-177">and more</span></span>  
        
1.  <span data-ttu-id="389e5-178">[パッケージ **] プロンプト** で、[PWA のパッケージ化] セクションで生成した `.msixbundle` `.classic.appxbundle` ファイル [とファイルを選択](#package-your-pwa-for-the-store) します。</span><span class="sxs-lookup"><span data-stu-id="389e5-178">On the **Packages** prompt, choose the `.msixbundle` and the `.classic.appxbundle` files you generated in the [Package your PWA](#package-your-pwa-for-the-store) section.</span></span>  
    
<span data-ttu-id="389e5-179">申請が完了すると、アプリは通常 24 ~ 48 時間以内に確認されます。</span><span class="sxs-lookup"><span data-stu-id="389e5-179">After you complete your submission, your app is reviewed, typically within between 24 and 48 hours.</span></span>  <span data-ttu-id="389e5-180">承認を受け取った後、PWA は Microsoft Store で利用できます。</span><span class="sxs-lookup"><span data-stu-id="389e5-180">After you receive approval, your PWA is available in the Microsoft Store.</span></span>  

## <a name="see-also"></a><span data-ttu-id="389e5-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="389e5-181">See also</span></span>  

<span data-ttu-id="389e5-182">PWABuilder には、Microsoft Store で PWA を取得するのに役立つその他のドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="389e5-182">PWABuilder provides more documentation to help you get your PWA in the Microsoft Store.</span></span>  

*   [<span data-ttu-id="389e5-183">PWA アプリ パッケージをテストして提出する</span><span class="sxs-lookup"><span data-stu-id="389e5-183">Test and submit your PWA app package</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [<span data-ttu-id="389e5-184">新しい PWA をストアに発行する</span><span class="sxs-lookup"><span data-stu-id="389e5-184">Publish a new PWA to the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [<span data-ttu-id="389e5-185">既存のストア アプリを PWA に更新する</span><span class="sxs-lookup"><span data-stu-id="389e5-185">Update an existing Store app to a PWA</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [<span data-ttu-id="389e5-186">ストア内の PWA のイメージの推奨事項</span><span class="sxs-lookup"><span data-stu-id="389e5-186">Image recommendations for PWAs in the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [<span data-ttu-id="389e5-187">アプリパッケージの説明者</span><span class="sxs-lookup"><span data-stu-id="389e5-187">App packaging explainer</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

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
