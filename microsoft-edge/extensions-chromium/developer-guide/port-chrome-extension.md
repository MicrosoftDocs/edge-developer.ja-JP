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
# <span data-ttu-id="7d092-104">内線番号を移植する</span><span class="sxs-lookup"><span data-stu-id="7d092-104">Port your extension</span></span>  

<span data-ttu-id="7d092-105">Microsoft Edge では、最小限の変更で Chrome 拡張機能を移植できます。</span><span class="sxs-lookup"><span data-stu-id="7d092-105">Microsoft Edge allows you to port your Chrome extension with minimal changes.</span></span>  <span data-ttu-id="7d092-106">Chrome でサポートされている拡張 Api とマニフェストキーは、Microsoft Edge とのコード互換性があります。</span><span class="sxs-lookup"><span data-stu-id="7d092-106">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="7d092-107">Microsoft Edge でサポートされている Api の一覧については、「 [api のサポート][ExtensionApiSupport]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d092-107">For a list of APIs supported by Microsoft Edge, navigate to [API support][ExtensionApiSupport].</span></span>  

<span data-ttu-id="7d092-108">Chrome の拡張機能を移植するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d092-108">To port your Chrome extension, complete the following steps.</span></span>  

1.  <span data-ttu-id="7d092-109">Microsoft Edge extensions の [サポートされている api][ExtensionApiSupport] の一覧で、拡張機能で使用されている Chrome 拡張 api を確認します。</span><span class="sxs-lookup"><span data-stu-id="7d092-109">Review the Chrome extension APIs used in your extensions with the Microsoft Edge extensions [supported APIs][ExtensionApiSupport] list.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="7d092-110">拡張機能で Microsoft Edge でサポートされていない Api を使用している場合は、直接移植できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d092-110">If your extension uses APIs that are not supported by Microsoft Edge, it may not port directly.</span></span>  
    
1.  <span data-ttu-id="7d092-111">名前 `Chrome` が拡張子の名前または説明のいずれかで使用されている場合は、用の拡張子をもう一度ブランド化し `Microsoft Edge` ます。</span><span class="sxs-lookup"><span data-stu-id="7d092-111">If the name `Chrome` is being used in either the name or the description of the extension, rebrand the extension for `Microsoft Edge`.</span></span>  <span data-ttu-id="7d092-112">この手順は、認定プロセスに合格するために必要です。</span><span class="sxs-lookup"><span data-stu-id="7d092-112">This step is required to pass the certification process.</span></span>  
1.  <span data-ttu-id="7d092-113">拡張機能の [サイドローディング][ExtensionsGettingStartedExtensionSideloading]によって、Microsoft Edge で機能するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d092-113">Test your extension to check if it works in Microsoft Edge by [sideloading your extension][ExtensionsGettingStartedExtensionSideloading].</span></span>  
1.  <span data-ttu-id="7d092-114">問題が発生した場合は、DevTools を使用して Microsoft Edge で拡張機能をデバッグするか、 [お問い合わせ][mailtoExtensionMicrosoft]ください。</span><span class="sxs-lookup"><span data-stu-id="7d092-114">If you face any issues, you may debug your extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionMicrosoft].</span></span>  
1.  <span data-ttu-id="7d092-115">[公開ガイドライン][ExtensionsPublishPublishExtension]に従って、Microsoft Edge のアドオンストアで拡張機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="7d092-115">Follow the [publishing guidelines][ExtensionsPublishPublishExtension] to publish your extension on Microsoft Edge Add-ons store.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="7d092-116">拡張機能が API を使用してネイティブアプリとメッセージを交換する場合は `chrome.runtime.connectNative` 、 `allowed_origins` ネイティブの `extension://[Microsoft-Catalog-extensionID]` メッセージングホストマニフェストファイルでを設定してください。</span><span class="sxs-lookup"><span data-stu-id="7d092-116">If the extension exchanges messages with a native app using `chrome.runtime.connectNative` API, ensure that you set `allowed_origins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span>  <span data-ttu-id="7d092-117">これにより、アプリで拡張機能を識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d092-117">This enables the app to identify the extension.</span></span>  
    
## <span data-ttu-id="7d092-118">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7d092-118">Next steps</span></span>  

<span data-ttu-id="7d092-119">拡張パッケージを Microsoft Edge のアドオンストアに公開する準備ができたら、 [開発者アカウントを作成][ExtensionsPublishCreateDevAccount] して、 [拡張機能を公開][ExtensionsPublishPublishExtension]します。</span><span class="sxs-lookup"><span data-stu-id="7d092-119">Once your extension package is ready to be published to Microsoft Edge add-ons store, [create a developer account][ExtensionsPublishCreateDevAccount] and [publish your extension][ExtensionsPublishPublishExtension].</span></span>  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API サポート |Microsoft ドキュメント"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "内線番号をサイドローディング |Microsoft ドキュメント"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "開発者登録 |Microsoft ドキュメント"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "拡張機能を公開する |Microsoft ドキュメント"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "1回限りの支払い |Chrome 開発者"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
