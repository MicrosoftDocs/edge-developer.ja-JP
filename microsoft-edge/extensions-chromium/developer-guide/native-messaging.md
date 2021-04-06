---
description: ネイティブ メッセージングのドキュメント
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/31/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: e6233289794bc1c3ef235af46402c23173c09857
ms.sourcegitcommit: e6a4f73be57439149e3cc56491d7364831d0079e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "11475212"
---
# <a name="native-messaging"></a><span data-ttu-id="ebfcc-104">ネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="ebfcc-104">Native messaging</span></span>  

<span data-ttu-id="ebfcc-105">拡張機能は、API を渡すメッセージを使用して、ユーザーのデバイスにインストールされているネイティブの Win32 アプリと通信します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-105">Extensions communicate with a native Win32 app installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="ebfcc-106">ネイティブ アプリ ホストは、標準の入力と標準出力を使用して、拡張機能付きメッセージを送信および受信します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-106">The native app host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="ebfcc-107">ネイティブ メッセージングを使用する拡張機能は、他の拡張機能と同様に Microsoft Edge にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="ebfcc-108">ただし、ネイティブ アプリは Microsoft Edge によってインストールまたは管理されません。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-108">However, native apps are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="ebfcc-109">拡張機能とネイティブ アプリ ホストを取得するには、2 つの配布モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-109">To acquire the extension and native app host, you have two distribution models.</span></span>  

*   <span data-ttu-id="ebfcc-110">拡張機能とホストをまとめてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-110">Package your extension and the host together.</span></span>  <span data-ttu-id="ebfcc-111">ユーザーがパッケージをインストールすると、拡張機能とホストの両方がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-111">When a user installs the package, both the extension and the host are installed.</span></span>  
*   <span data-ttu-id="ebfcc-112">Microsoft Edge アドオン ストアを [使用して][MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]拡張機能をインストールすると、拡張機能によってホストのインストールを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-112">Install your extension using the [Microsoft Edge Add-ons store][MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="ebfcc-113">ネイティブ アプリ ホストを使用してメッセージを送受信する拡張機能を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-113">To create your extension to send and receive messages with native app hosts, complete the following steps.</span></span>  

## <a name="step-1---add-permissions-to-the-extension-manifest"></a><span data-ttu-id="ebfcc-114">手順 1 - 拡張機能マニフェストにアクセス許可を追加する</span><span class="sxs-lookup"><span data-stu-id="ebfcc-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="ebfcc-115">拡張子の `nativeMessaging` ファイルmanifest.js\*\* にアクセス\*\* 許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="ebfcc-116">次のコード スニペットは、on のコードmanifest.js\*\* です\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-116">The following code snippet is an example of **manifest.json**.</span></span>  

```json
{
    "name": "Native Messaging Example",
    "version": "1.0",
    "manifest_version": 2, 
    "description": "Send a message to a native app.",
    "app": { 
        "launch": { 
            "local_path": "main.html" 
        } 
    }, 
    "icons": { 
        "128": "icon-128.png"
    }, 
    "permissions": ["nativeMessaging"] 
}
```  

## <a name="step-2---create-your-native-messaging-host-manifest-file"></a><span data-ttu-id="ebfcc-117">手順 2 - ネイティブ メッセージング ホスト マニフェスト ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ebfcc-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="ebfcc-118">ネイティブ アプリは、ネイティブ メッセージング ホスト マニフェスト ファイルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-118">Native apps must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="ebfcc-119">マニフェスト ファイルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-119">The manifest file contains the following information.</span></span>  

*   <span data-ttu-id="ebfcc-120">ネイティブ メッセージング ホスト ランタイムへのパス。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-120">The path to the native messaging host runtime.</span></span>  
*   <span data-ttu-id="ebfcc-121">拡張機能との通信方法。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-121">The method of communication with the extension.</span></span>  
*   <span data-ttu-id="ebfcc-122">通信先の許可された拡張機能の一覧。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-122">A list of allowed extensions to which it communicates.</span></span>  
    
