---
ms.assetid: ''
description: 一定の期間安全に実験し、新しいプラットフォーム機能に関するフィードバックを提供します。
title: 元の試用版
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, origin trials, developer
ms.openlocfilehash: cc03ec556d4b32ca37cebcd4ee7ba155bfe4404b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397546"
---
# <a name="use-origin-trials-in-microsoft-edge"></a><span data-ttu-id="b82c5-104">Microsoft Edge で Origin Trials を使用する</span><span class="sxs-lookup"><span data-stu-id="b82c5-104">Use Origin Trials in Microsoft Edge</span></span>  

<span data-ttu-id="b82c5-105">開発者は、Origin Trials を使用して、限られた期間、ライブ サイトで実験的な API を試用できます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-105">Developers may use Origin Trials to try out experimental APIs on live sites for a limited period of time.</span></span>  <span data-ttu-id="b82c5-106">Origin Trials を使用する場合、サイトにアクセスした Microsoft Edge のユーザーは、実験的な API を使用するコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-106">When using Origin Trials, users of Microsoft Edge that visit your site may run code that uses experimental APIs.</span></span>  <span data-ttu-id="b82c5-107">各ユーザー コンピューター上の実験的な API にアクセスするには、機能フラグに移動して有効 `edge://flags` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b82c5-107">To access the experimental APIs on each user machine, you do not need to go to `edge://flags` and turn on feature flags.</span></span>  <span data-ttu-id="b82c5-108">詳細については、実験的な [API に移動します][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="b82c5-108">For more information, navigate to [experimental APIs][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="b82c5-109">さらに、API の設計、使用例、API の使用経験に関するフィードバックをブラウザー エンジニアや Web 標準コミュニティに提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-109">Additionally, you may provide feedback on the design of the API, your use cases, or your experience using the APIs to browser engineers and the web standard community.</span></span>  

## <a name="get-started-using-origin-trials"></a><span data-ttu-id="b82c5-110">Origin Trials の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b82c5-110">Get started using Origin Trials</span></span>  

