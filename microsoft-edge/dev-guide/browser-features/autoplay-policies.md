---
description: サイト上のメディア コンテンツが、必ずしも前に機能する
title: 自動再生ポリシー - 開発ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Edge、メディア、ビデオ、オーディオ、自動再生
ms.custom: seodec18
ms.openlocfilehash: 39c9bd8e9921167dfc3a9ab1a4cc12b2157f0f6f
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942064"
---
# <span data-ttu-id="45071-104">自動再生ポリシー</span><span class="sxs-lookup"><span data-stu-id="45071-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="45071-105">Microsoft Edge では、Web 上での音が最小化され帯域幅を確実にすることをために、サウンドでメディアを自動再生する機能を提供するお客様は、Web サイトの閲覧設定をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="45071-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="45071-106">さらに、Microsoft Edge はバックグラウンド タブでメディアの自動再生を自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="45071-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="45071-107">ユーザーは、グローバルおよびサイト[global](#global-media-autoplay-settings)単位の自動再生コントロールの[両方でメ](#per-site-media-autoplay-settings)ディア動作をカスタマイズでき、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="45071-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="45071-108">既定では、フェグラウンドでタブが最初に表示されたときにビデオは再生され続けます。</span><span class="sxs-lookup"><span data-stu-id="45071-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="45071-109">自動再生を制限するため、ビデオがミュートされている場合にのみ、ユーザーはサウンドによっては表示されません。</span><span class="sxs-lookup"><span data-stu-id="45071-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="45071-110">ユーザーがページ上の任意の場所をクリックすると、自動再生が再度有効化され、そのタブで引き続きそのドメイン内で引き続き許可されます。</span><span class="sxs-lookup"><span data-stu-id="45071-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="45071-111">ユーザーがメディア コンテンツを直接操作するまで、すべてのサイトでスオープンプトを防止します。</span><span class="sxs-lookup"><span data-stu-id="45071-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="45071-112">グローバル メディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="45071-112">Global media autoplay settings</span></span>  

<span data-ttu-id="45071-113">ユーザーは、[詳細設定メディアの自動再生] ですべてのサイト**Advanced Setting**の既定の自動再生  >  **動作を制御できます**。</span><span class="sxs-lookup"><span data-stu-id="45071-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="グローバル メディア自動再生設定" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="45071-115">グローバル メディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="45071-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="45071-116">サイトごとのメディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="45071-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="45071-117">ユーザーは、Web サイト情報ウィンドウの [Web サイトの権限] セクションで、サイト単位で自動再生 **動作** を制御できます。</span><span class="sxs-lookup"><span data-stu-id="45071-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="45071-118">この設定は、アドレス バーの左側にある情報アイコンまたはロック アイコンをクリックし、メディアの自動 **再生設定をクリック** して確認できます。</span><span class="sxs-lookup"><span data-stu-id="45071-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="45071-119">サイトごとの設定は、グローバル設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="45071-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="45071-120">たとえば、ユーザーがグローバル設定を設定しているが、サイトご `Allow` との設定を変更した場合、 `Block` そのサイトの自動再生はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="45071-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="サイトごとのメディア自動再生設定" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="45071-122">サイトごとのメディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="45071-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="45071-123">Web 開発者向けのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="45071-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="45071-124">サイトにホストされるメディアを使用して、良いユーザー エクスペリエンスを確かめてもらえる方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="45071-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="45071-125">メディア要素の各用語を使用する場合、ユーザー ジェスチャを開始する必要があるとします (ユーザーはいつでも自動再生をブロックできます)、またその場合はその計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="45071-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="45071-126">グローバルおよびサイトごとの自動再生ポリシーは、サイトでの使用方法に関係なく、すべての `<audio>` `<video>` 要素と要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="45071-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="45071-127">メディア コントロールが常にサイト メディアと広告コンテンツの両方に存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="45071-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="45071-128">これにより、ユーザーはページ上で自動再生がブロックされている場合に再生を再開できます。</span><span class="sxs-lookup"><span data-stu-id="45071-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="45071-129">Web サイト上のユーザーのエクスペリエンスに与える可能性がある自動再生を評価し、不要なメディア再生を最小化する方法で自動再生を使用することを検定します。</span><span class="sxs-lookup"><span data-stu-id="45071-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="45071-130">自動再生が経験の不正な部分である場合は、ミュートされたコンテンツを使用して開始し、ユーザーがミュート解除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="45071-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="45071-131">ミュートになったコンテンツを自動再生にするには、オーディオ ソースが、間もミュートに設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45071-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="45071-132">それ以外の場合、要素はミュートとして見なされません。</span><span class="sxs-lookup"><span data-stu-id="45071-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="45071-133">そうでない場合は、絶対に不必要な場合を除き、メディアの再生にネイティブ ブラウザー コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="45071-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="45071-134">これにより、ユーザーに一定した操作性が向上します。</span><span class="sxs-lookup"><span data-stu-id="45071-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="45071-135">カスタム コントロールを作成する場合は、メディア コントロールが常に存在し、コントロールが正しく自動再生停止のために正しく表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="45071-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="45071-136">Iframe の代理人</span><span class="sxs-lookup"><span data-stu-id="45071-136">Iframe delegation</span></span>  

<span data-ttu-id="45071-137">自動再生を行うと、コンテンツの発行先にかかわらず親ページから自動再生の権限 `<iframe>` が有効になります。</span><span class="sxs-lookup"><span data-stu-id="45071-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="45071-138">各メディア ファイルが別の iframe でホストされるプレイリスト シナリオでは、ユーザーはプレイリスト全体で再生を 1 回開始するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="45071-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="45071-139">自動再生が許可されているときの検出</span><span class="sxs-lookup"><span data-stu-id="45071-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="45071-140">メディア要素の関数によって返された確率を確認することで、自動再生がブロックされたときに、再生コントロールを調整して正しい状態 `play()` を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="45071-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

```javascript
var promise = document.querySelector('video').play();

if (promise !== undefined) { 
    promise.catch(_error => { 
        // Autoplay was blocked
        // Show user media controls to manually start playback
    }).then(() => { 
        // Autoplay started
    }); 
}
```  
