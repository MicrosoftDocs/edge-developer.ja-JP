---
description: Microsoft Store の拡張機能更新プロセス。
title: 拡張機能の一覧を更新する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 0d4512331b4f9542921d2063c908b5e9d4251074
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015681"
---
# <span data-ttu-id="0c7c0-104">拡張機能の一覧を更新する</span><span class="sxs-lookup"><span data-stu-id="0c7c0-104">Update An Extension Listing</span></span>  

<span data-ttu-id="0c7c0-105">Microsoft Edge アドオンカタログで既存の登録情報を更新します (Microsoft Edge アドオン \)。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-105">Update an existing listing in Microsoft Edge Addons catalog \(Microsoft Edge Addons\).</span></span>  <span data-ttu-id="0c7c0-106">公開された拡張機能はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-106">You may change a published Extension at any time.</span></span>  <span data-ttu-id="0c7c0-107">更新中は、説明やロゴの更新などの変更を行うために、拡張子全体を更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-107">While you are updating, you do not have to update the entire Extension to make few changes such as updating description or logo.</span></span>  <span data-ttu-id="0c7c0-108">ただし、拡張機能パッケージを更新する場合は、毎回バージョン番号を上げておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-108">But if you update your Extension package, just remember to increase the version number each time.</span></span>  

## <span data-ttu-id="0c7c0-109">既に公開されている拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="0c7c0-109">Update an already published Extension</span></span>  

<span data-ttu-id="0c7c0-110">登録情報を更新するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-110">To update your listing, follow these steps:</span></span>  

