---
description: このページでは、ユーザー エージェント文字列Microsoft Edgeドキュメントを提供します。
title: Microsoft Edgeユーザー エージェント文字列
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, compatibility, Web プラットフォーム, ユーザー エージェント文字列, ua string, ua overrides
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570800"
---
# <span data-ttu-id="29b57-104">Microsoft Edgeユーザー エージェント文字列 (デスクトップ)</span><span class="sxs-lookup"><span data-stu-id="29b57-104">Microsoft Edge User Agent String (Desktop)</span></span>  

<span data-ttu-id="29b57-105">ユーザー エージェント \(UA\) 文字列を使用して、特定のオペレーティング システムで使用されている特定のブラウザーのバージョンを検出できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-105">A user agent \(UA\) string is able to be used to detect what version of a specific browser is being used on a certain operating system.</span></span>  <span data-ttu-id="29b57-106">他のブラウザーと同様Microsoft Edgeサイトへの要求を行うたびに、HTTP ヘッダーにこの情報 `User-Agent` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29b57-106">Like other browsers, Microsoft Edge includes this information in the `User-Agent` HTTP header whenever it makes a request to a site.</span></span>  <span data-ttu-id="29b57-107">また、 の値を照会して JavaScript を介してアクセスすることもできます `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="29b57-107">It may also be accessed via JavaScript by querying the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="29b57-108">Microsoft では、Web 開発者が可能[](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)な限り機能検出を利用して、コードの保守性を向上し、コードのフラグビリティを低下し、将来の UA 文字列更新が発生した場合にコードが壊れるリスクを排除します。</span><span class="sxs-lookup"><span data-stu-id="29b57-108">Microsoft recommends that web developers make use of [feature detection](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) whenever possible to improve code maintainability, reduce code fragility, and eliminate the risk of code breakage in the event of future UA string updates.</span></span>  

<span data-ttu-id="29b57-109">機能検出が適用できない場合と UA 検出を使用する必要がある場合、デスクトップ上の UA のMicrosoft Edge形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29b57-109">For cases where feature detection is not applicable and UA detection must be used, the format of the Microsoft Edge UA on desktop is as follows:</span></span>

<span data-ttu-id="29b57-110">要求 `User-Agent` ヘッダーの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29b57-110">The `User-Agent` request header is in the following format:</span></span>

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

<span data-ttu-id="29b57-111">戻り値の `navigator.userAgent` 取得元は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="29b57-111">The return value from `navigator.userAgent` is in the following format:</span></span>

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

<span data-ttu-id="29b57-112">プラットフォーム識別子は、使用されているオペレーティング システムに基づいて変更され、バージョン番号も時間が経過すると増加します。</span><span class="sxs-lookup"><span data-stu-id="29b57-112">Platform identifiers change based on the operating system being used, and version numbers also increment as time passes.</span></span>  <span data-ttu-id="29b57-113">この形式は、最後に新Chromium追加した UA の形式 `Edg` と同じです。</span><span class="sxs-lookup"><span data-stu-id="29b57-113">This format is the same as the Chromium UA with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="29b57-114">Microsoft は、EdgeHTML に基づくバージョンのコードで使用される文字列の使用によって引き起こされる可能性がある互換性の問題を回避Microsoft Edge `Edg` `Edge` トークンを選択しました。</span><span class="sxs-lookup"><span data-stu-id="29b57-114">Microsoft selected the `Edg` token to avoid compatibility issues that may be caused by using the string `Edge`, which is used by the version of Microsoft Edge based on EdgeHTML.</span></span>  <span data-ttu-id="29b57-115">トークン `Edg` は、iOS および Android で [使用される](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) 既存のトークンと一致しています。</span><span class="sxs-lookup"><span data-stu-id="29b57-115">The `Edg` token is also consistent with [existing tokens](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) used on iOS and Android.</span></span>

## <span data-ttu-id="29b57-116">UA 文字列をブラウザー名にマッピングする</span><span class="sxs-lookup"><span data-stu-id="29b57-116">Mapping UA String to Browser Name</span></span>
<span data-ttu-id="29b57-117">コードで使用するために、UA 文字列トークンを人間が読み取り可能なブラウザー名にマッピングする方法は、今日の Web 上で一般的なパターンです。</span><span class="sxs-lookup"><span data-stu-id="29b57-117">Mapping UA string tokens to a more human-readable browser name for use in code is a common pattern on the web today.</span></span> <span data-ttu-id="29b57-118">新しいトークンをブラウザー名にマッピングする場合、従来のバージョンの Microsoft Edge で使用されている開発者とは異なる名前を使用して、Chromium ベースのブラウザーに適用できない従来の回避策を誤って適用しないようにお勧めします。 `Edg`</span><span class="sxs-lookup"><span data-stu-id="29b57-118">When mapping the new `Edg` token to a browser name, Microsoft recommends using a different name than the one developers used for the legacy version of Microsoft Edge to avoid accidentally applying any legacy workarounds that are not applicable to Chromium-based browsers.</span></span>

## <span data-ttu-id="29b57-119">ユーザー エージェントのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="29b57-119">User Agent Overrides</span></span>  

<span data-ttu-id="29b57-120">Web サイトが UA の更新されたバージョンを認識Microsoft Edge場合があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-120">Sometimes, a website does not recognize the updated version of the Microsoft Edge UA.</span></span>  <span data-ttu-id="29b57-121">その結果、その Web サイトの機能のセットが正しく動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-121">As a result, a set of the features of that website may not work correctly.</span></span>  <span data-ttu-id="29b57-122">Microsoft がこれらの種類の問題について通知を受け取った場合、Web サイトの所有者に連絡し、更新された UA について通知されます。</span><span class="sxs-lookup"><span data-stu-id="29b57-122">When Microsoft is notified about these types of issues, website owners are contacted and informed about the updated UA.</span></span>  

<span data-ttu-id="29b57-123">多くの場合、サイトでは、Microsoft がサイト所有者に報告する問題に対処するために、UA 検出ロジックを更新してテストする時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="29b57-123">The sites often need some time to update and test the UA detection logic to address the issues that Microsoft reports to site owners.</span></span>  <span data-ttu-id="29b57-124">このような場合、Microsoft は、これらのサイトにアクセスするユーザーの互換性を最大化するために、ベータ版と安定版のチャネルで UA オーバーライドの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="29b57-124">In these cases, Microsoft uses a list of UA overrides in our Beta and Stable channels to maximize compatibility for users who access these sites.</span></span>  <span data-ttu-id="29b57-125">オーバーライドでは、特定のサイトの既定の UA Microsoft Edge送信する必要がある新しい UA 値を指定します。</span><span class="sxs-lookup"><span data-stu-id="29b57-125">The overrides specify new UA values that Microsoft Edge should send instead of the default UA for specific sites.</span></span>  <span data-ttu-id="29b57-126">現在適用されている UA オーバーライドの一覧を表示するには、アプリの Beta チャネルと Stable チャネルに `edge://compat/useragent` 移動Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="29b57-126">You are able to view the list of UA overrides that are currently being applied by navigating to `edge://compat/useragent` in the Beta and Stable channels of Microsoft Edge.</span></span> 

<span data-ttu-id="29b57-127">現在、Canary チャネルと Dev チャネルは UA オーバーライドを受け取りないので、Web 開発者は、既定の UA によって発生するサイト上の問題を簡単に再現できる環境Microsoft Edgeしています。</span><span class="sxs-lookup"><span data-stu-id="29b57-127">Our Canary and Dev channels do not currently receive UA overrides so that web developers have an environment where they can easily reproduce issues on their sites that are caused by the default Microsoft Edge UA.</span></span>  <span data-ttu-id="29b57-128">何らかの理由で Microsoft Edge の Beta チャネルまたは Stable チャネルで UA オーバーライドを無効にする機能が必要な場合は、次のコマンド ライン引数を使用して Microsoft Edge 実行可能ファイルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-128">If for some reason you require the ability to disable UA overrides in the Beta or Stable channels of Microsoft Edge, you may run the Microsoft Edge executable using the following command line argument:</span></span>  

```shell
--disable-domain-action-user-agent-override
```  
