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
ms.openlocfilehash: 6ebed9e61bf7eda60e6e16b7a417306baa5d07bf
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654167"
---
# インターフェイス IWebView2WebView4 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2WebView4
  : public IWebView2WebView3
```

プライマリ WebView オブジェクトによって実装されるその他の機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AddRemoteObject](#addremoteobject) | 指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。
[RemoveRemoteObject](#removeremoteobject) | 名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。
[Opendevツールウィンドウ](#opendevtoolswindow) | WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。
[add_AcceleratorKeyPressed](#add_acceleratorkeypressed) | AcceleratorKeyPressed イベントのイベントハンドラーを追加します。
[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed) | Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。
[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type) | AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。
[WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status) | Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。 詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。

## Members

#### AddRemoteObject 

指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。

> パブリック HRESULT [Addremoteobject](#addremoteobject)(LPCWSTR NAME, VARIANT * object)

ホストオブジェクトは、を通じてリモートオブジェクトプロキシとして公開され `window.chrome.webview.remoteObjects.<name>` ます。 リモートオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。 アプリが名前付きのオブジェクトを追加していない場合、promise は拒否されます。 JavaScript コードがオブジェクトのプロパティまたはメソッドにアクセスする場合、promise が返されます。これは、ホストからプロパティやメソッドに対して返された値に解決されます。また、オブジェクトやパラメーターのプロパティやメソッドが無効であるなどのエラーが発生した場合には拒否されます。 たとえば、次のようなアプリケーションコードを実行するとします。 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。 コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。 JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。 入れ子になった配列は、最大3レベルまでサポートされます。 参照型での配列はサポートされていません。 VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。 JavaScript は null で、undefined は VT_EMPTY にマップされます。

さらに、すべてのリモートオブジェクトはとして公開され `window.chrome.webview.remoteObjects.sync.<name>` ます。 ここでは、ホストオブジェクトが同期リモートオブジェクトプロキシとして公開されています。 これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。 これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.remoteObjects.<name>` ます。

同期リモートオブジェクトプロキシと非同期リモートオブジェクトプロキシはどちらも、同じリモートオブジェクトをプロキシすることができます。 1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同一のリモートオブジェクトの他のプロキシにも反映されます。

JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。 これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。

