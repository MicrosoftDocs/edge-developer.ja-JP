---
description: ネイティブメッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 9d33fc4e8c9449d539b6ea82cca87c3aad4d564e
ms.sourcegitcommit: 39636248d0266730089aa2e57b9cf04d9feb363d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088556"
---
# <span data-ttu-id="dd640-104">ネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="dd640-104">Native messaging</span></span>  

<span data-ttu-id="dd640-105">拡張機能は、メッセージパッシング Api を使って、ユーザーのデバイスにインストールされているネイティブ Win32 アプリケーションと通信できます。</span><span class="sxs-lookup"><span data-stu-id="dd640-105">Extensions can communicate with a native Win32 application installed on a user’s device using message passing APIs.</span></span> <span data-ttu-id="dd640-106">ネイティブのアプリケーションホストでは、標準の入力と標準の出力を使って、拡張機能を使ってメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="dd640-106">The native application host can send and receive messages with extensions using standard input and standard output.</span></span> <span data-ttu-id="dd640-107">ネイティブメッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dd640-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span> <span data-ttu-id="dd640-108">ただし、ネイティブアプリケーションは Microsoft Edge でインストールまたは管理されません。</span><span class="sxs-lookup"><span data-stu-id="dd640-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>

<span data-ttu-id="dd640-109">拡張機能とネイティブアプリケーションホストを取得するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd640-109">To acquire the extension and native application host, you can:</span></span>

1. <span data-ttu-id="dd640-110">拡張機能とホストをまとめてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="dd640-110">Package the extension and the host together.</span></span> <span data-ttu-id="dd640-111">ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dd640-111">When users install the package, both the extension and the host are installed.</span></span>
1. <span data-ttu-id="dd640-112">[Microsoft Edge][EdgeAddons]のアドオンストアから拡張機能をインストールし、拡張機能によって、ホストのインストールをユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="dd640-112">Install the extension from the [Microsoft Edge Add-ons store][EdgeAddons], and have your extension prompt users to install the host.</span></span> 

<span data-ttu-id="dd640-113">ネイティブアプリケーションホストでメッセージを送受信するための拡張機能を設定するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd640-113">Refer to the steps below to setup your extension to send and receive messages with native application hosts.</span></span>

### <span data-ttu-id="dd640-114">手順 1: 拡張機能マニフェストにアクセス許可を追加する</span><span class="sxs-lookup"><span data-stu-id="dd640-114">Step 1: Add permissions to the extension manifest</span></span>

<span data-ttu-id="dd640-115">ファイルの拡張機能の **manifest.js** に nativeMessaging 権限を追加します。</span><span class="sxs-lookup"><span data-stu-id="dd640-115">Add the nativeMessaging permission to the extension’s **manifest.json** file.</span></span> <span data-ttu-id="dd640-116">次に、manifest.jsの例を示します。</span><span class="sxs-lookup"><span data-stu-id="dd640-116">Below is an example of manifest.json:</span></span>

```json
    {
          "name": "Native Messaging Example",
          "version": "1.0",
          "manifest_version": 2, 
          "description": "Send a message to a native application.",
          "app": { 
              "launch": { 
                  "local_path": "main.html" } 
                 }, 
          "icons": { 
              "128": "icon-128.png"}, 
          "permissions": ["nativeMessaging"] 
    }
```

### <span data-ttu-id="dd640-117">手順 2: ネイティブメッセージングホストマニフェストファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="dd640-117">Step 2: Create your native messaging host manifest file</span></span>
    
