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
# <span data-ttu-id="ac999-104">Microsoft \ (Chromium) Edge のポート Chrome 拡張機能</span><span class="sxs-lookup"><span data-stu-id="ac999-104">Port Chrome Extension To Microsoft \(Chromium\) Edge</span></span>  

<span data-ttu-id="ac999-105">Chrome 拡張機能を Microsoft Edge に移植するプロセスは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="ac999-105">The process of porting a Chrome Extension to Microsoft Edge is very straightforward.</span></span>  <span data-ttu-id="ac999-106">Chromium 用に記述された拡張機能は、ほとんどの場合、最小限の変更で Microsoft Edge で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ac999-106">Extensions written for Chromium, in most cases, run on Microsoft Edge with minimal changes.</span></span>  <span data-ttu-id="ac999-107">Chrome でサポートされている拡張 Api とマニフェストキーは、Microsoft Edge とのコード互換性があります。</span><span class="sxs-lookup"><span data-stu-id="ac999-107">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="ac999-108">ただし、Microsoft Edge では、次の拡張 Api はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ac999-108">However, Microsoft Edge does not support the following Extension APIs:</span></span>  

*   `chrome.gcm`  
*   `chrome.identity.getAccounts`  
*   `chrome.identity.getAuthToken`  
*   `chrome.instanceID`  

> [!Note]
> <span data-ttu-id="ac999-109">API を使用するには、ユーザーが MSA または AAD アカウントを使用して Microsoft Edge にサインインしている必要があり `chrome.identity.getProfileUserInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="ac999-109">The user must be signed into Microsoft Edge using an MSA or AAD account in order to use the `chrome.identity.getProfileUserInfo` API.</span></span>  <span data-ttu-id="ac999-110">ユーザーが **オンプレミス広告**を使って Microsoft Edge にサインインした場合、API は `null` メールと ID の値に対して戻ります。</span><span class="sxs-lookup"><span data-stu-id="ac999-110">If the user is signed into Microsoft Edge using **On-premise AD**, the API returns `null` for the email and ID values.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ac999-111">**支払い**: Microsoft Edge では、サインインしたユーザーが REST ベースのライセンス API 要求を送信するためのトークンを取得するために要求を使用する必要があるため、 [Chrome Web Store の支払い][ChromeDeveloperWebStorePayments] を使用する拡張機能は直接サポートされません `identity.getAuthtoken` 。</span><span class="sxs-lookup"><span data-stu-id="ac999-111">**Payments**:  Microsoft Edge does not directly support an Extension that uses [Chrome Web Store payments][ChromeDeveloperWebStorePayments] due to the requirement to use the `identity.getAuthtoken` request to get the token for signed-in users to send the REST-based licensing API request.</span></span>  <span data-ttu-id="ac999-112">Microsoft Edge は要求をサポートしていない `getAuthtoken` ため、このフローは動作しません。</span><span class="sxs-lookup"><span data-stu-id="ac999-112">Microsoft Edge does not support the `getAuthtoken` request, so this flow does not work.</span></span>  

<span data-ttu-id="ac999-113">Chrome 拡張機能を移植するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac999-113">To port your Chrome Extension, follow these steps:</span></span>  

1.  <span data-ttu-id="ac999-114">拡張機能で使用されている Chrome 拡張 Api を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac999-114">Review the Chrome Extension APIs used in your Extensions.</span></span>  <span data-ttu-id="ac999-115">Microsoft Edge でサポートされていない機能または Api を使用している場合は、拡張機能を移植できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac999-115">If you are using features or APIs that are not supported by Microsoft Edge, you may not be able to port your Extension.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ac999-116">`getAuthToken`API は Microsoft Edge では動作しませんが、OAuth2 トークンを取得してユーザーを認証するために使うことができ `launchWebAuthFlow` ます。</span><span class="sxs-lookup"><span data-stu-id="ac999-116">The `getAuthToken` API does not work with Microsoft Edge, however you may use `launchWebAuthFlow` to fetch an OAuth2 token to authenticate users.</span></span>  
    
1.  <span data-ttu-id="ac999-117">`Chrome`内線番号の名前または説明を使用している場合は、の内線番号を再ブランド化し `Microsoft Edge` ます。</span><span class="sxs-lookup"><span data-stu-id="ac999-117">If you are using `Chrome` in the name or description of your Extension, re-brand the Extension for `Microsoft Edge`.</span></span>  <span data-ttu-id="ac999-118">認定プロセスに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac999-118">You must pass the certification process.</span></span>  
    
1.  <span data-ttu-id="ac999-119">Microsoft Edge で動作するかどうかを確認するために拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="ac999-119">Test your Extension to check if it works in Microsoft Edge.</span></span>  <span data-ttu-id="ac999-120">この操作を行う最初の手順は、拡張機能の開発者向け機能が有効になっていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="ac999-120">The first step to do this is to ensure that you have Extension developer features turned on.</span></span>  <span data-ttu-id="ac999-121">これにより、Microsoft Edge で拡張機能ファイルをサイドロードすることができるため、拡張機能の開発中に拡張機能をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac999-121">This enables you to side load Extension files in Microsoft Edge so that you are able to test your Extension while developing it.</span></span>  
    
1.  <span data-ttu-id="ac999-122">問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、 [お問い合わせ][mailtoExtensionPartnerOpsMicrosoft]ください。</span><span class="sxs-lookup"><span data-stu-id="ac999-122">If you have any issues, debug your Extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionPartnerOpsMicrosoft].</span></span>  
    
1.  <span data-ttu-id="ac999-123">これで、拡張機能が最終的に磨き、パッケージ化される準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="ac999-123">Now your Extension is finally polished up and ready to be packaged.</span></span>  <span data-ttu-id="ac999-124">Microsoft Edge のアドオンカタログ (Microsoft Edge アドオン \) への提出を準備する場合は、拡張機能をパッケージ化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac999-124">If you wish to prepare for submission to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\), you do not need to package your Extension.</span></span>  <span data-ttu-id="ac999-125">さらに、 [公開ガイドライン][ExtensionsPublishExtension] に従って、Microsoft Edge のアドオンに拡張機能を公開してください。</span><span class="sxs-lookup"><span data-stu-id="ac999-125">Further, follow our [publishing guidelines][ExtensionsPublishExtension] to publish your Extension on Microsoft Edge Addons.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ac999-126">拡張機能が API を使ってネイティブアプリケーションとのメッセージを交換する場合は `chrome.runtime.connectNative` 、 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` ネイティブメッセージングホストマニフェストファイルで "" に設定してください。</span><span class="sxs-lookup"><span data-stu-id="ac999-126">If your Extension exchanges messages with a native application using `chrome.runtime.connectNative` API, ensure that you set `allowedorigins` to "`extension://[Microsoft-Catalog-extensionID]`" in your native messaging host manifest file.</span></span>  <span data-ttu-id="ac999-127">これにより、アプリで拡張機能を識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac999-127">This enables the app to identify the Extension.</span></span>  

<!-- image links -->  

<!-- links -->  

[ExtensionsPublishExtension]: ../publish/publish-extension.md "内線番号を発行する"  

[mailtoExtensionPartnerOpsMicrosoft]: mailto:extensionpartnerops@microsoft.com "ExtensionPartnerOps@microsoft.com"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "ワンタイムの支払い-Google Chrome"  
