---
description: Edge (Chromium) 拡張機能のエンタープライズドキュメントを拡張します。
title: ホスティングと更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: d918aec12e56daf66d13488d360a454d736031e8
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015703"
---
# <span data-ttu-id="cfecf-104">Web Store のホストと更新</span><span class="sxs-lookup"><span data-stu-id="cfecf-104">Web Store Hosting and Updating</span></span>  

<span data-ttu-id="cfecf-105">ほとんどの拡張機能は、 [Microsoft Edge Insider アドオンカタログ (Microsoft Edge insider のアドオン \)][MicrosoftStoreExtensions] にホストされ、ユーザーが悪意のある拡張機能を最大限に保護します。</span><span class="sxs-lookup"><span data-stu-id="cfecf-105">Most Extensions are hosted in the [Microsoft Edge Insider Addons catalog \(Microsoft Edge Insider Addons\)][MicrosoftStoreExtensions] to best protect users from malicious Extensions.</span></span>  

## <span data-ttu-id="cfecf-106">ホスティング</span><span class="sxs-lookup"><span data-stu-id="cfecf-106">Hosting</span></span>  

<span data-ttu-id="cfecf-107">すべての拡張機能は、すべてのユーザーに対して、crx というサフィックスを持つ特別な ZIP ファイルとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="cfecf-107">All Extensions are distributed to users as a special ZIP file with a .crx suffix.</span></span>  <span data-ttu-id="cfecf-108">Microsoft Edge のアドオンでホストされる拡張機能は、.zip ファイルとしてアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="cfecf-108">Extensions hosted in the Microsoft Edge Addons are uploaded as .zip files.</span></span> <span data-ttu-id="cfecf-109">発行処理によって、.zip が自動的に crx ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cfecf-109">The publishing process automatically converts the .zip into a .crx file.</span></span>  

<span data-ttu-id="cfecf-110">Microsoft Edge のアドオンホスティングルールには次の2つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="cfecf-110">There are two exceptions to the Microsoft Edge Addons hosting rule:</span></span>  

1.  <span data-ttu-id="cfecf-111">エンタープライズポリシーを通じて配布される拡張機能。</span><span class="sxs-lookup"><span data-stu-id="cfecf-111">Extensions that are distributed through the Enterprise policy.</span></span>  
1.  <span data-ttu-id="cfecf-112">開発者モードでローカルコンピューターから拡張機能ディレクトリを展開しました。</span><span class="sxs-lookup"><span data-stu-id="cfecf-112">Unpacked Extension directories from a local machine while in developer mode.</span></span>  

## <span data-ttu-id="cfecf-113">更新</span><span class="sxs-lookup"><span data-stu-id="cfecf-113">Updating</span></span>  

<span data-ttu-id="cfecf-114">Microsoft Edge ブラウザーでは、ユーザーの操作なしで、インストールされている拡張機能と更新プログラムの新しいバージョンが定期的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="cfecf-114">The Microsoft Edge browser periodically checks for new versions of installed Extensions and updates each without user intervention.</span></span>  

> [!NOTE]
> <span data-ttu-id="cfecf-115">Microsoft Edge のアドオンで拡張機能を更新する手順は計画されています。</span><span class="sxs-lookup"><span data-stu-id="cfecf-115">Steps to update an Extension on Microsoft Edge Addons are planned be added.</span></span>  

<!-- image links -->

<!-- links -->  

[MicrosoftStoreExtensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能-Microsoft Edge Insider アドオン"  

> [!NOTE]
> <span data-ttu-id="cfecf-117">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfecf-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cfecf-118">元のページは [ここ](https://developer.chrome.com/extensions/hosting)にあります。</span><span class="sxs-lookup"><span data-stu-id="cfecf-118">The original page is found [here](https://developer.chrome.com/extensions/hosting).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="cfecf-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="cfecf-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