<span data-ttu-id="dd640-118">ネイティブアプリケーションでは、ネイティブメッセージングホストマニフェストファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-118">Native applications must provide a native messaging host manifest file.</span></span> <span data-ttu-id="dd640-119">このマニフェストファイルには、ネイティブメッセージングホストの実行可能ファイルへのパス、拡張機能との通信方法、および通信できる許可された拡張機能の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd640-119">This manifest file contains the path to the native messaging host executable, the method of communication with the extension, and a list of allowed extensions it can communicate with.</span></span> <span data-ttu-id="dd640-120">ブラウザーはネイティブメッセージングホストマニフェストを読み取り、検証しますが、ブラウザーによってインストールまたは管理されることはありません。</span><span class="sxs-lookup"><span data-stu-id="dd640-120">Browsers read and validate the native messaging host manifest, but it’s never installed or managed by the browser.</span></span> <span data-ttu-id="dd640-121">ホストマニフェストファイルは、次のフィールドを含む有効な json ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-121">The host manifest file must be a valid json file containing the following fields.</span></span>

    
```json
    {
        "name": "com.my_company.my_application",
        "description": "My Application",
        "path": "C:\\Program Files\\My Application\\chrome_native_messaging_host.exe",
        "type": "stdio",
        "allowed_origins": [
            "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
        ]
    }
```  




| <span data-ttu-id="dd640-122">名前</span><span class="sxs-lookup"><span data-stu-id="dd640-122">Name</span></span> | <span data-ttu-id="dd640-123">説明</span><span class="sxs-lookup"><span data-stu-id="dd640-123">Description</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="dd640-124">ネイティブメッセージングホストの名前。</span><span class="sxs-lookup"><span data-stu-id="dd640-124">Name of the native messaging host.</span></span> <span data-ttu-id="dd640-125">クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="dd640-125">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  <span data-ttu-id="dd640-126">この名前には、小文字の英数字、アンダースコア、ドットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-126">This name must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  <span data-ttu-id="dd640-127">名前の先頭または末尾にドットを使用することはできません。ドットの後に別のドットを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="dd640-127">The name must not start or end with a dot, and a dot must not be followed by another dot.</span></span> |  
| `description` | <span data-ttu-id="dd640-128">アプリケーションの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="dd640-128">Brief description of the application.</span></span> |  
| `path` | <span data-ttu-id="dd640-129">ネイティブメッセージングホストバイナリへのパス。</span><span class="sxs-lookup"><span data-stu-id="dd640-129">Path to the native messaging host binary.</span></span> <span data-ttu-id="dd640-130">Windows デバイスでは、マニフェストファイルを含むディレクトリへの相対パスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd640-130">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span> <span data-ttu-id="dd640-131">MacOS と Linux では、パスは絶対パスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-131">On macOS and Linux, the path must be absolute.</span></span> <span data-ttu-id="dd640-132">ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。</span><span class="sxs-lookup"><span data-stu-id="dd640-132">The host process is started with the current directory set to the directory that contains the host binary.</span></span> <span data-ttu-id="dd640-133">たとえば、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリを使ってバイナリが開始され `C:\Application\` ます。</span><span class="sxs-lookup"><span data-stu-id="dd640-133">For example, if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory `C:\Application\`.</span></span> |  
| `type` | <span data-ttu-id="dd640-134">ネイティブメッセージングホストとの通信に使用されるインターフェイスの種類。</span><span class="sxs-lookup"><span data-stu-id="dd640-134">Type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="dd640-135">現在、このパラメーターに指定できる値は1つだけ `stdio` です。</span><span class="sxs-lookup"><span data-stu-id="dd640-135">Currently there's only one possible value for this parameter: `stdio`.</span></span>  <span data-ttu-id="dd640-136">この値は、Microsoft Edge がホストとの通信に使用することを示し `stdin` `stdout` ます。</span><span class="sxs-lookup"><span data-stu-id="dd640-136">This value indicates that Microsoft Edge should use `stdin` and `stdout` to communicate with the host.</span></span> |  
| `allowed_origins` |  <span data-ttu-id="dd640-137">ネイティブメッセージングホストにアクセスできる拡張機能の一覧です。</span><span class="sxs-lookup"><span data-stu-id="dd640-137">List of extensions that may have access to the native messaging host.</span></span>  <span data-ttu-id="dd640-138">アプリケーションで拡張機能を識別して通信できるようにするには、 `allowed_origins` `chrome-extension://[Microsoft-Catalog-extensionID]` ネイティブメッセージングホストマニフェストファイルにを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd640-138">To enable your application to identify and communicate with an extension, set `allowed_origins` to `chrome-extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span> |  


