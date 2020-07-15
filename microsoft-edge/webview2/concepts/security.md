---
description: セキュリティで保護された WebView2 アプリケーションの開発方法を理解する
title: セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、security
ms.openlocfilehash: 998bcf056e6350efc66880a9ad520f6d969af2f1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879145"
---
# <span data-ttu-id="5a165-104">セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="5a165-104">Best practices for developing secure WebView2 applications</span></span>

<span data-ttu-id="5a165-105">[WebView2 コントロール](https://docs.microsoft.com/microsoft-edge/webview2/)を使うと、開発者はネイティブアプリケーションで web コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="5a165-105">The [WebView2 control](https://docs.microsoft.com/microsoft-edge/webview2/) allows developers to host web content in their native applications.</span></span> <span data-ttu-id="5a165-106">適切に使用されると、web ベースの UI の使用、web プラットフォームの機能へのアクセス、コードのクロスプラットフォームの共有など、さまざまな利点が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5a165-106">When used correctly, hosting web content offers several advantages, such as using web-based UI, accessing features of the web platform, sharing code cross-platform, and so on.</span></span> <span data-ttu-id="5a165-107">Web コンテンツをホストすることで発生する可能性のある脆弱性を回避するために、WebView2 アプリケーションを設計して、web コンテンツとホストアプリケーション間の相互作用を厳密に監視してください。</span><span class="sxs-lookup"><span data-stu-id="5a165-107">To avoid vulnerabilities that can arise from hosting web content, make sure to design your WebView2 application to closely monitor interactions between the web content and the host application.</span></span> 

1. <span data-ttu-id="5a165-108">すべての web コンテンツを安全なセキュリティとして扱う</span><span class="sxs-lookup"><span data-stu-id="5a165-108">Treat all web content as insecure</span></span>
    - <span data-ttu-id="5a165-109">Web メッセージとホストオブジェクトパラメーターを使用する前に検証します。これは、web メッセージとパラメーターの形式が間違っている可能性があり (意図せず、または故意でなく)、アプリが予期せず動作する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="5a165-109">Validate web messages and host object parameters before consuming them, because web messages and parameters can be malformed (unintentionally or maliciously) and cause the app to behave unexpectedly.</span></span>
    - <span data-ttu-id="5a165-110">WebView2 内で実行されているドキュメントの出所を常に確認して、コンテンツの信頼性を評価してください。</span><span class="sxs-lookup"><span data-stu-id="5a165-110">Always check the origin of the document running inside WebView2 and assess the trustworthiness of the content.</span></span> 

2. <span data-ttu-id="5a165-111">汎用プロキシを使う代わりに、特定の web メッセージとホストオブジェクトの操作を設計します。</span><span class="sxs-lookup"><span data-stu-id="5a165-111">Design specific web messages and host object interactions instead of using generic proxies.</span></span>

3. <span data-ttu-id="5a165-112">次のように[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) または[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.net) を変更して、web コンテンツの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="5a165-112">Restrict web content functionality by modifying [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) or [CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.NET) as follows:</span></span>
    - <span data-ttu-id="5a165-113">`AreHostObjectsAllowed` `false` Web コンテンツがホストオブジェクトにアクセスすることを想定していない場合は、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="5a165-113">Set `AreHostObjectsAllowed` to `false`, if you don’t expect the web content to access host objects.</span></span>
    - <span data-ttu-id="5a165-114">`IsWebMessageEnabled` `false` Web コンテンツがネイティブアプリケーションに web メッセージを投稿しない場合は、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="5a165-114">Set `IsWebMessageEnabled` to `false`, if you don’t expect the web content to post web messages to your native application.</span></span> 
    - <span data-ttu-id="5a165-115">`IsScriptEnabled` `false` Web コンテンツによってスクリプトが実行されない場合 (静的 html コンテンツを表示する場合など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a165-115">Set `IsScriptEnabled` to `false`, if you don’t expect the web content to run scripts (for example, when showing static html content).</span></span>
    - <span data-ttu-id="5a165-116">`AreDefaultScriptDialogsEnabled` `false` Web コンテンツが表示されない場合、またはダイアログボックスが表示されない場合は、をに設定 `alert` `prompt` します。</span><span class="sxs-lookup"><span data-stu-id="5a165-116">Set `AreDefaultScriptDialogsEnabled` to `false`, if you don’t expect the web content to show `alert` or `prompt` dialog boxes.</span></span>

4. <span data-ttu-id="5a165-117">`NavigationStarting` `FrameNavigationStarting` 次に示すように、イベントを使用して、新しいページの原点に基づいて設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="5a165-117">Use the `NavigationStarting` and `FrameNavigationStarting` events to update settings based on the origin of the new page as follows:</span></span>
    1. <span data-ttu-id="5a165-118">アプリケーションが特定のページに移動できないようにするには、これらのイベントを使用して、ページまたはフレームのナビゲーションを確認してからブロックします。</span><span class="sxs-lookup"><span data-stu-id="5a165-118">To prevent your application from navigating to certain pages, use these events to check and then block page or frame navigation.</span></span> 
    2. <span data-ttu-id="5a165-119">新しいページに移動するときは、上で説明したように、 [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) または[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.net) のプロパティ値の調整が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="5a165-119">When navigating to a new page, you may need to adjust the property values on [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings.md) (Win32) or [CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings.md) (.NET)\` as described above.</span></span>

5. <span data-ttu-id="5a165-120">新しいドキュメントに移動するときは、 `ContentLoading` を使用して、公開されているホストオブジェクトを削除し `RemoveHostObjectFromScript` ます。</span><span class="sxs-lookup"><span data-stu-id="5a165-120">When navigating to a new document, use the `ContentLoading` event to remove exposed host objects using `RemoveHostObjectFromScript`.</span></span> 