---
description: ネイティブメッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/06/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: c5da9acf79225c88ad5829c2b7f57d1d833ca49b
ms.sourcegitcommit: 75c200a029d19fe372c1505c0006dbfbfad90bf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100253"
---
# <span data-ttu-id="cb6ca-104">ネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="cb6ca-104">Native messaging</span></span>  

<span data-ttu-id="cb6ca-105">拡張機能は、メッセージパッシング Api を使って、ユーザーのデバイスにインストールされているネイティブ Win32 アプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-105">Extensions communicate with a native Win32 application installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="cb6ca-106">ネイティブのアプリケーションホストは、標準の入力と標準の出力を使って、拡張機能を使ってメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-106">The native application host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="cb6ca-107">ネイティブメッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="cb6ca-108">ただし、ネイティブアプリケーションは Microsoft Edge でインストールまたは管理されません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="cb6ca-109">拡張機能とネイティブアプリケーションホストを取得するには、2つの配布モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-109">To acquire the extension and native application host, you have two distribution models.</span></span>  

*   <span data-ttu-id="cb6ca-110">拡張機能とホストをまとめてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-110">Package your extension and the host together.</span></span>  <span data-ttu-id="cb6ca-111">ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-111">When a user installs the package, both the extension and the host are installed.</span></span>
*   <span data-ttu-id="cb6ca-112">[Microsoft Edge アドオンストア][EdgeAddons]を使用して拡張機能をインストールすると、拡張機能により、ユーザーにホストをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-112">Install your extension using the [Microsoft Edge Add-ons store][EdgeAddons], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="cb6ca-113">ネイティブアプリケーションホストでメッセージを送受信するための拡張機能を作成するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-113">To create your extension to send and receive messages with native application hosts, refer to the following steps.</span></span>  

## <span data-ttu-id="cb6ca-114">手順 1-拡張機能マニフェストにアクセス許可を追加する</span><span class="sxs-lookup"><span data-stu-id="cb6ca-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="cb6ca-115">`nativeMessaging`拡張子のファイルの**manifest.js**にアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="cb6ca-116">次のコードスニペットは、 **manifest.js**の例です。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-116">The following code snippet is an example of **manifest.json**.</span></span>  

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

## <span data-ttu-id="cb6ca-117">手順 2-ネイティブメッセージングホストマニフェストファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cb6ca-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="cb6ca-118">ネイティブアプリケーションでは、ネイティブメッセージングホストマニフェストファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-118">Native applications must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="cb6ca-119">マニフェストファイルには、ネイティブメッセージングホストランタイムへのパス、拡張機能との通信方法、および通信先として使用できる拡張機能の一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-119">The manifest file contains the path to the native messaging host runtime, the method of communication with the extension, and a list of allowed extensions to which it communicates.</span></span>  <span data-ttu-id="cb6ca-120">ブラウザーは、ネイティブのメッセージングホストマニフェストを読み取り、検証します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-120">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="cb6ca-121">ブラウザーは、ネイティブメッセージングホストマニフェストファイルをインストールまたは管理しません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-121">The browser does not install or manage the native messaging host manifest file.</span></span>  

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

