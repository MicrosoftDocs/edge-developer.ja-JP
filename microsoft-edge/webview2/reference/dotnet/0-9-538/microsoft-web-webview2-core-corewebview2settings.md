---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b1cf72e967bde8d76ab345e37c1adc090af5d77d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699059"
---
# <span data-ttu-id="8c97e-104">WebView2 クラス (CoreWebView2Settings クラス)</span><span class="sxs-lookup"><span data-stu-id="8c97e-104">Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

<span data-ttu-id="8c97e-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8c97e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8c97e-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8c97e-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="8c97e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8c97e-108">Summary</span></span>

 <span data-ttu-id="8c97e-109">Members</span><span class="sxs-lookup"><span data-stu-id="8c97e-109">Members</span></span>                        | <span data-ttu-id="8c97e-110">説明</span><span class="sxs-lookup"><span data-stu-id="8c97e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8c97e-111">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-111">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="8c97e-112">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="8c97e-113">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-113">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="8c97e-114">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="8c97e-115">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-115">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="8c97e-116">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="8c97e-117">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="8c97e-117">AreHostObjectsAllowed</span></span>](#arehostobjectsallowed) | <span data-ttu-id="8c97e-118">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-118">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="8c97e-119">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-119">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="8c97e-120">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8c97e-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="8c97e-121">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-121">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="8c97e-122">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="8c97e-123">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-123">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="8c97e-124">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="8c97e-125">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-125">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="8c97e-126">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="8c97e-127">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-127">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="8c97e-128">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="8c97e-129">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="8c97e-129">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="8c97e-130">Members</span><span class="sxs-lookup"><span data-stu-id="8c97e-130">Members</span></span>

#### <span data-ttu-id="8c97e-131">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-131">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="8c97e-132">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="8c97e-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="8c97e-134">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-134">Defaults to TRUE.</span></span>

#### <span data-ttu-id="8c97e-135">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-135">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="8c97e-136">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-136">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="8c97e-137">public ブール値は[Defaultscriptし enabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-137">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="8c97e-138">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="8c97e-138">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="8c97e-139">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8c97e-139">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="8c97e-140">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-140">AreDevToolsEnabled</span></span> 

<span data-ttu-id="8c97e-141">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-141">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="8c97e-142">公開ブール型の[Devtaskenabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-142">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="8c97e-143">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-143">It is true by default.</span></span>

#### <span data-ttu-id="8c97e-144">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="8c97e-144">AreHostObjectsAllowed</span></span> 

<span data-ttu-id="8c97e-145">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-145">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="8c97e-146">public bool は[hostオブジェクトを許可](#arehostobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="8c97e-146">public bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span></span>

<span data-ttu-id="8c97e-147">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-147">Defaults to TRUE.</span></span>

#### <span data-ttu-id="8c97e-148">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-148">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="8c97e-149">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8c97e-149">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="8c97e-150">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-150">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="8c97e-151">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-151">Defaults to TRUE.</span></span> <span data-ttu-id="8c97e-152">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-152">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="8c97e-153">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-153">IsScriptEnabled</span></span> 

<span data-ttu-id="8c97e-154">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-154">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="8c97e-155">public bool [Isscriptenabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-155">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="8c97e-156">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-156">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="8c97e-157">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-157">It is true by default.</span></span>

#### <span data-ttu-id="8c97e-158">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-158">IsStatusBarEnabled</span></span> 

<span data-ttu-id="8c97e-159">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8c97e-159">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="8c97e-160">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-160">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="8c97e-161">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-161">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="8c97e-162">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-162">It is true by default.</span></span>

#### <span data-ttu-id="8c97e-163">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-163">IsWebMessageEnabled</span></span> 

<span data-ttu-id="8c97e-164">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-164">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="8c97e-165">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-165">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="8c97e-166">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8c97e-166">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="8c97e-167">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8c97e-167">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="8c97e-168">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="8c97e-168">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="8c97e-169">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="8c97e-169">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="8c97e-170">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-170">It is true by default.</span></span>

#### <span data-ttu-id="8c97e-171">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="8c97e-171">IsZoomControlEnabled</span></span> 

<span data-ttu-id="8c97e-172">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-172">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="8c97e-173">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="8c97e-173">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="8c97e-174">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="8c97e-174">Defaults to TRUE.</span></span> <span data-ttu-id="8c97e-175">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c97e-175">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

