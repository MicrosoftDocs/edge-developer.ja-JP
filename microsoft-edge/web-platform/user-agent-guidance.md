---
description: この記事では、ユーザー エージェント クライアント Microsoft Edgeおよびユーザー エージェント文字列に関するドキュメントを提供します。
title: Web サイトのMicrosoft Edge検出する方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、Web プラットフォーム、ユーザー エージェント文字列、ua 文字列、ua オーバーライド、ユーザー エージェント クライアント ヒント、ユーザー エージェント クライアント ヒント、ua クライアント ヒント、ua ch
ms.openlocfilehash: 1957bb5bd33d9d921d8a12e16a4a52a23836027b
ms.sourcegitcommit: e90bbc210b5d510004bbc2145d49e14fe72ed54b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "11578781"
---
# <a name="how-to-detect-microsoft-edge-in-your-website"></a><span data-ttu-id="8efa1-104">Web サイトのMicrosoft Edge検出する方法</span><span class="sxs-lookup"><span data-stu-id="8efa1-104">How to detect Microsoft Edge in your website</span></span>  

<span data-ttu-id="8efa1-105">ブラウザーは、Web サイトがブランドやバージョン番号などのブラウザー情報を検出するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-105">Browsers provide mechanisms for websites to detect browser information such as brand and version number.</span></span>  <span data-ttu-id="8efa1-106">このメカニズムは、ホスト オペレーティング システムなどの他のデバイス特性も検出します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-106">The mechanisms also detect other device characteristics like the host operating system.</span></span>  <span data-ttu-id="8efa1-107">ユーザー エージェントでサポートされる 2 つのMicrosoft Edgeは[、User-Agent クライアント](#user-agent-client-hints)ヒントと[User-Agent 文字列です](#user-agent-string)。</span><span class="sxs-lookup"><span data-stu-id="8efa1-107">Two such mechanisms supported on Microsoft Edge are [User-Agent Client Hints](#user-agent-client-hints) and [User-Agent strings](#user-agent-string).</span></span>  <span data-ttu-id="8efa1-108">数十年の使用の後、User-Agent文字列は古く、Web サイトの互換性の問題の原因として長い歴史を持っています。</span><span class="sxs-lookup"><span data-stu-id="8efa1-108">After decades of use, User-Agent strings are outdated and have a long history as the cause of website compatibility issues.</span></span>  <span data-ttu-id="8efa1-109">代わりに、Microsoft Edgeチームは[、User-Agent クライアント](#user-agent-client-hints)ヒントという名前のブラウザー情報を取得するために、改善されたメカニズムを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8efa1-109">Instead, the Microsoft Edge team recommends you use an improved mechanism to retrieve browser information named [User-Agent Client Hints](#user-agent-client-hints).</span></span>  <span data-ttu-id="8efa1-110">この記事では、ユーザー エージェント情報の取得Microsoft Edgeサポートする 2 つのメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-110">This article outlines the two mechanisms Microsoft Edge supports for retrieving user agent information.</span></span>  

|  | <span data-ttu-id="8efa1-111">サーバー側</span><span class="sxs-lookup"><span data-stu-id="8efa1-111">Server-side</span></span> | <span data-ttu-id="8efa1-112">クライアント側</span><span class="sxs-lookup"><span data-stu-id="8efa1-112">Client-side</span></span> |  
|:--- |:--- |:--- | 
| <span data-ttu-id="8efa1-113">**User-Agent クライアント ヒント** \(recommended\)</span><span class="sxs-lookup"><span data-stu-id="8efa1-113">**User-Agent Client Hints** \(recommended\)</span></span> | `Sec-CH-UA` <span data-ttu-id="8efa1-114">HTTPS ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8efa1-114">HTTPS header</span></span> | `navigator.userAgentData` <span data-ttu-id="8efa1-115">JavaScript メソッド</span><span class="sxs-lookup"><span data-stu-id="8efa1-115">JavaScript method</span></span> |  
| <span data-ttu-id="8efa1-116">**User-Agent 文字列** \(legacy\)</span><span class="sxs-lookup"><span data-stu-id="8efa1-116">**User-Agent string** \(legacy\)</span></span> | `User-Agent` <span data-ttu-id="8efa1-117">HTTPS ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8efa1-117">HTTPS header</span></span> | `navigator.userAgent` <span data-ttu-id="8efa1-118">JavaScript メソッド</span><span class="sxs-lookup"><span data-stu-id="8efa1-118">JavaScript method</span></span> |  

<span data-ttu-id="8efa1-119">Microsoft では、以下 [の理由により][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 、可能な限り機能検出を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8efa1-119">Microsoft recommends that you use [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] whenever possible for the following reasons.</span></span>  

*   <span data-ttu-id="8efa1-120">コードの保守性を向上します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-120">Improve code maintainability.</span></span>  
*   <span data-ttu-id="8efa1-121">コードのフラグ設定を減らします。</span><span class="sxs-lookup"><span data-stu-id="8efa1-121">Reduce code fragility.</span></span>  
*   <span data-ttu-id="8efa1-122">文字列の変更によるコードのUser-Agentします。</span><span class="sxs-lookup"><span data-stu-id="8efa1-122">Reduce code breakage from changes to the User-Agent string.</span></span>  
    
<span data-ttu-id="8efa1-123">機能[の検出が][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]適用できない場合で、ユーザー エージェントの検出を使用する必要がある場合は、次の形式を使用して、Microsoft Edgeおよび Android のユーザー エージェントWindows検出します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-123">When [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] isn't applicable and you must use user agent detection, use the following format to detect Microsoft Edge user agent on Windows and Android.</span></span>  

## <a name="user-agent-client-hints"></a><span data-ttu-id="8efa1-124">User-Agent クライアント ヒント</span><span class="sxs-lookup"><span data-stu-id="8efa1-124">User-Agent Client Hints</span></span>  

<span data-ttu-id="8efa1-125">バージョン 90 Microsoft Edgeから、よりクリーンでプライバシーを保持する方法でブラウザー情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8efa1-125">Starting in Microsoft Edge version 90, access browser information in a cleaner, more privacy-preserving way.</span></span>  

### <a name="user-agent-client-hints-https-header"></a><span data-ttu-id="8efa1-126">User-Agent クライアント ヒント HTTPS ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8efa1-126">User-Agent Client Hints HTTPS Header</span></span>  

<span data-ttu-id="8efa1-127">既定では、Chromium含むMicrosoft Edge次の形式 `Accept-CH-UA` で応答ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-127">By default, Chromium browsers including Microsoft Edge send the `Accept-CH-UA` response header in the following format.</span></span>  

```https
Sec-CH-UA: "Chromium";v="91", "Microsoft Edge";v="91","Dummy;Browser Brand";v="99"
Sec-CH-UA-Mobile: ?0
```  

> [!NOTE]
> <span data-ttu-id="8efa1-128">クライアント ヒントは、 を使用してセキュリティで保護された接続でのみ送信されます `HTTPS` 。</span><span class="sxs-lookup"><span data-stu-id="8efa1-128">Client Hints are only sent over secure connections using `HTTPS`.</span></span>  

<span data-ttu-id="8efa1-129">既定では、次の低エントロピー ヒントが送信されます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-129">The following low entropy hints are sent by default.</span></span>  <span data-ttu-id="8efa1-130">詳細にアクセスする必要がある場合は、次のいずれかの要求ヘッダーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-130">If you need to access more information, send one of the following request headers.</span></span>  

#### <a name="user-agent-request-and-response-headers"></a><span data-ttu-id="8efa1-131">User-Agentヘッダーと応答ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8efa1-131">User-Agent request and response headers</span></span>  

| <span data-ttu-id="8efa1-132">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8efa1-132">Request header</span></span> | <span data-ttu-id="8efa1-133">応答値の例</span><span class="sxs-lookup"><span data-stu-id="8efa1-133">Example response value</span></span> |  
|:--- |:--- |  
| `Sec-CH-UA` | `"Chromium";v="91", "Microsoft Edge";v="91","GREASE";v="99"` |  
| `Sec-CH-UA-Mobile` | `false` |  
| `Sec-CH-UA-Full-Version` | `91.0.866.0` |  
| `Sec-CH-UA-Platform` | `Windows` |  
| `Sec-CH-UA Platform-Version` | `10.0` |  
| `Sec-CH-UA-Arch` | `x86` |  
| `Sec-CH-UA-Model` |  |  

### <a name="user-agent-client-hints-javascript-api"></a><span data-ttu-id="8efa1-134">User-Agent クライアント ヒント JavaScript API</span><span class="sxs-lookup"><span data-stu-id="8efa1-134">User-Agent Client Hints JavaScript API</span></span>  

<span data-ttu-id="8efa1-135">既定の応答の値は `navigator.userAgentData` 、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-135">The default response value from `navigator.userAgentData` uses the following format.</span></span>  

```javascript
{ brands: [ {brand: "Chromium","version":"91"}, {brand: "Microsoft Edge","version":"91"}, {brand: "GREASE","version":"99"}, ]
mobile: false }
```  

<span data-ttu-id="8efa1-136">詳細な情報にアクセスする必要がある場合は [、getHighEntropyValues() メソッドを使用][GithubWicgUaClientHintsGethighentropyvalues] します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-136">If you need to access more detailed information, use the [getHighEntropyValues()][GithubWicgUaClientHintsGethighentropyvalues] method.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="8efa1-137">次のコード スニペットは要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-137">The following code snippet sends a request.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="8efa1-138">次の応答を受け取る。</span><span class="sxs-lookup"><span data-stu-id="8efa1-138">To receive the following response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```javascript
         navigator.userAgentData.getHighEntropyValues(
             ["architecture", "model", "platform", "platformVersion", "uaFullVersion"])
             .then(ua => { console.log(ua) });
      ```  
   :::column-end:::
   :::column span="":::
      ```javascript
      {architecture: "x86", 
      model: "", 
      platform: "Windows", 
      platformVersion: "10.0", 
      uaFullVersion: "92.0.866.0"}
      ```  
   :::column-end:::
:::row-end:::  

## <a name="recommended-uses-of-user-agent-client-hints"></a><span data-ttu-id="8efa1-139">クライアント ヒントのUser-Agent使用</span><span class="sxs-lookup"><span data-stu-id="8efa1-139">Recommended uses of User-Agent Client Hints</span></span>  

<span data-ttu-id="8efa1-140">ブランドのセットと関連付けられた表示順序は時間の間に変化しますので、返されるブランドの配列にインデックスをハードコードしたことがない必要があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-140">The set of brands and the associated display order change over time, so you should never hard-code indices into the array of returned brands.</span></span>  <span data-ttu-id="8efa1-141">Web サイトで同様の問題を早期に見つけるのに役立つため、ブラウザーには、一般的な文字列解析の問題のために、時間の間に変化し、破損する形式のブランド値が含 `GREASE` まれています。</span><span class="sxs-lookup"><span data-stu-id="8efa1-141">To help ensure you spot similar issues in your website early, the browser includes a `GREASE` brand value that changes over time and is formatted to break because of common string parsing issues.</span></span>  

<span data-ttu-id="8efa1-142">機能の検出を使用できない場合は[][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]、既知のブラウザーのハードコードされたリストChromium使用して検証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-142">If you're prevented from using [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection], don't use a hardcoded list of known Chromium-based browsers for verification.</span></span>  <span data-ttu-id="8efa1-143">ハードコードされたブラウザー名の例には、 `Microsoft Edge` と が含まれます `Google Chrome` 。</span><span class="sxs-lookup"><span data-stu-id="8efa1-143">Examples of hardcoded browser names include `Microsoft Edge` and `Google Chrome`.</span></span>  <span data-ttu-id="8efa1-144">機能の検出 [が適用][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] できない理由には、次のような状況が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-144">Reasons why [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] isn't applicable may include the following situation.</span></span>  

*   <span data-ttu-id="8efa1-145">新しいバージョンのChromium修正は避ける必要があります。影響を受けるブラウザーは、ブランドとバージョンの検証以外では検出が困難です。</span><span class="sxs-lookup"><span data-stu-id="8efa1-145">A fix for a Chromium bug in a later version must be avoided and the affected browsers are difficult to detect outside of a verification of the brand and version.</span></span>  
    
<span data-ttu-id="8efa1-146">代わりに、ブランドを確認する必要があります。これにより、影響を受けるすべてのユーザーベースのブラウザーにChromium `Chromium` が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-146">Instead, you should verify the `Chromium` brand, which ensures your detection applies to all affected Chromium-based browsers.</span></span>  


```javascript
function isChromium() {
    for (brand_version_pair in navigator.userAgentData.brands) {
        if (brand_version_pair.brand == "Chromium") {
            return true;
        }
    }
    return false;
}
```  

## <a name="user-agent-string"></a><span data-ttu-id="8efa1-147">ユーザー エージェント文字列</span><span class="sxs-lookup"><span data-stu-id="8efa1-147">User agent string</span></span>  

<span data-ttu-id="8efa1-148">可能な限り、Microsoft では、ユーザー エージェント文字列に基Microsoft Edgeブラウザー検出ロジックの使用を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-148">Wherever possible, Microsoft recommends you minimize your use of Microsoft Edge browser detection logic based on the user agent string.</span></span>  <span data-ttu-id="8efa1-149">ユーザー エージェントを検出する理由がある場合は、Microsoft Edgeクライアント ヒントをプライマリ検出ロジックとして[](#user-agent-client-hints)使用してください。</span><span class="sxs-lookup"><span data-stu-id="8efa1-149">If you have a good reason to detect the user agent, the Microsoft Edge team recommends you use [User-Agent Client Hints](#user-agent-client-hints) as the primary detection logic.</span></span>  <span data-ttu-id="8efa1-150">[User-Agent クライアント ヒントでは、](#user-agent-client-hints) 解析された文字列の必要な数も減らします。</span><span class="sxs-lookup"><span data-stu-id="8efa1-150">[User-Agent Client Hints](#user-agent-client-hints) also reduces the required number of parsed strings.</span></span>  <span data-ttu-id="8efa1-151">ただし、従来の参照では、次の形式が文字列にUser-Agentされます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-151">However, for legacy reference, the following format is used for the User-Agent string.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="8efa1-152">このWindows HTTP 要求 `User-Agent` ヘッダーは、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-152">On Windows, the `User-Agent` HTTP request header uses the following format.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="8efa1-153">Android では `User-Agent` 、HTTP 要求ヘッダーは次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-153">On Android, the `User-Agent` HTTP request header uses the following format.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Mobile Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="8efa1-154">メソッドからの応答値 `navigator.userAgent` は、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-154">The response value from `navigator.userAgent` method uses the following format.</span></span>  

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4501.0 Safari/537.36 Edg/91.0.866.0"
```  

<span data-ttu-id="8efa1-155">プラットフォーム識別子は使用されるオペレーティング システムに基づいて変更され、バージョン番号も時間が経過すると増加します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-155">Platform identifiers change based on the operating system used, and the version numbers also increment as time passes.</span></span>  <span data-ttu-id="8efa1-156">形式は、新しいトークンChromium追加したユーザー エージェントの形式 `Edg` と同じです。</span><span class="sxs-lookup"><span data-stu-id="8efa1-156">The format is the same as the Chromium user agent with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="8efa1-157">Microsoft は、EdgeHTML に基づく従来のブラウザーで使用された文字列による互換性 `Edg` `Edge` の問題を回避Microsoft Edge選択しました。</span><span class="sxs-lookup"><span data-stu-id="8efa1-157">Microsoft chose the `Edg` token to avoid compatibility issues caused by `Edge` string, which was used legacy Microsoft Edge browser based on EdgeHTML.</span></span>  <span data-ttu-id="8efa1-158">トークン `Edg` は、iOS および Android で [使用される][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper] 既存のトークンと一致しています。</span><span class="sxs-lookup"><span data-stu-id="8efa1-158">The `Edg` token is also consistent with [existing tokens][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper] used on iOS and Android.</span></span>

## <a name="map-the-user-agent-string-to-browser-name"></a><span data-ttu-id="8efa1-159">ユーザー エージェント文字列をブラウザー名にマップする</span><span class="sxs-lookup"><span data-stu-id="8efa1-159">Map the user agent string to browser name</span></span>  

<span data-ttu-id="8efa1-160">コードで使用する、より人間が読み取り可能なブラウザー名にユーザー エージェント文字列トークンをマップします。</span><span class="sxs-lookup"><span data-stu-id="8efa1-160">Map the user agent string tokens to a more human-readable browser name to use in code.</span></span>  <span data-ttu-id="8efa1-161">これは、今日の Web 上の一般的なパターンです。</span><span class="sxs-lookup"><span data-stu-id="8efa1-161">It's a common pattern on the web today.</span></span>  <span data-ttu-id="8efa1-162">新しいトークンをブラウザー名にマップする場合、従来の Microsoft Edge ブラウザーで使用される名前とは異なる名前を使用して、Chromium ベースのブラウザーに適用されない従来の回避策を誤って適用しないようにお勧めします。 `Edg`</span><span class="sxs-lookup"><span data-stu-id="8efa1-162">When you map the new `Edg` token to a browser name, Microsoft recommends that you use a different name than the one used for the legacy Microsoft Edge browser to avoid accidentally applying any legacy workarounds that aren't applicable to Chromium-based browsers.</span></span>

## <a name="user-agent-overrides"></a><span data-ttu-id="8efa1-163">ユーザー エージェントのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="8efa1-163">User Agent overrides</span></span>  

<span data-ttu-id="8efa1-164">Web サイトが新しいユーザー エージェントを認識Microsoft Edge場合があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-164">Sometimes, a website doesn't recognize the new Microsoft Edge user agent.</span></span>  <span data-ttu-id="8efa1-165">その結果、Web サイトの機能のセットが正しく動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-165">As a result, a set of the features of the website may not work correctly.</span></span>  <span data-ttu-id="8efa1-166">Microsoft が問題の種類について通知を受け取った場合、Microsoft から \(a web サイトの所有者\) に連絡し、更新されたユーザー エージェントについて通知します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-166">When Microsoft is notified about the types of issues, Microsoft contacts you \(a website owner\) and informs you about the updated user agent.</span></span>  

<span data-ttu-id="8efa1-167">Microsoft が報告した問題に対処するには、Web サイトのユーザー エージェント検出ロジックを更新してテストする時間が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8efa1-167">You may need more time to update and test the user agent detection logic for your website to address the issues reported by Microsoft.</span></span>  <span data-ttu-id="8efa1-168">ユーザーの互換性を最大化するために、Microsoft Edge Beta安定チャネルはユーザー エージェントのオーバーライドの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-168">To maximize compatibility for your users, the Microsoft Edge Beta and Stable channels use a list of user agent overrides.</span></span>  <span data-ttu-id="8efa1-169">Web サイトを更新する場合は、ユーザー エージェントの上書きを使用します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-169">Use the user agent overrides while you update your website.</span></span>  <span data-ttu-id="8efa1-170">Microsoft によって提供されるユーザー エージェントの上書きの一覧。</span><span class="sxs-lookup"><span data-stu-id="8efa1-170">The list of user agent overrides provided by Microsoft.</span></span>  

<span data-ttu-id="8efa1-171">オーバーライドは、特定の Web サイトの既定のユーザー エージェントMicrosoft Edge送信する新しいユーザー エージェント値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-171">The overrides specify new user agent values that Microsoft Edge sends instead of the default user agent for specific websites.</span></span>  <span data-ttu-id="8efa1-172">現在適用されているユーザー エージェントオーバーライドの一覧を表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-172">To display the list of user agent overrides that are currently applied, complete the following actions.</span></span>  

1.  <span data-ttu-id="8efa1-173">[ファイル] または [Microsoft Edge Beta] チャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-173">Open the Microsoft Edge Beta or Stable channel.</span></span>  
1.  <span data-ttu-id="8efa1-174">`edge://compat/useragent` に移動します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-174">Navigate to `edge://compat/useragent`.</span></span>  
    
<span data-ttu-id="8efa1-175">Canary Microsoft Edge Dev チャネルは現在、ユーザー エージェントの上書きを受け取らない。</span><span class="sxs-lookup"><span data-stu-id="8efa1-175">The Microsoft Edge Canary and Dev channels don't currently receive user agent overrides.</span></span>  <span data-ttu-id="8efa1-176">Canary Microsoft Edge開発チャネルには、既定のユーザー エージェントを使用するMicrosoft Edge提供されます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-176">The Microsoft Edge Canary and Dev channels provide environments that use the default Microsoft Edge user agent.</span></span>  <span data-ttu-id="8efa1-177">Canary Microsoft Edge Dev チャネルを使用して、既定のユーザー エージェントによって発生する web サイトの問題を簡単Microsoft Edge再現します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-177">Use the Microsoft Edge Canary and Dev channels to easily reproduce issues on your website caused by the default Microsoft Edge user agent.</span></span>  <span data-ttu-id="8efa1-178">クライアント チャネルまたは Stable チャネルでユーザー エージェントの上書Microsoft Edge Beta無効にするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-178">To turn off user agent overrides in the Microsoft Edge Beta or Stable channels, complete the following actions.</span></span>  

1.  <span data-ttu-id="8efa1-179">コマンド ライン アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-179">Open your command-line app.</span></span>  
1.  <span data-ttu-id="8efa1-180">次のコード スニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8efa1-180">Copy and paste the following code snippet.</span></span>  
    
    ```shell
    --disable-domain-action-user-agent-override
    ```  
    
1.  <span data-ttu-id="8efa1-181">コード スニペットをMicrosoft Edgeアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8efa1-181">Run the Microsoft Edge app using the code snippet.</span></span>  
    
    ```shell
    {path/to/microsoft/edge.ext} --disable-domain-action-user-agent-override
    ```  
    
<!-- links -->  

[WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]: https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer "Microsoft Edge iOS と Android 用: 開発者が知る必要がある|Microsoft Windowsブログ"  

[GithubWicgUaClientHintsGethighentropyvalues]: https://wicg.github.io/ua-client-hints#getHighEntropyValues "4.1.5. getHighEntropyValues メソッド - User-Agent クライアント ヒント |GitHub"  

[MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection "機能検出機能の実装|MDN"  
