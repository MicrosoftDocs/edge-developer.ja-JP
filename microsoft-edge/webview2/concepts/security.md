---
description: セキュリティで保護された WebView2 アプリケーションを開発する方法を理解する
title: 安全な WebView2 アプリケーションを開発するためのベスト プラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html、セキュリティ
ms.openlocfilehash: d53417cc1ac98b44565692edbaec06216f7c110b
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119003"
---
# <span data-ttu-id="5b086-104">安全な WebView2 アプリケーションを開発するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="5b086-104">Best practices for developing secure WebView2 applications</span></span>  

<span data-ttu-id="5b086-105">[WebView2 コントロールを使用][Webview2Main]すると、開発者はネイティブ アプリケーションで Web コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="5b086-105">The [WebView2 control][Webview2Main] allows developers to host web content in the native applications.</span></span> <span data-ttu-id="5b086-106">正しく使用すると、Web コンテンツのホスティングには、Web ベースの UI の使用、Web プラットフォームの機能へのアクセス、コードクロスプラットフォームの共有など、いくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="5b086-106">When used correctly, hosting web content offers several advantages, such as using web-based UI, accessing features of the web platform, sharing code cross-platform, and so on.</span></span>  <span data-ttu-id="5b086-107">Web コンテンツのホストから発生する可能性のある脆弱性を回避するには、Web コンテンツとホスト アプリケーションの間の相互作用を密接に監視するために、必ず WebView2 アプリケーションを設計してください。</span><span class="sxs-lookup"><span data-stu-id="5b086-107">To avoid vulnerabilities that can arise from hosting web content, make sure to design your WebView2 application to closely monitor interactions between the web content and the host application.</span></span>  

1.  <span data-ttu-id="5b086-108">すべての Web コンテンツを安全でないと扱います。</span><span class="sxs-lookup"><span data-stu-id="5b086-108">Treat all web content as insecure.</span></span>  
    *   <span data-ttu-id="5b086-109">Web メッセージとパラメーターの形式が正しく設定されていない \(意図しない、または悪意を持って\)、アプリが予期せず動作する可能性があるため、Web メッセージとホスト オブジェクト パラメーターを使用する前に検証します。</span><span class="sxs-lookup"><span data-stu-id="5b086-109">Validate web messages and host object parameters before consuming each, because web messages and parameters can be malformed \(unintentionally or maliciously\) and cause the app to behave unexpectedly.</span></span>
    *   <span data-ttu-id="5b086-110">WebView2 内で実行されているドキュメントの原点を常に確認し、コンテンツの信頼性を評価します。</span><span class="sxs-lookup"><span data-stu-id="5b086-110">Always check the origin of the document running inside WebView2 and assess the trustworthiness of the content.</span></span>  
1.  <span data-ttu-id="5b086-111">汎用プロキシを使用する代わりに、特定の Web メッセージとホスト オブジェクトの操作を設計します。</span><span class="sxs-lookup"><span data-stu-id="5b086-111">Design specific web messages and host object interactions instead of using generic proxies.</span></span>  
1.  <span data-ttu-id="5b086-112">[ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings]または[CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]を変更して、Web コンテンツ機能を制限するには、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b086-112">Set the following options to restrict web content functionality by modifying [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings].</span></span>  
    *   <span data-ttu-id="5b086-113">Web `AreHostObjectsAllowed` コンテンツ `false` がホスト オブジェクトにアクセスしない場合は、に設定します。</span><span class="sxs-lookup"><span data-stu-id="5b086-113">Set `AreHostObjectsAllowed` to `false`, if you do not expect the web content to access host objects.</span></span>  
    *   <span data-ttu-id="5b086-114">Web コンテンツが Web メッセージをネイティブ アプリケーションに投稿しない場合は `IsWebMessageEnabled` `false` 、に設定します。</span><span class="sxs-lookup"><span data-stu-id="5b086-114">Set `IsWebMessageEnabled` to `false`, if you do not expect the web content to post web messages to your native application.</span></span>  
    *   <span data-ttu-id="5b086-115">Web コンテンツでスクリプト \(静的な html コンテンツ\を表示する場合など) を実行しない場合は、に `IsScriptEnabled` `false` 設定します。</span><span class="sxs-lookup"><span data-stu-id="5b086-115">Set `IsScriptEnabled` to `false`, if you do not expect the web content to run scripts \(for example, when showing static html content\).</span></span>  
    *   <span data-ttu-id="5b086-116">Web コンテンツが表示またはダイアログ ボックスに表示されない場合は、 `AreDefaultScriptDialogsEnabled` `false` `alert` に `prompt` 設定します。</span><span class="sxs-lookup"><span data-stu-id="5b086-116">Set `AreDefaultScriptDialogsEnabled` to `false`, if you do not expect the web content to show `alert` or `prompt` dialog boxes.</span></span>  
1.  <span data-ttu-id="5b086-117">次の手順では、and `NavigationStarting` イベントを使用して、新しいページの原点に基づいて `FrameNavigationStarting` 設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="5b086-117">In the following steps, use the `NavigationStarting` and `FrameNavigationStarting` events to update settings based on the origin of the new page.</span></span>  
    1.  <span data-ttu-id="5b086-118">アプリケーションで特定のページへの移動を防止するには、イベントを使用してページまたはフレームのナビゲーションを確認してからブロックします。</span><span class="sxs-lookup"><span data-stu-id="5b086-118">To prevent your application from navigating to certain pages, use the events to check and then block page or frame navigation.</span></span>  
    1.  <span data-ttu-id="5b086-119">新しいページに移動する場合は、前述のように [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] または [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] のプロパティ値を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b086-119">When navigating to a new page, you may need to adjust the property values on [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] as previously described.</span></span>  
1.  <span data-ttu-id="5b086-120">新しいドキュメントに移動する場合は、イベントを使用して公開 `ContentLoading` されているホスト オブジェクトを削除します `RemoveHostObjectFromScript` 。</span><span class="sxs-lookup"><span data-stu-id="5b086-120">When navigating to a new document, use the `ContentLoading` event to remove exposed host objects using `RemoveHostObjectFromScript`.</span></span>  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2settings]: /microsoft-edge/webview2/reference/win32/icorewebview2settings "インターフェイス ICoreWebView2Settings |Microsoft Docs"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]: /dotnet/api/microsoft.web.webview2.core.corewebview2settings "CoreWebView2Settings クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