<span data-ttu-id="cb6ca-122">ホストマニフェストファイルは、次のキーを含む有効な JSON ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-122">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6ca-123">ネイティブメッセージングホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-123">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="cb6ca-124">クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-124">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="cb6ca-125">この値には、小文字の英数字、アンダースコア、ドットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-125">This value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="cb6ca-126">この値は、先頭と末尾以外のドットで指定する必要があります。ドットの後に別のドットを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-126">This value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6ca-127">アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-127">Describes the application.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6ca-128">ネイティブメッセージングホストバイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-128">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="cb6ca-129">Windows デバイスでは、マニフェストファイルを含むディレクトリへの相対パスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-129">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="cb6ca-130">MacOS と Linux では、パスは絶対パスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-130">On macOS and Linux, the path must be absolute.</span></span>  
      
      <span data-ttu-id="cb6ca-131">ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-131">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="cb6ca-132">たとえば、\ (Windows \) では、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリ \ (\) を使ってバイナリが開始され `C:\Application\` ます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-132">For example \(Windows\), if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory \(`C:\Application\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6ca-133">ネイティブメッセージングホストとの通信に使用されるインターフェイスの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-133">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="cb6ca-134">この値は、Microsoft Edge がホストとの通信を行うために使用することを指示 `stdin` し `stdout` ます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-134">This value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="cb6ca-135">指定できる値は、だけ `stdio` です。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-135">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6ca-136">ネイティブメッセージングホストにアクセスできる拡張子の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-136">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="cb6ca-137">アプリケーションで拡張機能を認識して通信できるようにするには、ネイティブメッセージングホストマニフェストファイルで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-137">To enable your application to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="cb6ca-138">ホストとのネイティブメッセージングをテストするために拡張機能をサイドローディングします。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-138">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="cb6ca-139">開発中に拡張機能をサイドローディングして取得するには `microsoft_catalog_extension_id` 、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-139">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following steps.</span></span>  

1.  <span data-ttu-id="cb6ca-140">に移動し `edge://extensions` て、[開発者モード] トグルボタンをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-140">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="cb6ca-141">[ **アンパックの読み込み**] を選択し、サイドローディングに拡張パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-141">Choose **Load unpacked**, and then select your extension package to sideload.</span></span>  
1.  <span data-ttu-id="cb6ca-142">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-142">Choose **OK**.</span></span>
1.  <span data-ttu-id="cb6ca-143">ページに移動して、 `edge://extensions` 拡張子が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-143">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="cb6ca-144">`microsoft_catalog_extension_id`ページの内線番号リストからキーを \ (ID) からコピーします。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-144">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>

<span data-ttu-id="cb6ca-145">内線番号をユーザーに配布する準備ができたら、Microsoft Edge のアドオンストアに拡張機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-145">When you are ready to distribute your extension to users, publish your extension to the Microsoft Edge add-ons store.</span></span>  <span data-ttu-id="cb6ca-146">公開された拡張機能の拡張 ID は、拡張機能のサイドローディング時に使用した ID とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-146">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="cb6ca-147">ID が変更された場合は、公開された `allowed_origins` 拡張機能の id でホストマニフェストファイル内で更新します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-147">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <span data-ttu-id="cb6ca-148">手順 3-ネイティブのメッセージングホストマニフェストファイルをシステムにコピーする</span><span class="sxs-lookup"><span data-stu-id="cb6ca-148">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="cb6ca-149">最後の手順では、ネイティブのメッセージングホストマニフェストファイルをコンピューターにコピーし、正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-149">The final step involves copying the native messaging host manifest file to your computer, and ensuring it is configured correctly.</span></span>  <span data-ttu-id="cb6ca-150">マニフェストファイルが予期した場所に配置されるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-150">To ensure your manifest file is placed in the expected location, complete the following the steps.</span></span>  <span data-ttu-id="cb6ca-151">場所はプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-151">The location varies by platform.</span></span>  

### [<span data-ttu-id="cb6ca-152">Windows</span><span class="sxs-lookup"><span data-stu-id="cb6ca-152">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="cb6ca-153">マニフェストファイルは、ファイルシステム内の任意の場所に配置されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-153">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="cb6ca-154">アプリケーションのインストーラーでは、レジストリキーを作成し、そのキーの既定値をマニフェストファイルの完全パスに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-154">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span>  <span data-ttu-id="cb6ca-155">次のコマンドは、レジストリキーの例です。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-155">The following commands are examples of registry keys.</span></span>  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

<span data-ttu-id="cb6ca-156">マニフェストキーを使ってディレクトリにレジストリキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-156">To add a registry key to the directory with the manifest key.</span></span>  

*   <span data-ttu-id="cb6ca-157">コマンドプロンプトでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-157">Run command in command prompt.</span></span>    
    
    1.  <span data-ttu-id="cb6ca-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-158">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   <span data-ttu-id="cb6ca-159">ファイルを作成 `.reg` して実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-159">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="cb6ca-160">次のコマンドをファイルにコピー `.reg` します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-160">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="cb6ca-161">ファイルを実行 `.reg` します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-161">Run the `.reg` file.</span></span>  
    
<span data-ttu-id="cb6ca-162">Microsoft Edge では、最初に32ビットレジストリが照会され、次に64ビットレジストリによってネイティブメッセージングホストが識別されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-162">Microsoft Edge queries the 32-bit registry first, and then the 64-bit registry to identify native messaging hosts.</span></span>  <span data-ttu-id="cb6ca-163">上記 `.reg` のファイルをバッチスクリプトの一部として実行する場合は、管理者のコマンドプロンプトを使用して実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-163">If you run the above `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>  

### [<span data-ttu-id="cb6ca-164">macOS</span><span class="sxs-lookup"><span data-stu-id="cb6ca-164">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="cb6ca-165">マニフェストファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-165">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="cb6ca-166">すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-166">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="cb6ca-167">たとえば、マニフェストファイルは、次の場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-167">For example, the manifest file must be stored in following location.</span></span> 
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   <span data-ttu-id="cb6ca-168">現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、 `NativeMessagingHosts` ユーザープロファイルディレクトリのサブディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-168">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="cb6ca-169">たとえば、マニフェストファイルは、次の場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-169">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    <span data-ttu-id="cb6ca-170">In は、  `{Channel_Name}` `Microsoft Edge {Channel_Name}` 次のいずれかの値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-170">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   <span data-ttu-id="cb6ca-171">Canary</span><span class="sxs-lookup"><span data-stu-id="cb6ca-171">Canary</span></span>  
    *   <span data-ttu-id="cb6ca-172">Dev</span><span class="sxs-lookup"><span data-stu-id="cb6ca-172">Dev</span></span>  
    *   <span data-ttu-id="cb6ca-173">Beta</span><span class="sxs-lookup"><span data-stu-id="cb6ca-173">Beta</span></span>  

    <span data-ttu-id="cb6ca-174">安定したチャネルを使用する場合 `{Channel_Name}` は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-174">When using the Stable channel, `{Channel_Name}` is not required.</span></span>  

### [<span data-ttu-id="cb6ca-175">Linux</span><span class="sxs-lookup"><span data-stu-id="cb6ca-175">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="cb6ca-176">マニフェストファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-176">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="cb6ca-177">すべてのユーザーが使用できるシステム全体のネイティブメッセージングホストは、固定された場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-177">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="cb6ca-178">マニフェストファイルは、次の場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-178">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="cb6ca-179">現在のユーザーのみが利用できる、ユーザー固有のネイティブメッセージホストは、 `NativeMessagingHosts` ユーザープロファイルディレクトリのサブディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-179">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="cb6ca-180">マニフェストファイルは、次の場所に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-180">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> <span data-ttu-id="cb6ca-181">マニフェストファイルで読み取りアクセス許可を指定し、ホストランタイムでアクセス許可を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-181">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="cb6ca-182">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cb6ca-183">元のページは [ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-183">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cb6ca-185">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
