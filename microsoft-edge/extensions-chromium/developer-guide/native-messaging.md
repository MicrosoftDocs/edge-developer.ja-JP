---
description: Chrome のドキュメントとのネイティブメッセージの違い
title: ネイティブ メッセージング
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/31/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 0fe45ea681c54ddea7b27a8d954022b8bda45770
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569581"
---
# <span data-ttu-id="6497d-104">ネイティブ メッセージング</span><span class="sxs-lookup"><span data-stu-id="6497d-104">Native Messaging</span></span>  

<span data-ttu-id="6497d-105">Microsoft Edge では、microsoft edge アドオンカタログ (Microsoft Edge アドオン \) からの拡張機能が、メッセージパッシング Api を使用してネイティブアプリケーションでメッセージを交換できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6497d-105">Microsoft Edge now allows Extension installed from Microsoft Edge Addons catalog \(Microsoft Edge Addons\) to exchange messages with a native application using message passing APIs.</span></span>  <span data-ttu-id="6497d-106">この機能を有効にするには、ネイティブアプリケーションのネイティブメッセージングホストを実装するときに、次の点を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-106">To enable the feature, you need to make sure of following things while implementing native messaging host of your Native Application.</span></span>  

<!--
 > [!NOTE]
> Native messaging is currently not supported on macOS and Linux version of Microsoft Edge.  This feature support is planned to be implemented soon.  -->  

