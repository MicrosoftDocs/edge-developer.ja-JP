---
description: マニフェスト V2 から V3 への拡張機能の更新について説明します。
title: マニフェスト V2 から V3 に拡張機能を更新するための準備をする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: エッジ chromium、拡張機能開発、edge extensions、ブラウザー拡張機能、アドオン、開発者、マニフェスト v3、マニフェスト v3 への移行
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117831"
---
# <span data-ttu-id="39cd0-104">マニフェスト v2 から v3 に拡張機能を更新するための準備をする</span><span class="sxs-lookup"><span data-stu-id="39cd0-104">Prepare to update your extensions from Manifest v2 to v3</span></span> 

<span data-ttu-id="39cd0-105">このドキュメントでは、Chromium Extensions プラットフォームの次のバージョンである、マニフェスト v3 の一部として実装されている重要な変更を示します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-105">This document lists important changes that's being implemented as part of Manifest v3, which is the next version of the Chromium Extensions platform.</span></span> <span data-ttu-id="39cd0-106">このドキュメントは、実装の進行に応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-106">We'll update this document as the implementation progresses.</span></span> <span data-ttu-id="39cd0-107">拡張機能をマニフェスト v3 に移行する方法の詳細については、「 [マニフェスト v3 への移行][Google_Migrate_to_MV3]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cd0-107">For detailed guidance on migrating your extension to Manifest v3, navigate to [Migrating to Manifest V3][Google_Migrate_to_MV3].</span></span> 

## <span data-ttu-id="39cd0-108">リモートでホストされるコード</span><span class="sxs-lookup"><span data-stu-id="39cd0-108">Remotely hosted code</span></span>  

<span data-ttu-id="39cd0-109">現時点では、拡張機能は、コードの一部をリモートでホストすることができます。また、検証プロセス中に拡張機能パッケージの一部として含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="39cd0-109">Today, extensions can host parts of their code remotely, and not include it as part of the extension package during the validation process.</span></span> <span data-ttu-id="39cd0-110">この方法では、拡張機能をストアに再送信せずにコードを変更する柔軟性が提供されますが、インストール後にコードを悪用することができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-110">While this offers flexibility to change code without resubmitting the extension to the store, the code can be exploited after installation.</span></span> <span data-ttu-id="39cd0-111">[Microsoft Edge アドオン][EdgeAddons]に、検証済みの拡張機能を表示させるには、リモートでホストされているコードの使用を禁止します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-111">To ensure [Microsoft Edge Add-ons][EdgeAddons] lists validated extensions, we're disallowing extensions from using remotely hosted code.</span></span> <span data-ttu-id="39cd0-112">この変更により、拡張機能が強化されます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-112">This change makes extensions more secure.</span></span> <span data-ttu-id="39cd0-113">開発者は、検証のために拡張機能によって使用されるすべてのコードをパッケージ化して送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39cd0-113">Developers will need to package and submit all code that's used by the extension for validation.</span></span> <span data-ttu-id="39cd0-114">または、開発者は、 [サンドボックス環境][sandboxingEval]で eval () 関数を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-114">Alternatively, developers can use the eval() function in a [sandboxed environment][sandboxingEval].</span></span> 

## <span data-ttu-id="39cd0-115">実行時のホストのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="39cd0-115">Run-time host permissions</span></span>  

<span data-ttu-id="39cd0-116">インストール時に、拡張機能で、すべてのサイトとコンテンツにアクセスするための一括アクセス許可を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-116">At installation time, extensions may request blanket permissions to access all sites and content.</span></span> <span data-ttu-id="39cd0-117">これらのアクセス許可では、最小限の操作で拡張機能を使用し、ユーザーのプライバシーとセキュリティに対するリスクを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-117">These permissions allow extensions to operate with minimum intervention, and create a risk to user privacy and security.</span></span> <span data-ttu-id="39cd0-118">透過性を高めるために、ユーザーが実行時に web サイトへのアクセスを許可または制限するためのコントロールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="39cd0-118">To improve transparency, we're providing controls for users to allow or restrict access to websites at runtime.</span></span> 

