---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 83193a6034184a630122864d5893ed6869ed88ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654512"
---
# インターフェイス ICoreWebView2Settings 

```
interface ICoreWebView2Settings
  : public IUnknown
```

WebView 機能を有効、無効、または変更するプロパティを定義します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。
[get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled) | Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。
[get_AreDevToolsEnabled](#get_aredevtoolsenabled) | Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。
[get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed) | AreRemoteObjectsAllowed プロパティは、webview のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。
[get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。
[get_IsScriptEnabled](#get_isscriptenabled) | WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。
[get_IsStatusBarEnabled](#get_isstatusbarenabled) | IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。
[get_IsWebMessageEnabled](#get_iswebmessageenabled) | IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。
[get_IsZoomControlEnabled](#get_iszoomcontrolenabled) | IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。
[put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled プロパティを設定します。
[put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled) | AreDefaultScriptDialogsEnabled プロパティを設定します。
[put_AreDevToolsEnabled](#put_aredevtoolsenabled) | Aredevset Enabled プロパティを設定します。
[put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed) | AreRemoteObjectsAllowed プロパティを設定します。
[put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled プロパティを設定します。
[put_IsScriptEnabled](#put_isscriptenabled) | IsScriptEnabled プロパティを設定します。
[put_IsStatusBarEnabled](#put_isstatusbarenabled) | IsStatusBarEnabled プロパティを設定します。
[put_IsWebMessageEnabled](#put_iswebmessageenabled) | IsWebMessageEnabled プロパティを設定します。
[put_IsZoomControlEnabled](#put_iszoomcontrolenabled) | IsZoomControlEnabled プロパティを設定します。

NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。

## Members

#### get_AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティは、既定のコンテキストメニューが webview でユーザーに表示されないようにするために使われます。

> パブリック HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(ブール * enabled)

既定値は TRUE です。

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

#### get_AreDefaultScriptDialogsEnabled 

Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。

> パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール * Aredefaultscriptな有効)

False に設定すると、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数、beforeunload イベントによって表示されます)。 代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。

#### get_AreDevToolsEnabled 

Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。

> パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール * areDevToolsEnabled)

既定では true です。

#### get_AreRemoteObjectsAllowed 

AreRemoteObjectsAllowed プロパティは、webview のページからホストオブジェクトにアクセスできるかどうかを制御するために使用されます。

> パブリック HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(ブール * 使用可能)

既定値は TRUE です。

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

#### get_IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled プロパティを使って、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを無効にします。

> パブリック HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(ブール * enabled)

既定値は TRUE です。 無効にすると、関連するエラーが発生したときに空白のページが表示されます。

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

#### get_IsScriptEnabled 

WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。

> パブリック HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(ブール * isScriptEnabled)

これは、文書内のスクリプトにのみ影響します。スクリプトが無効になっている場合でも、ExecuteScript によって挿入されたスクリプトが実行されます。 既定では true です。

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

#### get_IsStatusBarEnabled 

IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。

> パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL * IsStatusBarEnabled)

通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。 既定では true です。

#### get_IsWebMessageEnabled 

IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。

> パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL * IsWebMessageEnabled)

True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。 Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。 False に設定すると、通信は許可されません。 PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。 既定では true です。

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### get_IsZoomControlEnabled 

IsZoomControlEnabled プロパティは、ユーザーが WebView のズームに影響しないようにするために使われます。

> パブリック HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(ブール * enabled)

既定値は TRUE です。 無効にした場合、ユーザーは ctrl +/-または ctrl + マウスホイールを使用してズームすることはできませんが、ズームは ZoomFactor API を使って設定できます。

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

#### put_AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled プロパティを設定します。

> パブリック HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)

#### put_AreDefaultScriptDialogsEnabled 

AreDefaultScriptDialogsEnabled プロパティを設定します。

> パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)

#### put_AreDevToolsEnabled 

Aredevset Enabled プロパティを設定します。

> パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)

#### put_AreRemoteObjectsAllowed 

AreRemoteObjectsAllowed プロパティを設定します。

> パブリック HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(ブール値が許可されています)

#### put_IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled プロパティを設定します。

> パブリック HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)

#### put_IsScriptEnabled 

IsScriptEnabled プロパティを設定します。

> パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)

#### put_IsStatusBarEnabled 

IsStatusBarEnabled プロパティを設定します。

> パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)

#### put_IsWebMessageEnabled 

IsWebMessageEnabled プロパティを設定します。

> パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)

#### put_IsZoomControlEnabled 

IsZoomControlEnabled プロパティを設定します。

> パブリック HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)

