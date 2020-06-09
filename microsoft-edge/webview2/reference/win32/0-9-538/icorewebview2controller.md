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
ms.openlocfilehash: 1d221498312959efbc16204097eb81db65fd2a7b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699018"
---
# インターフェイス ICoreWebView2Controller 

```
interface ICoreWebView2Controller
  : public IUnknown
```

このインターフェイスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化とコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[add_AcceleratorKeyPressed](#add_acceleratorkeypressed) | AcceleratorKeyPressed イベントのイベントハンドラーを追加します。
[add_GotFocus](#add_gotfocus) | GotFocus イベントのイベントハンドラーを追加します。
[add_LostFocus](#add_lostfocus) | LostFocus イベントのイベントハンドラーを追加します。
[add_MoveFocusRequested](#add_movefocusrequested) | MoveFocusRequested されたイベントのイベントハンドラーを追加します。
[add_ZoomFactorChanged](#add_zoomfactorchanged) | ZoomFactorChanged イベントのイベントハンドラーを追加します。
[Close](#close) | WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。
[get_Bounds](#get_bounds) | Webview の境界。
[get_CoreWebView2](#get_corewebview2) | この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。
[get_IsVisible](#get_isvisible) | IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。
[get_ParentWindow](#get_parentwindow) | この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。
[get_ZoomFactor](#get_zoomfactor) | WebView のズームファクター。
[MoveFocus](#movefocus) | WebView にフォーカスを移動します。
[NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged) | これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。
[put_Bounds](#put_bounds) | 境界プロパティを設定します。
[put_IsVisible](#put_isvisible) | IsVisible プロパティを設定します。
[put_ParentWindow](#put_parentwindow) | WebView の親ウィンドウを設定します。
[put_ZoomFactor](#put_zoomfactor) | ZoomFactor プロパティを設定します。
[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed) | Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。
[remove_GotFocus](#remove_gotfocus) | Add_GotFocus で以前に追加されたイベントハンドラーを削除します。
[remove_LostFocus](#remove_lostfocus) | Add_LostFocus で以前に追加されたイベントハンドラーを削除します。
[remove_MoveFocusRequested](#remove_movefocusrequested) | Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。
[remove_ZoomFactorChanged](#remove_zoomfactorchanged) | Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。
[SetBoundsAndZoomFactor](#setboundsandzoomfactor) | 同時に境界と ZoomFactor のプロパティを更新します。

CoreWebView2Controller は CoreWebView2 を所有しており、CoreWebView2Controller へのすべての参照が終了した場合、WebView は閉じられます。

## Members

#### add_AcceleratorKeyPressed 

AcceleratorKeyPressed イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) * eventHandler、EventRegistrationToken * token)

AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。 次のいずれかの場合、キーはアクセラレータと見なされます。

1. Ctrl または Alt は現在保留中か

1. 押されたキーは文字にマップされません。 一部の特定のキーは、Shift などのアクセラレータとは見なされません。 Escape キーは、常にアクセラレータと見なされます。

キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。 これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。

ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。 イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。 ただし、すべての CoreWebView2 API メソッドが動作します。

ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。 さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。

ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_controller->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                COREWEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
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
                        COREWEBVIEW2_PHYSICAL_KEY_STATUS status;
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

#### add_GotFocus 

GotFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) * eventHandler、EventRegistrationToken * token)

GotFocus は、WebView がフォーカスを取得したときに発生します。

#### add_LostFocus 

LostFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) * eventHandler、EventRegistrationToken * token)

このとき、WebView はフォーカスを失ったときに発生します。 MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。 フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。

#### add_MoveFocusRequested 

MoveFocusRequested されたイベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) * eventHandler、EventRegistrationToken * token)

MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。 このイベントが発生すると、WebView のフォーカスが変更されません。

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_controller->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    COREWEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
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

#### add_ZoomFactorChanged 

ZoomFactorChanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) * eventHandler、EventRegistrationToken * token)

WebView の ZoomFactor プロパティが変更されると、イベントが発生します。 呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。 ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。 WebView は、各サイトで使用されている直前の拡大率を関連付けます。 そのため、別のページに移動するときにズーム倍率が変更される可能性があります。 このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_controller->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Controller* sender, IUnknown* args) -> HRESULT {
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

#### Close 

WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。

> パブリック HRESULT [Close](#close)()

ブラウザインスタンスをクリーンアップすると、WebView を電源にしているリソースが解放されます。 他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。

Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。 具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。

Close は、CoreWebView2Controller が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。 ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。 具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。 Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。 ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_controller)
    {
        m_controller->Close();
        m_controller = nullptr;
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
        // https://docs.microsoft.com/microsoft-edge/webview2/reference/win32/0-9-538/webview2-idl#createwebview2environmentwithoptions
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instances.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
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

#### get_CoreWebView2 

この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。

> パブリック HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](icorewebview2.md) * * CoreWebView2)

#### get_IsVisible 

IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。

> パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL * IsVisible)

IsVisible が false に設定されている場合、webview は透過的であり、表示されません。 ただし、この操作を行っても、webview (CreateCoreWebView2Controller に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。 ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。 子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。 パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。 アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_controller->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_controller->put_IsVisible(m_isVisible);
}
```

#### get_ParentWindow 

この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。

> パブリック HRESULT [get_ParentWindow](#get_parentwindow)(HWND * topLevelWindow)

この API では、最初に CreateCoreWebView2Controller に渡されたウィンドウが返されます。

#### get_ZoomFactor 

WebView のズームファクター。

> パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double * ZoomFactor)

ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。 ZoomFactor を呼び出して、ホストによって適用される拡大率は、WebView の新しい既定のズームになります。 このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。 拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。 すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。 0以下の zoomFactor を指定することはできません。 WebView には、内部でサポートされているズームファクター範囲もあります。 指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。 この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。

#### MoveFocus 

WebView にフォーカスを移動します。

> パブリック HRESULT [MoveFocus](#movefocus)(COREWEBVIEW2_MOVE_FOCUS_REASON の理由)

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
            for (size_t i = 0; i < m_tabbableWindows.size(); i++)
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
    for (size_t i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT);
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
    CHECK_FAILURE(m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### NotifyParentWindowPositionChanged 

これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。

> パブリック HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()

これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。 
```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_controller->NotifyParentWindowPositionChanged();
        return true;
    }
```

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

    m_controller->put_Bounds(desiredBounds);
    if (m_compositionController)
    {
        POINT webViewOffset = {m_webViewBounds.left, m_webViewBounds.top};

        if (m_dcompDevice)
        {
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetX(float(webViewOffset.x)));
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetY(float(webViewOffset.y)));
            CHECK_FAILURE(m_dcompRootVisual->SetClip(
                {0, 0, float(webViewSize.cx), float(webViewSize.cy)}));
            CHECK_FAILURE(m_dcompDevice->Commit());
        }
        else if (m_wincompHelper)
        {
            m_wincompHelper->UpdateSizeAndPosition(webViewOffset, webViewSize);
        }
    }
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
            m_controller->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_controller->put_IsVisible(TRUE);
            }
        }
    }
```

#### put_ParentWindow 

WebView の親ウィンドウを設定します。

> パブリック HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)

これにより、WebView が、新しく指定したウィンドウにウィンドウを再表示します。

#### put_ZoomFactor 

ZoomFactor プロパティを設定します。

> パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)

#### remove_AcceleratorKeyPressed 

Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)

#### remove_GotFocus 

Add_GotFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)

#### remove_LostFocus 

Add_LostFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)

#### remove_MoveFocusRequested 

Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)

#### remove_ZoomFactorChanged 

Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)

#### SetBoundsAndZoomFactor 

同時に境界と ZoomFactor のプロパティを更新します。

> パブリック HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT 境界、double zoomFactor)

この操作は、ホストの観点からはアトミックです。 この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。 境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。 この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_controller->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_controller->SetBoundsAndZoomFactor(bounds, scale);
}
```

