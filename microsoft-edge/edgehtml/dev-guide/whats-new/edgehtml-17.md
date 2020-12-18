---
title: EdgeHTML 17 の新機能と API
description: このガイドでは、EdgeHTML 17 に含まれる開発者向けの機能と標準の概要について説明します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 75429528fd814963a8c78e27f85564223fb2d3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234497"
---
# <span data-ttu-id="41544-104">EdgeHTML 17 の新機能</span><span class="sxs-lookup"><span data-stu-id="41544-104">What's new in EdgeHTML 17</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="41544-105">[Windows 10 April 2018 Update \(04/2018,](https://blogs.windows.com/windowsexperience/2018/04/27) Build 17134\) の一部として[、EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web プラットフォームで提供される新機能と更新された機能の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41544-105">Here's a list of the new and updated features shipped in [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web platform, as part of the [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, Build 17134\).</span></span>  <span data-ttu-id="41544-106">特定の [Windows Insider](https://insider.windows.com) Preview ビルドの変更については [、Microsoft Edge の変更ログ](https://developer.microsoft.com/microsoft-edge/platform/changelog) と EdgeHTML の新機能に関するページ [をご覧ください](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="41544-106">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="41544-107">次の変更の一覧の permalink を次に示します [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。</span><span class="sxs-lookup"><span data-stu-id="41544-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md).</span></span>  

## <span data-ttu-id="41544-108">新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="41544-108">New and updated features</span></span>  

### <span data-ttu-id="41544-109">ARIA 1.1 の役割、状態、およびイベント</span><span class="sxs-lookup"><span data-stu-id="41544-109">ARIA 1.1 Roles, States, and Events</span></span>  

