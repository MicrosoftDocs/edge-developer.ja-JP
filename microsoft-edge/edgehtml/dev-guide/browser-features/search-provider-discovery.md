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
# 検索プロバイダーの検出  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

リッチ検索の統合は、Microsoft Edge アドレス バーに組み込み、検索候補、Web からの結果、閲覧履歴、お気に入りを含む。  Microsoft Edge は、OpenSearch [1.1 仕様](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って、Web 検索プロバイダーを検出して使用します。  検索プロバイダーの場合は、Microsoft Edge がサービスをサポートする方法を次に示します。  

> [!IMPORTANT]
> ユーザーのセキュリティとプライバシーのために、Microsoft Edge では SSL を使用してすべての検索を実行する必要があります。  

検索エンジンの Microsoft Edge 統合を `https` 有効にするには、次のリソースを URL として指定する必要があります。  

*   説明ドキュメントへの参照を含むサイト  
*   説明ドキュメント自体の URL  
*   検索クエリ テンプレート  
    
1.  検索プロバイダー OpenSearchを含む新しい説明ファイルと、検索の構築に使用するテンプレートを指定します。  ドキュメントの例を次に示します。  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  ページのヘッダー セクションに OpenSearch 記述ファイルへの参照を含める (通常、サイトのホーム ページと検索結果ページが含まれます)。次に例を示します。  
    
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
    
ユーザーが検索サービスにアクセスすると、検索OpenSearch説明が自動的に選択され、後で使用するために保存されます。  その後、ユーザーは Microsoft Edge の設定に移動し、Microsoft Edge アドレス バーの検索プロバイダーの一覧に検索サービスを追加できます。  

詳細については [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) の仕様を参照してください。詳しくは、OpenSearch説明ドキュメントをご覧ください。  
