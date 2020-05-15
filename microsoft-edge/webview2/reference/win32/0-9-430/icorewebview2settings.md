---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 79f6e2712cab6d18025bd49ab0e7ceba01495d65
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654552"
---
# <span data-ttu-id="f9ac3-104">インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="f9ac3-104">interface ICoreWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="f9ac3-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="f9ac3-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="f9ac3-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="f9ac3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f9ac3-108">Summary</span></span>

 <span data-ttu-id="f9ac3-109">Members</span><span class="sxs-lookup"><span data-stu-id="f9ac3-109">Members</span></span>                        | <span data-ttu-id="f9ac3-110">説明</span><span class="sxs-lookup"><span data-stu-id="f9ac3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f9ac3-111">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-111">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="f9ac3-112">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-112">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="f9ac3-113">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-113">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="f9ac3-114">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-114">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="f9ac3-115">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-115">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="f9ac3-116">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-116">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="f9ac3-117">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-117">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="f9ac3-118">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-118">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="f9ac3-119">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-119">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="f9ac3-120">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-120">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="f9ac3-121">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-121">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="f9ac3-122">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-122">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="f9ac3-123">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-123">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="f9ac3-124">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="f9ac3-125">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-125">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="f9ac3-126">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-126">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="f9ac3-127">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-127">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="f9ac3-128">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-128">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="f9ac3-129">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-129">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="f9ac3-130">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-130">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="f9ac3-131">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-131">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="f9ac3-132">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="f9ac3-133">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-133">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="f9ac3-134">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-134">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="f9ac3-135">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="f9ac3-135">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="f9ac3-136">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-136">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="f9ac3-137">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="f9ac3-137">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="f9ac3-138">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-138">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="f9ac3-139">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-139">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="f9ac3-140">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-140">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="f9ac3-141">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-141">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="f9ac3-142">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-142">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="f9ac3-143">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-143">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="f9ac3-144">Members</span><span class="sxs-lookup"><span data-stu-id="f9ac3-144">Members</span></span>

#### <span data-ttu-id="f9ac3-145">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-145">get_IsScriptEnabled</span></span> 

<span data-ttu-id="f9ac3-146">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-146">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="f9ac3-147">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-147">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="f9ac3-148">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-148">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="f9ac3-149">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-149">It is true by default.</span></span>

```cpp
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
```

#### <span data-ttu-id="f9ac3-150">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-150">put_IsScriptEnabled</span></span> 

<span data-ttu-id="f9ac3-151">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-151">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="f9ac3-152">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-152">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="f9ac3-153">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-153">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="f9ac3-154">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-154">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="f9ac3-155">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-155">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="f9ac3-156">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-156">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="f9ac3-157">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-157">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="f9ac3-158">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-158">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="f9ac3-159">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-159">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="f9ac3-160">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-160">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="f9ac3-161">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-161">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="f9ac3-162">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-162">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="f9ac3-163">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-163">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="f9ac3-164">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-164">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="f9ac3-165">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-165">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="f9ac3-166">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-166">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="f9ac3-167">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-167">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="f9ac3-168">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-168">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="f9ac3-169">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-169">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="f9ac3-170">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-170">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="f9ac3-171">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-171">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="f9ac3-172">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-172">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="f9ac3-173">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-173">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="f9ac3-174">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-174">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="f9ac3-175">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-175">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="f9ac3-176">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-176">It is true by default.</span></span>

#### <span data-ttu-id="f9ac3-177">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-177">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="f9ac3-178">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-178">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="f9ac3-179">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-179">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="f9ac3-180">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-180">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="f9ac3-181">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-181">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="f9ac3-182">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-182">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="f9ac3-183">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-183">It is true by default.</span></span>

#### <span data-ttu-id="f9ac3-184">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-184">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="f9ac3-185">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-185">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="f9ac3-186">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-186">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="f9ac3-187">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-187">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="f9ac3-188">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-188">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="f9ac3-189">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-189">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="f9ac3-190">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-190">Defaults to TRUE.</span></span>

```cpp
            BOOL allowContextMenus;
            CHECK_FAILURE(m_settings->get_AreDefaultContextMenusEnabled(
                &allowContextMenus));
            if (allowContextMenus) {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(FALSE));
                MessageBox(nullptr,
                L"Context menus will be disabled after the next navigation.",
                L"Settings change", MB_OK);
            }
            else {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(TRUE));
                MessageBox(nullptr,
                    L"Context menus will be enabled after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="f9ac3-191">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-191">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="f9ac3-192">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-192">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="f9ac3-193">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-193">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="f9ac3-194">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="f9ac3-194">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="f9ac3-195">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-195">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="f9ac3-196">パブリック HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-196">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="f9ac3-197">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-197">Defaults to TRUE.</span></span>

```cpp
            BOOL allowRemoteObjects;
            CHECK_FAILURE(m_settings->get_AreRemoteObjectsAllowed(&allowRemoteObjects));
            if (allowRemoteObjects)
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(FALSE));
                MessageBox(
                    nullptr, L"Access to remote objects will be denied after the next navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(TRUE));
                MessageBox(
                    nullptr, L"Access to remote objects will be allowed after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="f9ac3-198">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="f9ac3-198">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="f9ac3-199">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-199">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="f9ac3-200">パブリック HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-200">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="f9ac3-201">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-201">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="f9ac3-202">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-202">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="f9ac3-203">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-203">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="f9ac3-204">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-204">Defaults to TRUE.</span></span> <span data-ttu-id="f9ac3-205">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは put_ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-205">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via put_ZoomFactor API.</span></span>

```cpp
            BOOL zoomControlEnabled;
            CHECK_FAILURE(m_settings->get_IsZoomControlEnabled(&zoomControlEnabled));
            if (zoomControlEnabled)
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(FALSE));
                MessageBox(
                    nullptr, L"Zoom control is disabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(TRUE));
                MessageBox(
                    nullptr, L"Zoom control is enabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
```

#### <span data-ttu-id="f9ac3-206">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="f9ac3-206">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="f9ac3-207">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9ac3-207">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="f9ac3-208">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="f9ac3-208">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

