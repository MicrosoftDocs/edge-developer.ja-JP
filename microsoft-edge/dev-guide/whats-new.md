---
description: このページでは、開発者向けの EdgeHTML プレビュー ビルドの新機能の概要を示します。
title: 開発者向け EdgeHTML の新機能 - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Edge、Web 開発、html、cs、javascript、開発者、Edge、Edgehtml の新しい API、Edgehtml、Edgehtml プレビュー ビルド
ms.openlocfilehash: 81973d12f6e66b5e6f1c3cd6a12fee196c4495d7
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941961"
---
# <span data-ttu-id="8b595-104">EdgeHTML の新着情報</span><span class="sxs-lookup"><span data-stu-id="8b595-104">What's new in EdgeHTML</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="8b595-105">Windows Insider になることで、最新の EdgeHTML の機能と API を [取得します](https://insider.windows.com)。</span><span class="sxs-lookup"><span data-stu-id="8b595-105">Get the latest EdgeHTML features and APIs by becoming a [Windows Insider](https://insider.windows.com)!</span></span>  <span data-ttu-id="8b595-106">[Windows Insider Program には](https://insider.windows.com)、提供されたらす次に、最新の Windows 10 ビルドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8b595-106">The [Windows Insider Program](https://insider.windows.com) provides the latest Windows 10 builds as soon as they're available.</span></span>  

<span data-ttu-id="8b595-107">Microsoft Edge プラットフォーム [の](../dev-guide.md) 現在のリリースで出荷された新機能と API を開発ガイドに進み、Microsoft Edge プラットフォーム、EdgeHTML 18 \(ビルド 17763\) に出荷された API を確認します。</span><span class="sxs-lookup"><span data-stu-id="8b595-107">Head over to the [Dev Guide](../dev-guide.md) to see the new features and APIs shipped in the current release of the Microsoft Edge platform, EdgeHTML 18 \(Build 17763\).</span></span>  

<span data-ttu-id="8b595-108">以下は、Windows 10 Preview ビルドの新しい EdgeHTML API を提供して更新します。</span><span class="sxs-lookup"><span data-stu-id="8b595-108">Below are new and updated EdgeHTML APIs in Windows 10 Preview Builds.</span></span> <span data-ttu-id="8b595-109">これらは形式で表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="8b595-109">They are listed in the format of `[interface name].[api name]`.</span></span>  <span data-ttu-id="8b595-110">Microsoft Edge およびプラットフォームの新機能の完全な一覧[Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog)については、変更ログまたは[デ](../dev-guide.md)ベロッパー ガイドに進み、Microsoft Edge プラットフォーム、EdgeHTML 18 の現在の中止済みリリースで API に出荷された API を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8b595-110">For a full list of new Microsoft Edge and platform features, check out [Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) or head over to the [Dev Guide](../dev-guide.md) to see new features and APIs shipped in the current stable release of the Microsoft Edge platform, EdgeHTML 18.</span></span>   

> [!WARNING] 
> <span data-ttu-id="8b595-111">一部の情報は、商用版のリリース前に大分に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b595-111">Some information relates to pre-released product which may be substantially modified before it's commercially released.</span></span>  <span data-ttu-id="8b595-112">ここに記載された情報について、Microsoft は明示または黙示を問わずいかなる保証をするものでもありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>  

## <span data-ttu-id="8b595-113">プレビュー ビルド 18272</span><span class="sxs-lookup"><span data-stu-id="8b595-113">Preview Build 18272</span></span>  

<span data-ttu-id="8b595-114">API が変更される必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-114">No API changes.</span></span>  

## <span data-ttu-id="8b595-115">プレビュー ビルド 18267</span><span class="sxs-lookup"><span data-stu-id="8b595-115">Preview Build 18267</span></span>  

<span data-ttu-id="8b595-116">API が変更される必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-116">No API changes.</span></span>  

## <span data-ttu-id="8b595-117">プレビュー ビルド 18262</span><span class="sxs-lookup"><span data-stu-id="8b595-117">Preview Build 18262</span></span>  

<span data-ttu-id="8b595-118">新しい API のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8b595-118">Added new API support:</span></span>  

<iframe height='341' scrolling='no' title='<span data-ttu-id="8b595-119">EdgeHTML Preview ビルド 17682</span><span class="sxs-lookup"><span data-stu-id="8b595-119">EdgeHTML Preview Build 17682</span></span>' src='//codepen.io/MSEdgeDev/embed/5a691c1840690352f409d3788b8167fa/?height=341&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="8b595-120">CodePen で Pen <a href='https://codepen.io/MSEdgeDev/pen/5a691c1840690352f409d3788b8167fa/'> EdgeHTML Preview ビルド 17682 </a> by MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev) を <a href='https://codepen.io'> 参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8b595-120">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/5a691c1840690352f409d3788b8167fa/'>EdgeHTML Preview Build 17682</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span>  </iframe>  

## <span data-ttu-id="8b595-121">プレビュー ビルド 18252</span><span class="sxs-lookup"><span data-stu-id="8b595-121">Preview Build 18252</span></span>  

<span data-ttu-id="8b595-122">API が変更される必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-122">No API changes.</span></span>  

## <span data-ttu-id="8b595-123">プレビュー ビルド 18247</span><span class="sxs-lookup"><span data-stu-id="8b595-123">Preview Build 18247</span></span>  

<span data-ttu-id="8b595-124">API が変更される必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-124">No API changes.</span></span>  

## <span data-ttu-id="8b595-125">プレビュー ビルド 18242</span><span class="sxs-lookup"><span data-stu-id="8b595-125">Preview Build 18242</span></span>  

<span data-ttu-id="8b595-126">API が変更される必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b595-126">No API changes.</span></span>  
