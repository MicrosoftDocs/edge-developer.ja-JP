---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ddb3fce4f3f9799bcfaf8a9aa297c3207392f916
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884541"
---
# 0.9.515-インターフェイス ICoreWebView2ExperimentalCompositionController 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

このインターフェイスは、ICoreWebView2Controller インターフェイスの拡張機能であり、ビジュアルホストをサポートします。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[add_CursorChanged](#add_cursorchanged) | カーソル変更イベントのイベントハンドラーを追加します。
[CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) | システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。
[get_Cursor](#get_cursor) | WebView で現在のカーソルの位置を判断します。
[get_RootVisualTarget](#get_rootvisualtarget) | RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。
[get_UIAProvider](#get_uiaprovider) | WebView の UI オートメーションプロバイダーを返します。
[put_RootVisualTarget](#put_rootvisualtarget) | RootVisualTarget プロパティを設定します。
[remove_CursorChanged](#remove_cursorchanged) | Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。
[SendMouseInput](#sendmouseinput) | EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。
[Sendポインタ入力](#sendpointerinput) | Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。
[COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4) | 3D 変換を表すマトリックス。
[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) | WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。
[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) | SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。
[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) | WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。

ICoreWebView2ExperimentalCompositionController インターフェイスを実装するオブジェクトも ICoreWebView2Controller を実装します。 呼び出し元は、サイズ変更、visibility、フォーカスなどのために ICoreWebView2Controller を使うことを前提としており、ICoreWebView2ExperimentalCompositionController を使ってコンポジションツリーに接続し、WebView 用の入力を提供します。

## Members

#### add_CursorChanged 

カーソル変更イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) * eventHandler、EventRegistrationToken * token)

WebView がカーソルの変更であると判断されたときに、イベントが発生します。 たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。

```cpp
        // Register a handler for the CursorChanged event.
        CHECK_FAILURE(m_compositionController->add_CursorChanged(
            Callback<ICoreWebView2ExperimentalCursorChangedEventHandler>(
                [this](ICoreWebView2ExperimentalCompositionController* sender,
                       IUnknown* args) -> HRESULT {
                    HCURSOR cursor;
                    CHECK_FAILURE(sender->get_Cursor(&cursor));
                    SetClassLongPtr(m_appWindow->GetMainWindow(), GCLP_HCURSOR, (LONG_PTR)cursor);
                    return S_OK;
                })
                .Get(),
            &m_cursorChangedToken));
```

#### CreateCoreWebView2PointerInfoFromPointerId 

システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。

> パブリック HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT ポインター ID、HWND parentwindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) * * ポインター情報)

parentWindow は、webview を含む HWND です。 これは、webview を含む hwnd ツリー内の任意の HWND にすることができます。 COREWEBVIEW2_MATRIX_4X4 は、その HWND から webview への変換です。 返された[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)は、Sendポインタ info で使われます。 ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。



#### get_Cursor 

WebView で現在のカーソルの位置を判断します。

> パブリック HRESULT [get_Cursor](#get_cursor)(hcursor * cursor)

カーソルは WM_SETCURSOR スルー:: SetCursor で設定するか、WebView ~:: SetClassLongPtr の対応する親または先祖の HWND で設定する必要があります。 HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。

#### get_RootVisualTarget 

RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。

> パブリック HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown * * target)

このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。 アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。 この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。 RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。 WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。 アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。 RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。 
```cpp
            // Set the host app visual that the WebView will connect its visual
            // tree to.
            BuildDCompTreeUsingVisual();
            CHECK_FAILURE(m_compositionController->put_RootVisualTarget(m_dcompWebViewVisual.get()));
            CHECK_FAILURE(m_dcompDevice->Commit());
```

```cpp
// Create host app visual that the WebView will connect to.
//   - Create a IDCompositionTarget for the host window
//   - Create a visual and set that as the IDCompositionTarget's root
//   - Create another visual and add that to the IDCompositionTarget's root.
//     This visual will be the visual root for the WebView.
void ViewComponent::BuildDCompTreeUsingVisual()
{
    CHECK_FAILURE_BOOL(m_dcompDevice != nullptr);

    if (m_dcompWebViewVisual == nullptr)
    {
        CHECK_FAILURE(m_dcompDevice->CreateTargetForHwnd(
            m_appWindow->GetMainWindow(), TRUE, &m_dcompHwndTarget));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompRootVisual));
        CHECK_FAILURE(m_dcompHwndTarget->SetRoot(m_dcompRootVisual.get()));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompWebViewVisual));
        CHECK_FAILURE(m_dcompRootVisual->AddVisual(m_dcompWebViewVisual.get(), TRUE, nullptr));
    }
}
```

#### get_UIAProvider 

WebView の UI オートメーションプロバイダーを返します。

> パブリック HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown * * provider)

#### put_RootVisualTarget 

RootVisualTarget プロパティを設定します。

> パブリック HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown * ターゲット)

#### remove_CursorChanged 

Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)

#### SendMouseInput 

EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。

> パブリック HRESULT 送信[マウス入力](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventkind、 [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) VIRTUALKEYS、UINT32 mousedata、ポイントポイント)

正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。 ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。 EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN、または COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。 この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。 EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE の場合、virtualKeys、mouseData、point はすべてゼロである必要があります。 EventKind がその他の値である場合は、mouseData は0である必要があります。 Point は、WebView のクライアント座標空間に存在する必要があります。 WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。 ホバーポップアップを消すには、WM_MOUSELEAVE メッセージを送信することをお勧めします。 
```cpp
bool ViewComponent::OnMouseMessage(UINT message, WPARAM wParam, LPARAM lParam)
{
    // Manually relay mouse messages to the WebView
    if (m_dcompDevice || m_wincompHelper)
    {
        POINT point;
        POINTSTOPOINT(point, lParam);
        if (message == WM_MOUSEWHEEL || message == WM_MOUSEHWHEEL)
        {
            // Mouse wheel messages are delivered in screen coordinates.
            // SendMouseInput expects client coordinates for the WebView, so convert
            // the point from screen to client.
            ::ScreenToClient(m_appWindow->GetMainWindow(), &point);
        }
        // Send the message to the WebView if the mouse location is inside the
        // bounds of the WebView, if the message is telling the WebView the
        // mouse has left the client area, or if we are currently capturing
        // mouse events.
        bool isMouseInWebView = PtInRect(&m_webViewBounds, point);
        if (isMouseInWebView || message == WM_MOUSELEAVE || m_isCapturingMouse)
        {
            DWORD mouseData = 0;

            switch (message)
            {
            case WM_MOUSEWHEEL:
            case WM_MOUSEHWHEEL:
                mouseData = GET_WHEEL_DELTA_WPARAM(wParam);
                break;
            case WM_XBUTTONDBLCLK:
            case WM_XBUTTONDOWN:
            case WM_XBUTTONUP:
                mouseData = GET_XBUTTON_WPARAM(wParam);
                break;
            case WM_MOUSEMOVE:
                if (!m_isTrackingMouse)
                {
                    // WebView needs to know when the mouse leaves the client area
                    // so that it can dismiss hover popups. TrackMouseEvent will
                    // provide a notification when the mouse leaves the client area.
                    TrackMouseEvents(TME_LEAVE);
                    m_isTrackingMouse = true;
                }
                break;
            case WM_MOUSELEAVE:
                m_isTrackingMouse = false;
                break;
            }

            // We need to capture the mouse in case the user drags the
            // mouse outside of the window bounds and we still need to send
            // mouse messages to the WebView process. This is useful for
            // scenarios like dragging the scroll bar or panning a map.
            // This is very similar to the Pointer Message case where a
            // press started inside of the WebView.
            if (message == WM_LBUTTONDOWN || message == WM_MBUTTONDOWN ||
                message == WM_RBUTTONDOWN || message == WM_XBUTTONDOWN)
            {
                if (isMouseInWebView && ::GetCapture() != m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = true;
                    ::SetCapture(m_appWindow->GetMainWindow());
                }
            }
            else if (message == WM_LBUTTONUP || message == WM_MBUTTONUP ||
                message == WM_RBUTTONUP || message == WM_XBUTTONUP)
            {
                if (::GetCapture() == m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = false;
                    ::ReleaseCapture();
                }
            }

            // Adjust the point from app client coordinates to webview client coordinates.
            // WM_MOUSELEAVE messages don't have a point, so don't adjust the point.
            if (message != WM_MOUSELEAVE)
            {
                point.x -= m_webViewBounds.left;
                point.y -= m_webViewBounds.top;
            }

            CHECK_FAILURE(m_compositionController->SendMouseInput(
                static_cast<COREWEBVIEW2_MOUSE_EVENT_KIND>(message),
                static_cast<COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS>(GET_KEYSTATE_WPARAM(wParam)),
                mouseData, point));
            return true;
        }
        else if (message == WM_MOUSEMOVE && m_isTrackingMouse)
        {
            // When the mouse moves outside of the WebView, but still inside the app
            // turn off mouse tracking and send the WebView a leave event.
            m_isTrackingMouse = false;
            TrackMouseEvents(TME_LEAVE | TME_CANCEL);
            OnMouseMessage(WM_MOUSELEAVE, 0, 0);
        }
    }
    return false;
}
```

#### Sendポインタ入力 

Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。

> パブリック HRESULT 送信[ポインター入力](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) * のポインター情報)

