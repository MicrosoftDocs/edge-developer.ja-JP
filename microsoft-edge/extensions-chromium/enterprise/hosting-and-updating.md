---
description: Microsoft Edge (Chromium) の企業で拡張機能をホストおよび公開します。
title: Microsoft Edge アドオン ストアでの拡張機能の公開と更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 91fdd5c2f625890653085e8999da3e513b072348
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327688"
---
# <span data-ttu-id="b0659-104">Microsoft Edge アドオン ストアでの拡張機能の公開と更新</span><span class="sxs-lookup"><span data-stu-id="b0659-104">Publish and update extensions in the Microsoft Edge Add-ons store</span></span>  

<span data-ttu-id="b0659-105">ほとんどの拡張機能は、悪意のある拡張機能からユーザーを保護するために [Microsoft Edge アドオン][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] ストアに公開されます。</span><span class="sxs-lookup"><span data-stu-id="b0659-105">Most extensions are published to the [Microsoft Edge Add-ons store][MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions] to protect users from malicious extensions.</span></span>  

## <span data-ttu-id="b0659-106">拡張機能の公開オプション</span><span class="sxs-lookup"><span data-stu-id="b0659-106">Publish options for extensions</span></span>  

<span data-ttu-id="b0659-107">すべての拡張子は、サフィックス付き特別なアーカイブ `.zip` \( \) ファイルとしてユーザーに配布 `.crx` されます。</span><span class="sxs-lookup"><span data-stu-id="b0659-107">All extensions are distributed to users as a special archive \(`.zip`\) file with a `.crx` suffix.</span></span>  <span data-ttu-id="b0659-108">Microsoft Edge アドオン ストアに公開された拡張機能は、ファイルとしてアップロード `.zip` されます。</span><span class="sxs-lookup"><span data-stu-id="b0659-108">Extensions published to the Microsoft Edge Add-ons store are uploaded as `.zip` files.</span></span>  <span data-ttu-id="b0659-109">発行プロセスでは、ファイルがファイル `.zip` に自動的に変換 `.crx` されます。</span><span class="sxs-lookup"><span data-stu-id="b0659-109">The publishing process automatically converts the `.zip` file into a `.crx` file.</span></span>  

<span data-ttu-id="b0659-110">次の 2 つのシナリオでは、Microsoft Edge アドオン ストアで拡張機能を公開する必要が生じることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0659-110">The following two scenarios don't require you to publish your extension in the Microsoft Edge Add-ons store.</span></span>  

*   <span data-ttu-id="b0659-111">エンタープライズ ポリシーを使用して配布される拡張機能。</span><span class="sxs-lookup"><span data-stu-id="b0659-111">Extensions distributed using Enterprise policy.</span></span>  
*   <span data-ttu-id="b0659-112">Microsoft Edge が開発者モードの場合に、ローカル コンピューターで展開されていない拡張ディレクトリを使用する。</span><span class="sxs-lookup"><span data-stu-id="b0659-112">Using unpacked extension directories on a local machine when Microsoft Edge is in developer mode.</span></span>  

## <span data-ttu-id="b0659-113">拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="b0659-113">Updates to extensions</span></span>

<span data-ttu-id="b0659-114">Microsoft Edge ブラウザーは、インストールされている拡張機能の新しいバージョンを定期的にチェックし、ユーザーの介入なしに各拡張機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="b0659-114">The Microsoft Edge browser periodically checks for new versions of installed extensions and updates each without user intervention.</span></span>  

<!-- links -->  

[MicrosoftMicrosoftedgeInsiderAddonsEdgeextensions]: https://microsoftedge.microsoft.com/insider-addons/category/EdgeExtensions "拡張機能 - Microsoft Edge Insider アドオン |Microsoft"  

> [!NOTE]
> <span data-ttu-id="b0659-116">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="b0659-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b0659-117">元のページはここ [です](https://developer.chrome.com/extensions/hosting)。</span><span class="sxs-lookup"><span data-stu-id="b0659-117">The original page is found [here](https://developer.chrome.com/extensions/hosting).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b0659-119">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b0659-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
