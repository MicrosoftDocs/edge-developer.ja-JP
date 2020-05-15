---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 86bdc71375e5789d89c380a43d09e49a5640f7fb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654483"
---
# WebView2 クラス (CoreWebView2Controller クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

このクラスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化やコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AcceleratorKeyPressed](#acceleratorkeypressed) | AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。
[範囲](#bounds) | Webview の境界。
[CoreWebView2](#corewebview2) | この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。
[GotFocus](#gotfocus) | GotFocus は、WebView がフォーカスを取得したときに発生します。
[IsVisible](#isvisible) | IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。
[LostFocus](#lostfocus) | このとき、WebView はフォーカスを失ったときに発生します。
[MoveFocusRequested](#movefocusrequested) | MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。
[ParentWindow](#parentwindow) | この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。
[ZoomFactor](#zoomfactor) | WebView のズームファクター。
[ZoomFactorChanged](#zoomfactorchanged) | WebView の ZoomFactor プロパティが変更されると、イベントが発生します。
[Close](#close) | WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。
[MoveFocus](#movefocus) | WebView にフォーカスを移動します。
[NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged) | これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。
[SetBoundsAndZoomFactor](#setboundsandzoomfactor) | 同時に境界と ZoomFactor のプロパティを更新します。

CoreWebView2Controller は CoreWebView2 を所有しており、CoreWebView2Controller へのすべての参照が終了した場合、WebView は閉じられます。

## Members

#### AcceleratorKeyPressed 

AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。

> パブリックイベント EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)  >  [AcceleratorKeyPressed](#acceleratorkeypressed)

AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。 次のいずれかの場合、キーはアクセラレータと見なされます。

1. Ctrl または Alt は現在保留中か

1. 押されたキーは文字にマップされません。 一部の特定のキーは、Shift などのアクセラレータとは見なされません。 Escape キーは、常にアクセラレータと見なされます。

キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。 これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。

ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。 イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。 ただし、すべての CoreWebView2 API メソッドが動作します。

ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。 さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。

ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。

#### 範囲 

Webview の境界。

> パブリック四角形の[境界](#bounds)

境界は親 HWND を基準としています。 アプリには、WebView を配置する2つの方法があります。

1. WebView 親 HWND である子 HWND を作成します。 WebView が必要な場所にこのウィンドウを配置します。 この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。

1. アプリの一番上のウィンドウは、WebView 親 HWND として使います。 Webview の左上隅を、アプリ内で適切に配置されるように設定します。 バインドされた値は、ホストの座標空間にあります。

#### CoreWebView2 

この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。

> パブリック[CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)

#### GotFocus 

GotFocus は、WebView がフォーカスを取得したときに発生します。

> パブリックイベントハンドラー< オブジェクト > [GotFocus](#gotfocus)

#### IsVisible 

IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。

> public bool [IsVisible](#isvisible)

IsVisible が false に設定されている場合、webview は透過的であり、表示されません。 ただし、この操作を行っても、webview (CreateCoreWebView2Controller に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。 ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。 子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。 パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。 アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。

#### LostFocus 

このとき、WebView はフォーカスを失ったときに発生します。

> パブリックイベント EventHandler< オブジェクト > [LostFocus](#lostfocus)

MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。 フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。

#### MoveFocusRequested 

MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。

> パブリックイベント EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)  >  [movefocusrequested](#movefocusrequested)

このイベントが発生すると、WebView のフォーカスが変更されません。

#### ParentWindow 

この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。

> パブリック IntPtr の[親ウィンドウ](#parentwindow)

プロパティを設定すると、WebView が、新しく提供されたウィンドウにウィンドウを再表示します。

#### ZoomFactor 

WebView のズームファクター。

> パブリックダブル[ZoomFactor](#zoomfactor)

ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。 ZoomFactor を呼び出して、ホストによって適用される拡大率は、WebView の新しい既定のズームになります。 このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。 拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。 すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。 0以下の zoomFactor を指定することはできません。 WebView には、内部でサポートされているズームファクター範囲もあります。 指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。 この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。

#### ZoomFactorChanged 

WebView の ZoomFactor プロパティが変更されると、イベントが発生します。

> public イベント EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)

呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。 ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。 WebView は、各サイトで使用されている直前の拡大率を関連付けます。 そのため、別のページに移動するときにズーム倍率が変更される可能性があります。 このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。

#### Close 

WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。

> パブリックの void [Close](#close)()

ブラウザインスタンスをクリーンアップすると、WebView を電源にしているリソースが解放されます。 他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。

Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。 具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。

Close は、CoreWebView2Controller が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。 ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。 具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。 Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。 ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。

#### MoveFocus 

WebView にフォーカスを移動します。

> パブリック void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md)の理由)

WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。 プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。 次の理由から、フォーカスは最初の要素に設定されます。 前の理由から、フォーカスは最後の要素に設定されます。 また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。 Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。 または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。 プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。 WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。

#### NotifyParentWindowPositionChanged 

これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。

> パブリック void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()

これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。

#### SetBoundsAndZoomFactor 

同時に境界と ZoomFactor のプロパティを更新します。

> パブリック void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect 境界、double ZoomFactor)

この操作は、ホストの観点からはアトミックです。 この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。 境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。 この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。

