---
description: 検証済みストア以外のメカニズムによって内線番号を配布するプロセス
title: 内線番号を配布する別の方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: e28a84fd75ad1ac0be2000a22c26371ca73d0293
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015696"
---
# <span data-ttu-id="03acb-104">内線番号を配布する別の方法</span><span class="sxs-lookup"><span data-stu-id="03acb-104">Alternate Method of Distributing Extension</span></span>  

<span data-ttu-id="03acb-105">他のソフトウェアのインストールプロセスの一環として、または組織全体で拡張機能を配布するネットワーク管理者を配布する場合は、Microsoft Edge は次の拡張インストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="03acb-105">If you are a developer who wants to distribute an Extension as part of the installation process for other software, or a network admin that want to distribute an Extension throughout their organization, Microsoft Edge supports the following Extension installation methods:</span></span>  

*   **<span data-ttu-id="03acb-106">Windows レジストリを使用する \ (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="03acb-106">Using the Windows registry \(Windows only\)</span></span>**  

<span data-ttu-id="03acb-107">Microsoft Edge では、でホストされている拡張機能のインストールをサポート `update_URL` しています。</span><span class="sxs-lookup"><span data-stu-id="03acb-107">Microsoft Edge supports installing an Extension hosted at an `update_URL`.</span></span>  <span data-ttu-id="03acb-108">Windows では、 `update_URL` 拡張機能がホストされている必要がある Microsoft Edge アドオンカタログ (Microsoft Edge アドオン \) をポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="03acb-108">On Windows, the `update_URL` must point to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\) where the Extension must be hosted.</span></span>  

> [!NOTE]
> <span data-ttu-id="03acb-109">MacOS 用の設定 json ファイルを使用した拡張の外部インストール</span><span class="sxs-lookup"><span data-stu-id="03acb-109">External installation of Extension via a preferences json file for macOS</span></span> <!--and Linux--> <span data-ttu-id="03acb-110">はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="03acb-110">are not supported yet.</span></span>  <span data-ttu-id="03acb-111">この機能のサポートは間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="03acb-111">This feature support will soon be available.</span></span>

## <span data-ttu-id="03acb-112">Windows レジストリを使用する</span><span class="sxs-lookup"><span data-stu-id="03acb-112">Using the Windows registry</span></span>  

<span data-ttu-id="03acb-113">まず、Microsoft Edge のアドオンで拡張機能を公開するか、または crx ファイルをパッケージ化して正常にインストールされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03acb-113">First, publish the Extension in the Microsoft Edge Addons, or package a .crx file and make sure that it installs successfully.</span></span>  

<span data-ttu-id="03acb-114">Windows のレジストリ経由で拡張機能をインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="03acb-114">The steps to install Extension via registry in windows are:</span></span>  

*   <span data-ttu-id="03acb-115">レジストリで次のキーを検索または作成します。</span><span class="sxs-lookup"><span data-stu-id="03acb-115">Find or create the following key in the registry:</span></span>  
    *   <span data-ttu-id="03acb-116">32ビット版の Windows:</span><span class="sxs-lookup"><span data-stu-id="03acb-116">32-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   <span data-ttu-id="03acb-117">64ビット版の Windows:</span><span class="sxs-lookup"><span data-stu-id="03acb-117">64-bit Windows:</span></span>  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   <span data-ttu-id="03acb-118">拡張機能の ID と同じ名前 (\ など) で、Extensions キーの下に新しいキー \ (フォルダー \) を作成 `aaaaaaaaaabbbbbbbbbbcccccccccc` します。</span><span class="sxs-lookup"><span data-stu-id="03acb-118">Create a new key \(folder\) under the Extensions key with the same name as the ID of your Extension \(for example, `aaaaaaaaaabbbbbbbbbbcccccccccc`\).</span></span>  
*   <span data-ttu-id="03acb-119">内線キーで、プロパティを作成し、 `update_url` 次の値に設定します。 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` \ (これは、Microsoft Edge アドオンの内線番号の crx を指します)。</span><span class="sxs-lookup"><span data-stu-id="03acb-119">In your Extension key, create a property, `update_url`, and set it to the value: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`,  \(this points to the crx of your extension in the Microsoft Edge Addons\).</span></span> <span data-ttu-id="03acb-120">Chrome Web ストアから拡張機能をインストールする場合は、Chrome Web ストアの更新 URL を入力してください `https://clients2.google.com/service/update2/crx` 。</span><span class="sxs-lookup"><span data-stu-id="03acb-120">If you want to install an extension from the Chrome Web Store, please provide the Chrome Web Store update URL, `https://clients2.google.com/service/update2/crx`.</span></span>  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   <span data-ttu-id="03acb-121">ブラウザを起動して「」に移動し `edge://extensions` ます。表示される拡張子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="03acb-121">Launch the browser and go to `edge://extensions`; you should see the extension listed.</span></span>  

## <span data-ttu-id="03acb-122">更新とアンインストール</span><span class="sxs-lookup"><span data-stu-id="03acb-122">Updating and uninstalling</span></span>  

<span data-ttu-id="03acb-123">Microsoft Edge は、ブラウザーが起動するたびに、レジストリのメタデータエントリをスキャンし、インストールされている外部拡張機能に必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="03acb-123">Microsoft Edge scans the metadata entries in the registry each time the browser starts, and makes any necessary changes to the installed external extensions.</span></span>  

<span data-ttu-id="03acb-124">拡張機能を新しいバージョンに更新するには、ファイルを更新してから、レジストリのバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="03acb-124">To update your extension to a new version, update the file, and then update the version in the registry.</span></span>  

<span data-ttu-id="03acb-125">拡張機能をアンインストールするには (たとえば、ソフトウェアがアンインストールされた場合など)、設定ファイル \ ( `aaaaaaaaaabbbbbbbbbbcccccccccc.json` \) またはレジストリからメタデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="03acb-125">To uninstall your extension \(for example, if your software is uninstalled\), remove your preference file \(`aaaaaaaaaabbbbbbbbbbcccccccccc.json`\) or the metadata from the registry.</span></span>  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="03acb-126">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="03acb-126">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="03acb-127">元のページは [ここ](https://developer.chrome.com/apps/external_extensions)にあります。</span><span class="sxs-lookup"><span data-stu-id="03acb-127">The original page is found [here](https://developer.chrome.com/apps/external_extensions).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="03acb-129">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="03acb-129">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
