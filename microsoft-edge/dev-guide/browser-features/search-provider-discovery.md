---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 検索プロバイダーの場合は、Microsoft Edge がサービスをサポートする方法に関する説明を参照してください。
title: 開発ガイド-検索プロバイダーの検出
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: ac23c2c62d436d5772b498208a56ad306eb8cb3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568832"
---
# <span data-ttu-id="4fc7c-104">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="4fc7c-104">Search provider discovery</span></span>


<span data-ttu-id="4fc7c-105">Microsoft Edge のアドレスバーには、検索候補、web の結果、閲覧履歴、お気に入りなど、リッチ検索の統合機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span> <span data-ttu-id="4fc7c-106">Microsoft Edge は、 [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)仕様に従って、web 検索プロバイダーを検出して使用します。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-106">Microsoft Edge follows the [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582) specification to discover and use web search providers.</span></span> <span data-ttu-id="4fc7c-107">検索プロバイダーの場合は、Microsoft Edge がサービスをサポートするようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>

**<span data-ttu-id="4fc7c-108">Microsoft Edge では、ユーザーのセキュリティとプライバシーを保護するために、すべての検索を SSL 経由で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-108">For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>** <span data-ttu-id="4fc7c-109">`https`検索エンジンの Microsoft Edge 統合を有効にするには、次のリソースを url として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>
* <span data-ttu-id="4fc7c-110">説明ドキュメントへの参照が含まれているサイト</span><span class="sxs-lookup"><span data-stu-id="4fc7c-110">The site that contains the reference to the description document</span></span>
* <span data-ttu-id="4fc7c-111">説明ドキュメント自体の URL</span><span class="sxs-lookup"><span data-stu-id="4fc7c-111">The URL to the description document itself</span></span>
* <span data-ttu-id="4fc7c-112">検索クエリテンプレート</span><span class="sxs-lookup"><span data-stu-id="4fc7c-112">The search query template</span></span> 

1.  <span data-ttu-id="4fc7c-113">検索プロバイダーの名前と検索の構築に使うテンプレートを含む、OpenSearch description ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span> <span data-ttu-id="4fc7c-114">ドキュメントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-114">Here is an example document:</span></span>

    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```

2.  <span data-ttu-id="4fc7c-115">ページのヘッダーセクションに OpenSearch description ファイルへの参照を追加します (通常は、次のように、サイトのホームページと検索結果ページが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>

    ```html
    <html>
        <head>
            <link rel="search" 
                type="application/opensearchdescription+xml"  
                href="https://contoso.com/content-search.xml" 
                title="Contoso search" /> 
        </head> 
        <body> 
        ...
    ```

<span data-ttu-id="4fc7c-116">ユーザーが検索サービスを参照すると、OpenSearch 説明が自動的に取得されて、後で使用できるように保存されます。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span> <span data-ttu-id="4fc7c-117">その後、ユーザーは Microsoft Edge の [設定] に移動して、Microsoft Edge アドレスバーの検索プロバイダーのリストに検索サービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>

<span data-ttu-id="4fc7c-118">OpenSearch description ドキュメントの作成について詳しくは、 [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)の仕様をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4fc7c-118">See the [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582) specification for further details on creating your OpenSearch description document.</span></span>
