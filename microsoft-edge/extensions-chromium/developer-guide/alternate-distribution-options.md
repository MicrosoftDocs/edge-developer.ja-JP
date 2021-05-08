---
description: 検証済みストアを使用しない代替メソッドを使用して拡張機能を配布する方法について説明します。
title: 拡張機能を配布する代替メソッド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 3b2c72e13488632e2fadea2a7e8eb95888f67170
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343151"
---
# <span data-ttu-id="a7b00-104">代替拡張機能の配布方法</span><span class="sxs-lookup"><span data-stu-id="a7b00-104">Alternate extension distribution methods</span></span>  

<span data-ttu-id="a7b00-105">通常、拡張機能は Microsoft Edge アドオン ストアを通じて配布されます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-105">Generally, extensions are distributed through the Microsoft Edge Add-ons store.</span></span> <span data-ttu-id="a7b00-106">開発者が代替メソッドを使用して拡張機能を配布する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-106">There are some scenarios where developers may need to distribute extensions using alternate methods.</span></span> <span data-ttu-id="a7b00-107">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-107">For example:</span></span>

1.  <span data-ttu-id="a7b00-108">拡張機能は他のソフトウェアに関連付けられているので、バンドルされているソフトウェアの残りの部分と共にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-108">The extension is associated with other software, and it should be installed together with the rest of the bundled software.</span></span>   
1.  <span data-ttu-id="a7b00-109">ネットワーク管理者は、組織全体に拡張機能を配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-109">Network administrators want to distribute an extension throughout their organization.</span></span>   

<span data-ttu-id="a7b00-110">エッジ アドオン ストアから読み込まれない拡張機能は、外部にインストールされた拡張機能と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-110">Extensions that are not loaded from the Edge Add-ons store are referred to as externally installed extensions.</span></span> <span data-ttu-id="a7b00-111">次の一覧では、外部にインストールされた拡張機能を配布する別の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-111">The following list provides alternate methods of distributing externally installed extensions.</span></span> 

