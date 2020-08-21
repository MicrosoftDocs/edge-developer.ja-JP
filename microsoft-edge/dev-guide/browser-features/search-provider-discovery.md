---
ms.assetid: f74760f5-061c-494d-b096-9fb6ecb71a16
description: 検索プロバイダーの場合、Microsoft Edge がサービスをサポートしていることを確認する方法をご覧ください。
title: 検索プロバイダーの検出 - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 4ac8ea966e9c4736834a0be1130a8c2a8dfb2614
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941968"
---
# <span data-ttu-id="6569d-104">検索プロバイダーの検出</span><span class="sxs-lookup"><span data-stu-id="6569d-104">Search provider discovery</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="6569d-105">高度な検索統合は、検索候補、Web からの結果、閲覧履歴、お気に入りなど、Microsoft Edge アドレス バーに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="6569d-105">Rich search integration is built into the Microsoft Edge address bar, including search suggestions, results from the web, your browsing history, and favorites.</span></span>  <span data-ttu-id="6569d-106">Microsoft Edge は [、web OpenSearch 1.1 の指定](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って Web 検索プロバイダーを見つけ、使用します。</span><span class="sxs-lookup"><span data-stu-id="6569d-106">Microsoft Edge follows the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification to discover and use web search providers.</span></span>  <span data-ttu-id="6569d-107">検索プロバイダーを検索プロバイダーの場合、Microsoft Edge がサービスをサポートしているかどうかを確認する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6569d-107">If you are a search provider, here's how to ensure that Microsoft Edge supports your service.</span></span>  

> <span data-ttu-id="6569d-108">[重要]ユーザーセキュリティとプライバシーのために Microsoft Edge では、すべての検索を SSL を使用して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6569d-108">[IMPORTANT] For user security and privacy, Microsoft Edge requires all searches be conducted over SSL.</span></span>  

<span data-ttu-id="6569d-109">次のリソースは、検索エンジンの Microsoft Edge 統合を有効にするには、次 `https` のリソースを、URL として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6569d-109">The following resources must be specified as `https` URLs to enable Microsoft Edge integration of your search engine:</span></span>  

*   <span data-ttu-id="6569d-110">説明ドキュメントへの参照を含むサイト</span><span class="sxs-lookup"><span data-stu-id="6569d-110">The site that contains the reference to the description document</span></span>  
*   <span data-ttu-id="6569d-111">説明文書自体の URL</span><span class="sxs-lookup"><span data-stu-id="6569d-111">The URL to the description document itself</span></span>  
*   <span data-ttu-id="6569d-112">検索クエリ テンプレート</span><span class="sxs-lookup"><span data-stu-id="6569d-112">The search query template</span></span>  

1.  <span data-ttu-id="6569d-113">検索プロバイダー OpenSearchの名前と検索を構構造するテンプレートを含む、説明ファイルを入力します。</span><span class="sxs-lookup"><span data-stu-id="6569d-113">Provide an OpenSearch description file, which contains the name of the search provider, and the template to use to construct the search.</span></span>  <span data-ttu-id="6569d-114">ドキュメントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6569d-114">Here is an example document:</span></span>  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  <span data-ttu-id="6569d-115">次のように、ページのヘッダー セクションに OpenSearch の説明ファイルへの参照を含めます (通常、これには、次のようにサイトのホーム ページと検索結果ページが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="6569d-115">Include a reference to your OpenSearch description file in the header section of your pages (typically this would include your site home page and search result pages), for example:</span></span>  
    
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
    
<span data-ttu-id="6569d-116">ユーザーが検索サービスにアクセスすると、後で使用できるように、OpenSearch説明が自動的に選択され保存されます。</span><span class="sxs-lookup"><span data-stu-id="6569d-116">When a user browses to your search service, your OpenSearch description will be automatically picked up and saved for later use.</span></span>  <span data-ttu-id="6569d-117">ユーザーは Microsoft Edge の設定に移動し、検索サービスを Microsoft Edge アドレス バーの検索プロバイダーの一覧に追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6569d-117">The user will then be able to go to Microsoft Edge settings and choose to add your search service to his or her list of search providers for the Microsoft Edge address bar.</span></span>  

<span data-ttu-id="6569d-118">詳細については [、OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) の固 OpenSearch定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6569d-118">See the [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) specification for further details on creating your OpenSearch description document.</span></span>  
