---
title: EdgeHTML 17 の新機能と API
description: このガイドでは、EdgeHTML 17 に含まれる開発者の機能と標準の概要を示します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、Web 開発、html、cs、javascript、開発者
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941945"
---
# <span data-ttu-id="c11df-104">Microsoft EdgeHTML 17 の新機能</span><span class="sxs-lookup"><span data-stu-id="c11df-104">What's new in EdgeHTML 17</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="c11df-105">[Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, ビルド 17134\) の一部として[、EdgeHTML 17 Web](https://blogs.windows.com/msedgedev/2018/04/30)プラットフォームで出荷された新機能と更新された機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c11df-105">Here's a list of the new and updated features shipped in [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web platform, as part of the [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, Build 17134\).</span></span>  <span data-ttu-id="c11df-106">特定の Windows Insider Preview ビルド [の変更内容](https://insider.windows.com) については [、Microsoft Edge の変更履歴と](https://developer.microsoft.com/microsoft-edge/platform/changelog) [EdgeHTML の新機能を参照してください](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="c11df-106">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="c11df-107">次の一覧を行うと、この機能が利用できます [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。</span><span class="sxs-lookup"><span data-stu-id="c11df-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md).</span></span>  

## <span data-ttu-id="c11df-108">新機能と更新された機能</span><span class="sxs-lookup"><span data-stu-id="c11df-108">New and updated features</span></span>  

### <span data-ttu-id="c11df-109">ARIA 1.1 の役割、状態、イベント</span><span class="sxs-lookup"><span data-stu-id="c11df-109">ARIA 1.1 Roles, States, and Events</span></span>  

