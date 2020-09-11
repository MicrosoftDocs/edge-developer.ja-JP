---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2CompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2CompositionController。
ms.openlocfilehash: 51c6ebb12130632c5fb08e2992caf6ae83a478b1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012295"
---
# WebView2 クラス (CoreWebView2CompositionController クラス) 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

このクラスは、CoreWebView2Controller クラスの拡張機能であり、ビジュアルホストをサポートします。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Cursor](#cursor) | WebView で現在のカーソルの位置を判断します。
[カーソルが変更されました](#cursorchanged) | WebView がカーソルの変更であると判断されたときに、イベントが発生します。
[RootVisualTarget](#rootvisualtarget) | RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。
[UIAProvider](#uiaprovider) | WebView の UI オートメーションプロバイダーを返します。
[CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) | システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。
[SendMouseInput](#sendmouseinput) | EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。
[Sendポインタ入力](#sendpointerinput) | Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。

## Members

#### Cursor 

WebView で現在のカーソルの位置を判断します。

> パブリック IntPtr [カーソル](#cursor)

WM_SETCURSOR でカーソルを設定するか、WebView ~ SetClassLongPtr の対応する親または先祖の HWND を設定する必要があります。 HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。

#### カーソルが変更されました 

WebView がカーソルの変更であると判断されたときに、イベントが発生します。

> < オブジェクト >[カーソルが変更された](#cursorchanged)パブリックイベント EventHandler

たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。 CoreWebView2MouseEventKind を送信するには、送信者が送信する必要があります。 SendMouseInput API を介して、(CoreWebView2MouseEventKind に加えて) メッセージを移動します。 これは、カーソルの変更されたイベントを送信する WebView 内に実際にマウスがあることを確認するためです。

#### RootVisualTarget 

RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。

> パブリックオブジェクト [Rootvisualtarget](#rootvisualtarget)

このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。 アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。 この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。 RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。 WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。 アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。 RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。

#### UIAProvider 

WebView の UI オートメーションプロバイダーを返します。

> パブリックオブジェクト [Uiaprovider](#uiaprovider)

#### CreateCoreWebView2PointerInfoFromPointerId 

システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。

> パブリック [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(Uint ポインター Id、IntPtr parentwindow、Matrix4x4 transform)

parentWindow は、WebView を含む HWND です。 これは、WebView を含む hwnd ツリー内の任意の HWND にすることができます。 CoreWebView2Matrix4x4 は、その HWND から WebView への変換です。 返された CoreWebView2PointerInfo は、Sendポインタ Info で使われます。 ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。

#### SendMouseInput 

EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。

> パブリックの void [Sendmouseinput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventkind、 [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) Virtualkeys、uint mousedata、ポイントポイント)

正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。 ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。 EventKind が CoreWebView2MouseEventKind XButtonDoubleClick CoreWebView2MouseEventKind Down または CoreWebView2MouseEventKind Up の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。 この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。 EventKind が CoreWebView2MouseEventKind の場合は、virtualKeys、mouseData、point がすべてゼロである必要があります。 EventKind がその他の値である場合は、mouseData は0である必要があります。 Point は、WebView のクライアント座標空間に存在する必要があります。 WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。 ホバーポップアップを消すには、CoreWebView2MouseEventKind メッセージを送信することもお勧めします。

#### Sendポインタ入力 

Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。

> パブリック void [Sendポインタ入力](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventkind、 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) ポインタ info)

システムからのポインター入力は、最初に CoreWebView2PointerInfo に変換する必要があります。

