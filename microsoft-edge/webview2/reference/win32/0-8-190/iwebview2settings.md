---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 3c799e97f8e85927e1c11b30be747d7649faeca0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654308"
---
# <span data-ttu-id="098ec-104">インターフェイス IWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="098ec-104">interface IWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="098ec-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="098ec-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="098ec-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="098ec-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Settings
  : public IUnknown
```

<span data-ttu-id="098ec-107">WebView 機能を有効、無効、または変更するプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="098ec-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="098ec-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="098ec-108">Summary</span></span>

 <span data-ttu-id="098ec-109">Members</span><span class="sxs-lookup"><span data-stu-id="098ec-109">Members</span></span>                        | <span data-ttu-id="098ec-110">説明</span><span class="sxs-lookup"><span data-stu-id="098ec-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="098ec-111">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-111">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="098ec-112">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-112">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="098ec-113">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-113">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="098ec-114">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-114">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="098ec-115">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-115">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="098ec-116">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-116">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="098ec-117">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-117">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="098ec-118">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-118">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="098ec-119">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-119">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="098ec-120">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-120">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="098ec-121">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-121">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="098ec-122">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-122">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="098ec-123">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="098ec-123">get_IsFullscreenAllowed_deprecated</span></span>](#get_isfullscreenallowed_deprecated) | <span data-ttu-id="098ec-124">この設定は廃止され、常に false を返します。</span><span class="sxs-lookup"><span data-stu-id="098ec-124">This setting is deprecated and will always return false.</span></span>
[<span data-ttu-id="098ec-125">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="098ec-125">put_IsFullscreenAllowed_deprecated</span></span>](#put_isfullscreenallowed_deprecated) | <span data-ttu-id="098ec-126">この設定は廃止され、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="098ec-126">This setting is deprecated and will have no effect.</span></span>
[<span data-ttu-id="098ec-127">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-127">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="098ec-128">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-128">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="098ec-129">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-129">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="098ec-130">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-130">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="098ec-131">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-131">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="098ec-132">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-132">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="098ec-133">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-133">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="098ec-134">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-134">Set the AreDevToolsEnabled property.</span></span>

<span data-ttu-id="098ec-135">NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。</span><span class="sxs-lookup"><span data-stu-id="098ec-135">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="098ec-136">Members</span><span class="sxs-lookup"><span data-stu-id="098ec-136">Members</span></span>

#### <span data-ttu-id="098ec-137">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-137">get_IsScriptEnabled</span></span> 

<span data-ttu-id="098ec-138">WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-138">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="098ec-139">パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール \* isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-139">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="098ec-140">これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-140">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="098ec-141">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="098ec-141">It is true by default.</span></span>

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

#### <span data-ttu-id="098ec-142">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-142">put_IsScriptEnabled</span></span> 

<span data-ttu-id="098ec-143">IsScriptEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-143">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="098ec-144">パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-144">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="098ec-145">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-145">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="098ec-146">IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-146">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="098ec-147">パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-147">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="098ec-148">True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="098ec-148">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="098ec-149">Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="098ec-149">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="098ec-150">False に設定すると、通信は許可されません。</span><span class="sxs-lookup"><span data-stu-id="098ec-150">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="098ec-151">PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。</span><span class="sxs-lookup"><span data-stu-id="098ec-151">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="098ec-152">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="098ec-152">It is true by default.</span></span>

```cpp
    ComPtr<IWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="098ec-153">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-153">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="098ec-154">IsWebMessageEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-154">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="098ec-155">パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-155">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="098ec-156">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-156">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="098ec-157">Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-157">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="098ec-158">パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール \* Aredefaultscriptな有効)</span><span class="sxs-lookup"><span data-stu-id="098ec-158">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="098ec-159">False に設定した場合、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数によって表示されます)。</span><span class="sxs-lookup"><span data-stu-id="098ec-159">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, and prompt functions).</span></span> <span data-ttu-id="098ec-160">代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="098ec-160">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="098ec-161">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-161">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="098ec-162">AreDefaultScriptDialogsEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-162">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="098ec-163">パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)</span><span class="sxs-lookup"><span data-stu-id="098ec-163">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="098ec-164">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="098ec-164">get_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="098ec-165">この設定は廃止され、常に false を返します。</span><span class="sxs-lookup"><span data-stu-id="098ec-165">This setting is deprecated and will always return false.</span></span>

> <span data-ttu-id="098ec-166">パブリック HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(ブール \* isFullscreenAllowed)</span><span class="sxs-lookup"><span data-stu-id="098ec-166">public HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(BOOL \* isFullscreenAllowed)</span></span>

<span data-ttu-id="098ec-167">つまり、WebView の要素は、WebView の境界線にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-167">That means elements in the WebView will only fill the WebView bounds.</span></span> <span data-ttu-id="098ec-168">このプロパティは、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-168">This property will then be completely removed.</span></span> <span data-ttu-id="098ec-169">指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。</span><span class="sxs-lookup"><span data-stu-id="098ec-169">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="098ec-170">WebView の要素に対してフルスクリーンを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-170">Controls if fullscreen is allowed for elements in the WebView.</span></span> <span data-ttu-id="098ec-171">許可されている場合、WebView の video 要素などの web コンテンツは全画面表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="098ec-171">When it is allowed, web content such as a video element in the WebView is allowed to be displayed full screen.</span></span> <span data-ttu-id="098ec-172">許可されていない場合、この要素は、要素が全画面表示を要求したときに WebView の境界線を埋めます。</span><span class="sxs-lookup"><span data-stu-id="098ec-172">When it is not allowed, such element will fill the WebView bounds when the element requests full screen.</span></span> <span data-ttu-id="098ec-173">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="098ec-173">It is true by default.</span></span>

#### <span data-ttu-id="098ec-174">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="098ec-174">put_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="098ec-175">この設定は廃止され、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="098ec-175">This setting is deprecated and will have no effect.</span></span>

> <span data-ttu-id="098ec-176">パブリック HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)</span><span class="sxs-lookup"><span data-stu-id="098ec-176">public HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)</span></span>

<span data-ttu-id="098ec-177">指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。</span><span class="sxs-lookup"><span data-stu-id="098ec-177">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="098ec-178">IsFullscreenAllowed プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-178">Set the IsFullscreenAllowed property.</span></span>

#### <span data-ttu-id="098ec-179">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-179">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="098ec-180">IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-180">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="098ec-181">パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-181">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="098ec-182">通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="098ec-182">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="098ec-183">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="098ec-183">It is true by default.</span></span>

#### <span data-ttu-id="098ec-184">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-184">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="098ec-185">IsStatusBarEnabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-185">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="098ec-186">パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-186">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="098ec-187">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-187">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="098ec-188">Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="098ec-188">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="098ec-189">パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール \* areDevToolsEnabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-189">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="098ec-190">既定では true です。</span><span class="sxs-lookup"><span data-stu-id="098ec-190">It is true by default.</span></span>

#### <span data-ttu-id="098ec-191">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="098ec-191">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="098ec-192">Aredevset Enabled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="098ec-192">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="098ec-193">パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)</span><span class="sxs-lookup"><span data-stu-id="098ec-193">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