<span data-ttu-id="c11df-110">Microsoft EdgeHTML 17 では、アクセシビリティに対応したリッチな[インターネット アプリケーション (WAI-ARIA) 1.1 の指定](https://w3.org/TR/wai-aria-1.1)([フ](https://www.w3.org/TR/wai-aria-1.1#feed)ィード、[フォーム](https://www.w3.org/TR/wai-aria-1.1#form)[、aria-haspopup、aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-haspopup)[aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder)など) からさまざまな役割、状態、プロパティのサポートが追加されました。変更ログ[で ARIA の更新プログラムの完全なリストを検索します](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。</span><span class="sxs-lookup"><span data-stu-id="c11df-110">EdgeHTML 17 adds support for various roles, states, and properties from the [Accessible Rich Internet Applications (WAI-ARIA) 1.1 specification](https://w3.org/TR/wai-aria-1.1), including [feed](https://www.w3.org/TR/wai-aria-1.1#feed), [form](https://www.w3.org/TR/wai-aria-1.1#form), [aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup), [aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder), and many more; find a [full list of ARIA updates in the changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299).</span></span>  <span data-ttu-id="c11df-111">今回の更新プログラムでは、WAI-ARIA 1.1 で定義されたすべてのロールと属性がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-111">With this update, EdgeHTML 17 now supports all roles and attributes defined in WAI-ARIA 1.1.</span></span>  <span data-ttu-id="c11df-112">Microsoft Edge [のアクセシビリティ](../../accessibility.md) に関する詳細については、アクセシビリティに関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c11df-112">Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.</span></span>  

### <span data-ttu-id="c11df-113">CSS マスキング</span><span class="sxs-lookup"><span data-stu-id="c11df-113">CSS masking</span></span>  

<span data-ttu-id="c11df-114">EdgeHTML 17 では、CSS マスキングのためのサポート [が含まれており、サポートが含まれており、サポートが含まれており、サポートが含まれており、サポートされます](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。</span><span class="sxs-lookup"><span data-stu-id="c11df-114">EdgeHTML 17 includes experimental support for [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking).</span></span>  <span data-ttu-id="c11df-115">部分的な実装では、CSS [マスク](https://developer.mozilla.org/docs/Web/CSS/mask-image) イメージとマス [ク サイズのプロパティが](https://developer.mozilla.org/docs/Web/CSS/mask-size) 説明されています。</span><span class="sxs-lookup"><span data-stu-id="c11df-115">The partial implementation introduces the CSS [mask-image](https://developer.mozilla.org/docs/Web/CSS/mask-image) and [mask-size](https://developer.mozilla.org/docs/Web/CSS/mask-size) properties.</span></span>  <span data-ttu-id="c11df-116">実用する場合は、「CSS Masking を有効にする」フラグを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c11df-116">Check the "Enable CSS Masking" flag in about:flags to being experimenting!</span></span>  

### <span data-ttu-id="c11df-117">SVG 要素での CSS 変換</span><span class="sxs-lookup"><span data-stu-id="c11df-117">CSS transforms on SVG elements</span></span>  

<span data-ttu-id="c11df-118">Microsoft EdgeHTML 17 では、SVG 要素とプレゼンテーション属性の CSS 変換がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-118">EdgeHTML 17 now supports CSS transforms on SVG elements and presentation attributes.</span></span>  <span data-ttu-id="c11df-119">これにより、回転、スケーリング、移動、スケース、翻訳を含む、SVG 要素を視覚的に操作できます。</span><span class="sxs-lookup"><span data-stu-id="c11df-119">This allows SVG elements to be visually manipulated, including rotating, scaling, moving, skewing, or translating.</span></span>  

### <span data-ttu-id="c11df-120">拡張機能</span><span class="sxs-lookup"><span data-stu-id="c11df-120">Extensions</span></span>  

<span data-ttu-id="c11df-121">Microsoft Edge では、 [拡張機能からの通知を表示する通知 API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-121">Microsoft Edge now supports the [Notification API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) which displays notifications from extensions.</span></span>  <span data-ttu-id="c11df-122">拡張機能開発者は、すべてのユーザーが操作をサポートするさまざまな種類の通知 \(基本、リスト、画像など) を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-122">Extension developers can now create different types of notifications \(basic, list, image  and so on\) which support full user interaction.</span></span>  <span data-ttu-id="c11df-123">通知は、アクション センターにも自動的にログインされます。</span><span class="sxs-lookup"><span data-stu-id="c11df-123">The notifications are also automatically logged into the Action Center.</span></span>  <span data-ttu-id="c11df-124">拡張機能で [この](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) API の使用方法についての通知サンプルにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c11df-124">Visit the [notifications sample](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) on how to use this API in your extension.</span></span>  

<span data-ttu-id="c11df-125">また、Microsoft EdgeHTML 17 では、標準タブ API クラスの一部としてメソ `Tabs.reload()` ッドがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-125">EdgeHTML 17 now also supports the `Tabs.reload()` method as part of the standard tabs API class.</span></span>  <span data-ttu-id="c11df-126">また、Windows 10 2018 年 4 月の更新プログラムの新機能を使用すると、ユーザーは、InPrivate ブラウジング中に拡張機能を実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c11df-126">Also new in the Windows 10 April 2018 Update, users can now choose to allow extensions to run during inPrivate browsing.</span></span>  

<span data-ttu-id="c11df-127">このリリースの拡張機能の更新について詳しくは [、Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24)の拡張機能のための新機能をブログ投稿に移動してください。</span><span class="sxs-lookup"><span data-stu-id="c11df-127">For more details on extensions updates in this release, head over to the blog post [New features for extensions in the Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24).</span></span>  

### <span data-ttu-id="c11df-128">DevTools</span><span class="sxs-lookup"><span data-stu-id="c11df-128">DevTools</span></span>  

<span data-ttu-id="c11df-129">このリリースでは、DevTools のリリースでは、従用ブラウザー \( \( \) ツールと Microsoft Store からスタンドア `F12` ロン [の Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) アプリとしてプレビューする方法の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c11df-129">This release of the DevTools ships in two ways: as the traditional in-browser \(`F12`\) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools アプリ" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   <span data-ttu-id="c11df-131">Microsoft Edge DevTools アプリ</span><span class="sxs-lookup"><span data-stu-id="c11df-131">Microsoft Edge DevTools app</span></span>  
:::image-end:::  

<span data-ttu-id="c11df-132">また、ツールは、リモート デバッ [グのサポート](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(新 [しい DevTools プロトコ](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)ル \) を使用した [、PWA](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)デバッグ [管理、](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)インデックス作成、垂直ドッキングなど、多くの主要な機能 [で更新されています](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) 。</span><span class="sxs-lookup"><span data-stu-id="c11df-132">The tools have also been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(via our new [DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\), [PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging), [IndexedDB cache management](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection), [vertical docking](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="c11df-133">また、パフォーマンスと確実性に関 [する](./edgehtml-16.md) 進行中の一部として、全体的な再現作業を継続していました。</span><span class="sxs-lookup"><span data-stu-id="c11df-133">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>  

<span data-ttu-id="c11df-134">詳細については [、最新の Windows 10 更新プログラム (EdgeHTML 17) の DevTools](../../devtools-guide/whats-new/edgehtml-17.md) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c11df-134">Visit [DevTools in the latest Windows 10 update (EdgeHTML 17)](../../devtools-guide/whats-new/edgehtml-17.md) for more details.</span></span>  

### <span data-ttu-id="c11df-135">JavaScript</span><span class="sxs-lookup"><span data-stu-id="c11df-135">JavaScript</span></span>  

<span data-ttu-id="c11df-136">Microsoft EdgeHTML 17 では、Chakra JavaScript エンジンでは、次の複数の主要領域でパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="c11df-136">With EdgeHTML 17 the Chakra JavaScript engine introduces performance improvements in a number of key areas:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="c11df-137">Leaner メモリ フットプリント</span><span class="sxs-lookup"><span data-stu-id="c11df-137">Leaner memory footprint</span></span>**  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="c11df-138">オブジェクト リテラルの矢印関数およびメソッ[arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105)ドについて \(Re-\)[デファイナル](https://github.com/Microsoft/ChakraCore/pull/4136)</span><span class="sxs-lookup"><span data-stu-id="c11df-138">\(Re-\)defer parsing for [arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105) and [methods on object literals](https://github.com/Microsoft/ChakraCore/pull/4136)</span></span>  
      *   [<span data-ttu-id="c11df-139">RegExp バイト コードのリファクター</span><span class="sxs-lookup"><span data-stu-id="c11df-139">RegExp bytecode refactoring</span></span>](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c11df-140">JavaScript の組み込み関数のパフォーマンスを上下</span><span class="sxs-lookup"><span data-stu-id="c11df-140">Faster JavaScript built-ins</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="c11df-141">Object.create の共有の種類</span><span class="sxs-lookup"><span data-stu-id="c11df-141">Type sharing for Object.create</span></span>](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [<span data-ttu-id="c11df-142">Object.assign の Polymorphic インライン キャッシュ</span><span class="sxs-lookup"><span data-stu-id="c11df-142">Polymorphic inline cache for Object.assign</span></span>](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [<span data-ttu-id="c11df-143">JSON.parse/stringify の最適化</span><span class="sxs-lookup"><span data-stu-id="c11df-143">JSON.parse/stringify optimizations</span></span>](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [<span data-ttu-id="c11df-144">JavaScript で配列のイターターを書き換え、...が</span><span class="sxs-lookup"><span data-stu-id="c11df-144">Rewriting Array Iterators in JavaScript and faster for...of</span></span>](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="c11df-145">Web アシンボリ</span><span class="sxs-lookup"><span data-stu-id="c11df-145">Web Assembly</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="c11df-146">Inling サポート</span><span class="sxs-lookup"><span data-stu-id="c11df-146">Inling support</span></span>](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c11df-147">詳細については [、EdgeHTML 17 での JavaScript と WebAssembly](https://blogs.windows.com/msedgedev/2018/06/19) のパフォーマンスが改善されました。</span><span class="sxs-lookup"><span data-stu-id="c11df-147">Check out [Improved JavaScript and WebAssembly performance in EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) for all the details.</span></span>  

### <span data-ttu-id="c11df-148">メディア要素</span><span class="sxs-lookup"><span data-stu-id="c11df-148">Media element</span></span>

<span data-ttu-id="c11df-149">EdgeHTML 17 には、次のような [HTMLMediaElement の更新が含](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) まれています。</span><span class="sxs-lookup"><span data-stu-id="c11df-149">EdgeHTML 17 includes updates to [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) including:</span></span>  

*   <span data-ttu-id="c11df-150">要素の `preload` 新しい属性 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) は、先頭にどのデータが事前に読み込むべきかを示します。</span><span class="sxs-lookup"><span data-stu-id="c11df-150">The new `preload` attribute on the [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) element indicates what data should be preloaded.</span></span>
*   <span data-ttu-id="c11df-151">メソッドとプロパティ [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) が追加され、デベロッ [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) パーはオーディオ出力デバイスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c11df-151">The addition of the [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) method and [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) property allow developers to select the audio output device.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c11df-152">これは RTC ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="c11df-152">This is not yet available in RTC.</span></span>  
    
### <span data-ttu-id="c11df-153">メディア キャプチャ API</span><span class="sxs-lookup"><span data-stu-id="c11df-153">Media Capture API</span></span>  

<span data-ttu-id="c11df-154">Microsoft Edge では、メディア キャプチャ API を通して RTC で画面キ [ャプチャをサポートできるようになりました](https://w3c.github.io/mediacapture-screen-share)。</span><span class="sxs-lookup"><span data-stu-id="c11df-154">Microsoft Edge now supports Screen Capture in RTC via the [Media Capture API](https://w3c.github.io/mediacapture-screen-share).</span></span>  <span data-ttu-id="c11df-155">この機能を使用すると、Web ページでユーザーの表示デバイスの出力をキャプチャできます。一般的に、プラグインの仮想会議やプレゼンテーション用にデスクトップをブロードキャストするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c11df-155">This feature lets web pages capture output of a user's display device, commonly used to broadcast a desktop for plugin-free virtual meetings or presentation.</span></span>  

### <span data-ttu-id="c11df-156">プログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="c11df-156">Progressive Web Apps</span></span>  

<span data-ttu-id="c11df-157">Microsoft EdgeHTML 17 から、サービス ワーカーとプッシュ通知は既定で有効になっています (ブログ投稿サービス ワーカー[のこれらの機能の詳細については、ページをさらに発表するものです)。](https://blogs.windows.com/msedgedev/2017/12/19)</span><span class="sxs-lookup"><span data-stu-id="c11df-157">Starting in EdgeHTML 17, Service Workers and push notifications are enabled by default \(learn more about these features in the blog post [Service Worker: Going beyond the page](https://blogs.windows.com/msedgedev/2017/12/19)).</span></span>  <span data-ttu-id="c11df-158">これにより、Windows 10 でプッシュネットワークの \(PWA\) を処理するテクノロジを示すテクノロジ (フェッチ ネットワーク、プッシュ/キャッシュ API を含む) が完了します。</span><span class="sxs-lookup"><span data-stu-id="c11df-158">This completes the suite of technologies \(including Fetch networking and the Push and Cache APIs\) that lays the technical foundation for progressive Web Apps \(PWAs\) on Windows 10.</span></span>  

<span data-ttu-id="c11df-159">PWA は、インストール、ホーム画面起動、[progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement)オフライン サポート、プッシュ通知などのプラットフォームやブラウザー エンジンをサポートするネイティブ アプリのような機能で積み的に強化される Web アプリです。</span><span class="sxs-lookup"><span data-stu-id="c11df-159">PWAs are simply web apps that are [progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement) with native app-like features on supporting platforms and browser engines, such as installation / home screen launch, offline support, and push notifications.</span></span>  <span data-ttu-id="c11df-160">PWA では、Microsoft Edge \(EdgeHTML\) エンジンを使用すると、ブラウザー ウィンドウをユニバーサル [Windows プ](/windows/uwp/get-started/whats-a-uwp) ラットフォーム アプリとしては別に実行する方法が楽になります。</span><span class="sxs-lookup"><span data-stu-id="c11df-160">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform](/windows/uwp/get-started/whats-a-uwp) apps.</span></span>  

<span data-ttu-id="c11df-161">PWA、サービス ワーカー、キャッシュ API 以外では、ネットワーク要求をインタープライアンスし、キャッシュから応答できる機能をデベロッパーが許可します。</span><span class="sxs-lookup"><span data-stu-id="c11df-161">Beyond PWAs, Service Workers and the Cache API allow developers the ability to intercept network requests and respond from the cache.</span></span>  <span data-ttu-id="c11df-162">Web サイトは、インターネットや低品質のページ読み込みのパフォーマンスと信頼性を高めて、サービス ワーカー キャッシュを利用できるフル ブロー Web アプリでもかまいません。さらに、インターネットや低品質なしの間にオフライン エクスペリエンスを提供する機能も必要です。</span><span class="sxs-lookup"><span data-stu-id="c11df-162">A website need not even been a full-blow web app to take advantage of the Service Worker cache for fine-tined page load performance and reliability, as well as the ability to provide an offline experience during periods of no internet or poor-quality connection.</span></span>  

<span data-ttu-id="c11df-163">Windows 10 の Service Workers と PWA の詳細について説明するには [、Windows](../../progressive-web-apps-edgehtml/index.md) ドキュメントのプレイ状況に進みます。</span><span class="sxs-lookup"><span data-stu-id="c11df-163">Head over to our [Progressive Web Apps on Windows](../../progressive-web-apps-edgehtml/index.md) docs to learn more about Service Workers and details about PWAs on Windows 10.</span></span>  

### <span data-ttu-id="c11df-164">Web セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c11df-164">Web Security</span></span>  

<span data-ttu-id="c11df-165">Microsoft EdgeHTML 17 では、Subresource Integrity \(SRI\) のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="c11df-165">EdgeHTML 17 introduces support for Subresource Integrity \(SRI\).</span></span>  <span data-ttu-id="c11df-166">[サブリソース整合性は](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 、ブラウザーが予期しない操作を行わずに配信されることを確認できるセキュリティ機能です。</span><span class="sxs-lookup"><span data-stu-id="c11df-166">[Subresource Integrity](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) is a security feature that allows browsers to verify that fetched resources \(such as images, scripts, fonts, and so on\) are delivered without unexpected manipulation.</span></span>  

<span data-ttu-id="c11df-167">次の例のように、Web ページで読み込みる予算リソースのキャッシュ表現を含む `integrity` `<script>` `<link>` 属性を、要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="c11df-167">Add an `integrity` attribute containing a cryptographic hash representation of the resource that you expect to load on your webpage to a `<script>` or `<link>` element, like the example below.</span></span>  <span data-ttu-id="c11df-168">その後、Microsoft Edge は要求されたリソースを、属性で定義されたハッシュと `integrity` 比較します。</span><span class="sxs-lookup"><span data-stu-id="c11df-168">Then, Microsoft Edge will compare the requested resource to the hash defined in the `integrity` attribute.</span></span>  <span data-ttu-id="c11df-169">一致しない場合、Microsoft Edge はリソースを実行しません。ネットワークにエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="c11df-169">If they do not match, Microsoft Edge will not execute the resource and returns an error to the network.</span></span>  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

<span data-ttu-id="c11df-170">また [、Upgrade-Insecure-Requests ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) を使用すると、ブラウザーでは、ブラウザーがスキューでの閲覧体験を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="c11df-170">Also new in EdgeHTML 17, the [Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) request header allows browsers to request a secure browsing experience.</span></span>  <span data-ttu-id="c11df-171">このヘッダーは、ブラウザーが不正な要求のアップグレードをサポートしているサーバーに示され、ユーザーは利用可能な場合は、サイトの保護されたバージョンにリダイレクトする必要があることをサーバーに示します。</span><span class="sxs-lookup"><span data-stu-id="c11df-171">This header tells the server that the browser supports upgrading any insecure requests and the user should be redirected to a secure version of the site if available.</span></span>  

### <span data-ttu-id="c11df-172">可変フォント</span><span class="sxs-lookup"><span data-stu-id="c11df-172">Variable Fonts</span></span>
<span data-ttu-id="c11df-173">Variable Fonts \(CSS[フォント バリエーション設定および](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)[フォント-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) の完全なサポートは、EdgeHTML 17 で入手できます。</span><span class="sxs-lookup"><span data-stu-id="c11df-173">Full support for Variable Fonts \(including CSS [font-variation-settings](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) and [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) is available in EdgeHTML 17.</span></span>  <span data-ttu-id="c11df-174">さまざまな軸を調整することで、デベロッパーは、さまざまな軸を調整することで、1 つのフォントで異なる書スタイルの外観を実現できます。複数のフォント ファイルが必要なファイルやパフォーマンス向上のためのニーズを下げることができます。</span><span class="sxs-lookup"><span data-stu-id="c11df-174">Variable fonts enable developers to achieve the look of seemingly different typefaces with a single font by adjusting various axes – reducing the need for multiple font files and bettering performance.</span></span>  

<span data-ttu-id="c11df-175">拡張機能に参加 [して、Web 開](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)発者やデザイナーが提供する可変フォントとサイトでの使い分けについて学習します。</span><span class="sxs-lookup"><span data-stu-id="c11df-175">Join us on [an expedition to learn about what variable fonts provide web developers and designers](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts), and how to use them on your site.</span></span>  <span data-ttu-id="c11df-176">また、ブログ投稿に表示される可変フォントの詳細については、「もちのとも」を参照してください。可用なフォントを使用して Microsoft Edge に対する文字体裁を [実行する](https://blogs.windows.com/msedgedev/2018/03/13)。</span><span class="sxs-lookup"><span data-stu-id="c11df-176">And read more about Variable Fonts in the blog post, [Bringing expressive, performant typography to Microsoft Edge with Variable Fonts](https://blogs.windows.com/msedgedev/2018/03/13).</span></span>  

<iframe height='456' scrolling='no' title='<span data-ttu-id="c11df-177">可変チェットの例</span><span class="sxs-lookup"><span data-stu-id="c11df-177">Variable Tides ticket examples</span></span>' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="c11df-178"><a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> CodePen の MsEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) によるペン変数チ@MSEdgeDev </a> を <a href='https://codepen.io'> 確認できます </a> 。</span><span class="sxs-lookup"><span data-stu-id="c11df-178">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'>Variable Tides ticket examples</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="c11df-179">EdgeHTML 17 の新しい API</span><span class="sxs-lookup"><span data-stu-id="c11df-179">New APIs in EdgeHTML 17</span></span>  

<span data-ttu-id="c11df-180">EdgeHTML 17 の新しい API の完全な一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c11df-180">Here's the full list of new APIs in EdgeHTML 17.</span></span>  <span data-ttu-id="c11df-181">これらは形式で表示されます `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="c11df-181">They are listed in the format of `[interface name].[api name]`.</span></span>  

> [!NOTE] 
> <span data-ttu-id="c11df-182">次の API は DOM で予定されていますが、一部の開発中のエンドツーエンド動作がまだあります。</span><span class="sxs-lookup"><span data-stu-id="c11df-182">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="c11df-183">機能サポート  [のコーサル語については、Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/status) プラットフォームの状態を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c11df-183">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="c11df-184">EdgeHTML 17 の新しい API</span><span class="sxs-lookup"><span data-stu-id="c11df-184">New APIs in EdgeHTML 17</span></span>' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="c11df-185"><a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>CodePen の EdgeHTML 17 の </a> 新しい <a href='https://codepen.io/MSEdgeDev'> API @MSEdgeDev </a> <a href='https://codepen.io'> を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="c11df-185">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>New APIs in EdgeHTML 17</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

> [!TIP]
> <span data-ttu-id="c11df-186">MDN [partnered](https://blogs.windows.com/msedgedev/2017/10/18) Web ドキュメントは、最新の、ブラウザーアジャイル、現在および拡大標準 Web テクノロジのための定義的な場所として[、MDN Web](https://developer.mozilla.org)ドキュメントを開発する場合の定義的な場所としてパートナー化しています。</span><span class="sxs-lookup"><span data-stu-id="c11df-186">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="c11df-187">Microsoft EdgeHTML API のサポートの詳細は、MDN Web リファレンス ライブラリの各 [ページに直接表示できます](https://developer.mozilla.org/docs/Web)。</span><span class="sxs-lookup"><span data-stu-id="c11df-187">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="c11df-188">Microsoft Edge でサポートされている最新機能については [、Microsoft](https://developer.microsoft.com/microsoft-edge/status) Edge のプラットフォームの状態にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c11df-188">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/status) for the latest features supported in Microsoft Edge.</span></span>  

## <span data-ttu-id="c11df-189">以前の EdgeHTML リリース</span><span class="sxs-lookup"><span data-stu-id="c11df-189">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="c11df-190">Microsoft EdgeHTML 13 / Windows ビルド 10586 (2015/11)</span><span class="sxs-lookup"><span data-stu-id="c11df-190">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)  

[<span data-ttu-id="c11df-191">EdgeHTML 14 / Windows ビルド 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="c11df-191">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)  

[<span data-ttu-id="c11df-192">Microsoft EdgeHTML 15 / Windows ビルド 15063 (4/2017)</span><span class="sxs-lookup"><span data-stu-id="c11df-192">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)  

[<span data-ttu-id="c11df-193">Microsoft EdgeHTML 16 / Windows ビルド 16299 (10/2017)</span><span class="sxs-lookup"><span data-stu-id="c11df-193">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)  