## <span data-ttu-id="39cd0-119">コンテンツスクリプトでの cross-origin 要求</span><span class="sxs-lookup"><span data-stu-id="39cd0-119">Cross-origin requests in content scripts</span></span>  

<span data-ttu-id="39cd0-120">今日のコンテンツスクリプトでは、web サイトで許可されていない元のものを含む、任意の起点へのアクセスを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-120">Today content scripts can request access to any origin including origins that aren't allowed by the website.</span></span> <span data-ttu-id="39cd0-121">この動作により、クロスオリジンの原則が中断します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-121">This behavior breaks cross-origin principles.</span></span> <span data-ttu-id="39cd0-122">今後は、コンテンツスクリプトが挿入されたページと同じアクセス許可を持つようにする必要があります。これにより、潜在的なセキュリティ loophole が終了します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-122">Going forward, we'll require content scripts to have the same permissions as the page they're injected into, closing a potential security loophole.</span></span> <span data-ttu-id="39cd0-123">クロスオリジン要求を実行するには、バックグラウンドスクリプトを使用して、応答をコンテンツスクリプトに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="39cd0-123">To perform cross-origin requests, you'll need to use background scripts to relay responses back to content scripts.</span></span> <span data-ttu-id="39cd0-124">これらの変更は、フラグと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-124">These changes are available and behind a flag.</span></span> <span data-ttu-id="39cd0-125">詳細については、この [ドキュメント][CORS]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="39cd0-125">For more information, navigate to this [document][CORS].</span></span> 

## <span data-ttu-id="39cd0-126">Web 要求 API</span><span class="sxs-lookup"><span data-stu-id="39cd0-126">Web Request API</span></span>  

<span data-ttu-id="39cd0-127">[Web 要求 api][WebRequestAPI]は[宣言型のネット要求 api][DeclarativeNetRequestAPI]に置き換えていますが、引き続き web 要求 api の observational 機能は維持されます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-127">We're replacing [Web Request API][WebRequestAPI] with [Declarative Net Request API][DeclarativeNetRequestAPI], but will continue to keep Web Request API's observational capabilities.</span></span> <span data-ttu-id="39cd0-128">ただし、Web 要求 API の observational 機能が拡張機能で必要となる特定のシナリオについては、「Api のみを使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39cd0-128">Except in some specific scenarios where observational capabilities of the Web Request API are required by the extension, we recommend using the DNR APIs only.</span></span> <span data-ttu-id="39cd0-129">この変更は、機能豊富な宣言機能を使用する拡張機能に対してプラスの影響を与えると思われます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-129">We believe this change will have positive impact on extensions that use feature-rich declarative capabilities.</span></span> <span data-ttu-id="39cd0-130">この変更により、この変更によって、拡張機能の使用に対する信頼が強化され、ユーザーのプライバシーが向上します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-130">As more extensions transition to the DNR APIs, this change will improve user privacy, which contributes to enhancing trust in the use of extensions.</span></span>
<span data-ttu-id="39cd0-131">エンタープライズポリシーによって管理される拡張機能については、企業は引き続き Web 要求 API のブロッキング動作を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-131">Enterprises can continue to use the blocking behavior of the Web Request API for extensions managed through enterprise policies.</span></span> <span data-ttu-id="39cd0-132">拡張ポリシーの詳細については、「 [Microsoft Edge –ポリシー][MicrosoftEdgePolicies]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cd0-132">For more information about extension policies, navigate to [Microsoft Edge – Policies][MicrosoftEdgePolicies].</span></span> 

## <span data-ttu-id="39cd0-133">バックグラウンドサービスのワーカー</span><span class="sxs-lookup"><span data-stu-id="39cd0-133">Background service workers</span></span>  
 
