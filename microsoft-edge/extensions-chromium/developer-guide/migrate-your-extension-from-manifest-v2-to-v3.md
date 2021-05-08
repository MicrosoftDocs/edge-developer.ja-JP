---
description: マニフェスト V2 から V3 への拡張機能の更新の詳細
title: マニフェスト V2 から V3 への拡張機能の更新の準備
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, edge extensions, browser extensions, addons, developer, manifest v3, migrate to manifest v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117831"
---
# <span data-ttu-id="28100-104">マニフェスト v2 から v3 に拡張機能を更新する準備をする</span><span class="sxs-lookup"><span data-stu-id="28100-104">Prepare to update your extensions from Manifest v2 to v3</span></span> 

<span data-ttu-id="28100-105">このドキュメントでは、マニフェスト v3 の一部として実装されている重要な変更点を示します。これは、Chromium拡張機能プラットフォームの次のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="28100-105">This document lists important changes that's being implemented as part of Manifest v3, which is the next version of the Chromium Extensions platform.</span></span> <span data-ttu-id="28100-106">実装の進行に合わせ、このドキュメントを更新します。</span><span class="sxs-lookup"><span data-stu-id="28100-106">We'll update this document as the implementation progresses.</span></span> <span data-ttu-id="28100-107">マニフェスト v3 への拡張機能の移行に関する詳細なガイダンスについては、「マニフェスト V3 への移行」 [に移動します][Google_Migrate_to_MV3]。</span><span class="sxs-lookup"><span data-stu-id="28100-107">For detailed guidance on migrating your extension to Manifest v3, navigate to [Migrating to Manifest V3][Google_Migrate_to_MV3].</span></span> 

## <span data-ttu-id="28100-108">リモートでホストされるコード</span><span class="sxs-lookup"><span data-stu-id="28100-108">Remotely hosted code</span></span>  

<span data-ttu-id="28100-109">現在、拡張機能はコードの一部をリモートでホストし、検証プロセス中に拡張パッケージの一部として含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="28100-109">Today, extensions can host parts of their code remotely, and not include it as part of the extension package during the validation process.</span></span> <span data-ttu-id="28100-110">これにより、拡張機能をストアに再送信せずにコードを柔軟に変更することができますが、インストール後にコードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="28100-110">While this offers flexibility to change code without resubmitting the extension to the store, the code can be exploited after installation.</span></span> <span data-ttu-id="28100-111">アドオンリスト[Microsoft Edge検証][EdgeAddons]済み拡張機能を確認するために、拡張機能がリモートでホストされたコードを使用するのを禁止しています。</span><span class="sxs-lookup"><span data-stu-id="28100-111">To ensure [Microsoft Edge Add-ons][EdgeAddons] lists validated extensions, we're disallowing extensions from using remotely hosted code.</span></span> <span data-ttu-id="28100-112">この変更により、拡張機能のセキュリティが高くなっています。</span><span class="sxs-lookup"><span data-stu-id="28100-112">This change makes extensions more secure.</span></span> <span data-ttu-id="28100-113">開発者は、拡張機能で検証のために使用されるコードをパッケージ化して提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28100-113">Developers will need to package and submit all code that's used by the extension for validation.</span></span> <span data-ttu-id="28100-114">または、開発者はサンドボックス環境で eval() 関数 [を使用できます][sandboxingEval]。</span><span class="sxs-lookup"><span data-stu-id="28100-114">Alternatively, developers can use the eval() function in a [sandboxed environment][sandboxingEval].</span></span> 

## <span data-ttu-id="28100-115">実行時ホストのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="28100-115">Run-time host permissions</span></span>  

<span data-ttu-id="28100-116">インストール時に、拡張機能がすべてのサイトとコンテンツにアクセスするための一括アクセス許可を要求する場合があります。</span><span class="sxs-lookup"><span data-stu-id="28100-116">At installation time, extensions may request blanket permissions to access all sites and content.</span></span> <span data-ttu-id="28100-117">これらのアクセス許可により、拡張機能は最小限の介入で動作し、ユーザーのプライバシーとセキュリティに対するリスクを生み出します。</span><span class="sxs-lookup"><span data-stu-id="28100-117">These permissions allow extensions to operate with minimum intervention, and create a risk to user privacy and security.</span></span> <span data-ttu-id="28100-118">透明性を向上させるために、ユーザーが実行時に Web サイトへのアクセスを許可または制限するためのコントロールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="28100-118">To improve transparency, we're providing controls for users to allow or restrict access to websites at runtime.</span></span> 

