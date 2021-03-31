---
description: サイト上のメディア コンテンツが意図した通り動作することを確認する
title: 自動再生ポリシー - 開発者ガイド
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, メディア, ビデオ, オーディオ, 自動再生
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 85b91a8b87d73d6fccc6eac2aa64513f283d7f21
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234636"
---
# <span data-ttu-id="4a258-104">自動再生ポリシー</span><span class="sxs-lookup"><span data-stu-id="4a258-104">Autoplay Policies</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="4a258-105">Microsoft Edge は、Web 上の注意をそらす操作を最小限に抑え、帯域幅を節約するために、メディアをサウンドで自動再生する Web サイトで閲覧設定をカスタマイズする機能をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="4a258-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="4a258-106">さらに、Microsoft Edge では、バックグラウンド タブでのメディアの自動再生が自動的に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-106">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="4a258-107">ユーザーは、グローバル自動再生コントロール[](#global-media-autoplay-settings)とサイト[](#per-site-media-autoplay-settings)ごとの自動再生コントロールの両方を使用してメディアの動作をカスタマイズできます。これらのコントロールには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4a258-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>  

*   `Allow`  <span data-ttu-id="4a258-108">既定では、サイトの判断で、タブが最初にフォアグラウンドで表示された時点で引き続きビデオを再生します。</span><span class="sxs-lookup"><span data-stu-id="4a258-108">The default and will continue to play videos when a tab is first viewed in the foreground, at the site's discretion.</span></span>  

*   `Limit`  <span data-ttu-id="4a258-109">ビデオがミュートされている場合にのみ、自動再生を機能に制限します。そのため、ユーザーがサウンドに驚かされるのは決してではありません。</span><span class="sxs-lookup"><span data-stu-id="4a258-109">Restricts autoplay to only work when videos are muted, so users are never surprised by sound.</span></span>  <span data-ttu-id="4a258-110">ユーザーがページ上の任意の場所をクリックすると、自動再生が再び有効にされ、そのタブ内のそのドメイン内で引き続き許可されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>  

*   `Block`  <span data-ttu-id="4a258-111">ユーザーがメディア コンテンツを直接操作するまで、すべてのサイトで自動再生を防止します。</span><span class="sxs-lookup"><span data-stu-id="4a258-111">Prevent sautoplay on all sites until users directly interact with the media content.</span></span>  

## <span data-ttu-id="4a258-112">グローバル メディアの自動再生の設定</span><span class="sxs-lookup"><span data-stu-id="4a258-112">Global media autoplay settings</span></span>  

<span data-ttu-id="4a258-113">ユーザーは、[メディアの自動再生の詳細設定] で、すべてのサイトの**既定の**自動再生  >  **動作を制御できます**。</span><span class="sxs-lookup"><span data-stu-id="4a258-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>  

:::image type="complex" source="../media/autoplay_global.png" alt-text="グローバル メディアの自動再生の設定" lightbox="../media/autoplay_global.png":::
   <span data-ttu-id="4a258-115">グローバル メディアの自動再生の設定</span><span class="sxs-lookup"><span data-stu-id="4a258-115">Global media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="4a258-116">サイトごとのメディア自動再生の設定</span><span class="sxs-lookup"><span data-stu-id="4a258-116">Per-site media autoplay settings</span></span>  

<span data-ttu-id="4a258-117">ユーザーは、Web サイト情報ウィンドウの [Web サイト のアクセス許可] セクションで、サイトごとに自動再生動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="4a258-117">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span>  <span data-ttu-id="4a258-118">この設定は、アドレス バーの左側にある情報アイコンまたはロック アイコンをクリックし、メディアの自動再生設定を クリックして開始することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a258-118">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on **Media autoplay settings** to get started.</span></span>  

<span data-ttu-id="4a258-119">サイトごとの設定は、グローバル設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-119">Per-site settings override the global setting.</span></span>  <span data-ttu-id="4a258-120">たとえば、ユーザーのグローバル設定が設定されているが、サイトごとの設定が変更された場合、そのサイトの自動再生 `Allow` `Block` はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="4a258-120">For example, if a user has their global setting set to `Allow` but changes a per-site setting to `Block`, autoplay will be blocked for that site.</span></span>  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="サイトごとのメディア自動再生の設定" lightbox="../media/autoplay_per-site.png":::
   <span data-ttu-id="4a258-122">サイトごとのメディア自動再生の設定</span><span class="sxs-lookup"><span data-stu-id="4a258-122">Per-site media autoplay settings</span></span>  
