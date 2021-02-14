---
description: ネイティブ メッセージングに関するドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 2d629762d4c7c75832905cfbf8c2d5311191092d
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327702"
---
# <span data-ttu-id="9cb3b-104">ネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="9cb3b-104">Native messaging</span></span>  

<span data-ttu-id="9cb3b-105">拡張機能は、メッセージを渡す API を使用して、ユーザーのデバイスにインストールされているネイティブの Win32 アプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-105">Extensions communicate with a native Win32 application installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="9cb3b-106">ネイティブ アプリケーション ホストは、標準の入力と標準出力を使用して、拡張機能を使用してメッセージを送信および受信します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-106">The native application host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="9cb3b-107">ネイティブ メッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="9cb3b-108">ただし、ネイティブ アプリケーションは Microsoft Edge によってインストールまたは管理されません。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="9cb3b-109">拡張機能とネイティブ アプリケーション ホストを取得するには、2 つの配布モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-109">To acquire the extension and native application host, you have two distribution models.</span></span>  

*   <span data-ttu-id="9cb3b-110">拡張機能とホストを一緒にパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-110">Package your extension and the host together.</span></span>  <span data-ttu-id="9cb3b-111">ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-111">When a user installs the package, both the extension and the host are installed.</span></span>  
*   <span data-ttu-id="9cb3b-112">Microsoft Edge アドオン ストアを [使用して] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]拡張機能をインストールすると、拡張機能によってホストのインストールを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-112">Install your extension using the [Microsoft Edge Add-ons store] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="9cb3b-113">ネイティブ アプリケーション ホストとの間でメッセージを送受信する拡張機能を作成するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-113">To create your extension to send and receive messages with native application hosts, refer to the following steps.</span></span>  

## <span data-ttu-id="9cb3b-114">手順 1 - 拡張機能マニフェストにアクセス許可を追加する</span><span class="sxs-lookup"><span data-stu-id="9cb3b-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="9cb3b-115">拡張子の `nativeMessaging` ファイルのmanifest.js\*\* に\*\* アクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="9cb3b-116">次のコード スニペットは、次に示すmanifest.js\*\* です\*\*。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-116">The following code snippet is an example of **manifest.json**.</span></span>  

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

## <span data-ttu-id="9cb3b-117">手順 2 - ネイティブ メッセージング ホスト マニフェスト ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="9cb3b-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="9cb3b-118">ネイティブ アプリケーションは、ネイティブ のメッセージング ホスト マニフェスト ファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-118">Native applications must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="9cb3b-119">マニフェスト ファイルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-119">The manifest file contains the following information.</span></span>  

*   <span data-ttu-id="9cb3b-120">ネイティブ メッセージング ホスト ランタイムへのパス。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-120">The path to the native messaging host runtime.</span></span>  
*   <span data-ttu-id="9cb3b-121">拡張機能との通信方法。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-121">The method of communication with the extension.</span></span>  
*   <span data-ttu-id="9cb3b-122">通信先の許可された拡張機能の一覧。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-122">A list of allowed extensions to which it communicates.</span></span>  
    
<span data-ttu-id="9cb3b-123">ブラウザーは、ネイティブ メッセージング ホスト マニフェストを読み取って検証します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-123">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="9cb3b-124">ブラウザーは、ネイティブ のメッセージング ホスト マニフェスト ファイルをインストールまたは管理しない。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-124">The browser doesn't install or manage the native messaging host manifest file.</span></span>  

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

