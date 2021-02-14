---
description: Chrome 拡張機能を Microsoft Edge に移植するプロセス。
title: Chrome 拡張機能を Microsoft Edge に移植する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 64a92927b9fe7658562f87f326bb9ac148991031
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327695"
---
# 内線番号を移植する  

Microsoft Edge では、最小限の変更で Chrome 拡張機能を移植できます。  Chrome でサポートされている拡張 API とマニフェスト キーは、Microsoft Edge とコード互換です。  Microsoft Edge でサポートされている API の一覧については [、API][ExtensionApiSupport]サポートに移動してください。  

Chrome 拡張機能を移植するには、次の手順を実行します。  

1.  Microsoft Edge 拡張機能でサポートされている API リストを使用して、拡張機能で使用されている Chrome 拡張機能 [API を確認][ExtensionApiSupport] します。  
    
    > [!NOTE]
    > 拡張機能が Microsoft Edge でサポートされていない API を使用している場合は、直接移植できない可能性があります。  
    
1.  マニフェスト ファイルで、フィールドを `update_URL` 次の値に設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  この値は、Microsoft Edge アドオン ストア内の拡張機能のファイルをポイントし、Microsoft Edge で拡張機能の更新 `.crx` プログラムを確認できます。  
1.  拡張機能の名前または説明で使用する場合は、次を使用して拡張機能 `Chrome` のブランドを変更します `Microsoft Edge` 。  認定プロセスに合格するには、変更が必要です。  
1.  拡張機能をテストして、拡張機能をサイドロードして、Microsoft Edge で機能 [する機能を確認します][ExtensionsGettingStartedExtensionSideloading]。  
1.  問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、マイクロソフトにお問い [合わせください][mailtoExtensionMicrosoft]。  
1.  Microsoft Edge [アドオン ストアで][ExtensionsPublishPublishExtension] 拡張機能を公開するには、公開ガイドラインに従います。  
    
    > [!NOTE]
    > 拡張機能が使用しているネイティブ アプリとメッセージを交換する場合は、ネイティブ メッセージング ホスト マニフェスト ファイルに設定 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` してください。  この設定により、アプリは拡張機能を識別できます。  
    
## 次の手順  

拡張機能パッケージを Microsoft Edge アドオン ストアで公開する準備ができたら、開発者 [アカウント][ExtensionsPublishCreateDevAccount] を作成し、拡張機能 [を公開します][ExtensionsPublishPublishExtension]。  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "拡張機能をサイドロード|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能を公開|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1 回払い|Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