:::image-end:::  

## <span data-ttu-id="4a258-123">Web 開発者向けのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="4a258-123">Best Practices for Web Developers</span></span>  

<span data-ttu-id="4a258-124">サイトでホストされているメディアで優れたユーザー エクスペリエンスを確保する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a258-124">Here's how to ensure a good user experience with media hosted on your site:</span></span>  

*   <span data-ttu-id="4a258-125">メディア要素を使うごとに、ユーザー ジェスチャで再生を開始する必要がある (ユーザーが任意の時点で自動再生をブロックできる\) と想定し、必要に応じて計画します。</span><span class="sxs-lookup"><span data-stu-id="4a258-125">Assume each use of a media element wil require a user gesture to start the playback \(as users can block autoplay at any point in time\) and plan accordingly.</span></span>  <span data-ttu-id="4a258-126">グローバルおよびサイトごとの自動再生ポリシーは、サイトでの使い方に関係なく、すべての要素 `<audio>` `<video>` に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-126">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>  

*   <span data-ttu-id="4a258-127">メディア コントロールがサイト メディアと広告コンテンツの両方に常に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a258-127">Ensure that media controls are always present on both site media and ad content.</span></span>  <span data-ttu-id="4a258-128">これにより、ページで自動再生がブロックされている場合に、再生を再開できます。</span><span class="sxs-lookup"><span data-stu-id="4a258-128">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>  

*   <span data-ttu-id="4a258-129">自動再生が Web サイトでのユーザーのエクスペリエンスに与える影響を評価し、不要なメディア再生を最小限に抑える方法で自動再生の使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="4a258-129">Evaluate how autoplay may affect users' experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span>  <span data-ttu-id="4a258-130">自動再生がエクスペリエンスの重要な部分である場合は、ミュートされたコンテンツを使用して開始し、ユーザーがミュートを解除できるようにすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4a258-130">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span>  <span data-ttu-id="4a258-131">ミュートされたコンテンツを自動再生するには、オーディオ ソースを明示的にミュートするか、設定しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a258-131">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span>  <span data-ttu-id="4a258-132">それ以外の場合、要素はミュートとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="4a258-132">Otherwise the element will not be considered as muted.</span></span>  

*   <span data-ttu-id="4a258-133">特に必要でない限り、メディア再生にはネイティブ ブラウザー コントロールを使います。</span><span class="sxs-lookup"><span data-stu-id="4a258-133">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span>  <span data-ttu-id="4a258-134">これにより、ユーザーの一貫したエクスペリエンスが保証されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-134">This will ensure a consistent experience for users.</span></span>  <span data-ttu-id="4a258-135">カスタム コントロールを作成する場合は、メディア コントロールが常に存在し、コントロールが自動再生の抑制に適切に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a258-135">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>  

### <span data-ttu-id="4a258-136">Iframe 委任</span><span class="sxs-lookup"><span data-stu-id="4a258-136">Iframe delegation</span></span>  

<span data-ttu-id="4a258-137">自動再生では、コンテンツの生成元に関係なく、親ページから自動再生 `<iframe>` のアクセス許可が継承されます。</span><span class="sxs-lookup"><span data-stu-id="4a258-137">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span>  <span data-ttu-id="4a258-138">各メディア ファイルが個別の iframe でホストされているプレイリストのシナリオでは、ユーザーは再生リスト全体に対して再生を 1 回だけ開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a258-138">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>  

### <span data-ttu-id="4a258-139">自動再生が許可されている場合の検出</span><span class="sxs-lookup"><span data-stu-id="4a258-139">Detecting when autoplay is allowed</span></span>  

<span data-ttu-id="4a258-140">メディア要素の関数によって返される promise を調べることで、自動再生がブロックされた場合に正しい状態を表示するために再生コントロール `play()` を調整できます。</span><span class="sxs-lookup"><span data-stu-id="4a258-140">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>  

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