1.  <span data-ttu-id="0c7c0-111">[開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-111">Go to your [developer dashboard][MicrosoftPartnerCenter].</span></span>  <span data-ttu-id="0c7c0-112">[概要] ページで、更新するリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-112">From the Overview page, click the listing which you want to update.</span></span>  <span data-ttu-id="0c7c0-113">これにより、発行中に入力した申請フォームの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-113">This brings up the submission form details which you filled out during publishing.</span></span>  
1.  <span data-ttu-id="0c7c0-114">パッケージ、説明、グラフィックアセット、またはその他の設定に必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-114">Make the changes you want to the package, description, graphic assets, or other settings.</span></span>  <span data-ttu-id="0c7c0-115">パッケージファイルを更新する場合は、マニフェストのバージョンが前のパッケージバージョンよりも大きいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-115">If you update the package file, make sure that the version in the manifest is higher than the previous package version.</span></span>
1.  <span data-ttu-id="0c7c0-116">変更を加えたら、[保存]、[発行] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-116">After making changes, click Save and then Publish.</span></span>
1.  <span data-ttu-id="0c7c0-117">[パートナーセンター][MicrosoftPartnerCenter]の開発者ダッシュボードにアクセスして、リストがに変更された状態をに確認し `In the store` `In the store.  Certification in progress` ます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-117">Visit the [Partner Center][MicrosoftPartnerCenter] developer dashboard to see the status of your listing changed from `In the store` to `In the store.  Certification in progress`.</span></span>  

> [!NOTE]
> <span data-ttu-id="0c7c0-118">更新プログラムの公開プロセスの期間は、数時間から数日間に及びます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-118">The duration of the update publishing process ranges from a few hours to few days.</span></span>  

<span data-ttu-id="0c7c0-119">`Status`列が表示されたら `In the store` 、拡張機能の更新プログラムを Microsoft Edge のアドオンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-119">Once the `Status` column displays `In the store`, your Extension update is available in Microsoft Edge Addons.</span></span>  

## <span data-ttu-id="0c7c0-120">認定手順中に拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="0c7c0-120">Update an Extension during certification step</span></span>  

<span data-ttu-id="0c7c0-121">公開手順を開始する前に、提出後に拡張機能の申請を編集して更新することができます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-121">You may edit and update your Extension submission after submitting prior to it entering the Publish step.</span></span>  <span data-ttu-id="0c7c0-122">[パートナーセンター][MicrosoftPartnerCenter]のリストに関連付けられている拡張**機能の概要**ページで、拡張機能の状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-122">You may check the status of your Extension on the **Extension Overview** page associated with your listing on [Partner Center][MicrosoftPartnerCenter].</span></span>  

<span data-ttu-id="0c7c0-123">申請を編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-123">To edit your submission, you may follow these steps:</span></span>  

1.  <span data-ttu-id="0c7c0-124">[開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-124">Go to your [developer dashboard][MicrosoftPartnerCenter].</span></span>  <span data-ttu-id="0c7c0-125">[ **概要** ] ページで、更新するリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-125">From the **Overview** page, click the listing which you want to update.</span></span>  <span data-ttu-id="0c7c0-126">これにより、発行中に入力した申請フォームの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-126">This brings up the submission form details which you filled out during publishing.</span></span>  
1.  <span data-ttu-id="0c7c0-127">左側のナビゲーションバーに表示されている [ **拡張機能の概要** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-127">Go to **Extension overview** section using the left navigation bar as shown.</span></span>  <span data-ttu-id="0c7c0-128">[ **送信のキャンセル** ] をクリックして、現在の申請をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-128">Cancel the current submission by clicking **Cancel submission** button.</span></span>  
1.  <span data-ttu-id="0c7c0-129">[その他] セクションに移動し、パッケージ、説明、グラフィックアセット、その他の設定に必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-129">Move to other section and make the changes you want to the package, description, graphic assets or other settings.</span></span>  <span data-ttu-id="0c7c0-130">パッケージファイルを更新する場合は、マニフェストのバージョンが前のパッケージバージョンよりも大きいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-130">If you update the package file, make sure that the version in the manifest is higher than the previous package version.</span></span>  
1.  <span data-ttu-id="0c7c0-131">変更を加えたら、[ **保存** ]、[ **発行**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-131">After making changes, click **Save** and then **Publish**.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0c7c0-132">このプロセスは、認定パイプラインから現在の申請を停止して削除し、新しいレビューは最新の申請から始まります。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-132">This process stops and removes your current submission from our certification pipeline and a new review starts with the latest submission.</span></span>  

> [!NOTE]
> <span data-ttu-id="0c7c0-133">更新プログラムの公開プロセスの期間は、数時間から数日間に及びます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-133">The duration of the update publishing process ranges from a few hours to few days.</span></span>  

<span data-ttu-id="0c7c0-134">`Status`列が表示されたら `In the store` 、拡張機能の更新プログラムを Microsoft Edge のアドオンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-134">Once the `Status` column displays `In the store`, your Extension update is available in Microsoft Edge Addons.</span></span>  

## <span data-ttu-id="0c7c0-135">Microsoft Edge アドオンから拡張機能を削除する</span><span class="sxs-lookup"><span data-stu-id="0c7c0-135">Remove your Extension from Microsoft Edge Addons</span></span>  

<span data-ttu-id="0c7c0-136">Microsoft Edge アドオンから拡張機能を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-136">To remove your Extension from Microsoft Edge Addons, do the following:</span></span>  

1.  <span data-ttu-id="0c7c0-137">[開発者ダッシュボード][MicrosoftPartnerCenter]に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-137">Go to your [developer dashboard][MicrosoftPartnerCenter].</span></span>  <span data-ttu-id="0c7c0-138">[ **概要** ] ページで、削除するリストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-138">From the **Overview** page, click the listing which you want to remove.</span></span>  
1.  <span data-ttu-id="0c7c0-139">リストの [ **拡張機能の概要** ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-139">Open **Extension Overview** page of your listing.</span></span>  
1.  <span data-ttu-id="0c7c0-140">[ **非公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-140">Click **Unpublish**.</span></span>  <span data-ttu-id="0c7c0-141">これにより、Microsoft Edge アドオンの一覧が unpublishes されます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-141">This unpublishes the listing from Microsoft Edge Addons.</span></span>  

<span data-ttu-id="0c7c0-142">次の手順では、拡張機能を Microsoft Edge アドオンから削除します。これは、新しいユーザーが拡張機能を見つけることも、インストールすることもできないことを意味します。ただし、既に拡張機能をインストールしているユーザーは引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0c7c0-142">These steps remove the Extension from Microsoft Edge Addons, that means new users are not able to find your Extension or install it, but users who already installed the Extension may continue to use it.</span></span>  

<!-- image links -->  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "パートナーセンター"  
