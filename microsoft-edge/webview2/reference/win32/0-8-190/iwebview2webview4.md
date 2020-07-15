---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 8b029202843dd006be4d9ecdadc63161bebb6b39
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878058"
---
# <span data-ttu-id="6c25d-104">0.8.355-インターフェイス IWebView2WebView4</span><span class="sxs-lookup"><span data-stu-id="6c25d-104">0.8.355 - interface IWebView2WebView4</span></span> 

> [!NOTE]
> <span data-ttu-id="6c25d-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="6c25d-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c25d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView4
  : public IWebView2WebView3
```

<span data-ttu-id="6c25d-107">プライマリ WebView オブジェクトによって実装されるその他の機能。</span><span class="sxs-lookup"><span data-stu-id="6c25d-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="6c25d-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6c25d-108">Summary</span></span>

 <span data-ttu-id="6c25d-109">Members</span><span class="sxs-lookup"><span data-stu-id="6c25d-109">Members</span></span>                        | <span data-ttu-id="6c25d-110">説明</span><span class="sxs-lookup"><span data-stu-id="6c25d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6c25d-111">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="6c25d-111">AddRemoteObject</span></span>](#addremoteobject) | <span data-ttu-id="6c25d-112">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-112">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="6c25d-113">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="6c25d-113">RemoveRemoteObject</span></span>](#removeremoteobject) | <span data-ttu-id="6c25d-114">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c25d-114">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="6c25d-115">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6c25d-115">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="6c25d-116">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-116">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="6c25d-117">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="6c25d-117">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="6c25d-118">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-118">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="6c25d-119">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="6c25d-119">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="6c25d-120">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-120">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="6c25d-121">WEBVIEW2_KEY_EVENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="6c25d-121">WEBVIEW2_KEY_EVENT_TYPE</span></span>](#webview2_key_event_type) | <span data-ttu-id="6c25d-122">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="6c25d-122">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="6c25d-123">WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="6c25d-123">WEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#webview2_physical_key_status) | <span data-ttu-id="6c25d-124">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="6c25d-124">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

<span data-ttu-id="6c25d-125">このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-125">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="6c25d-126">詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c25d-126">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="6c25d-127">Members</span><span class="sxs-lookup"><span data-stu-id="6c25d-127">Members</span></span>

#### <span data-ttu-id="6c25d-128">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="6c25d-128">AddRemoteObject</span></span> 

<span data-ttu-id="6c25d-129">指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-129">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="6c25d-130">パブリック HRESULT [Addremoteobject](#addremoteobject)(LPCWSTR NAME, VARIANT \* object)</span><span class="sxs-lookup"><span data-stu-id="6c25d-130">public HRESULT [AddRemoteObject](#addremoteobject)(LPCWSTR name,VARIANT \* object)</span></span>

<span data-ttu-id="6c25d-131">ホストオブジェクトは、を通じてリモートオブジェクトプロキシとして公開され `window.chrome.webview.remoteObjects.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-131">Host objects are exposed as remote object proxies via `window.chrome.webview.remoteObjects.<name>`.</span></span> <span data-ttu-id="6c25d-132">リモートオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-132">Remote object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="6c25d-133">アプリが名前付きのオブジェクトを追加していない場合、promise は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-133">The promise is rejected if the app has not added an object with the name.</span></span> <span data-ttu-id="6c25d-134">JavaScript コードがオブジェクトのプロパティまたはメソッドにアクセスする場合、promise が返されます。これは、ホストからプロパティやメソッドに対して返された値に解決されます。また、オブジェクトやパラメーターのプロパティやメソッドが無効であるなどのエラーが発生した場合には拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-134">When JavaScript code access a property or method of the object, a promise is return, which will resolve to the value returned from the host for the property or method, or rejected in case of error such as there is no such property or method on the object or parameters are invalid.</span></span> <span data-ttu-id="6c25d-135">たとえば、次のようなアプリケーションコードを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="6c25d-135">For example, when the application code does the following:</span></span> 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 <span data-ttu-id="6c25d-136">WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-136">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span> 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 <span data-ttu-id="6c25d-137">単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c25d-137">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="6c25d-138">コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-138">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="6c25d-139">JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-139">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="6c25d-140">入れ子になった配列は、最大3レベルまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-140">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="6c25d-141">参照型での配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-141">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="6c25d-142">VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-142">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="6c25d-143">JavaScript は null で、undefined は VT_EMPTY にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-143">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="6c25d-144">さらに、すべてのリモートオブジェクトはとして公開され `window.chrome.webview.remoteObjects.sync.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-144">Additionally, all remote objects are exposed as `window.chrome.webview.remoteObjects.sync.<name>`.</span></span> <span data-ttu-id="6c25d-145">ここでは、ホストオブジェクトが同期リモートオブジェクトプロキシとして公開されています。</span><span class="sxs-lookup"><span data-stu-id="6c25d-145">Here the host objects are exposed as synchronous remote object proxies.</span></span> <span data-ttu-id="6c25d-146">これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-146">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="6c25d-147">これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.remoteObjects.<name>` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-147">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.remoteObjects.<name>` API described above.</span></span>