<span data-ttu-id="39cd0-134">サービスワーカーは、カナリアでテストできます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-134">Service workers are available for testing in Canary.</span></span> <span data-ttu-id="39cd0-135">拡張機能をバックグラウンドページからサービスワーカーに移行する方法については、「 [バックグラウンドページからサービスワーカーへの移行][ServiceWorkers]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39cd0-135">To migrate your extensions from background pages to service workers, refer to [Migrating from Background Pages to Service Workers][ServiceWorkers].</span></span> <span data-ttu-id="39cd0-136">この変更が開発者とユーザーの両方にもたらす影響を調査 & 検討しています。</span><span class="sxs-lookup"><span data-stu-id="39cd0-136">We're evaluating & investigating the impact that this change brings to both developers and users.</span></span> <span data-ttu-id="39cd0-137">この変更についての詳細は、今後このドキュメントに追加します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-137">We'll add  additional details on this change to this document in the future.</span></span> 

## <span data-ttu-id="39cd0-138">Microsoft Edge でこれらの変更を利用できるようになるのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="39cd0-138">When will these changes be available in Microsoft Edge?</span></span>

<span data-ttu-id="39cd0-139">現在の宣言型の net 要求 API の実装は、microsoft の安定性とベータチャネルで利用できます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-139">The current declarative net request API implementation is available in our Stable and Beta channels.</span></span> <span data-ttu-id="39cd0-140">開発者は、これらの変更をテストし、フィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="39cd0-140">Developers can test these changes, and provide feedback.</span></span> <span data-ttu-id="39cd0-141">開発作業に貢献し、さらに変更を調査します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-141">We'll contribute to development efforts and investigate further changes.</span></span> 

| <span data-ttu-id="39cd0-142">チャネル名</span><span class="sxs-lookup"><span data-stu-id="39cd0-142">Channel name</span></span> | <span data-ttu-id="39cd0-143">説明</span><span class="sxs-lookup"><span data-stu-id="39cd0-143">Description</span></span> |
|:--- |:--- |  
| <span data-ttu-id="39cd0-144">Microsoft Edge 84 (安定)</span><span class="sxs-lookup"><span data-stu-id="39cd0-144">Microsoft Edge 84 Stable</span></span> | <span data-ttu-id="39cd0-145">確認のためのお勧め API を使用できます</span><span class="sxs-lookup"><span data-stu-id="39cd0-145">DNR API is available for testing</span></span> |  
| <span data-ttu-id="39cd0-146">Microsoft Edge 85 ベータ版</span><span class="sxs-lookup"><span data-stu-id="39cd0-146">Microsoft Edge 85 Beta</span></span> | <span data-ttu-id="39cd0-147">ヘッダー変更のサポートを利用できます</span><span class="sxs-lookup"><span data-stu-id="39cd0-147">Header modification support is available</span></span>| 

<span data-ttu-id="39cd0-148">Chromium に変更が加えられた場合は、タイムラインを共有して、開発者がコードを更新したり、ストアの拡張機能を再発行したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="39cd0-148">When the changes are made to Chromium, we'll share timelines so that developers can update their code and republish extensions to the store.</span></span> 

<span data-ttu-id="39cd0-149">引き続き、弊社のブログに更新プログラムを公開します。</span><span class="sxs-lookup"><span data-stu-id="39cd0-149">We'll continue publishing updates on our blog.</span></span> <span data-ttu-id="39cd0-150">このような変更については、「」 [コミュニティ][TechCommunity]を通じてお客様にご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="39cd0-150">You can provide your feedback on these changes through [TechCommunity][TechCommunity].</span></span>

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edge アドオン"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技術コミュニティ"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "Chrome の拡張機能で eval を使います。なく."
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "拡張コンテンツスクリプトでの cross-origin 要求の変更"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 要求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "宣言型ネットワーク要求 API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


