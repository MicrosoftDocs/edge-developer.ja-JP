---
description: このページでは、Microsoft Edge ユーザーエージェント文字列に関するドキュメントを提供します。
title: Microsoft Edge ユーザーエージェント文字列
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、互換性、web プラットフォーム、ユーザーエージェント文字列、ua 文字列、ua の上書き
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570800"
---
# <span data-ttu-id="65ad9-104">Microsoft Edge ユーザーエージェント文字列 (デスクトップ)</span><span class="sxs-lookup"><span data-stu-id="65ad9-104">Microsoft Edge User Agent String (Desktop)</span></span>  

<span data-ttu-id="65ad9-105">ユーザーエージェント \ (UA \) 文字列は、特定のオペレーティングシステムで使用されている特定のブラウザーのバージョンを検出するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-105">A user agent \(UA\) string is able to be used to detect what version of a specific browser is being used on a certain operating system.</span></span>  <span data-ttu-id="65ad9-106">他のブラウザーと同じように、Microsoft Edge で `User-Agent` は、サイトへの要求を行うたびに、HTTP ヘッダーにこの情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="65ad9-106">Like other browsers, Microsoft Edge includes this information in the `User-Agent` HTTP header whenever it makes a request to a site.</span></span>  <span data-ttu-id="65ad9-107">また、の値を照会して、JavaScript を使ってアクセスすることもでき `navigator.userAgent` ます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-107">It may also be accessed via JavaScript by querying the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="65ad9-108">Microsoft は、web 開発者が可能な限り[機能検出](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)を利用して、コードの保守性を向上させ、コードの fragility を減らし、将来の UA 文字列更新が発生した場合に、コード売り上げ高からのリスクを排除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65ad9-108">Microsoft recommends that web developers make use of [feature detection](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) whenever possible to improve code maintainability, reduce code fragility, and eliminate the risk of code breakage in the event of future UA string updates.</span></span>  

<span data-ttu-id="65ad9-109">機能の検出が適用されず、UA 検出を使う必要がある場合は、デスクトップの Microsoft Edge UA の形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-109">For cases where feature detection is not applicable and UA detection must be used, the format of the Microsoft Edge UA on desktop is as follows:</span></span>

<span data-ttu-id="65ad9-110">`User-Agent`要求ヘッダーは、次の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="65ad9-110">The `User-Agent` request header is in the following format:</span></span>

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

<span data-ttu-id="65ad9-111">戻り値は、 `navigator.userAgent` 次の形式になります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-111">The return value from `navigator.userAgent` is in the following format:</span></span>

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

<span data-ttu-id="65ad9-112">プラットフォーム識別子は、使用されているオペレーティングシステムに基づいて変更されます。また、バージョン番号は、時間の経過に応じて増加します。</span><span class="sxs-lookup"><span data-stu-id="65ad9-112">Platform identifiers change based on the operating system being used, and version numbers also increment as time passes.</span></span>  <span data-ttu-id="65ad9-113">この形式は、最後に新しいトークンが追加された Chromium UA と同じです `Edg` 。</span><span class="sxs-lookup"><span data-stu-id="65ad9-113">This format is the same as the Chromium UA with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="65ad9-114">Microsoft は、 `Edg` `Edge` EdgeHTML に基づく Microsoft Edge のバージョンによって使用される文字列を使用して発生する可能性のある互換性の問題を回避するために、トークンを選択しました。</span><span class="sxs-lookup"><span data-stu-id="65ad9-114">Microsoft selected the `Edg` token to avoid compatibility issues that may be caused by using the string `Edge`, which is used by the version of Microsoft Edge based on EdgeHTML.</span></span>  <span data-ttu-id="65ad9-115">`Edg`トークンは、iOS および Android で使用される[既存のトークン](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/)とも整合性があります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-115">The `Edg` token is also consistent with [existing tokens](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) used on iOS and Android.</span></span>

