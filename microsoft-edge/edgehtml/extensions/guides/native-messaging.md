---
description: ネイティブ メッセージングを使用して拡張機能をコンパニオン UWP アプリと通信する方法について説明します。
title: ネイティブ メッセージング |拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, ネイティブ, メッセージング, uwp
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9a306055b8f86b92aa5c3e7cd6de44f2386307d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399359"
---
# <a name="native-messaging-in-microsoft-edge"></a><span data-ttu-id="2a134-104">Microsoft Edge でのネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="2a134-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <a name="native-messaging-architecture-overview"></a><span data-ttu-id="2a134-105">ネイティブ メッセージング アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="2a134-105">Native messaging architecture overview</span></span>  

<span data-ttu-id="2a134-106">Windows 10 Creators Update を使用すると、Microsoft Edge 拡張機能はネイティブ メッセージングを使用して、コンパニオンユニバーサル Windows プラットフォーム \(UWP\) アプリと通信できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform \(UWP\) app.</span></span>  <span data-ttu-id="2a134-107">高レベルでは、Microsoft Edge 拡張機能は、Chrome 拡張機能や Firefox 拡張機能と同じ API をネイティブ メッセージングに使用します。</span><span class="sxs-lookup"><span data-stu-id="2a134-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span>  <span data-ttu-id="2a134-108">ただし、ネイティブ メッセージング ホストはユニバーサル Windows プラットフォームを使用して実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>  

