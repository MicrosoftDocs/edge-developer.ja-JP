---
description: サイトのメディアコンテンツが意図したとおりに動作することを確認する
title: 開発ガイド-自動再生ポリシー
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 9/17/2018
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、メディア、ビデオ、音声、自動再生
ms.custom: seodec18
ms.openlocfilehash: 397c6f0a22359dbfab7c44370b0429147b7c9834
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568835"
---
# <span data-ttu-id="9eccc-104">自動再生ポリシー</span><span class="sxs-lookup"><span data-stu-id="9eccc-104">Autoplay Policies</span></span>

<span data-ttu-id="9eccc-105">Microsoft Edge では、web 上の集中を最小限に抑え、帯域幅を節約するために、メディアを自動再生する web サイトの閲覧の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-105">Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span> <span data-ttu-id="9eccc-106">さらに、Microsoft Edge では、バックグラウンドタブでのメディアの自動再生が自動的に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-106">Additionaly, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>

<span data-ttu-id="9eccc-107">ユーザーは、[グローバル](#global-media-autoplay-settings)および[サイトごと](#per-site-media-autoplay-settings)の再生コントロールの両方でメディア動作をカスタマイズできます。これにより、次のオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-107">Users can customize media behavior with both [global](#global-media-autoplay-settings) and [per-site](#per-site-media-autoplay-settings) autoplay controls, which provide the following options:</span></span>

- <span data-ttu-id="9eccc-108">[**許可**] は既定の設定であり、サイトの判断でタブがフォアグラウンドで最初に表示されたときに、引き続きビデオを再生します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-108">**Allow**  is the default and will continue to play videos when a tab is first viewed in the foreground, at the site’s discretion.</span></span>

- <span data-ttu-id="9eccc-109">[**制限**] は、ビデオがミュートになっている場合にのみ、自動再生を有効にします。そのため、ユーザーはサウンドで驚かされることはありません。</span><span class="sxs-lookup"><span data-stu-id="9eccc-109">**Limit** will restrict autoplay to only work when videos are muted, so users are never surprised by sound.</span></span> <span data-ttu-id="9eccc-110">ユーザーがページ上の任意の場所をクリックすると、自動再生が再び有効になり、そのタブのそのドメイン内で引き続き許可されます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-110">Once the user clicks anywhere on the page, autoplay is re-enabled, and will continue to be allowed within that domain in that tab.</span></span>

- <span data-ttu-id="9eccc-111">**ブロック**を使うと、ユーザーが直接メディアコンテンツを操作するまで、すべてのサイトの自動再生が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-111">**Block** will prevent autoplay on all sites until users directly interact with the media content.</span></span>

## <span data-ttu-id="9eccc-112">グローバルメディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="9eccc-112">Global media autoplay settings</span></span>

<span data-ttu-id="9eccc-113">ユーザーは、[ **Advanced Setting**  >  **メディア自動再生**の詳細設定] の下にあるすべてのサイトの既定の自動再生動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-113">Users can control the default autoplay behavior for all sites under **Advanced Setting** > **Media autoplay**.</span></span>

![グローバルメディア自動再生設定](../media/autoplay_global.png)

## <span data-ttu-id="9eccc-115">サイト単位のメディア自動再生設定</span><span class="sxs-lookup"><span data-stu-id="9eccc-115">Per-site media autoplay settings</span></span>

<span data-ttu-id="9eccc-116">ユーザーは、[web サイトの情報] ウィンドウの [ **Web サイトの権限**] セクションで、サイトごとに自動再生の動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-116">Users can control autoplay behavior on a per-site basis under the **Website permissions** section of the website information pane.</span></span> <span data-ttu-id="9eccc-117">この設定を確認するには、アドレスバーの左側にある情報アイコンまたはロックアイコンをクリックし、「メディア自動再生設定」をクリックして開始します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-117">This setting can be found by clicking the information icon or lock icon on the left side of the address bar and clicking on “Media autoplay settings” to get started.</span></span>

<span data-ttu-id="9eccc-118">サイトごとの設定では、グローバル設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-118">Per-site settings override the global setting.</span></span> <span data-ttu-id="9eccc-119">たとえば、ユーザーのグローバル設定が "許可" に設定されている場合、サイトごとの設定を "ブロック" に変更すると、そのサイトでは自動再生がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-119">For example, if a user has their global setting set to “Allow” but changes a per-site setting to “Block”, autoplay will be blocked for that site.</span></span>

![サイト単位のメディア自動再生設定](../media/autoplay_per-site.png)
 
## <span data-ttu-id="9eccc-121">Web 開発者向けのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="9eccc-121">Best Practices for Web Developers</span></span>

<span data-ttu-id="9eccc-122">次に、サイトでホストされているメディアを使用して良好なユーザーエクスペリエンスを実現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-122">Here's how to ensure a good user experience with media hosted on your site:</span></span>

- <span data-ttu-id="9eccc-123">メディア要素を使用する場合、再生を開始するにはユーザーのジェスチャが必要です (任意の時点で自動再生をブロックすることができます)。それに応じて計画してください。</span><span class="sxs-lookup"><span data-stu-id="9eccc-123">Assume  each use of a media element wil require a user gesture to start the playback (as users can block autoplay at any point in time) and plan accordingly.</span></span>  <span data-ttu-id="9eccc-124">グローバルおよびサイトごとの自動再生ポリシー `<audio>` `<video>` は、サイトでの使用方法に関係なく、すべての要素と要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-124">Global and per-site autoplay policies apply to all `<audio>` and `<video>` elements, regardless of how they are used on your site</span></span>

- <span data-ttu-id="9eccc-125">メディアコントロールがサイトメディアと広告コンテンツの両方に常に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9eccc-125">Ensure that media controls are always present on both site media and ad content.</span></span> <span data-ttu-id="9eccc-126">これにより、ページで自動再生がブロックされた場合に、再生を再開することができます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-126">This will give users the ability to restart playback if autoplay is blocked on the page.</span></span>

- <span data-ttu-id="9eccc-127">自動再生が web サイト上のユーザーエクスペリエンスに与える影響を評価し、不要なメディアの再生を最小化する方法で自動再生を使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-127">Evaluate how autoplay may affect users’ experience on your website and consider using autoplay in a way that minimizes unwanted media playback.</span></span> <span data-ttu-id="9eccc-128">自動再生がエクスペリエンスの重要な部分である場合は、ミュートされたコンテンツの使用を開始し、ユーザーがミュートを解除できるようにすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9eccc-128">If autoplay is a crucial part of your experience, consider using muted content to start and allowing the user to unmute it.</span></span> <span data-ttu-id="9eccc-129">ミュートされたコンテンツを自動再生するには、オーディオソースを明示的にミュートにするか、設定しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eccc-129">For muted content to autoplay, the audio source must be either explicitly muted or not be set.</span></span> <span data-ttu-id="9eccc-130">そうしないと、要素はミュートと見なされません。</span><span class="sxs-lookup"><span data-stu-id="9eccc-130">Otherwise the element will not be considered as muted.</span></span>

- <span data-ttu-id="9eccc-131">特に必要でない限り、メディアの再生にはネイティブブラウザーコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-131">Unless absolutely necessary to do otherwise, use the native browser controls for media playback.</span></span> <span data-ttu-id="9eccc-132">これにより、一貫したエクスペリエンスをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-132">This will ensure a consistent experience for users.</span></span> <span data-ttu-id="9eccc-133">代わりにカスタムコントロールを作成する場合は、メディアコントロールが常に存在し、コントロールが自動再生抑制に適切に反応することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-133">If you are building custom controls instead, ensure that media controls are always present and that your controls properly react to autoplay suppression.</span></span>

### <span data-ttu-id="9eccc-134">Iframe の委任</span><span class="sxs-lookup"><span data-stu-id="9eccc-134">Iframe delegation</span></span>

<span data-ttu-id="9eccc-135">の自動再生 `<iframe>` は、コンテンツの出所に関係なく、親ページから自動再生のアクセス許可を継承します。</span><span class="sxs-lookup"><span data-stu-id="9eccc-135">Autoplay in an `<iframe>` will inherit the autoplay permission from the parent page regardless of content origin.</span></span> <span data-ttu-id="9eccc-136">各メディアファイルが個別の iframe でホストされている再生リストシナリオでは、ユーザーは再生リスト全体の再生を1回だけ開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eccc-136">In a playlist scenario where each media file is hosted by a separate iframe, the user would only need to initiate playback once for the entire playlist.</span></span>

### <span data-ttu-id="9eccc-137">自動再生が許可されているかを検出する</span><span class="sxs-lookup"><span data-stu-id="9eccc-137">Detecting when autoplay is allowed</span></span>

<span data-ttu-id="9eccc-138">再生コントロールを調整して、自動再生がブロックされたときに正しい状態が表示されるようにするには、次のようにし `play()` ます。</span><span class="sxs-lookup"><span data-stu-id="9eccc-138">You can adjust your playback controls to display the correct state when autoplay is blocked by examining the promise returned by the `play()` function on the media element:</span></span>

```Javascript

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