## <span data-ttu-id="65ad9-116">ブラウザー名への UA 文字列のマッピング</span><span class="sxs-lookup"><span data-stu-id="65ad9-116">Mapping UA String to Browser Name</span></span>
<span data-ttu-id="65ad9-117">コードで使うために、よりわかりやすいブラウザー名に UA 文字列トークンをマッピングすることは、今日の web 上の一般的なパターンです。</span><span class="sxs-lookup"><span data-stu-id="65ad9-117">Mapping UA string tokens to a more human-readable browser name for use in code is a common pattern on the web today.</span></span> <span data-ttu-id="65ad9-118">新しい `Edg` トークンをブラウザー名にマッピングする場合、Chromium ベースのブラウザーに適用されない従来の回避策が誤って適用されないように、旧バージョンの Microsoft Edge に使用されている開発者とは異なる名前を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65ad9-118">When mapping the new `Edg` token to a browser name, Microsoft recommends using a different name than the one developers used for the legacy version of Microsoft Edge to avoid accidentally applying any legacy workarounds that are not applicable to Chromium-based browsers.</span></span>

## <span data-ttu-id="65ad9-119">ユーザーエージェントの上書き</span><span class="sxs-lookup"><span data-stu-id="65ad9-119">User Agent Overrides</span></span>  

<span data-ttu-id="65ad9-120">場合によっては、更新された Microsoft Edge UA のバージョンが web サイトで認識されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-120">Sometimes, a website does not recognize the updated version of the Microsoft Edge UA.</span></span>  <span data-ttu-id="65ad9-121">その結果、その web サイトの一連の機能が正しく動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-121">As a result, a set of the features of that website may not work correctly.</span></span>  <span data-ttu-id="65ad9-122">Microsoft がこのような種類の問題について通知を受けると、web サイトの所有者に連絡し、更新された UA について通知されます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-122">When Microsoft is notified about these types of issues, website owners are contacted and informed about the updated UA.</span></span>  

<span data-ttu-id="65ad9-123">多くの場合、このサイトでは、UA 検出ロジックの更新とテストを行って、Microsoft からサイト所有者に報告される問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ad9-123">The sites often need some time to update and test the UA detection logic to address the issues that Microsoft reports to site owners.</span></span>  <span data-ttu-id="65ad9-124">このような場合、Microsoft はベータおよび安定したチャネルでの UA の上書きの一覧を使って、これらのサイトにアクセスするユーザーに対して互換性を最大限に高めています。</span><span class="sxs-lookup"><span data-stu-id="65ad9-124">In these cases, Microsoft uses a list of UA overrides in our Beta and Stable channels to maximize compatibility for users who access these sites.</span></span>  <span data-ttu-id="65ad9-125">この上書きによって、特定のサイトの既定の UA の代わりに Microsoft Edge が送信する新しい UA 値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-125">The overrides specify new UA values that Microsoft Edge should send instead of the default UA for specific sites.</span></span>  <span data-ttu-id="65ad9-126">`edge://compat/useragent`Microsoft Edge のベータ版と安定したチャネルに移動して、現在適用されている UA の上書きの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-126">You are able to view the list of UA overrides that are currently being applied by navigating to `edge://compat/useragent` in the Beta and Stable channels of Microsoft Edge.</span></span> 

<span data-ttu-id="65ad9-127">現時点では、Microsoft Edge の既定の UA によって発生した問題について、web 開発者が自分のサイトで問題を簡単に再現できる環境を提供しています。</span><span class="sxs-lookup"><span data-stu-id="65ad9-127">Our Canary and Dev channels do not currently receive UA overrides so that web developers have an environment where they can easily reproduce issues on their sites that are caused by the default Microsoft Edge UA.</span></span>  <span data-ttu-id="65ad9-128">何らかの理由で Microsoft Edge のベータまたは安定したチャネルでの UA の上書きを無効にする必要がある場合は、次のコマンドライン引数を使用して Microsoft Edge 実行可能ファイルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="65ad9-128">If for some reason you require the ability to disable UA overrides in the Beta or Stable channels of Microsoft Edge, you may run the Microsoft Edge executable using the following command line argument:</span></span>  

```shell
--disable-domain-action-user-agent-override
```  