<span data-ttu-id="dd640-139">開発中に、拡張機能をサイドローディングして、ホストとのネイティブメッセージングをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd640-139">While developing, you can sideload your extension to test native messaging with the host by:</span></span>
1. <span data-ttu-id="dd640-140">に移動 `edge://extensions` して、[開発者モード] のトグルボタンをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dd640-140">Navigating to `edge://extensions`, and then turning on the Developer mode toggle button.</span></span> 
1. <span data-ttu-id="dd640-141">[アンパックの読み込み] を選択し、サイドローディングに拡張パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="dd640-141">Choose Load unpacked, and then select your extension package to sideload.</span></span>  
1. <span data-ttu-id="dd640-142">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd640-142">Choose OK.</span></span>
1. <span data-ttu-id="dd640-143">ページに `edge://extensions` 拡張機能の一覧が表示されるようになったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd640-143">Verify the `edge://extensions` page now lists your extension.</span></span> 
1. <span data-ttu-id="dd640-144">ページの内線番号リストからキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dd640-144">Copy the key from ID from the extension listing on the page.</span></span>

<span data-ttu-id="dd640-145">内線番号をユーザーに配布する準備ができたら、Microsoft Edge のアドオンストアに拡張機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="dd640-145">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge add-ons store.</span></span> <span data-ttu-id="dd640-146">公開された拡張機能の拡張 ID は、サイドローディングの拡張機能で使用される ID と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-146">The extension ID of the published extension may be different to the ID used while sideloading your extension.</span></span> <span data-ttu-id="dd640-147">ID が変更された場合は、公開された `allowed_origins` 拡張機能の id でホストマニフェストファイル内で更新します。</span><span class="sxs-lookup"><span data-stu-id="dd640-147">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span> 



### <span data-ttu-id="dd640-148">手順 3: ネイティブメッセージングホストマニフェストファイルをシステムにコピーする</span><span class="sxs-lookup"><span data-stu-id="dd640-148">Step 3: Copy the native messaging host manifest file to your system</span></span>

<span data-ttu-id="dd640-149">最後の手順では、ネイティブのメッセージングホストマニフェストファイルをコンピューターにコピーし、正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd640-149">The final step involves copying the native messaging host manifest file to your computer, and ensuring it’s configured correctly.</span></span> <span data-ttu-id="dd640-150">プラットフォームによって異なるため、ネイティブメッセージングホストファイルが予期した場所に配置されるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd640-150">Follow the steps below to ensure the native messaging host file is placed in the expected location because it varies by platform.</span></span>
    
<span data-ttu-id="dd640-151">**Windows**。</span><span class="sxs-lookup"><span data-stu-id="dd640-151">**Windows**.</span></span> <span data-ttu-id="dd640-152">マニフェストファイルは、ファイルシステム内の任意の場所に配置されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-152">The manifest file may be located anywhere in the file system.</span></span> <span data-ttu-id="dd640-153">アプリケーションのインストーラーでは、レジストリキーを作成し、そのキーの既定値をマニフェストファイルの完全パスに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-153">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span> <span data-ttu-id="dd640-154">次のコマンドは、レジストリキーの例です。</span><span class="sxs-lookup"><span data-stu-id="dd640-154">The following commands are examples of registry keys.</span></span>
    
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    <span data-ttu-id="dd640-155">または</span><span class="sxs-lookup"><span data-stu-id="dd640-155">or</span></span>  
`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`<span data-ttu-id="dd640-156">,</span><span class="sxs-lookup"><span data-stu-id="dd640-156">,</span></span>  
    
<span data-ttu-id="dd640-157">コマンドプロンプトで次のコマンドを実行して、マニフェストファイルを含むフォルダーにレジストリキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd640-157">Run the following command at a command prompt to add a registry key to the folder with the manifest file.</span></span>
    
