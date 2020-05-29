---
description: ネイティブメッセージングを使って、拡張機能とコンパニオン UWP アプリとの通信を行う方法について説明します。
title: 拡張機能-ネイティブメッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者、ネイティブ、メッセージング、uwp
ms.openlocfilehash: 83f80e112180317c38763225c1cdd015da4238b0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569477"
---
# <span data-ttu-id="310c3-104">Microsoft Edge のネイティブメッセージング</span><span class="sxs-lookup"><span data-stu-id="310c3-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="310c3-105">ネイティブメッセージングアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="310c3-105">Native messaging architecture overview</span></span>

<span data-ttu-id="310c3-106">Windows 10 の作成者の更新プログラムでは、Microsoft Edge extensions はネイティブメッセージングを使って、コンパニオンユニバーサル Windows プラットフォーム (UWP) アプリと通信できます。</span><span class="sxs-lookup"><span data-stu-id="310c3-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span></span>  <span data-ttu-id="310c3-107">高レベルでは、Microsoft Edge extensions は、Chrome および Firefox 拡張機能と同じ Api をネイティブメッセージに使用します。</span><span class="sxs-lookup"><span data-stu-id="310c3-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span> <span data-ttu-id="310c3-108">ただし、ネイティブメッセージングホストは、ユニバーサル Windows プラットフォームを使って実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>

> [!NOTE]
> <span data-ttu-id="310c3-109">次のように、Microsoft Edge extensions とネイティブコンポーネントの間の通信を有効にするためにサポートされているメカニズム (AppService 経由の UWP アプリへの接続) がサポートされている方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="310c3-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span> <span data-ttu-id="310c3-110">従来の Win32 コンポーネントとの通信を有効にする方法の詳細については、このガイドの「[デスクトップブリッジコンポーネントを追加](#adding-a-desktop-bridge-component)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="310c3-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span> 

 <span data-ttu-id="310c3-111">Microsoft Edge のネイティブメッセージングアーキテクチャは、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) 基礎となるプロセス間通信 (IPC) インフラストラクチャとして既存の API を活用します。</span><span class="sxs-lookup"><span data-stu-id="310c3-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span></span> <span data-ttu-id="310c3-112">UWP アプリは、 `AppService` API を使って互いに通信します。</span><span class="sxs-lookup"><span data-stu-id="310c3-112">UWP apps use the `AppService` API to communicate with one another.</span></span> <span data-ttu-id="310c3-113">このため、Microsoft Edge extensions は UWP アプリと通信できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="310c3-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span></span>

![ネイティブメッセージングアーキテクチャ](./../media/native-messaging-architecture.png)


### <span data-ttu-id="310c3-115">ネイティブメッセージングを使用するタイミング</span><span class="sxs-lookup"><span data-stu-id="310c3-115">When and when not to use native messaging</span></span>

<span data-ttu-id="310c3-116">ネイティブメッセージは、新しいレイヤー全体を拡張機能に追加します。</span><span class="sxs-lookup"><span data-stu-id="310c3-116">Native messaging adds a whole new layer to your extension.</span></span> <span data-ttu-id="310c3-117">拡張機能用の UWP コンパニオンアプリを実装することによって、次の可能性が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="310c3-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>

* <span data-ttu-id="310c3-118">データ (資格情報など) をコンパニオン UWP アプリと同期します。</span><span class="sxs-lookup"><span data-stu-id="310c3-118">Synchronize data (e.g. credentials) with a companion UWP app.</span></span>
* <span data-ttu-id="310c3-119">Web Api では、より強力な暗号化/暗号化アルゴリズムを実装することはできません。</span><span class="sxs-lookup"><span data-stu-id="310c3-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>
* <span data-ttu-id="310c3-120">ハードウェアや USB デバイスなどの web Api を介してアクセスできないリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="310c3-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span></span>

<span data-ttu-id="310c3-121">セキュリティまたはポリシーの制限により、ネイティブメッセージングを使用できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="310c3-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span></span>

* <span data-ttu-id="310c3-122">Microsoft Edge または Windows のいずれかでユーザー設定を変更する (例: 既定のブラウザーまたは検索プロバイダーの変更)。</span><span class="sxs-lookup"><span data-stu-id="310c3-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span></span>
* <span data-ttu-id="310c3-123">アプリと拡張機能の両方について、Microsoft ストアのポリシーに違反するアクション。</span><span class="sxs-lookup"><span data-stu-id="310c3-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>
* <span data-ttu-id="310c3-124">ネイティブメッセージホスト経由でリモートエンドポイントにデータを転送します。</span><span class="sxs-lookup"><span data-stu-id="310c3-124">Transferring data to remote endpoint via native message host.</span></span>
* <span data-ttu-id="310c3-125">拡張機能の動作を変更するコンテンツを他のアプリからダウンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="310c3-125">Allowing other apps to download content that changes extension behavior.</span></span>

