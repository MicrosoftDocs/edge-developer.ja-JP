---
description: Microsoft Edge への Chrome 拡張機能の移植プロセス。
title: Microsoft Edge のポート Chrome 拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 0f767107bfb259476d1ab35d081fb9bb05c81b46
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195160"
---
# 内線番号を移植する  

Microsoft Edge では、最小限の変更で Chrome 拡張機能を移植できます。  Chrome でサポートされている拡張 Api とマニフェストキーは、Microsoft Edge とのコード互換性があります。  Microsoft Edge でサポートされている Api の一覧については、「 [api のサポート][ExtensionApiSupport]」を参照してください。  

Chrome の拡張機能を移植するには、次の手順を実行します。  

1.  Microsoft Edge extensions の [サポートされている api][ExtensionApiSupport] の一覧で、拡張機能で使用されている Chrome 拡張 api を確認します。  
    
    > [!NOTE]
    > 拡張機能で Microsoft Edge でサポートされていない Api を使用している場合は、直接移植できない可能性があります。  
    
1.  名前 `Chrome` が拡張子の名前または説明のいずれかで使用されている場合は、用の拡張子をもう一度ブランド化し `Microsoft Edge` ます。  この手順は、認定プロセスに合格するために必要です。  
1.  拡張機能の [サイドローディング][ExtensionsGettingStartedExtensionSideloading]によって、Microsoft Edge で機能するかどうかを確認します。  
1.  問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、 [お問い合わせ][mailtoExtensionMicrosoft]ください。  
1.  [公開ガイドライン][ExtensionsPublishPublishExtension]に従って、Microsoft Edge のアドオンストアで拡張機能を公開します。  
    
    > [!NOTE]
    > 拡張機能が API を使用してネイティブアプリとメッセージを交換する場合は `chrome.runtime.connectNative` 、 `allowed_origins` ネイティブの `extension://[Microsoft-Catalog-extensionID]` メッセージングホストマニフェストファイルでを設定してください。  これにより、アプリで拡張機能を識別できるようになります。  
    
## 次のステップ  

拡張パッケージを Microsoft Edge のアドオンストアに公開する準備ができたら、 [開発者アカウントを作成][ExtensionsPublishCreateDevAccount] して、 [拡張機能を公開][ExtensionsPublishPublishExtension]します。  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft ドキュメント"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "内線番号をサイドローディング |Microsoft ドキュメント"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録 |Microsoft ドキュメント"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能を公開する |Microsoft ドキュメント"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1回限りの支払い |Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
