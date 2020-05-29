---
description: Edge (Chromium) 拡張機能のエンタープライズドキュメントを拡張します。
title: ホスティングと更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: eb1f9921d503d25557fc9efb1517537e7a90f4aa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569582"
---
# <span data-ttu-id="23f1d-104">Web Store のホストと更新</span><span class="sxs-lookup"><span data-stu-id="23f1d-104">Web Store Hosting and Updating</span></span>  

<span data-ttu-id="23f1d-105">ほとんどの拡張機能は、 [Microsoft Edge Insider アドオンカタログ (Microsoft Edge insider のアドオン \)][MicrosoftStoreExtensions]にホストされ、ユーザーが悪意のある拡張機能を最大限に保護します。</span><span class="sxs-lookup"><span data-stu-id="23f1d-105">Most Extensions are hosted in the [Microsoft Edge Insider Addons catalog \(Microsoft Edge Insider Addons\)][MicrosoftStoreExtensions] to best protect users from malicious Extensions.</span></span>  

## <span data-ttu-id="23f1d-106">ホスト</span><span class="sxs-lookup"><span data-stu-id="23f1d-106">Hosting</span></span>  

<span data-ttu-id="23f1d-107">すべての拡張機能は、すべてのユーザーに対して、crx というサフィックスを持つ特別な ZIP ファイルとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="23f1d-107">All Extensions are distributed to users as a special ZIP file with a .crx suffix.</span></span>  <span data-ttu-id="23f1d-108">Microsoft Edge のアドオンでホストされる拡張機能は、.zip ファイルとしてアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="23f1d-108">Extensions hosted in the Microsoft Edge Addons are uploaded as .zip files.</span></span> <span data-ttu-id="23f1d-109">発行処理によって、.zip が自動的に crx ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="23f1d-109">The publishing process automatically converts the .zip into a .crx file.</span></span>  

<span data-ttu-id="23f1d-110">Microsoft Edge のアドオンホスティングルールには次の2つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="23f1d-110">There are two exceptions to the Microsoft Edge Addons hosting rule:</span></span>  

1.  <span data-ttu-id="23f1d-111">エンタープライズポリシーを通じて配布される拡張機能。</span><span class="sxs-lookup"><span data-stu-id="23f1d-111">Extensions that are distributed through the Enterprise policy.</span></span>  
1.  <span data-ttu-id="23f1d-112">開発者モードでローカルコンピューターから拡張機能ディレクトリを展開しました。</span><span class="sxs-lookup"><span data-stu-id="23f1d-112">Unpacked Extension directories from a local machine while in developer mode.</span></span>  

## <span data-ttu-id="23f1d-113">更新</span><span class="sxs-lookup"><span data-stu-id="23f1d-113">Updating</span></span>  

<span data-ttu-id="23f1d-114">Microsoft Edge ブラウザーでは、ユーザーの操作なしで、インストールされている拡張機能と更新プログラムの新しいバージョンが定期的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="23f1d-114">The Microsoft Edge browser periodically checks for new versions of installed Extensions and updates each without user intervention.</span></span>  

> [!NOTE]
> <span data-ttu-id="23f1d-115">Microsoft Edge のアドオンで拡張機能を更新する手順は計画されています。</span><span class="sxs-lookup"><span data-stu-id="23f1d-115">Steps to update an Extension on Microsoft Edge Addons are planned be added.</span></span>  

<!-- image links -->

<!-- links -->  

[MicrosoftStoreExtensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能-Microsoft Edge Insider アドオン"  

> [!NOTE]
> <span data-ttu-id="23f1d-117">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="23f1d-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="23f1d-118">元のページは[ここ](https://developer.chrome.com/extensions/hosting)にあります。</span><span class="sxs-lookup"><span data-stu-id="23f1d-118">The original page is found [here](https://developer.chrome.com/extensions/hosting).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="23f1d-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="23f1d-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
