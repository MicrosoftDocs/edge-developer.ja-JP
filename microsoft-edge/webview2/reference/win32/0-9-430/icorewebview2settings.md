---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 70ccef9e99b3649ceca49b736570ba416cf73ebd
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883988"
---
# <span data-ttu-id="e7954-104">0.9.430-インターフェイス ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="e7954-104">0.9.430 - interface ICoreWebView2Settings</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="e7954-105">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e7954-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="e7954-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e7954-106">Summary</span></span>

 <span data-ttu-id="e7954-107">Members</span><span class="sxs-lookup"><span data-stu-id="e7954-107">Members</span></span>                        | <span data-ttu-id="e7954-108">説明</span><span class="sxs-lookup"><span data-stu-id="e7954-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e7954-109">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-109">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="e7954-110">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-110">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="e7954-111">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-111">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="e7954-112">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-112">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="e7954-113">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-113">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="e7954-114">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-114">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="e7954-115">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-115">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="e7954-116">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-116">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="e7954-117">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-117">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="e7954-118">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-118">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="e7954-119">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-119">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="e7954-120">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-120">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="e7954-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="e7954-122">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="e7954-123">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-123">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="e7954-124">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-124">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="e7954-125">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-125">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="e7954-126">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-126">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="e7954-127">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-127">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="e7954-128">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-128">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="e7954-129">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-129">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="e7954-130">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="e7954-130">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="e7954-131">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-131">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="e7954-132">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-132">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="e7954-133">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="e7954-133">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="e7954-134">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-134">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="e7954-135">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="e7954-135">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="e7954-136">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-136">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="e7954-137">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-137">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="e7954-138">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="e7954-138">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="e7954-139">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-139">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="e7954-140">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-140">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="e7954-141">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="e7954-141">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="e7954-142">Members</span><span class="sxs-lookup"><span data-stu-id="e7954-142">Members</span></span>

#### <span data-ttu-id="e7954-143">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-143">get_IsScriptEnabled</span></span> 

<span data-ttu-id="e7954-144">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-144">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="e7954-145">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-145">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="e7954-146">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-146">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="e7954-147">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="e7954-147">It is true by default.</span></span>

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

#### <span data-ttu-id="e7954-148">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-148">put_IsScriptEnabled</span></span> 

<span data-ttu-id="e7954-149">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-149">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="e7954-150">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-150">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="e7954-151">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-151">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="e7954-152">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-152">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="e7954-153">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-153">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="e7954-154">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e7954-154">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="e7954-155">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e7954-155">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="e7954-156">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="e7954-156">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="e7954-157">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="e7954-157">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="e7954-158">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="e7954-158">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="e7954-159">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-159">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="e7954-160">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-160">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="e7954-161">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-161">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="e7954-162">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-162">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="e7954-163">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-163">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="e7954-164">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="e7954-164">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="e7954-165">False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="e7954-165">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="e7954-166">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e7954-166">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="e7954-167">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-167">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="e7954-168">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-168">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="e7954-169">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="e7954-169">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="e7954-170">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-170">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="e7954-171">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-171">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="e7954-172">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-172">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="e7954-173">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-173">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="e7954-174">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="e7954-174">It is true by default.</span></span>

#### <span data-ttu-id="e7954-175">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-175">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="e7954-176">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-176">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="e7954-177">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-177">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="e7954-178">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-178">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="e7954-179">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7954-179">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="e7954-180">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-180">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="e7954-181">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="e7954-181">It is true by default.</span></span>

#### <span data-ttu-id="e7954-182">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-182">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="e7954-183">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-183">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="e7954-184">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-184">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="e7954-185">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-185">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="e7954-186">AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="e7954-186">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="e7954-187">パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-187">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="e7954-188">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="e7954-188">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="e7954-189">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-189">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="e7954-190">AreDefaultContextMenusEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-190">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="e7954-191">パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-191">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="e7954-192">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="e7954-192">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="e7954-193">AreRemoteObjectsAllowed プロパティは、リモートオブジェクトが webview のページからアクセスできるかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7954-193">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="e7954-194">パブリック HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(ブール \* 使用可能)</span><span class="sxs-lookup"><span data-stu-id="e7954-194">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="e7954-195">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="e7954-195">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="e7954-196">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="e7954-196">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="e7954-197">AreRemoteObjectsAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-197">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="e7954-198">パブリック HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(ブール値が許可されています)</span><span class="sxs-lookup"><span data-stu-id="e7954-198">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="e7954-199">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-199">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="e7954-200">IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。</span><span class="sxs-lookup"><span data-stu-id="e7954-200">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="e7954-201">パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール \* enabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-201">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="e7954-202">既定値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="e7954-202">Defaults to TRUE.</span></span> <span data-ttu-id="e7954-203">無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは put_ZoomFactor API を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="e7954-203">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via put_ZoomFactor API.</span></span>

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

#### <span data-ttu-id="e7954-204">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="e7954-204">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="e7954-205">IsZoomControlEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7954-205">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="e7954-206">パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span><span class="sxs-lookup"><span data-stu-id="e7954-206">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

