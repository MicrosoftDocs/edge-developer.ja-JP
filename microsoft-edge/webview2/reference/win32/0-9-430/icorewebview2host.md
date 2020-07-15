---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Host
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 9202c17d83ad7d0750dbf76724b550d73ecca434
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881034"
---
# 0.9.430-インターフェイス ICoreWebView2Host 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2Host
  : public IUnknown
```

このインターフェイスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化とコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsVisible](#get_isvisible) | IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。
[put_IsVisible](#put_isvisible) | IsVisible プロパティを設定します。
[get_Bounds](#get_bounds) | Webview の境界。
[put_Bounds](#put_bounds) | 境界プロパティを設定します。
[get_ZoomFactor](#get_zoomfactor) | WebView のズームファクター。
[put_ZoomFactor](#put_zoomfactor) | ZoomFactor プロパティを設定します。
[add_ZoomFactorChanged](#add_zoomfactorchanged) | ZoomFactorChanged イベントのイベントハンドラーを追加します。
[remove_ZoomFactorChanged](#remove_zoomfactorchanged) | Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。
[SetBoundsAndZoomFactor](#setboundsandzoomfactor) | 同時に境界と ZoomFactor のプロパティを更新します。
[MoveFocus](#movefocus) | WebView にフォーカスを移動します。
[add_MoveFocusRequested](#add_movefocusrequested) | MoveFocusRequested されたイベントのイベントハンドラーを追加します。
[remove_MoveFocusRequested](#remove_movefocusrequested) | Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。
[add_GotFocus](#add_gotfocus) | GotFocus イベントのイベントハンドラーを追加します。
[remove_GotFocus](#remove_gotfocus) | Add_GotFocus で以前に追加されたイベントハンドラーを削除します。
[add_LostFocus](#add_lostfocus) | LostFocus イベントのイベントハンドラーを追加します。
[remove_LostFocus](#remove_lostfocus) | Add_LostFocus で以前に追加されたイベントハンドラーを削除します。
[add_AcceleratorKeyPressed](#add_acceleratorkeypressed) | AcceleratorKeyPressed イベントのイベントハンドラーを追加します。
[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed) | Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。
[get_ParentWindow](#get_parentwindow) | この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。
[put_ParentWindow](#put_parentwindow) | WebView の親ウィンドウを設定します。
[NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged) | これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。
[Close](#close) | WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。
[get_CoreWebView2](#get_corewebview2) | この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。
[CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason) | フォーカスを移動する理由。
[CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind) | AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。
[CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status) | Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

CoreWebView2Host は CoreWebView2 を所有しており、CoreWebView2Host へのすべての参照が終了した場合、WebView は閉じられます。

## Members

#### get_IsVisible 

IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。

> パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL * IsVisible)

IsVisible が false に設定されている場合、webview は透過的であり、表示されません。 ただし、この操作を行っても、webview (CreateCoreWebView2Host に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。 ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。 子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。 パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。 アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_host->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_host->put_IsVisible(m_isVisible);
}
```

#### put_IsVisible 

IsVisible プロパティを設定します。

> パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_host->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_host->put_IsVisible(TRUE);
            }
        }
    }
```

#### get_Bounds 

Webview の境界。

> パブリック HRESULT [get_Bounds](#get_bounds)(RECT * 境界)

境界は親 HWND を基準としています。 アプリには、WebView を配置する2つの方法があります。

1. WebView 親 HWND である子 HWND を作成します。 WebView が必要な場所にこのウィンドウを配置します。 この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。

1. アプリの一番上のウィンドウは、WebView 親 HWND として使います。 Webview の左上隅を、アプリ内で適切に配置されるように設定します。 バインドされた値は、ホストの座標空間にあります。

#### put_Bounds 

境界プロパティを設定します。

> パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    SIZE webViewSize = {
            LONG((m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio * m_webViewScale),
            LONG((m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio * m_webViewScale) };

    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        webViewSize.cy + m_webViewBounds.top);
    desiredBounds.right = LONG(
        webViewSize.cx + m_webViewBounds.left);

    m_host->put_Bounds(desiredBounds);
}
```

#### get_ZoomFactor 

WebView のズームファクター。

> パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double * ZoomFactor)

ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。 Put_ZoomFactor を呼び出すことによってホストによって適用されるズームファクターは、WebView の新しい既定のズームになります。 このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。 拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。 すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。 0以下の zoomFactor を指定することはできません。 WebView には、内部でサポートされているズームファクター範囲もあります。 指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。 この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。

#### put_ZoomFactor 

ZoomFactor プロパティを設定します。

> パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)

#### add_ZoomFactorChanged 

ZoomFactorChanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView の ZoomFactor プロパティが変更されると、イベントが発生します。 呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。 ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。 WebView は、各サイトで使用されている直前の拡大率を関連付けます。 そのため、別のページに移動するときにズーム倍率が変更される可能性があります。 このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_host->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Host* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### remove_ZoomFactorChanged 

Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)