<span data-ttu-id="41544-110">EdgeHTML 17 では、Accessible [Rich Internet Applications (RIA-ARIA) 1.1](https://w3.org/TR/wai-aria-1.1)仕様から、フィード、[](https://www.w3.org/TR/wai-aria-1.1#feed)[フォーム](https://www.w3.org/TR/wai-aria-1.1#form)[、aria-haspopup、aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-haspopup)など、さまざまなロール、状態、およびプロパティのサポートが追加されています。 [](https://w3.org/TR/wai-aria-1.1#aria-placeholder)変更ログ[で ARIA 更新プログラムの完全な一覧を見つける](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。</span><span class="sxs-lookup"><span data-stu-id="41544-110">EdgeHTML 17 adds support for various roles, states, and properties from the [Accessible Rich Internet Applications (WAI-ARIA) 1.1 specification](https://w3.org/TR/wai-aria-1.1), including [feed](https://www.w3.org/TR/wai-aria-1.1#feed), [form](https://www.w3.org/TR/wai-aria-1.1#form), [aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup), [aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder), and many more; find a [full list of ARIA updates in the changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299).</span></span>  <span data-ttu-id="41544-111">この更新プログラムを使用して、EdgeHTML 17 は、RIA-ARIA 1.1 で定義されているロールと属性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="41544-111">With this update, EdgeHTML 17 now supports all roles and attributes defined in WAI-ARIA 1.1.</span></span>  <!--  Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.  -->  

### <span data-ttu-id="41544-112">CSS マスク</span><span class="sxs-lookup"><span data-stu-id="41544-112">CSS masking</span></span>  

<span data-ttu-id="41544-113">EdgeHTML 17 には、CSS マスクの試験 [的なサポートが含まれています](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。</span><span class="sxs-lookup"><span data-stu-id="41544-113">EdgeHTML 17 includes experimental support for [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking).</span></span>  <span data-ttu-id="41544-114">部分的な実装では、CSS マスク イメージ[とマスク サイズの](https://developer.mozilla.org/docs/Web/CSS/mask-image)[プロパティが導入](https://developer.mozilla.org/docs/Web/CSS/mask-size)されています。</span><span class="sxs-lookup"><span data-stu-id="41544-114">The partial implementation introduces the CSS [mask-image](https://developer.mozilla.org/docs/Web/CSS/mask-image) and [mask-size](https://developer.mozilla.org/docs/Web/CSS/mask-size) properties.</span></span>  <span data-ttu-id="41544-115">about:flags の [CSS マスクを有効にする] フラグを確認して、試用してください。</span><span class="sxs-lookup"><span data-stu-id="41544-115">Check the "Enable CSS Masking" flag in about:flags to being experimenting!</span></span>  

### <span data-ttu-id="41544-116">SVG 要素での CSS 変換</span><span class="sxs-lookup"><span data-stu-id="41544-116">CSS transforms on SVG elements</span></span>  

<span data-ttu-id="41544-117">EdgeHTML 17 では、SVG 要素とプレゼンテーション属性で CSS 変換がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41544-117">EdgeHTML 17 now supports CSS transforms on SVG elements and presentation attributes.</span></span>  <span data-ttu-id="41544-118">これにより、回転、スケーリング、移動、ゆがみ、翻訳など、SVG 要素を視覚的に操作できます。</span><span class="sxs-lookup"><span data-stu-id="41544-118">This allows SVG elements to be visually manipulated, including rotating, scaling, moving, skewing, or translating.</span></span>  

### <span data-ttu-id="41544-119">拡張機能</span><span class="sxs-lookup"><span data-stu-id="41544-119">Extensions</span></span>  

<span data-ttu-id="41544-120">Microsoft Edge では、拡張機能からの [通知を表示](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) する通知 API がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="41544-120">Microsoft Edge now supports the [Notification API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) which displays notifications from extensions.</span></span>  <span data-ttu-id="41544-121">拡張機能の開発者は、ユーザーの完全な操作をサポートするさまざまな種類の通知 \(基本、リスト、画像など)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="41544-121">Extension developers can now create different types of notifications \(basic, list, image  and so on\) which support full user interaction.</span></span>  <span data-ttu-id="41544-122">通知は、アクション センターにも自動的にログインされます。</span><span class="sxs-lookup"><span data-stu-id="41544-122">The notifications are also automatically logged into the Action Center.</span></span>  <span data-ttu-id="41544-123">拡張機能で [この API を](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 使用する方法に関する通知サンプルにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="41544-123">Visit the [notifications sample](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) on how to use this API in your extension.</span></span>  

<span data-ttu-id="41544-124">EdgeHTML 17 では、標準のタブ API クラスの一部としてメソッド `Tabs.reload()` もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41544-124">EdgeHTML 17 now also supports the `Tabs.reload()` method as part of the standard tabs API class.</span></span>  <span data-ttu-id="41544-125">また、Windows 10 April 2018 Update の新機能として、ユーザーは InPrivate ブラウズ中に拡張機能の実行を許可するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="41544-125">Also new in the Windows 10 April 2018 Update, users can now choose to allow extensions to run during inPrivate browsing.</span></span>  

<span data-ttu-id="41544-126">このリリースの拡張機能の更新プログラムについて詳しくは [、Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24)の拡張機能の新機能に関するブログ投稿をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41544-126">For more details on extensions updates in this release, head over to the blog post [New features for extensions in the Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24).</span></span>  

### <span data-ttu-id="41544-127">DevTools</span><span class="sxs-lookup"><span data-stu-id="41544-127">DevTools</span></span>  

<span data-ttu-id="41544-128">DevTools のこのリリースには、従来の Microsoft Edge 用のブラウザー内 \( \) ツールとして、および Microsoft Store からスタンドアロン `F12` [の Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) アプリとしてプレビューする 2 つの方法が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41544-128">This release of the DevTools ships in two ways: as the traditional in-browser \(`F12`\) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools アプリ" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   <span data-ttu-id="41544-130">Microsoft Edge DevTools アプリ</span><span class="sxs-lookup"><span data-stu-id="41544-130">Microsoft Edge DevTools app</span></span>  
:::image-end:::  

<span data-ttu-id="41544-131">このツールは、リモート デバッグの基本的なサポート (新しい[](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge)[DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\ 経由)、PWA デバッグ機能[](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)[、IndexedDB](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)キャッシュ管理、垂直ドッキングなど、多くの主要な機能で更新されました。 [](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)</span><span class="sxs-lookup"><span data-stu-id="41544-131">The tools have also been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(via our new [DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\), [PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging), [IndexedDB cache management](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection), [vertical docking](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="41544-132">また、パフォーマンスと信頼性 [に対](./edgehtml-16.md) する継続的な投資の一環として、最後のリリースで開始された全体的なリファクタリング作業も継続しました。</span><span class="sxs-lookup"><span data-stu-id="41544-132">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>  

<span data-ttu-id="41544-133">詳 [しくは、最新の Windows 10 更新プログラム (EdgeHTML 17) の DevTools](../../devtools-guide/whats-new/edgehtml-17.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41544-133">Visit [DevTools in the latest Windows 10 update (EdgeHTML 17)](../../devtools-guide/whats-new/edgehtml-17.md) for more details.</span></span>  

### <span data-ttu-id="41544-134">JavaScript</span><span class="sxs-lookup"><span data-stu-id="41544-134">JavaScript</span></span>  

<span data-ttu-id="41544-135">EdgeHTML 17 では、Chakra JavaScript エンジンを使用すると、多くの主要な領域でパフォーマンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="41544-135">With EdgeHTML 17 the Chakra JavaScript engine introduces performance improvements in a number of key areas:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="41544-136">より細いメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="41544-136">Leaner memory footprint</span></span>**  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="41544-137">\(Re-\)オブジェクト リテラルの [方向キー関数](https://github.com/Microsoft/ChakraCore/pull/4105) とメソッド [の解析を延期する](https://github.com/Microsoft/ChakraCore/pull/4136)</span><span class="sxs-lookup"><span data-stu-id="41544-137">\(Re-\)defer parsing for [arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105) and [methods on object literals](https://github.com/Microsoft/ChakraCore/pull/4136)</span></span>  
      *   [<span data-ttu-id="41544-138">RegExp バイトコードリファクタリング</span><span class="sxs-lookup"><span data-stu-id="41544-138">RegExp bytecode refactoring</span></span>](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="41544-139">JavaScript の組み込み時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="41544-139">Faster JavaScript built-ins</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="41544-140">Object.create の型共有</span><span class="sxs-lookup"><span data-stu-id="41544-140">Type sharing for Object.create</span></span>](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [<span data-ttu-id="41544-141">Object.assign のポリモーフィック インライン キャッシュ</span><span class="sxs-lookup"><span data-stu-id="41544-141">Polymorphic inline cache for Object.assign</span></span>](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [<span data-ttu-id="41544-142">JSON.parse/stringify の最適化</span><span class="sxs-lookup"><span data-stu-id="41544-142">JSON.parse/stringify optimizations</span></span>](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [<span data-ttu-id="41544-143">JavaScript での配列反復子の書き換えと高速化.of</span><span class="sxs-lookup"><span data-stu-id="41544-143">Rewriting Array Iterators in JavaScript and faster for...of</span></span>](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="41544-144">Web アセンブリ</span><span class="sxs-lookup"><span data-stu-id="41544-144">Web Assembly</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="41544-145">インリングのサポート</span><span class="sxs-lookup"><span data-stu-id="41544-145">Inling support</span></span>](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="41544-146">すべての詳細 [については、EdgeHTML 17 の JavaScript と WebAssembly の](https://blogs.windows.com/msedgedev/2018/06/19) パフォーマンスの向上を確認してください。</span><span class="sxs-lookup"><span data-stu-id="41544-146">Check out [Improved JavaScript and WebAssembly performance in EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) for all the details.</span></span>  

### <span data-ttu-id="41544-147">メディア要素</span><span class="sxs-lookup"><span data-stu-id="41544-147">Media element</span></span>

<span data-ttu-id="41544-148">EdgeHTML 17 には、次の [HTMLMediaElement の更新が含](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) まれています。</span><span class="sxs-lookup"><span data-stu-id="41544-148">EdgeHTML 17 includes updates to [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) including:</span></span>  

*   <span data-ttu-id="41544-149">要素の `preload` 新しい [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性は、プリロードするデータを示します。</span><span class="sxs-lookup"><span data-stu-id="41544-149">The new `preload` attribute on the [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) element indicates what data should be preloaded.</span></span>
*   <span data-ttu-id="41544-150">メソッドとプロパティ [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) を追加 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) すると、開発者はオーディオ出力デバイスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="41544-150">The addition of the [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) method and [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) property allow developers to select the audio output device.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="41544-151">これは、RTC ではまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="41544-151">This is not yet available in RTC.</span></span>  
    
### <span data-ttu-id="41544-152">メディア キャプチャ API</span><span class="sxs-lookup"><span data-stu-id="41544-152">Media Capture API</span></span>  

<span data-ttu-id="41544-153">Microsoft Edge では、メディア キャプチャ API を介した RTC での画面キャプチャ [がサポートされます](https://w3c.github.io/mediacapture-screen-share)。</span><span class="sxs-lookup"><span data-stu-id="41544-153">Microsoft Edge now supports Screen Capture in RTC via the [Media Capture API](https://w3c.github.io/mediacapture-screen-share).</span></span>  <span data-ttu-id="41544-154">この機能を使用すると、Web ページはユーザーのディスプレイ デバイスの出力をキャプチャできます。通常は、プラグインを使用する仮想会議やプレゼンテーション用にデスクトップをブロードキャストするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="41544-154">This feature lets web pages capture output of a user's display device, commonly used to broadcast a desktop for plugin-free virtual meetings or presentation.</span></span>  

### <span data-ttu-id="41544-155">プログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="41544-155">Progressive Web Apps</span></span>  

<span data-ttu-id="41544-156">EdgeHTML 17 以降、サービス ワーカーとプッシュ通知は既定で有効になっています (これらの機能の詳細については、「サービス ワーカー: ページを越えて」を参照[してください)。](https://blogs.windows.com/msedgedev/2017/12/19)</span><span class="sxs-lookup"><span data-stu-id="41544-156">Starting in EdgeHTML 17, Service Workers and push notifications are enabled by default \(learn more about these features in the blog post [Service Worker: Going beyond the page](https://blogs.windows.com/msedgedev/2017/12/19)).</span></span>  <span data-ttu-id="41544-157">これで、Windows 10 上の段階的な Web Apps \(PWAs\) の技術的基盤を構築するテクノロジ \(Fetch ネットワークと Push and Cache API を含む)が完成します。</span><span class="sxs-lookup"><span data-stu-id="41544-157">This completes the suite of technologies \(including Fetch networking and the Push and Cache APIs\) that lays the technical foundation for progressive Web Apps \(PWAs\) on Windows 10.</span></span>  

<span data-ttu-id="41544-158">PAS は、インストール/ホーム[](https://en.wikipedia.org/wiki/Progressive_enhancement)画面の起動、オフライン サポート、プッシュ通知など、サポート プラットフォームとブラウザー エンジン上のネイティブ アプリのような機能によって段階的に拡張される単純な Web アプリです。</span><span class="sxs-lookup"><span data-stu-id="41544-158">PWAs are simply web apps that are [progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement) with native app-like features on supporting platforms and browser engines, such as installation / home screen launch, offline support, and push notifications.</span></span>  <span data-ttu-id="41544-159">Microsoft Edge \(EdgeHTML\) エンジンを搭載した Windows 10 では、PAS は、ユニバーサル [Windows](/windows/uwp/get-started/whats-a-uwp) プラットフォーム アプリとしてブラウザー ウィンドウとは別に実行できるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="41544-159">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform](/windows/uwp/get-started/whats-a-uwp) apps.</span></span>  

<span data-ttu-id="41544-160">PAS 以外にも、サービス ワーカーとキャッシュ API を使用すると、開発者はネットワーク要求を傍受してキャッシュから応答できます。</span><span class="sxs-lookup"><span data-stu-id="41544-160">Beyond PWAs, Service Workers and the Cache API allow developers the ability to intercept network requests and respond from the cache.</span></span>  <span data-ttu-id="41544-161">Web サイトは、ページ読み込みパフォーマンスと信頼性を細かく設定するためにサービス ワーカー キャッシュを活用したり、インターネットや低品質接続の期間中にオフライン エクスペリエンスを提供したりするために、本格的な Web アプリである必要さえありません。</span><span class="sxs-lookup"><span data-stu-id="41544-161">A website need not even been a full-blow web app to take advantage of the Service Worker cache for fine-tined page load performance and reliability, as well as the ability to provide an offline experience during periods of no internet or poor-quality connection.</span></span>  

<span data-ttu-id="41544-162">Windows 10 のサービス ワーカー [と PAS](../../progressive-web-apps/index.md) の詳細については、Windows ドキュメントの段階的な Web アプリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41544-162">Head over to our [Progressive Web Apps on Windows](../../progressive-web-apps/index.md) docs to learn more about Service Workers and details about PWAs on Windows 10.</span></span>  

### <span data-ttu-id="41544-163">Web セキュリティ</span><span class="sxs-lookup"><span data-stu-id="41544-163">Web Security</span></span>  

<span data-ttu-id="41544-164">EdgeHTML 17 では、Subresource Integrity \(SRI\) のサポートが導入されています。</span><span class="sxs-lookup"><span data-stu-id="41544-164">EdgeHTML 17 introduces support for Subresource Integrity \(SRI\).</span></span>  <span data-ttu-id="41544-165">[サブリソースの整合性](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) は、ブラウザーがフェッチされたリソース \(画像、スクリプト、フォントなど)が予期しない操作なしに配信されるのを検証できるセキュリティ機能です。</span><span class="sxs-lookup"><span data-stu-id="41544-165">[Subresource Integrity](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) is a security feature that allows browsers to verify that fetched resources \(such as images, scripts, fonts, and so on\) are delivered without unexpected manipulation.</span></span>  

<span data-ttu-id="41544-166">以下の例のように、Web ページに読み込むリソースの暗号化ハッシュ表現を含む属性を、1 つ以上の要素 `integrity` `<script>` `<link>` に追加します。</span><span class="sxs-lookup"><span data-stu-id="41544-166">Add an `integrity` attribute containing a cryptographic hash representation of the resource that you expect to load on your webpage to a `<script>` or `<link>` element, like the example below.</span></span>  <span data-ttu-id="41544-167">次に、Microsoft Edge は要求されたリソースと属性で定義されているハッシュを比較 `integrity` します。</span><span class="sxs-lookup"><span data-stu-id="41544-167">Then, Microsoft Edge will compare the requested resource to the hash defined in the `integrity` attribute.</span></span>  <span data-ttu-id="41544-168">一致しない場合、Microsoft Edge はリソースを実行し、ネットワークにエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="41544-168">If they do not match, Microsoft Edge will not execute the resource and returns an error to the network.</span></span>  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

<span data-ttu-id="41544-169">また、EdgeHTML 17 の新機能である [Upgrade-Insecure-Requests 要求](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) ヘッダーを使用すると、ブラウザーは安全な閲覧エクスペリエンスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="41544-169">Also new in EdgeHTML 17, the [Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) request header allows browsers to request a secure browsing experience.</span></span>  <span data-ttu-id="41544-170">このヘッダーは、ブラウザーが安全でない要求のアップグレードをサポートし、利用可能な場合はユーザーを安全なバージョンのサイトにリダイレクトする必要があるというサーバーに指示します。</span><span class="sxs-lookup"><span data-stu-id="41544-170">This header tells the server that the browser supports upgrading any insecure requests and the user should be redirected to a secure version of the site if available.</span></span>  

### <span data-ttu-id="41544-171">可変フォント</span><span class="sxs-lookup"><span data-stu-id="41544-171">Variable Fonts</span></span>
<span data-ttu-id="41544-172">可変フォント \(CSS [フォント](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) バリエーション設定や [フォント](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)光学式サイズ変更 \を含む) の完全なサポートは、EdgeHTML 17 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="41544-172">Full support for Variable Fonts \(including CSS [font-variation-settings](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) and [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) is available in EdgeHTML 17.</span></span>  <span data-ttu-id="41544-173">可変フォントを使用すると、開発者はさまざまな軸を調整することで、1 つのフォントで一見異なる書体の外観を実現できます。複数のフォント ファイルの必要性が減り、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="41544-173">Variable fonts enable developers to achieve the look of seemingly different typefaces with a single font by adjusting various axes – reducing the need for multiple font files and bettering performance.</span></span>  

<span data-ttu-id="41544-174">Web 開発者やデザイナー [に](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)提供される可変フォントや、サイトで使用する方法について学ぶには、ご参加ください。</span><span class="sxs-lookup"><span data-stu-id="41544-174">Join us on [an expedition to learn about what variable fonts provide web developers and designers](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts), and how to use them on your site.</span></span>  <span data-ttu-id="41544-175">また、ブログ投稿の変数フォントの詳細については、「可変フォントを使用して表現力のあるパフォーマンスの高い文字体裁を [Microsoft Edge に取り込む」を参照してください](https://blogs.windows.com/msedgedev/2018/03/13)。</span><span class="sxs-lookup"><span data-stu-id="41544-175">And read more about Variable Fonts in the blog post, [Bringing expressive, performant typography to Microsoft Edge with Variable Fonts](https://blogs.windows.com/msedgedev/2018/03/13).</span></span>  

<iframe height='456' scrolling='no' title='<span data-ttu-id="41544-176">Variable VariableS ticket examples</span><span class="sxs-lookup"><span data-stu-id="41544-176">Variable Tides ticket examples</span></span>' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="41544-177">CodePen の MSEdgeDev ( @MSEdgeDev ) による Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> Variable Variable のチケットの例 </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="41544-177">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'>Variable Tides ticket examples</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="41544-178">EdgeHTML 17 の新しい API</span><span class="sxs-lookup"><span data-stu-id="41544-178">New APIs in EdgeHTML 17</span></span>  

<span data-ttu-id="41544-179">EdgeHTML 17 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41544-179">Here's the full list of new APIs in EdgeHTML 17.</span></span>  <span data-ttu-id="41544-180">これらは次の形式で一覧表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="41544-180">They are listed in the format of `[interface name].[api name]`.</span></span>  

> [!NOTE] 
> <span data-ttu-id="41544-181">以下の API は DOM で公開されていますが、一部の API のエンド エンドの動作はまだ開発中である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41544-181">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="41544-182">機能の  [サポートに関する公式](https://developer.microsoft.com/microsoft-edge/platform/status) の単語については、Microsoft Edge プラットフォームの状態を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41544-182">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="41544-183">EdgeHTML 17 の新しい API</span><span class="sxs-lookup"><span data-stu-id="41544-183">New APIs in EdgeHTML 17</span></span>' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="41544-184">CodePen の <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> EdgeHTML 17 by MSEdgeDev ( @MSEdgeDev ) の Pen New API を </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> 参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="41544-184">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>New APIs in EdgeHTML 17</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

> [!TIP]
> <span data-ttu-id="41544-185">他のブラウザー[](https://blogs.windows.com/msedgedev/2017/10/18)や Web コミュニティと提携し[、MDN Web Docs](https://developer.mozilla.org)を、現在および新たな標準ベースの Web テクノロジに関する有用で、未確定のブラウザーに依存しないドキュメントの決定的な場所として採用しています。</span><span class="sxs-lookup"><span data-stu-id="41544-185">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="41544-186">EdgeHTML API のサポートに関する詳細は、MDN Web リファレンス ライブラリの各ページ [で直接確認できます](https://developer.mozilla.org/docs/Web)。</span><span class="sxs-lookup"><span data-stu-id="41544-186">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="41544-187">Microsoft Edge でサポートされている最新 [の](https://developer.microsoft.com/microsoft-edge/status) 機能については、Microsoft Edge のプラットフォームの状態にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="41544-187">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/status) for the latest features supported in Microsoft Edge.</span></span>  

## <span data-ttu-id="41544-188">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="41544-188">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="41544-189">EdgeHTML 13 / Windows ビルド 10586 (11/2015)</span><span class="sxs-lookup"><span data-stu-id="41544-189">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)  

[<span data-ttu-id="41544-190">EdgeHTML 14 / Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="41544-190">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)  

[<span data-ttu-id="41544-191">EdgeHTML 15 / Windows ビルド 15063 (4/2017)</span><span class="sxs-lookup"><span data-stu-id="41544-191">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)  

[<span data-ttu-id="41544-192">EdgeHTML 16 / Windows ビルド 16299 (10/2017)</span><span class="sxs-lookup"><span data-stu-id="41544-192">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)  
