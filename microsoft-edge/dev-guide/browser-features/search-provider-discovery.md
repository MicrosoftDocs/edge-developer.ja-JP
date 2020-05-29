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
# 検索プロバイダーの検出


Microsoft Edge のアドレスバーには、検索候補、web の結果、閲覧履歴、お気に入りなど、リッチ検索の統合機能が組み込まれています。 Microsoft Edge は、 [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)仕様に従って、web 検索プロバイダーを検出して使用します。 検索プロバイダーの場合は、Microsoft Edge がサービスをサポートするようにする方法について説明します。

**Microsoft Edge では、ユーザーのセキュリティとプライバシーを保護するために、すべての検索を SSL 経由で行う必要があります。** `https`検索エンジンの Microsoft Edge 統合を有効にするには、次のリソースを url として指定する必要があります。
* 説明ドキュメントへの参照が含まれているサイト
* 説明ドキュメント自体の URL
* 検索クエリテンプレート 

1.  検索プロバイダーの名前と検索の構築に使うテンプレートを含む、OpenSearch description ファイルを指定します。 ドキュメントの例を次に示します。

    ```html
    <?xml version="1.0" encoding="UTF-8"?> 
    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
        <ShortName>Contoso Search</ShortName>
        <Url type="text/html" template="https://www.contoso.com/?query={searchTerms}"/> 
    </OpenSearchDescription>
    ```

2.  ページのヘッダーセクションに OpenSearch description ファイルへの参照を追加します (通常は、次のように、サイトのホームページと検索結果ページが含まれます)。

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

ユーザーが検索サービスを参照すると、OpenSearch 説明が自動的に取得されて、後で使用できるように保存されます。 その後、ユーザーは Microsoft Edge の [設定] に移動して、Microsoft Edge アドレスバーの検索プロバイダーのリストに検索サービスを追加することができます。

OpenSearch description ドキュメントの作成について詳しくは、 [OpenSearch 1.1](https://go.microsoft.com/fwlink/p/?LinkID=208582)の仕様をご覧ください。
