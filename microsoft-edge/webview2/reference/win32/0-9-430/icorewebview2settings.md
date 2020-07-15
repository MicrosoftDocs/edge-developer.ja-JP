---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 2596b2352f36dce6773de2e60e0442ff5fa3b6d5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880221"
---
# <span data-ttu-id="ae3fc-104">0.9.430-インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="ae3fc-104">0.9.430 - interface ICoreWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="ae3fc-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="ae3fc-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="ae3fc-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="ae3fc-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ae3fc-108">Summary</span></span>

 <span data-ttu-id="ae3fc-109">Members</span><span class="sxs-lookup"><span data-stu-id="ae3fc-109">Members</span></span>                        | <span data-ttu-id="ae3fc-110">説明</span><span class="sxs-lookup"><span data-stu-id="ae3fc-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ae3fc-111">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-111">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="ae3fc-112">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-112">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="ae3fc-113">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-113">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="ae3fc-114">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-114">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="ae3fc-115">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-115">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="ae3fc-116">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-116">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="ae3fc-117">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-117">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="ae3fc-118">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-118">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="ae3fc-119">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-119">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="ae3fc-120">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-120">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="ae3fc-121">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-121">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="ae3fc-122">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-122">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="ae3fc-123">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-123">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="ae3fc-124">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="ae3fc-125">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-125">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="ae3fc-126">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-126">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="ae3fc-127">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-127">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="ae3fc-128">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-128">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="ae3fc-129">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-129">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="ae3fc-130">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-130">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="ae3fc-131">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-131">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="ae3fc-132">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="ae3fc-133">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-133">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="ae3fc-134">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-134">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="ae3fc-135">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="ae3fc-135">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="ae3fc-136">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-136">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="ae3fc-137">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="ae3fc-137">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="ae3fc-138">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-138">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="ae3fc-139">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-139">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="ae3fc-140">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-140">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="ae3fc-141">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-141">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="ae3fc-142">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-142">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="ae3fc-143">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-143">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="ae3fc-144">Members</span><span class="sxs-lookup"><span data-stu-id="ae3fc-144">Members</span></span>

#### <span data-ttu-id="ae3fc-145">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-145">get_IsScriptEnabled</span></span> 

<span data-ttu-id="ae3fc-146">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-146">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="ae3fc-147">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-147">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="ae3fc-148">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-148">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="ae3fc-149">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-149">It is true by default.</span></span>

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

#### <span data-ttu-id="ae3fc-150">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-150">put_IsScriptEnabled</span></span> 

<span data-ttu-id="ae3fc-151">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-151">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="ae3fc-152">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-152">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="ae3fc-153">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-153">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="ae3fc-154">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-154">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="ae3fc-155">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-155">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="ae3fc-156">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-156">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="ae3fc-157">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-157">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="ae3fc-158">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-158">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="ae3fc-159">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-159">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="ae3fc-160">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-160">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="ae3fc-161">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-161">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="ae3fc-162">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-162">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="ae3fc-163">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-163">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="ae3fc-164">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-164">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="ae3fc-165">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-165">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="ae3fc-166">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-166">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="ae3fc-167">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-167">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="ae3fc-168">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-168">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="ae3fc-169">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-169">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="ae3fc-170">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-170">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="ae3fc-171">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-171">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="ae3fc-172">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-172">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="ae3fc-173">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-173">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="ae3fc-174">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-174">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="ae3fc-175">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-175">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="ae3fc-176">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-176">It is true by default.</span></span>

#### <span data-ttu-id="ae3fc-177">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-177">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="ae3fc-178">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-178">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="ae3fc-179">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-179">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="ae3fc-180">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-180">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="ae3fc-181">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-181">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="ae3fc-182">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-182">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="ae3fc-183">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-183">It is true by default.</span></span>

#### <span data-ttu-id="ae3fc-184">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-184">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="ae3fc-185">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-185">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="ae3fc-186">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-186">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="ae3fc-187">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-187">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="ae3fc-188">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-188">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="ae3fc-189">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-189">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="ae3fc-190">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-190">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="ae3fc-191">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-191">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="ae3fc-192">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-192">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="ae3fc-193">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-193">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="ae3fc-194">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="ae3fc-194">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="ae3fc-195">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-195">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="ae3fc-196">パブリック HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-196">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="ae3fc-197">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-197">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="ae3fc-198">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="ae3fc-198">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="ae3fc-199">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-199">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="ae3fc-200">パブリック HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-200">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="ae3fc-201">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-201">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="ae3fc-202">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-202">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="ae3fc-203">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-203">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="ae3fc-204">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-204">Defaults to TRUE.</span></span> <span data-ttu-id="ae3fc-205">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは put_ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-205">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via put_ZoomFactor API.</span></span>

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

#### <span data-ttu-id="ae3fc-206">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="ae3fc-206">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="ae3fc-207">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae3fc-207">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="ae3fc-208">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="ae3fc-208">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

