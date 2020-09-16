---
description: Microsoft Edge への Chrome 拡張機能の移植プロセス。
title: Microsoft (Chromium) Edge の港の Chrome 拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 1852e267579f0fb790c6b8cac75a566298223933
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015689"
---
# Microsoft \ (Chromium) Edge のポート Chrome 拡張機能  

Chrome 拡張機能を Microsoft Edge に移植するプロセスは非常に簡単です。  Chromium 用に記述された拡張機能は、ほとんどの場合、最小限の変更で Microsoft Edge で実行されます。  Chrome でサポートされている拡張 Api とマニフェストキーは、Microsoft Edge とのコード互換性があります。  ただし、Microsoft Edge では、次の拡張 Api はサポートされていません。  

*   `chrome.gcm`  
*   `chrome.identity.getAccounts`  
*   `chrome.identity.getAuthToken`  
*   `chrome.instanceID`  

> [!Note]
> API を使用するには、ユーザーが MSA または AAD アカウントを使用して Microsoft Edge にサインインしている必要があり `chrome.identity.getProfileUserInfo` ます。  ユーザーが **オンプレミス広告**を使って Microsoft Edge にサインインした場合、API は `null` メールと ID の値に対して戻ります。  

> [!IMPORTANT]
> **支払い**: Microsoft Edge では、サインインしたユーザーが REST ベースのライセンス API 要求を送信するためのトークンを取得するために要求を使用する必要があるため、 [Chrome Web Store の支払い][ChromeDeveloperWebStorePayments] を使用する拡張機能は直接サポートされません `identity.getAuthtoken` 。  Microsoft Edge は要求をサポートしていない `getAuthtoken` ため、このフローは動作しません。  

Chrome 拡張機能を移植するには、次の手順を実行します。  

1.  拡張機能で使用されている Chrome 拡張 Api を確認します。  Microsoft Edge でサポートされていない機能または Api を使用している場合は、拡張機能を移植できない可能性があります。  
    
    > [!NOTE]
    > `getAuthToken`API は Microsoft Edge では動作しませんが、OAuth2 トークンを取得してユーザーを認証するために使うことができ `launchWebAuthFlow` ます。  
    
1.  `Chrome`内線番号の名前または説明を使用している場合は、の内線番号を再ブランド化し `Microsoft Edge` ます。  認定プロセスに合格する必要があります。  
    
1.  Microsoft Edge で動作するかどうかを確認するために拡張機能をテストします。  この操作を行う最初の手順は、拡張機能の開発者向け機能が有効になっていることを確認することです。  これにより、Microsoft Edge で拡張機能ファイルをサイドロードすることができるため、拡張機能の開発中に拡張機能をテストすることができます。  
    
1.  問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、 [お問い合わせ][mailtoExtensionPartnerOpsMicrosoft]ください。  
    
1.  これで、拡張機能が最終的に磨き、パッケージ化される準備が整いました。  Microsoft Edge のアドオンカタログ (Microsoft Edge アドオン \) への提出を準備する場合は、拡張機能をパッケージ化する必要はありません。  さらに、 [公開ガイドライン][ExtensionsPublishExtension] に従って、Microsoft Edge のアドオンに拡張機能を公開してください。  
    
    > [!NOTE]
    > 拡張機能が API を使ってネイティブアプリケーションとのメッセージを交換する場合は `chrome.runtime.connectNative` 、 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` ネイティブメッセージングホストマニフェストファイルで "" に設定してください。  これにより、アプリで拡張機能を識別できるようになります。  

<!-- image links -->  

<!-- links -->  

[ExtensionsPublishExtension]: ../publish/publish-extension.md "内線番号を発行する"  

[mailtoExtensionPartnerOpsMicrosoft]: mailto:extensionpartnerops@microsoft.com "ExtensionPartnerOps@microsoft.com"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "ワンタイムの支払い-Google Chrome"  
