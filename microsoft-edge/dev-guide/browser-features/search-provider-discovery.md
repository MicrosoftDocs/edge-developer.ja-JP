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
# 検索プロバイダーの検出  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

高度な検索統合は、検索候補、Web からの結果、閲覧履歴、お気に入りなど、Microsoft Edge アドレス バーに組み込まれています。  Microsoft Edge は [、web OpenSearch 1.1 の指定](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) に従って Web 検索プロバイダーを見つけ、使用します。  検索プロバイダーを検索プロバイダーの場合、Microsoft Edge がサービスをサポートしているかどうかを確認する方法は次のとおりです。  

> [重要]ユーザーセキュリティとプライバシーのために Microsoft Edge では、すべての検索を SSL を使用して行う必要があります。  

次のリソースは、検索エンジンの Microsoft Edge 統合を有効にするには、次 `https` のリソースを、URL として指定する必要があります。  

*   説明ドキュメントへの参照を含むサイト  
*   説明文書自体の URL  
*   検索クエリ テンプレート  

1.  検索プロバイダー OpenSearchの名前と検索を構構造するテンプレートを含む、説明ファイルを入力します。  ドキュメントの例を次に示します。  
    
    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```  
    
1.  次のように、ページのヘッダー セクションに OpenSearch の説明ファイルへの参照を含めます (通常、これには、次のようにサイトのホーム ページと検索結果ページが含まれます)。  
    
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
    
ユーザーが検索サービスにアクセスすると、後で使用できるように、OpenSearch説明が自動的に選択され保存されます。  ユーザーは Microsoft Edge の設定に移動し、検索サービスを Microsoft Edge アドレス バーの検索プロバイダーの一覧に追加できるようになります。  

詳細については [、OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) の固 OpenSearch定を参照してください。  
