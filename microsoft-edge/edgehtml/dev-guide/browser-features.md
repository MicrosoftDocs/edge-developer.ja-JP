---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge のブラウザー機能のガイドです。
title: ブラウザー - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2579fad881496e2197f9f696bb2c12c47c7f723e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234891"
---
# <span data-ttu-id="6b945-104">ブラウザーの機能</span><span class="sxs-lookup"><span data-stu-id="6b945-104">Browser features</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## <span data-ttu-id="6b945-105">自動再生のポリシー</span><span class="sxs-lookup"><span data-stu-id="6b945-105">Autoplay policies</span></span>  

 <span data-ttu-id="6b945-106">Microsoft Edge は、Web 上の注意をそらす操作を最小限に抑え、帯域幅を節約するために、音声でメディアを自動再生する Web サイトの閲覧設定をカスタマイズする機能をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="6b945-106">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="6b945-107">ユーザーは、グローバル自動再生コントロールとサイトごとの自動再生コントロールの両方でメディアの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6b945-107">Users can customize media behavior with both global and per-site autoplay controls.</span></span>  <span data-ttu-id="6b945-108">さらに、Microsoft Edge では、バックグラウンド タブでのメディアの自動再生が自動的に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="6b945-108">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="6b945-109">サイトで [ホストされているメディアのユーザー](./browser-features/autoplay-policies.md) エクスペリエンスを向上するために、詳細とベスト プラクティスについては、自動再生ポリシーをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b945-109">Check out [Autoplay policies](./browser-features/autoplay-policies.md) for details and best practices to ensure a good user experience with media hosted on your site.</span></span>  

## <span data-ttu-id="6b945-110">Flash</span><span class="sxs-lookup"><span data-stu-id="6b945-110">Flash</span></span>  

<span data-ttu-id="6b945-111">Flash がページで使用されているが、ユーザーが有効にしていない場合、Microsoft Edge は通常、アドレス バーにパズルの一部のアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b945-111">If Flash is used on your page but the user has not enabled it, Microsoft Edge will normally show a puzzle piece icon in the address bar.</span></span>  <span data-ttu-id="6b945-112">ページの読み込み後に Flash コントロールを動的に追加する場合は、パズル アイコンが表示されない可能性があります。この場合は [、Flash](./browser-features/flash.md) が読み込まれているかテストし、存在しない場合は適切なフォールバック エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b945-112">If you are dynamically adding the Flash control after the page is loaded, the puzzle icon may not display, in which case you'll want to [test if Flash is loaded and provide a graceful fallback experience](./browser-features/flash.md) if its not present.</span></span>  

## <span data-ttu-id="6b945-113">読み取りビュー</span><span class="sxs-lookup"><span data-stu-id="6b945-113">Reading view</span></span>  

<span data-ttu-id="6b945-114">Microsoft Edge[](./browser-features/reading-view.md)は、ページ上の無関係なコンテンツや他のセカンダリ コンテンツを気を散らさずに、より合理化された書籍のような Web ページの閲覧エクスペリエンスのための閲覧ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b945-114">Microsoft Edge provides a [reading view](./browser-features/reading-view.md) for a more streamlined, book-like reading experience of webpages, without the distraction of unrelated or other secondary content on the page.</span></span>  <span data-ttu-id="6b945-115">ここでは、サイトの閲覧表示エクスペリエンスを向上する方法に関するヒントと、サイトを閲覧ビューからオプトアウトするための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="6b945-115">Here are tips on how to ensure a great reading view experience with your site and also instructions for opting your site out of reading view.</span></span>  

## <span data-ttu-id="6b945-116">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="6b945-116">Search provider discovery</span></span>  

<span data-ttu-id="6b945-117">リッチ検索の統合は、Microsoft Edge アドレス バーに組み込み、検索候補、Web からの結果、閲覧履歴、お気に入りを含む。</span><span class="sxs-lookup"><span data-stu-id="6b945-117">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="6b945-118">Microsoft Edge[のサポートを提供する](./browser-features/search-provider-discovery.md)検索プロバイダーについて詳しくは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b945-118">[Here's more info for search providers](./browser-features/search-provider-discovery.md) looking to provide support for Microsoft Edge.</span></span>  