<span data-ttu-id="6c25d-148">同期リモートオブジェクトプロキシと非同期リモートオブジェクトプロキシはどちらも、同じリモートオブジェクトをプロキシすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-148">Synchronous remote object proxies and asynchronous remote object proxies can both proxy the same remote object.</span></span> <span data-ttu-id="6c25d-149">1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同一のリモートオブジェクトの他のプロキシにも反映されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-149">Remote changes made by one proxy will be reflected in any other proxy of that same remote object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="6c25d-150">JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-150">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="6c25d-151">これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-151">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="6c25d-152">リモートオブジェクトプロキシは JavaScript プロキシオブジェクトで、すべてのプロパティ get、プロパティセット、メソッドの呼び出しを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-152">Remote object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="6c25d-153">関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-153">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="6c25d-154">さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.remoteObjects.options.forceLocalProperties` もローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-154">Additionally any property or method in the array `chrome.webview.remoteObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="6c25d-155">これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-155">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="6c25d-156">必要に応じて、この配列に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-156">You can add more to this array as required.</span></span>

<span data-ttu-id="6c25d-157">最適な手段と `chrome.webview.remoteObjects.cleanupSome` して、リモートオブジェクトプロキシを収集する方法があります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-157">There's a method `chrome.webview.remoteObjects.cleanupSome` that will best effort garbage collect remote object proxies.</span></span>

<span data-ttu-id="6c25d-158">リモートオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-158">Remote object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="6c25d-159">applyRemote、getRemote、setRemote: リモートオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-159">applyRemote, getRemote, setRemote: Perform a method invocation, property get, or property set on the remote object.</span></span> <span data-ttu-id="6c25d-160">これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-160">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="6c25d-161">たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-161">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="6c25d-162">ただし `proxy.applyRemote('toString')` `toString` 、代わりにリモートプロキシオブジェクトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-162">But `proxy.applyRemote('toString')` runs `toString` on the remote proxied object instead.</span></span>