#### SetBoundsAndZoomFactor 

同時に境界と ZoomFactor のプロパティを更新します。

> パブリック HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT 境界、double zoomFactor)

この操作は、ホストの perspecive によってアトミック処理されます。 この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。 境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。 この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_host->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_host->SetBoundsAndZoomFactor(bounds, scale);
}
```

#### MoveFocus 

WebView にフォーカスを移動します。

> パブリック HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)の理由)

WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。 プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。 次の理由から、フォーカスは最初の要素に設定されます。 前の理由から、フォーカスは最後の要素に設定されます。 また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。 Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。 または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。 プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。 WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (int i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### add_MoveFocusRequested 

MoveFocusRequested されたイベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。 このイベントが発生すると、WebView のフォーカスが変更されません。

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_host->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    CORE_WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### remove_MoveFocusRequested 

Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)

#### add_GotFocus 

GotFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

GotFocus は、WebView がフォーカスを取得したときに発生します。

#### remove_GotFocus 

Add_GotFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)

#### add_LostFocus 

LostFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

このとき、WebView はフォーカスを失ったときに発生します。 MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。 フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。

#### remove_LostFocus 

Add_LostFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)

#### add_AcceleratorKeyPressed 

AcceleratorKeyPressed イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) * eventHandler、EventRegistrationToken * token)

AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。 次のいずれかの場合、キーはアクセラレータと見なされます。

1. Ctrl または Alt は現在保留中か

1. 押されたキーは文字にマップされません。 一部の特定のキーは、Shift などのアクセラレータとは見なされません。 Escape キーは、常にアクセラレータと見なされます。

キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。 これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。

ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。 イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。 ただし、すべての CoreWebView2 API メソッドが動作します。

ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。 さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。

ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_host->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                CORE_WEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->put_Handled(TRUE));

                        // Filter out autorepeated keys.
                        CORE_WEBVIEW2_PHYSICAL_KEY_STATUS status;
                        CHECK_FAILURE(args->get_PhysicalKeyStatus(&status));
                        if (!status.WasKeyDown)
                        {
                            // Perform the action asynchronously to avoid blocking the
                            // browser process's event queue.
                            m_appWindow->RunAsync(action);
                        }
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_acceleratorKeyPressedToken));
```

#### remove_AcceleratorKeyPressed 

Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)

#### get_ParentWindow 

この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。

> パブリック HRESULT [get_ParentWindow](#get_parentwindow)(HWND * topLevelWindow)

この API では、最初に CreateCoreWebView2Host に渡されたウィンドウが返されます。

#### put_ParentWindow 

WebView の親ウィンドウを設定します。

> パブリック HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)

これにより、WebView が、新しく指定したウィンドウにウィンドウを再表示します。

#### NotifyParentWindowPositionChanged 

これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。

> パブリック HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()

これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。 

```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_host->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### Close 

WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。

> パブリック HRESULT [Close](#close)()

ブラウザーの instace をクリーンアップすると、WebView に電源が入っているリソースが解放されます。 他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。

Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。 具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。

Close は、CoreWebView2Host が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。 ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。 具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。 Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。 ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_host)
    {
        m_host->Close();
        m_host = nullptr;
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
    if (cleanupUserDataFolder)
    {
        // For non-UWP apps, the default user data folder {Executable File Name}.WebView2
        // is in the same directory next to the app executable. If end
        // developers specify userDataFolder during WebView environment
        // creation, they would need to pass in that explicit value here.
        // For more information about userDataFolder:
        // https://docs.microsoft.com/microsoft-edge/hosting/webview2/reference/win32/0-9-488/webview2.idl#createwebview2environmentwithdetails
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instnaces.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
        }
    }
}
```

#### get_CoreWebView2 

この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。

> パブリック HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) * * CoreWebView2)

#### CORE_WEBVIEW2_MOVE_FOCUS_REASON 

フォーカスを移動する理由。

> 列挙型[CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC            | コード設定による WebView へのフォーカス。
CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT            | タブトラバーサルを前方に移動するためにフォーカスを移動する。
CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS            | タブトラバーサルに戻るためにフォーカスを移動する。

#### CORE_WEBVIEW2_KEY_EVENT_KIND 

AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。

> 列挙型[CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN            | ウィンドウメッセージ WM_KEYDOWN に対応します。
CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP            | ウィンドウメッセージ WM_KEYUP に対応します。
CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN            | ウィンドウメッセージ WM_SYSKEYDOWN に対応します。
CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP            | ウィンドウメッセージ WM_SYSKEYUP に対応します。

#### CORE_WEBVIEW2_PHYSICAL_KEY_STATUS 

Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

> typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)

詳細については、WM_KEYDOWN のドキュメントを参照してください。[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)

