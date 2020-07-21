---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 649506b28e0ecdbff33b44bbd8010ddb3d2a66b0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885801"
---
# <span data-ttu-id="38f2d-104">0.8.355-インターフェイス IWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="38f2d-104">0.8.355 - interface IWebView2Settings</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings
  : public IUnknown
```

<span data-ttu-id="38f2d-105">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="38f2d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="38f2d-106">Summary</span></span>

 <span data-ttu-id="38f2d-107">Members</span><span class="sxs-lookup"><span data-stu-id="38f2d-107">Members</span></span>                        | <span data-ttu-id="38f2d-108">説明</span><span class="sxs-lookup"><span data-stu-id="38f2d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="38f2d-109">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-109">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="38f2d-110">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-110">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="38f2d-111">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-111">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="38f2d-112">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-112">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="38f2d-113">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-113">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="38f2d-114">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-114">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="38f2d-115">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-115">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="38f2d-116">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-116">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="38f2d-117">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-117">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="38f2d-118">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-118">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="38f2d-119">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-119">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="38f2d-120">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-120">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="38f2d-121">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="38f2d-121">get_IsFullscreenAllowed_deprecated</span></span>](#get_isfullscreenallowed_deprecated) | <span data-ttu-id="38f2d-122">この設定は廃止され、常に false を返します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-122">This setting is deprecated and will always return false.</span></span>
[<span data-ttu-id="38f2d-123">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="38f2d-123">put_IsFullscreenAllowed_deprecated</span></span>](#put_isfullscreenallowed_deprecated) | <span data-ttu-id="38f2d-124">この設定は廃止され、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="38f2d-124">This setting is deprecated and will have no effect.</span></span>
[<span data-ttu-id="38f2d-125">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-125">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="38f2d-126">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-126">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="38f2d-127">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-127">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="38f2d-128">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-128">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="38f2d-129">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-129">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="38f2d-130">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-130">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="38f2d-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="38f2d-132">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-132">Set the AreDevToolsEnabled property.</span></span>

<span data-ttu-id="38f2d-133">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="38f2d-133">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="38f2d-134">Members</span><span class="sxs-lookup"><span data-stu-id="38f2d-134">Members</span></span>

#### <span data-ttu-id="38f2d-135">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-135">get_IsScriptEnabled</span></span> 

<span data-ttu-id="38f2d-136">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-136">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="38f2d-137">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-137">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="38f2d-138">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-138">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="38f2d-139">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="38f2d-139">It is true by default.</span></span>

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

#### <span data-ttu-id="38f2d-140">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-140">put_IsScriptEnabled</span></span> 

<span data-ttu-id="38f2d-141">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-141">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="38f2d-142">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-142">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="38f2d-143">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-143">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="38f2d-144">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-144">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="38f2d-145">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-145">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="38f2d-146">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="38f2d-146">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="38f2d-147">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="38f2d-147">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="38f2d-148">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="38f2d-148">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="38f2d-149">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="38f2d-149">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="38f2d-150">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="38f2d-150">It is true by default.</span></span>

```cpp
    ComPtr<IWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="38f2d-151">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-151">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="38f2d-152">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-152">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="38f2d-153">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-153">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="38f2d-154">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-154">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="38f2d-155">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-155">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="38f2d-156">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="38f2d-156">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="38f2d-157">False に設定した場合、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数によって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="38f2d-157">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, and prompt functions).</span></span> <span data-ttu-id="38f2d-158">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="38f2d-158">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="38f2d-159">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-159">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="38f2d-160">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-160">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="38f2d-161">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="38f2d-161">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="38f2d-162">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="38f2d-162">get_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="38f2d-163">この設定は廃止され、常に false を返します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-163">This setting is deprecated and will always return false.</span></span>

> <span data-ttu-id="38f2d-164">パブリック HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(ブール \* isFullscreenAllowed)</span><span class="sxs-lookup"><span data-stu-id="38f2d-164">public HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(BOOL \* isFullscreenAllowed)</span></span>

<span data-ttu-id="38f2d-165">つまり、WebView の要素は、WebView の境界線にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-165">That means elements in the WebView will only fill the WebView bounds.</span></span> <span data-ttu-id="38f2d-166">このプロパティは、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-166">This property will then be completely removed.</span></span> <span data-ttu-id="38f2d-167">指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。</span><span class="sxs-lookup"><span data-stu-id="38f2d-167">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="38f2d-168">WebView の要素に対してフルスクリーンを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-168">Controls if fullscreen is allowed for elements in the WebView.</span></span> <span data-ttu-id="38f2d-169">許可されている場合、WebView の video 要素などの web コンテンツは全画面表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-169">When it is allowed, web content such as a video element in the WebView is allowed to be displayed full screen.</span></span> <span data-ttu-id="38f2d-170">許可されていない場合、この要素は、要素が全画面表示を要求したときに WebView の境界線を埋めます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-170">When it is not allowed, such element will fill the WebView bounds when the element requests full screen.</span></span> <span data-ttu-id="38f2d-171">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="38f2d-171">It is true by default.</span></span>

#### <span data-ttu-id="38f2d-172">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="38f2d-172">put_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="38f2d-173">この設定は廃止され、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="38f2d-173">This setting is deprecated and will have no effect.</span></span>

> <span data-ttu-id="38f2d-174">パブリック HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)</span><span class="sxs-lookup"><span data-stu-id="38f2d-174">public HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)</span></span>

<span data-ttu-id="38f2d-175">指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。</span><span class="sxs-lookup"><span data-stu-id="38f2d-175">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="38f2d-176">IsFullscreenAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-176">Set the IsFullscreenAllowed property.</span></span>

#### <span data-ttu-id="38f2d-177">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-177">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="38f2d-178">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-178">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="38f2d-179">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-179">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="38f2d-180">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f2d-180">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="38f2d-181">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="38f2d-181">It is true by default.</span></span>

#### <span data-ttu-id="38f2d-182">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-182">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="38f2d-183">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-183">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="38f2d-184">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-184">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="38f2d-185">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-185">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="38f2d-186">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-186">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="38f2d-187">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-187">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="38f2d-188">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="38f2d-188">It is true by default.</span></span>

#### <span data-ttu-id="38f2d-189">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="38f2d-189">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="38f2d-190">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38f2d-190">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="38f2d-191">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="38f2d-191">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

