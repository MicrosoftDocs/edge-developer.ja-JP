---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge のブラウザー機能のガイド。
title: 開発ガイド-ブラウザー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/28/2018
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: e7b13b18048e0a703ca5e2a0e5b52712f41c2101
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568838"
---
# <span data-ttu-id="71e3e-104">ブラウザーの機能</span><span class="sxs-lookup"><span data-stu-id="71e3e-104">Browser features</span></span>

## <span data-ttu-id="71e3e-105">自動再生ポリシー</span><span class="sxs-lookup"><span data-stu-id="71e3e-105">Autoplay policies</span></span>

 <span data-ttu-id="71e3e-106">Microsoft Edge では、web 上の集中を最小限に抑え、帯域幅を節約するために、メディアを自動再生する web サイトの閲覧の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="71e3e-106">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span> <span data-ttu-id="71e3e-107">ユーザーは、グローバルおよびサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="71e3e-107">Users can customize media behavior with both global and per-site autoplay controls.</span></span> <span data-ttu-id="71e3e-108">また、Microsoft Edge では、バックグラウンドタブでのメディアの自動再生が自動的に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="71e3e-108">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>

<span data-ttu-id="71e3e-109">サイトでホストされているメディアでユーザーエクスペリエンスを向上させるための詳細とベストプラクティスについては、[自動再生ポリシー](./browser-features/autoplay-policies.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="71e3e-109">Check out [Autoplay policies](./browser-features/autoplay-policies.md) for details and best practices to ensure a good user experience with media hosted on your site.</span></span>

## <span data-ttu-id="71e3e-110">フラッシュ</span><span class="sxs-lookup"><span data-stu-id="71e3e-110">Flash</span></span>
<span data-ttu-id="71e3e-111">ページで Flash が使用されていても、ユーザーが有効にしていない場合、Microsoft Edge では通常、アドレスバーにパズルのピースアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71e3e-111">If Flash is used on your page but the user has not enabled it, Microsoft Edge will normally show a puzzle piece icon in the address bar.</span></span> <span data-ttu-id="71e3e-112">ページの読み込み後にフラッシュコントロールを動的に追加している場合は、パズルアイコンが表示されないことがあります。この場合、 [flash が読み込まれているか](./browser-features/flash.md)どうかをテストし、存在しない場合は、正常なフォールバックエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="71e3e-112">If you are dynamically adding the Flash control after the page is loaded, the puzzle icon may not display, in which case you'll want to [test if Flash is loaded and provide a graceful fallback experience](./browser-features/flash.md) if its not present.</span></span>

## <span data-ttu-id="71e3e-113">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="71e3e-113">Reading view</span></span>
<span data-ttu-id="71e3e-114">Microsoft Edge では、ページ上の関連性のない、または他の二次的なコンテンツに煩わされることなく、web ページをより効率的に整理するための[閲覧表示](./browser-features/reading-view.md)が用意されています。</span><span class="sxs-lookup"><span data-stu-id="71e3e-114">Microsoft Edge provides a [reading view](./browser-features/reading-view.md) for a more streamlined, book-like reading experience of webpages, without the distraction of unrelated or other secondary content on the page.</span></span> <span data-ttu-id="71e3e-115">ここでは、サイトで優れた読み取り操作エクスペリエンスを実現するためのヒントと、サイトを閲覧表示から除外する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71e3e-115">Here are tips on how to ensure a great reading view experience with your site and also instructions for opting your site out of reading view.</span></span>

## <span data-ttu-id="71e3e-116">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="71e3e-116">Search provider discovery</span></span>

<span data-ttu-id="71e3e-117">Microsoft Edge のアドレスバーには、検索候補、web の結果、閲覧履歴、お気に入りなど、リッチ検索の統合機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="71e3e-117">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span> <span data-ttu-id="71e3e-118">Microsoft Edge のサポートを提供する[検索プロバイダーの詳細については、こちら](./browser-features/search-provider-discovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71e3e-118">[Here's more info for search providers](./browser-features/search-provider-discovery.md) looking to provide support for Microsoft Edge.</span></span>
