---
description: Microsoft Edge 拡張機能に関する便利なヒントとコツについて説明します。
title: ヒントと|拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, developer, extensions
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8a5ea19152f5524d86d17d6f978c677c45f8f3a8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399352"
---
# <a name="tips-and-tricks"></a><span data-ttu-id="cf160-104">ヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="cf160-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="cf160-105">Microsoft Edge 拡張機能で現在作業している場合でも、既に公開済みである場合でも、次のヒントとコツが役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf160-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>  

## <a name="get-a-direct-link-to-your-extension-in-the-microsoft-store"></a><span data-ttu-id="cf160-106">Microsoft Store で拡張機能への直接リンクを取得する</span><span class="sxs-lookup"><span data-stu-id="cf160-106">Get a direct link to your extension in the Microsoft Store</span></span>  

<span data-ttu-id="cf160-107">Windows デベロッパー センター ダッシュボードでは、Microsoft Store で拡張機能への直接リンクを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cf160-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span>  <span data-ttu-id="cf160-108">このリンクは、広告や拡張機能の共有に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf160-108">This link can be useful for advertising and sharing out your extension.</span></span>  

<span data-ttu-id="cf160-109">Windows デベロッパー センターにログインし、ダッシュボードを介して拡張機能に移動すると、[アプリ ID] ページの [ストア プロトコル] リンク行にリンク **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="cf160-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>  

![ストア プロトコル リンク](./media/store-link.png)  
 
## <a name="make-sure-youre-following-the-microsoft-store-policy"></a><span data-ttu-id="cf160-111">Microsoft Store ポリシーに従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf160-111">Make sure you’re following the Microsoft Store Policy</span></span>  

<span data-ttu-id="cf160-112">拡張機能を作成する場合は [、Microsoft](/windows/uwp/publish/store-policies)ストア ポリシーで強調表示されている Microsoft Store に提出するためのガイドラインに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf160-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](/windows/uwp/publish/store-policies).</span></span>  
 
<span data-ttu-id="cf160-113">Microsoft Edge 拡張機能には、ここに示すポリシーの追加セットも用意 [されています](/windows/uwp/publish/store-policies#pol_10_12)。</span><span class="sxs-lookup"><span data-stu-id="cf160-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](/windows/uwp/publish/store-policies#pol_10_12).</span></span>  

## <a name="improve-your-extensions-discoverability-in-the-microsoft-store"></a><span data-ttu-id="cf160-114">Microsoft Store での拡張機能の検出可能性を向上させる</span><span class="sxs-lookup"><span data-stu-id="cf160-114">Improve your extension’s discoverability in the Microsoft Store</span></span>  

<span data-ttu-id="cf160-115">拡張機能の申請にキーワードを追加して、検索を通じて検出可能性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="cf160-115">You can add keywords to your extension submission to improve its discoverability through searches.</span></span>  <span data-ttu-id="cf160-116">たとえば、 `Microsoft Edge Extensions` および `name of my extension` .</span><span class="sxs-lookup"><span data-stu-id="cf160-116">For example, `Microsoft Edge Extensions` and `name of my extension`.</span></span>  

<span data-ttu-id="cf160-117">これは、拡張機能の説明セクションの Windows デベロッパー センターで行います。</span><span class="sxs-lookup"><span data-stu-id="cf160-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span>  <span data-ttu-id="cf160-118">これらのキーワードは、拡張機能でサポートされている言語ごとに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf160-118">These keywords will need to be added for every language your extension supports.</span></span>  

![キーワードを使用してレビューに応答を送信する](./media/keywords.png)  

## <a name="automate-your-submission-to-the-microsoft-store"></a><span data-ttu-id="cf160-120">Microsoft Store への申請を自動化する</span><span class="sxs-lookup"><span data-stu-id="cf160-120">Automate your submission to the Microsoft Store</span></span>  

<span data-ttu-id="cf160-121">新しい Microsoft Store 申請 API を使用すると、アプリ/ゲーム、アドオン \(アプリ内購入\)、REST API を使用してフライトをパッケージ化することで、Microsoft Store への申請を自動化および合理化できます。</span><span class="sxs-lookup"><span data-stu-id="cf160-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons \(in-app purchases\), and package flights through a REST API.</span></span>  <span data-ttu-id="cf160-122">ドキュメントとサンプル [を確認するか、](/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) オープンソースの申請 [API VSTS](https://github.com/Microsoft/windows-dev-center-vsts-extension) 拡張機能を使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="cf160-122">Check out the [documentation and samples](/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>  

## <a name="use-the-windows-feedback-hub-to-gather-feedbackreviewsfeature-requests"></a><span data-ttu-id="cf160-123">Windows フィードバック ハブを使用してフィードバック/レビュー/機能要求を収集する</span><span class="sxs-lookup"><span data-stu-id="cf160-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>  

<span data-ttu-id="cf160-124">ユーザーに対して、それをポイントするリンクを埋め込み、拡張機能の Windows Feedback Hub サブカテゴリにユーザーを指示できます。</span><span class="sxs-lookup"><span data-stu-id="cf160-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span>  <span data-ttu-id="cf160-125">このリンクは、次の形式で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf160-125">This link will need to be created using the following format:</span></span>  

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

<span data-ttu-id="cf160-126">拡張機能のパッケージ `<PFN>` ファミリ名で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf160-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span>  <span data-ttu-id="cf160-127">これは、Windows デベロッパー **センターの拡張機能** の [アプリ ID] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="cf160-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>  

## <a name="check-out-your-ratings-and-reviews"></a><span data-ttu-id="cf160-128">評価とレビューを確認する</span><span class="sxs-lookup"><span data-stu-id="cf160-128">Check out your ratings and reviews</span></span>  

<span data-ttu-id="cf160-129">定期的にログインして、ユーザーのレビューと評価を確認します。</span><span class="sxs-lookup"><span data-stu-id="cf160-129">Log in regularly to check your user reviews and ratings.</span></span>  <span data-ttu-id="cf160-130">UWP アプリには現在のユーザー 市場に関する情報しか表示されませんが、Windows デベロッパー センターにログインすると、すべての市場で平均評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf160-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>  

## <a name="respond-to-user-reviews"></a><span data-ttu-id="cf160-131">ユーザー レビューに応答する</span><span class="sxs-lookup"><span data-stu-id="cf160-131">Respond to user reviews</span></span>  

<span data-ttu-id="cf160-132">Windows デベロッパー センターのダッシュボードを使用して、Microsoft ストアのユーザー レビューに応答できます。</span><span class="sxs-lookup"><span data-stu-id="cf160-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span>  <span data-ttu-id="cf160-133">拡張機能に移動し、[分析] で [レビュー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf160-133">Navigate to your extension and under Analytics select **Reviews**.</span></span>  <span data-ttu-id="cf160-134">各レビューの下に、顧客に直接対応できるリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf160-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span>  <span data-ttu-id="cf160-135">このコミュニケーション チャネルを使用すると、フィードバック、解決策を提供したり、レビューに対して感謝のメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="cf160-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>  

![ユーザー レビューに応答する](./media/reviews.png)  
