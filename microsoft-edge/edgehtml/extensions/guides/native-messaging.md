---
description: ネイティブ メッセージングを使用して拡張機能をコンパニオン UWP アプリと通信する方法について説明します。
title: 拡張機能 - ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者, ネイティブ, メッセージング, UWP
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 983ae11822edabc0f27bd6c02f9397104b082ad6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234950"
---
# <span data-ttu-id="69ac3-104">Microsoft Edge のネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="69ac3-104">Native messaging in Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="69ac3-105">ネイティブ メッセージング アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="69ac3-105">Native messaging architecture overview</span></span>

<span data-ttu-id="69ac3-106">Windows 10 Creators Update を使用すると、Microsoft Edge 拡張機能はネイティブ メッセージングを使用して、コンパニオン ユニバーサル Windows プラットフォーム (UWP) アプリと通信できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-106">With the Windows 10 Creators Update, Microsoft Edge extensions are able to use native messaging to communicate with a companion Universal Windows Platform (UWP) app.</span></span>  <span data-ttu-id="69ac3-107">大きなレベルでは、Microsoft Edge 拡張機能では、Chrome および Firefox 拡張機能と同じ API をネイティブ メッセージングに使用します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-107">At a high level, Microsoft Edge extensions use the same APIs for native messaging as Chrome and Firefox extensions.</span></span> <span data-ttu-id="69ac3-108">ただし、ネイティブ メッセージング ホストは、ユニバーサル Windows プラットフォームを使用して実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-108">However, the native messaging host will need to be implemented using the Universal Windows Platform.</span></span>

> [!NOTE]
> <span data-ttu-id="69ac3-109">次に示すメソッド (AppService 経由で UWP アプリに接続する) は、Microsoft Edge 拡張機能とネイティブ コンポーネント間の通信を可能にするための唯一のサポートされているメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="69ac3-109">The method outlined below (connecting to a UWP app via AppService) is the only supported mechanism for enabling communication between Microsoft Edge extensions and native components.</span></span> <span data-ttu-id="69ac3-110">従来の[](#adding-a-desktop-bridge-component)Win32 コンポーネントとの通信を有効にする方法の詳細については、このガイドの「デスクトップ ブリッジ コンポーネントの追加」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-110">Please see the [Adding a Desktop Bridge component](#adding-a-desktop-bridge-component) section of this guide for more information on how to enable communication with legacy Win32 components.</span></span> 

 <span data-ttu-id="69ac3-111">Microsoft Edge のネイティブ メッセージング アーキテクチャは、基になるプロセス間通信 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) (IPC) インフラストラクチャとして既存の API を利用します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-111">Microsoft Edge's native messaging architecture leverages the existing [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API as the underlying inter-process communication (IPC) infrastructure.</span></span> <span data-ttu-id="69ac3-112">UWP アプリは `AppService` 、API を使って相互に通信します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-112">UWP apps use the `AppService` API to communicate with one another.</span></span> <span data-ttu-id="69ac3-113">これにより、Microsoft Edge 拡張機能は UWP アプリと通信できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-113">Because of this, Microsoft Edge extensions can now communicate with UWP apps.</span></span>

![ネイティブ メッセージング アーキテクチャ](./../media/native-messaging-architecture.png)

### <span data-ttu-id="69ac3-115">ネイティブ メッセージングを使用しない場合</span><span class="sxs-lookup"><span data-stu-id="69ac3-115">When and when not to use native messaging</span></span>

<span data-ttu-id="69ac3-116">ネイティブ メッセージングは、拡張機能に全く新しいレイヤーを追加します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-116">Native messaging adds a whole new layer to your extension.</span></span> <span data-ttu-id="69ac3-117">拡張機能用の UWP コンパニオン アプリを実装すると、次の可能性が利用できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-117">By implementing a UWP companion app for your extension, the following possibilities become available to you:</span></span>

* <span data-ttu-id="69ac3-118">データ (資格情報など) をコンパニオン UWP アプリと同期します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-118">Synchronize data (e.g. credentials) with a companion UWP app.</span></span>
* <span data-ttu-id="69ac3-119">Web API では使用できない強力な暗号化/暗号化解除アルゴリズムを実装します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-119">Implement stronger encryption/decryption algorithms not available in web APIs.</span></span>
* <span data-ttu-id="69ac3-120">Web API からアクセスできないリソース (ハードウェアや USB デバイスなど) にアクセスする</span><span class="sxs-lookup"><span data-stu-id="69ac3-120">Access resources that are not accessible through web APIs, e.g. hardware or USB devices</span></span>

<span data-ttu-id="69ac3-121">セキュリティやポリシーの制限によりネイティブ メッセージングを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-121">There are a few instances where native messaging can't be used due to security or policy restrictions:</span></span>

* <span data-ttu-id="69ac3-122">Microsoft Edge または Windows のユーザー設定の変更 (既定のブラウザーまたは検索プロバイダーの変更など)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-122">Modifying user settings in either Microsoft Edge or Windows, e.g. changing the default browser or search provider.</span></span>
* <span data-ttu-id="69ac3-123">アプリと拡張機能の両方の Microsoft Store ポリシーに違反するアクション。</span><span class="sxs-lookup"><span data-stu-id="69ac3-123">Actions that violate Microsoft Store policies for both apps and extensions.</span></span>
* <span data-ttu-id="69ac3-124">ネイティブ メッセージ ホスト経由でリモート エンドポイントにデータを転送する。</span><span class="sxs-lookup"><span data-stu-id="69ac3-124">Transferring data to remote endpoint via native message host.</span></span>
* <span data-ttu-id="69ac3-125">拡張機能の動作を変更するコンテンツを他のアプリがダウンロードすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-125">Allowing other apps to download content that changes extension behavior.</span></span>

