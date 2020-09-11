---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Settings
ms.openlocfilehash: 1ad6754d2ff59a92e107c66644e389582ff6053b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012319"
---
# <span data-ttu-id="73ed3-104">インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="73ed3-104">interface ICoreWebView2Settings</span></span> 

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="73ed3-105">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="73ed3-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="73ed3-106">Summary</span></span>

 <span data-ttu-id="73ed3-107">Members</span><span class="sxs-lookup"><span data-stu-id="73ed3-107">Members</span></span>                        | <span data-ttu-id="73ed3-108">説明</span><span class="sxs-lookup"><span data-stu-id="73ed3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="73ed3-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="73ed3-110">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>
[<span data-ttu-id="73ed3-111">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-111">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="73ed3-112">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-112">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="73ed3-113">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-113">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="73ed3-114">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-114">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="73ed3-115">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="73ed3-115">get_AreHostObjectsAllowed</span></span>](#get_arehostobjectsallowed) | <span data-ttu-id="73ed3-116">Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-116">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>
[<span data-ttu-id="73ed3-117">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-117">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="73ed3-118">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="73ed3-118">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="73ed3-119">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-119">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="73ed3-120">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-120">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="73ed3-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="73ed3-122">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="73ed3-123">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-123">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="73ed3-124">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-124">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="73ed3-125">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-125">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="73ed3-126">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-126">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="73ed3-127">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-127">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="73ed3-128">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-128">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="73ed3-129">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-129">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="73ed3-130">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-130">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="73ed3-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="73ed3-132">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-132">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="73ed3-133">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="73ed3-133">put_AreHostObjectsAllowed</span></span>](#put_arehostobjectsallowed) | <span data-ttu-id="73ed3-134">Arehostオブジェクト許可プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-134">Set the AreHostObjectsAllowed property.</span></span>
[<span data-ttu-id="73ed3-135">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-135">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="73ed3-136">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-136">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="73ed3-137">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-137">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="73ed3-138">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-138">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="73ed3-139">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-139">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="73ed3-140">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-140">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="73ed3-141">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-141">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="73ed3-142">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-142">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="73ed3-143">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-143">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="73ed3-144">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-144">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="73ed3-145">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="73ed3-145">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="73ed3-146">Members</span><span class="sxs-lookup"><span data-stu-id="73ed3-146">Members</span></span>

#### <span data-ttu-id="73ed3-147">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-147">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="73ed3-148">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが WebView でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-148">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>

> <span data-ttu-id="73ed3-149">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-149">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="73ed3-150">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-150">It is true by default.</span></span>

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

#### <span data-ttu-id="73ed3-151">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-151">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="73ed3-152">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-152">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="73ed3-153">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="73ed3-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="73ed3-154">False に設定すると、WebView には、既定の JavaScript ダイアログボックスは表示されません (具体的には、JavaScript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="73ed3-154">If set to false, then WebView won't render the default JavaScript dialog box (Specifically those shown by the JavaScript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="73ed3-155">代わりに、イベントハンドラーが add_ScriptDialogOpening によって設定された場合は、そのダイアログのすべての情報を含むイベントが WebView に送信され、ホストアプリは独自のカスタム UI を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-155">Instead, if an event handler is set via add_ScriptDialogOpening, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span> <span data-ttu-id="73ed3-156">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-156">It is true by default.</span></span>

#### <span data-ttu-id="73ed3-157">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-157">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="73ed3-158">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-158">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="73ed3-159">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-159">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="73ed3-160">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-160">It is true by default.</span></span>

#### <span data-ttu-id="73ed3-161">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="73ed3-161">get_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="73ed3-162">Arehostobjects Allowed プロパティは、WebView 内のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-162">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>

> <span data-ttu-id="73ed3-163">パブリック HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="73ed3-163">public HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="73ed3-164">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-164">It is true by default.</span></span>

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

#### <span data-ttu-id="73ed3-165">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-165">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="73ed3-166">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="73ed3-166">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="73ed3-167">パブリック HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-167">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="73ed3-168">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-168">It is true by default.</span></span> <span data-ttu-id="73ed3-169">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-169">When disabled, blank page will be shown when related error happens.</span></span>

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

#### <span data-ttu-id="73ed3-170">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-170">get_IsScriptEnabled</span></span> 

<span data-ttu-id="73ed3-171">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-171">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="73ed3-172">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-172">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="73ed3-173">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-173">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="73ed3-174">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-174">It is true by default.</span></span>

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

#### <span data-ttu-id="73ed3-175">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-175">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="73ed3-176">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-176">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="73ed3-177">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-177">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="73ed3-178">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-178">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="73ed3-179">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-179">It is true by default.</span></span>

#### <span data-ttu-id="73ed3-180">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-180">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="73ed3-181">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-181">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="73ed3-182">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-182">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="73ed3-183">True に設定されている場合、ホストから WebView のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="73ed3-183">If set to true, communication from the host to the WebView's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="73ed3-184">WebView の最上位レベルの HTML ドキュメントからホストへの通信は、postMessage 関数と add_WebMessageReceived メソッドで許可されています (詳しくは、「add_WebMessageReceived ドキュメント」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="73ed3-184">Communication from the WebView's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and add_WebMessageReceived method (see add_WebMessageReceived documentation for details).</span></span> <span data-ttu-id="73ed3-185">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="73ed3-185">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="73ed3-186">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="73ed3-186">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="73ed3-187">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-187">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="73ed3-188">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-188">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="73ed3-189">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-189">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="73ed3-190">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-190">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="73ed3-191">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="73ed3-191">It is true by default.</span></span> <span data-ttu-id="73ed3-192">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="73ed3-192">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

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

#### <span data-ttu-id="73ed3-193">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-193">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="73ed3-194">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-194">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="73ed3-195">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-195">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="73ed3-196">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-196">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="73ed3-197">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-197">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="73ed3-198">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="73ed3-198">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="73ed3-199">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-199">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="73ed3-200">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-200">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="73ed3-201">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-201">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="73ed3-202">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="73ed3-202">put_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="73ed3-203">Arehostオブジェクト許可プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-203">Set the AreHostObjectsAllowed property.</span></span>

> <span data-ttu-id="73ed3-204">パブリック HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="73ed3-204">public HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="73ed3-205">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-205">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="73ed3-206">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-206">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="73ed3-207">パブリック HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-207">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="73ed3-208">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-208">put_IsScriptEnabled</span></span> 

<span data-ttu-id="73ed3-209">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-209">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="73ed3-210">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-210">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="73ed3-211">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-211">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="73ed3-212">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-212">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="73ed3-213">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-213">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="73ed3-214">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-214">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="73ed3-215">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-215">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="73ed3-216">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-216">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="73ed3-217">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="73ed3-217">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="73ed3-218">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73ed3-218">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="73ed3-219">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="73ed3-219">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

