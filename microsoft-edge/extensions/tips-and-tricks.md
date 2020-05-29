---
description: Microsoft Edge extensions に関する便利なヒントとテクニックについて説明します。
title: 拡張機能-ヒントとテクニック
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: db15aa49649432a6c4400b4e6830501c40485a83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569427"
---
# <span data-ttu-id="1eeab-104">ヒント</span><span class="sxs-lookup"><span data-stu-id="1eeab-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="1eeab-105">現在 Microsoft Edge 拡張機能を使用している場合も、既に公開している場合も、次のヒントとテクニックが役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="1eeab-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>

## <span data-ttu-id="1eeab-106">Microsoft Store の内線番号への直接リンクを取得する</span><span class="sxs-lookup"><span data-stu-id="1eeab-106">Get a direct link to your extension in the Microsoft Store</span></span>
<span data-ttu-id="1eeab-107">Windows デベロッパーセンターダッシュボードでは、Microsoft Store の内線番号への直接リンクを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span> <span data-ttu-id="1eeab-108">このリンクは、お客様の内線番号の広告や共有に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-108">This link can be useful for advertising and sharing out your extension.</span></span>


<span data-ttu-id="1eeab-109">Windows デベロッパーセンターにログインし、ダッシュボードを使用して内線番号に移動した後、[アプリ id] ページで、[**ストアプロトコル] リンク**行に次のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>

![ストアプロトコルリンク](./media/store-link.png)
 
## <span data-ttu-id="1eeab-111">Microsoft Store のポリシーに従っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="1eeab-111">Make sure you’re following the Microsoft Store Policy</span></span>
<span data-ttu-id="1eeab-112">拡張機能を作成する場合は、Microsoft store の[ポリシー](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)で強調表示されている microsoft store に提出するためのガイドラインに留意してください。</span><span class="sxs-lookup"><span data-stu-id="1eeab-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span></span> 
 
<span data-ttu-id="1eeab-113">Microsoft Edge extensions には、次のような追加のポリシーのセットも用意[されています](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。</span><span class="sxs-lookup"><span data-stu-id="1eeab-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span></span>

## <span data-ttu-id="1eeab-114">Microsoft Store で拡張機能の発見性を向上させる</span><span class="sxs-lookup"><span data-stu-id="1eeab-114">Improve your extension’s discoverability in the Microsoft Store</span></span>

<span data-ttu-id="1eeab-115">拡張機能の申請にキーワードを追加して、検索によって検索結果を imporove することができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-115">You can add keywords to your extension submission to imporove its discoverability through searches.</span></span> <span data-ttu-id="1eeab-116">たとえば、"Microsoft Edge Extensions" と "内線名" のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1eeab-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span></span> 

<span data-ttu-id="1eeab-117">これは、Windows デベロッパーセンターの拡張機能の [説明] セクションで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span> <span data-ttu-id="1eeab-118">これらのキーワードは、拡張機能でサポートされているすべての言語に対して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eeab-118">These keywords will need to be added for every language your extension supports.</span></span>

![レビューに返信を送信する](./media/keywords.png)

## <span data-ttu-id="1eeab-120">Microsoft ストアへの申請を自動化する</span><span class="sxs-lookup"><span data-stu-id="1eeab-120">Automate your submission to the Microsoft Store</span></span>
<span data-ttu-id="1eeab-121">新しい Microsoft ストア申請 API を使用すると、microsoft ストアへの申請を自動化および合理化することができます。これにより、アプリ/ゲーム、アドオン (アプリ内購入)、およびパッケージフライトを REST API で更新できます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span></span> <span data-ttu-id="1eeab-122">[ドキュメントとサンプル](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services)をご覧になるか、またはオープンソースの[送信 API の VSTS 拡張機能](https://github.com/Microsoft/windows-dev-center-vsts-extension)を使って作業を開始してください。</span><span class="sxs-lookup"><span data-stu-id="1eeab-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>

## <span data-ttu-id="1eeab-123">Windows フィードバック Hub を使用して、フィードバック/レビュー/機能のリクエストを収集する</span><span class="sxs-lookup"><span data-stu-id="1eeab-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>

<span data-ttu-id="1eeab-124">拡張機能をポイントするリンクを埋め込むことにより、ユーザーを拡張機能の Windows フィードバック Hub サブカテゴリに導くことができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span> <span data-ttu-id="1eeab-125">このリンクは、次の形式を使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eeab-125">This link will need to be created using the following format:</span></span> 

`feedback-hub://?tabid=2&appid=<PFN>!App`

<span data-ttu-id="1eeab-126">`<PFN>`パッケージファミリ名の内線番号に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eeab-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span> <span data-ttu-id="1eeab-127">これは、Windows デベロッパーセンターの拡張機能の [**アプリ id** ] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="1eeab-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>

## <span data-ttu-id="1eeab-128">評価とレビューを確認する</span><span class="sxs-lookup"><span data-stu-id="1eeab-128">Check out your ratings and reviews</span></span>
<span data-ttu-id="1eeab-129">定期的にログインして、ユーザーのレビューと評価を確認します。</span><span class="sxs-lookup"><span data-stu-id="1eeab-129">Log in regularly to check your user reviews and ratings.</span></span> <span data-ttu-id="1eeab-130">UWP アプリには、現在のユーザー市場に関する情報しかありませんが、Windows デベロッパーセンターにログインすると、すべての市場での平均評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>

## <span data-ttu-id="1eeab-131">ユーザーレビューに返信する</span><span class="sxs-lookup"><span data-stu-id="1eeab-131">Respond to user reviews</span></span>
<span data-ttu-id="1eeab-132">Microsoft ストアのユーザーレビューには、Windows デベロッパーセンターのダッシュボードを通じて返信することができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span> <span data-ttu-id="1eeab-133">拡張機能に移動し、[分析] で [**レビュー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1eeab-133">Navigate to your extension and under Analytics select **Reviews**.</span></span> <span data-ttu-id="1eeab-134">顧客に直接返信できるようにするための各レビューの下にリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span> <span data-ttu-id="1eeab-135">この通信チャネルを使用すると、フィードバック、解決策、またはレビューを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="1eeab-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>

![レビューに返信を送信する](./media/reviews.png)