## <span data-ttu-id="28100-119">コンテンツ スクリプトでのクロスオリジン要求</span><span class="sxs-lookup"><span data-stu-id="28100-119">Cross-origin requests in content scripts</span></span>  

<span data-ttu-id="28100-120">今日のコンテンツ スクリプトでは、Web サイトで許可されていないオリジンを含む任意のオリジンへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="28100-120">Today content scripts can request access to any origin including origins that aren't allowed by the website.</span></span> <span data-ttu-id="28100-121">この動作は、クロスオリジンの原則を壊します。</span><span class="sxs-lookup"><span data-stu-id="28100-121">This behavior breaks cross-origin principles.</span></span> <span data-ttu-id="28100-122">今後は、コンテンツ スクリプトが挿入するページと同じアクセス許可を持つ必要が生じ、潜在的なセキュリティの抜け穴を閉じます。</span><span class="sxs-lookup"><span data-stu-id="28100-122">Going forward, we'll require content scripts to have the same permissions as the page they're injected into, closing a potential security loophole.</span></span> <span data-ttu-id="28100-123">クロスオリジン要求を実行するには、バックグラウンド スクリプトを使用して応答をコンテンツ スクリプトに中継する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28100-123">To perform cross-origin requests, you'll need to use background scripts to relay responses back to content scripts.</span></span> <span data-ttu-id="28100-124">これらの変更は使用可能で、フラグの背後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28100-124">These changes are available and behind a flag.</span></span> <span data-ttu-id="28100-125">詳細については、このドキュメントに移動 [します][CORS]。</span><span class="sxs-lookup"><span data-stu-id="28100-125">For more information, navigate to this [document][CORS].</span></span> 

## <span data-ttu-id="28100-126">Web 要求 API</span><span class="sxs-lookup"><span data-stu-id="28100-126">Web Request API</span></span>  

<span data-ttu-id="28100-127">Web 要求 API を[Declarative Net Request][DeclarativeNetRequestAPI] [API][WebRequestAPI]に置き換える予定ですが、引き続き Web 要求 API の観測機能を維持します。</span><span class="sxs-lookup"><span data-stu-id="28100-127">We're replacing [Web Request API][WebRequestAPI] with [Declarative Net Request API][DeclarativeNetRequestAPI], but will continue to keep Web Request API's observational capabilities.</span></span> <span data-ttu-id="28100-128">拡張機能で Web 要求 API の観測機能が必要な特定のシナリオを除き、DNR API のみを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28100-128">Except in some specific scenarios where observational capabilities of the Web Request API are required by the extension, we recommend using the DNR APIs only.</span></span> <span data-ttu-id="28100-129">この変更は、機能豊富な宣言型機能を使用する拡張機能にプラスの影響を及ぼすと考えます。</span><span class="sxs-lookup"><span data-stu-id="28100-129">We believe this change will have positive impact on extensions that use feature-rich declarative capabilities.</span></span> <span data-ttu-id="28100-130">より多くの拡張機能が DNR API に移行すると、この変更によりユーザーのプライバシーが向上し、拡張機能の使用に対する信頼が向上します。</span><span class="sxs-lookup"><span data-stu-id="28100-130">As more extensions transition to the DNR APIs, this change will improve user privacy, which contributes to enhancing trust in the use of extensions.</span></span>
<span data-ttu-id="28100-131">企業は、エンタープライズ ポリシーによって管理される拡張機能に対して Web 要求 API のブロック動作を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="28100-131">Enterprises can continue to use the blocking behavior of the Web Request API for extensions managed through enterprise policies.</span></span> <span data-ttu-id="28100-132">拡張機能ポリシーの詳細については、「Microsoft Edge –[ポリシー」 に移動します][MicrosoftEdgePolicies]。</span><span class="sxs-lookup"><span data-stu-id="28100-132">For more information about extension policies, navigate to [Microsoft Edge – Policies][MicrosoftEdgePolicies].</span></span> 

