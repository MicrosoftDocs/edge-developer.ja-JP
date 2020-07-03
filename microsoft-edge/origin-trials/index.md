---
ms.assetid: ''
description: 一定期間、安全なテストを行い、新しいプラットフォーム機能についてフィードバックを提供します。
title: オリジン試用版
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、元の試用、開発者
ms.openlocfilehash: 470896435ab348419749a7de00adcdb83b784df3
ms.sourcegitcommit: 5cbc9237363b3a8ba212ca128aa03c71a33ec86f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "10846529"
---
# <span data-ttu-id="232b0-104">Microsoft Edge で元の試用版を使用する</span><span class="sxs-lookup"><span data-stu-id="232b0-104">Use Origin Trials in Microsoft Edge</span></span>  

<span data-ttu-id="232b0-105">開発者は、一定期間、実際のサイトで実験的な Api を試すために、オリジンの試用版を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-105">Developers may use Origin Trials to try out experimental APIs on live sites for a limited period of time.</span></span>  <span data-ttu-id="232b0-106">元の試用版を使用している場合、サイトにアクセスする Microsoft Edge のユーザーは、実験的な Api を使うコードを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-106">When using Origin Trials, users of Microsoft Edge that visit your site may run code that uses experimental APIs.</span></span>  <span data-ttu-id="232b0-107">各ユーザーコンピューターの実験的な Api にアクセスするには、機能のフラグを設定して有効にする必要はありません `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="232b0-107">To access the experimental APIs on each user machine, you do not need to go to `edge://flags` and turn on feature flags.</span></span>  <span data-ttu-id="232b0-108">詳しくは、「[実験的な api][DeveloperMicrsoftEdgeOriginTrials]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="232b0-108">For more information, see [experimental APIs][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="232b0-109">さらに、API の設計、ユースケース、または Api を使用したブラウザーエンジニアと web standard コミュニティのエクスペリエンスについて、フィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="232b0-109">Additionally, you may provide feedback on the design of the API, your use cases, or your experience using the APIs to browser engineers and the web standard community.</span></span>  

## <span data-ttu-id="232b0-110">元の試用版の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="232b0-110">Get started using Origin Trials</span></span>  