<span data-ttu-id="9cb3b-125">ホスト マニフェスト ファイルは、次のキーを含む有効な JSON ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-125">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9cb3b-126">ネイティブ メッセージング ホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-126">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="9cb3b-127">クライアントは、この文字列を渡す、または `runtime.connectNative` `runtime.sendNativeMessage` .</span><span class="sxs-lookup"><span data-stu-id="9cb3b-127">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="9cb3b-128">この値には、小文字の英数字、アンダースコア、ドットのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-128">This value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="9cb3b-129">この値は、ドットで開始または終了し、ドットの後に別のドットを付けずにしてください。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-129">This value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9cb3b-130">アプリケーションを記述します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-130">Describes the application.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9cb3b-131">ネイティブ メッセージング ホスト バイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-131">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="9cb3b-132">Windows デバイスでは、マニフェスト ファイルを含むディレクトリへの相対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-132">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="9cb3b-133">macOS と Linux では、パスは絶対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-133">On macOS and Linux, the path must be absolute.</span></span>  
      
      <span data-ttu-id="9cb3b-134">ホスト プロセスは、ホスト バイナリを含むディレクトリに設定された現在のディレクトリから始まります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-134">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="9cb3b-135">たとえば、\(Windows\) の場合、このパラメーターが設定されている場合、バイナリは現在の `C:\Application\nm_host.exe` ディレクトリ \( \) を使用して `C:\Application\` 開始されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-135">For example \(Windows\), if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory \(`C:\Application\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9cb3b-136">ネイティブ メッセージング ホストとの通信に使用するインターフェイスの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-136">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="9cb3b-137">この値は、Microsoft Edge がホストを使用 `stdin` し、 `stdout` ホストと通信するように指示します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-137">This value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="9cb3b-138">唯一の許容値は次の値です `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-138">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9cb3b-139">ネイティブ メッセージング ホストにアクセスできる拡張機能の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-139">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="9cb3b-140">アプリケーションで拡張機能を識別して通信するには、ネイティブ メッセージング ホスト マニフェスト ファイルで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-140">To enable your application to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9cb3b-141">拡張機能をサイドロードして、ホストとのネイティブ メッセージングをテストします。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-141">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="9cb3b-142">開発中に拡張機能をサイドロードして取得するには、 `microsoft_catalog_extension_id` 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-142">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following steps.</span></span>  

1.  <span data-ttu-id="9cb3b-143">[開発モード `edge://extensions` ] トグル ボタンに移動し、オンにします。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-143">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="9cb3b-144">[ **アンパックの読み込**み] を選択し、サイドロードする拡張機能パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-144">Choose **Load unpacked**, and then select your extension package to sideload.</span></span>  
1.  <span data-ttu-id="9cb3b-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-145">Choose **OK**.</span></span>  
1.  <span data-ttu-id="9cb3b-146">ページに `edge://extensions` 移動し、拡張機能が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-146">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="9cb3b-147">ページの拡張機能の `microsoft_catalog_extension_id` 一覧から \(ID\) からキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-147">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>  

<span data-ttu-id="9cb3b-148">拡張機能をユーザーに配布する準備ができたら、拡張機能を Microsoft Edge アドオン ストアに公開します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-148">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge add-ons store.</span></span>  <span data-ttu-id="9cb3b-149">公開された拡張機能の拡張 ID は、拡張機能のサイドロード中に使用される ID とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-149">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="9cb3b-150">ID が変更された場合は、公開された拡張機能の ID を使用してホスト `allowed_origins` マニフェスト ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-150">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <span data-ttu-id="9cb3b-151">手順 3 - ネイティブ メッセージング ホスト マニフェスト ファイルをシステムにコピーする</span><span class="sxs-lookup"><span data-stu-id="9cb3b-151">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="9cb3b-152">最後の手順では、ネイティブのメッセージング ホスト マニフェスト ファイルをコンピューターにコピーし、マニフェスト ファイルが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-152">The final step involves copying the native messaging host manifest file to your computer, and ensuring the manifest file is correctly configured.</span></span>  <span data-ttu-id="9cb3b-153">マニフェスト ファイルが想定される場所に配置されるのを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-153">To ensure your manifest file is placed in the expected location, complete the following the steps.</span></span>  <span data-ttu-id="9cb3b-154">場所はプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-154">The location varies by platform.</span></span>  

### [<span data-ttu-id="9cb3b-155">Windows</span><span class="sxs-lookup"><span data-stu-id="9cb3b-155">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="9cb3b-156">マニフェスト ファイルは、ファイル システムの任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-156">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="9cb3b-157">アプリケーション インストーラーは、レジストリ キーを作成し、そのキーの既定値をマニフェスト ファイルの完全なパスに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-157">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span>  <span data-ttu-id="9cb3b-158">レジストリ キーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-158">The following commands are examples of registry keys.</span></span>  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

<span data-ttu-id="9cb3b-159">マニフェスト キーを使用してディレクトリにレジストリ キーを追加する。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-159">To add a registry key to the directory with the manifest key.</span></span>  

*   <span data-ttu-id="9cb3b-160">コマンド プロンプトでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-160">Run command in command prompt.</span></span>  
    
    1.  <span data-ttu-id="9cb3b-161">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-161">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   <span data-ttu-id="9cb3b-162">ファイルを `.reg` 作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-162">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="9cb3b-163">次のコマンドをファイルにコピー `.reg` します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-163">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="9cb3b-164">ファイルを実行 `.reg` します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-164">Run the `.reg` file.</span></span>  
    
<span data-ttu-id="9cb3b-165">Microsoft Edge は、ルート `HKEY_CURRENT_USER` キーの後にクエリを実行 `HKEY_LOCAL_MACHINE` します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-165">Microsoft Edge queries the `HKEY_CURRENT_USER` root key followed by `HKEY_LOCAL_MACHINE`.</span></span>  <span data-ttu-id="9cb3b-166">どちらのキーでも、最初に 32 ビット レジストリが検索され、次に 64 ビット レジストリが検索され、ネイティブ メッセージング ホストが識別されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-166">In both of the keys, the 32-bit registry is searched first, and then the 64-bit registry is searched to identify native messaging hosts.</span></span>  <span data-ttu-id="9cb3b-167">レジストリ キーは、ネイティブ メッセージング ホスト マニフェストの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-167">The registry key specifies the location of the native messaging host manifest.</span></span>  <span data-ttu-id="9cb3b-168">Microsoft Edge は、前に示した場所でレジストリ キーを見つけた場合、この段落に記載されている場所に対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-168">If Microsoft Edge finds the registry key at any of the previously listed locations, it doesn't query the locations that are listed in this paragraph.</span></span>  <span data-ttu-id="9cb3b-169">上記のファイルをバッチ スクリプトの一部として実行する場合は、管理者コマンド プロンプトを使用 `.reg` して実行してください。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-169">If you run the above `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>  

### [<span data-ttu-id="9cb3b-170">macOS</span><span class="sxs-lookup"><span data-stu-id="9cb3b-170">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="9cb3b-171">マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-171">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="9cb3b-172">すべてのユーザーが利用できるシステム全体のネイティブ メッセージング ホストは、固定の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-172">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="9cb3b-173">たとえば、マニフェスト ファイルは次の場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-173">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   <span data-ttu-id="9cb3b-174">ユーザー固有のネイティブ メッセージング ホスト (現在のユーザーだけが使用できます) は、ユーザー プロファイル ディレクトリのサブディレクトリ `NativeMessagingHosts` にあります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-174">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="9cb3b-175">たとえば、マニフェスト ファイルは次の場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-175">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    <span data-ttu-id="9cb3b-176">in  `{Channel_Name}` は `Microsoft Edge {Channel_Name}` 、次のいずれかの値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-176">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   <span data-ttu-id="9cb3b-177">Canary</span><span class="sxs-lookup"><span data-stu-id="9cb3b-177">Canary</span></span>  
    *   <span data-ttu-id="9cb3b-178">Dev</span><span class="sxs-lookup"><span data-stu-id="9cb3b-178">Dev</span></span>  
    *   <span data-ttu-id="9cb3b-179">Beta</span><span class="sxs-lookup"><span data-stu-id="9cb3b-179">Beta</span></span>  

    <span data-ttu-id="9cb3b-180">Stable チャネルを使用する `{Channel_Name}` 場合、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-180">When using the Stable channel, `{Channel_Name}` isn't required.</span></span>  

### [<span data-ttu-id="9cb3b-181">Linux</span><span class="sxs-lookup"><span data-stu-id="9cb3b-181">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="9cb3b-182">マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-182">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="9cb3b-183">すべてのユーザーが利用できるシステム全体のネイティブ メッセージング ホストは、固定の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-183">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="9cb3b-184">マニフェスト ファイルは、次の場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-184">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="9cb3b-185">ユーザー固有のネイティブ メッセージング ホスト (現在のユーザーだけが使用できます) は、ユーザー プロファイル ディレクトリのサブディレクトリ `NativeMessagingHosts` にあります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-185">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="9cb3b-186">マニフェスト ファイルは、次の場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-186">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> <span data-ttu-id="9cb3b-187">マニフェスト ファイルに対する読み取りアクセス許可を提供し、ホスト ランタイムでアクセス許可を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-187">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

<!-- links -->  


 [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"

> [!NOTE]
> <span data-ttu-id="9cb3b-189">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-189">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9cb3b-190">元のページはここ [です](https://developer.chrome.com/extensions/nativeMessaging)。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-190">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9cb3b-192">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9cb3b-192">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