*   <span data-ttu-id="a7b00-112">Windows レジストリを使用します (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="a7b00-112">Use the Windows registry (Windows only).</span></span>  
*   <span data-ttu-id="a7b00-113">基本設定 JSON ファイル (macOS と Linux) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-113">Use a preferences JSON file (macOS and Linux).</span></span>  
    
## <span data-ttu-id="a7b00-114">始める前に</span><span class="sxs-lookup"><span data-stu-id="a7b00-114">Before you begin</span></span>  

<span data-ttu-id="a7b00-115">Microsoft Edge アドオン ストアで拡張機能を発行するか、ファイルをパッケージ化し、コンピューターに正常にインストール `.crx` されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-115">Ensure that you publish your extension in the Microsoft Edge Add-ons store, or package a `.crx` file and ensure that it installs successfully on your computer.</span></span>  <span data-ttu-id="a7b00-116">ファイルをインストールする `.crx` 場合は、その URL で拡張子に移動 `update_URL` できます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-116">If you install the `.crx` file using the `update_URL`, ensure you can navigate to your extension at that URL.</span></span>  

<span data-ttu-id="a7b00-117">また、次の情報を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-117">Also, ensure that you have the following information.</span></span>    

1.  <span data-ttu-id="a7b00-118">ファイルのファイル `.crx` パス、または拡張子 `update_URL` のファイル パス。</span><span class="sxs-lookup"><span data-stu-id="a7b00-118">The file path of the `.crx` file, or the `update_URL` of your extension.</span></span>
1.  <span data-ttu-id="a7b00-119">拡張機能のバージョン。</span><span class="sxs-lookup"><span data-stu-id="a7b00-119">The version of your extension.</span></span>  <span data-ttu-id="a7b00-120">バージョン情報は、マニフェスト ファイル、またはパックされた拡張機能の読み込み後の Microsoft Edge `edge://extensions` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-120">The version information is available in your manifest file, or in Microsoft Edge at `edge://extensions` after you load the packed extension.</span></span>   
1.  <span data-ttu-id="a7b00-121">拡張機能の ID。</span><span class="sxs-lookup"><span data-stu-id="a7b00-121">The ID of your extension.</span></span>  <span data-ttu-id="a7b00-122">ID 情報は、パックされた拡張機能を読み込み後に Microsoft Edge `edge://extensions` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-122">The ID information is available in Microsoft Edge at `edge://extensions` after you load the packed extension.</span></span>  

> [!NOTE] 
> <span data-ttu-id="a7b00-123">次の例では、 `1.0` バージョンと ID `aaaaaaaaaabbbbbbbbbbcccccccccc` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-123">The following examples use `1.0` as the version, and `aaaaaaaaaabbbbbbbbbbcccccccccc` for the ID.</span></span>  

## <span data-ttu-id="a7b00-124">Windows レジストリを使用する (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="a7b00-124">Use the Windows registry (Windows only)</span></span>  

<span data-ttu-id="a7b00-125">Windows レジストリを使用して拡張機能を配布するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-125">To distribute your extension using the Windows registry, perform the following steps.</span></span>

1.  <span data-ttu-id="a7b00-126">レジストリで次のキーを検索または作成します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-126">Find or create the following key in the registry:</span></span>  
    *   <span data-ttu-id="a7b00-127">32 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions` .</span><span class="sxs-lookup"><span data-stu-id="a7b00-127">32-bit Windows:  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`.</span></span>  
    *   <span data-ttu-id="a7b00-128">64 ビット Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions` .</span><span class="sxs-lookup"><span data-stu-id="a7b00-128">64-bit Windows:  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`.</span></span>  
1.  <span data-ttu-id="a7b00-129">拡張機能の ID と同じ名前\*\*\*\* の [拡張機能] の下に新しいキーまたはフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-129">Create a new key, or folder, under **Extensions** with the same name as the ID of your extension.</span></span> <span data-ttu-id="a7b00-130">たとえば、名前を持つキーを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-130">For example, create the key with the name `aaaaaaaaaabbbbbbbbbbcccccccccc`.</span></span>  
1.  <span data-ttu-id="a7b00-131">Extensions **キーで** プロパティを作成 `update_url` し、値をに設定します `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-131">In the **Extensions** key, create the `update_url` property, and set the value to `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span>  <span data-ttu-id="a7b00-132">プロパティ `update_url` は、Microsoft Edge アドオン `.crx` ストア内の拡張機能のファイルをポイントします。</span><span class="sxs-lookup"><span data-stu-id="a7b00-132">The `update_url` property points to the `.crx` file of your extension in the Microsoft Edge Add-ons store.</span></span>  

    ```json
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="a7b00-133">Chrome Web ストアから拡張機能をインストールする場合は、の値をに設定 `update_url` します `https://clients2.google.com/service/update2/crx` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-133">If you want to install an extension from the Chrome Web Store, set the value of `update_url` to `https://clients2.google.com/service/update2/crx`.</span></span>  
  
1.  <span data-ttu-id="a7b00-134">に移動して、拡張機能が Microsoft Edge に表示されるのを確認します `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-134">Verify that your extension is listed in Microsoft Edge by navigating to `edge://extensions`.</span></span>  

## <span data-ttu-id="a7b00-135">基本設定 JSON ファイルを使用する (macOS と Linux)</span><span class="sxs-lookup"><span data-stu-id="a7b00-135">Use a preferences JSON file (macOS and Linux)</span></span>  

<span data-ttu-id="a7b00-136">基本設定 JSON ファイルを使用して拡張機能を配布するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-136">To distribute your extension using a preferences JSON file, perform the following steps.</span></span>

1.  <span data-ttu-id="a7b00-137">Linux を使用する場合は、拡張機能がインストールされるコンピューターで拡張機能 `.crx` ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-137">When using Linux, ensure your `.crx` extension file is available on the machine that the extension will be installed on.</span></span> <span data-ttu-id="a7b00-138">拡張機能ファイル `.crx` をローカル ディレクトリにコピーするか、コンピューターから到達可能なネットワーク共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-138">Copy the `.crx` extension file to a local directory, or use a  network share that is reachable from the machine.</span></span> 
1.  <span data-ttu-id="a7b00-139">ファイルの名前が拡張子の ID に対応する JSON ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-139">Create a JSON file where the name of the file corresponds to the ID of your extension.</span></span> <span data-ttu-id="a7b00-140">たとえば、ファイル名を使用して JSON ファイルを作成します `aaaaaaaaaabbbbbbbbbbcccccccccc.json` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-140">For example, create a JSON file with the file name `aaaaaaaaaabbbbbbbbbbcccccccccc.json`.</span></span>  
1.  <span data-ttu-id="a7b00-141">オペレーティング システムに応じて、JSON ファイルを次のいずれかのフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-141">Depending on your operating system, save the JSON file to one of the following folders.</span></span>   
    *   **<span data-ttu-id="a7b00-142">macOS</span><span class="sxs-lookup"><span data-stu-id="a7b00-142">macOS</span></span>**  
        *   <span data-ttu-id="a7b00-143">ユーザー固有:</span><span class="sxs-lookup"><span data-stu-id="a7b00-143">User specific:</span></span> `~USERNAME/Library/Application Support/Microsoft Edge/External Extensions/`  
        *   <span data-ttu-id="a7b00-144">すべてのユーザー:</span><span class="sxs-lookup"><span data-stu-id="a7b00-144">All users:</span></span> `/Library/Application Support/Microsoft/Edge/External Extensions/`  
        
        <span data-ttu-id="a7b00-145">権限のないユーザーがすべてのユーザーに拡張機能をインストールしに行かねない場合は、拡張機能ファイルの読み取り専用を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7b00-145">To prevent unauthorized users from installing extensions for all users, ensure your extension file is read only.</span></span> <span data-ttu-id="a7b00-146">さらに、次の条件が満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-146">Additionally, ensure that the following conditions are met:</span></span>
        
        *   <span data-ttu-id="a7b00-147">パス内のすべてのディレクトリは、ユーザー ルートによって所有されます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-147">Every directory in the path is owned by the user root.</span></span>  
        *   <span data-ttu-id="a7b00-148">パス内のすべてのディレクトリが、またはグループに `admin` 割り当 `wheel` てられます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-148">Every directory in the path is assigned to the `admin` or `wheel` group.</span></span>  
        *   <span data-ttu-id="a7b00-149">パス内のすべてのディレクトリは、ワールド書き込み可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="a7b00-149">Every directory in the path isn't world writable.</span></span>  
        *   <span data-ttu-id="a7b00-150">パスにはシンボリック リンクも含めずに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-150">The path must also be free of symbolic links.</span></span>  
        
    *   **<span data-ttu-id="a7b00-151">Linux</span><span class="sxs-lookup"><span data-stu-id="a7b00-151">Linux</span></span>**  
        *   <span data-ttu-id="a7b00-152">ユーザー固有:</span><span class="sxs-lookup"><span data-stu-id="a7b00-152">User specific:</span></span> `~/.config/microsoft-edge/External Extensions/`  
        *   <span data-ttu-id="a7b00-153">すべてのユーザー:</span><span class="sxs-lookup"><span data-stu-id="a7b00-153">All users:</span></span> `/usr/share/microsoft-edge/extensions/`  
1.  <span data-ttu-id="a7b00-154">シナリオに応じて、JSON ファイルに続く適切なコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a7b00-154">Depending on your scenario, copy the appropriate code that follows to your JSON file.</span></span> 
    *   <span data-ttu-id="a7b00-155">Linux にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-155">Applies to Linux only.</span></span> <span data-ttu-id="a7b00-156">ファイルからインストールする場合は、場所とバージョンを使用して指定 `external_crx` します `external_version` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-156">If you install from a file, specify the location and version using `external_crx` and `external_version`.</span></span>  
            
        ```json
        {
            "external_crx": "/home/share/extension.crx",
            "external_version": "1.0"
        }
        ```  

    *   <span data-ttu-id="a7b00-157">macOS と Linux に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-157">Applies to macOS and Linux.</span></span> <span data-ttu-id="a7b00-158">からインストールする場合は `update_URL` 、 を使用して更新 URL を指定します `external_update_url` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-158">If you install from an `update_URL`, specify the update URL using `external_update_url`.</span></span> 
        
        <span data-ttu-id="a7b00-159">Linux 上のローカル ファイルからのみインストールする場合は、次のコードを `.crx` JSON ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a7b00-159">Copy the following code to your JSON file when installing from local `.crx` files on Linux only.</span></span>  
    
        ```json
        {
            "external_update_url": "http://myhost.com/mytestextension/updates.xml"
        }
        ```  
 
    *  <span data-ttu-id="a7b00-160">macOS と Linux の Microsoft Edge アドオン ストアからインストールする場合は、次のコードを JSON ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a7b00-160">Copy the following code to your JSON file when installing from the Microsoft Edge Add-ons store on macOS and Linux.</span></span>
    
        ```json
        {
            "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
        }
        ```  
    
1.  <span data-ttu-id="a7b00-161">特定の地域の拡張機能をインストールするには、サポートされている地域を使用して一覧表示します `supported_locale` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-161">To install extensions for specific locales, list the supported locales using `supported_locale`.</span></span>  <span data-ttu-id="a7b00-162">親を使用しているすべての言語の地域に拡張機能をインストールする親のローカルを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-162">You may also specify parent locales to install your extension for all language locales that use that parent.</span></span> <span data-ttu-id="a7b00-163">たとえば、親ロケールを使用する場合、拡張機能は 、など、すべての英語ロケールに `en` `en-US` `en-GB` インストールされます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-163">For example, when using the parent locale `en`, your extension installs for all English locales, such as `en-US`, `en-GB`, and so on.</span></span>  <span data-ttu-id="a7b00-164">ユーザーがブラウザーでロケールを変更すると、外部にインストールされている拡張機能がアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-164">When users change their locale in their browser, externally installed extensions are uninstalled.</span></span>  <span data-ttu-id="a7b00-165">任意のロケールの拡張機能をインストールするには、使用しません `supported_locales` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-165">To install your extension for any locale, do not use `supported_locales`.</span></span>  

    ```json
    {
        "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx",
        "supported_locales": [ "en", "fr", "de" ]
    }
    ```  

1.  <span data-ttu-id="a7b00-166">に移動して、拡張機能が Microsoft Edge にインストールされていることを確認します `edge://extensions` 。</span><span class="sxs-lookup"><span data-stu-id="a7b00-166">Verify that your extension is installed in Microsoft Edge by navigating to `edge://extensions`.</span></span>  

## <span data-ttu-id="a7b00-167">外部にインストールされている拡張機能の更新とアンインストール</span><span class="sxs-lookup"><span data-stu-id="a7b00-167">Update and uninstall externally installed extensions</span></span>

<span data-ttu-id="a7b00-168">Microsoft Edge は、ブラウザーが起動する度にレジストリ内のメタデータ エントリをスキャンし、外部にインストールされている拡張機能に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="a7b00-168">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any changes to the externally installed extensions.</span></span>  

<span data-ttu-id="a7b00-169">拡張機能を新しいバージョンに更新するには、マニフェスト ファイルのバージョンを更新し、レジストリのバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-169">To update your extension to a new version, update the version in the manifest file, and then update the version in the registry.</span></span>  

<span data-ttu-id="a7b00-170">以前にコンピューターにインストールされたソフトウェアのバンドルの一部としてインストールされた、外部にインストールされた拡張機能をアンインストールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7b00-170">You may need to uninstall externally installed extensions, which were installed as part of a bundle of software that was previously installed on the machine.</span></span>  <span data-ttu-id="a7b00-171">拡張機能をアンインストールするには、基本設定の JSON ファイルを削除するか、レジストリからキーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a7b00-171">To uninstall your extension, remove your preferences JSON file or remove the key from the registry.</span></span>   

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="a7b00-172">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="a7b00-172">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  <span data-ttu-id="a7b00-173">元のページは次 [のページに表示されます](https://developer.chrome.com/apps/external_extensions)。</span><span class="sxs-lookup"><span data-stu-id="a7b00-173">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a7b00-175">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a7b00-175">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
