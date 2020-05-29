---
description: Microsoft Edge extensions を開発する方法について説明します。 これらの小さいプログラムを使って、Microsoft Edge に新しい機能を追加したり、既存の機能を変更したりできます。
title: 拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
ms.technology: extensions
keywords: edge、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: 4cc47ba9d927caf7457141f5c8c7eacbb9627b07
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569437"
---
# <span data-ttu-id="2d755-105">Microsoft Edge (EdgeHTML) の拡張機能</span><span class="sxs-lookup"><span data-stu-id="2d755-105">Microsoft Edge (EdgeHTML) extensions</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="2d755-106">拡張機能は、Microsoft Edge (EdgeHTML) に新しい機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。</span><span class="sxs-lookup"><span data-stu-id="2d755-106">Extensions are small programs that can be used to add new features to Microsoft Edge (EdgeHTML) or modify the existing functionality.</span></span> <span data-ttu-id="2d755-107">拡張子は、対象ユーザーにとって重要なニッチ機能を提供することによって、ユーザーの日常的なブラウジングエクスペリエンスを向上させることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="2d755-107">Extensions are intended to improve a user’s day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>

<span data-ttu-id="2d755-108">Microsoft Edge (EdgeHTML) では、新しい HTML、JavaScript、CSS ベースの拡張モデルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d755-108">Microsoft Edge (EdgeHTML) supports a new HTML, JavaScript and CSS based extension model.</span></span> <span data-ttu-id="2d755-109">この新しいモデルは Chrome に対応しています。これは、既存の Chrome 拡張開発者が、最小限の変更で Microsoft Edge (EdgeHTML) に拡張機能を移行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d755-109">This new model is Chrome-compatible which means that existing Chrome extension developers will be able to migrate their extensions to Microsoft Edge (EdgeHTML) with minimal changes.</span></span>

<span data-ttu-id="2d755-110">開発から公開までの Microsoft Edge (EdgeHTML) 拡張機能の作成の最終終了の過程の概要については、「はじめに[」ガイド](./getting-started.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d755-110">To get an overview of the end to end journey of creating a Microsoft Edge (EdgeHTML) extension from development to publishing, check out the [Getting started guide](./getting-started.md)!</span></span>


## <span data-ttu-id="2d755-111">人気の記事</span><span class="sxs-lookup"><span data-stu-id="2d755-111">Popular articles</span></span>

<table>
  <tr>
    <td><a href = "./api-support/extension-api-roadmap.md"><span data-ttu-id="2d755-112">拡張 API のロードマップ</span><span class="sxs-lookup"><span data-stu-id="2d755-112">Extension API roadmap</span></span></a></td>
    <td><span data-ttu-id="2d755-113">サポートされている Api、Windows 10 Insider Preview および一般リリース版の Microsoft Edge のビルドでの Api について確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d755-113">Check out what APIs are supported/in development for Windows 10 Insider Preview and publicly released builds of Microsoft Edge.</span></span></td></p>
<p>  </tr>
  <tr>
    <td><a href = "./api-support/supported-apis.md"><span data-ttu-id="2d755-114">サポートされる Api</span><span class="sxs-lookup"><span data-stu-id="2d755-114">Supported APIs</span></span></a></td>
    <td><span data-ttu-id="2d755-115">既知の問題や Chrome の非互換性など、サポートされている Api に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2d755-115">Get info on our supported APIs including known issues and Chrome incompatibilities.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/creating-an-extension.md"><span data-ttu-id="2d755-116">内線番号を作成する</span><span class="sxs-lookup"><span data-stu-id="2d755-116">Creating an extension</span></span></a></td>
    <td><span data-ttu-id="2d755-117">拡張開発の世界の新機能</span><span class="sxs-lookup"><span data-stu-id="2d755-117">New to the world of extension development?</span></span> <span data-ttu-id="2d755-118">操作速度を向上させるために、いくつかのチュートリアルを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="2d755-118">Try out some tutorials to get up to speed.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/packaging.md"><span data-ttu-id="2d755-119">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="2d755-119">Packaging</span></span></a></td>
    <td><span data-ttu-id="2d755-120">開発を完了した後&#39;、延長をパッケージ化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d755-120">Learn how to package up your extension after you&#39;ve finished development.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/porting-chrome-extensions.md"><span data-ttu-id="2d755-121">Chrome 拡張機能の移植</span><span class="sxs-lookup"><span data-stu-id="2d755-121">Porting Chrome extensions</span></span></a></td>
    <td><span data-ttu-id="2d755-122">Microsoft Edge に表示されるように、d&#39;の Chrome 拡張機能を作成しましたか?</span><span class="sxs-lookup"><span data-stu-id="2d755-122">Created a Chrome extension you&#39;d like to see on Microsoft Edge?</span></span> <span data-ttu-id="2d755-123">Microsoft Edge 拡張機能キットを使用してポートに移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d755-123">See how to port it with the Microsoft Edge Extension Toolkit.</span></span></td>

  </tr>
</table>