<span data-ttu-id="ebfcc-123">ブラウザーは、ネイティブ メッセージング ホスト マニフェストを読み取り、検証します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-123">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="ebfcc-124">ブラウザーは、ネイティブ メッセージング ホスト マニフェスト ファイルをインストールまたは管理しない。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-124">The browser doesn't install or manage the native messaging host manifest file.</span></span>  

```json
{
    "name": "com.my_company.my_app",
    "description": "My App",
    "path": "C:\\Program Files\\My App\\chrome_native_messaging_host.exe",
    "type": "stdio",
    "allowed_origins": [
        "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```  

<span data-ttu-id="ebfcc-125">ホスト マニフェスト ファイルは、次のキーを含む有効な JSON ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-125">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="ebfcc-126">キー</span><span class="sxs-lookup"><span data-stu-id="ebfcc-126">Key</span></span>**  
   :::column-end:::
   :::column span="3":::
      **<span data-ttu-id="ebfcc-127">詳細</span><span class="sxs-lookup"><span data-stu-id="ebfcc-127">Details</span></span>**  
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `name`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="ebfcc-128">ネイティブ メッセージング ホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-128">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="ebfcc-129">クライアントは、文字列を `runtime.connectNative` または `runtime.sendNativeMessage` に渡します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-129">Clients pass the string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="ebfcc-130">この値には、小文字の英数字、アンダースコア、ドットのみを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-130">The value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="ebfcc-131">値はドットで開始または終了し、ドットの後に別のドットを付けずに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-131">The value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `description`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="ebfcc-132">アプリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-132">Describes the app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `path`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="ebfcc-133">ネイティブ メッセージング ホスト バイナリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-133">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="ebfcc-134">Windows デバイスでは、マニフェスト ファイルを含むディレクトリへの相対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-134">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="ebfcc-135">macOS および Linux では、パスは絶対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-135">On macOS and Linux, the path must be absolute.</span></span>  
          
      <span data-ttu-id="ebfcc-136">ホスト プロセスは、ホスト バイナリを含むディレクトリに設定されている現在のディレクトリから始まります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-136">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="ebfcc-137">たとえば、\(Windows\) パラメーターが設定されている場合、バイナリはカレント ディレクトリ `C:\App\nm_host.exe` \( \) を使用して `C:\App\` 開始されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-137">For example \(Windows\), if the parameter is set to `C:\App\nm_host.exe`, the binary is started using the current directory \(`C:\App\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `type`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="ebfcc-138">ネイティブ メッセージング ホストとの通信に使用するインターフェイスの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-138">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="ebfcc-139">この値は、ホストを使用して通信するように Microsoft Edge `stdin` `stdout` に指示します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-139">The value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="ebfcc-140">受け入れ可能な唯一の値は `stdio` です。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-140">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `allowed_origins` 
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="ebfcc-141">ネイティブ メッセージング ホストにアクセスできる拡張機能の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-141">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="ebfcc-142">アプリを有効にし、拡張機能を識別して通信するには、ネイティブ メッセージング ホスト マニフェスト ファイルで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-142">To turn on your app to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="ebfcc-143">拡張機能をサイドロードして、ホストとのネイティブ メッセージングをテストします。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-143">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="ebfcc-144">開発中に拡張機能をサイドロードして取得するには `microsoft_catalog_extension_id` 、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-144">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following actions.</span></span>  

1.  <span data-ttu-id="ebfcc-145">に移動 `edge://extensions` し、[開発者モード] トグル ボタンをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-145">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="ebfcc-146">[ **アンパックの読み込み**] を選択し、サイドロードする拡張パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-146">Choose **Load unpacked**, and then choose your extension package to sideload.</span></span>  
1.  <span data-ttu-id="ebfcc-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-147">Choose **OK**.</span></span>  
1.  <span data-ttu-id="ebfcc-148">ページに移動 `edge://extensions` し、拡張機能が一覧に表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-148">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="ebfcc-149">ページの内線 `microsoft_catalog_extension_id` 番号の一覧から \(ID\) からキーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-149">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>  
    
<span data-ttu-id="ebfcc-150">拡張機能をユーザーに配布する準備ができたら、拡張機能を Microsoft Edge アドオン ストアに発行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-150">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge Add-ons store.</span></span>  <span data-ttu-id="ebfcc-151">発行された拡張機能の内線番号 ID は、拡張機能のサイドロード中に使用される ID と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-151">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="ebfcc-152">ID が変更された場合は、発行された拡張子の ID を使用してホスト マニフェスト `allowed_origins` ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-152">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <a name="step-3---copy-the-native-messaging-host-manifest-file-to-your-system"></a><span data-ttu-id="ebfcc-153">手順 3 - ネイティブ メッセージング ホスト マニフェスト ファイルをシステムにコピーする</span><span class="sxs-lookup"><span data-stu-id="ebfcc-153">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="ebfcc-154">最後の手順では、ネイティブ メッセージング ホスト マニフェスト ファイルをコンピューターにコピーし、マニフェスト ファイルが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-154">The final step involves copying the native messaging host manifest file to your computer, and ensuring the manifest file is correctly configured.</span></span>  <span data-ttu-id="ebfcc-155">マニフェスト ファイルが予期した場所に配置されるのを確認するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-155">To ensure your manifest file is placed in the expected location, complete the following the actions.</span></span>  <span data-ttu-id="ebfcc-156">場所はプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-156">The location varies by platform.</span></span>

> [!NOTE]
> <span data-ttu-id="ebfcc-157">マニフェスト ファイルに対する読み取りアクセス許可を指定し、ホスト ランタイムでアクセス許可を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-157">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

### [<a name="windows"></a><span data-ttu-id="ebfcc-158">Windows</span><span class="sxs-lookup"><span data-stu-id="ebfcc-158">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="ebfcc-159">マニフェスト ファイルは、ファイル システム内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-159">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="ebfcc-160">アプリ インストーラーは、レジストリ キーを作成し、キーの既定値をマニフェスト ファイルの完全なパスに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-160">The app installer must create a registry key and set the default value of the key to the full path of the manifest file.</span></span>  <span data-ttu-id="ebfcc-161">レジストリ キーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-161">The following locations are examples of registry keys.</span></span>  

```output
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app
```  

<span data-ttu-id="ebfcc-162">マニフェスト キーを使用してレジストリ キーをディレクトリに追加するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-162">To add a registry key to the directory with the manifest key, complete one of the following actions.</span></span>  

*   <span data-ttu-id="ebfcc-163">コマンド プロンプトでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-163">Run command in command prompt.</span></span>  
    
    1.  <span data-ttu-id="ebfcc-164">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-164">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
        
*   <span data-ttu-id="ebfcc-165">ファイルを `.reg` 作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-165">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="ebfcc-166">次のコマンドをファイルに `.reg` コピーします。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-166">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="ebfcc-167">ファイルを実行 `.reg` します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-167">Run the `.reg` file.</span></span>  
        
<span data-ttu-id="ebfcc-168">Microsoft Edge は、ルート キー `HKEY_CURRENT_USER` の後に続いてクエリを実行します `HKEY_LOCAL_MACHINE` 。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-168">Microsoft Edge queries the `HKEY_CURRENT_USER` root key followed by `HKEY_LOCAL_MACHINE`.</span></span>  <span data-ttu-id="ebfcc-169">どちらのキーでも、最初に 32 ビット レジストリが検索され、次に 64 ビット レジストリが検索され、ネイティブ メッセージング ホストが識別されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-169">In both of the keys, the 32-bit registry is searched first, and then the 64-bit registry is searched to identify native messaging hosts.</span></span>  <span data-ttu-id="ebfcc-170">レジストリ キーは、ネイティブ メッセージング ホスト マニフェストの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-170">The registry key specifies the location of the native messaging host manifest.</span></span>  <span data-ttu-id="ebfcc-171">Microsoft Edge のレジストリ エントリにホスト マニフェストの場所がない場合は、Chrome レジストリの場所と Chrome レジストリの場所がフォールバック オプションとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-171">If the registry entries for Microsoft Edge don't have the location of the host manifest, the Chromium and Chrome registry locations are used as fallback options.</span></span>  <span data-ttu-id="ebfcc-172">Microsoft Edge が、前にリストした場所でレジストリ キーを見つけた場合、次のコード スニペットに記載されている場所に対するクエリは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-172">If Microsoft Edge finds the registry key at any of the previously listed locations, it doesn't query the locations that are listed in the following code snippet.</span></span>  <span data-ttu-id="ebfcc-173">作成したファイルをバッチ スクリプトの一部として実行する場合は、管理者のコマンド プロンプトを使用 `.reg` して実行してください。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-173">If you run your created `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>

<span data-ttu-id="ebfcc-174">次の一覧は、レジストリの場所の検索順序です。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-174">The following list is the search order for the registry locations.</span></span>  

```output
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\

HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\
```  
 
> [!NOTE] 
> <span data-ttu-id="ebfcc-175">Microsoft Edge アドオンと Chrome Web ストアに拡張機能がある場合は、最初に見つかったレジストリの場所に対応するホスト マニフェストだけが読み取れるので、ホスト マニフェスト ファイルの両方のストアに対応する拡張機能の ID を追加する必要があります。 `allowed_origins`</span><span class="sxs-lookup"><span data-stu-id="ebfcc-175">If you have extensions on the Microsoft Edge Add-ons and the Chrome Webstore, you must add the extension IDs corresponding to both the stores in the `allowed_origins` of the host manifest file because only the host manifest corresponding to the first registry location found is read.</span></span>  

### [<a name="macos"></a><span data-ttu-id="ebfcc-176">macOS</span><span class="sxs-lookup"><span data-stu-id="ebfcc-176">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="ebfcc-177">マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-177">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="ebfcc-178">システム全体のネイティブ メッセージング ホスト (すべてのユーザーが利用できる) は、固定の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-178">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="ebfcc-179">たとえば、マニフェスト ファイルを次の場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-179">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
*   <span data-ttu-id="ebfcc-180">現在のユーザーだけが使用できるユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-180">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="ebfcc-181">たとえば、マニフェスト ファイルを次の場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-181">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
    <span data-ttu-id="ebfcc-182">in  `{Channel_Name}` は `Microsoft Edge {Channel_Name}` 、次のいずれかの値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-182">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   `Canary`  
    *   `Dev`  
    *   `Beta`  
        
    <span data-ttu-id="ebfcc-183">Stable チャネルを使用する ` {Channel_Name}` 場合は、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-183">When using the Stable channel, ` {Channel_Name}` isn't required.</span></span>  
    
### [<a name="linux"></a><span data-ttu-id="ebfcc-184">Linux</span><span class="sxs-lookup"><span data-stu-id="ebfcc-184">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="ebfcc-185">マニフェスト ファイルを保存するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-185">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="ebfcc-186">システム全体のネイティブ メッセージング ホスト (すべてのユーザーが利用できる) は、固定の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-186">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="ebfcc-187">マニフェスト ファイルは、次の場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-187">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="ebfcc-188">現在のユーザーだけが使用できるユーザー固有のネイティブ メッセージング ホストは、ユーザー プロファイル ディレクトリのサブ `NativeMessagingHosts` ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-188">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="ebfcc-189">マニフェスト ファイルは、次の場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-189">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

<!-- links -->  

[MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge アドオン"

> [!NOTE]
> <span data-ttu-id="ebfcc-191">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-191">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ebfcc-192">元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/nativeMessaging)。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-192">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ebfcc-194">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ebfcc-194">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