> [!NOTE]
> <span data-ttu-id="2a134-109">\(AppService\経由で UWP アプリに接続する) で説明するメソッドは、Microsoft Edge 拡張機能とネイティブ コンポーネント間の通信を有効にする唯一のサポートされるメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="2a134-109">The method outlined below \(connecting to a UWP app via AppService\) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span>  <span data-ttu-id="2a134-110">従来の[](#adding-a-desktop-bridge-component)Win32 コンポーネントとの通信を有効にする方法の詳細については、このガイドの「デスクトップ ブリッジ コンポーネントの追加」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a134-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span>  

<span data-ttu-id="2a134-111">Microsoft Edge のネイティブ メッセージング アーキテクチャは、既存の API を基になるプロセス間通信 [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) \(IPC\) インフラストラクチャとして活用します。</span><span class="sxs-lookup"><span data-stu-id="2a134-111">The native messaging architecture in Microsoft Edge leverages the existing [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) API as the underlying inter-process communication \(IPC\) infrastructure.</span></span>  <span data-ttu-id="2a134-112">UWP アプリは API を `AppService` 使用して相互に通信します。</span><span class="sxs-lookup"><span data-stu-id="2a134-112">UWP apps use the `AppService` API to communicate with one another.</span></span>  <span data-ttu-id="2a134-113">これにより、Microsoft Edge 拡張機能は UWP アプリと通信できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-113">Because of this, Microsoft Edge extensions are now able to communicate with UWP apps.</span></span>  

![ネイティブ メッセージング アーキテクチャ](../media/native-messaging-architecture.png)  

### <a name="when-and-when-not-to-use-native-messaging"></a><span data-ttu-id="2a134-115">ネイティブ メッセージングを使用しない場合と使用しない場合</span><span class="sxs-lookup"><span data-stu-id="2a134-115">When and when not to use native messaging</span></span>  

<span data-ttu-id="2a134-116">ネイティブ メッセージングは、拡張機能に新しいレイヤーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2a134-116">Native messaging adds a whole new layer to your extension.</span></span>  <span data-ttu-id="2a134-117">拡張機能に UWP コンパニオン アプリを実装すると、次の可能性が利用できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>  

*   <span data-ttu-id="2a134-118">コンパニオン UWP アプリとデータ \(資格情報\など) を同期します。</span><span class="sxs-lookup"><span data-stu-id="2a134-118">Synchronize data \(for example credentials\) with a companion UWP app.</span></span>  
*   <span data-ttu-id="2a134-119">Web API では使用できない、より強力な暗号化/復号化アルゴリズムを実装します。</span><span class="sxs-lookup"><span data-stu-id="2a134-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>  
*   <span data-ttu-id="2a134-120">ハードウェアや USB デバイスなど、Web API を介してアクセスできないリソースにアクセスする</span><span class="sxs-lookup"><span data-stu-id="2a134-120">Access resources that are not accessible through web APIs, for example hardware or USB devices</span></span>  

<span data-ttu-id="2a134-121">セキュリティまたはポリシーの制限のためにネイティブ メッセージングを使用しない場合は、次に示すいくつかの例があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-121">There are a few instances where native messaging should not be used due to security or policy restrictions:</span></span>  

*   <span data-ttu-id="2a134-122">既定のブラウザーまたは検索プロバイダーの変更など、Microsoft Edge または Windows のユーザー設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="2a134-122">Modifying user settings in either Microsoft Edge or Windows, for example changing the default browser or search provider.</span></span>  
*   <span data-ttu-id="2a134-123">アプリと拡張機能の両方に対する Microsoft Store ポリシーに違反するアクション。</span><span class="sxs-lookup"><span data-stu-id="2a134-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>  
*   <span data-ttu-id="2a134-124">ネイティブ メッセージ ホスト経由でリモート エンドポイントにデータを転送する。</span><span class="sxs-lookup"><span data-stu-id="2a134-124">Transferring data to remote endpoint via native message host.</span></span>  
*   <span data-ttu-id="2a134-125">拡張機能の動作を変更するコンテンツを他のアプリがダウンロードすることを許可する。</span><span class="sxs-lookup"><span data-stu-id="2a134-125">Allowing other apps to download content that changes extension behavior.</span></span>  

## <a name="demos"></a><span data-ttu-id="2a134-126">デモ</span><span class="sxs-lookup"><span data-stu-id="2a134-126">Demos</span></span>  

<span data-ttu-id="2a134-127">コンパニオン UWP アプリとデスクトップ ブリッジの両方を持つ Microsoft Edge ネイティブ メッセージング拡張機能の外観を確認するには、GitHub の [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) と [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a134-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>  

### <a name="how-it-works"></a><span data-ttu-id="2a134-128">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="2a134-128">How it works</span></span>  

<span data-ttu-id="2a134-129">サンプルの Microsoft Edge 拡張コンポーネントは、コンテンツ スクリプトを使用して、ユーザーが暗号化する必要がある情報を入力する際に検出します。</span><span class="sxs-lookup"><span data-stu-id="2a134-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span>  <span data-ttu-id="2a134-130">拡張機能は、ネイティブ メッセージングを介してデスクトップ ブリッジ コンポーネントにこれを通信します。</span><span class="sxs-lookup"><span data-stu-id="2a134-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span>  <span data-ttu-id="2a134-131">ユーザーがデータを送信する準備ができたら、拡張機能は暗号化された値を Web サイトに返します。</span><span class="sxs-lookup"><span data-stu-id="2a134-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>  

> [!NOTE]
> <span data-ttu-id="2a134-132">このサンプルは、カスタム イベントを使用して拡張機能のコンテンツ スクリプトと通信する Web ページでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="2a134-132">This sample will only work on a webpage that uses custom events to communicate with the content script of the extension.</span></span>  <span data-ttu-id="2a134-133">サンプル フォルダーには、拡張子をテスト [する .html](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a134-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>  

<span data-ttu-id="2a134-134">この例では、UWP アプリを使用してデスクトップ ブリッジから Microsoft Edge に応答を渡し、コールバックを介して Microsoft Edge 拡張機能に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span>  <span data-ttu-id="2a134-135">この例では、メイン アプリでネイティブ メッセージング ホストを実行しますが、バックグラウンド タスクとして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a134-135">While this example has the native messaging host run in the main app, it is also able to run as a background task.</span></span>  <span data-ttu-id="2a134-136">2 つを切り替えるには、内線の背景スクリプトを編集し、文字列をに変更する必要 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` があります `"NativeMessagingHostOutOfProcess"` 。</span><span class="sxs-lookup"><span data-stu-id="2a134-136">Switching between the two requires editing the background script of the extension, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>  

## <a name="chrome-vs-microsoft-edge-implementation"></a><span data-ttu-id="2a134-137">Chrome と Microsoft Edge の実装</span><span class="sxs-lookup"><span data-stu-id="2a134-137">Chrome vs Microsoft Edge implementation</span></span>  

<span data-ttu-id="2a134-138">Chrome では、拡張機能にメッセージを渡す API を使用してアプリと通信しますが、Microsoft Edge は API を利用して Microsoft Edge 拡張機能と UWP アプリの通信を可能 [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) にしています。</span><span class="sxs-lookup"><span data-stu-id="2a134-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>  

<span data-ttu-id="2a134-139">このセクションでは、Chrome と Microsoft Edge がネイティブ メッセージングの実装を処理する方法の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2a134-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>  

### <a name="registration-and-host-manifest"></a><span data-ttu-id="2a134-140">登録マニフェストとホスト マニフェスト</span><span class="sxs-lookup"><span data-stu-id="2a134-140">Registration and host manifest</span></span>  

<span data-ttu-id="2a134-141">拡張機能でアプリをネイティブ メッセージング ホストとして認識するには、アプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>  

<span data-ttu-id="2a134-142">[Chrome ネイティブ メッセージング ホスト](https://developer.chrome.com/extensions/nativeMessaging)の登録では、アプリは、ネイティブ メッセージング ホスト構成を定義する Windows ファイル システムの任意の場所にマニフェスト ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>  

<span data-ttu-id="2a134-143">次の JSON は、構成ファイルの設定の例です。</span><span class="sxs-lookup"><span data-stu-id="2a134-143">The following JSON is an example of settings for the config file:</span></span>  

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

<span data-ttu-id="2a134-144">このファイルをインストールするには、アプリで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-144">To install this file, the app would need to:</span></span>  

1.  <span data-ttu-id="2a134-145">ホスト構成を定義するレジストリの定義済みの場所にマニフェスト ファイルを登録します。</span><span class="sxs-lookup"><span data-stu-id="2a134-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>  
    *   `HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`  
        
        <span data-ttu-id="2a134-146">or</span><span class="sxs-lookup"><span data-stu-id="2a134-146">or</span></span>  
    *   `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`  
        
1.  <span data-ttu-id="2a134-147">マニフェスト ファイルの完全パスに、そのキーの既定値を設定します。たとえば、</span><span class="sxs-lookup"><span data-stu-id="2a134-147">Set the default value of that key to the full path to the manifest file, for example</span></span> `[HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"`  

<span data-ttu-id="2a134-148">Microsoft Edge の場合、\(ネイティブ メッセージング ホスト\) を登録するには、拡張子と同じパッケージに UWP コンパニオン アプリを含め、プロジェクトのファイルに [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) [AppService](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)拡張機能を指定する必要があります。 `Package.appxmanifest`</span><span class="sxs-lookup"><span data-stu-id="2a134-148">For Microsoft Edge, in order to register an [`AppService`](/uwp/api/Windows.ApplicationModel.AppService?view=winrt-19041&preserve-view=true) \(native messaging host\) you must include the UWP companion app in the same package as your extension and specify the [AppService extension](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in the `Package.appxmanifest` file of your project.</span></span>  <span data-ttu-id="2a134-149">属性 `EntryPoint` と `Name` 属性は、ユーザーが構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-149">The `EntryPoint` and `Name` attributes may be configured by you:</span></span>  

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

<span data-ttu-id="2a134-150">また、サービスへの接続を許可する拡張機能を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-150">You also need to set which extensions are allowed to connect to the service.</span></span>  <span data-ttu-id="2a134-151">Microsoft Edge には AppxManifest には同等のマニフェスト プロパティが存在しないので、UWP アプリによって実行時にこれを決定して適用する `"allowed_origins"` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-151">Because Microsoft Edge does not have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span>  <span data-ttu-id="2a134-152">Microsoft Edge は拡張機能の代わりに接続を確立しますので、アプリは呼び出し元のパッケージ ファミリ名を検索して、呼び出し元を制御または認証するために拡張機能が Microsoft Edge によって接続されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2a134-152">Since Microsoft Edge establishes the connection on behalf of the extension, the app looks up the Package Family Name of the caller to determine if extension is being connected by Microsoft Edge to control or authenticate the caller.</span></span>  <span data-ttu-id="2a134-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a134-153">For example</span></span>   

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

### <a name="message-sending"></a><span data-ttu-id="2a134-154">メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="2a134-154">Message sending</span></span>  

<span data-ttu-id="2a134-155">アプリと拡張機能が相互に通信するには、メッセージの送信と送信が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a134-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>  

<span data-ttu-id="2a134-156">Chrome 拡張機能は、API を使用してメッセージを開始し、永続的でないチャネルを使用してネイティブ ホスト [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) にメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="2a134-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span>  

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

<span data-ttu-id="2a134-157">最初のパラメーターはネイティブ ホストの名前で、Chrome はマニフェストのレジストリで検索します。</span><span class="sxs-lookup"><span data-stu-id="2a134-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span>  <span data-ttu-id="2a134-158">マニフェストは、Chrome がサンドボックスで起動する .exe を指定し、メッセージは std i/o を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span>  
<span data-ttu-id="2a134-159">拡張機能では、API を使用して永続的なチャネルも確立します。これはネイティブ ホストの名前を唯一の `runtime.connectNative` パラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2a134-159">Extensions also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span>  

<span data-ttu-id="2a134-160">Microsoft Edge では、Chrome のネイティブ メッセージング API と同じ構成を使用して、Microsoft Edge 拡張機能が接続先のアプリ サービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-160">Microsoft Edge uses the same construct as the native messaging API in Chrome to allow Microsoft Edge extensions to specify which app service to connect to.</span></span>  <span data-ttu-id="2a134-161">最初のパラメーターは `runtime.sendNativeMessage` 、アプリ サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a134-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span>  <span data-ttu-id="2a134-162">[登録と [ホスト マニフェスト] セクションで](#registration-and-host-manifest) 、次の値を指定します `"com.microsoft.inventory"` 。</span><span class="sxs-lookup"><span data-stu-id="2a134-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span>  <span data-ttu-id="2a134-163">Microsoft Edge 拡張機能プラットフォームは、ネイティブ メッセージング ホストを拡張機能と同じ AppX にパッケージ化された UWP アプリに制限します。</span><span class="sxs-lookup"><span data-stu-id="2a134-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span>  <span data-ttu-id="2a134-164">これにより、マニフェスト エントリを改ざんして Microsoft Edge を別のパッケージ ファミリ名に接続しようとする悪意のある攻撃に関連するセキュリティ リスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span>  

<span data-ttu-id="2a134-165">つまり、Microsoft Edge は、API で指定された名前に加えて、拡張機能と同じパッケージ ファミリ名を使用して、アプリ サービスのプロバイダーを一意に `AppService` 識別します。</span><span class="sxs-lookup"><span data-stu-id="2a134-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="2a134-166">これは、Microsoft Edge Extension ファイルによって簡単[に変換Toolkit。](./porting-chrome-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="2a134-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span>  <span data-ttu-id="2a134-167">アクセス許可を指定する拡張機能には、このコンポーネントの手動変換が必要として `"nativeMessaging"` フラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>  

### <a name="communication-protocol"></a><span data-ttu-id="2a134-168">通信プロトコル</span><span class="sxs-lookup"><span data-stu-id="2a134-168">Communication protocol</span></span>  

<span data-ttu-id="2a134-169">ネイティブ メッセージングの通信プロトコルは、送信前にメッセージの書式設定方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="2a134-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>  

<span data-ttu-id="2a134-170">Chrome は、各ネイティブ メッセージング ホストを個別のプロセスで開始し、標準の入力と標準出力を使用してそのホストと通信します。</span><span class="sxs-lookup"><span data-stu-id="2a134-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span>  <span data-ttu-id="2a134-171">両方向にメッセージを送信するには、同じ形式が使用されます。各メッセージは JSON を使用してシリアル化され、UTF-8 エンコードされ、ネイティブ バイト順で 32 ビット のメッセージ長が先行します。</span><span class="sxs-lookup"><span data-stu-id="2a134-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>  

<span data-ttu-id="2a134-172">Microsoft Edge では、アプリ サービスを実装するバックグラウンド タスク/メイン アプリがプラットフォームによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span>  <span data-ttu-id="2a134-173">起動時に、 `Run` バックグラウンド タスクのメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-173">On startup, the `Run` method of the background task is invoked:</span></span>  

```csharp
public void Run(IBackgroundTaskInstance taskInstance)    
{
    this.backgroundTaskDeferral = taskInstance.GetDeferral();
    // Get a deferral so that the service is not stopped and ended.
    taskInstance.Canceled += OnTaskCanceled;
    // Associate a cancellation handler with the background task.
    // Retrieve the app service connection and set up a listener for incoming app service requests.
    var details = taskInstance.TriggerDetails as AppServiceTriggerDetails;
    appServiceconnection = details.AppServiceConnection;
    appServiceconnection.RequestReceived += OnRequestReceived;
}
```  

<span data-ttu-id="2a134-174">拡張機能が UWP アプリにメッセージを送信すると、 [`onRequestReceived`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="2a134-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) event will be raised.</span></span>  <span data-ttu-id="2a134-175">この JSON 形式のメッセージは、オブジェクトの最初の KeyValue ペアに文字列化 [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) object.</span></span>  <span data-ttu-id="2a134-176">:</span><span class="sxs-lookup"><span data-stu-id="2a134-176">:</span></span>  

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

<span data-ttu-id="2a134-177">UWP アプリが拡張機能に応答を送信すると、オブジェクトに a [`KeyValuePair`](/dotnet/api/system.collections.generic.keyvaluepair-2?view=netcore-3.1&preserve-view=true) が追加 `ValueSet` されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](/dotnet/api/system.collections.generic.keyvaluepair-2?view=netcore-3.1&preserve-view=true) will be added to the `ValueSet` object.</span></span>  <span data-ttu-id="2a134-178">プロパティ `Key` は Microsoft Edge では無視されますが、プロパティ `Value` には有効な JSON 文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a134-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>  

### <a name="callback"></a><span data-ttu-id="2a134-179">コールバック</span><span class="sxs-lookup"><span data-stu-id="2a134-179">Callback</span></span>  

<span data-ttu-id="2a134-180">コールバックの場合、Chrome はコールバック関数がメッセージの送信から非同期応答を処理 [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2a134-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>  

<span data-ttu-id="2a134-181">Microsoft Edge では、 [`SendResponseAsync`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) オブジェクトのメソッド [`AppServiceRequest`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) を使用して、アプリがオブジェクトを拡張機能 [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) に戻します。</span><span class="sxs-lookup"><span data-stu-id="2a134-181">Microsoft Edge uses the [`SendResponseAsync`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) method  of the [`AppServiceRequest`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceRequest?view=winrt-19041&preserve-view=true) object to let the app send a [`ValueSet`](/uwp/api/Windows.Foundation.Collections.ValueSet?view=winrt-19041&preserve-view=true) object back to the extension.</span></span>  

### <a name="message-size-limit"></a><span data-ttu-id="2a134-182">メッセージ サイズの制限</span><span class="sxs-lookup"><span data-stu-id="2a134-182">Message size limit</span></span>  

<span data-ttu-id="2a134-183">拡張機能とアプリの間で送信されるメッセージには、Chrome と Microsoft Edge のメッセージ サイズの制限が異なります。</span><span class="sxs-lookup"><span data-stu-id="2a134-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>  

<span data-ttu-id="2a134-184">Chrome には、次のメッセージ サイズの制限があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-184">Chrome has the following message size limitations:</span></span>  

*   <span data-ttu-id="2a134-185">ネイティブ メッセージング ホストからの 1 つのメッセージ制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="2a134-185">Single message limit from native messaging host:  1 MB</span></span>  
*   <span data-ttu-id="2a134-186">ネイティブ メッセージング ホストに送信される 1 つのメッセージ制限: 4 GB</span><span class="sxs-lookup"><span data-stu-id="2a134-186">Single message limit sent to native messaging host:  4 GB</span></span>  

<span data-ttu-id="2a134-187">Microsoft Edge の場合、メッセージ サイズ \(memory\に依存) は制限されませんが、Microsoft Edge は、次のメッセージ サイズの制限を課して、ネイティブ アプリの動作を誤って行うのを禁止 `AppService` します。</span><span class="sxs-lookup"><span data-stu-id="2a134-187">For Microsoft Edge, while `AppService` has no limit on message size \(dependent on memory\), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>  

*   <span data-ttu-id="2a134-188">UWP アプリから拡張機能への 1 つのメッセージ制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="2a134-188">Single message limit from UWP app to extension: 1 MB</span></span>  
*   <span data-ttu-id="2a134-189">拡張機能から UWP アプリへの 1 つのメッセージ制限: 100 MB</span><span class="sxs-lookup"><span data-stu-id="2a134-189">Single message limit from extension to UWP app: 100 MB</span></span>  

### <a name="native-messaging-connections"></a><span data-ttu-id="2a134-190">ネイティブ メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="2a134-190">Native messaging connections</span></span>  

<span data-ttu-id="2a134-191">ネイティブ メッセージングには 2 種類の接続があります。永続的および非永続的。</span><span class="sxs-lookup"><span data-stu-id="2a134-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>  
<span data-ttu-id="2a134-192">永続的 **な** 接続とは、ポートが破棄されるまで実行され続けた接続です。</span><span class="sxs-lookup"><span data-stu-id="2a134-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span>  <span data-ttu-id="2a134-193">非 **永続的な接続は** 、一度に 1 つのメッセージに対して開き、配信後に閉じる接続です。</span><span class="sxs-lookup"><span data-stu-id="2a134-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>  

#### <a name="persistent"></a><span data-ttu-id="2a134-194">永続的</span><span class="sxs-lookup"><span data-stu-id="2a134-194">Persistent</span></span>  

<span data-ttu-id="2a134-195">Chrome の場合、永続的な接続は、 を使用してメッセージング ポートを作成することで行います [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。</span><span class="sxs-lookup"><span data-stu-id="2a134-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span>  <span data-ttu-id="2a134-196">ポートが作成されると、Chrome はネイティブ メッセージング ホスト プロセスを開始し、破棄されたポートまで実行を続ける。</span><span class="sxs-lookup"><span data-stu-id="2a134-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>  

<span data-ttu-id="2a134-197">Microsoft Edge の場合、メッセージング ポートを使用して作成すると、Microsoft Edge はポートを起動し、ポートが破棄されるまで実行 `runtime.connectNative` [`AppServiceConnection`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) を続ける。</span><span class="sxs-lookup"><span data-stu-id="2a134-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceConnection?view=winrt-19041&preserve-view=true) and keeps it running until the port is destroyed.</span></span>  <span data-ttu-id="2a134-198">次のスニペットは、UWP アプリ内から永続的な接続が確立される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a134-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span>  

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```  

#### <a name="non-persistent"></a><span data-ttu-id="2a134-199">非永続的</span><span class="sxs-lookup"><span data-stu-id="2a134-199">Non-persistent</span></span>  

<span data-ttu-id="2a134-200">Chrome でメッセージング ポートを作成せずにメッセージを送信すると、メッセージごとに新しいネイティブ メッセージング ホスト プロセス [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span>  <span data-ttu-id="2a134-201">ホスト プロセスによって生成された最初のメッセージは、元の要求に対する応答として処理され、無視された後の他のすべてのメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>  

<span data-ttu-id="2a134-202">Microsoft Edge は、各メッセージに対する応答が受信された後、接続を停止および終了します。</span><span class="sxs-lookup"><span data-stu-id="2a134-202">Microsoft Edge stops and ends the connection after every response to each message has been received.</span></span>  <span data-ttu-id="2a134-203">次のスニペットは、要求を受信して保存した後、UWP アプリ内で終了する非永続的な接続を `AppServiceConnection` 示しています [`AppServiceResponse`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceResponse?view=winrt-19041&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="2a134-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](/uwp/api/Windows.ApplicationModel.AppService.AppServiceResponse?view=winrt-19041&preserve-view=true).</span></span>  

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

### <a name="permission"></a><span data-ttu-id="2a134-204">許可</span><span class="sxs-lookup"><span data-stu-id="2a134-204">Permission</span></span>  

<span data-ttu-id="2a134-205">拡張機能でネイティブ メッセージングの使用を有効にするには、Chrome と Microsoft Edge の両方で、ファイルでアクセス許可 `"nativeMessaging"` を宣言する必要 `manifest.json` があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you must declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>  

## <a name="app-services"></a><span data-ttu-id="2a134-206">アプリ サービス</span><span class="sxs-lookup"><span data-stu-id="2a134-206">App services</span></span>  

<span data-ttu-id="2a134-207">このセクションでは、アプリ サービスが Microsoft Edge ネイティブ メッセージングのパフォーマンスとメモリに与える影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a134-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>  

### <a name="performance"></a><span data-ttu-id="2a134-208">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="2a134-208">Performance</span></span>  

<span data-ttu-id="2a134-209">アプリ サービスは、ネイティブ メッセージングの目的で Microsoft Edge を呼び出すフォアグラウンド アプリによって "スポンサー" されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span>  <span data-ttu-id="2a134-210">つまり、Microsoft Edge が実行されている限り、アプリ サービスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-210">This means that app services can run as long as Microsoft Edge is running.</span></span>  

<span data-ttu-id="2a134-211">待機時間に関して、アプリ サービスは名前付きパイプを使用し、最初の接続後に 2 つのアプリが直接通信できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span>  <span data-ttu-id="2a134-212">この通信方法では、低遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="2a134-212">This method of communication produces low latency.</span></span>  <span data-ttu-id="2a134-213">CPU が遅いデバイスでは、アプリ サービスをホストするプロセスを開始した後に初期待機時間が発生します \(~80ms)、一部のデバイスでバックグラウンド タスクを起動します\)。</span><span class="sxs-lookup"><span data-stu-id="2a134-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service \(~80ms to startup the background task on some devices\).</span></span>  <span data-ttu-id="2a134-214">起動後、低速の CPU デバイスのパフォーマンスは良好です。</span><span class="sxs-lookup"><span data-stu-id="2a134-214">After start-up, performance on slow CPU devices should be good.</span></span>  

### <a name="memory"></a><span data-ttu-id="2a134-215">メモリ</span><span class="sxs-lookup"><span data-stu-id="2a134-215">Memory</span></span>  

<span data-ttu-id="2a134-216">アプリ サービスに割り当てられたメモリは、Microsoft Edge に割り当てられたクォータから取り出されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span>  <span data-ttu-id="2a134-217">つまり、Microsoft Edge で開始されるアプリ サービスが多すぎると、メモリが使い切れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span>  <span data-ttu-id="2a134-218">通常のバックグラウンド タスクのメモリ上限は、アプリ サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-218">The usual background task memory caps are enforced on app services.</span></span>  <span data-ttu-id="2a134-219">たとえば、512 MB デバイスでは、アプリ サービスのバックグラウンド タスクを 16 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="2a134-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span>  <span data-ttu-id="2a134-220">この番号は、デバイスのスケール アップに合って上がっています。</span><span class="sxs-lookup"><span data-stu-id="2a134-220">This number goes up as the devices scale up.</span></span>  

## <a name="creating-an-extension-with-native-messaging"></a><span data-ttu-id="2a134-221">ネイティブ メッセージングを使用した拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="2a134-221">Creating an extension with native messaging</span></span>  

<span data-ttu-id="2a134-222">ネイティブ メッセージングをテストするには、拡張機能にパッケージ ファミリ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a134-222">In order to test native messaging, your extension needs a Package Family Name.</span></span>  <span data-ttu-id="2a134-223">Microsoft Edge では、これを使用してネイティブ メッセージ ホスト ID を決定します。つまり、拡張機能をパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span>  

<span data-ttu-id="2a134-224">ネイティブ メッセージングを使用して拡張機能を作成するには、次Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2a134-224">To create your extension with native messaging in Visual Studio:</span></span>  

1.  <span data-ttu-id="2a134-225">UWP プロジェクトを作成するには、Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2a134-225">Create a UWP project in Visual Studio.</span></span>  
1.  <span data-ttu-id="2a134-226">[ `AppService` UWP アプリに追加します](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。</span><span class="sxs-lookup"><span data-stu-id="2a134-226">[Add `AppService` to your UWP app](/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>  
    *   <span data-ttu-id="2a134-227">必要に応じて [、 `AppService` この](/windows/uwp/launch-resume/convert-app-service-in-process) 時点でバックグラウンド タスクとしてではなく、メイン アプリでホストされる構成を行います。</span><span class="sxs-lookup"><span data-stu-id="2a134-227">You can optionally [configure `AppService` to be hosted in the main app](/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>  
1.  <span data-ttu-id="2a134-228">UWP プロジェクトをビルドしてテストします。</span><span class="sxs-lookup"><span data-stu-id="2a134-228">Build and test your UWP project.</span></span>  
    *   <span data-ttu-id="2a134-229">必要に応じて、デスクトップ ブリッジ [コンポーネントを追加できます](#adding-a-desktop-bridge-component)。</span><span class="sxs-lookup"><span data-stu-id="2a134-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>  
1.  <span data-ttu-id="2a134-230">ネイティブ メッセージングを使用して UWP コンパニオン アプリと通信する Microsoft Edge 拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="2a134-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span>  <span data-ttu-id="2a134-231">拡張ファイルは、UWP プロジェクトの名前 `Extension` のフォルダーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span>  <span data-ttu-id="2a134-232">このフォルダーの下のすべてのファイル (サブフォルダーを含む) は、そのプロパティを構成する必要 `Build Action=Content` があります `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="2a134-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>  <span data-ttu-id="2a134-233">これらのプロパティ `manifest.json` も構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a134-233">Make sure `manifest.json` is also configured with these properties.</span></span>  
1.  <span data-ttu-id="2a134-234">プロジェクト内のファイルを変更して拡張メタデータを含め、次の項目を追加してヘッドレス `package.manifest.xml` アプリに変換します `AppListEntry="none"` 。</span><span class="sxs-lookup"><span data-stu-id="2a134-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>  
    
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
    
1.  <span data-ttu-id="2a134-235">ネイティブ メッセージング `AppService` API で UWP 用に構成された名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a134-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>  
1.  <span data-ttu-id="2a134-236">UWP [プロジェクト](#deploying) \(オプションのデスクトップ ブリッジ コンポーネント\を使用して) をビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="2a134-236">Build and [deploy](#deploying) the UWP project \(with the optional Desktop Bridge component\).</span></span>  
1.  <span data-ttu-id="2a134-237">[ストア](#packaging) 申請の準備ができたら、ネイティブ メッセージング拡張機能をパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="2a134-237">[Package](#packaging) your native messaging extension once it is ready for Store submission</span></span>  
    
> [!NOTE]
> <span data-ttu-id="2a134-238">完全な [ネイティブ メッセージング拡張機能](#demos) の例については、「Demos」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a134-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>  

## <a name="adding-a-desktop-bridge-component"></a><span data-ttu-id="2a134-239">デスクトップ ブリッジ コンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="2a134-239">Adding a Desktop Bridge component</span></span>  

<span data-ttu-id="2a134-240">デスクトップ ブリッジ コンポーネントをパッケージに追加する場合は、Win32 プロジェクトを作成してビルドする必要Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2a134-240">If you want to add a Desktop Bridge component to your package, you must create and build your Win32 project in Visual Studio.</span></span>  <span data-ttu-id="2a134-241">win32 アプリを UWP に変換する方法については、「デスクトップ ブリッジ経由でアプリを [Windows 10](/windows/uwp/porting/desktop-to-uwp-root)に移植する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a134-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span>  <span data-ttu-id="2a134-242">ビルドが完了Visual Studio、次の手順を実行して、Win32 実行可能ファイルをパッケージに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>  

1.  <span data-ttu-id="2a134-243">Win32 プロジェクトを UWP プロジェクトと同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="2a134-243">Add the Win32 project to the same solution as the UWP project.</span></span>  
1.  <span data-ttu-id="2a134-244">Win32 プロジェクトを UWP プロジェクトの依存プロジェクトとして設定します。</span><span class="sxs-lookup"><span data-stu-id="2a134-244">Set the Win32 project as a dependent project for the UWP project:</span></span>  
    
    ![プロジェクトの依存関係を設定する](../media/project-dependencies.png)  
    
1.  <span data-ttu-id="2a134-246">`Win32`UWP プロジェクト内にフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a134-246">Create a `Win32` folder within the UWP project.</span></span>  <span data-ttu-id="2a134-247">プロジェクトに必要なバイナリを `Win32` このフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2a134-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span>  <span data-ttu-id="2a134-248">など、すべてのバイナリのプロパティを `Build Action=Content` 構成します `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="2a134-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>  
    
    ![win32 および UWP アプリ ファイルを含むフォルダー](../media/desktop-bridge.png)  
    
1.  <span data-ttu-id="2a134-250">PostBuild イベント コマンドを使用して、プロジェクトに必要なすべてのバイナリをこのフォルダーにコピーするには、UWP プロジェクト ファイル `Win32` を変更します。</span><span class="sxs-lookup"><span data-stu-id="2a134-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span>  <span data-ttu-id="2a134-251">これにより、ソリューションが再構築される度に、更新されたバイナリがフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2a134-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>  
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```  
    
1.  <span data-ttu-id="2a134-252">要素 `package.manifest.xml` を要素に追加 `<desktop:Extension>` して変更 `<Extensions>` します。</span><span class="sxs-lookup"><span data-stu-id="2a134-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>  
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```  
    
## <a name="deploying"></a><span data-ttu-id="2a134-253">展開</span><span class="sxs-lookup"><span data-stu-id="2a134-253">Deploying</span></span>  

<span data-ttu-id="2a134-254">上記で説明した UWP プロジェクト \(およびオプションで Win32 project\) を構成したら、ソリューションを展開する準備が整い、Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2a134-254">Once you have configured your UWP project \(and optionally Win32 project\) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>  

![ビルドインプロセス プロジェクト](../media/native-message-uwp-debug.png)  

<span data-ttu-id="2a134-256">ソリューションが正しく展開された後、Microsoft Edge に拡張機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>  

![Microsoft Edge に表示される拡張機能](../media/secureextension.png)  

## <a name="packaging"></a><span data-ttu-id="2a134-258">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="2a134-258">Packaging</span></span>  

> [!NOTE]
> <span data-ttu-id="2a134-259">Microsoft Edge 拡張機能を Microsoft Store に提出する機能は、現在制限付き機能です。</span><span class="sxs-lookup"><span data-stu-id="2a134-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="2a134-260">[Microsoft Store の一](https://developer.microsoft.com/microsoft-edge/extensions/requests/) 部として要求を送信し、将来の更新プログラムと見なします。</span><span class="sxs-lookup"><span data-stu-id="2a134-260">[Send a request](https://developer.microsoft.com/microsoft-edge/extensions/requests/) to be a part of the Microsoft Store, and be considered for future updates.</span></span>  

<span data-ttu-id="2a134-261">組み込みの機能を使用して Windows デベロッパー センターに提出するためのストア パッケージをVisual Studioできます。</span><span class="sxs-lookup"><span data-stu-id="2a134-261">You may generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>  

![ストア パッケージの作成](../media/create-store-package.png)  

## <a name="debugging"></a><span data-ttu-id="2a134-263">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2a134-263">Debugging</span></span>  

<span data-ttu-id="2a134-264">デバッグの手順は、テストするコンポーネントによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a134-264">The instructions for debugging vary depending on which component you want to test out:</span></span>  

### <a name="debugging-the-extension"></a><span data-ttu-id="2a134-265">拡張機能のデバッグ</span><span class="sxs-lookup"><span data-stu-id="2a134-265">Debugging the extension</span></span>  

<span data-ttu-id="2a134-266">ソリューションを展開すると、拡張機能が Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2a134-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span>  <span data-ttu-id="2a134-267">拡張機能のデバッグ [方法については](./debugging-extensions.md) 、「デバッグ ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a134-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>  

### <a name="debugging-the-uwp-app"></a><span data-ttu-id="2a134-268">UWP アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2a134-268">Debugging the UWP app</span></span>  

<span data-ttu-id="2a134-269">拡張機能がネイティブ メッセージング API を使用して接続しようとすると、UWP アプリ [が起動します](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。</span><span class="sxs-lookup"><span data-stu-id="2a134-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span>  <span data-ttu-id="2a134-270">プロセスが開始された後にのみ、UWP アプリをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a134-270">You must debug the UWP app only once the process starts.</span></span>  <span data-ttu-id="2a134-271">これは、プロジェクトの [プロパティ] ページを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-271">This may be configured using the Property page of the project:</span></span>  

1.  <span data-ttu-id="2a134-272">[Visual Studio UWP アプリ プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="2a134-272">In Visual Studio, hover on your UWP app project and open the contextual menu \(right-click\)</span></span>  
1.  <span data-ttu-id="2a134-273">プロパティの **選択**</span><span class="sxs-lookup"><span data-stu-id="2a134-273">Select **Properties**</span></span>  
1.  <span data-ttu-id="2a134-274">[起動 **しない] をオンにし、起動時にコードをデバッグする**</span><span class="sxs-lookup"><span data-stu-id="2a134-274">Check **Do not launch, but debug my code when it starts**</span></span>  
    
    ![[起動しない] ボックスを選択する](../media/native-message-do-not-launch.png)  
    
<span data-ttu-id="2a134-276">このVisual Studio、デバッグするコードでブレークポイントを設定し、F5 キーを押してデバッガーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="2a134-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span>  <span data-ttu-id="2a134-277">拡張機能を操作して UWP アプリに接続すると、Visual Studioプロセスに自動的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="2a134-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>  

### <a name="debugging-the-desktop-bridge"></a><span data-ttu-id="2a134-278">デスクトップ ブリッジのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2a134-278">Debugging the Desktop Bridge</span></span>  

<span data-ttu-id="2a134-279">デスクトップ ブリッジ [\(](/windows/msix/desktop/desktop-to-uwp-debug) 変換された Win32 app\) をデバッグする方法はさまざまな場合でも、このシナリオに適用できる唯一の方法は PLMDebug オプションです。</span><span class="sxs-lookup"><span data-stu-id="2a134-279">Even though there are various [methods for debugging a Desktop Bridge](/windows/msix/desktop/desktop-to-uwp-debug) \(converted Win32 app\), the only one applicable for this scenarios is the PLMDebug option.</span></span>  <span data-ttu-id="2a134-280">また、デバッグ コードをスタートアップ関数に追加して、特定の時間の待機を実行し、プロセスにVisual Studioすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a134-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>  