<span data-ttu-id="232b0-111">Microsoft Edge で利用できる実験的な Api の詳細については、 [Microsoft Edge オリジンの試用版の開発者コンソール][DeveloperMicrsoftEdgeOriginTrials]に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="232b0-111">For more information about the experimental APIs available in Microsoft Edge, see [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="232b0-112">Web サイトで実験的な Api を使うことができないかどうかを評価するには、Microsoft Edge の最小バージョン要件とトライアル終了日を確認してください。</span><span class="sxs-lookup"><span data-stu-id="232b0-112">Ensure that you review the minimum version requirements for Microsoft Edge, and the trial end date to assess suitability of using the experimental APIs on your website.</span></span>  

> [!NOTE]
> <span data-ttu-id="232b0-113">次のいずれかの状況が発生した場合、実験は計画よりも早く終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-113">An experiment may end earlier than planned if any of the following situations occur.</span></span>  
> *   <span data-ttu-id="232b0-114">重大なセキュリティインシデント。</span><span class="sxs-lookup"><span data-stu-id="232b0-114">A major security incident.</span></span>  
> *   <span data-ttu-id="232b0-115">十分なフィードバックが収集された場合は、web 開発者のニーズを満たすために大きな再設計が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="232b0-115">If sufficient feedback is collected that indicates a major redesign is needed to meet the needs of web developers.</span></span>  
> <span data-ttu-id="232b0-116">どちらの場合も、実験に現在登録されているすべての開発者に通知メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="232b0-116">In either case, a notification email is sent to all developers currently enrolled in the experiment.</span></span>  

### <span data-ttu-id="232b0-117">実験的な API の試用版に登録する</span><span class="sxs-lookup"><span data-stu-id="232b0-117">Register for a trial of an experimental API</span></span>  

<span data-ttu-id="232b0-118">実験的な API の試用版を登録するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="232b0-118">Use the following steps to register for a trial of an experimental API.</span></span>  

1.  <span data-ttu-id="232b0-119">[Microsoft Edge の [試用版の開発者用コンソール][DeveloperMicrsoftEdgeOriginTrials]] ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="232b0-119">Visit the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  
1.  <span data-ttu-id="232b0-120">利用可能な実験のいずれかで [登録] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="232b0-120">Choose the Register button on any of the available experiments.</span></span>  
1.  <span data-ttu-id="232b0-121">GitHub のユーザー名とパスワードを使って、開発者コンソールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="232b0-121">Sign into the Developer Console using your GitHub username and password.</span></span>  
1.  <span data-ttu-id="232b0-122">[**承認 MicrosoftEdge**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="232b0-122">Choose **Authorize MicrosoftEdge**.</span></span>  
1.  <span data-ttu-id="232b0-123">フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="232b0-123">Complete the form.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="232b0-124">1つまたはすべてのサブドメインを登録するには、[設定の設定] `Do you need to match all subdomains for the provided origin?` を選び `Yes` ます。</span><span class="sxs-lookup"><span data-stu-id="232b0-124">To enroll a single or all subdomains, choose set the `Do you need to match all subdomains for the provided origin?` setting to `Yes`.</span></span>  <span data-ttu-id="232b0-125">たとえば、 `https://dev.contoso.com` は単一ドメインであり、ワイルドカードを使ってすべてのサブドメインを `https://*.contoso.com` 表します。</span><span class="sxs-lookup"><span data-stu-id="232b0-125">For example, `https://dev.contoso.com` is a single domain, and `https://*.contoso.com` uses a wildcard to represent all subdomains.</span></span>  
    
    > [!IMPORTANT]
    > <span data-ttu-id="232b0-126">次の元の形式は使用できません。</span><span class="sxs-lookup"><span data-stu-id="232b0-126">The following origin formats are not allowed.</span></span>  
    > *   <span data-ttu-id="232b0-127">元のサブフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="232b0-127">Specifying a subfolder on the origin.</span></span>  <span data-ttu-id="232b0-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="232b0-128">For example,</span></span> `https://contoso.com/path/subfolder`  
    > 
    > *   <span data-ttu-id="232b0-129">クエリ文字列パラメーターでの原点の使用。</span><span class="sxs-lookup"><span data-stu-id="232b0-129">Using an origin with query string parameters.</span></span>  <span data-ttu-id="232b0-130">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="232b0-130">For example,</span></span> `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  <span data-ttu-id="232b0-131">[**承諾して登録**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="232b0-131">Choose **ACCEPT and REGISTER**.</span></span>  

### <span data-ttu-id="232b0-132">トークンを適用する</span><span class="sxs-lookup"><span data-stu-id="232b0-132">Apply your token</span></span>  

<span data-ttu-id="232b0-133">トークンはすぐに生成され、 [Microsoft Edge の [開発者向け] 本体][DeveloperMicrsoftEdgeOriginTrials]のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="232b0-133">A token is instantly generated and displayed on the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  <span data-ttu-id="232b0-134">Web サイトの試用版の使用を開始するには、次のいずれかの方法を使用して、トークンをページに適用します。</span><span class="sxs-lookup"><span data-stu-id="232b0-134">To begin using the trial on your website, use either of the following methods to apply the token to your page.</span></span>  

*   <span data-ttu-id="232b0-135">`origin-trial` `meta` 実験的 API を使用するすべてのページで、属性値とトークンをタグに追加します。</span><span class="sxs-lookup"><span data-stu-id="232b0-135">Add the `origin-trial` attribute value and your token to the `meta` tag on every page that uses the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   <span data-ttu-id="232b0-136">`Origin-Trial`サーバーの HTTP 応答ヘッダーにを追加します。</span><span class="sxs-lookup"><span data-stu-id="232b0-136">Add `Origin-Trial` to the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> <span data-ttu-id="232b0-137">トークンは6週間有効です。</span><span class="sxs-lookup"><span data-stu-id="232b0-137">Your token is valid for 6 weeks.</span></span>  <span data-ttu-id="232b0-138">試用期間が終了する前に、フィードバックを求めるメッセージが送信され、トークンの有効期限が切れる前に試用版の更新を検討するように求められます。</span><span class="sxs-lookup"><span data-stu-id="232b0-138">Before your trial ends, reminder emails are sent to you that ask for your feedback and ask you to consider renewing your trial before your token expires.</span></span>  

### <span data-ttu-id="232b0-139">実験をやめる</span><span class="sxs-lookup"><span data-stu-id="232b0-139">Opt out of an experiment</span></span>  

<span data-ttu-id="232b0-140">試験的機能を無効にするには、次のいずれかの方法を使用してトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="232b0-140">To opt out of an experiment, use one of the following methods to remove your token.</span></span>  

*   <span data-ttu-id="232b0-141">`meta`実験的 API を使用したすべてのページからタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="232b0-141">Remove the `meta` tag from every page that used the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   <span data-ttu-id="232b0-142">`Origin-Trial`サーバーの HTTP 応答ヘッダーから削除します。</span><span class="sxs-lookup"><span data-stu-id="232b0-142">Remove `Origin-Trial` from the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <span data-ttu-id="232b0-143">実験的な機能を検出し、フォールバックを提供する</span><span class="sxs-lookup"><span data-stu-id="232b0-143">Detect experimental features and provide a fallback</span></span>  

<span data-ttu-id="232b0-144">実験的 Api を使用している場合は、web サイトの全利用者に対して動作環境を提供していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="232b0-144">When using experimental APIs, ensure you provide a working experience to all visitors of your website.</span></span>  <span data-ttu-id="232b0-145">閲覧者は、コードに追加した実験的 Api をサポートしていないブラウザーを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-145">Visitors may use browsers that do not support the experimental APIs that you added to your code.</span></span>  <span data-ttu-id="232b0-146">さらに、更新前にトークンの有効期限が切れた場合、実験的 API は使用できなくなり、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-146">Additionally, if your token expires before you renew it, the experimental API is no longer available which may result in errors.</span></span>  <span data-ttu-id="232b0-147">この問題を回避するには、ブラウザーで利用できる機能を検出していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="232b0-147">To avoid this situation, ensure you detect features available in your browser.</span></span>  <span data-ttu-id="232b0-148">詳しくは、「[機能の検出の実装][MDNImplementingFeatureDetection]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="232b0-148">For more information, see [Implementing feature detection][MDNImplementingFeatureDetection].</span></span>

### <span data-ttu-id="232b0-149">許可元のロードマップ</span><span class="sxs-lookup"><span data-stu-id="232b0-149">Roadmap for Allowed Origins</span></span>  

<span data-ttu-id="232b0-150">Microsoft Edge オリジンの試用版ポータルでは、現時点では SSL を有効にした元のサイトのみがサポートされています。つまり、実験の登録に HTTPS が適切に実装されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="232b0-150">The Microsoft Edge Origin Trials portal today only supports SSL Enabled Origins, which means that websites must have HTTPS properly implemented to register for an experiment.</span></span>  <span data-ttu-id="232b0-151">今後、次のセキュリティ保護元が計画されています。</span><span class="sxs-lookup"><span data-stu-id="232b0-151">In the future, the following secure origins are planned.</span></span>  

*   <span data-ttu-id="232b0-152">`http://localhost`実験の起点として登録します。</span><span class="sxs-lookup"><span data-stu-id="232b0-152">Register `http://localhost` as the origin for your experiments.</span></span>  <span data-ttu-id="232b0-153">今日を使用するには `http://localhost` 、に移動 `edge://flags` して、実験を [**有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="232b0-153">To use `http://localhost` today, go to `edge://flags` and set the experiment to **Enabled**.</span></span>  
*   <span data-ttu-id="232b0-154">"元の拡張子" というプレフィックスを使用して、試験的機能 `extensions://` に登録します。</span><span class="sxs-lookup"><span data-stu-id="232b0-154">Use extensions with `extensions://` prefixed origins to enroll in experiments.</span></span>  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge オリジン試用開発者コンソール |Microsoft ドキュメント"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "機能検出の実装 |MDN"  