リモートオブジェクトプロキシは JavaScript プロキシオブジェクトで、すべてのプロパティ get、プロパティセット、メソッドの呼び出しを受け取ります。 関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。 さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.remoteObjects.options.forceLocalProperties` もローカルで実行されます。 これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。 必要に応じて、この配列に追加することができます。

最適な手段と `chrome.webview.remoteObjects.cleanupSome` して、リモートオブジェクトプロキシを収集する方法があります。

リモートオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。

* applyRemote、getRemote、setRemote: リモートオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。 これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。 たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。 ただし `proxy.applyRemote('toString')` `toString` 、代わりにリモートプロキシオブジェクトで実行されます。

* getLocal、setLocal: プロパティ get、またはローカルにプロパティを設定します。 これらのメソッドを使って、リモートオブジェクトプロキシ自体のプロパティを、それが表すリモートオブジェクトではなく、強制的に取得または設定することができます。 たとえば、 `proxy.unknownProperty` は、リモートプロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。 ただし、この `proxy.getLocal('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。

* 同期: 非同期のリモートオブジェクトプロキシは、同一のリモートオブジェクトの同期リモートオブジェクトプロキシの promise を返す同期メソッドを公開します。 たとえば、 `chrome.webview.remoteObjects.sample.methodCall()` 非同期のリモートオブジェクトプロキシを返します。 代わりに、メソッドを使用して `sync` 同期リモートオブジェクトプロキシを取得できます。 `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* 非同期: 同期リモートオブジェクトプロキシは、同じリモートオブジェクトの非同期リモートオブジェクトプロキシをブロックして返す async メソッドを公開します。 たとえば、 `chrome.webview.remoteObjects.sync.sample.methodCall()` 同期リモートオブジェクトプロキシを返します。 このブロックに対してメソッドを呼び出す `async` と、同じリモートオブジェクトの非同期リモートオブジェクトプロキシが返されます。 `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* 次に、非同期リモートオブジェクトプロキシには then メソッドがあります。 これにより、awaitable を行うことができます。 `then` リモートオブジェクトの表現によって解決される promise を返します。 プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。 プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。 プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティと共にリモートオブジェクトプロキシとして返されます。

その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。 非同期のリモートオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。 この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。 同期リモートオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。

非同期リモートオブジェクトプロキシのプロパティの設定は、少し異なります。 Set はすぐに戻り値として設定されます。 これは JavaScript プロキシオブジェクトの要件です。 プロパティセットの完了を非同期的に待つ必要がある場合は、前述のように、setRemote メソッドを使って、promise を返します。 同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。

たとえば、次のインターフェイスを持つ COM オブジェクトがあるとします。

```idl
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IRemoteObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);
    };
```

 このインターフェイスのインスタンスは、の JavaScript に追加することができ `AddRemoteObject` ます。 この場合は、次のように名前を指定し `sample` ます。

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_remoteObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddRemoteObject multiple times in a row without
            // calling RemoveRemoteObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(m_webView->AddRemoteObject(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```

 HTML 文書では、次の方法でこの COM オブジェクトを使うことができ `chrome.webview.remoteObjects.sample` ます。

```js
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = await chrome.webview.remoteObjects.sample.property;
            document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
            const propertyValue = chrome.webview.remoteObjects.sync.sample.property;
            document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyAsyncInput").value;
            // The following line will work but it will return immediately before the property value has actually been set.
            // If you need to set the property and wait for the property to change value, use the setRemote function.
            chrome.webview.remoteObjects.sample.property = propertyValue;
            document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
            // If you care about waiting until the property has actually changed value use the setRemote function.
            await chrome.webview.remoteObjects.sample.setRemote("property", propertyValue);
            document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
            const propertyValue = document.getElementById("setPropertySyncInput").value;
            chrome.webview.remoteObjects.sync.sample.property = propertyValue;
            document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
            const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
            const resultValue = await chrome.webview.remoteObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
            const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
            const resultValue = chrome.webview.remoteObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
            chrome.webview.remoteObjects.sample.CallCallbackAsynchronously(() => {
                document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
            });
        });
```

#### RemoveRemoteObject 

名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。

> パブリック HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)

新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。 既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。

#### Opendevツールウィンドウ 

WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。

> パブリック HRESULT [Opendevツールウィンドウ](#opendevtoolswindow)()

DevTools ウィンドウが既に開いているときに、何も呼び出されません。

#### add_AcceleratorKeyPressed 

AcceleratorKeyPressed イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) * eventHandler、EventRegistrationToken * token)

AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。 次のいずれかの場合、キーはアクセラレータと見なされます。

1. Ctrl または Alt は現在保留中か

1. 押されたキーは文字にマップされません。 一部の特定のキーは、Shift などのアクセラレータとは見なされません。 Escape キーは、常にアクセラレータと見なされます。

キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。 これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。

ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。 イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。 ただし、すべての WebView2 API メソッドが動作します。

ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。 さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。

ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_webView->add_AcceleratorKeyPressed(
        Callback<IWebView2AcceleratorKeyPressedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2AcceleratorKeyPressedEventArgs* args)
                -> HRESULT {
                WEBVIEW2_KEY_EVENT_TYPE type;
                CHECK_FAILURE(args->get_KeyEventType(&type));
                // We only care about key down events.
                if (type == WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN ||
                    type == WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->Handle(TRUE));

                        // Filter out autorepeated keys.
                        WEBVIEW2_PHYSICAL_KEY_STATUS status;
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

#### WEBVIEW2_KEY_EVENT_TYPE 

AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。

> 列挙型[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN            | ウィンドウメッセージ WM_KEYDOWN に対応します。
WEBVIEW2_KEY_EVENT_TYPE_KEY_UP            | ウィンドウメッセージ WM_KEYUP に対応します。
WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN            | ウィンドウメッセージ WM_SYSKEYDOWN に対応します。
WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP            | ウィンドウメッセージ WM_SYSKEYUP に対応します。

#### WEBVIEW2_PHYSICAL_KEY_STATUS 

Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

> typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)

詳細については、WM_KEYDOWN のドキュメントを参照してください。[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)

