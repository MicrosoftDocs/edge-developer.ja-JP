---
description: Microsoft Edge 拡張機能に関する便利なヒントとコツについて説明します。
title: ヒントとコツ |拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, 拡張機能
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd512085f13b76c5a8e474301ef296612eeb0414
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234572"
---
# <span data-ttu-id="c4ba8-104">ヒントとテクニック</span><span class="sxs-lookup"><span data-stu-id="c4ba8-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="c4ba8-105">Microsoft Edge 拡張機能を現在使用している場合でも、既に公開している場合でも、次のヒントやコツが役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>

## <span data-ttu-id="c4ba8-106">Microsoft Store で拡張機能への直接リンクを取得する</span><span class="sxs-lookup"><span data-stu-id="c4ba8-106">Get a direct link to your extension in the Microsoft Store</span></span>

<span data-ttu-id="c4ba8-107">Windows デベロッパー センター ダッシュボードでは、Microsoft Store で拡張機能への直接リンクを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span> <span data-ttu-id="c4ba8-108">このリンクは、拡張機能を宣伝して共有する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-108">This link can be useful for advertising and sharing out your extension.</span></span>

<span data-ttu-id="c4ba8-109">Windows デベロッパー センターにログインし、ダッシュボードから拡張機能に移動すると、アプリ ID ページの [ストア プロトコル] リンク行にリンクが **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>

![ストア プロトコル リンク](./media/store-link.png)
 
## <span data-ttu-id="c4ba8-111">Microsoft Store ポリシーに従っている必要があります</span><span class="sxs-lookup"><span data-stu-id="c4ba8-111">Make sure you’re following the Microsoft Store Policy</span></span>

<span data-ttu-id="c4ba8-112">拡張機能を作成する場合は [、Microsoft Store](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)ポリシーで強調表示されている Microsoft Store に提出するためのガイドラインに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span></span> 
 
<span data-ttu-id="c4ba8-113">Microsoft Edge 拡張機能には、ここに示すポリシーの追加セットも用意 [されています](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span></span>

## <span data-ttu-id="c4ba8-114">Microsoft Store での拡張機能の検出可能性を向上させる</span><span class="sxs-lookup"><span data-stu-id="c4ba8-114">Improve your extension’s discoverability in the Microsoft Store</span></span>

<span data-ttu-id="c4ba8-115">拡張機能の申請にキーワードを追加して、検索を通じて検出可能性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-115">You can add keywords to your extension submission to improve its discoverability through searches.</span></span> <span data-ttu-id="c4ba8-116">たとえば、"Microsoft Edge Extensions" や "name of my extension" などです。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span></span> 

<span data-ttu-id="c4ba8-117">これは、拡張機能の説明セクションの下の Windows デベロッパー センターで行います。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span> <span data-ttu-id="c4ba8-118">これらのキーワードは、拡張機能がサポートする言語ごとに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-118">These keywords will need to be added for every language your extension supports.</span></span>

![レビューへの応答の送信 - キーワード](./media/keywords.png)

## <span data-ttu-id="c4ba8-120">Microsoft Store への申請を自動化する</span><span class="sxs-lookup"><span data-stu-id="c4ba8-120">Automate your submission to the Microsoft Store</span></span>

<span data-ttu-id="c4ba8-121">新しい Microsoft Store 申請 API を使うと、アプリ/ゲーム、アドオン (アプリ内購入)、パッケージ フライトを REST API を通じて更新できます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span></span> <span data-ttu-id="c4ba8-122">ドキュメントとサンプル [を確認するか、](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) オープン ソース [の申請 API VSTS](https://github.com/Microsoft/windows-dev-center-vsts-extension) 拡張機能を使用して開始してください。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>

## <span data-ttu-id="c4ba8-123">Windows フィードバック Hub を使用して、フィードバック/レビュー/機能の要求を収集する</span><span class="sxs-lookup"><span data-stu-id="c4ba8-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>

<span data-ttu-id="c4ba8-124">ユーザーに Windows フィードバック Hub サブカテゴリへのリンクを埋め込むには、そのリンクを埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span> <span data-ttu-id="c4ba8-125">このリンクは、次の形式で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-125">This link will need to be created using the following format:</span></span> 

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

<span data-ttu-id="c4ba8-126">拡張機能のパッケージ `<PFN>` ファミリ名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span> <span data-ttu-id="c4ba8-127">これは、Windows デベロッパー **センターの拡張機能** の [アプリ ID] セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>

## <span data-ttu-id="c4ba8-128">評価とレビューを確認する</span><span class="sxs-lookup"><span data-stu-id="c4ba8-128">Check out your ratings and reviews</span></span>

<span data-ttu-id="c4ba8-129">定期的にログインして、ユーザーのレビューと評価を確認します。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-129">Log in regularly to check your user reviews and ratings.</span></span> <span data-ttu-id="c4ba8-130">UWP アプリには現在のユーザー市場に関する情報しか表示されませんが、Windows デベロッパー センターにログインすると、すべての市場の平均評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>

## <span data-ttu-id="c4ba8-131">ユーザー レビューに応答する</span><span class="sxs-lookup"><span data-stu-id="c4ba8-131">Respond to user reviews</span></span>

<span data-ttu-id="c4ba8-132">Windows デベロッパー センターのダッシュボードから Microsoft Store のユーザー レビューに応答できます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span> <span data-ttu-id="c4ba8-133">拡張機能に移動し、[分析] で [レビュー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-133">Navigate to your extension and under Analytics select **Reviews**.</span></span> <span data-ttu-id="c4ba8-134">各レビューの下にリンクが表示され、顧客に直接回答できます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span> <span data-ttu-id="c4ba8-135">このコミュニケーション チャネルを使用すると、フィードバックや解決策を提供したり、レビューに感謝のメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="c4ba8-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>

![レビューへの応答の送信](./media/reviews.png)