* <span data-ttu-id="6c25d-163">getLocal、setLocal: プロパティ get、またはローカルにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-163">getLocal, setLocal: Perform property get, or property set locally.</span></span> <span data-ttu-id="6c25d-164">これらのメソッドを使って、リモートオブジェクトプロキシ自体のプロパティを、それが表すリモートオブジェクトではなく、強制的に取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-164">You can use these methods to force getting or setting a property on the remote object proxy itself rather than on the remote object it represents.</span></span> <span data-ttu-id="6c25d-165">たとえば、 `proxy.unknownProperty` は、リモートプロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-165">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the remote proxied object.</span></span> <span data-ttu-id="6c25d-166">ただし、この `proxy.getLocal('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-166">But `proxy.getLocal('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="6c25d-167">同期: 非同期のリモートオブジェクトプロキシは、同一のリモートオブジェクトの同期リモートオブジェクトプロキシの promise を返す同期メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-167">sync: Asynchronous remote object proxies expose a sync method which returns a promise for a synchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="6c25d-168">たとえば、 `chrome.webview.remoteObjects.sample.methodCall()` 非同期のリモートオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-168">For example, `chrome.webview.remoteObjects.sample.methodCall()` returns an asynchronous remote object proxy.</span></span> <span data-ttu-id="6c25d-169">代わりに、メソッドを使用して `sync` 同期リモートオブジェクトプロキシを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-169">You can use the `sync` method to obtain a synchronous remote object proxy instead:</span></span> `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* <span data-ttu-id="6c25d-170">非同期: 同期リモートオブジェクトプロキシは、同じリモートオブジェクトの非同期リモートオブジェクトプロキシをブロックして返す async メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-170">async: Synchronous remote object proxies expose an async method which blocks and returns an asynchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="6c25d-171">たとえば、 `chrome.webview.remoteObjects.sync.sample.methodCall()` 同期リモートオブジェクトプロキシを返します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-171">For example, `chrome.webview.remoteObjects.sync.sample.methodCall()` returns a synchronous remote object proxy.</span></span> <span data-ttu-id="6c25d-172">このブロックに対してメソッドを呼び出す `async` と、同じリモートオブジェクトの非同期リモートオブジェクトプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-172">Calling the `async` method on this blocks and then returns an asynchronous remote object proxy for the same remote object:</span></span> `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="6c25d-173">次に、非同期リモートオブジェクトプロキシには then メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-173">then: Asynchronous remote object proxies have a then method.</span></span> <span data-ttu-id="6c25d-174">これにより、awaitable を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-174">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="6c25d-175">リモートオブジェクトの表現によって解決される promise を返します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-175">will return a promise that resolves with a representation of the remote object.</span></span> <span data-ttu-id="6c25d-176">プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-176">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="6c25d-177">プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-177">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="6c25d-178">プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティと共にリモートオブジェクトプロキシとして返されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-178">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as remote object proxies.</span></span>

<span data-ttu-id="6c25d-179">その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-179">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="6c25d-180">非同期のリモートオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-180">Asynchronous remote object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="6c25d-181">この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-181">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="6c25d-182">同期リモートオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-182">Synchronous remote object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="6c25d-183">非同期リモートオブジェクトプロキシのプロパティの設定は、少し異なります。</span><span class="sxs-lookup"><span data-stu-id="6c25d-183">Setting a property on an asynchronous remote object proxy works slightly differently.</span></span> <span data-ttu-id="6c25d-184">Set はすぐに戻り値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-184">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="6c25d-185">これは JavaScript プロキシオブジェクトの要件です。</span><span class="sxs-lookup"><span data-stu-id="6c25d-185">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="6c25d-186">プロパティセットの完了を非同期的に待つ必要がある場合は、前述のように、setRemote メソッドを使って、promise を返します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-186">If you need to asynchronously wait for the property set to complete, use the setRemote method which returns a promise as described above.</span></span> <span data-ttu-id="6c25d-187">同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-187">Synchronous object property set property synchronously blocks until the property is set.</span></span>

<span data-ttu-id="6c25d-188">たとえば、次のインターフェイスを持つ COM オブジェクトがあるとします。</span><span class="sxs-lookup"><span data-stu-id="6c25d-188">For example, suppose you have a COM object with the following interface</span></span>

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

 <span data-ttu-id="6c25d-189">このインターフェイスのインスタンスは、の JavaScript に追加することができ `AddRemoteObject` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-189">We can add an instance of this interface into our JavaScript with `AddRemoteObject`.</span></span> <span data-ttu-id="6c25d-190">この場合は、次のように名前を指定し `sample` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-190">In this case we name it `sample`:</span></span>

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

 <span data-ttu-id="6c25d-191">HTML 文書では、次の方法でこの COM オブジェクトを使うことができ `chrome.webview.remoteObjects.sample` ます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-191">Then in the HTML document we can use this COM object via `chrome.webview.remoteObjects.sample`:</span></span>

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

