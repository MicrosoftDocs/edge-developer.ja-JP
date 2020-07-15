---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: a996660bb667ca0e556326e0bf2b71c15b9344c2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880333"
---
# <span data-ttu-id="fca2c-104">0.9.515-インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="fca2c-104">0.9.515 - interface ICoreWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="fca2c-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fca2c-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="fca2c-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fca2c-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="fca2c-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="fca2c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="fca2c-108">Summary</span></span>

 <span data-ttu-id="fca2c-109">Members</span><span class="sxs-lookup"><span data-stu-id="fca2c-109">Members</span></span>                        | <span data-ttu-id="fca2c-110">説明</span><span class="sxs-lookup"><span data-stu-id="fca2c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fca2c-111">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-111">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="fca2c-112">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="fca2c-113">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-113">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="fca2c-114">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="fca2c-115">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-115">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="fca2c-116">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="fca2c-117">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="fca2c-117">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="fca2c-118">AreRemoteObjectsAllowed プロパティは、webview のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-118">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="fca2c-119">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-119">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="fca2c-120">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fca2c-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="fca2c-121">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-121">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="fca2c-122">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="fca2c-123">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-123">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="fca2c-124">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="fca2c-125">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-125">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="fca2c-126">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="fca2c-127">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-127">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="fca2c-128">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="fca2c-129">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-129">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="fca2c-130">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-130">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="fca2c-131">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-131">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="fca2c-132">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-132">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="fca2c-133">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-133">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="fca2c-134">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-134">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="fca2c-135">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="fca2c-135">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="fca2c-136">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-136">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="fca2c-137">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-137">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="fca2c-138">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-138">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="fca2c-139">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-139">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="fca2c-140">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-140">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="fca2c-141">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-141">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="fca2c-142">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-142">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="fca2c-143">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-143">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="fca2c-144">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-144">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="fca2c-145">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-145">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="fca2c-146">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-146">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="fca2c-147">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="fca2c-147">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="fca2c-148">Members</span><span class="sxs-lookup"><span data-stu-id="fca2c-148">Members</span></span>

#### <span data-ttu-id="fca2c-149">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-149">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="fca2c-150">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-150">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="fca2c-151">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-151">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="fca2c-152">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-152">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="fca2c-153">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-153">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="fca2c-154">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-154">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="fca2c-155">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="fca2c-155">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="fca2c-156">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="fca2c-156">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="fca2c-157">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fca2c-157">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="fca2c-158">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-158">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="fca2c-159">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-159">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="fca2c-160">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-160">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="fca2c-161">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-161">It is true by default.</span></span>

#### <span data-ttu-id="fca2c-162">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="fca2c-162">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="fca2c-163">AreRemoteObjectsAllowed プロパティは、webview のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-163">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="fca2c-164">パブリック HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="fca2c-164">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="fca2c-165">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-165">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="fca2c-166">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-166">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="fca2c-167">IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fca2c-167">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="fca2c-168">パブリック HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-168">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="fca2c-169">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-169">Defaults to TRUE.</span></span> <span data-ttu-id="fca2c-170">無効にすると、関連するエラーが発生したときに空白のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-170">When disabled, blank page will be shown when related error happens.</span></span>

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

#### <span data-ttu-id="fca2c-171">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-171">get_IsScriptEnabled</span></span> 

<span data-ttu-id="fca2c-172">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-172">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="fca2c-173">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-173">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="fca2c-174">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-174">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="fca2c-175">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-175">It is true by default.</span></span>

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

#### <span data-ttu-id="fca2c-176">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-176">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="fca2c-177">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-177">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="fca2c-178">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-178">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="fca2c-179">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-179">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="fca2c-180">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-180">It is true by default.</span></span>

#### <span data-ttu-id="fca2c-181">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-181">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="fca2c-182">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-182">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="fca2c-183">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-183">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="fca2c-184">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fca2c-184">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="fca2c-185">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fca2c-185">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="fca2c-186">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="fca2c-186">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="fca2c-187">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="fca2c-187">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="fca2c-188">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-188">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="fca2c-189">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-189">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="fca2c-190">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-190">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="fca2c-191">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-191">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="fca2c-192">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="fca2c-192">Defaults to TRUE.</span></span> <span data-ttu-id="fca2c-193">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="fca2c-193">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

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

#### <span data-ttu-id="fca2c-194">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-194">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="fca2c-195">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-195">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="fca2c-196">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-196">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="fca2c-197">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-197">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="fca2c-198">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-198">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="fca2c-199">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="fca2c-199">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="fca2c-200">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-200">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="fca2c-201">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-201">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="fca2c-202">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-202">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="fca2c-203">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="fca2c-203">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="fca2c-204">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-204">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="fca2c-205">パブリック HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="fca2c-205">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="fca2c-206">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-206">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="fca2c-207">IsBuiltInErrorPageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-207">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="fca2c-208">パブリック HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-208">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="fca2c-209">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-209">put_IsScriptEnabled</span></span> 

<span data-ttu-id="fca2c-210">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-210">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="fca2c-211">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-211">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="fca2c-212">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-212">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="fca2c-213">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-213">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="fca2c-214">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-214">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="fca2c-215">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-215">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="fca2c-216">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-216">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="fca2c-217">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-217">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="fca2c-218">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="fca2c-218">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="fca2c-219">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fca2c-219">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="fca2c-220">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="fca2c-220">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

