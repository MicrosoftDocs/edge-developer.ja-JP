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
# <span data-ttu-id="d8b80-104">内線番号を発行する</span><span class="sxs-lookup"><span data-stu-id="d8b80-104">Publish An Extension</span></span>  

<span data-ttu-id="d8b80-105">Microsoft Edge のアドオンカタログ (Microsoft Edge アドオン \) に拡張機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-105">Publish your Extension on Microsoft Edge Addons catalog \(Microsoft Edge Addons\).</span></span>  <span data-ttu-id="d8b80-106">まず、[パートナーセンター][MicrosoftPartnerCenter]で申請を作成して送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-106">You must first create a submission on [Partner Center][MicrosoftPartnerCenter] and submit it.</span></span>  <span data-ttu-id="d8b80-107">このドキュメントでは、拡張機能の申請を作成するために提供する必要があるすべての詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-107">This document lists all the details that you must provide to create an Extension submission.</span></span>  

## <span data-ttu-id="d8b80-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="d8b80-108">Before You Begin</span></span>  

*   <span data-ttu-id="d8b80-109">Microsoft Edge のアドオンで拡張機能を送信するには、[パートナーセンター][MicrosoftPartnerCenter]でアクティブな開発者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-109">You must have an active developer account on [Partner Center][MicrosoftPartnerCenter] to submit your Extension in Microsoft Edge Addons.</span></span>  <span data-ttu-id="d8b80-110">まだインストールしていない場合は、[新しい開発者アカウントを作成][MicrosoftPartnerCenter]します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-110">If you do not have one, [create a new developer account][MicrosoftPartnerCenter].</span></span>  
*   <span data-ttu-id="d8b80-111">拡張パッケージの zip ファイルを作成して、次のファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-111">Create a zip file of your Extension package and ensure that it contains these files:</span></span>  
    *   <span data-ttu-id="d8b80-112">マニフェストファイルと、拡張機能の名前とバージョンを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-112">The manifest file and it must define the name and version of your Extension.</span></span>  
    *   <span data-ttu-id="d8b80-113">拡張機能に必要な画像やその他のファイル。</span><span class="sxs-lookup"><span data-stu-id="d8b80-113">The images and other files that are required for your Extension.</span></span>  


<span data-ttu-id="d8b80-114">拡張機能の構築を開始していない場合は、「Microsoft Edge Chromium 拡張機能を構築するための[はじめ][ExtensionsGettingStarted]に」チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-114">If you have not started building an Extension, you may refer to the [Getting Started][ExtensionsGettingStarted] tutorial for building a Microsoft Edge Chromium extension.</span></span>  

<span data-ttu-id="d8b80-115">[パートナーセンター][MicrosoftPartnerCenter]で拡張機能の申請を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-115">To create an Extension submission on [Partner Center][MicrosoftPartnerCenter], follow these steps.</span></span>  

## <span data-ttu-id="d8b80-116">手順 1: 新しい申請を開始する</span><span class="sxs-lookup"><span data-stu-id="d8b80-116">Step 1: Start a New Submission</span></span>  

