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
ms.openlocfilehash: 004e2cbac7da8780c26d4eebb35e0ab2e47e41dd
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699075"
---
# <span data-ttu-id="cdc14-104">インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="cdc14-104">interface ICoreWebView2Settings</span></span> 

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="cdc14-105">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="cdc14-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="cdc14-106">Summary</span></span>

 <span data-ttu-id="cdc14-107">Members</span><span class="sxs-lookup"><span data-stu-id="cdc14-107">Members</span></span>                        | <span data-ttu-id="cdc14-108">説明</span><span class="sxs-lookup"><span data-stu-id="cdc14-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cdc14-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="cdc14-110">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="cdc14-111">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-111">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="cdc14-112">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-112">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="cdc14-113">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-113">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="cdc14-114">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-114">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="cdc14-115">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="cdc14-115">get_AreHostObjectsAllowed</span></span>](#get_arehostobjectsallowed) | <span data-ttu-id="cdc14-116">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-116">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="cdc14-117">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-117">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="cdc14-118">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cdc14-118">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="cdc14-119">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-119">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="cdc14-120">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-120">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="cdc14-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="cdc14-122">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="cdc14-123">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-123">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="cdc14-124">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-124">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="cdc14-125">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-125">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="cdc14-126">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-126">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="cdc14-127">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-127">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="cdc14-128">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-128">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="cdc14-129">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-129">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="cdc14-130">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-130">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="cdc14-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="cdc14-132">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-132">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="cdc14-133">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="cdc14-133">put_AreHostObjectsAllowed</span></span>](#put_arehostobjectsallowed) | <span data-ttu-id="cdc14-134">Arehostオブジェクト許可プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-134">Set the AreHostObjectsAllowed property.</span></span>
[<span data-ttu-id="cdc14-135">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-135">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="cdc14-136">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-136">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="cdc14-137">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-137">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="cdc14-138">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-138">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="cdc14-139">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-139">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="cdc14-140">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-140">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="cdc14-141">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-141">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="cdc14-142">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-142">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="cdc14-143">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-143">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="cdc14-144">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-144">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="cdc14-145">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="cdc14-145">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="cdc14-146">Members</span><span class="sxs-lookup"><span data-stu-id="cdc14-146">Members</span></span>

#### <span data-ttu-id="cdc14-147">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-147">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="cdc14-148">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-148">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="cdc14-149">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-149">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="cdc14-150">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-150">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="cdc14-151">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-151">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="cdc14-152">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-152">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="cdc14-153">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="cdc14-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="cdc14-154">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="cdc14-154">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="cdc14-155">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cdc14-155">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="cdc14-156">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-156">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="cdc14-157">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-157">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="cdc14-158">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-158">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="cdc14-159">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-159">It is true by default.</span></span>

#### <span data-ttu-id="cdc14-160">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="cdc14-160">get_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="cdc14-161">Arehostobjects Allowed プロパティは、webview 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-161">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="cdc14-162">パブリック HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="cdc14-162">public HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="cdc14-163">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-163">Defaults to TRUE.</span></span>

```cpp
            BOOL allowHostObjects;
            CHECK_FAILURE(m_settings->get_AreHostObjectsAllowed(&allowHostObjects));
            if (allowHostObjects)
            {
                CHECK_FAILURE(m_settings->put_AreHostObjectsAllowed(FALSE));
                MessageBox(
                    nullptr, L"Access to host objects will be denied after the next navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_AreHostObjectsAllowed(TRUE));
                MessageBox(
                    nullptr, L"Access to host objects will be allowed after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="cdc14-164">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-164">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="cdc14-165">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cdc14-165">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="cdc14-166">パブリック HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-166">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="cdc14-167">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-167">Defaults to TRUE.</span></span> <span data-ttu-id="cdc14-168">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-168">When disabled, blank page will be shown when related error happens.</span></span>

```cpp
            BOOL enabled;
            CHECK_FAILURE(m_settings->get_IsBuiltInErrorPageEnabled(&enabled));
            if (enabled)
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(FALSE));
                MessageBox(
                    nullptr, L"Built-in error page will be disabled for future navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(TRUE));
                MessageBox(
                    nullptr, L"Built-in error page will be enabled for future navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="cdc14-169">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-169">get_IsScriptEnabled</span></span> 

<span data-ttu-id="cdc14-170">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-170">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="cdc14-171">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-171">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="cdc14-172">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-172">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="cdc14-173">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-173">It is true by default.</span></span>

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

#### <span data-ttu-id="cdc14-174">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-174">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="cdc14-175">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-175">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="cdc14-176">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-176">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="cdc14-177">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-177">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="cdc14-178">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-178">It is true by default.</span></span>

#### <span data-ttu-id="cdc14-179">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-179">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="cdc14-180">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-180">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="cdc14-181">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-181">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="cdc14-182">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="cdc14-182">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="cdc14-183">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="cdc14-183">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="cdc14-184">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="cdc14-184">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="cdc14-185">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="cdc14-185">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="cdc14-186">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-186">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="cdc14-187">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-187">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="cdc14-188">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-188">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="cdc14-189">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-189">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="cdc14-190">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="cdc14-190">Defaults to TRUE.</span></span> <span data-ttu-id="cdc14-191">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="cdc14-191">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

```cpp
            BOOL zoomControlEnabled;
            CHECK_FAILURE(m_settings->get_IsZoomControlEnabled(&zoomControlEnabled));
            if (zoomControlEnabled)
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(FALSE));
                MessageBox(
                    nullptr, L"Zoom control will be disabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(TRUE));
                MessageBox(
                    nullptr, L"Zoom control will be enabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
```

#### <span data-ttu-id="cdc14-192">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-192">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="cdc14-193">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-193">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="cdc14-194">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-194">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="cdc14-195">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-195">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="cdc14-196">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-196">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="cdc14-197">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="cdc14-197">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="cdc14-198">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-198">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="cdc14-199">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-199">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="cdc14-200">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-200">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="cdc14-201">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="cdc14-201">put_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="cdc14-202">Arehostオブジェクト許可プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-202">Set the AreHostObjectsAllowed property.</span></span>

> <span data-ttu-id="cdc14-203">パブリック HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="cdc14-203">public HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="cdc14-204">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-204">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="cdc14-205">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-205">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="cdc14-206">パブリック HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-206">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="cdc14-207">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-207">put_IsScriptEnabled</span></span> 

<span data-ttu-id="cdc14-208">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-208">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="cdc14-209">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-209">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="cdc14-210">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-210">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="cdc14-211">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-211">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="cdc14-212">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-212">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="cdc14-213">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-213">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="cdc14-214">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-214">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="cdc14-215">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-215">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="cdc14-216">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="cdc14-216">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="cdc14-217">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdc14-217">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="cdc14-218">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="cdc14-218">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