## <span data-ttu-id="310c3-126">デモ</span><span class="sxs-lookup"><span data-stu-id="310c3-126">Demos</span></span>

<span data-ttu-id="310c3-127">コンパニオン UWP アプリと Desktop Bridge の両方を備えた Microsoft Edge のネイティブメッセージング拡張機能の外観を確認するには、GitHub の[Secureinput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput)と[DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning)の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="310c3-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>

### <span data-ttu-id="310c3-128">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="310c3-128">How it works</span></span>

<span data-ttu-id="310c3-129">サンプルの Microsoft Edge 拡張コンポーネントは、コンテンツスクリプトを使って、ユーザーが暗号化する必要がある情報を入力したときに検出します。</span><span class="sxs-lookup"><span data-stu-id="310c3-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span> <span data-ttu-id="310c3-130">拡張機能は、ネイティブメッセージ経由で、これを Desktop Bridge コンポーネントに伝えます。</span><span class="sxs-lookup"><span data-stu-id="310c3-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span> <span data-ttu-id="310c3-131">ユーザーがデータを送信する準備ができたら、拡張機能は暗号化された値を web サイトに戻します。</span><span class="sxs-lookup"><span data-stu-id="310c3-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>

> [!NOTE]
> <span data-ttu-id="310c3-132">このサンプルは、拡張機能のコンテンツスクリプトと通信するためにカスタムイベントを使う web ページでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="310c3-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span></span> <span data-ttu-id="310c3-133">サンプルのフォルダーには、拡張子をテストするための[.html ファイル](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="310c3-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>

<span data-ttu-id="310c3-134">この例では、UWP アプリを使って、Desktop Bridge から Microsoft Edge に応答を渡します。これは、コールバックによって Microsoft Edge extension に送信されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span> <span data-ttu-id="310c3-135">この例では、ネイティブメッセージングホストがメインアプリで実行されていますが、バックグラウンドタスクとして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="310c3-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span></span> <span data-ttu-id="310c3-136">この2つの切り替えを行うには、拡張機能のバックグラウンドスクリプトを編集する必要があり `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` `"NativeMessagingHostOutOfProcess"` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>

## <span data-ttu-id="310c3-137">Chrome vs Microsoft Edge の実装</span><span class="sxs-lookup"><span data-stu-id="310c3-137">Chrome vs Microsoft Edge implementation</span></span>

<span data-ttu-id="310c3-138">Chrome は、アプリと通信するための拡張機能のためにメッセージパッシング Api を使用するルートになっていますが、Microsoft Edge では、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) Microsoft edge extensions と UWP アプリの通信を可能にする api を利用しています。</span><span class="sxs-lookup"><span data-stu-id="310c3-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>

<span data-ttu-id="310c3-139">このセクションでは、Chrome と Microsoft Edge がネイティブメッセージングの実装を処理する方法の違いについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="310c3-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>

### <span data-ttu-id="310c3-140">登録とホストマニフェスト</span><span class="sxs-lookup"><span data-stu-id="310c3-140">Registration and host manifest</span></span>
<span data-ttu-id="310c3-141">アプリが拡張機能によってネイティブメッセージングホストとして認識されるためには、アプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>


