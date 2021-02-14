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
# <span data-ttu-id="e9ad5-104">内線番号を移植する</span><span class="sxs-lookup"><span data-stu-id="e9ad5-104">Port your extension</span></span>  

<span data-ttu-id="e9ad5-105">Microsoft Edge では、最小限の変更で Chrome 拡張機能を移植できます。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-105">Microsoft Edge allows you to port your Chrome extension with minimal changes.</span></span>  <span data-ttu-id="e9ad5-106">Chrome でサポートされている拡張 API とマニフェスト キーは、Microsoft Edge とコード互換です。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-106">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="e9ad5-107">Microsoft Edge でサポートされている API の一覧については [、API][ExtensionApiSupport]サポートに移動してください。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-107">For a list of APIs supported by Microsoft Edge, navigate to [API support][ExtensionApiSupport].</span></span>  

<span data-ttu-id="e9ad5-108">Chrome 拡張機能を移植するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-108">To port your Chrome extension, complete the following steps.</span></span>  

1.  <span data-ttu-id="e9ad5-109">Microsoft Edge 拡張機能でサポートされている API リストを使用して、拡張機能で使用されている Chrome 拡張機能 [API を確認][ExtensionApiSupport] します。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-109">Review the Chrome extension APIs used in your extensions with the Microsoft Edge extensions [supported APIs][ExtensionApiSupport] list.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e9ad5-110">拡張機能が Microsoft Edge でサポートされていない API を使用している場合は、直接移植できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-110">If your extension uses APIs that are not supported by Microsoft Edge, it may not port directly.</span></span>  
    
1.  <span data-ttu-id="e9ad5-111">マニフェスト ファイルで、フィールドを `update_URL` 次の値に設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-111">In the manifest file, set the `update_URL` field to `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span>  <span data-ttu-id="e9ad5-112">この値は、Microsoft Edge アドオン ストア内の拡張機能のファイルをポイントし、Microsoft Edge で拡張機能の更新 `.crx` プログラムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-112">The value points to the `.crx` file of your extension in the Microsoft Edge Add-ons store and allows Microsoft Edge to check for extension updates.</span></span>  
1.  <span data-ttu-id="e9ad5-113">拡張機能の名前または説明で使用する場合は、次を使用して拡張機能 `Chrome` のブランドを変更します `Microsoft Edge` 。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-113">If `Chrome` is used in either the name or the description of your extension, rebrand your extension using `Microsoft Edge`.</span></span>  <span data-ttu-id="e9ad5-114">認定プロセスに合格するには、変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-114">To pass the certification process, the changes are required.</span></span>  
1.  <span data-ttu-id="e9ad5-115">拡張機能をテストして、拡張機能をサイドロードして、Microsoft Edge で機能 [する機能を確認します][ExtensionsGettingStartedExtensionSideloading]。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-115">Test your extension to check if it works in Microsoft Edge by [sideloading your extension][ExtensionsGettingStartedExtensionSideloading].</span></span>  
1.  <span data-ttu-id="e9ad5-116">問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、マイクロソフトにお問い [合わせください][mailtoExtensionMicrosoft]。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-116">If you face any issues, you may debug your extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionMicrosoft].</span></span>  
1.  <span data-ttu-id="e9ad5-117">Microsoft Edge [アドオン ストアで][ExtensionsPublishPublishExtension] 拡張機能を公開するには、公開ガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-117">Follow the [publishing guidelines][ExtensionsPublishPublishExtension] to publish your extension on Microsoft Edge Add-ons store.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e9ad5-118">拡張機能が使用しているネイティブ アプリとメッセージを交換する場合は、ネイティブ メッセージング ホスト マニフェスト ファイルに設定 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` してください。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-118">If your extension exchanges messages with a native app using `chrome.runtime.connectNative`, ensure that you set `allowed_origins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span>  <span data-ttu-id="e9ad5-119">この設定により、アプリは拡張機能を識別できます。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-119">The setting allows the app to identify your extension.</span></span>  
    
## <span data-ttu-id="e9ad5-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="e9ad5-120">Next steps</span></span>  

<span data-ttu-id="e9ad5-121">拡張機能パッケージを Microsoft Edge アドオン ストアで公開する準備ができたら、開発者 [アカウント][ExtensionsPublishCreateDevAccount] を作成し、拡張機能 [を公開します][ExtensionsPublishPublishExtension]。</span><span class="sxs-lookup"><span data-stu-id="e9ad5-121">After your extension package is ready to publish in the Microsoft Edge add-ons store, [create a developer account][ExtensionsPublishCreateDevAccount] and [publish your extension][ExtensionsPublishPublishExtension].</span></span>  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "拡張機能をサイドロード|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能を公開|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1 回払い|Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
