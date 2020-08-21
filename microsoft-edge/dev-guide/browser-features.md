---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge のブラウザー機能のガイド。
title: ブラウザー - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 854b0e8ac057db3cc8b53af6205404d0841dfdb4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942043"
---
# <span data-ttu-id="40e27-104">ブラウザーの機能</span><span class="sxs-lookup"><span data-stu-id="40e27-104">Browser features</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## <span data-ttu-id="40e27-105">自動再生のポリシー</span><span class="sxs-lookup"><span data-stu-id="40e27-105">Autoplay policies</span></span>  

 <span data-ttu-id="40e27-106">Microsoft Edge では、Web 上での音が最小化され帯域幅を確実にすることをために、サウンドでメディアを自動再生する機能を提供するお客様は、Web サイトの閲覧設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="40e27-106">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="40e27-107">ユーザーは、グローバルかつサイト単位の自動再生コントロールの両方でメディアの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="40e27-107">Users can customize media behavior with both global and per-site autoplay controls.</span></span>  <span data-ttu-id="40e27-108">さらに、Microsoft Edge はバックグラウンド タブでメディアの自動再生を自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="40e27-108">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="40e27-109">サイトに [ホストされる](./browser-features/autoplay-policies.md) メディアを使用して、良いユーザー エクスペリエンスを確実に使用できるように、自動再生ポリシーをチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="40e27-109">Check out [Autoplay policies](./browser-features/autoplay-policies.md) for details and best practices to ensure a good user experience with media hosted on your site.</span></span>  

## <span data-ttu-id="40e27-110">Flash</span><span class="sxs-lookup"><span data-stu-id="40e27-110">Flash</span></span>  

<span data-ttu-id="40e27-111">ページで Flash を使用していて、ユーザーがフラッシュを有効にしていない場合、通常、Microsoft Edge ではアドレス バーに puzzle 円のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40e27-111">If Flash is used on your page but the user has not enabled it, Microsoft Edge will normally show a puzzle piece icon in the address bar.</span></span>  <span data-ttu-id="40e27-112">ページの読み込み後に Flash コントロールを動的に追加する場合、Puzzle アイコンが表示されない場合があります [。Flash](./browser-features/flash.md) が読み込んでいない場合はテストし、成績フォールバック エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="40e27-112">If you are dynamically adding the Flash control after the page is loaded, the puzzle icon may not display, in which case you'll want to [test if Flash is loaded and provide a graceful fallback experience](./browser-features/flash.md) if its not present.</span></span>  

## <span data-ttu-id="40e27-113">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="40e27-113">Reading view</span></span>  

<span data-ttu-id="40e27-114">Microsoft Edge では[reading view](./browser-features/reading-view.md)、Web ページの閲覧表示機能がさらに効率的で、ページ上の関連性のない他の第一コンテンツに気がつかることなく、より効率的で、より効率的に Web ページの閲覧表示機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="40e27-114">Microsoft Edge provides a [reading view](./browser-features/reading-view.md) for a more streamlined, book-like reading experience of webpages, without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="40e27-115">ここでは、サイトとの読みやすい閲覧表示機能を確かにする方法と、閲覧表示からサイトをオプトアウトする手順についても説明します。</span><span class="sxs-lookup"><span data-stu-id="40e27-115">Here are tips on how to ensure a great reading view experience with your site and also instructions for opting your site out of reading view.</span></span>  

## <span data-ttu-id="40e27-116">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="40e27-116">Search provider discovery</span></span>  

<span data-ttu-id="40e27-117">高度な検索統合は、検索候補、Web からの結果、閲覧履歴、お気に入りなど、Microsoft Edge アドレス バーに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="40e27-117">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="40e27-118">[Microsoft Edge のサポートを提供する検索](./browser-features/search-provider-discovery.md) プロバイダーの詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="40e27-118">[Here's more info for search providers](./browser-features/search-provider-discovery.md) looking to provide support for Microsoft Edge.</span></span>  