<span data-ttu-id="b82c5-111">Microsoft Edge で使用できる実験的 API の詳細については [、「Microsoft Edge Origin Trials Developer Console」に移動します][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="b82c5-111">For more information about the experimental APIs available in Microsoft Edge, navigate to [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="b82c5-112">Microsoft Edge の最小バージョン要件と試用終了日を確認して、Web サイトで実験的な API を使用する適合性を評価してください。</span><span class="sxs-lookup"><span data-stu-id="b82c5-112">Ensure that you review the minimum version requirements for Microsoft Edge, and the trial end date to assess suitability of using the experimental APIs on your website.</span></span>  

> [!NOTE]
> <span data-ttu-id="b82c5-113">次の状況が発生した場合、実験は計画より早く終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b82c5-113">An experiment may end earlier than planned if any of the following situations occur.</span></span>  
> *   <span data-ttu-id="b82c5-114">大規模なセキュリティ インシデント。</span><span class="sxs-lookup"><span data-stu-id="b82c5-114">A major security incident.</span></span>  
> *   <span data-ttu-id="b82c5-115">Web 開発者のニーズを満たすために大幅な再設計が必要な十分なフィードバックが収集された場合。</span><span class="sxs-lookup"><span data-stu-id="b82c5-115">If sufficient feedback is collected that indicates a major redesign is needed to meet the needs of web developers.</span></span>  
> <span data-ttu-id="b82c5-116">いずれの場合も、テストに現在登録されているすべての開発者に通知メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-116">In either case, a notification email is sent to all developers currently enrolled in the experiment.</span></span>  

### <a name="register-for-a-trial-of-an-experimental-api"></a><span data-ttu-id="b82c5-117">実験的な API の試用版に登録する</span><span class="sxs-lookup"><span data-stu-id="b82c5-117">Register for a trial of an experimental API</span></span>  

<span data-ttu-id="b82c5-118">実験的な API の試用版に登録するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-118">Use the following steps to register for a trial of an experimental API.</span></span>  

1.  <span data-ttu-id="b82c5-119">Microsoft [Edge Origin Trials Developer Console ページにアクセス][DeveloperMicrsoftEdgeOriginTrials] します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-119">Visit the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  
1.  <span data-ttu-id="b82c5-120">使用可能な実験の [登録] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-120">Choose the Register button on any of the available experiments.</span></span>  
1.  <span data-ttu-id="b82c5-121">GitHub のユーザー名とパスワードを使用して開発者コンソールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b82c5-121">Sign into the Developer Console using your GitHub username and password.</span></span>  
1.  <span data-ttu-id="b82c5-122">**[MicrosoftEdge の承認] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b82c5-122">Choose **Authorize MicrosoftEdge**.</span></span>  
1.  <span data-ttu-id="b82c5-123">フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-123">Complete the form.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b82c5-124">単一またはすべてのサブドメインを登録するには、[設定] を [ に設定] `Do you need to match all subdomains for the provided origin?` を選択します `Yes` 。</span><span class="sxs-lookup"><span data-stu-id="b82c5-124">To enroll a single or all subdomains, choose set the `Do you need to match all subdomains for the provided origin?` setting to `Yes`.</span></span>  <span data-ttu-id="b82c5-125">たとえば、単 `https://dev.contoso.com` 一のドメインであり、ワイルドカード `https://*.contoso.com` を使用してすべてのサブドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-125">For example, `https://dev.contoso.com` is a single domain, and `https://*.contoso.com` uses a wildcard to represent all subdomains.</span></span>  
    
    > [!IMPORTANT]
    > <span data-ttu-id="b82c5-126">次の元の形式は使用されません。</span><span class="sxs-lookup"><span data-stu-id="b82c5-126">The following origin formats are not allowed.</span></span>  
    > *   <span data-ttu-id="b82c5-127">原点のサブフォルダーを指定する。</span><span class="sxs-lookup"><span data-stu-id="b82c5-127">Specifying a subfolder on the origin.</span></span>  <span data-ttu-id="b82c5-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-128">For example,</span></span> `https://contoso.com/path/subfolder`  
    > 
    > *   <span data-ttu-id="b82c5-129">クエリ文字列パラメーターでオリジンを使用する。</span><span class="sxs-lookup"><span data-stu-id="b82c5-129">Using an origin with query string parameters.</span></span>  <span data-ttu-id="b82c5-130">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-130">For example,</span></span> `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  <span data-ttu-id="b82c5-131">**[ACCEPT] と [登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b82c5-131">Choose **ACCEPT and REGISTER**.</span></span>  
    
### <a name="apply-your-token"></a><span data-ttu-id="b82c5-132">トークンを適用する</span><span class="sxs-lookup"><span data-stu-id="b82c5-132">Apply your token</span></span>  

<span data-ttu-id="b82c5-133">トークンは即座に生成され [、Microsoft Edge Origin Trials Developer Console ページに表示][DeveloperMicrsoftEdgeOriginTrials] されます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-133">A token is instantly generated and displayed on the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  <span data-ttu-id="b82c5-134">Web サイトで試用版の使用を開始するには、次のいずれかの方法でトークンをページに適用します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-134">To begin using the trial on your website, use either of the following methods to apply the token to your page.</span></span>  

*   <span data-ttu-id="b82c5-135">実験的 `origin-trial` な API を使用する各ページのタグに属性値とトークン `meta` を追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-135">Add the `origin-trial` attribute value and your token to the `meta` tag on every page that uses the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   <span data-ttu-id="b82c5-136">サーバー `Origin-Trial` の HTTP 応答ヘッダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-136">Add `Origin-Trial` to the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> <span data-ttu-id="b82c5-137">トークンは 6 週間有効です。</span><span class="sxs-lookup"><span data-stu-id="b82c5-137">Your token is valid for 6 weeks.</span></span>  <span data-ttu-id="b82c5-138">試用版が終了する前に、フィードバックを求める通知メールが送信され、トークンの有効期限が切れる前に試用版の更新を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b82c5-138">Before your trial ends, reminder emails are sent to you that ask for your feedback and ask you to consider renewing your trial before your token expires.</span></span>  

### <a name="opt-out-of-an-experiment"></a><span data-ttu-id="b82c5-139">実験をオプトアウトする</span><span class="sxs-lookup"><span data-stu-id="b82c5-139">Opt out of an experiment</span></span>  

<span data-ttu-id="b82c5-140">実験をオプトアウトするには、次のいずれかの方法を使用してトークンを削除します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-140">To opt out of an experiment, use one of the following methods to remove your token.</span></span>  

*   <span data-ttu-id="b82c5-141">実験 `meta` API を使用したページごとにタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-141">Remove the `meta` tag from every page that used the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   <span data-ttu-id="b82c5-142">サーバー `Origin-Trial` の HTTP 応答ヘッダーから削除します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-142">Remove `Origin-Trial` from the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <a name="detect-experimental-features-and-provide-a-fallback"></a><span data-ttu-id="b82c5-143">実験的な機能を検出し、フォールバックを提供する</span><span class="sxs-lookup"><span data-stu-id="b82c5-143">Detect experimental features and provide a fallback</span></span>  

<span data-ttu-id="b82c5-144">実験的な API を使用する場合は、Web サイトのすべての訪問者に作業エクスペリエンスを提供してください。</span><span class="sxs-lookup"><span data-stu-id="b82c5-144">When using experimental APIs, ensure you provide a working experience to all visitors of your website.</span></span>  <span data-ttu-id="b82c5-145">訪問者は、コードに追加した実験的な API をサポートしていないブラウザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b82c5-145">Visitors may use browsers that do not support the experimental APIs that you added to your code.</span></span>  <span data-ttu-id="b82c5-146">さらに、トークンを更新する前にトークンの有効期限が切れると、実験的な API は使用できなくなったので、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b82c5-146">Additionally, if your token expires before you renew it, the experimental API is no longer available which may result in errors.</span></span>  <span data-ttu-id="b82c5-147">このような状況を回避するには、ブラウザーで使用可能な機能を検出してください。</span><span class="sxs-lookup"><span data-stu-id="b82c5-147">To avoid this situation, ensure you detect features available in your browser.</span></span>  <span data-ttu-id="b82c5-148">詳細については、「機能検出の実装 [」に移動します][MDNImplementingFeatureDetection]。</span><span class="sxs-lookup"><span data-stu-id="b82c5-148">For more information, navigate to [Implementing feature detection][MDNImplementingFeatureDetection].</span></span>

### <a name="roadmap-for-allowed-origins"></a><span data-ttu-id="b82c5-149">許可されたオリジンのロードマップ</span><span class="sxs-lookup"><span data-stu-id="b82c5-149">Roadmap for Allowed Origins</span></span>  

<span data-ttu-id="b82c5-150">今日の Microsoft Edge Origin Trials ポータルでは SSL Enabled Origins のみをサポートしています。つまり、テストに登録するには、WEB サイトに HTTPS が適切に実装されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b82c5-150">The Microsoft Edge Origin Trials portal today only supports SSL Enabled Origins, which means that websites must have HTTPS properly implemented to register for an experiment.</span></span>  <span data-ttu-id="b82c5-151">将来、次のセキュリティで保護された発生元が計画されています。</span><span class="sxs-lookup"><span data-stu-id="b82c5-151">In the future, the following secure origins are planned.</span></span>  

*   <span data-ttu-id="b82c5-152">実験 `http://localhost` の原点として登録します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-152">Register `http://localhost` as the origin for your experiments.</span></span>  <span data-ttu-id="b82c5-153">今日使用 `http://localhost` するには、実験に移動 `edge://flags` して [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="b82c5-153">To use `http://localhost` today, navigate to `edge://flags` and set the experiment to **Enabled**.</span></span>  
*   <span data-ttu-id="b82c5-154">プレフィックスが付いたオ `extensions://` リジンを持つ拡張機能を使用して、実験に登録します。</span><span class="sxs-lookup"><span data-stu-id="b82c5-154">Use extensions with `extensions://` prefixed origins to enroll in experiments.</span></span>  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge Origin Trials Developer Console |Microsoft Docs"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "機能検出機能の実装|MDN"  