## <span data-ttu-id="69ac3-126">デモ</span><span class="sxs-lookup"><span data-stu-id="69ac3-126">Demos</span></span>

<span data-ttu-id="69ac3-127">コンパニオン UWP アプリとデスクトップ ブリッジの両方を含む Microsoft Edge ネイティブ メッセージング拡張機能の外観を確認するには、GitHub の [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) と [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-127">To get a feel for what an Microsoft Edge native messaging extension that has both a companion UWP app and a Desktop Bridge looks like, check out the [SecureInput](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/SecureInput) and [DigitalSigning (C++)](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/DigitalSigning) examples on GitHub.</span></span>

### <span data-ttu-id="69ac3-128">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="69ac3-128">How it works</span></span>

<span data-ttu-id="69ac3-129">サンプルの Microsoft Edge 拡張機能コンポーネントは、コンテンツ スクリプトを使用して、ユーザーが暗号化する必要がある情報を入力している場合を検出します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-129">The Microsoft Edge extension component of the sample uses its content script to detect when a user is typing in information that should be encrypted.</span></span> <span data-ttu-id="69ac3-130">拡張機能は、ネイティブ メッセージングを介してデスクトップ ブリッジ コンポーネントにこれを通信します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-130">The extension communicates this to the Desktop Bridge component via native messaging.</span></span> <span data-ttu-id="69ac3-131">ユーザーがデータを送信する準備ができたら、拡張機能は暗号化された値を Web サイトに返します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-131">When the user is ready to submit the data, the extension will return an encrypted value back to the website.</span></span>

> [!NOTE]
> <span data-ttu-id="69ac3-132">このサンプルは、カスタム イベントを使用して拡張機能のコンテンツ スクリプトと通信する Web ページでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-132">This sample will only work on a webpage that uses custom events to communicate with the extension's content script.</span></span> <span data-ttu-id="69ac3-133">サンプル フォルダーには、拡張子をテスト [する .html](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="69ac3-133">The sample folder includes a [.html file](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/blob/master/SecureInput/SecureInput.html) to test the extension with.</span></span>

<span data-ttu-id="69ac3-134">この例では、UWP アプリを使ってデスクトップ ブリッジから Microsoft Edge に応答を渡し、コールバック経由で Microsoft Edge 拡張機能に送信します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-134">In this example, the UWP app is used to pass responses from the Desktop Bridge to Microsoft Edge, which then gets sent to the Microsoft Edge extension via callback.</span></span> <span data-ttu-id="69ac3-135">この例では、メイン アプリでネイティブ メッセージング ホストを実行しますが、バックグラウンド タスクとして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-135">While this example has the native messaging host run in the main app, it's also able to run as a background task.</span></span> <span data-ttu-id="69ac3-136">2 つのスクリプトを切り替えるには、拡張機能のバックグラウンド スクリプトを編集し、次に示す文字列を変更する必要 `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` があります `"NativeMessagingHostOutOfProcess"` 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-136">Switching between the two requires editing the extension's background script, changing the string within `port = browser.runtime.connectNative("NativeMessagingHostInProcessService");` to `"NativeMessagingHostOutOfProcess"`.</span></span>

## <span data-ttu-id="69ac3-137">Chrome と Microsoft Edge の実装</span><span class="sxs-lookup"><span data-stu-id="69ac3-137">Chrome vs Microsoft Edge implementation</span></span>

<span data-ttu-id="69ac3-138">Chrome は、拡張機能がアプリと通信するためにメッセージを渡す API を使用するルートに進む一方で、Microsoft Edge は、Microsoft Edge 拡張機能と UWP アプリの通信を可能にする API を利用 [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-138">While Chrome goes the route of using message passing APIs for their extensions to communicate with apps, Microsoft Edge utilizes the [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) API which now enables Microsoft Edge extensions and UWP apps to communicate.</span></span>

<span data-ttu-id="69ac3-139">このセクションでは、Chrome と Microsoft Edge がネイティブ メッセージングの実装を処理する方法の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-139">This section details the differences between how Chrome and Microsoft Edge handle native messaging implementation.</span></span>

### <span data-ttu-id="69ac3-140">登録とホスト マニフェスト</span><span class="sxs-lookup"><span data-stu-id="69ac3-140">Registration and host manifest</span></span>
<span data-ttu-id="69ac3-141">拡張機能によってアプリがネイティブ メッセージング ホストとして認識されるには、アプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-141">In order for your app to be recognized by your extension as a native messaging host, it will need to be registered.</span></span>

<span data-ttu-id="69ac3-142">[Chrome ネイティブ メッセージング ホスト](https://developer.chrome.com/extensions/nativeMessaging)の登録では、アプリは、ネイティブ メッセージング ホストの構成を定義する Windows ファイル システムの任意の場所にマニフェスト ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-142">For [Chrome native messaging](https://developer.chrome.com/extensions/nativeMessaging) host registration, your app needs to install a manifest file anywhere in the Windows file system that defines the native messaging host configuration.</span></span>

<span data-ttu-id="69ac3-143">次の JSON は、構成ファイルのセットアップ方法の例です。</span><span class="sxs-lookup"><span data-stu-id="69ac3-143">The following JSON is an example of how the config file can be set up:</span></span>

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

<span data-ttu-id="69ac3-144">このファイルをインストールするには、アプリで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-144">To install this file, the app would need to:</span></span>

1.  <span data-ttu-id="69ac3-145">マニフェスト ファイルを、ホスト構成を定義するレジストリ内の定義済みの場所に登録します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-145">Register the manifest file in a predefined location in the registry that defines the host configuration:</span></span>
    -   ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
        <span data-ttu-id="69ac3-146">または</span><span class="sxs-lookup"><span data-stu-id="69ac3-146">or</span></span>
        
    -   ```text
        HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application
        ```  
        
2.  <span data-ttu-id="69ac3-147">そのキーの既定値をマニフェスト ファイルへの完全パス (例:</span><span class="sxs-lookup"><span data-stu-id="69ac3-147">Set the default value of that key to the full path to the manifest file, e.g.</span></span> 
    
    ```text
    [HKEY_CURRENT_USER\Software\Google\Chrome\NativeMessagingHosts\com.my_company.my_application] @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
<span data-ttu-id="69ac3-148">Microsoft Edge の場合、(ネイティブ メッセージング ホスト) を登録するには、拡張機能と同じパッケージに UWP コンパニオン アプリを含め、プロジェクトのファイルに [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx) [AppService](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)拡張機能を指定する必要があります。 `Package.appxmanifest`</span><span class="sxs-lookup"><span data-stu-id="69ac3-148">For Microsoft Edge, in order to register an [`AppService`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.aspx)(native messaging host) you'll need to include the UWP companion app in the same package as your extension and specify the [AppService extension](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) in your project's `Package.appxmanifest` file.</span></span> <span data-ttu-id="69ac3-149">これらの `EntryPoint` 属性 `Name` は、次の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-149">The `EntryPoint` and `Name` attributes can be configured by you:</span></span>

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


<span data-ttu-id="69ac3-150">また、サービスへの接続を許可する拡張機能を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-150">You'll also need to set which extension(s) are allowed to connect to the service.</span></span> <span data-ttu-id="69ac3-151">Microsoft Edge の AppxManifest には同等のマニフェスト プロパティはないので、これは実行時に UWP アプリによって決定され、適用される `"allowed_origins"` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-151">Because Microsoft Edge doesn't have an equivalent `"allowed_origins"` manifest property in its AppxManifest, this will need to be determined and enforced at runtime by your UWP app.</span></span> <span data-ttu-id="69ac3-152">Microsoft Edge は拡張機能の代わりに接続を確立します。アプリは、呼び出し元のパッケージ ファミリ名を検索して、発信者を制御または認証するために Microsoft Edge によって接続されていないかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-152">Since Microsoft Edge will be establishing the connection on behalf of the extension, the app can look up the caller's Package Family Name to determine if they're being connected by Microsoft Edge to control or authenticate the caller.</span></span> <span data-ttu-id="69ac3-153">例:</span><span class="sxs-lookup"><span data-stu-id="69ac3-153">E.g.</span></span> 

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

### <span data-ttu-id="69ac3-154">メッセージ送信</span><span class="sxs-lookup"><span data-stu-id="69ac3-154">Message sending</span></span>

<span data-ttu-id="69ac3-155">アプリと拡張機能が相互に通信するには、メッセージのやり取りが必要です。</span><span class="sxs-lookup"><span data-stu-id="69ac3-155">For an app and an extension to communicate with one another, messages need to be sent to and from them.</span></span>

<span data-ttu-id="69ac3-156">Chrome 拡張機能は、API を使用してメッセージを開始し、非永続的なチャネルを使用してネイティブ ホスト [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) にメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-156">Chrome extensions initiate a message using the [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) API to deliver a message to the native host using a non-persistent channel.</span></span> 

```javascript
chrome.runtime.sendNativeMessage(string application, object message, function responseCallback)
```  

<span data-ttu-id="69ac3-157">最初のパラメーターはネイティブ ホストの名前です。Chrome は、レジストリでマニフェストを検索します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-157">The first parameter is the name of the native host, which Chrome looks up in the registry for the manifest.</span></span> <span data-ttu-id="69ac3-158">マニフェストは、Chrome がサンドボックス内で起動する .exe を指定し、メッセージは std i/o を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-158">The manifest specifies the .exe that Chrome will launch in a sandbox, and the message is sent using std i/o.</span></span> <span data-ttu-id="69ac3-159">拡張機能は、API を使用して永続的なチャネルを確立することもできます。このチャネルは、ネイティブ ホストの名前を唯一の `runtime.connectNative` パラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-159">Extensions can also establish a persistent channel using the `runtime.connectNative` API, which takes the name of the native host as the only parameter.</span></span> 

<span data-ttu-id="69ac3-160">Microsoft Edge では、Chrome のネイティブ メッセージング API と同じコンストラクトを使用して、Microsoft Edge 拡張機能で接続先のアプリ サービスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-160">Microsoft Edge uses the same construct as Chrome's native messaging API to allow Microsoft Edge extensions to specify which app service to connect to.</span></span> <span data-ttu-id="69ac3-161">最初のパラメーターは `runtime.sendNativeMessage` 、アプリ サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-161">The first parameter in `runtime.sendNativeMessage` specifies the app service name.</span></span> <span data-ttu-id="69ac3-162">[登録と [ホスト マニフェスト] セクションでは](#registration-and-host-manifest) 、次の情報が表示されます `"com.microsoft.inventory"` 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-162">In the [Registration and host manifest](#registration-and-host-manifest) section, this is `"com.microsoft.inventory"`.</span></span> <span data-ttu-id="69ac3-163">Microsoft Edge 拡張機能プラットフォームでは、ネイティブ メッセージング ホストが拡張機能と同じ AppX にパッケージ化された UWP アプリに制限されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-163">The Microsoft Edge extension platform restricts the native messaging host to being a UWP app that is packaged in the same AppX as the extension.</span></span> <span data-ttu-id="69ac3-164">これにより、マニフェスト エントリを改ざんして Microsoft Edge を別のパッケージ ファミリ名に接続しようとする悪意のある攻撃に関連するセキュリティ リスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-164">This mitigates any security risks associated with malicious attacks that try to connect Microsoft Edge with another Package Family Name by tampering with manifest entries.</span></span> 

<span data-ttu-id="69ac3-165">つまり、Microsoft Edge は、アプリ サービスのプロバイダーを一意に識別するために、API で指定された名前に加えて、拡張機能と同じパッケージ ファミリ名を `AppService` 使用します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-165">This means that Microsoft Edge will use the same Package Family Name as the extension, in addition to the `AppService` name specified in the API, to uniquely identify the provider of the app service.</span></span>  

> [!NOTE]
> <span data-ttu-id="69ac3-166">これは [、Microsoft Edge](./porting-chrome-extensions.md)Extension Toolkit によって簡単に変換Toolkit。</span><span class="sxs-lookup"><span data-stu-id="69ac3-166">This will not be easily converted by the [Microsoft Edge Extension Toolkit](./porting-chrome-extensions.md).</span></span> <span data-ttu-id="69ac3-167">アクセス許可を指定する拡張機能には、このコンポーネントの手動変換を必要とするようにフラグ `"nativeMessaging"` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-167">Any extensions that specifies the `"nativeMessaging"` permission will be flagged as requiring manual conversion for this component.</span></span>

### <span data-ttu-id="69ac3-168">通信プロトコル</span><span class="sxs-lookup"><span data-stu-id="69ac3-168">Communication protocol</span></span>

<span data-ttu-id="69ac3-169">ネイティブ メッセージングの通信プロトコルは、送信前のメッセージの書式設定方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-169">Communication protocol for native messaging determines how messages are formatted before sending.</span></span>

<span data-ttu-id="69ac3-170">Chrome は、各ネイティブ メッセージング ホストを個別のプロセスで開始し、標準の入力と標準出力を使用して通信します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-170">Chrome starts each native messaging host in a separate process and communicates with it using standard input and standard output.</span></span> <span data-ttu-id="69ac3-171">両方向でメッセージを送信するために同じ形式が使用されます。各メッセージは JSON、UTF-8 エンコードを使用してシリアル化され、ネイティブバイト順で 32 ビットのメッセージ長が先行します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-171">The same format is used to send messages in both directions: each message is serialized using JSON, UTF-8 encoded and is preceded with 32-bit message length in native byte order.</span></span>

<span data-ttu-id="69ac3-172">Microsoft Edge では、アプリ サービスを実装するバックグラウンド タスク/メイン アプリがプラットフォームによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-172">For Microsoft Edge, the background task/main app that implements the app service will be started by the platform.</span></span> <span data-ttu-id="69ac3-173">起動時に、バックグラウンド タスクのメソッド `Run` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-173">On startup, the background task's `Run` method will be invoked:</span></span>  

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

<span data-ttu-id="69ac3-174">拡張機能が UWP アプリにメッセージを送信すると、 [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-174">When your extension sends a message to your UWP app, the [`onRequestReceived`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection.requestreceived) event will be raised.</span></span> <span data-ttu-id="69ac3-175">この JSON 形式のメッセージは、オブジェクトの最初の KeyValue ペアに文字列化 [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-175">This JSON formatted message will then be stringified into the first KeyValue pair of a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object.</span></span> <span data-ttu-id="69ac3-176">:</span><span class="sxs-lookup"><span data-stu-id="69ac3-176">:</span></span>

```csharp
private async void OnRequestReceived(
AppServiceConnection sender,
AppServiceRequestReceivedEventArgs args)
{
    ...
}
```  

<span data-ttu-id="69ac3-177">UWP アプリが拡張機能に応答を返す場合、a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) がオブジェクトに追加 `ValueSet` されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-177">When your UWP app sends a response back to your extension, a [`KeyValuePair`](https://msdn.microsoft.com/library/windows/apps/5tbh8a42) will be added to the `ValueSet` object.</span></span> <span data-ttu-id="69ac3-178">この `Key` プロパティは Microsoft Edge では無視されますが、プロパティには `Value` 有効な JSON 文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-178">The `Key` property will be ignored by Microsoft Edge, but the `Value` property will contain a valid JSON string.</span></span>

### <span data-ttu-id="69ac3-179">Callback</span><span class="sxs-lookup"><span data-stu-id="69ac3-179">Callback</span></span>

<span data-ttu-id="69ac3-180">コールバックの場合、Chrome は、コールバック関数がメッセージの送信からの非同期応答を処理するために [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) 使用します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-180">For callbacks, Chrome uses [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) which allows a callback function to handle any asynchronous response from sending a message.</span></span>

<span data-ttu-id="69ac3-181">Microsoft Edge では、 [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) オブジェクトのメソッド [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) を使って、アプリがオブジェクトを拡張機能に [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) 送り返します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-181">Microsoft Edge uses the [`AppServiceRequest`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest) object's [`SendResponseAsync`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appservicerequest.sendresponseasync) method to let the app send a [`ValueSet`](https://msdn.microsoft.com/library/windows/apps/dn636131) object back to the extension.</span></span>


### <span data-ttu-id="69ac3-182">メッセージ サイズの制限</span><span class="sxs-lookup"><span data-stu-id="69ac3-182">Message size limit</span></span>
<span data-ttu-id="69ac3-183">拡張機能とアプリの間で送信されるメッセージのメッセージサイズの制限は、Chrome と Microsoft Edge では異なります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-183">Messages that are sent back and forth between an extension and an app have different message size limitations in place for Chrome and Microsoft Edge.</span></span>

<span data-ttu-id="69ac3-184">Chrome には、次のメッセージ サイズ制限があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-184">Chrome has the following message size limitations:</span></span>
-   <span data-ttu-id="69ac3-185">ネイティブ メッセージング ホストからの単一メッセージの制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="69ac3-185">Single message limit from native messaging host: 1 MB</span></span>
-   <span data-ttu-id="69ac3-186">ネイティブ メッセージング ホストに送信される単一のメッセージ制限: 4 GB</span><span class="sxs-lookup"><span data-stu-id="69ac3-186">Single message limit sent to native messaging host: 4 GB</span></span>
    
<span data-ttu-id="69ac3-187">Microsoft Edge では、メッセージ サイズに制限はありません (メモリに依存)、Microsoft Edge は次のメッセージ サイズ制限を課して、ネイティブ アプリの動作の誤りから自分自身を `AppService` 保護します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-187">For Microsoft Edge, while `AppService` has no limit on message size (dependent on memory), Microsoft Edge protects itself against misbehaving native apps by imposing the following message size limits:</span></span>
-   <span data-ttu-id="69ac3-188">UWP アプリから拡張機能への単一メッセージの制限: 1 MB</span><span class="sxs-lookup"><span data-stu-id="69ac3-188">Single message limit from UWP app to extension: 1 MB</span></span>
-   <span data-ttu-id="69ac3-189">拡張機能から UWP アプリへの単一メッセージの制限: 100 MB</span><span class="sxs-lookup"><span data-stu-id="69ac3-189">Single message limit from extension to UWP app: 100 MB</span></span>
    
### <span data-ttu-id="69ac3-190">ネイティブ メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="69ac3-190">Native messaging connections</span></span>

<span data-ttu-id="69ac3-191">ネイティブ メッセージングには 2 種類の接続があります。永続的および非永続的。</span><span class="sxs-lookup"><span data-stu-id="69ac3-191">There are two types of connections for native messaging; persistent and non-persistent.</span></span>
<span data-ttu-id="69ac3-192">固定 **接続** とは、ポートが破棄されるまで実行され続けた接続です。</span><span class="sxs-lookup"><span data-stu-id="69ac3-192">A **persistent** connection is a connection that is kept running until the port is destroyed.</span></span> <span data-ttu-id="69ac3-193">永続的 **でない接続とは** 、一度に 1 つのメッセージに対して開き、配信後に閉じる接続です。</span><span class="sxs-lookup"><span data-stu-id="69ac3-193">A **non-persistent** connection is a connection that is opened for one message at a time and closes after delivery.</span></span>

#### <span data-ttu-id="69ac3-194">永続的</span><span class="sxs-lookup"><span data-stu-id="69ac3-194">Persistent</span></span>

<span data-ttu-id="69ac3-195">Chrome の場合、永続的な接続は、次を使用してメッセージング ポートを作成することで行います [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-195">For Chrome, a persistent connection is made by creating a messaging port using [`runtime.connectNative`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="69ac3-196">ポートが作成されると、Chrome はネイティブメッセージング ホスト プロセスを開始し、破棄されたポートまで実行を続ける。</span><span class="sxs-lookup"><span data-stu-id="69ac3-196">Once the port is made, Chrome starts a native messaging host process that keeps running until the port it destroyed.</span></span>

<span data-ttu-id="69ac3-197">Microsoft Edge の場合、メッセージング ポートが作成されると、Microsoft Edge はポートを開始し、ポートが破棄されるまで実行 `runtime.connectNative` [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) を維持します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-197">For Microsoft Edge, once a messaging port is created using `runtime.connectNative`, Microsoft Edge starts the [`AppServiceConnection`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceconnection) and keeps it running until the port is destroyed.</span></span> <span data-ttu-id="69ac3-198">次のスニペットは、UWP アプリ内から永続的な接続が確立される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="69ac3-198">The following snippet shows how a persistent connection is established from within a UWP app.</span></span> 

```csharp
this.inventoryService = new AppServiceConnection();  
// Here, we use the app service name provided via the runtime.connectNative API  
this.inventoryService.AppServiceName = "com.microsoft.inventory";  
// Use the same Package Family Name as the extension package
this.inventoryService.PackageFamilyName = "replace with the Package Family Name";  
var status = await
this.inventoryService.OpenAsync();
```  

#### <span data-ttu-id="69ac3-199">非永続的</span><span class="sxs-lookup"><span data-stu-id="69ac3-199">Non-persistent</span></span>

<span data-ttu-id="69ac3-200">メッセージを Chrome で使用して送信すると、メッセージング ポートを作成せずに、Chrome はメッセージごとに新しいネイティブ メッセージング [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) ホスト プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-200">When a message is sent using [`runtime.sendNativeMessage`](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) in Chrome, without creating a messaging port, Chrome starts a new native messaging host process for each message.</span></span> <span data-ttu-id="69ac3-201">ホスト プロセスによって生成された最初のメッセージは、元の要求に対する応答として処理され、その後の他のすべてのメッセージは無視されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-201">The first message generated by the host process is handled as a response to the original request, and all other messages after it are ignored.</span></span>

<span data-ttu-id="69ac3-202">Microsoft Edge は、すべてのメッセージの応答を受信した後、接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-202">Microsoft Edge will terminate the connection after every messages' response has been received.</span></span> <span data-ttu-id="69ac3-203">次のスニペットは、要求を受信して UWP アプリ内で終了する非永続的な接続を示しています `AppServiceConnection` [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse) 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-203">The following snippet shows a non-persistent connection that is established with `AppServiceConnection` that will then be terminated within the UWP app after a request has been received and stored as an [`AppServiceResponse`](https://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.appservice.appserviceresponse).</span></span>

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

### <span data-ttu-id="69ac3-204">許可</span><span class="sxs-lookup"><span data-stu-id="69ac3-204">Permission</span></span>

<span data-ttu-id="69ac3-205">拡張機能でネイティブ メッセージングの使用を有効にするには、Chrome と Microsoft Edge の両方について、ファイルでアクセス許可を `"nativeMessaging"` 宣言する必要 `manifest.json` があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-205">In order to enable native messaging use with your extension, for both Chrome and Microsoft Edge you'll need to declare the `"nativeMessaging"` permission in you `manifest.json` file.</span></span>

## <span data-ttu-id="69ac3-206">アプリ サービス</span><span class="sxs-lookup"><span data-stu-id="69ac3-206">App services</span></span>
<span data-ttu-id="69ac3-207">このセクションでは、アプリ サービスが Microsoft Edge ネイティブ メッセージングのパフォーマンスとメモリに与える影響について詳しい説明します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-207">This section details the impact app services has on Microsoft Edge native messaging performance and memory.</span></span>

### <span data-ttu-id="69ac3-208">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="69ac3-208">Performance</span></span>

<span data-ttu-id="69ac3-209">アプリ サービスは、ネイティブ メッセージングの目的で Microsoft Edge を呼び出すフォアグラウンド アプリによって "スポンサー付け" されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-209">App services are "sponsored" by the foreground app that calls them which for native messaging purposes is Microsoft Edge.</span></span> <span data-ttu-id="69ac3-210">つまり、Microsoft Edge が実行されている限り、アプリ サービスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-210">This means that app services can run as long as Microsoft Edge is running.</span></span>

<span data-ttu-id="69ac3-211">待機時間に関して、アプリ サービスは名前付きパイプを使用します。このパイプは、最初の接続後に 2 つのアプリが直接通信できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-211">In regards to latency, app services use named pipes that, after initial connection, allow two apps to directly communicate.</span></span> <span data-ttu-id="69ac3-212">この通信方法により、待機時間が短くなる。</span><span class="sxs-lookup"><span data-stu-id="69ac3-212">This method of communication produces low latency.</span></span> <span data-ttu-id="69ac3-213">CPU が遅いデバイスでは、アプリ サービスをホストするプロセスを開始した後、初期遅延が発生します (一部のデバイスではバックグラウンド タスクを起動するために約 80ms)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-213">Devices with slow CPUs will experience some initial latency after starting up the process that hosts the app service (~80ms to startup the background task on some devices).</span></span> <span data-ttu-id="69ac3-214">起動後は、低速な CPU デバイスのパフォーマンスが良好である必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-214">After start-up, performance on slow CPU devices should be good.</span></span> 

### <span data-ttu-id="69ac3-215">メモリ</span><span class="sxs-lookup"><span data-stu-id="69ac3-215">Memory</span></span>
<span data-ttu-id="69ac3-216">アプリ サービスに割り当てられたメモリは、Microsoft Edge に割り当てられたクォータから取り出されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-216">The memory allocated to an app service is taken out of the quota allocated to Microsoft Edge.</span></span> <span data-ttu-id="69ac3-217">つまり、Microsoft Edge が起動するアプリ サービスが多すぎると、メモリが使い切れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-217">This means that if Microsoft Edge starts too many app services there is a possibility that they could run out of memory.</span></span> <span data-ttu-id="69ac3-218">通常のバックグラウンド タスクのメモリ制限は、アプリ サービスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-218">The usual background task memory caps are enforced on app services.</span></span> <span data-ttu-id="69ac3-219">たとえば、512 MB デバイスでは、アプリ サービスのバックグラウンド タスクは 16 MB 以下に設定できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-219">For instance, on a 512MB device an app service background task can be no larger than 16MB.</span></span> <span data-ttu-id="69ac3-220">この数は、デバイスのスケール アップに合って上がっています。</span><span class="sxs-lookup"><span data-stu-id="69ac3-220">This number goes up as the devices scale up.</span></span>

## <span data-ttu-id="69ac3-221">ネイティブ メッセージングを使用した拡張機能の作成</span><span class="sxs-lookup"><span data-stu-id="69ac3-221">Creating an extension with native messaging</span></span>

<span data-ttu-id="69ac3-222">ネイティブ メッセージングをテストするには、拡張機能にパッケージ ファミリ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="69ac3-222">In order to test native messaging, your extension needs a Package Family Name.</span></span> <span data-ttu-id="69ac3-223">Microsoft Edge はこれを使用してネイティブ メッセージホスト ID を決定します。つまり、拡張機能をパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-223">Microsoft Edge uses this to determine the native message host identity, which means your extension should be packaged.</span></span> 

<span data-ttu-id="69ac3-224">ネイティブ メッセージングを使用して拡張機能を作成するには、次Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="69ac3-224">To create your extension with native messaging in Visual Studio:</span></span>

1.  <span data-ttu-id="69ac3-225">アプリで UWP プロジェクトをVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="69ac3-225">Create a UWP project in Visual Studio.</span></span>
2.  <span data-ttu-id="69ac3-226">[ `AppService` UWP アプリに追加します](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-226">[Add `AppService` to your UWP app](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
    -   <span data-ttu-id="69ac3-227">必要に応じて [、 `AppService` この](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) 時点でバックグラウンド タスクとしてではなくメイン アプリでホストされる構成を行います。</span><span class="sxs-lookup"><span data-stu-id="69ac3-227">You can optionally [configure `AppService` to be hosted in the main app](https://msdn.microsoft.com/windows/uwp/launch-resume/convert-app-service-in-process) instead of as a background task at this point.</span></span>
3.  <span data-ttu-id="69ac3-228">UWP プロジェクトをビルドしてテストします。</span><span class="sxs-lookup"><span data-stu-id="69ac3-228">Build and test your UWP project.</span></span>
    -   <span data-ttu-id="69ac3-229">必要に応じて、デスクトップ ブリッジ [コンポーネントを追加できます](#adding-a-desktop-bridge-component)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-229">You can optionally add a [Desktop Bridge component](#adding-a-desktop-bridge-component).</span></span>
4.  <span data-ttu-id="69ac3-230">ネイティブ メッセージングを使用して UWP コンパニオン アプリと通信する Microsoft Edge 拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-230">Create a Microsoft Edge extension that uses native messaging to communicate with the UWP companion app.</span></span> <span data-ttu-id="69ac3-231">拡張ファイルは、UWP プロジェクトで指定された `Extension` フォルダーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-231">The extension files can be added into a folder named `Extension` in the UWP project.</span></span> <span data-ttu-id="69ac3-232">サブフォルダーを含む、このフォルダーの下のすべてのファイルは、それらのプロパティを構成する必要 `Build Action=Content` があります `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-232">All of the files underneath this folder, including subfolders, need to have their properties configured such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span> <span data-ttu-id="69ac3-233">これらのプロパティ `manifest.json` も構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-233">Make sure `manifest.json` is also configured with these properties.</span></span>
5.  <span data-ttu-id="69ac3-234">プロジェクト内のファイルを変更して拡張機能のメタデータを含め、以下を追加してヘッドレス `package.manifest.xml` アプリに変換します `AppListEntry="none"` 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-234">Modify the `package.manifest.xml` file in the project to include extension metadata and convert it to a headless app by adding `AppListEntry="none"`:</span></span>
    
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
    
6.  <span data-ttu-id="69ac3-235">ネイティブ メッセージング `AppService` API で UWP 用に構成された名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-235">Use the `AppService` name configured for the UWP in the native messaging APIs.</span></span>
7.  <span data-ttu-id="69ac3-236">UWP [プロジェクトを](#deploying) ビルドして展開します (オプションのデスクトップ ブリッジ コンポーネントを使用)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-236">Build and [deploy](#deploying) the UWP project (with the optional Desktop Bridge component).</span></span>
8.  <span data-ttu-id="69ac3-237">[ストア](#packaging) 申請の準備ができたら、ネイティブ メッセージング拡張機能をパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="69ac3-237">[Package](#packaging) your native messaging extension once it's ready for Store submission</span></span>
    
> [!NOTE]
> <span data-ttu-id="69ac3-238">完全な [ネイティブ メッセージング拡張機能](#demos) の例については、「Demos」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-238">Reference the [Demos](#demos) section for an example of a complete native messaging extension.</span></span>

## <span data-ttu-id="69ac3-239">デスクトップ ブリッジ コンポーネントの追加</span><span class="sxs-lookup"><span data-stu-id="69ac3-239">Adding a Desktop Bridge component</span></span> 
<span data-ttu-id="69ac3-240">デスクトップ ブリッジ コンポーネントをパッケージに追加する場合は、Win32 プロジェクトを作成してビルドする必要Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="69ac3-240">If you want to add a Desktop Bridge component to your package, you'll need to create and build your Win32 project in Visual Studio.</span></span> <span data-ttu-id="69ac3-241">win32 アプリを UWP に変換する方法について詳しくは、「デスクトップ ブリッジを使った [Windows 10](/windows/uwp/porting/desktop-to-uwp-root)へのアプリの移植」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-241">For info on how to convert your win32 app to UWP, see [Porting apps to Windows 10 via Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).</span></span> <span data-ttu-id="69ac3-242">組み込みVisual Studio、次の手順を実行して、Win32 実行可能ファイルをパッケージに追加できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-242">Once built in Visual Studio, you can add the Win32 executable to the package by doing the following steps:</span></span>

1.  <span data-ttu-id="69ac3-243">Win32 プロジェクトを UWP プロジェクトと同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-243">Add the Win32 project to the same solution as the UWP project.</span></span> 
2.  <span data-ttu-id="69ac3-244">Win32 プロジェクトを UWP プロジェクトの依存プロジェクトとして設定します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-244">Set the Win32 project as a dependent project for the UWP project:</span></span>
    
    ![プロジェクトの依存関係の設定](./../media/project-dependencies.PNG)
    
3.  <span data-ttu-id="69ac3-246">`Win32`UWP プロジェクト内にフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-246">Create a `Win32` folder within the UWP project.</span></span> <span data-ttu-id="69ac3-247">プロジェクトに必要なバイナリを `Win32` このフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="69ac3-247">Copy the necessary binaries for the `Win32` project to this folder.</span></span> <span data-ttu-id="69ac3-248">すべてのバイナリのプロパティを構成します `Build Action=Content` `Copy to Output Directory=Copy Always` 。</span><span class="sxs-lookup"><span data-stu-id="69ac3-248">Configure the properties of all the binaries such that `Build Action=Content` and `Copy to Output Directory=Copy Always`.</span></span>
    
    ![フォルダーに win32 と UWP アプリ ファイルがある](./../media/desktop-bridge.png)
    
4.  <span data-ttu-id="69ac3-250">PostBuild イベント コマンドを使用して、UWP プロジェクト ファイルを変更して、プロジェクトに必要なすべてのバイナリをこの `Win32` フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="69ac3-250">Modify the UWP project file to copy all the necessary binaries for the `Win32` project into this folder using PostBuild event command.</span></span> <span data-ttu-id="69ac3-251">これにより、ソリューションが再構築されるたび、更新されたバイナリがフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-251">This ensures that the updated binaries are being copied to the folder every time the solution is rebuilt.</span></span>
    
    ```xml
    <Target Name="AfterBuild">
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.exe.config" DestinationFolder="win32" />
    <Copy SourceFiles="..\PasswordInputProtection\bin\$(Configuration)\PasswordInputProtection.pdb" DestinationFolder="win32" />
    </Target>
    ```
    
5.  <span data-ttu-id="69ac3-252">要素 `package.manifest.xml` に要素を `<desktop:Extension>` 追加して変更 `<Extensions>` します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-252">Modify `package.manifest.xml` by adding the `<desktop:Extension>` element to the `<Extensions>` element:</span></span>
    
    ```xml
    <Extensions>
    <desktop:Extension Category="windows.fullTrustProcess"Executable="Win32\PasswordInputProtection.exe"
    xmlns:desktop="http://schemas.microsoft.com/appx/manifest/desktop/windows10" />
    </Extensions>
    ```
    
## <span data-ttu-id="69ac3-253">展開</span><span class="sxs-lookup"><span data-stu-id="69ac3-253">Deploying</span></span>
<span data-ttu-id="69ac3-254">上記で説明したように UWP プロジェクト (およびオプションで Win32 プロジェクト) を構成したら、次の手順を使用してソリューションを展開Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="69ac3-254">Once you have configured your UWP project (and optionally Win32 project) as outlined above, you are ready to deploy the solution using Visual Studio.</span></span>

![ビルド inprocess プロジェクト](../media/native-message-uwp-debug.PNG)

<span data-ttu-id="69ac3-256">ソリューションを正しく展開すると、Microsoft Edge に拡張機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-256">Once the solution is correctly deployed, you should see your extension in Microsoft Edge.</span></span>

![Microsoft Edge に表示される拡張機能](../media/secureextension.png)

## <span data-ttu-id="69ac3-258">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="69ac3-258">Packaging</span></span>

> [!NOTE]
> <span data-ttu-id="69ac3-259">Microsoft Store に Microsoft Edge 拡張機能を提出する機能は、現在制限されています。</span><span class="sxs-lookup"><span data-stu-id="69ac3-259">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="69ac3-260">Microsoft Store[の一](https://aka.ms/extension-request)部としてお客様からのリクエストをお問い合わせください。今後の更新について検討します。</span><span class="sxs-lookup"><span data-stu-id="69ac3-260">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we'll consider you for a future update.</span></span>

<span data-ttu-id="69ac3-261">Windows デベロッパー センターへの申請用にストア パッケージを生成するには、次の組み込みのVisual Studioできます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-261">You can generate a Store package for submission to the Windows Dev Center using built-in Visual Studio functionality:</span></span>

![ストア パッケージの作成](../media/create-store-package.PNG)

## <span data-ttu-id="69ac3-263">デバッグ</span><span class="sxs-lookup"><span data-stu-id="69ac3-263">Debugging</span></span>
<span data-ttu-id="69ac3-264">デバッグの手順は、テストするコンポーネントによって異なります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-264">The instructions for debugging vary depending on which component you want to test out:</span></span>

### <span data-ttu-id="69ac3-265">拡張機能のデバッグ</span><span class="sxs-lookup"><span data-stu-id="69ac3-265">Debugging the extension</span></span>
<span data-ttu-id="69ac3-266">ソリューションを展開すると、拡張機能が Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-266">Once the solution is deployed, the extension will be installed in Microsoft Edge.</span></span> <span data-ttu-id="69ac3-267">拡張機能をデバッグ [する](./debugging-extensions.md) 方法については、デバッグ ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-267">Check out the [Debugging](./debugging-extensions.md) guide for info on how to debug an extension.</span></span>


### <span data-ttu-id="69ac3-268">UWP アプリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="69ac3-268">Debugging the UWP app</span></span>
<span data-ttu-id="69ac3-269">拡張機能がネイティブ メッセージング API を使用して接続しようとすると、UWP アプリ [が起動します](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative)。</span><span class="sxs-lookup"><span data-stu-id="69ac3-269">The UWP app will launch when the extension tries to connect to it using [native messaging APIs](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative).</span></span> <span data-ttu-id="69ac3-270">プロセスが開始された後にのみ、UWP アプリをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ac3-270">You'll need to debug the UWP app only once the process starts.</span></span> <span data-ttu-id="69ac3-271">これは、プロジェクトの [プロパティ] ページから構成できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-271">This can be configured via the project's Property page:</span></span>

1.  <span data-ttu-id="69ac3-272">次Visual Studio、UWP アプリ プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="69ac3-272">In Visual Studio, right click your UWP app project</span></span>
2.  <span data-ttu-id="69ac3-273">プロパティの選択</span><span class="sxs-lookup"><span data-stu-id="69ac3-273">Select Properties</span></span>
3.  <span data-ttu-id="69ac3-274">[起動しないが、起動時にコードをデバッグする] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="69ac3-274">Check "Do not launch, but debug my code when it starts"</span></span>
    
    ![[起動しない] ボックスを選択する](../media/native-message-do-not-launch.png)
    
<span data-ttu-id="69ac3-276">このVisual Studio、デバッグするコードにブレークポイントを設定し、F5 キーを押してデバッガーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-276">In Visual Studio you can now set breakpoints in the code where you want to debug, then launch the debugger by pressing F5.</span></span> <span data-ttu-id="69ac3-277">拡張機能を操作して UWP アプリに接続すると、Visual Studioプロセスに自動的にアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-277">Once you interact with the extension to connect to the UWP app, Visual Studio will automatically attach to the process.</span></span>

### <span data-ttu-id="69ac3-278">デスクトップ ブリッジのデバッグ</span><span class="sxs-lookup"><span data-stu-id="69ac3-278">Debugging the Desktop Bridge</span></span>
<span data-ttu-id="69ac3-279">デスクトップ ブリッジ [(変換](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) された Win32 アプリ) をデバッグする方法はさまざまな場合でも、このシナリオに該当する唯一の方法は PLMDebug オプションです。</span><span class="sxs-lookup"><span data-stu-id="69ac3-279">Even though there are various [methods for debugging a Desktop Bridge](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-debug) (converted Win32 app), the only one applicable for this scenarios is the PLMDebug option.</span></span> <span data-ttu-id="69ac3-280">また、デバッグ コードをスタートアップ関数に追加して、特定の時間の待機時間を実行し、プロセスにVisual Studioを追加できます。</span><span class="sxs-lookup"><span data-stu-id="69ac3-280">You could also add debugging code to the startup function to perform a wait for a specific time, allowing you to attach Visual Studio to the process.</span></span>
