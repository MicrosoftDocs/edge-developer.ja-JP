---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2Settings。
ms.openlocfilehash: 87b78956c29dac74bd023556a8c495222d248e9f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012245"
---
# <span data-ttu-id="3ea6a-104">WebView2 クラス (CoreWebView2Settings クラス)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-104">Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

<span data-ttu-id="3ea6a-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="3ea6a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="3ea6a-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="3ea6a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="3ea6a-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="3ea6a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3ea6a-108">Summary</span></span>

 <span data-ttu-id="3ea6a-109">Members</span><span class="sxs-lookup"><span data-stu-id="3ea6a-109">Members</span></span>                        | <span data-ttu-id="3ea6a-110">説明</span><span class="sxs-lookup"><span data-stu-id="3ea6a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3ea6a-111">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-111">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="3ea6a-112">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>
[<span data-ttu-id="3ea6a-113">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-113">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="3ea6a-114">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="3ea6a-115">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-115">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="3ea6a-116">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="3ea6a-117">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="3ea6a-117">AreHostObjectsAllowed</span></span>](#arehostobjectsallowed) | <span data-ttu-id="3ea6a-118">Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-118">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>
[<span data-ttu-id="3ea6a-119">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-119">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="3ea6a-120">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="3ea6a-121">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-121">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="3ea6a-122">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="3ea6a-123">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-123">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="3ea6a-124">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="3ea6a-125">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-125">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="3ea6a-126">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="3ea6a-127">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-127">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="3ea6a-128">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="3ea6a-129">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-129">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="3ea6a-130">Members</span><span class="sxs-lookup"><span data-stu-id="3ea6a-130">Members</span></span>

#### <span data-ttu-id="3ea6a-131">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-131">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="3ea6a-132">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>

> <span data-ttu-id="3ea6a-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="3ea6a-134">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-134">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-135">Aredefaultscriptて Enabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-135">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="3ea6a-136">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-136">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="3ea6a-137">public ブール値は [Defaultscriptし enabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-137">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="3ea6a-138">False に設定すると、WebView には、既定の JavaScript ダイアログボックスは表示されません (具体的には、JavaScript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-138">If set to false, then WebView won't render the default JavaScript dialog box (Specifically those shown by the JavaScript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="3ea6a-139">True に設定されている場合は、Scriptui> 左中イベントをサブスクライブして、ダイアログのすべての情報が含まれ、ホストアプリが独自のカスタム UI を表示できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-139">If set to true, one can also subscribe to ScriptDialogOpening event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span> <span data-ttu-id="3ea6a-140">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-140">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-141">Aredev| Enabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-141">AreDevToolsEnabled</span></span> 

<span data-ttu-id="3ea6a-142">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-142">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="3ea6a-143">公開ブール型の [Devtaskenabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-143">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="3ea6a-144">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-144">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-145">Arehostオブジェクトが許可されています</span><span class="sxs-lookup"><span data-stu-id="3ea6a-145">AreHostObjectsAllowed</span></span> 

<span data-ttu-id="3ea6a-146">Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-146">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>

> <span data-ttu-id="3ea6a-147">public bool は [hostオブジェクトを許可](#arehostobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-147">public bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span></span>

<span data-ttu-id="3ea6a-148">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-148">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-149">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-149">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="3ea6a-150">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-150">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="3ea6a-151">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-151">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="3ea6a-152">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-152">It is true by default.</span></span> <span data-ttu-id="3ea6a-153">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-153">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="3ea6a-154">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-154">IsScriptEnabled</span></span> 

<span data-ttu-id="3ea6a-155">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-155">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="3ea6a-156">public bool [Isscriptenabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-156">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="3ea6a-157">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-157">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="3ea6a-158">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-158">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-159">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-159">IsStatusBarEnabled</span></span> 

<span data-ttu-id="3ea6a-160">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-160">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="3ea6a-161">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-161">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="3ea6a-162">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-162">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="3ea6a-163">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-163">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-164">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-164">IsWebMessageEnabled</span></span> 

<span data-ttu-id="3ea6a-165">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-165">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="3ea6a-166">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-166">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="3ea6a-167">True に設定されている場合、ホストから WebView のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-167">If set to true, communication from the host to the WebView's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="3ea6a-168">WebView の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と WebMessageReceived イベントによって許可されます (詳しくは WebMessageReceived のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-168">Communication from the WebView's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the WebMessageReceived event (see WebMessageReceived documentation for details).</span></span> <span data-ttu-id="3ea6a-169">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-169">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="3ea6a-170">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-170">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="3ea6a-171">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-171">It is true by default.</span></span>

#### <span data-ttu-id="3ea6a-172">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="3ea6a-172">IsZoomControlEnabled</span></span> 

<span data-ttu-id="3ea6a-173">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-173">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="3ea6a-174">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="3ea6a-174">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="3ea6a-175">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-175">It is true by default.</span></span> <span data-ttu-id="3ea6a-176">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="3ea6a-176">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