```shell
REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
```  
    
<span data-ttu-id="dd640-158">または、次のコマンドを .reg ファイルにコピーして実行し、レジストリキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd640-158">Alternatively, copy the following command to a .reg file and run it to add the registry key.</span></span> 
    
```shell
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
@="C:\\path\\to\\nmh-manifest.json"
``` 

  <span data-ttu-id="dd640-159">Microsoft Edge では、最初に32ビットレジストリが照会され、次に64ビットレジストリによってネイティブメッセージングホストが識別されます。</span><span class="sxs-lookup"><span data-stu-id="dd640-159">Microsoft Edge queries the 32-bit registry first, and then the 64-bit registry to identify native messaging hosts.</span></span> <span data-ttu-id="dd640-160">上記の .reg ファイルをバッチスクリプトの一部として実行する場合は、管理者のコマンドプロンプトを使用して実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd640-160">If you run the above .reg file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>


<span data-ttu-id="dd640-161">**macOS**。</span><span class="sxs-lookup"><span data-stu-id="dd640-161">**macOS**.</span></span> <span data-ttu-id="dd640-162">マニフェストファイルは、次のように保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-162">The manifest file must be stored as follows:</span></span>

1. <span data-ttu-id="dd640-163">すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="dd640-163">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span> <span data-ttu-id="dd640-164">たとえば、マニフェストファイルが保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-164">For example, the manifest file must be stored in</span></span> `/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`

1. <span data-ttu-id="dd640-165">現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、ユーザープロファイルディレクトリの NativeMessagingHosts サブディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="dd640-165">User-specific native messaging hosts, which are available to the current user only, are located in the NativeMessagingHosts  subdirectory in the user profile directory.</span></span> <span data-ttu-id="dd640-166">たとえば、マニフェストファイルが保存されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-166">For example, the manifest file must be stored in</span></span>  
    `~/Library/Application Support/Microsoft Edge <ChannelName>/NativeMessagingHosts/com.my_company.my_application.json`

    <span data-ttu-id="dd640-167">は `ChannelName` 、カナリア、Dev、またはβです。</span><span class="sxs-lookup"><span data-stu-id="dd640-167">where `ChannelName` may be Canary, Dev, or Beta.</span></span> <span data-ttu-id="dd640-168">安定したチャネルを使用する場合は、必須では `ChannelName` ありません。</span><span class="sxs-lookup"><span data-stu-id="dd640-168">When using the Stable channel, `ChannelName` isn't required.</span></span>


<span data-ttu-id="dd640-169">**Linux** マニフェストファイルは、次のように保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd640-169">**Linux** The manifest file must be stored as follows:</span></span>

1. <span data-ttu-id="dd640-170">システム全体のネイティブメッセージングホスト:  `~/.config/microsoft-edge/NativeMessagingHosts`</span><span class="sxs-lookup"><span data-stu-id="dd640-170">System-wide native messaging hosts:  `~/.config/microsoft-edge/NativeMessagingHosts`</span></span>

1. <span data-ttu-id="dd640-171">ユーザー固有のネイティブメッセージホスト:  `/etc/opt/edge/native-messaging-hosts`</span><span class="sxs-lookup"><span data-stu-id="dd640-171">User-specific native messaging hosts:  `/etc/opt/edge/native-messaging-hosts`</span></span>


> [!NOTE]
> <span data-ttu-id="dd640-172">マニフェストファイルで読み取りアクセス許可を指定し、ホストの実行可能ファイルでアクセス許可を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd640-172">Ensure that you provide read permissions on the manifest file, and execute permissions on the host executable.</span></span>


> [!NOTE]
> <span data-ttu-id="dd640-173">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd640-173">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dd640-174">元のページは [ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。</span><span class="sxs-lookup"><span data-stu-id="dd640-174">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="dd640-176">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="dd640-176">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- image links -->  

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