<span data-ttu-id="d8b80-117">[開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-117">Go to your [developer dashboard][MicrosoftPartnerCenter].</span></span>  <span data-ttu-id="d8b80-118">[概要] ページで、[**新しい拡張機能の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-118">From the Overview page, click **Create new extension**.</span></span>  

## <span data-ttu-id="d8b80-119">手順 2: 拡張機能 Zip ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="d8b80-119">Step 2: Upload Your Extension Zip File</span></span>  

<span data-ttu-id="d8b80-120">[**パッケージ**] ページでは、拡張機能の申請用に zip ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-120">The **Package** page is where you upload the zip file for your Extension submission.</span></span>  <span data-ttu-id="d8b80-121">パッケージは一度に1つしかアップロードできないため、拡張機能が完了していない場合は、進行中のパッケージをアップロードしてから公開するまでの間に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-121">You may only upload one package at a time, so if your Extension is not complete you may upload a work-in-progress package and update at any time before you publish it.</span></span>  <span data-ttu-id="d8b80-122">パッケージにファイルが含まれて `manifest.json` おり、アップロードする前に Microsoft Edge で正常に動作していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-122">Be sure that your package contains the `manifest.json` file and is working fine on Microsoft Edge prior to uploading.</span></span>  
<span data-ttu-id="d8b80-123">[アップロード] フィールドにパッケージをドラッグするか、[**ファイルの参照**] を選択して、パッケージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-123">Upload the package by dragging it into the upload field or by selecting **Browse your files**.</span></span>  <span data-ttu-id="d8b80-124">[パッケージ] ページでは、Extensions zip ファイルが検証され、**アップロードの成功または失敗の状態**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-124">The Package page validates the Extensions zip file and displays that **success or failure status of your upload**.</span></span>  <span data-ttu-id="d8b80-125">パッケージが検証に合格した場合正常にアップロードされ、成功メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-125">If the package passes validation; it is uploaded successfully and you see a success message.</span></span>  <span data-ttu-id="d8b80-126">パッケージの検証に失敗した場合パッケージは受け入れられず、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-126">If the package fails validation; the package is not accepted and you see an error message.</span></span>  <span data-ttu-id="d8b80-127">パッケージにエラーがある場合は、問題を解決して、もう一度アップロードしてみてください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-127">If there are errors in the package, resolve the issues and try uploading it again.</span></span>  

<span data-ttu-id="d8b80-128">アップロードが正常に完了したら、拡張機能の詳細を確認し、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-128">After successful upload, review your Extension details and click **Next** to proceed.</span></span>  

## <span data-ttu-id="d8b80-129">手順 3: 空き時間情報を入力する</span><span class="sxs-lookup"><span data-stu-id="d8b80-129">Step 3: Provide Availability details</span></span>  

### <span data-ttu-id="d8b80-130">表示の定義</span><span class="sxs-lookup"><span data-stu-id="d8b80-130">Define Visibility</span></span>  

<span data-ttu-id="d8b80-131">**表示**オプションを選んで、内線番号を検出して入手できる参加者を定義します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-131">Select a **Visibility** option to define the audience who may discover and acquire your Extension.</span></span>  <span data-ttu-id="d8b80-132">これにより、ユーザーが Microsoft Edge のアドオンで拡張機能を検索するかどうかを指定したり、一覧を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-132">This gives you the option to specify whether users should find your Extension in Microsoft Edge Addons or see the listing at all.</span></span>  <span data-ttu-id="d8b80-133">現在、[表示] には2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-133">Currently, you have two options under visibility:</span></span>  

*   `Public`  
    <span data-ttu-id="d8b80-134">これは既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="d8b80-134">This is the default option.</span></span>  
    <span data-ttu-id="d8b80-135">を選択する `Public` と、拡張機能が使用可能になり、Microsoft Edge のアドオンのすべてのユーザーが検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-135">If you select `Public`, your Extension is available and discoverable to everyone in Microsoft Edge Addons.</span></span>  <span data-ttu-id="d8b80-136">ユーザーが検索、参照、内線番号の直接リンクを使用して検索できるようにする場合は、このオプションを選択したままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-136">Leave this option selected if you want your Extension to be listed in Microsoft Edge Addons for users to find via searching, browsing, and the direct link of your Extension.</span></span>  

*   `Hidden`  
    <span data-ttu-id="d8b80-137">を選択した場合 `Hidden` 、拡張機能は、ユーザーが検索または参照したときの Microsoft Edge アドオンでは表示されません。拡張機能を配布するには、リストの URL を共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-137">If you select `Hidden`, your Extension is hidden in Microsoft Edge Addons from users searching or browsing; you must share your listing URL to distribute your Extension.</span></span>  <span data-ttu-id="d8b80-138">このリストへの直接リンクを持っているユーザーは、Microsoft Edge にダウンロードすることができます (この情報は、「拡張**機能の概要」** ページに表示されています)。</span><span class="sxs-lookup"><span data-stu-id="d8b80-138">Users who have the direct link to the listing may download it on Microsoft Edge \(you may find your listing URL under **Extension Overview** page of Extension submission\).</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-139">内線番号を**公開**し、後で [**非公開**] に変更した場合、内線番号が公開されているユーザーは、今後の更新プログラムにアクセスして受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-139">If you submit an Extension as **Public** and later change it to **Private**, Users who installed the Extension when it was public continue to have access and receive future updates.</span></span>  

### <span data-ttu-id="d8b80-140">市場の定義</span><span class="sxs-lookup"><span data-stu-id="d8b80-140">Define markets</span></span>  

<span data-ttu-id="d8b80-141">内線番号を提供する特定の市場を定義する必要があります。 [**利用可能状況**] ページの [**市場**] セクションで、[**オプションの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-141">You must define the specific markets in which you are offering your Extension, select **Show options** in the **Markets** section on the **Availability** page.</span></span>  <span data-ttu-id="d8b80-142">市場選択のポップアップウィンドウが表示され、そこで市場を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-142">The Market selection pop-up window is displayed, where you should choose the markets.</span></span>  <span data-ttu-id="d8b80-143">既定では、後で追加される可能性がある**将来の市場**も含めて、すべての市場が選択されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-143">By default, all markets are selected, including any **future markets** that may be added later.</span></span>  <span data-ttu-id="d8b80-144">個々の市場の選択を解除して除外することができます。または、[**すべて選択解除**] をクリックし、選択した個々の市場を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-144">You may deselect individual markets to exclude them, or you may click **Unselect all** and then add individual markets of your choice.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-145">ユーザーが既に特定の市場に内線番号を持っていて、その市場でその市場を削除した場合、その市場の内線番号を既に持っているユーザーはその市場を引き続き使用できますが、提出した後の更新プログラムは取得できません。</span><span class="sxs-lookup"><span data-stu-id="d8b80-145">If users already have your Extension in a certain market, and you later remove that market, users who already has the Extension in that market may continue to use it, but they do not get the later updates you submit.</span></span>  

<span data-ttu-id="d8b80-146">[**保存**] をクリックして、[**プロパティ**] セクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-146">Click **Save** to proceed to **Properties** section.</span></span>  

## <span data-ttu-id="d8b80-147">手順 4: 拡張機能のプロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="d8b80-147">Step 4: Select Properties for Your Extension</span></span>  

### <span data-ttu-id="d8b80-148">拡張機能のプロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b80-148">Extension properties</span></span>  

*   [<span data-ttu-id="d8b80-149">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d8b80-149">Category</span></span>](#category)  
*   [<span data-ttu-id="d8b80-150">プライバシーポリシーの要件</span><span class="sxs-lookup"><span data-stu-id="d8b80-150">Privacy policy requirements</span></span>](#privacy-policy-requirements)  
*   [<span data-ttu-id="d8b80-151">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="d8b80-151">Privacy policy URL</span></span>](#privacy-policy-url)  
*   [<span data-ttu-id="d8b80-152">Web サイトの URL</span><span class="sxs-lookup"><span data-stu-id="d8b80-152">Website URL</span></span>](#website-url)  
*   [<span data-ttu-id="d8b80-153">サポート URL/メールアドレス</span><span class="sxs-lookup"><span data-stu-id="d8b80-153">Support URL/email address</span></span>](#support-urlemail-address)  
*   [<span data-ttu-id="d8b80-154">内線番号の評価</span><span class="sxs-lookup"><span data-stu-id="d8b80-154">Extension Rating</span></span>](#extension-rating)  

#### <span data-ttu-id="d8b80-155">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d8b80-155">Category</span></span>  

<span data-ttu-id="d8b80-156">適切なカテゴリに拡張機能を登録すると、ユーザーは拡張機能を簡単に見つけて理解することができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-156">Listing your Extension in the right category helps users find your Extension easily and understand more about it.</span></span>  <span data-ttu-id="d8b80-157">拡張機能に最も適したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-157">Select a Category that best describes your Extension.</span></span>  

<span data-ttu-id="d8b80-158">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-158">**Possible Values**:</span></span>  

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

#### <span data-ttu-id="d8b80-159">プライバシーポリシーの要件</span><span class="sxs-lookup"><span data-stu-id="d8b80-159">Privacy policy requirements</span></span>  

<span data-ttu-id="d8b80-160">拡張機能で個人情報へのアクセス、収集、または送信を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-160">Indicate whether your Extension accesses, collects, or transmits any personal information.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-161">お客さまの内線番号にプライバシーポリシーが必要であり、提供されていない場合は、申請が認定に合格しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-161">If your Extension requires a privacy policy and you have not provided one, your submission may fail certification.</span></span>  

<span data-ttu-id="d8b80-162">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-162">**Possible Values**:</span></span>  

*   `No`<span data-ttu-id="d8b80-163">: プライバシーポリシーの URL は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-163">:  A privacy policy URL is optional.</span></span>  
*   `Yes`<span data-ttu-id="d8b80-164">: プライバシーポリシー URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-164">:  A privacy policy URL is required.</span></span>  

#### <span data-ttu-id="d8b80-165">プライバシー ポリシーの URL</span><span class="sxs-lookup"><span data-stu-id="d8b80-165">Privacy policy URL</span></span>  

<span data-ttu-id="d8b80-166">お客様は、お客様がお客様の内線番号とプライバシーポリシーに準拠していること、および必要に応じて有効なプライバシーポリシー URL を提供する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="d8b80-166">You are responsible for ensuring your Extension complies with privacy laws and regulations, and for providing a valid privacy policy URL, if required.</span></span>  <span data-ttu-id="d8b80-167">個人情報が、内線番号によってアクセス、送信、または収集される場合は、プライバシーポリシー URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-167">You must provide a privacy policy URL if any personal information is being accessed, transmitted, or collected by your Extension.</span></span>  
<span data-ttu-id="d8b80-168">拡張機能にプライバシーポリシーが必要かどうかを判断するには、 [Microsoft Edge Developer Agreement][MicrosoftAppDeveloperAgreement]と[Microsoft Edge アドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-168">To determine if your Extension requires a privacy policy, review the [Microsoft Edge Developer Agreement][MicrosoftAppDeveloperAgreement] and the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="d8b80-169">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-169">**Possible Values**:</span></span>  

*   `{url}`  

#### <span data-ttu-id="d8b80-170">Web サイトの URL</span><span class="sxs-lookup"><span data-stu-id="d8b80-170">Website URL</span></span>  

<span data-ttu-id="d8b80-171">このプロパティは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-171">This property is Optional.</span></span>  
<span data-ttu-id="d8b80-172">拡張機能の web ページの URL です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-172">The URL of the web page for your Extension.</span></span>  <span data-ttu-id="d8b80-173">この URL は、お客様の web サイトのページを指している必要があります。 Microsoft Edge アドオンの内線番号の web サイトではありません。</span><span class="sxs-lookup"><span data-stu-id="d8b80-173">This URL must point to a page on your own website, not the web listing for your Extension in Microsoft Edge Addons.</span></span>  

<span data-ttu-id="d8b80-174">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-174">**Possible Values**:</span></span>  

*   `{url}`  

#### <span data-ttu-id="d8b80-175">サポート URL/メールアドレス</span><span class="sxs-lookup"><span data-stu-id="d8b80-175">Support URL/email address</span></span>  

<span data-ttu-id="d8b80-176">このプロパティは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-176">This property is Optional.</span></span>  
<span data-ttu-id="d8b80-177">ユーザーが拡張機能をサポートするために使用する web ページの URL、またはサポートのために連絡するメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="d8b80-177">The URL of the web page where users go for support with your Extension, or an email address to contact you for support.</span></span>  <span data-ttu-id="d8b80-178">すべての申請のサポート情報が含まれているので、ユーザーが自分のサポートを受ける方法を知ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-178">You include support information for all submissions, so that your users know how to get support from you.</span></span>  

<span data-ttu-id="d8b80-179">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-179">**Possible Values**:</span></span>  

*   `{email_address}`  
*   `{url}`  

#### <span data-ttu-id="d8b80-180">内線番号の評価</span><span class="sxs-lookup"><span data-stu-id="d8b80-180">Extension Rating</span></span>  

<span data-ttu-id="d8b80-181">拡張評価は、お客様の内線番号の対象ユーザーの年齢を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-181">Extension rating helps us determine the age of the target audience of your Extension.</span></span>  
<span data-ttu-id="d8b80-182">拡張機能に成熟したコンテンツがあるかどうかを判断するには、 [Microsoft Edge のアドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-182">To help you determine if your Extensions has a mature content, review the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="d8b80-183">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-183">**Possible Values**:</span></span>  

*   <span data-ttu-id="d8b80-184">成熟した \ (チェックボックス \): 拡張機能に成熟したコンテンツが含まれている場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-184">Mature \(checkbox\): Check this box if your Extension contains any mature content.</span></span>  <span data-ttu-id="d8b80-185">拡張機能として「成熟」を選択した場合、その登録情報には、拡張機能に成熟したコンテンツが含まれていることを示す個別のタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-185">If you select mature for your Extension, your listing is available with a separate tag to indicate that the Extension contains mature content.</span></span>  

<span data-ttu-id="d8b80-186">[**保存**] をクリックして、セクションの一覧に進みます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-186">Click **Save** to proceed to listing section.</span></span>  

## <span data-ttu-id="d8b80-187">手順 5: 拡張機能の一覧情報を追加する</span><span class="sxs-lookup"><span data-stu-id="d8b80-187">Step 5: Add Listings Information for Your Extension</span></span>  

<span data-ttu-id="d8b80-188">これは、Microsoft Edge のアドオンで登録情報を表示するときにユーザーに表示される情報です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-188">This is the information that users see when viewing your listing in Microsoft Edge Addons.</span></span>  <span data-ttu-id="d8b80-189">リスト内の多くのフィールドはオプションですが、リストを目立たせるためにできるだけ多くの情報を提供することをお勧めします。 Microsoft Edge のアドオンの完了と見なされるために必要な最低限の情報は、拡張機能パッケージで指定された各言語の[テキスト説明](#description)、[拡張ロゴ](#store-logo)、および[小さいプロモーションタイル](#small-promotional-tile)です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-189">Many of the fields in a listing are optional, but we suggest providing as much information as possible to make your listing stand out.  The minimum required for your listing in Microsoft Edge Addons to be considered complete is the [text description](#description), [Extension logo](#store-logo), and [small promotional tile](#small-promotional-tile) in each language mentioned in your Extension package.</span></span>  

### <span data-ttu-id="d8b80-190">ストア登録情報フィールド</span><span class="sxs-lookup"><span data-stu-id="d8b80-190">Store Listing fields</span></span>  

*   [<span data-ttu-id="d8b80-191">ストア登録情報の言語</span><span class="sxs-lookup"><span data-stu-id="d8b80-191">Store listing languages</span></span>](#store-listing-languages)  
*   [<span data-ttu-id="d8b80-192">ストアの表示名</span><span class="sxs-lookup"><span data-stu-id="d8b80-192">Store display name</span></span>](#store-display-name)  
*   [<span data-ttu-id="d8b80-193">説明</span><span class="sxs-lookup"><span data-stu-id="d8b80-193">Description</span></span>](#description)  
*   [<span data-ttu-id="d8b80-194">ストアロゴ</span><span class="sxs-lookup"><span data-stu-id="d8b80-194">Store logo</span></span>](#store-logo)  
*   [<span data-ttu-id="d8b80-195">小規模のプロモーションタイル</span><span class="sxs-lookup"><span data-stu-id="d8b80-195">Small promotional tile</span></span>](#small-promotional-tile)  
*   [<span data-ttu-id="d8b80-196">メディア</span><span class="sxs-lookup"><span data-stu-id="d8b80-196">Media</span></span>](#media)  
*   [<span data-ttu-id="d8b80-197">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d8b80-197">Short description</span></span>](#short-description)  
*   [<span data-ttu-id="d8b80-198">検索語句</span><span class="sxs-lookup"><span data-stu-id="d8b80-198">Search terms</span></span>](#search-terms)  

#### <span data-ttu-id="d8b80-199">ストア登録情報の言語</span><span class="sxs-lookup"><span data-stu-id="d8b80-199">Store listing languages</span></span>  

<span data-ttu-id="d8b80-200">拡張機能パッケージで複数の言語がサポートされている場合は、各言語の登録情報ページが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-200">If your Extension package supports multiple languages, your Extension must have a listing page for each one.</span></span>  
<span data-ttu-id="d8b80-201">言語ごとに同じコンテンツを使用している場合は、各言語のリストの詳細 \ (テキストの説明、画像など) を個別に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-201">You must complete listing details \(text description, images, and so on\) for each language separately even if you are using the same content for each language.</span></span>  <span data-ttu-id="d8b80-202">拡張機能が複数の言語でローカライズされている場合、これらの言語は、一覧ページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-202">If your Extension is localized in more than one language, those languages are displayed at the top of listing page.</span></span>  

1.  <span data-ttu-id="d8b80-203">[**言語] ドロップダウン**リストから1つの言語名を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-203">Select any one language name from **Languages** drop-down list.</span></span>  
1.  <span data-ttu-id="d8b80-204">登録情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-204">Fill the listing details.</span></span>  
1.  <span data-ttu-id="d8b80-205">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-205">Click **Save**.</span></span>  
1.  <span data-ttu-id="d8b80-206">サポートされているすべての言語について同じ手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-206">Repeat for all of your supported languages.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-207">Microsoft Edge アドオンで登録する言語を追加または削除するには、拡張機能パッケージでサポートされている言語の一覧を変更してから、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-207">To add or remove languages for your listing in Microsoft Edge Addons, you must modify the list of languages supported by your Extension package and re-upload it.</span></span>  

<span data-ttu-id="d8b80-208">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-208">**Possible Values**:</span></span>  

*   `English (United States)`<span data-ttu-id="d8b80-209">: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-209">:  This is the default value.</span></span>  <span data-ttu-id="d8b80-210">パッケージの言語について説明していない場合は、既定の言語を英語 (米国) に設定し、英語 (米国) で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-210">If you do not mention any language in your package, we set your default language to English \(United States\) and you must provide a listing in English \(United States\).</span></span>  
*   `{language}` <span data-ttu-id="d8b80-211">\(`{Country}`\)</span><span class="sxs-lookup"><span data-stu-id="d8b80-211">\(`{Country}`\)</span></span>  

#### <span data-ttu-id="d8b80-212">ストアの表示名</span><span class="sxs-lookup"><span data-stu-id="d8b80-212">Store display name</span></span>  

<span data-ttu-id="d8b80-213">拡張機能パッケージマニフェストで示されている拡張子の名前。</span><span class="sxs-lookup"><span data-stu-id="d8b80-213">The name of Extension as mentioned in your Extension package manifest.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-214">名前を編集するには、拡張機能パッケージのマニフェストを更新して、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-214">To edit the name, you must update the manifest in your Extension package and re-upload it.</span></span>  

#### <span data-ttu-id="d8b80-215">説明</span><span class="sxs-lookup"><span data-stu-id="d8b80-215">Description</span></span>  

<span data-ttu-id="d8b80-216">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-216">This field is required.</span></span>  
<span data-ttu-id="d8b80-217">拡張機能のユーザーについての説明。</span><span class="sxs-lookup"><span data-stu-id="d8b80-217">The description for your users of what your Extension does.</span></span>  

<span data-ttu-id="d8b80-218">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-218">**Possible Values**:</span></span>  

*   <span data-ttu-id="d8b80-219">{plain_text}: 1万文字未満</span><span class="sxs-lookup"><span data-stu-id="d8b80-219">{plain_text}: Less than 10,000 characters.</span></span>  

#### <span data-ttu-id="d8b80-220">ストアロゴ</span><span class="sxs-lookup"><span data-stu-id="d8b80-220">Store logo</span></span>  

<span data-ttu-id="d8b80-221">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-221">This field is required.</span></span>  
<span data-ttu-id="d8b80-222">拡張ロゴの1:1 画像。</span><span class="sxs-lookup"><span data-stu-id="d8b80-222">A 1:1 image for your Extension logo.</span></span>  

<span data-ttu-id="d8b80-223">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-223">**Possible Values**:</span></span>  

*   <span data-ttu-id="d8b80-224">128px x 128px、PNG \ (.png \)</span><span class="sxs-lookup"><span data-stu-id="d8b80-224">128px x 128px, PNG \(.png\)</span></span>  
*   <span data-ttu-id="d8b80-225">150px x 140px、PNG \ (.png \)</span><span class="sxs-lookup"><span data-stu-id="d8b80-225">150px x 140px, PNG \(.png\)</span></span>  
*   <span data-ttu-id="d8b80-226">300px x 300px、PNG \ (.png \): 推奨サイズ。</span><span class="sxs-lookup"><span data-stu-id="d8b80-226">300px x 300px, PNG \(.png\):  The recommended size.</span></span>  

#### <span data-ttu-id="d8b80-227">小規模のプロモーションタイル</span><span class="sxs-lookup"><span data-stu-id="d8b80-227">Small promotional tile</span></span>  

<span data-ttu-id="d8b80-228">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-228">This field is required.</span></span>  
<span data-ttu-id="d8b80-229">小さいサイズのプロモーションタイル。</span><span class="sxs-lookup"><span data-stu-id="d8b80-229">A small size promotional tile.</span></span>  <span data-ttu-id="d8b80-230">このタイルには、登録情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-230">Your listing is displayed on this tile.</span></span>  

<span data-ttu-id="d8b80-231">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-231">**Possible Values**:</span></span>  

*   <span data-ttu-id="d8b80-232">440px x 280x, PNG \ (.png \)</span><span class="sxs-lookup"><span data-stu-id="d8b80-232">440px x 280x, PNG \(.png\)</span></span>  

#### <span data-ttu-id="d8b80-233">メディア</span><span class="sxs-lookup"><span data-stu-id="d8b80-233">Media</span></span>  

<span data-ttu-id="d8b80-234">このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-234">This field is optional.</span></span>  
<span data-ttu-id="d8b80-235">製品をより効果的に表示するために、これらのアセットを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-235">You should provide these assets to help display your product more effectively.</span></span>  

*   <span data-ttu-id="d8b80-236">スクリーンショット</span><span class="sxs-lookup"><span data-stu-id="d8b80-236">Screenshots</span></span>  
    <span data-ttu-id="d8b80-237">拡張機能について説明する拡張機能の画像。</span><span class="sxs-lookup"><span data-stu-id="d8b80-237">The images of your Extension that describe what your Extension does.</span></span>  
    
*   <span data-ttu-id="d8b80-238">大きなプロモーションタイル</span><span class="sxs-lookup"><span data-stu-id="d8b80-238">Large promotion tiles</span></span>  
    <span data-ttu-id="d8b80-239">大きなプロモーションタイルは、Microsoft Edge のアドオンで拡張機能をより目立つようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="d8b80-239">A large promotional tile to be feature your Extension more prominently in Microsoft Edge Addons.</span></span>  
    
*   <span data-ttu-id="d8b80-240">YouTube ビデオの URL</span><span class="sxs-lookup"><span data-stu-id="d8b80-240">YouTube video URL</span></span>  
    <span data-ttu-id="d8b80-241">[内線番号の有効な YouTube ビデオ URL][MicrosoftEdgeAddonsUploadYouTubeVideo]。</span><span class="sxs-lookup"><span data-stu-id="d8b80-241">A valid [YouTube video URL for your Extension][MicrosoftEdgeAddonsUploadYouTubeVideo].</span></span>  <span data-ttu-id="d8b80-242">ビデオの品質と最小の長さは、適切である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-242">Your video should be good quality and minimal length.</span></span>  <span data-ttu-id="d8b80-243">Microsoft Edge のアドオンで、内線番号を公開する前に、YouTube ビデオが認定に合格している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-243">Your YouTube video must pass certification before publishing your Extension in Microsoft Edge Addons.</span></span>  <span data-ttu-id="d8b80-244">YouTube ビデオが[Microsoft Edge アドオンカタログ開発者ポリシードキュメント][MicrosoftEdgeAddonsCatalogDeveloperPolicies]に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-244">Verify that your YouTube video complies with the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="d8b80-245">指定**可能な値**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-245">**Possible Values**:</span></span>  

*   <span data-ttu-id="d8b80-246">最大10個のスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="d8b80-246">10 Screenshots maximum.</span></span>  
    *   <span data-ttu-id="d8b80-247">640 px x 480px、PNG \ (.png \): スクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="d8b80-247">640px x 480px, PNG \(.png\):  Screenshots.</span></span>  
    *   <span data-ttu-id="d8b80-248">1280px x 800px、PNG \ (.png \): スクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="d8b80-248">1280px x 800px, PNG \(.png\):  Screenshots.</span></span>  
*   <span data-ttu-id="d8b80-249">1400px x 560px、PNG \ (.png \): 大きなプロモーションタイル。</span><span class="sxs-lookup"><span data-stu-id="d8b80-249">1400px x 560px, PNG \(.png\):  Large promotion tiles.</span></span>  
*   <span data-ttu-id="d8b80-250">60秒または短い間の YouTube ビデオ URL。</span><span class="sxs-lookup"><span data-stu-id="d8b80-250">60 seconds or shorter and 2GB or smaller, YouTube video URL.</span></span>  

#### <span data-ttu-id="d8b80-251">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d8b80-251">Short description</span></span>  

<span data-ttu-id="d8b80-252">Catchy の簡単な説明。製品の一覧の一番上に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-252">A short, catchy description that may be used at the top of the listing for your product.</span></span>  <span data-ttu-id="d8b80-253">指定しない場合は、長い説明の最初の数行が代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-253">If not provided, the first few lines from your longer description are used instead.</span></span>  <span data-ttu-id="d8b80-254">説明はこのテキストの下にも表示されているため、リストが繰り返されないように、別のテキストの短い説明を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-254">Because your description also appears below this text, you should provide a short description with different text so that your listing is less repetitive.</span></span>  <span data-ttu-id="d8b80-255">拡張機能の短い説明は、パッケージのマニフェストファイルから直接選択されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-255">The Short description of your Extension is picked directly from the manifest file of your package.</span></span>  

> [!NOTE]
> <span data-ttu-id="d8b80-256">短い説明を編集するには、拡張機能パッケージのマニフェストを更新して、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-256">To edit the short description, you must update the manifest in your Extension package and re-upload it.</span></span>  

#### <span data-ttu-id="d8b80-257">検索語句</span><span class="sxs-lookup"><span data-stu-id="d8b80-257">Search terms</span></span>  

<span data-ttu-id="d8b80-258">検索用語は、ユーザーには表示されない1つの単語または短いフレーズですが、ユーザーがこれらの用語を使用して検索するときに、Microsoft Edge のアドオンで拡張機能を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-258">Search terms are single words or short phrases that are not displayed to users but help make your Extension discoverable in Microsoft Edge Addons when users search using those terms.</span></span>  

<span data-ttu-id="d8b80-259">**要件**:</span><span class="sxs-lookup"><span data-stu-id="d8b80-259">**Requirements**:</span></span>  

*   <span data-ttu-id="d8b80-260">7つ以下の検索語句</span><span class="sxs-lookup"><span data-stu-id="d8b80-260">7 or fewer search terms</span></span>  
*   <span data-ttu-id="d8b80-261">検索用語あたり30文字以下</span><span class="sxs-lookup"><span data-stu-id="d8b80-261">30 or fewer characters per search term</span></span>  
*   <span data-ttu-id="d8b80-262">検索語句の合計が21以下である</span><span class="sxs-lookup"><span data-stu-id="d8b80-262">21 or fewer words for combined search terms</span></span>  

<span data-ttu-id="d8b80-263">[**保存**] をクリックして、リストセクションの保存に進みます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-263">Click **Save** to proceed to save your listing section.</span></span>  <span data-ttu-id="d8b80-264">[**発行**] をクリックして、申請の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-264">Click **Publish** to provide submission details.</span></span>  

## <span data-ttu-id="d8b80-265">手順 6: 申請を完了し、[発行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-265">Step 6: Complete your submission and click Publish</span></span>  

<span data-ttu-id="d8b80-266">拡張機能の申請プロセスの [申請オプション] ページでは、製品を適切にテストするための詳細情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="d8b80-266">The Submission options page of the Extension submission process is where you provide more information to help us test your product properly.</span></span>  <span data-ttu-id="d8b80-267">これは省略可能な手順ですが、多くの申請にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-267">This is an optional step, but it is recommended for many submissions.</span></span>  

### <span data-ttu-id="d8b80-268">公開の保留オプション</span><span class="sxs-lookup"><span data-stu-id="d8b80-268">Publishing hold options</span></span>  

<span data-ttu-id="d8b80-269">既定では、申請は認定に合格するとすぐに公開されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-269">By default, your submission is published as soon as it passes certification.</span></span>  <span data-ttu-id="d8b80-270">特定の日付まで申請を発行することを保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-270">You may choose to place a hold on publishing your submission until a specific date.</span></span>  <span data-ttu-id="d8b80-271">ここでは、このセクションのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-271">The options in this section are described below.</span></span>  

*   **<span data-ttu-id="d8b80-272">認定に合格するとすぐに申請を公開する</span><span class="sxs-lookup"><span data-stu-id="d8b80-272">Publish your submission as soon as it passes certification</span></span>**  

    <span data-ttu-id="d8b80-273">これは既定の選択です。</span><span class="sxs-lookup"><span data-stu-id="d8b80-273">This is the default selection.</span></span>  <span data-ttu-id="d8b80-274">これは、申請が認定に合格するとすぐに、発行プロセスを開始することを意味します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-274">It means that your submission begins the publishing process as soon as it passes certification</span></span>  

*   **<span data-ttu-id="d8b80-275">特定の日に申請の公開を開始する</span><span class="sxs-lookup"><span data-stu-id="d8b80-275">Start publishing your submission on a certain date</span></span>**  

    <span data-ttu-id="d8b80-276">[特定の**日付に提出の発行を開始**する] を選択して、申請が特定の日付まで公開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d8b80-276">Choose **Start publishing your submission on a certain date** to ensure that the submission is not published until a specific date.</span></span>  <span data-ttu-id="d8b80-277">このオプションを使用すると、指定した日付以降に、できるだけ早く申請がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-277">With this option, your submission is released as soon as possible on or after the date you specify.</span></span>  <span data-ttu-id="d8b80-278">日付は 24 時間以上先の日付にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-278">The date must be at least 24 hours in the future.</span></span>  <span data-ttu-id="d8b80-279">日付と共に、提出を開始する時刻を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-279">Along with the date, you may specify the time at which the submission should begin to be published.</span></span>  

### <span data-ttu-id="d8b80-280">認定の注意書き</span><span class="sxs-lookup"><span data-stu-id="d8b80-280">Notes for certification</span></span>  

<span data-ttu-id="d8b80-281">内線番号を申請するときに、[認定のメモ] ページを使用して、認定テスト担当者に追加情報を提供するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-281">As you submit your Extension, you have the option to use the Notes for certification page to provide additional information to the certification testers.</span></span>  <span data-ttu-id="d8b80-282">この情報は、拡張機能が正しくテストされていることを確認するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-282">This information helps ensure that your Extension is tested correctly.</span></span>  <span data-ttu-id="d8b80-283">申請を完全にテストできない場合は、認定が不合格になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-283">If we are not able to fully test your submission, it may fail certification.</span></span>  

<span data-ttu-id="d8b80-284">以下の \ (内線番号に該当する場合) を必ず含めてください。</span><span class="sxs-lookup"><span data-stu-id="d8b80-284">Make sure to include the following \(if applicable for your Extension\):</span></span>  

*   <span data-ttu-id="d8b80-285">テストアカウントのユーザー名とパスワード。</span><span class="sxs-lookup"><span data-stu-id="d8b80-285">User names and passwords for test accounts.</span></span>  
*   <span data-ttu-id="d8b80-286">非表示の機能やロックされた機能にアクセスする手順。</span><span class="sxs-lookup"><span data-stu-id="d8b80-286">Steps to access hidden or locked features.</span></span>  
*   <span data-ttu-id="d8b80-287">地域またはその他のユーザー設定に基づいて、動作の違いが予測されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-287">Expected differences in behavior based on region or other user settings.</span></span>  
*   <span data-ttu-id="d8b80-288">アプリの更新プログラムで変更された内容に関する情報。</span><span class="sxs-lookup"><span data-stu-id="d8b80-288">Information about what changed in an app update.</span></span>  
*   <span data-ttu-id="d8b80-289">テスターが申請について理解していると思われるその他のもの。</span><span class="sxs-lookup"><span data-stu-id="d8b80-289">Anything else you think testers must understand about your submission.</span></span>  

<span data-ttu-id="d8b80-290">上記の詳細を完了したら、[**発行**] をクリックして、Microsoft Edge のアドオンで拡張機能を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8b80-290">After completing the above details, click **Publish** to submit your Extension in Microsoft Edge Addons.</span></span>  

<span data-ttu-id="d8b80-291">拡張機能の申請の作成が完了し、[**公開**] をクリックすると、申請が認定手順に入ります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-291">When you finish creating the submission for your Extension and click **Publish**, the submission enters the certification step.</span></span>  <span data-ttu-id="d8b80-292">通常、このプロセスは数日以内に完了します。ただし、場合によっては、最大7営業日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8b80-292">This process usually is completed within a couple of days, though in some cases it may take up to 7 business days.</span></span>  <span data-ttu-id="d8b80-293">申請が認定に合格すると、特定の日付までリリースされないように指定するために、[公開保留] オプションを選択していない限り、拡張機能が Microsoft Edge のアドオンに公開されます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-293">After your submission passes certification, your Extension is published in Microsoft Edge Addons unless you selected the Publishing hold options to specify that it should not be released until a certain date.</span></span>  <span data-ttu-id="d8b80-294">申請が公開され、ダッシュボードの内線番号がに変更されたときに通知され `In the Store` ます。</span><span class="sxs-lookup"><span data-stu-id="d8b80-294">You are notified when your submission is published, and the status of your Extension in the dashboard changes to `In the Store`.</span></span>  

<!-- image links -->  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge \ (Chromium \) Extensions の概要 |Microsoft ドキュメント"  

[MicrosoftEdgeAddonsUploadYouTubeVideo]: ./upload-video.md "YouTube のビデオをアップロードする |Microsoft ドキュメント"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge アドオンカタログ開発者ポリシー |Microsoft ドキュメント"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "アプリ開発者契約 |Microsoft ドキュメント"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  
