---
description: Microsoft Edge 拡張機能を開発する方法について説明します。 これらの小規模なプログラムは、Microsoft Edge に新機能を追加したり、既存の機能を変更したりするために使用できます。
title: 拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: extensions
keywords: edge, Web 開発, html, css, javascript, 開発者, 拡張機能
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cc54e3512cf315183ce8baa59abde3db568d1828
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234914"
---
# <span data-ttu-id="ae74d-105">Microsoft Edge (EdgeHTML) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="ae74d-105">Microsoft Edge (EdgeHTML) extensions</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="ae74d-106">拡張機能は、Microsoft Edge (EdgeHTML) に新機能を追加したり、既存の機能を変更したりするために使用できる小規模なプログラムです。</span><span class="sxs-lookup"><span data-stu-id="ae74d-106">Extensions are small programs that can be used to add new features to Microsoft Edge (EdgeHTML) or modify the existing functionality.</span></span> <span data-ttu-id="ae74d-107">拡張機能は、対象ユーザーにとって重要な最適な機能を提供することで、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="ae74d-107">Extensions are intended to improve a user’s day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>

<span data-ttu-id="ae74d-108">Microsoft Edge (EdgeHTML) は、新しい HTML、JavaScript、および CSS ベースの拡張機能モデルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ae74d-108">Microsoft Edge (EdgeHTML) supports a new HTML, JavaScript and CSS based extension model.</span></span> <span data-ttu-id="ae74d-109">この新しいモデルは Chrome 互換です。つまり、既存の Chrome 拡張機能の開発者は、最小限の変更で拡張機能を Microsoft Edge (EdgeHTML) に移行できます。</span><span class="sxs-lookup"><span data-stu-id="ae74d-109">This new model is Chrome-compatible which means that existing Chrome extension developers will be able to migrate their extensions to Microsoft Edge (EdgeHTML) with minimal changes.</span></span>

<span data-ttu-id="ae74d-110">Microsoft Edge (EdgeHTML) 拡張機能を開発から公開まで作成するためのエンドツーエンドの手順の概要については、概要ガイド [をご覧ください](./getting-started.md)。</span><span class="sxs-lookup"><span data-stu-id="ae74d-110">To get an overview of the end to end journey of creating a Microsoft Edge (EdgeHTML) extension from development to publishing, check out the [Getting started guide](./getting-started.md)!</span></span>


## <span data-ttu-id="ae74d-111">人気のある記事</span><span class="sxs-lookup"><span data-stu-id="ae74d-111">Popular articles</span></span>

<table>
  <tr>
    <td><a href = "./api-support/extension-api-roadmap.md"><span data-ttu-id="ae74d-112">拡張 API のロードマップ</span><span class="sxs-lookup"><span data-stu-id="ae74d-112">Extension API roadmap</span></span></a></td>
    <td><span data-ttu-id="ae74d-113">Windows 10 Insider Preview および Microsoft Edge の一般にリリースされたビルドでサポートされている API や開発中の API をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ae74d-113">Check out what APIs are supported/in development for Windows 10 Insider Preview and publicly released builds of Microsoft Edge.</span></span></td></p>
<p>  </tr>
  <tr>
    <td><a href = "./api-support/supported-apis.md"><span data-ttu-id="ae74d-114">サポートされる API</span><span class="sxs-lookup"><span data-stu-id="ae74d-114">Supported APIs</span></span></a></td>
    <td><span data-ttu-id="ae74d-115">既知の問題や Chrome の非互換性など、サポートされている API に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae74d-115">Get info on our supported APIs including known issues and Chrome incompatibilities.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/creating-an-extension.md"><span data-ttu-id="ae74d-116">拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="ae74d-116">Creating an extension</span></span></a></td>
    <td><span data-ttu-id="ae74d-117">拡張機能の開発の世界は新しいですか?</span><span class="sxs-lookup"><span data-stu-id="ae74d-117">New to the world of extension development?</span></span> <span data-ttu-id="ae74d-118">いくつかのチュートリアルを試して、速度を上げしてみてください。</span><span class="sxs-lookup"><span data-stu-id="ae74d-118">Try out some tutorials to get up to speed.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/packaging.md"><span data-ttu-id="ae74d-119">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="ae74d-119">Packaging</span></span></a></td>
    <td><span data-ttu-id="ae74d-120">開発が完了したら、拡張機能をパッケージ化&#39;方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae74d-120">Learn how to package up your extension after you&#39;ve finished development.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/porting-chrome-extensions.md"><span data-ttu-id="ae74d-121">Chrome 拡張機能の移植</span><span class="sxs-lookup"><span data-stu-id="ae74d-121">Porting Chrome extensions</span></span></a></td>
    <td><span data-ttu-id="ae74d-122">Microsoft Edge で表示&#39;Chrome 拡張機能を作成しましたか?</span><span class="sxs-lookup"><span data-stu-id="ae74d-122">Created a Chrome extension you&#39;d like to see on Microsoft Edge?</span></span> <span data-ttu-id="ae74d-123">Microsoft Edge Extension Toolkit で移植する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae74d-123">See how to port it with the Microsoft Edge Extension Toolkit.</span></span></td>

  </tr>
</table>
