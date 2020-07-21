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
# 0.8.355-インターフェイス IWebView2Settings 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings
  : public IUnknown
```

WebView 機能を有効、無効、または変更するプロパティを定義します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsScriptEnabled](#get_isscriptenabled) | WebView で今後のすべてのナビゲーションで JavaScript の実行が有効になっているかどうかを制御します。
[put_IsScriptEnabled](#put_isscriptenabled) | IsScriptEnabled プロパティを設定します。
[get_IsWebMessageEnabled](#get_iswebmessageenabled) | IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。
[put_IsWebMessageEnabled](#put_iswebmessageenabled) | IsWebMessageEnabled プロパティを設定します。
[get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled) | Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。
[put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled) | AreDefaultScriptDialogsEnabled プロパティを設定します。
[get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated) | この設定は廃止され、常に false を返します。
[put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated) | この設定は廃止され、効果はありません。
[get_IsStatusBarEnabled](#get_isstatusbarenabled) | IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。
[put_IsStatusBarEnabled](#put_isstatusbarenabled) | IsStatusBarEnabled プロパティを設定します。
[get_AreDevToolsEnabled](#get_aredevtoolsenabled) | Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。
[put_AreDevToolsEnabled](#put_aredevtoolsenabled) | Aredevset Enabled プロパティを設定します。

NavigationStarting イベント後に行われた設定の変更は、次の最上位レベルのナビゲーションまで適用されません。

## Members

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

#### put_IsScriptEnabled 

IsScriptEnabled プロパティを設定します。

> パブリック HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)

#### get_IsWebMessageEnabled 

IsWebMessageEnabled プロパティは、新しい HTML ドキュメントを読み込むときに使用されます。

> パブリック HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL * IsWebMessageEnabled)

True に設定されている場合、ホストから webview のトップレベル HTML ドキュメントは、PostWebMessageAsJson、Postwebmessageasjson、およびウィンドウの chrome のメッセージイベントで許可されます (詳細については、「PostWebMessageAsJson のドキュメント」を参照してください)。 Webview の最上位レベル HTML ドキュメントからホストへの通信は、postMessage 関数と SetWebMessageReceivedEventHandler メソッドを使って行うことができます (詳細については、SetWebMessageReceivedEventHandler のドキュメントを参照してください)。 False に設定すると、通信は許可されません。 PostWebMessageAsJson と Postwebmessageasjson は、postMessage と E_ACCESSDENIED で失敗し、エラーオブジェクトのインスタンスをスローします。 既定では true です。

```cpp
    ComPtr<IWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### put_IsWebMessageEnabled 

IsWebMessageEnabled プロパティを設定します。

> パブリック HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL IsWebMessageEnabled)

#### get_AreDefaultScriptDialogsEnabled 

Aredefaultscriptた Enabled は、新しい HTML ドキュメントを読み込むときに使用されます。

> パブリック HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(ブール * Aredefaultscriptな有効)

False に設定した場合、WebView には、既定の javascript ダイアログボックスは表示されません (具体的には、javascript alert、confirm、prompt 関数によって表示されます)。 代わりに、イベントハンドラーが SetScriptDialogOpeningEventHandler によって設定されている場合、WebView は、ダイアログのすべての情報が含まれるイベントを送信し、ホストアプリが独自のカスタム UI を表示できるようにします。

#### put_AreDefaultScriptDialogsEnabled 

AreDefaultScriptDialogsEnabled プロパティを設定します。

> パブリック HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(ブール値は Defaultscriptして有効)

#### get_IsFullscreenAllowed_deprecated 

この設定は廃止され、常に false を返します。

> パブリック HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(ブール * isFullscreenAllowed)

つまり、WebView の要素は、WebView の境界線にのみ表示されます。 このプロパティは、完全に削除されます。 指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。

WebView の要素に対してフルスクリーンを許可するかどうかを制御します。 許可されている場合、WebView の video 要素などの web コンテンツは全画面表示にすることができます。 許可されていない場合、この要素は、要素が全画面表示を要求したときに WebView の境界線を埋めます。 既定では true です。

#### put_IsFullscreenAllowed_deprecated 

この設定は廃止され、効果はありません。

> パブリック HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)

指定した場合は、ここでは、すべての ' Fullfullscreenelementchanged イベントをリッスンしてください。

IsFullscreenAllowed プロパティを設定します。

#### get_IsStatusBarEnabled 

IsStatusBarEnabled は、ステータスバーを表示するかどうかを制御します。

> パブリック HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL * IsStatusBarEnabled)

通常、ステータスバーは WebView の左下に表示され、ユーザーがマウスをポイントしたときのリンクの URI などの情報が表示されます。 既定では true です。

#### put_IsStatusBarEnabled 

IsStatusBarEnabled プロパティを設定します。

> パブリック HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL IsStatusBarEnabled)

#### get_AreDevToolsEnabled 

Aredevtools Enabled は、ユーザーがコンテキストメニューまたはキーボードショートカットを使用して DevTools ウィンドウを開くことができるかどうかを制御します。

> パブリック HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(ブール * areDevToolsEnabled)

既定では true です。

#### put_AreDevToolsEnabled 

Aredevset Enabled プロパティを設定します。

> パブリック HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL = Devtaskenabled)

