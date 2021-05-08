---
description: エンタープライズ内の拡張機能をホストして公開する (Microsoft Edge) (Chromium)。
title: アドオン ストアで拡張機能Microsoft Edge更新する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 2249462b0a2dac86efa4b775171e2a3229a34431
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461221"
---
# <a name="publish-and-update-extensions-in-the-microsoft-edge-add-ons-store"></a><span data-ttu-id="ab1d2-104">アドオン ストアで拡張機能Microsoft Edge更新する</span><span class="sxs-lookup"><span data-stu-id="ab1d2-104">Publish and update extensions in the Microsoft Edge Add-ons store</span></span>  

<span data-ttu-id="ab1d2-105">ほとんどの拡張機能は、悪意のあるMicrosoft Edge[から][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]ユーザーを保護するために、アドオン ストアに発行されます。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-105">Most extensions are published to the [Microsoft Edge Add-ons store][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] to protect users from malicious extensions.</span></span>  

## <a name="publish-options-for-extensions"></a><span data-ttu-id="ab1d2-106">拡張機能の発行オプション</span><span class="sxs-lookup"><span data-stu-id="ab1d2-106">Publish options for extensions</span></span>  

<span data-ttu-id="ab1d2-107">すべての拡張子は、接尾辞付き特別なアーカイブ \( `.zip` \) ファイルとしてユーザーに配布 `.crx` されます。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-107">All extensions are distributed to users as a special archive \(`.zip`\) file with a `.crx` suffix.</span></span>  <span data-ttu-id="ab1d2-108">アドオン ストアに発行Microsoft Edge拡張機能はファイルとしてアップロード `.zip` されます。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-108">Extensions published to the Microsoft Edge Add-ons store are uploaded as `.zip` files.</span></span>  <span data-ttu-id="ab1d2-109">発行プロセスは、ファイルをファイル `.zip` に自動的に変換 `.crx` します。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-109">The publishing process automatically converts the `.zip` file into a `.crx` file.</span></span>  

<span data-ttu-id="ab1d2-110">次の 2 つのシナリオでは、アドオン ストアで拡張機能を発行Microsoft Edge必要としません。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-110">The following two scenarios don't require you to publish your extension in the Microsoft Edge Add-ons store.</span></span>  

*   <span data-ttu-id="ab1d2-111">ポリシーを使用して配布Enterprise拡張機能。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-111">Extensions distributed using Enterprise policy.</span></span>  
*   <span data-ttu-id="ab1d2-112">開発者モードの場合は、ローカル コンピューターで展開Microsoft Edgeディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-112">Using unpacked extension directories on a local machine when Microsoft Edge is in developer mode.</span></span>  

## <a name="updates-to-extensions"></a><span data-ttu-id="ab1d2-113">拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="ab1d2-113">Updates to extensions</span></span>

<span data-ttu-id="ab1d2-114">このMicrosoft Edgeブラウザーは、インストールされている拡張機能の新しいバージョンを自動的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-114">The Microsoft Edge browser automatically checks for new versions of installed Extensions.</span></span> <span data-ttu-id="ab1d2-115">更新プログラムは、ユーザーの介入なしにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-115">Updates are installed without user intervention.</span></span>  


<!-- image links -->

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能 - Insider Microsoft Edge アドオン |Microsoft"  

> [!NOTE]
> <span data-ttu-id="ab1d2-117">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ab1d2-118">元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/hosting)。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-118">The original page is found [here](https://developer.chrome.com/extensions/hosting).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ab1d2-120">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ab1d2-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