1.  <span data-ttu-id="6497d-107">**ネイティブメッセージングホスト**:</span><span class="sxs-lookup"><span data-stu-id="6497d-107">**Native messaging host**:</span></span>  
    
    <span data-ttu-id="6497d-108">ネイティブメッセージングホストを登録するために、アプリケーションは、ネイティブメッセージングホスト構成を定義するマニフェストファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-108">In order to register a native messaging host the application must install a manifest file that defines the native messaging host configuration.</span></span>  <span data-ttu-id="6497d-109">マニフェストファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6497d-109">Below is an example of the manifest file:</span></span>  
    
    ```xml
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
    
<span data-ttu-id="6497d-110">ネイティブメッセージングホストマニフェストファイルは、有効な JSON であり、次のフィールドが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-110">The native messaging host manifest file must be valid JSON and contains the following fields:</span></span>  

| <span data-ttu-id="6497d-111">名前</span><span class="sxs-lookup"><span data-stu-id="6497d-111">Name</span></span> | <span data-ttu-id="6497d-112">説明</span><span class="sxs-lookup"><span data-stu-id="6497d-112">Description</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="6497d-113">ネイティブメッセージングホストの名前。</span><span class="sxs-lookup"><span data-stu-id="6497d-113">Name of the native messaging host.</span></span> <span data-ttu-id="6497d-114">クライアントは、またはにこの文字列を渡し `runtime.connectNative` `runtime.sendNativeMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="6497d-114">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  <span data-ttu-id="6497d-115">この名前には、小文字の英数字、アンダースコア、ドットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-115">This name must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  <span data-ttu-id="6497d-116">名前の先頭または末尾にドットを使用することはできません。ドットの後に別のドットを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="6497d-116">The name must not start or end with a dot, and a dot must not be followed by another dot.</span></span> |  
| `description` | <span data-ttu-id="6497d-117">短いアプリケーションの説明。</span><span class="sxs-lookup"><span data-stu-id="6497d-117">Short application description.</span></span> |  
| `path` | <span data-ttu-id="6497d-118">ネイティブメッセージングホストバイナリへのパス。</span><span class="sxs-lookup"><span data-stu-id="6497d-118">Path to the native messaging host binary.</span></span>  <span data-ttu-id="6497d-119">Windows では、パスはマニフェストファイルが配置されているディレクトリに関連している場合があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-119">On Windows, the path may be relative to the directory in which the manifest file is located.</span></span>  <span data-ttu-id="6497d-120">MacOS では、パスは絶対パスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-120">On macOS, the path must be absolute.</span></span>  <span data-ttu-id="6497d-121">ホストプロセスは、現在のディレクトリがホストバイナリを含むディレクトリに設定された状態で開始されます。</span><span class="sxs-lookup"><span data-stu-id="6497d-121">The host process is started with the current directory set to the directory that contains the host binary.</span></span> <span data-ttu-id="6497d-122">たとえば、このパラメーターがに設定されている場合、 `C:\Application\nm_host.exe` 現在のディレクトリを使ってバイナリが開始され `C:\Application\` ます。</span><span class="sxs-lookup"><span data-stu-id="6497d-122">For example if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory `C:\Application\`.</span></span> |  
| `type` | <span data-ttu-id="6497d-123">ネイティブメッセージングホストとの通信に使用されるインターフェイスの種類。</span><span class="sxs-lookup"><span data-stu-id="6497d-123">Type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="6497d-124">現在、このパラメーターに指定できる値は1つだけ `stdio` です。</span><span class="sxs-lookup"><span data-stu-id="6497d-124">Currently there is only one possible value for this parameter: `stdio`.</span></span>  <span data-ttu-id="6497d-125">この値は、Chrome で `stdin` ホストと `stdout` 通信するために使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="6497d-125">This value indicates that Chrome should use `stdin` and `stdout` to communicate with the host.</span></span> |  
| `allowed_origins` |  <span data-ttu-id="6497d-126">ネイティブメッセージングホストにアクセスする必要がある拡張機能の一覧。</span><span class="sxs-lookup"><span data-stu-id="6497d-126">list of Extension that should access to the native messaging host.</span></span>  <span data-ttu-id="6497d-127">ネイティブアプリケーションで Microsoft Edge のアドオン拡張機能を使用できるようにするには、 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` ネイティブのメッセージングホストマニフェストファイルにを設定します。</span><span class="sxs-lookup"><span data-stu-id="6497d-127">To enable your Native Application identify and communicate with Microsoft Edge Addons Extension, set `allowedorigins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span> |  

1.  **<span data-ttu-id="6497d-128">ネイティブメッセージングホストの場所</span><span class="sxs-lookup"><span data-stu-id="6497d-128">Native messaging host location</span></span>**  
    
    <span data-ttu-id="6497d-129">マニフェストファイルの場所はプラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6497d-129">The location of the manifest file depends on the platform.</span></span>  
    
    <span data-ttu-id="6497d-130">Windows では、マニフェストファイルはファイルシステムの任意の場所に配置されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-130">On Windows, the manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="6497d-131">アプリケーションインストーラーは、レジストリキーを作成する必要がある</span><span class="sxs-lookup"><span data-stu-id="6497d-131">The application installer must create registry key</span></span>  
    
    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    <span data-ttu-id="6497d-132">または</span><span class="sxs-lookup"><span data-stu-id="6497d-132">or</span></span>  
    `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`<span data-ttu-id="6497d-133">,</span><span class="sxs-lookup"><span data-stu-id="6497d-133">,</span></span>  
    
    <span data-ttu-id="6497d-134">そのキーの既定値をマニフェストファイルの完全パスに設定します。</span><span class="sxs-lookup"><span data-stu-id="6497d-134">and set default value of that key to the full path to the manifest file.</span></span>  <span data-ttu-id="6497d-135">たとえば、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6497d-135">For example, using the following command:</span></span>  
    
    ```shell
    REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
    ```  
    
    <span data-ttu-id="6497d-136">または、次の .reg ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6497d-136">or using the following .reg file:</span></span>  
    
    ```shell
    Windows Registry Editor Version 5.00
    [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
    @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
    <span data-ttu-id="6497d-137">Microsoft Edge でネイティブメッセージホストを検索すると、32ビットのレジストリが最初に照会され、次に64ビットのレジストリが照会されます。</span><span class="sxs-lookup"><span data-stu-id="6497d-137">When Microsoft Edge looks for native messaging hosts, the 32-bit registry is queried first, then the 64-bit registry.</span></span>  

<span data-ttu-id="6497d-138">MacOS では、システム全体のネイティブメッセージングホストは固定された場所で検索されますが、ユーザーレベルのネイティブメッセージングホストは、という名前のユーザープロファイルディレクトリ内のサブディレクトリで検索され `NativeMessagingHosts` ます。</span><span class="sxs-lookup"><span data-stu-id="6497d-138">On macOS, the system-wide native messaging hosts are looked up at a fixed location, while the user-level native messaging hosts are looked up in a subdirectory within the user profile directory called `NativeMessagingHosts`.</span></span>  

<span data-ttu-id="6497d-139">MacOS での Microsoft Edge \ (システム全体 \):</span><span class="sxs-lookup"><span data-stu-id="6497d-139">Microsoft Edge on macOS \(system-wide\) :</span></span>  
`/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`  

<span data-ttu-id="6497d-140">MacOS での Microsoft Edge \ (ユーザー固有、既定のパス \):</span><span class="sxs-lookup"><span data-stu-id="6497d-140">Microsoft Edge on macOS \(user-specific, default path\):</span></span>  
`~/Library/Application Support/Microsoft Edge <ChannelName>/ NativeMessagingHosts/com.my_company.my_application.json`  

`<ChannelName>` <span data-ttu-id="6497d-141">は、カナリア、Dev、またはベータ版の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6497d-141">may be Canary, Dev, or Beta.</span></span> <span data-ttu-id="6497d-142">安定したチャネルの場合にのみ `Microsoft Edge` 使用する必要があり `<ChannelName` ます。>' は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6497d-142">For stable channel, only `Microsoft Edge` should be used, `<ChannelName`>\` is not required.</span></span>

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="6497d-143">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6497d-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6497d-144">元のページは[ここ](https://developer.chrome.com/extensions/nativeMessaging)にあります。</span><span class="sxs-lookup"><span data-stu-id="6497d-144">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6497d-146">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6497d-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