<span data-ttu-id="310c3-142">[Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration の場合、アプリでは、ネイティブメッセージングホスト構成を定義する Windows ファイルシステム内の任意の場所にマニフェストファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>

<span data-ttu-id="310c3-143">次の JSON は、構成ファイルを設定する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="310c3-143">The following JSON is an example of how the config file can be set up:</span></span>

```json
{
   "name": "com.my_company.my_application",
   "description": "My Application",
   "path": "C:\\ProgramFiles\\MyApplication\\chrome_native_messaging_host.exe",
   "type": "stdio",
   "allowed_origins": [
      "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```

<span data-ttu-id="310c3-144">このファイルをインストールするには、アプリで次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-144">To install this file, the app would need to:</span></span>

1. <span data-ttu-id="310c3-145">ホスト構成を定義するレジストリ内の事前定義された場所にマニフェストファイルを登録します。</span><span class="sxs-lookup"><span data-stu-id="310c3-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>
   - `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

     <span data-ttu-id="310c3-146">または</span><span class="sxs-lookup"><span data-stu-id="310c3-146">or</span></span>
   - `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`

2. <span data-ttu-id="310c3-147">このキーの既定値をマニフェストファイルへの完全パスに設定します (例:</span><span class="sxs-lookup"><span data-stu-id="310c3-147">Set the default value of that key to the full path to the manifest file, e.g.</span></span>  `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`




<span data-ttu-id="310c3-148">Microsoft Edge では、(ネイティブメッセージホスト) を登録するために、 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) UWP コンパニオンアプリを拡張機能と同じパッケージに含める必要があります。また、プロジェクトのファイルで[AppService の拡張子](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)を指定する必要があり `Package.appxmanifest` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span></span> <span data-ttu-id="310c3-149">`EntryPoint`および属性は、 `Name` 次の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="310c3-149">The `EntryPoint` and `Name` attributes can be configured by you:</span></span>

```xml
...
<Applications>    
    <Application Id="App"         
        <Extensions>        
            <uap:Extension Category="windows.appService" EntryPoint="MyAppService.Inventory">          
            <uap:AppService Name="com.microsoft.inventory"/>        
            </uap:Extension>      
        </Extensions>      
        ...    
    </Application>
</Applications>
```


<span data-ttu-id="310c3-150">また、サービスへの接続を許可する拡張機能を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-150">You'll also need to set which extension(s) are allowed to connect to the service.</span></span> <span data-ttu-id="310c3-151">Microsoft Edge では、 `"allowed_origins"` package.appxmanifest に同等のマニフェストプロパティがないため、これは UWP アプリによって実行時に決定され、適用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span> <span data-ttu-id="310c3-152">Microsoft Edge は、拡張機能の代わりに接続を確立するため、アプリは呼び出し元のパッケージファミリ名を検索して、Microsoft Edge によって接続されているため、呼び出し元を制御または認証することができます。</span><span class="sxs-lookup"><span data-stu-id="310c3-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span></span> <span data-ttu-id="310c3-153">例:</span><span class="sxs-lookup"><span data-stu-id="310c3-153">E.g.</span></span> 

```csharp
protected async override void
OnBackgroundActivated(BackgroundActivatedEventArgs args)
{
    IBackgroundTaskInstance taskInstance = args.TaskInstance;
    if (taskInstance.TriggerDetails is AppServiceTriggerDetails)
    {
        AppServiceTriggerDetails appService = taskInstance.TriggerDetails as AppServiceTriggerDetails;
        if (appService.CallerPackageFamilyName == EdgePFN)
        {
            // Establish the connection
        }
        else
        {
            // Reject the connection
        }
    }
}
```



### <span data-ttu-id="310c3-154">メッセージ送信</span><span class="sxs-lookup"><span data-stu-id="310c3-154">Message sending</span></span>

<span data-ttu-id="310c3-155">アプリと拡張機能が相互に通信するためには、メッセージを送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>

<span data-ttu-id="310c3-156">Chrome 拡張機能 API を使ってメッセージを開始し、 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 非永続的なチャネルを使ってネイティブホストにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="310c3-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span> 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```

<span data-ttu-id="310c3-157">最初のパラメーターは、マニフェストのレジストリで Chrome が検索されるネイティブホストの名前です。</span><span class="sxs-lookup"><span data-stu-id="310c3-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span> <span data-ttu-id="310c3-158">マニフェストでは、Chrome がサンドボックスで起動する .exe を指定します。このマニフェストでは、標準 i/o を使ってメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span> <span data-ttu-id="310c3-159">また、拡張機能は API を使って永続的なチャネルを確立することもでき `runtime.connectNative` ます。これは、ネイティブホストの名前を唯一のパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="310c3-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span> 

<span data-ttu-id="310c3-160">Microsoft Edge では、Chrome のネイティブメッセージング API と同じ構成を使用して、Microsoft Edge 拡張機能が接続するアプリサービスを指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="310c3-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span></span> <span data-ttu-id="310c3-161">の最初のパラメーターは、 `runtime.sendNativeMessage` アプリサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="310c3-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span> <span data-ttu-id="310c3-162">[[登録とホストマニフェスト](#registration-and-host-manifest)] セクションで、これは `"com.microsoft.inventory"` です。</span><span class="sxs-lookup"><span data-stu-id="310c3-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span> <span data-ttu-id="310c3-163">Microsoft Edge extension platform は、拡張機能と同じ AppX にパッケージ化されている UWP アプリとしてネイティブメッセージングホストを制限します。</span><span class="sxs-lookup"><span data-stu-id="310c3-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span> <span data-ttu-id="310c3-164">これにより、マニフェストエントリが改ざんされ、Microsoft Edge を別のパッケージファミリ名に接続しようとしている悪意のある攻撃に関連するセキュリティリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span> 

<span data-ttu-id="310c3-165">つまり、Microsoft Edge では、API で指定された名前と同じパッケージファミリ名が、 `AppService` アプリサービスのプロバイダーを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="310c3-166">これは、 [Microsoft Edge 拡張ツールキット](./porting-chrome-extensions.md)によって簡単に変換されることはありません。</span><span class="sxs-lookup"><span data-stu-id="310c3-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span> <span data-ttu-id="310c3-167">アクセス許可を指定するすべての拡張機能に `"nativeMessaging"` は、このコンポーネントの手動変換が必要であるというマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="310c3-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>





### <span data-ttu-id="310c3-168">通信プロトコル</span><span class="sxs-lookup"><span data-stu-id="310c3-168">Communication protocol</span></span>

<span data-ttu-id="310c3-169">ネイティブメッセージングの通信プロトコルによって、送信前にメッセージの書式設定方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="310c3-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>

<span data-ttu-id="310c3-170">Chrome では、各ネイティブメッセージングホストが個別のプロセスで開始され、標準の入力と標準の出力を使って通信します。</span><span class="sxs-lookup"><span data-stu-id="310c3-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span> <span data-ttu-id="310c3-171">この形式は、両方の方向でメッセージを送信するために使用されます。各メッセージは JSON、UTF-8 encoded を使ってシリアル化され、その前に32ビットのメッセージ長がネイティブのバイト順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>


<span data-ttu-id="310c3-172">Microsoft Edge では、アプリサービスを実装するバックグラウンドタスク/メインアプリはプラットフォームによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span> <span data-ttu-id="310c3-173">起動時に、バックグラウンドタスクの `Run` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-173">On startup, the background task's `Run` method will be invoked:</span></span>  

```csharp
public void Run(IBackgroundTaskInstance taskInstance)    
{
    this.backgroundTaskDeferral = taskInstance.GetDeferral();
    // Get a deferral so that the service isn't terminated.
    taskInstance.Canceled += OnTaskCanceled;
    // Associate a cancellation handler with the background task.
    // Retrieve the app service connection and set up a listener for incoming app service requests.
    var details = taskInstance.TriggerDetails as AppServiceTriggerDetails;
    appServiceconnection = details.AppServiceConnection;
    appServiceconnection.RequestReceived += OnRequestReceived;
}
```

<span data-ttu-id="310c3-174">拡張機能によって UWP アプリにメッセージが送信されると、 [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="310c3-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span></span> <span data-ttu-id="310c3-175">この JSON 形式のメッセージは、オブジェクトの最初の KeyValue ペアに stringified され [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span></span> <span data-ttu-id="310c3-176">:</span><span class="sxs-lookup"><span data-stu-id="310c3-176">:</span></span>

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```

<span data-ttu-id="310c3-177">UWP アプリから拡張機能に返信が返されると、が [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) オブジェクトに追加され `ValueSet` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span></span> <span data-ttu-id="310c3-178">プロパティは、 `Key` Microsoft Edge では無視されますが、プロパティには `Value` 有効な JSON 文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="310c3-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>

### <span data-ttu-id="310c3-179">Callback</span><span class="sxs-lookup"><span data-stu-id="310c3-179">Callback</span></span>

<span data-ttu-id="310c3-180">コールバックの場合、Chrome では、コールバック関数を使って、 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) メッセージの送信による非同期応答を処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="310c3-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>

<span data-ttu-id="310c3-181">Microsoft Edge では、オブジェクトのメソッドを使って、 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) アプリが [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) オブジェクトを拡張機能に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="310c3-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span></span>


### <span data-ttu-id="310c3-182">メッセージサイズの制限</span><span class="sxs-lookup"><span data-stu-id="310c3-182">Message size limit</span></span>
<span data-ttu-id="310c3-183">内線番号とアプリの間でやり取りされるメッセージには、Chrome と Microsoft Edge では異なるメッセージサイズの制限があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>

<span data-ttu-id="310c3-184">Chrome には、次のようなメッセージサイズの制限があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-184">Chrome has the following message size limitations:</span></span>
- <span data-ttu-id="310c3-185">ネイティブメッセージングホストからの1つのメッセージ制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="310c3-185">Single message limit from native messaging host: 1 MB</span></span>
- <span data-ttu-id="310c3-186">ネイティブメッセージングホストに送信される1つのメッセージ制限: 4 GB</span><span class="sxs-lookup"><span data-stu-id="310c3-186">Single message limit sent to native messaging host: 4 GB</span></span>

<span data-ttu-id="310c3-187">Microsoft Edge では、 `AppService` (メモリに依存する) メッセージサイズに制限はありませんが、Microsoft edge では、次のようなメッセージサイズの制限を課すことによって、不適切なネイティブアプリから保護されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>
- <span data-ttu-id="310c3-188">UWP アプリから拡張機能への1つのメッセージの制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="310c3-188">Single message limit from UWP app to extension: 1 MB</span></span>
- <span data-ttu-id="310c3-189">拡張子から UWP アプリへの1つのメッセージ制限: 100 MB</span><span class="sxs-lookup"><span data-stu-id="310c3-189">Single message limit from extension to UWP app: 100 MB</span></span>



### <span data-ttu-id="310c3-190">ネイティブメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="310c3-190">Native messaging connections</span></span>

<span data-ttu-id="310c3-191">ネイティブメッセージングには2種類の接続があります。常設と非永続的。</span><span class="sxs-lookup"><span data-stu-id="310c3-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>
<span data-ttu-id="310c3-192">**固定**接続は、ポートが破棄されるまで実行されたままの接続です。</span><span class="sxs-lookup"><span data-stu-id="310c3-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span> <span data-ttu-id="310c3-193">**非永続的**な接続とは、一度に1つのメッセージに対して開かれ、配信後に終了する接続のことです。</span><span class="sxs-lookup"><span data-stu-id="310c3-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>

#### <span data-ttu-id="310c3-194">永続的</span><span class="sxs-lookup"><span data-stu-id="310c3-194">Persistent</span></span>

<span data-ttu-id="310c3-195">Chrome の場合、固定接続は、を使ってメッセージポートを作成することによって行われ [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="310c3-196">ポートが確立されると、Chrome は、ポートが破棄されるまで実行し続けているネイティブメッセージングホストプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="310c3-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>

<span data-ttu-id="310c3-197">Microsoft Edge では、を使ってメッセージポートを作成する `runtime.connectNative` と、Microsoft edge が起動し、 [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) ポートが破棄されるまで実行されたままになります。</span><span class="sxs-lookup"><span data-stu-id="310c3-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span></span> <span data-ttu-id="310c3-198">次のスニペットは、UWP アプリ内から永続的な接続が確立される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="310c3-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span> 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```

#### <span data-ttu-id="310c3-199">非永続的</span><span class="sxs-lookup"><span data-stu-id="310c3-199">Non-persistent</span></span>

<span data-ttu-id="310c3-200">メッセージが Chrome で送信された場合 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 、メッセージポートを作成することなく、chrome は各メッセージに対して新しいネイティブメッセージングホストプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="310c3-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span> <span data-ttu-id="310c3-201">ホストプロセスによって生成された最初のメッセージは、元の要求に対する応答として処理され、他のすべてのメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>

<span data-ttu-id="310c3-202">Microsoft Edge は、すべてのメッセージの応答が受信されるたびに接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="310c3-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span></span> <span data-ttu-id="310c3-203">次のスニペットは、 `AppServiceConnection` 要求が受信され、ととして保存された後に、UWP アプリ内で確立される非永続的な接続を示して [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) います。</span><span class="sxs-lookup"><span data-stu-id="310c3-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span></span>

```csharp
using (var connection = new AppServiceConnection())
{    
    //Set up a new app service connection
    connection.AppServiceName = "com.microsoft.randomnumbergenerator";
    connection.PackageFamilyName = "Microsoft.SDKSamples.AppServicesProvider.CS_8wekyb3d8bbwe";
    AppServiceConnectionStatus status = await connection.OpenAsync();
    AppServiceResponse response = await connection.SendMessageAsync(inputs);
}
```

### <span data-ttu-id="310c3-204">許可</span><span class="sxs-lookup"><span data-stu-id="310c3-204">Permission</span></span>

<span data-ttu-id="310c3-205">ネイティブメッセージングで拡張機能を使用できるようにするには、Chrome と Microsoft Edge の両方について、ファイルにアクセス許可を宣言する必要があり `"nativeMessaging"` `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>


## <span data-ttu-id="310c3-206">アプリ サービス</span><span class="sxs-lookup"><span data-stu-id="310c3-206">App services</span></span>
<span data-ttu-id="310c3-207">このセクションでは、Microsoft Edge のネイティブメッセージングのパフォーマンスとメモリに影響を与えるアプリサービスの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="310c3-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>

### <span data-ttu-id="310c3-208">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="310c3-208">Performance</span></span>

<span data-ttu-id="310c3-209">アプリサービスは、ネイティブメッセージングの目的で呼び出されるフォアグラウンドアプリによって "スポンサー" されます。これは Microsoft Edge です。</span><span class="sxs-lookup"><span data-stu-id="310c3-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span> <span data-ttu-id="310c3-210">これは、Microsoft Edge が実行されている間、アプリサービスを実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="310c3-210">This means that app services can run as long as Microsoft Edge is running.</span></span>

<span data-ttu-id="310c3-211">待機時間については、アプリサービスは、最初の接続後、2つのアプリが直接通信できるようにする名前付きパイプを使います。</span><span class="sxs-lookup"><span data-stu-id="310c3-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span> <span data-ttu-id="310c3-212">この通信方法では、待機時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="310c3-212">This method of communication produces low latency.</span></span> <span data-ttu-id="310c3-213">低速の Cpu を搭載したデバイスでは、アプリサービスをホストするプロセスを起動してから、いくつかの初期待ち時間が発生します (一部のデバイスでは、バックグラウンドタスクの起動に対しては、最大80ms 秒)。</span><span class="sxs-lookup"><span data-stu-id="310c3-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span></span> <span data-ttu-id="310c3-214">起動後、スロー CPU デバイスのパフォーマンスは良好である必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-214">After start-up, performance on slow CPU devices should be good.</span></span> 


### <span data-ttu-id="310c3-215">メモリ</span><span class="sxs-lookup"><span data-stu-id="310c3-215">Memory</span></span>
<span data-ttu-id="310c3-216">アプリサービスに割り当てられたメモリは、Microsoft Edge に割り当てられているクォータから差し引かれます。</span><span class="sxs-lookup"><span data-stu-id="310c3-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span> <span data-ttu-id="310c3-217">これは、Microsoft Edge でアプリサービスが多すぎると、メモリが不足する可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="310c3-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span> <span data-ttu-id="310c3-218">通常のバックグラウンドタスクのメモリキャップは、アプリサービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-218">The usual background task memory caps are enforced on app services.</span></span> <span data-ttu-id="310c3-219">たとえば、512MB デバイスでは、アプリサービスのバックグラウンドタスクが16MB を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="310c3-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span> <span data-ttu-id="310c3-220">この番号は、デバイスのスケールアップに合わせて表示されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-220">This number goes up as the devices scale up.</span></span>


## <span data-ttu-id="310c3-221">ネイティブメッセージングを使用した拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="310c3-221">Creating an extension with native messaging</span></span>

<span data-ttu-id="310c3-222">ネイティブメッセージングをテストするには、拡張機能にパッケージファミリ名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-222">In order to test native messaging, your extension needs a Package Family Name.</span></span> <span data-ttu-id="310c3-223">Microsoft Edge は、これを使ってネイティブメッセージホスト id を判断します。これは、拡張機能をパッケージ化する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="310c3-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span> 


<span data-ttu-id="310c3-224">Visual Studio でネイティブメッセージングで拡張機能を作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="310c3-224">To create your extension with native messaging in Visual Studio:</span></span>

1. <span data-ttu-id="310c3-225">Visual Studio で UWP プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="310c3-225">Create a UWP project in Visual Studio.</span></span>
2. <span data-ttu-id="310c3-226">[ `AppService` UWP アプリにを追加](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)します。</span><span class="sxs-lookup"><span data-stu-id="310c3-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
   - <span data-ttu-id="310c3-227">必要に応じて、この時点でバックグラウンドタスクとしてではなく[ `AppService` 、メインアプリでホストするように構成](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process)することができます。</span><span class="sxs-lookup"><span data-stu-id="310c3-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>
3. <span data-ttu-id="310c3-228">UWP プロジェクトをビルドしてテストします。</span><span class="sxs-lookup"><span data-stu-id="310c3-228">Build and test your UWP project.</span></span>
   - <span data-ttu-id="310c3-229">必要に応じて、 [Desktop Bridge コンポーネント](#adding-a-desktop-bridge-component)を追加できます。</span><span class="sxs-lookup"><span data-stu-id="310c3-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>
4. <span data-ttu-id="310c3-230">UWP コンパニオンアプリと通信するためにネイティブメッセージングを使う Microsoft Edge 拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="310c3-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span> <span data-ttu-id="310c3-231">拡張機能ファイルは、UWP プロジェクトで指定したフォルダーに追加でき `Extension` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span> <span data-ttu-id="310c3-232">サブフォルダーを含む、このフォルダーの下にあるすべてのファイルには、およびを構成するプロパティを設定する必要があり `Build Action=Content` `Copy to Output Directory=Copy Always` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span> <span data-ttu-id="310c3-233">これらの `manifest.json` プロパティでも構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="310c3-233">Make sure `manifest.json` is also configured with these properties.</span></span>
5. <span data-ttu-id="310c3-234">プロジェクト内のファイルを変更して、 `package.manifest.xml` 拡張機能のメタデータを含め、次のように追加して、そのファイルをヘッドレスアプリに変換し `AppListEntry="none"` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>

    ```xml
    <Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10" 
    xmlns:rescap="http://schemas.microsoft.com/appx/manifest/foundation/windows10/restrictedcapabilities" 
    xmlns:mp="http://schemas.microsoft.com/appx/2014/phone/manifest" 
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10" 
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap uap3 mp rescap build" 
    xmlns:build="http://schemas.microsoft.com/developer/appx/2015/build">

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.15063.0" MaxVersionTested="10.0.15063.0" />
    </Dependencies>

       <Application Id="App" Executable="$targetnametoken$.exe" EntryPoint="NativeMessagingHostInProcess.App">
          <uap:VisualElements AppListEntry="none"
            DisplayName="SecureInput"
            Square150x150Logo="Assets\Square150x150Logo.png"
            Square44x44Logo="Assets\Square44x44Logo.png"
            Description="NativeMessagingHostInProcess"
            BackgroundColor="transparent">
          </uap:VisualElements>
          <Extensions>
            <uap3:Extension Category="windows.appExtension">
                <uap3:AppExtension
                    Name="com.microsoft.edge.extension"
                    Id="EdgeExtension"
                    PublicFolder="Extension"
                    DisplayName="ms-resource:DisplayName">
                </uap3:AppExtension>
            </uap3:Extension>
          </Extensions>
    </Application>
    ```

6. <span data-ttu-id="310c3-235">`AppService`ネイティブメッセージング api で、UWP に対して構成された名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="310c3-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>
7. <span data-ttu-id="310c3-236">UWP プロジェクトをビルドして[展開](#deploying)します (オプションの Desktop Bridge コンポーネントを使用します)。</span><span class="sxs-lookup"><span data-stu-id="310c3-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span></span>
8. <span data-ttu-id="310c3-237">ストアへの申請の準備ができたら、ネイティブメッセージングの拡張機能を[パッケージ化](#packaging)する</span><span class="sxs-lookup"><span data-stu-id="310c3-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span></span>

> [!NOTE]
> <span data-ttu-id="310c3-238">完全なネイティブメッセージング拡張機能の例については、「[デモ](#demos)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="310c3-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>


## <span data-ttu-id="310c3-239">Desktop Bridge コンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="310c3-239">Adding a Desktop Bridge component</span></span> 
<span data-ttu-id="310c3-240">パッケージに Desktop Bridge コンポーネントを追加する場合は、Win32 プロジェクトを Visual Studio で作成してビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span></span> <span data-ttu-id="310c3-241">Win32 アプリを UWP に変換する方法について詳しくは、「 [Desktop Bridge を使った Windows 10 へのアプリの移植](/windows/uwp/porting/desktop-to-uwp-root)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="310c3-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span> <span data-ttu-id="310c3-242">Visual Studio でビルドされた後、次の手順に従って Win32 実行可能ファイルをパッケージに追加できます。</span><span class="sxs-lookup"><span data-stu-id="310c3-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>

1. <span data-ttu-id="310c3-243">UWP プロジェクトと同じソリューションに Win32 プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="310c3-243">Add the Win32 project to the same solution as the UWP project.</span></span> 

2. <span data-ttu-id="310c3-244">Win32 プロジェクトを UWP プロジェクトの依存プロジェクトとして設定します。</span><span class="sxs-lookup"><span data-stu-id="310c3-244">Set the Win32 project as a dependent project for the UWP project:</span></span>

    ![プロジェクトの依存関係を設定する](./../media/project-dependencies.PNG)

3. <span data-ttu-id="310c3-246">`Win32`UWP プロジェクト内にフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="310c3-246">Create a `Win32` folder within the UWP project.</span></span> <span data-ttu-id="310c3-247">プロジェクトに必要なバイナリを `Win32` このフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="310c3-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span> <span data-ttu-id="310c3-248">などのすべてのバイナリのプロパティを構成 `Build Action=Content` し `Copy to Output Directory=Copy Always` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>

    ![win32 と UWP アプリのファイルが含まれるフォルダー](./../media/desktop-bridge.png)

4. <span data-ttu-id="310c3-250">UWP プロジェクトファイルを変更して、プロジェクトに必要なすべてのバイナリを `Win32` このフォルダーにポストビルドイベントコマンドを使用してコピーします。</span><span class="sxs-lookup"><span data-stu-id="310c3-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span> <span data-ttu-id="310c3-251">これにより、ソリューションが再構築されるたびに、更新されたバイナリがフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="310c3-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>

    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```


5. <span data-ttu-id="310c3-252">要素 `package.manifest.xml` に要素を追加して変更し `<desktop:Extension>` `<Extensions>` ます。</span><span class="sxs-lookup"><span data-stu-id="310c3-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>

    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```

## <span data-ttu-id="310c3-253">展開</span><span class="sxs-lookup"><span data-stu-id="310c3-253">Deploying</span></span>
<span data-ttu-id="310c3-254">前に説明したように UWP プロジェクト (および必要に応じて Win32 プロジェクト) を構成したら、Visual Studio を使ってソリューションを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="310c3-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>

![inprocess プロジェクトを構築する](../media/native-message-uwp-debug.PNG)

<span data-ttu-id="310c3-256">ソリューションが正しく展開されると、Microsoft Edge に拡張機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="310c3-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>

![Microsoft Edge に表示される拡張機能](../media/secureextension.png)

## <span data-ttu-id="310c3-258">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="310c3-258">Packaging</span></span>

> [!NOTE]
> <span data-ttu-id="310c3-259">Microsoft Store への Microsoft Edge 拡張機能の送信は現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="310c3-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="310c3-260">Microsoft Store の一部として要求が送信された場合は、skype[に](https://aka.ms/extension-request)連絡して、将来の更新についてご検討ください。</span><span class="sxs-lookup"><span data-stu-id="310c3-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>


<span data-ttu-id="310c3-261">組み込みの Visual Studio 機能を使用して、Windows デベロッパーセンターに申請するためのストアパッケージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="310c3-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>


![ストアパッケージを作成する](../media/create-store-package.PNG)

## <span data-ttu-id="310c3-263">デバッグ</span><span class="sxs-lookup"><span data-stu-id="310c3-263">Debugging</span></span>
<span data-ttu-id="310c3-264">デバッグの手順は、テストするコンポーネントによって異なります。</span><span class="sxs-lookup"><span data-stu-id="310c3-264">The instructions for debugging vary depending on which component you want to test out:</span></span>

### <span data-ttu-id="310c3-265">拡張機能のデバッグ</span><span class="sxs-lookup"><span data-stu-id="310c3-265">Debugging the extension</span></span>
<span data-ttu-id="310c3-266">ソリューションが展開されると、Microsoft Edge に拡張機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="310c3-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span> <span data-ttu-id="310c3-267">拡張機能のデバッグ方法について詳しくは、「[デバッグ](./debugging-extensions.md)ガイド」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="310c3-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>


### <span data-ttu-id="310c3-268">UWP アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="310c3-268">Debugging the UWP app</span></span>
<span data-ttu-id="310c3-269">UWP アプリは、拡張機能が[ネイティブメッセージング api](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)を使って接続しようとしたときに起動します。</span><span class="sxs-lookup"><span data-stu-id="310c3-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="310c3-270">プロセスが開始された場合にのみ、UWP アプリをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="310c3-270">You'll need to debug the UWP app only once the process starts.</span></span> <span data-ttu-id="310c3-271">この設定は、プロジェクトのプロパティページで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="310c3-271">This can be configured via the project's Property page:</span></span>

1.  <span data-ttu-id="310c3-272">Visual Studio で、UWP アプリプロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="310c3-272">In Visual Studio, right click your UWP app project</span></span>
2.  <span data-ttu-id="310c3-273">プロパティを選ぶ</span><span class="sxs-lookup"><span data-stu-id="310c3-273">Select Properties</span></span>
3.  <span data-ttu-id="310c3-274">[起動しないが、開始時にコードをデバッグする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="310c3-274">Check "Do not launch, but debug my code when it starts"</span></span>

    ![[起動しない] ボックスを選択する](../media/native-message-do-not-launch.png)

<span data-ttu-id="310c3-276">Visual Studio で、デバッグするコードにブレークポイントを設定して、F5 キーを押してデバッガーを起動できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="310c3-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span> <span data-ttu-id="310c3-277">UWP アプリに接続するために拡張機能を操作すると、Visual Studio が自動的にプロセスにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="310c3-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>


### <span data-ttu-id="310c3-278">Desktop Bridge のデバッグ</span><span class="sxs-lookup"><span data-stu-id="310c3-278">Debugging the Desktop Bridge</span></span>
<span data-ttu-id="310c3-279">Desktop Bridge (変換された Win32 アプリ)[をデバッグするに](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug)はさまざまな方法がありますが、このシナリオでは、PLMDebug オプションのみに該当します。</span><span class="sxs-lookup"><span data-stu-id="310c3-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span></span> <span data-ttu-id="310c3-280">また、スタートアップ関数にデバッグコードを追加して、特定の時間の待機を実行し、Visual Studio をプロセスにアタッチすることもできます。</span><span class="sxs-lookup"><span data-stu-id="310c3-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>
