---
description: Chrome 拡張機能をユーザーに移植するMicrosoft Edge
title: ポート Chrome 拡張機能 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 6be7d788ac22232475e278ae9a5b04de9b6e17f7
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343137"
---
# 拡張機能を移植する  

Microsoft Edge変更を最小限に抑え、Chrome 拡張機能を移植できます。  Chrome でサポートされている拡張機能 API とマニフェスト キーは、コードと互換性Microsoft Edge。  ユーザーがサポートする API の一覧についてはMicrosoft Edge API サポート[に移動します][ExtensionApiSupport]。  

Chrome 拡張機能を移植するには、次の手順を実行します。  

1.  拡張機能でサポートされている API リストを使用して、拡張機能で使用Microsoft Edge Chrome 拡張機能[API を確認][ExtensionApiSupport]します。  
    
    > [!NOTE]
    > 拡張機能でサポートされていない API を使用している場合は、Microsoft Edgeポートしない場合があります。  
    
1.  マニフェスト ファイルで、フィールドを `update_URL` に設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  この値は、Microsoft Edge アドオン ストア内の拡張機能のファイルをポイントし、Microsoft Edge更新 `.crx` プログラムを確認できます。  
1.  拡張機能の名前または説明で使用する場合は、 を使用して `Chrome` 拡張機能のブランドを変更します `Microsoft Edge` 。  認定プロセスに合格するには、変更が必要です。  
1.  拡張機能をテストして、拡張機能をサイドローディングMicrosoft Edgeで機能[する場合に確認します][ExtensionsGettingStartedExtensionSideloading]。  
1.  問題が発生した場合は、DevTools を使用してMicrosoft Edgeで拡張機能をデバッグするか、お問い[合わせください][mailtoExtensionMicrosoft]。  
1.  発行ガイドライン[に従って][ExtensionsPublishPublishExtension]、拡張機能をアドオン ストアMicrosoft Edge発行します。  
    
    > [!NOTE]
    > 拡張機能が使用しているネイティブ アプリとメッセージを交換する場合は、ネイティブ メッセージング ホスト マニフェスト ファイルに設定 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` してください。  この設定により、アプリは拡張機能を識別できます。  
    
## 次の手順  

拡張機能パッケージをアドイン ストアで発行する準備がMicrosoft Edge、開発者アカウントを作成し、拡張機能[][ExtensionsPublishCreateDevAccount][を発行します][ExtensionsPublishPublishExtension]。  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "拡張機能をサイドロード|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能の公開|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1 回払い|Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
