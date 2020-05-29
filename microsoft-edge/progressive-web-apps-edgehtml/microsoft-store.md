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
# <span data-ttu-id="5c28a-104">Microsoft Store のプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="5c28a-104">Progressive Web Apps in the Microsoft Store</span></span>

<span data-ttu-id="5c28a-105">プログレッシブ Web アプリ (PWA) を[Microsoft ストア](https://developer.microsoft.com/store)に公開すると、アプリの対象ユーザーは、約7億のアクティブな月次ユーザーの Windows 10 インストールベース全体に拡張します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-105">When you publish your Progressive Web App (PWA) to the [Microsoft Store](https://developer.microsoft.com/store), your potential app audience expands to the entire Windows 10 install base of nearly 700 million active monthly users!</span></span> 

<span data-ttu-id="5c28a-106">Microsoft Store では、次のようなさまざまなメリットを享受できます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-106">PWAs in the Microsoft Store enjoy a number of advantages:</span></span>

- <span data-ttu-id="5c28a-107">検索のし**やすさ**-Microsoft Store のアプリは、さまざまなカテゴリ、curated コレクション、検索フィルターによって紹介されており、アプリの潜在的な顧客にとって簡単な閲覧とショッピングエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-107">**Discoverability** - Apps in the Microsoft Store are showcased through different categories, curated collections, and search filters, providing an easy browsing and shopping experience for potential customers of your app.</span></span> <span data-ttu-id="5c28a-108">スクリーンショット、ヒーローの画像、ビデオの予告編を使って、[ストア登録](/windows/uwp/publish/app-screenshots-and-images)情報を拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-108">You can even [enhance your Store listing](/windows/uwp/publish/app-screenshots-and-images) with screenshots, a hero image, and video trailers!</span></span>

- <span data-ttu-id="5c28a-109">**信頼性**-Windows のお客様は、microsoft の厳密な[品質と安全性の標準](/legal/windows/agreements/store-policies)に準拠しているため、microsoft ストアの購入とダウンロードを信頼できることをご存じです。</span><span class="sxs-lookup"><span data-stu-id="5c28a-109">**Trustworthiness** - Windows customers know they can trust their Microsoft Store purchases and downloads because they adhere to Microsoft's rigorous [quality and safety standards](/legal/windows/agreements/store-policies).</span></span>

- <span data-ttu-id="5c28a-110">**簡単なインストール**-Microsoft Store は、[すべての Windows 10 アプリ](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)で一貫したユーザーフレンドリなインストールエクスペリエンスを提供します。これにより、すべてのユーザーが、技術的な安心レベルにかかわらず、PWA を簡単にインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-110">**Easy install** - The Microsoft Store provides a consistent and user friendly install experience across [all Windows 10 apps](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), making it easy for all customers to install your PWA, regardless of technical comfort level.</span></span>

- <span data-ttu-id="5c28a-111">**Business insights** -Microsoft Store 用[windows デベロッパーセンターダッシュボード](/windows/uwp/publish/using-the-windows-dev-center-dashboard)では、PWA が使用している windows ユーザーの数や、ユーザーがどのように話しているかについて、[詳細な分析](/windows/uwp/publish/analytics)を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-111">**Business insights** - The [Windows Dev Center dashboard](/windows/uwp/publish/using-the-windows-dev-center-dashboard) for the Microsoft Store provides you with [detailed analytics](/windows/uwp/publish/analytics) about everything from how many Windows customers your PWA has reached to how they're using it and what they have to say.</span></span> <span data-ttu-id="5c28a-112">アプリの正常性、広告の使用状況などに関するメトリックとテレメトリデータも見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-112">You can also find metrics and telemetry data on app health, ad usage, and more.</span></span>

<span data-ttu-id="5c28a-113">Microsoft ストアに PWA をダウンロードするには、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-113">There are two options for getting your PWA into the Microsoft Store:</span></span>

1. <span data-ttu-id="5c28a-114">[手動で送信](#submitting-your-pwa-manually)することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-114">You can [manually submit it](#submitting-your-pwa-manually), or</span></span>

2. <span data-ttu-id="5c28a-115">PWA が特定の[条件](#criteria-for-automatic-submission)を満たしている場合は、Bing web クローラーによって[インデックスが自動的に](#automatic-pwa-importing-with-bing)作成されます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-115">If your PWA meets [certain criteria](#criteria-for-automatic-submission), it can be [automatically indexed](#automatic-pwa-importing-with-bing) by the Bing web crawler.</span></span> <span data-ttu-id="5c28a-116">(自動申請の解除を[選択](#opting-out-of-automatic-microsoft-store-import)することもできます)。</span><span class="sxs-lookup"><span data-stu-id="5c28a-116">(You also have the option to [opt-out](#opting-out-of-automatic-microsoft-store-import) of auto-submission.)</span></span>

<span data-ttu-id="5c28a-117">申請方法に関係なく、PWA が Microsoft Store に承認されると、上記のすべての特典にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-117">Regardless of submission method, once your PWA is accepted to the Microsoft Store you'll gain access to all the benefits outlined above.</span></span>

## <span data-ttu-id="5c28a-118">手動で PWA を送信する</span><span class="sxs-lookup"><span data-stu-id="5c28a-118">Submitting your PWA manually</span></span>

<span data-ttu-id="5c28a-119">Microsoft ストアでアプリを配布および昇格するには、そのアプリを Windows アプリパッケージ (*.appx*ファイル) として提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-119">In order to distribute and promote an app through the Microsoft Store, you'll need to submit it as a Windows app package (*.appx* file).</span></span>  <span data-ttu-id="5c28a-120">PWAs などのサーバーでホストされる web アプリの場合、このパッケージには、アプリのメタデータとホーム画面のアイコン (および実際のアプリケーションコードは含まれません) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-120">For server-hosted web apps such as PWAs, this package simply contains app metadata and home screen icons (and none of the actual application code).</span></span> <span data-ttu-id="5c28a-121">これにより、web アプリをホーム画面から他の[Windows 10 アプリ](/windows/uwp/get-started/whats-a-uwp)と共にインストールして起動することができます。これには、Microsoft Edge ブラウザーウィンドウとは別に、軽量のネイティブアプリラッパー (*wwahost*プロセス) で実行します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-121">With this, your web app can be installed and launched from the home screen alongside other [Windows 10 apps](/windows/uwp/get-started/whats-a-uwp) by running in a lightweight native app wrapper (*WWAHost.exe* process), independent from the Microsoft Edge browser window.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5c28a-122">EdgeHTML web platform engine は、Microsoft Edge (Chromium) ベースの PWA との互換性の違いをもたらす、WWAHost アプリラッパーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-122">The EdgeHTML web platform engine is used by the WWAHost app wrapper which could introduce compatibility differences for your Microsoft Edge (Chromium) based PWA.</span></span>  <span data-ttu-id="5c28a-123">EdgeHTML エンジンが新しい web 標準によって更新されなくなったため、microsoft Edge (EdgeHTML) を使ってアプリケーションの完全なテストパスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="5c28a-123">Be sure to do a full test pass on your application using Microsoft Edge (EdgeHTML) before submitting your app to the Microsoft store as the EdgeHTML engine is no longer being updated with newer web standards.</span></span>  

<span data-ttu-id="5c28a-124">その方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5c28a-124">Here's how to do it.</span></span>

### <span data-ttu-id="5c28a-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="5c28a-125">Prerequisites</span></span>

- <span data-ttu-id="5c28a-126">**既存の PWA**。</span><span class="sxs-lookup"><span data-stu-id="5c28a-126">**An existing PWA**.</span></span> <span data-ttu-id="5c28a-127">Web アプリがまだ存在しない場合は、次のようにして[PWA に変換](./get-started.md)する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-127">Here's how to [convert your web app to a PWA](./get-started.md) if it isn't one already.</span></span> 
- <span data-ttu-id="5c28a-128">**PWAs 用の WINDOWS APPX パッケージツールがありました**。</span><span class="sxs-lookup"><span data-stu-id="5c28a-128">**A Windows APPX packaging tool for PWAs**.</span></span> <span data-ttu-id="5c28a-129">Visual Studio を使って[Windows で PWA をビルドして実行](./windows-features.md)する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-129">Here's how to [build and run your PWA on Windows](./windows-features.md) using Visual Studio.</span></span> <span data-ttu-id="5c28a-130">また、 [PWA ビルダー](https://www.pwabuilder.com/)を使用して、Windows パッケージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-130">You can also use [PWA Builder](https://www.pwabuilder.com/) to build a Windows package.</span></span>
- <span data-ttu-id="5c28a-131">[**Microsoft ストアアプリの開発者アカウント**](/windows/uwp/publish/opening-a-developer-account)。</span><span class="sxs-lookup"><span data-stu-id="5c28a-131">[**Microsoft Store app developer account**](/windows/uwp/publish/opening-a-developer-account).</span></span> <span data-ttu-id="5c28a-132">選択したアカウントの種類と場所によっては[1 回限りの料金](/windows/uwp/publish/account-types-locations-and-fees)が発生し、登録には有効な[Microsoft アカウント](https://account.microsoft.com/)が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c28a-132">There is a [one-time fee](/windows/uwp/publish/account-types-locations-and-fees) depending on your chosen account type and location, and registration requires a valid [Microsoft Account](https://account.microsoft.com/).</span></span>


### <span data-ttu-id="5c28a-133">*Visual Studio*によるストアの申請</span><span class="sxs-lookup"><span data-stu-id="5c28a-133">Store submission through *Visual Studio*</span></span> 

<span data-ttu-id="5c28a-134">Visual Studio で PWA の[アプリパッケージアップロードファイルを作成](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file)するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-134">Follow these steps to [create an app package upload file](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) for your PWA in Visual Studio.</span></span> <span data-ttu-id="5c28a-135">このプロセスの一般的な概要については、「 [*UWP アプリで Visual Studio をパッケージ化*](/windows/uwp/packaging/packaging-uwp-apps)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c28a-135">See [*Package a UWP app with Visual Studio*](/windows/uwp/packaging/packaging-uwp-apps) for a more general overview of this process.</span></span>

<span data-ttu-id="5c28a-136">この手順では、 [**Windows アプリ認定キット**](https://developer.microsoft.com/windows/develop/app-certification-kit)を実行して、Microsoft ストアの要件に準拠したアプリをテストする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-136">The instructions will also guide you through running the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit) to test your app for compliance with Microsoft Store requirements.</span></span> <span data-ttu-id="5c28a-137">これはオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c28a-137">This is optional, but highly recommended.</span></span>

### <span data-ttu-id="5c28a-138">*Windows デベロッパーセンター*を使用したストアへの申請</span><span class="sxs-lookup"><span data-stu-id="5c28a-138">Store submission through *Windows Dev Center*</span></span>

<span data-ttu-id="5c28a-139">ここでは、 *PWA ビルダー*を使用して、Windows デベロッパーセンターにアップロードするためのアプリパッケージを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-139">Here's how to use *PWA Builder* to generate an app package for upload to the Windows Dev Center.</span></span>

1. <span data-ttu-id="5c28a-140">Windows 10 アプリを生成します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-140">Generate your Windows 10 app.</span></span> <span data-ttu-id="5c28a-141">[Visual Studio で Windows アプリとして PWA](./windows-features.md)を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-141">Here's how to run your [PWA as a Windows app with Visual Studio](./windows-features.md).</span></span> <span data-ttu-id="5c28a-142">また、 [PWA ビルダー](https://www.pwabuilder.com/)を使用して、Windows 10 アプリを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-142">You can also use [PWA Builder](https://www.pwabuilder.com/) to generate your Windows 10 app.</span></span>

2. <span data-ttu-id="5c28a-143">Microsoft ストアのアプリ名を予約するには、アカウント情報を使用して[Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にログインし、[名前を予約してアプリを作成](/windows/uwp/publish/create-your-app-by-reserving-a-name)する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5c28a-143">Reserve your app name for the Microsoft Store by logging into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) with your account info and following the steps to [create your app by reserving a name](/windows/uwp/publish/create-your-app-by-reserving-a-name).</span></span> <span data-ttu-id="5c28a-144">予約する名前は、Microsoft Store 全体で一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-144">Each reserved name must be unique throughout the Microsoft Store.</span></span>

3. <span data-ttu-id="5c28a-145">アプリのパッケージをアップロードするときに、 *package.appxmanifest*ファイルの*DisplayName*、 *Name*、 *Publisher*、および*PublisherDisplayName*の値は、名前を予約するときに、Windows デベロッパーセンターダッシュボードのアプリに割り当てられている値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-145">When you upload your app's packages, the *DisplayName*, *Name*, *Publisher*, and *PublisherDisplayName* values in your *.appxmanifest* file must match the values assigned to your app in the Windows Dev Center dashboard upon reserving its name.</span></span> 

    <span data-ttu-id="5c28a-146">[Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にログインし、[**アプリ管理**] の下の [アプリ id] の値を探し  >  **App identity**ます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-146">Log into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview), and locate your app identity values under **App management** > **App identity**:</span></span>

    ![Windows デベロッパーセンターダッシュボードのアプリ id の設定](./media/dashboard-app-identity.png)

    <span data-ttu-id="5c28a-148">次に、ファイルを見つけ `appxmanifest.xml` て、次の値を Windows デベロッパーセンターダッシュボードに割り当てられているものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-148">Then, locate your `appxmanifest.xml` file and replace the following values with the ones assigned in the Windows Dev Center dashboard:</span></span>

    - <span data-ttu-id="5c28a-149">**<Identity Name = "** *Package/identity/Name* "</span><span class="sxs-lookup"><span data-stu-id="5c28a-149">**<Identity Name="** *Package/Identity/Name*</span></span>
    - <span data-ttu-id="5c28a-150">**<Identity Publisher = "** *Package/identity/Publisher*</span><span class="sxs-lookup"><span data-stu-id="5c28a-150">**<Identity Publisher="** *Package/Identity/Publisher*</span></span>
    - <span data-ttu-id="5c28a-151">**DisplayName<** \**>\*\*\*アプリ用に予約した名前*</span><span class="sxs-lookup"><span data-stu-id="5c28a-151">**<DisplayName** **>** *Name you reserved for your app*</span></span> 
    - <span data-ttu-id="5c28a-152">**<PublisherDisplayName** **>***Package/Properties/PublisherDisplayName***</PublisherDisplayName>**</span><span class="sxs-lookup"><span data-stu-id="5c28a-152">**<PublisherDisplayName** **>** *Package/Properties/PublisherDisplayName* **</PublisherDisplayName>**</span></span>

4. <span data-ttu-id="5c28a-153">これで、すべての PWA リソースを1つのファイルにコンパイルして、 `.appx` Microsoft Store にアップロードする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5c28a-153">Now you're ready to compile all your PWA resources into a single `.appx` file you can upload to the Microsoft Store.</span></span> <span data-ttu-id="5c28a-154">コマンドプロンプトで、web マニフェストのディレクトリに移動し、Windows 10 パッケージを作成します ([オプションのデバッグログ] の下で指定します)。</span><span class="sxs-lookup"><span data-stu-id="5c28a-154">From a command prompt, navigate to the directory of your web manifest and create a Windows 10 package (specified below w/ optional debug logging):</span></span>

    ```
    pwabuilder package -p windows10 -l debug
    ```

    <span data-ttu-id="5c28a-155">この場所に .appx ファイルが生成さ `PWA\Store packages\windows10\package\windows.appx` れます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-155">Your .appx file will be generated to this location: `PWA\Store packages\windows10\package\windows.appx`.</span></span>

5. <span data-ttu-id="5c28a-156">アプリを Microsoft Store にアップロードする前に、Microsoft ストアのポリシーに準拠するようにアプリをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c28a-156">Before you upload your app for submisison to the Microsoft Store, its a good idea to test your app for compliance with Microsoft Store policies.</span></span> <span data-ttu-id="5c28a-157">これを行うには、 [**Windows アプリ認定キット**](https://developer.microsoft.com/windows/develop/app-certification-kit)をダウンロードして起動し、アプリの *.appx*ファイルをテスト用に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-157">You can do this by downloading the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit), launching it, and then selecting your app's *.appx* file for testing.</span></span> <span data-ttu-id="5c28a-158">すべてのテストが完了すると、対応する領域のレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-158">You will receive a report of areas to address once all the tests are complete.</span></span>

6. <span data-ttu-id="5c28a-159">パッケージをアップロードし、 [Windows デベロッパーセンターダッシュボード](https://developer.microsoft.com/dashboard/windows/overview)にもう一度ログインして申請を完了し、**申請**のサブページを展開し  >  **Submisison 1**ます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-159">Upload your package and complete the submission by logging back into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) and expanding the **Submissions** > **Submisison 1** panel.</span></span> <span data-ttu-id="5c28a-160">チェックリストに従って、[必要なストア登録情報](/windows/uwp/publish/app-submissions)を入力し、[アプリパッケージをアップロード](/windows/uwp/publish/upload-app-packages)します。</span><span class="sxs-lookup"><span data-stu-id="5c28a-160">Follow the checklist to complete the [required store listing information](/windows/uwp/publish/app-submissions) and [upload your app package](/windows/uwp/publish/upload-app-packages).</span></span>

<span data-ttu-id="5c28a-161">Microsoft Store アプリ開発者が利用できるすべての機能とサービスの詳細については、「 [Windows デベロッパーセンター](https://developer.microsoft.com/windows)で[*Windows アプリを公開*](https://developer.microsoft.com/store/publish-apps)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c28a-161">For more on the all the features and services available to Microsoft Store app developers, see [*Publish Windows apps*](https://developer.microsoft.com/store/publish-apps) on the [Windows Dev Center](https://developer.microsoft.com/windows).</span></span>

## <span data-ttu-id="5c28a-162">Bing での自動 PWA インポート</span><span class="sxs-lookup"><span data-stu-id="5c28a-162">Automatic PWA importing with Bing</span></span>

<span data-ttu-id="5c28a-163">PWA の[web アプリマニフェスト](https://developer.mozilla.org/docs/Web/Manifest)は、アプリがオフラインに対応しており、完全に統合されたアプリエクスペリエンスとして提供する準備ができているプラットフォームをサポートするためのシグナルであるのと同じように、Microsoft Store で自動的に追加することを pwa に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c28a-163">Just as your PWA's [web app manifest](https://developer.mozilla.org/docs/Web/Manifest) is a signal to supporting platforms that your app is offline-capable and ready to be presented as a fully integrated app experience, it's also a hint to the Bing web crawler that your PWA should be considered for automatic inclusion in the Microsoft Store.</span></span> 

<span data-ttu-id="5c28a-164">PWA が以下の要件を満たしている場合、Bing インデックスサービスは、Windows 10 でのインストールに必要な[*.appx*](#submitting-your-pwa-manually)形式で pwa を自動的にパッケージ化し、web アプリマニフェストのメタデータに基づいてアプリのストア製品ページをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="5c28a-164">If your PWA meets the requirements below, the Bing indexing service will automatically package your PWA in the [*.appx*](#submitting-your-pwa-manually) format required for installation on Windows 10 and assemble your app's store product page based on the metadata in its web app manifest.</span></span> <span data-ttu-id="5c28a-165">PWA を申請した後は、Windows デベロッパーセンターダッシュボードを使って、ストアページをさらにカスタマイズして、ユーザー分析やその他のアプリ管理ツールにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-165">After claiming your PWA, you'll be able to further customize your store page and gain access to user analytics and other app management tools through the Windows Dev Center dashboard.</span></span>

### <span data-ttu-id="5c28a-166">自動提出の条件</span><span class="sxs-lookup"><span data-stu-id="5c28a-166">Criteria for automatic submission</span></span>

<span data-ttu-id="5c28a-167">自動的に Microsoft ストア用にパッケージ化されて一覧表示されるようにするには、PWA に次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c28a-167">To be automatically packaged and listed for the Microsoft Store, your PWA will need:</span></span>

- <span data-ttu-id="5c28a-168">[X] 少なくとも次のような、空でない web アプリマニフェストファイル。</span><span class="sxs-lookup"><span data-stu-id="5c28a-168">[X] A non-empty web app manifest file, with at minimum:</span></span>

  - <span data-ttu-id="5c28a-169">名前</span><span class="sxs-lookup"><span data-stu-id="5c28a-169">Name</span></span>
  - <span data-ttu-id="5c28a-170">説明</span><span class="sxs-lookup"><span data-stu-id="5c28a-170">Description</span></span>
  - <span data-ttu-id="5c28a-171">512 x 512 ピクセル以上のアプリアイコン</span><span class="sxs-lookup"><span data-stu-id="5c28a-171">App icon that is at least 512 x 512 pixels</span></span>

- <span data-ttu-id="5c28a-172">[X] 固有のコアロジック ([アプリの定型](https://en.wikipedia.org/wiki/Boilerplate_code)入力テンプレートから変更されたコードを最小限にしたものではありません)</span><span class="sxs-lookup"><span data-stu-id="5c28a-172">[X] Unique core logic (not minimally modified code from an [app boilerplate](https://en.wikipedia.org/wiki/Boilerplate_code) template)</span></span>

- <span data-ttu-id="5c28a-173">[X] セキュリティで保護された接続 (HTTPS) を介して提供される</span><span class="sxs-lookup"><span data-stu-id="5c28a-173">[X] To be served over a secure connection (HTTPS)</span></span>

- <span data-ttu-id="5c28a-174">[X] サービスワーカースクリプト</span><span class="sxs-lookup"><span data-stu-id="5c28a-174">[X] Service worker script(s)</span></span>

- <span data-ttu-id="5c28a-175">[X] 法律または[Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)に違反しないようにします。</span><span class="sxs-lookup"><span data-stu-id="5c28a-175">[X] To not violate any laws or [Microsoft Store policies](/legal/windows/agreements/store-policies).</span></span>

<span data-ttu-id="5c28a-176">Microsoft は、これらの条件を満たしているアプリをすべて取り込んではありませんが、プログラムを段階的に展開することで、候補についての考慮事項として含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c28a-176">We won't ingest every app that meets these criteria, but will be including them in our considerations for candidates as we gradually expand our program.</span></span>

### <span data-ttu-id="5c28a-177">Microsoft Store の自動インポートの無効化</span><span class="sxs-lookup"><span data-stu-id="5c28a-177">Opting out of automatic Microsoft Store import</span></span>

<span data-ttu-id="5c28a-178">PWA は、次のファイルを提供することにより、Microsoft ストアへの自動インポートを無効にすることができ `robots.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-178">Your PWA can opt out of automatic import to the Microsoft Store by serving a `robots.txt` file containing the following:</span></span>

```
User-agent: bingbot
Disallow: /manifest.json
```

<span data-ttu-id="5c28a-179">これにより、Bing web クローラー (Bingbot) に、PWA インデックス作成のための web マニフェストファイルを無視するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="5c28a-179">This directs the Bing web crawler (Bingbot) to disregard your web manifest file for PWA indexing purposes.</span></span> <span data-ttu-id="5c28a-180">Bing の通常の[web インデックス処理](https://www.bing.com/webmaster/help/help-center-661b2d18)では、サイトの検索のランク付けには影響しません。</span><span class="sxs-lookup"><span data-stu-id="5c28a-180">This will not affect your site's search ranking in Bing's regular [web indexing process](https://www.bing.com/webmaster/help/help-center-661b2d18).</span></span>
