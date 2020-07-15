---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2Settings の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 6adc494c63d0bd7adc2fd578fcb877e0bf75307f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879367"
---
# <span data-ttu-id="f7ee7-104">0.9.515 クラスの WebView2 クラス (CoreWebView2Settings)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

> [!NOTE]
> <span data-ttu-id="f7ee7-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="f7ee7-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="f7ee7-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="f7ee7-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f7ee7-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f7ee7-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f7ee7-109">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-109">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="f7ee7-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="f7ee7-110">Summary</span></span>

 <span data-ttu-id="f7ee7-111">Members</span><span class="sxs-lookup"><span data-stu-id="f7ee7-111">Members</span></span>                        | <span data-ttu-id="f7ee7-112">説明</span><span class="sxs-lookup"><span data-stu-id="f7ee7-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f7ee7-113">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-113">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="f7ee7-114">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-114">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="f7ee7-115">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-115">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="f7ee7-116">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-116">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="f7ee7-117">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-117">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="f7ee7-118">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-118">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="f7ee7-119">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="f7ee7-119">AreHostObjectsAllowed</span></span>](#arehostobjectsallowed) | <span data-ttu-id="f7ee7-120">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-120">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="f7ee7-121">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-121">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="f7ee7-122">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-122">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="f7ee7-123">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-123">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="f7ee7-124">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-124">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="f7ee7-125">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-125">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="f7ee7-126">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-126">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="f7ee7-127">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-127">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="f7ee7-128">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-128">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="f7ee7-129">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-129">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="f7ee7-130">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-130">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="f7ee7-131">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-131">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="f7ee7-132">Members</span><span class="sxs-lookup"><span data-stu-id="f7ee7-132">Members</span></span>

#### <span data-ttu-id="f7ee7-133">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-133">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="f7ee7-134">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-134">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="f7ee7-135">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-135">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="f7ee7-136">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-136">Defaults to TRUE.</span></span>

#### <span data-ttu-id="f7ee7-137">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-137">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="f7ee7-138">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-138">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="f7ee7-139">public ブール値は[Defaultscriptし enabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-139">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="f7ee7-140">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-140">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="f7ee7-141">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-141">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="f7ee7-142">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-142">AreDevToolsEnabled</span></span> 

<span data-ttu-id="f7ee7-143">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-143">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="f7ee7-144">公開ブール型の[Devtaskenabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-144">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="f7ee7-145">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-145">It is true by default.</span></span>

#### <span data-ttu-id="f7ee7-146">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="f7ee7-146">AreHostObjectsAllowed</span></span> 

<span data-ttu-id="f7ee7-147">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-147">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="f7ee7-148">public bool は[hostオブジェクトを許可](#arehostobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-148">public bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span></span>

<span data-ttu-id="f7ee7-149">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-149">Defaults to TRUE.</span></span>

#### <span data-ttu-id="f7ee7-150">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-150">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="f7ee7-151">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-151">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="f7ee7-152">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-152">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="f7ee7-153">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-153">Defaults to TRUE.</span></span> <span data-ttu-id="f7ee7-154">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-154">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="f7ee7-155">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-155">IsScriptEnabled</span></span> 

<span data-ttu-id="f7ee7-156">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-156">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="f7ee7-157">public bool [Isscriptenabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-157">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="f7ee7-158">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-158">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="f7ee7-159">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-159">It is true by default.</span></span>

#### <span data-ttu-id="f7ee7-160">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-160">IsStatusBarEnabled</span></span> 

<span data-ttu-id="f7ee7-161">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-161">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="f7ee7-162">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-162">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="f7ee7-163">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-163">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="f7ee7-164">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-164">It is true by default.</span></span>

#### <span data-ttu-id="f7ee7-165">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-165">IsWebMessageEnabled</span></span> 

<span data-ttu-id="f7ee7-166">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-166">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="f7ee7-167">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-167">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="f7ee7-168">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-168">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="f7ee7-169">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-169">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="f7ee7-170">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-170">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="f7ee7-171">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-171">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="f7ee7-172">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-172">It is true by default.</span></span>

#### <span data-ttu-id="f7ee7-173">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f7ee7-173">IsZoomControlEnabled</span></span> 

<span data-ttu-id="f7ee7-174">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-174">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="f7ee7-175">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="f7ee7-175">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="f7ee7-176">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-176">Defaults to TRUE.</span></span> <span data-ttu-id="f7ee7-177">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="f7ee7-177">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