システムからのポインター入力は、最初に[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換する必要があります。

#### COREWEBVIEW2_MATRIX_4X4 

3D 変換を表すマトリックス。

> typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)

この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。 これは D2D1_MATRIX_4X4_F と同じです。

#### COREWEBVIEW2_MOUSE_EVENT_KIND 

WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。

> 列挙型[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL            | マウスの水平ホイールスクロールイベント、WM_MOUSEHWHEEL。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK            | [左] ボタンをダブルクリックすると、[マウスイベント] が WM_LBUTTONDBLCLK ます。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN            | [左] ボタンのマウスイベント、WM_LBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP            | [左] ボタンのマウスイベント、WM_LBUTTONUP。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE            | マウスの終了イベント、WM_MOUSELEAVE。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK            | 中央ボタン [マウスイベント]、[WM_MBUTTONDBLCLK] の順にダブルクリックします。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN            | 中央ボタンのマウスイベント、WM_MBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP            | 中央ボタン上のマウスイベント、WM_MBUTTONUP。
COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE            | マウス移動イベント、WM_MOUSEMOVE。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK            | 右ボタン [マウスイベント]、[WM_RBUTTONDBLCLK] の順にダブルクリックします。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN            | 右ボタンのマウスイベント、WM_RBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP            | マウスの右上にあるイベントの [WM_RBUTTONUP] をクリックします。
COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL            | マウスホイールスクロールイベント、WM_MOUSEWHEEL。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK            | 第1または第2の X ボタンをダブルクリックすると、[マウスイベント] が WM_XBUTTONDBLCLK ます。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN            | 最初または2番目の X ボタンのマウスイベントを WM_XBUTTONDOWN します。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP            | 最初または2番目の X ボタンのマウスイベントを WM_XBUTTONUP します。

この列挙型の値は、対応する WM_ * ウィンドウメッセージと整列します。

#### COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS 

SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。

> 列挙型[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)

 値                         | 説明
--------------------------------|---------------------------------------------
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE            | 追加のキーが押されていません。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON            | マウスの左ボタンが押されています。 MK_LBUTTON。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON            | マウスの右ボタンが押されて MK_RBUTTON ます。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT            | SHIFT キーを押しながら MK_SHIFT ます。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL            | CTRL キーを押しながら MK_CONTROL ます。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON            | マウスの中央ボタンが押されて MK_MBUTTON。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1            | 最初の X ボタンが押されて MK_XBUTTON1。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2            | 第2の X ボタンが押され、MK_XBUTTON2 ます。

これらの値は、複数の仮想キーがイベントとして押されている場合に、ビットフラグに組み合わせることができます。 この列挙型の値は、一致する MK_ * マウスキーと整列します。

#### COREWEBVIEW2_POINTER_EVENT_KIND 

WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。

> 列挙型[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE            | WM_POINTERACTIVATE に対応します。
COREWEBVIEW2_POINTER_EVENT_KIND_DOWN            | WM_POINTERDOWN に対応します。
COREWEBVIEW2_POINTER_EVENT_KIND_ENTER            | WM_POINTERENTER に対応します。
COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE            | WM_POINTERLEAVE に対応します。
COREWEBVIEW2_POINTER_EVENT_KIND_UP            | WM_POINTERUP に対応します。
COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE            | WM_POINTERUPDATE に対応します。

この列挙型の値は、対応する WM_POINTER * ウィンドウメッセージと整列します。