## <span data-ttu-id="28100-133">バックグラウンド サービスワーカー</span><span class="sxs-lookup"><span data-stu-id="28100-133">Background service workers</span></span>  
 
<span data-ttu-id="28100-134">サービス ワーカーは、Canary でテストできます。</span><span class="sxs-lookup"><span data-stu-id="28100-134">Service workers are available for testing in Canary.</span></span> <span data-ttu-id="28100-135">拡張機能をバックグラウンド ページからサービス ワーカーに移行するには、「バックグラウンド ページからサービス ワーカーへの移行 [」を参照してください][ServiceWorkers]。</span><span class="sxs-lookup"><span data-stu-id="28100-135">To migrate your extensions from background pages to service workers, refer to [Migrating from Background Pages to Service Workers][ServiceWorkers].</span></span> <span data-ttu-id="28100-136">この変更が開発者&に与える影響を調査するために、この変更を評価しています。</span><span class="sxs-lookup"><span data-stu-id="28100-136">We're evaluating & investigating the impact that this change brings to both developers and users.</span></span> <span data-ttu-id="28100-137">この変更に関する詳細は、今後このドキュメントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="28100-137">We'll add  additional details on this change to this document in the future.</span></span> 

## <span data-ttu-id="28100-138">これらの変更は、このサイトでいつMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="28100-138">When will these changes be available in Microsoft Edge?</span></span>

<span data-ttu-id="28100-139">現在の宣言型ネット要求 API の実装は、Stable チャネルと Beta チャネルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="28100-139">The current declarative net request API implementation is available in our Stable and Beta channels.</span></span> <span data-ttu-id="28100-140">開発者は、これらの変更をテストし、フィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="28100-140">Developers can test these changes, and provide feedback.</span></span> <span data-ttu-id="28100-141">開発作業に貢献し、さらなる変更を調査します。</span><span class="sxs-lookup"><span data-stu-id="28100-141">We'll contribute to development efforts and investigate further changes.</span></span> 

| <span data-ttu-id="28100-142">チャネル名</span><span class="sxs-lookup"><span data-stu-id="28100-142">Channel name</span></span> | <span data-ttu-id="28100-143">説明</span><span class="sxs-lookup"><span data-stu-id="28100-143">Description</span></span> |
|:--- |:--- |  
| <span data-ttu-id="28100-144">Microsoft Edge 84 Stable</span><span class="sxs-lookup"><span data-stu-id="28100-144">Microsoft Edge 84 Stable</span></span> | <span data-ttu-id="28100-145">DNR API はテストに使用できます</span><span class="sxs-lookup"><span data-stu-id="28100-145">DNR API is available for testing</span></span> |  
| <span data-ttu-id="28100-146">Microsoft Edge 85 Beta</span><span class="sxs-lookup"><span data-stu-id="28100-146">Microsoft Edge 85 Beta</span></span> | <span data-ttu-id="28100-147">ヘッダー変更のサポートが利用可能</span><span class="sxs-lookup"><span data-stu-id="28100-147">Header modification support is available</span></span>| 

<span data-ttu-id="28100-148">この変更が変更されたChromium、開発者がコードを更新し、ストアに拡張機能を再発行できるよう、タイムラインを共有します。</span><span class="sxs-lookup"><span data-stu-id="28100-148">When the changes are made to Chromium, we'll share timelines so that developers can update their code and republish extensions to the store.</span></span> 

<span data-ttu-id="28100-149">引き続きブログで更新プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="28100-149">We'll continue publishing updates on our blog.</span></span> <span data-ttu-id="28100-150">これらの変更に関するフィードバックは [、TechCommunity を通じて提供できます][TechCommunity]。</span><span class="sxs-lookup"><span data-stu-id="28100-150">You can provide your feedback on these changes through [TechCommunity][TechCommunity].</span></span>

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edgeアドオン"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技術Community"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "Chrome 拡張機能で eval を使用する。安全に。"
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "拡張機能コンテンツ スクリプトでのクロスオリジン要求への変更"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 要求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "宣言型 Net Request API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