#### <span data-ttu-id="6c25d-192">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="6c25d-192">RemoveRemoteObject</span></span> 

<span data-ttu-id="6c25d-193">名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c25d-193">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="6c25d-194">パブリック HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="6c25d-194">public HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)</span></span>

<span data-ttu-id="6c25d-195">新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-195">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="6c25d-196">既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-196">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="6c25d-197">Opendevツールウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6c25d-197">OpenDevToolsWindow</span></span> 

<span data-ttu-id="6c25d-198">WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-198">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="6c25d-199">パブリック HRESULT [Opendevツールウィンドウ](#opendevtoolswindow)()</span><span class="sxs-lookup"><span data-stu-id="6c25d-199">public HRESULT [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="6c25d-200">DevTools ウィンドウが既に開いているときに、何も呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-200">Does nothing if called when the DevTools window is already open</span></span>

#### <span data-ttu-id="6c25d-201">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="6c25d-201">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="6c25d-202">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-202">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="6c25d-203">パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="6c25d-203">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([IWebView2AcceleratorKeyPressedEventHandler](IWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="6c25d-204">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-204">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="6c25d-205">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-205">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="6c25d-206">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="6c25d-206">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="6c25d-207">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-207">the pressed key does not map to a character.</span></span> <span data-ttu-id="6c25d-208">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="6c25d-208">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="6c25d-209">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-209">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="6c25d-210">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-210">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="6c25d-211">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-211">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="6c25d-212">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-212">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="6c25d-213">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-213">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="6c25d-214">ただし、すべての WebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-214">All WebView2 API methods will work, however.</span></span>

<span data-ttu-id="6c25d-215">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6c25d-215">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="6c25d-216">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-216">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="6c25d-217">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c25d-217">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

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

#### <span data-ttu-id="6c25d-218">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="6c25d-218">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="6c25d-219">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-219">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="6c25d-220">パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="6c25d-220">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="6c25d-221">WEBVIEW2_KEY_EVENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="6c25d-221">WEBVIEW2_KEY_EVENT_TYPE</span></span> 

<span data-ttu-id="6c25d-222">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="6c25d-222">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="6c25d-223">列挙型[WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)</span><span class="sxs-lookup"><span data-stu-id="6c25d-223">enum [WEBVIEW2_KEY_EVENT_TYPE](#webview2_key_event_type)</span></span>

 <span data-ttu-id="6c25d-224">値</span><span class="sxs-lookup"><span data-stu-id="6c25d-224">Values</span></span>                         | <span data-ttu-id="6c25d-225">説明</span><span class="sxs-lookup"><span data-stu-id="6c25d-225">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="6c25d-226">WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="6c25d-226">WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN</span></span>            | <span data-ttu-id="6c25d-227">ウィンドウメッセージ WM_KEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-227">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="6c25d-228">WEBVIEW2_KEY_EVENT_TYPE_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="6c25d-228">WEBVIEW2_KEY_EVENT_TYPE_KEY_UP</span></span>            | <span data-ttu-id="6c25d-229">ウィンドウメッセージ WM_KEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-229">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="6c25d-230">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="6c25d-230">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="6c25d-231">ウィンドウメッセージ WM_SYSKEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-231">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="6c25d-232">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="6c25d-232">WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="6c25d-233">ウィンドウメッセージ WM_SYSKEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="6c25d-233">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="6c25d-234">WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="6c25d-234">WEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="6c25d-235">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="6c25d-235">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="6c25d-236">typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="6c25d-236">typedef [WEBVIEW2_PHYSICAL_KEY_STATUS](#webview2_physical_key_status)</span></span>

<span data-ttu-id="6c25d-237">詳細については、WM_KEYDOWN のドキュメントを参照してください。[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="6c25d-237">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

