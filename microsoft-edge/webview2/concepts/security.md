---
description: セキュリティで保護された WebView2 アプリケーションの開発方法を理解する
title: セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、security
ms.openlocfilehash: 774c812789bea4936611c41915e0c34f93205dba
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010762"
---
# <span data-ttu-id="6cf21-104">セキュリティで保護された WebView2 アプリケーションを開発するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="6cf21-104">Best practices for developing secure WebView2 applications</span></span>  

<span data-ttu-id="6cf21-105">[WebView2 コントロール][Webview2Main]を使うと、開発者はネイティブアプリケーションで web コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="6cf21-105">The [WebView2 control][Webview2Main] allows developers to host web content in the native applications.</span></span> <span data-ttu-id="6cf21-106">適切に使用されると、web ベースの UI の使用、web プラットフォームの機能へのアクセス、コードのクロスプラットフォームの共有など、さまざまな利点が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6cf21-106">When used correctly, hosting web content offers several advantages, such as using web-based UI, accessing features of the web platform, sharing code cross-platform, and so on.</span></span>  <span data-ttu-id="6cf21-107">Web コンテンツをホストすることで発生する可能性のある脆弱性を回避するために、WebView2 アプリケーションを設計して、web コンテンツとホストアプリケーション間の相互作用を厳密に監視してください。</span><span class="sxs-lookup"><span data-stu-id="6cf21-107">To avoid vulnerabilities that can arise from hosting web content, make sure to design your WebView2 application to closely monitor interactions between the web content and the host application.</span></span>  

1.  <span data-ttu-id="6cf21-108">すべての web コンテンツを安全ではないとして扱う。</span><span class="sxs-lookup"><span data-stu-id="6cf21-108">Treat all web content as insecure.</span></span>  
    *   <span data-ttu-id="6cf21-109">Web メッセージとパラメーターを検証してから各パラメーターを使うことができます。これは、web メッセージとパラメーターの形式が間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6cf21-109">Validate web messages and host object parameters before consuming each, because web messages and parameters can be malformed \(unintentionally or maliciously\) and cause the app to behave unexpectedly.</span></span>
    *   <span data-ttu-id="6cf21-110">WebView2 内で実行されているドキュメントの出所を常に確認して、コンテンツの信頼性を評価してください。</span><span class="sxs-lookup"><span data-stu-id="6cf21-110">Always check the origin of the document running inside WebView2 and assess the trustworthiness of the content.</span></span>  
1.  <span data-ttu-id="6cf21-111">汎用プロキシを使う代わりに、特定の web メッセージとホストオブジェクトの操作を設計します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-111">Design specific web messages and host object interactions instead of using generic proxies.</span></span>  
1.  <span data-ttu-id="6cf21-112">次のオプションを設定して、 [ICoreWebView2Settings (Win32)][Webview2ReferenceWin3209622Icorewebview2settings] または [CoreWebView2Settings (.net)][Webview2ReferenceWin3209628MicrosoftWebWebview2CoreCorewebview2settings]を変更することにより、web コンテンツの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-112">Set the following options to restrict web content functionality by modifying [ICoreWebView2Settings (Win32)][Webview2ReferenceWin3209622Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceWin3209628MicrosoftWebWebview2CoreCorewebview2settings].</span></span>  
    *   <span data-ttu-id="6cf21-113">`AreHostObjectsAllowed` `false` Web コンテンツがホストオブジェクトにアクセスすることを想定していない場合は、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-113">Set `AreHostObjectsAllowed` to `false`, if you do not expect the web content to access host objects.</span></span>  
    *   <span data-ttu-id="6cf21-114">Web `IsWebMessageEnabled` `false` コンテンツによってネイティブアプリケーションに web メッセージが投稿されないようにする場合は、をに設定します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-114">Set `IsWebMessageEnabled` to `false`, if you do not expect the web content to post web messages to your native application.</span></span>  
    *   <span data-ttu-id="6cf21-115">`IsScriptEnabled` `false` Web コンテンツがスクリプトを実行することを想定していない場合は、をに設定します (静的 html コンテンツを表示する場合など)。</span><span class="sxs-lookup"><span data-stu-id="6cf21-115">Set `IsScriptEnabled` to `false`, if you do not expect the web content to run scripts \(for example, when showing static html content\).</span></span>  
    *   <span data-ttu-id="6cf21-116">`AreDefaultScriptDialogsEnabled` `false` Web コンテンツが表示されない場合、またはダイアログボックスを表示しない場合は、をに設定 `alert` `prompt` します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-116">Set `AreDefaultScriptDialogsEnabled` to `false`, if you do not expect the web content to show `alert` or `prompt` dialog boxes.</span></span>  
1.  <span data-ttu-id="6cf21-117">次の手順では、およびイベントを使用して、 `NavigationStarting` `FrameNavigationStarting` 新しいページの起点に基づいて設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="6cf21-117">In the following steps, use the `NavigationStarting` and `FrameNavigationStarting` events to update settings based on the origin of the new page.</span></span>  
    1.  <span data-ttu-id="6cf21-118">アプリケーションが特定のページに移動できないようにするには、イベントを使用して、ページまたはフレームのナビゲーションを確認してからブロックします。</span><span class="sxs-lookup"><span data-stu-id="6cf21-118">To prevent your application from navigating to certain pages, use the events to check and then block page or frame navigation.</span></span>  
    1.  <span data-ttu-id="6cf21-119">新しいページに移動するときは、前に説明したように、 [ICoreWebView2Settings (Win32)][Webview2ReferenceWin3209622Icorewebview2settings] または [CoreWebView2Settings (.net)][Webview2ReferenceWin3209628MicrosoftWebWebview2CoreCorewebview2settings] でプロパティ値を調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6cf21-119">When navigating to a new page, you may need to adjust the property values on [ICoreWebView2Settings (Win32)][Webview2ReferenceWin3209622Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceWin3209628MicrosoftWebWebview2CoreCorewebview2settings] as previously described.</span></span>  
1.  <span data-ttu-id="6cf21-120">新しいドキュメントに移動するときは、 `ContentLoading` を使用して、公開されているホストオブジェクトを削除し `RemoveHostObjectFromScript` ます。</span><span class="sxs-lookup"><span data-stu-id="6cf21-120">When navigating to a new document, use the `ContentLoading` event to remove exposed host objects using `RemoveHostObjectFromScript`.</span></span>  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[Webview2ReferenceWin3209622Icorewebview2settings]: ../reference/win32/0-9-622/icorewebview2settings.md "インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  

[Webview2ReferenceWin3209628MicrosoftWebWebview2CoreCorewebview2settings]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2settings.md "WebView2 クラス | CoreWebView2Settings クラスを |Microsoft ドキュメント"  
