---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 検索プロバイダーの場合は、Microsoft Edge がサービスをサポートする方法を参照してください。
title: 検索プロバイダーの検出 - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb21182e910cb91658dd4fb204f7f7783843f447
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235017"
---
# <span data-ttu-id="7f471-104">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="7f471-104">Search provider discovery</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="7f471-105">リッチ検索の統合は、Microsoft Edge アドレス バーに組み込み、検索候補、Web からの結果、閲覧履歴、お気に入りを含む。</span><span class="sxs-lookup"><span data-stu-id="7f471-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="7f471-106">Microsoft Edge は、OpenSearch [1.1 仕様](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って、Web 検索プロバイダーを検出して使用します。</span><span class="sxs-lookup"><span data-stu-id="7f471-106">Microsoft Edge follows the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification to discover and use web search providers.</span></span>  <span data-ttu-id="7f471-107">検索プロバイダーの場合は、Microsoft Edge がサービスをサポートする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7f471-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="7f471-108">ユーザーのセキュリティとプライバシーのために、Microsoft Edge では SSL を使用してすべての検索を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f471-108">For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>  

<span data-ttu-id="7f471-109">検索エンジンの Microsoft Edge 統合を `https` 有効にするには、次のリソースを URL として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f471-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>  

*   <span data-ttu-id="7f471-110">説明ドキュメントへの参照を含むサイト</span><span class="sxs-lookup"><span data-stu-id="7f471-110">The site that contains the reference to the description document</span></span>  
*   <span data-ttu-id="7f471-111">説明ドキュメント自体の URL</span><span class="sxs-lookup"><span data-stu-id="7f471-111">The URL to the description document itself</span></span>  
*   <span data-ttu-id="7f471-112">検索クエリ テンプレート</span><span class="sxs-lookup"><span data-stu-id="7f471-112">The search query template</span></span>  
    
1.  <span data-ttu-id="7f471-113">検索プロバイダー OpenSearchを含む新しい説明ファイルと、検索の構築に使用するテンプレートを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f471-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span>  <span data-ttu-id="7f471-114">ドキュメントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7f471-114">Here is an example document:</span></span>  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  <span data-ttu-id="7f471-115">ページのヘッダー セクションに OpenSearch 記述ファイルへの参照を含める (通常、サイトのホーム ページと検索結果ページが含まれます)。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f471-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>  
    
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
    
<span data-ttu-id="7f471-116">ユーザーが検索サービスにアクセスすると、検索OpenSearch説明が自動的に選択され、後で使用するために保存されます。</span><span class="sxs-lookup"><span data-stu-id="7f471-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span>  <span data-ttu-id="7f471-117">その後、ユーザーは Microsoft Edge の設定に移動し、Microsoft Edge アドレス バーの検索プロバイダーの一覧に検索サービスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7f471-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>  

<span data-ttu-id="7f471-118">詳細については [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) の仕様を参照してください。詳しくは、OpenSearch説明ドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f471-118">See the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification for further details on creating your OpenSearch description document.</span></span>  
