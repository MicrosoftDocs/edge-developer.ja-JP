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
# <span data-ttu-id="2cf1e-104">拡張機能を移植する</span><span class="sxs-lookup"><span data-stu-id="2cf1e-104">Port your extension</span></span>  

<span data-ttu-id="2cf1e-105">Microsoft Edge変更を最小限に抑え、Chrome 拡張機能を移植できます。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-105">Microsoft Edge allows you to port your Chrome extension with minimal changes.</span></span>  <span data-ttu-id="2cf1e-106">Chrome でサポートされている拡張機能 API とマニフェスト キーは、コードと互換性Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-106">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="2cf1e-107">ユーザーがサポートする API の一覧についてはMicrosoft Edge API サポート[に移動します][ExtensionApiSupport]。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-107">For a list of APIs supported by Microsoft Edge, navigate to [API support][ExtensionApiSupport].</span></span>  

<span data-ttu-id="2cf1e-108">Chrome 拡張機能を移植するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-108">To port your Chrome extension, complete the following steps.</span></span>  

1.  <span data-ttu-id="2cf1e-109">拡張機能でサポートされている API リストを使用して、拡張機能で使用Microsoft Edge Chrome 拡張機能[API を確認][ExtensionApiSupport]します。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-109">Review the Chrome extension APIs used in your extensions with the Microsoft Edge extensions [supported APIs][ExtensionApiSupport] list.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2cf1e-110">拡張機能でサポートされていない API を使用している場合は、Microsoft Edgeポートしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-110">If your extension uses APIs that are not supported by Microsoft Edge, it may not port directly.</span></span>  
    
1.  <span data-ttu-id="2cf1e-111">マニフェスト ファイルで、フィールドを `update_URL` に設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-111">In the manifest file, set the `update_URL` field to `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span>  <span data-ttu-id="2cf1e-112">この値は、Microsoft Edge アドオン ストア内の拡張機能のファイルをポイントし、Microsoft Edge更新 `.crx` プログラムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-112">The value points to the `.crx` file of your extension in the Microsoft Edge Add-ons store and allows Microsoft Edge to check for extension updates.</span></span>  
1.  <span data-ttu-id="2cf1e-113">拡張機能の名前または説明で使用する場合は、 を使用して `Chrome` 拡張機能のブランドを変更します `Microsoft Edge` 。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-113">If `Chrome` is used in either the name or the description of your extension, rebrand your extension using `Microsoft Edge`.</span></span>  <span data-ttu-id="2cf1e-114">認定プロセスに合格するには、変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-114">To pass the certification process, the changes are required.</span></span>  
1.  <span data-ttu-id="2cf1e-115">拡張機能をテストして、拡張機能をサイドローディングMicrosoft Edgeで機能[する場合に確認します][ExtensionsGettingStartedExtensionSideloading]。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-115">Test your extension to check if it works in Microsoft Edge by [sideloading your extension][ExtensionsGettingStartedExtensionSideloading].</span></span>  
1.  <span data-ttu-id="2cf1e-116">問題が発生した場合は、DevTools を使用してMicrosoft Edgeで拡張機能をデバッグするか、お問い[合わせください][mailtoExtensionMicrosoft]。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-116">If you face any issues, you may debug your extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionMicrosoft].</span></span>  
1.  <span data-ttu-id="2cf1e-117">発行ガイドライン[に従って][ExtensionsPublishPublishExtension]、拡張機能をアドオン ストアMicrosoft Edge発行します。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-117">Follow the [publishing guidelines][ExtensionsPublishPublishExtension] to publish your extension on Microsoft Edge Add-ons store.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="2cf1e-118">拡張機能が使用しているネイティブ アプリとメッセージを交換する場合は、ネイティブ メッセージング ホスト マニフェスト ファイルに設定 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` してください。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-118">If your extension exchanges messages with a native app using `chrome.runtime.connectNative`, ensure that you set `allowed_origins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span>  <span data-ttu-id="2cf1e-119">この設定により、アプリは拡張機能を識別できます。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-119">The setting allows the app to identify your extension.</span></span>  
    
## <span data-ttu-id="2cf1e-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="2cf1e-120">Next steps</span></span>  

<span data-ttu-id="2cf1e-121">拡張機能パッケージをアドイン ストアで発行する準備がMicrosoft Edge、開発者アカウントを作成し、拡張機能[][ExtensionsPublishCreateDevAccount][を発行します][ExtensionsPublishPublishExtension]。</span><span class="sxs-lookup"><span data-stu-id="2cf1e-121">After your extension package is ready to publish in the Microsoft Edge Add-ons store, [create a developer account][ExtensionsPublishCreateDevAccount] and [publish your extension][ExtensionsPublishPublishExtension].</span></span>  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "拡張機能をサイドロード|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能の公開|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1 回払い|Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
