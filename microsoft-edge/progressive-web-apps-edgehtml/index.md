---
description: プログレッシブ Web アプリは Windows 10 でネイティブに実行されます。  ここでは、web 開発者として知っておく必要があるものをすべて紹介します。
title: Windows のプログレッシブ Web アプリ (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: 778502f6db9a89da810b4fb59b10e8fb889fa4b5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568781"
---
# <span data-ttu-id="740a7-105">Windows のプログレッシブ Web アプリ (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="740a7-105">Progressive Web Apps (EdgeHTML) on Windows</span></span>  

<span data-ttu-id="740a7-106">[プログレッシブ Web アプリ][MDNApps](または単に pwas) を使用する場合、クロスプラットフォームの相互運用性を実現するために開かれた web テクノロジを使用する方法と、デバイスに合わせてカスタマイズされたネイティブアプリなどのエクスペリエンスをユーザーに提供することを決定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="740a7-106">With [Progressive Web Apps][MDNApps] \(or simply PWAs\) you do not have to decide between using open web technologies for cross-platform interoperability and providing your users with a native app-like experience customized for their device.</span></span>  <span data-ttu-id="740a7-107">これは、PWAs は、サポートしているプラットフォーム上のネイティブアプリのように機能するように[段階的に拡張][AListApartUnderstandingProgressiveEnhancement]された web サイトだけであるためです。</span><span class="sxs-lookup"><span data-stu-id="740a7-107">That is because PWAs are just websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="740a7-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="740a7-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [<span data-ttu-id="740a7-110">見つけ</span><span class="sxs-lookup"><span data-stu-id="740a7-110">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="740a7-111">Web 検索結果とサポートされているアプリストアから</span><span class="sxs-lookup"><span data-stu-id="740a7-111">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [<span data-ttu-id="740a7-113">Installable</span><span class="sxs-lookup"><span data-stu-id="740a7-113">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="740a7-114">ホーム画面からピン留めして起動する</span><span class="sxs-lookup"><span data-stu-id="740a7-114">Pin and launch from the home screen</span></span>  
    :::column-end:::
    :::column:::
        ![再 engageable アイコン][ImageIPushNotification]
        ### [<span data-ttu-id="740a7-116">再 engageable</span><span class="sxs-lookup"><span data-stu-id="740a7-116">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="740a7-117">アプリがアクティブでない場合でも、プッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="740a7-117">Send push notifications, even when the app is not active</span></span>  
    :::column-end:::
    :::column:::
        ![ネットワークに依存しないアイコン][ImageIOffline]
        ### [<span data-ttu-id="740a7-119">ネットワークに依存しない</span><span class="sxs-lookup"><span data-stu-id="740a7-119">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="740a7-120">オフラインおよび低ネットワークの状態で動作する</span><span class="sxs-lookup"><span data-stu-id="740a7-120">Works offline and in low-network conditions</span></span>  
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![プログレッシブアイコン][ImageIProgressive]
        ### [<span data-ttu-id="740a7-122">的</span><span class="sxs-lookup"><span data-stu-id="740a7-122">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="740a7-123">デバイス機能を使用して、エクスペリエンスを (上または下に) 拡張する</span><span class="sxs-lookup"><span data-stu-id="740a7-123">Experience scales \(up or down\) with device capabilities</span></span>  
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [<span data-ttu-id="740a7-125">問題</span><span class="sxs-lookup"><span data-stu-id="740a7-125">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="740a7-126">セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する</span><span class="sxs-lookup"><span data-stu-id="740a7-126">Provides a secure HTTPS endpoint and other user safeguards</span></span>  
    :::column-end:::
    :::column:::
        ![応答性アイコン][ImageIResponsive]
        ### [<span data-ttu-id="740a7-128">応答中</span><span class="sxs-lookup"><span data-stu-id="740a7-128">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="740a7-129">ユーザーの画面サイズ/向きと入力方式に合わせて調整する</span><span class="sxs-lookup"><span data-stu-id="740a7-129">Adapts to the user's screen size / orientation and input method</span></span>  
    :::column-end:::
    :::column:::
        ![Linkable アイコン][ImageILink]
        ### [<span data-ttu-id="740a7-131">Linkable</span><span class="sxs-lookup"><span data-stu-id="740a7-131">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="740a7-132">標準ハイパーリンクを共有して起動する</span><span class="sxs-lookup"><span data-stu-id="740a7-132">Share and launch from a standard hyperlink</span></span>  
    :::column-end:::
:::row-end:::

<span data-ttu-id="740a7-133">既存のサイトを作成したり、既存のサイトを PWA に変換したりすることで、既存の対象ユーザーに対してプッシュ通知とオフラインサポートを強化することができます。</span><span class="sxs-lookup"><span data-stu-id="740a7-133">By building or converting your existing site to a PWA, you are able to better engage your existing audience with push notifications and offline support.</span></span>  <span data-ttu-id="740a7-134">同時に、ユーザーが検索とリンク共有を通じて PWA を見つけているため、開いている web で参加者の作成を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="740a7-134">At the same time, you are able to continue building your audience on the open web, as users discover your PWA through search and link-sharing.</span></span>  

## <span data-ttu-id="740a7-135">PWAs は Windows 10 (EdgeHTML) で行われました</span><span class="sxs-lookup"><span data-stu-id="740a7-135">PWAs on Windows 10 (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="740a7-136">EdgeHTML から [Microsoft Edge へ移動] (Chromium) を使うと、PWAs によって使用された基になる web プラットフォームは同じではありません。</span><span class="sxs-lookup"><span data-stu-id="740a7-136">With the move to Microsoft Edge (Chromium) from EdgeHTML, the underlying web platforms used by PWAs are not the same.</span></span>  <span data-ttu-id="740a7-137">Edge (Chromium) PWAs は、ブラウザーからインストールして実行します。</span><span class="sxs-lookup"><span data-stu-id="740a7-137">Edge (Chromium) PWAs are installed from and run within the browser.</span></span>  <span data-ttu-id="740a7-138">Edge (EdgeHTML) PWAs ユニバーサル Windows プラットフォーム (UWP) アプリケーションとして実行され、以前の EdgeHTML web プラットフォームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="740a7-138">Edge (EdgeHTML) PWAs run as Universal Windows Platform (UWP) applications and use the older EdgeHTML web platform.</span></span>  <span data-ttu-id="740a7-139">PWA に Windows 10 API アクセスが必要な場合は、この EdgeHTML のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-139">If you require Windows 10 API access for your PWA, this EdgeHTML documentation is for you.</span></span>  <span data-ttu-id="740a7-140">Windows 固有の API アクセスのないクロスプラットフォームサポートの目標である場合は、 [Microsoft Edge (Chromium) PWA ドキュメント][PwaChromiumIndex]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-140">If your goal is cross platform support without Windows specific API access, please head over to the [Microsoft Edge (Chromium) PWA documentation][PwaChromiumIndex].</span></span>  

<span data-ttu-id="740a7-141">プログレッシブ Web アプリを構築して Windows 10 を利用できるようにすると、 [Microsoft ストア][MicrosoftDeveloperStore]で PWA を配布できます。 windows 10 のインストールベースの 600% 100 のインストールベースは、アプリの対象ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="740a7-141">When you build a Progressive Web App to take advantage of Windows 10, you are able to distribute your PWA through the [Microsoft Store][MicrosoftDeveloperStore], the entire Windows 10 install base of 600+ million active monthly users is your potential app audience!</span></span>  <span data-ttu-id="740a7-142">この方法で開発されたアプリケーションは、[ユニバーサル Windows プラットフォーム][WindowsUWPGetStartedGuide]アプリとして実行され、WinRT api へのアクセスなどのネイティブ機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="740a7-142">Applications developed this way run as [Universal Windows Platform][WindowsUWPGetStartedGuide] apps and have native like access to the WinRT APIs.</span></span>  <span data-ttu-id="740a7-143">コードをレンダリングする web プラットフォームは、WinRT Api を使っているときには EdgeHTML であることに注意してください。 Windows 固有の Api を呼び出す前に、機能の検出を確実に使用して、Microsoft Edge \ (Chromium \) PWAs が利用可能なプラットフォーム間でも PWA を実行できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="740a7-143">Note that the web platform rendering your code is EdgeHTML when using the WinRT APIs so be sure to use feature detection before calling any Windows specific APIs to ensure your PWA is able to still run across platforms where Microsoft Edge \(Chromium\) PWAs are available.</span></span>  

<span data-ttu-id="740a7-144">ここでは、web アプリを PWA \ (EdgeHTML \) に変換して、Windows 10 でテストし、Microsoft Store で配布[する方法について説明][PwaEdgehtmlGetStarted]します。</span><span class="sxs-lookup"><span data-stu-id="740a7-144">[Here is how to get started][PwaEdgehtmlGetStarted] converting your web app to a PWA \(EdgeHTML\), testing it on Windows 10, and distributing it in the Microsoft Store.</span></span>  

## <span data-ttu-id="740a7-145">要件</span><span class="sxs-lookup"><span data-stu-id="740a7-145">Requirements</span></span>  

<span data-ttu-id="740a7-146">PWA として実行するには、サーバーでホストされている web アプリで少なくとも次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="740a7-146">To run as a PWA, your server-hosted web app at minimum requires:</span></span>  

*   <span data-ttu-id="740a7-147">[X] [HTTPS][WikiHttps]。</span><span class="sxs-lookup"><span data-stu-id="740a7-147">[X] [HTTPS][WikiHttps].</span></span>  <span data-ttu-id="740a7-148">サーバー/アプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="740a7-148">Protect your users by providing a secure connection for server/app communication.</span></span>  <span data-ttu-id="740a7-149">サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。</span><span class="sxs-lookup"><span data-stu-id="740a7-149">Service workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
  
*   <span data-ttu-id="740a7-150">[X][サービスワーカー][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="740a7-150">[X] [Service workers][MDNServiceWorkerApi].</span></span>  <span data-ttu-id="740a7-151">サービスワーカースレッドを使って、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供するために、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="740a7-151">Use service worker threads to act as network proxies between your server and client app in order to provide offline support, resource caching, push notifications, background data sync, and page load perf optimizations.</span></span>  

*   <span data-ttu-id="740a7-152">[X] [Web app マニフェスト][MDNWebAppManifest]。</span><span class="sxs-lookup"><span data-stu-id="740a7-152">[X] [Web app manifest][MDNWebAppManifest].</span></span>  <span data-ttu-id="740a7-153">Windows 10 やその他のホストプラットフォームが、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーを提供できるように、Windows 10 とその他のホストプラットフォームが、自分の web アプリについての重要な情報を記述した JSON ベースのメタデータファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="740a7-153">Provide a JSON-based metadata file describing key information about your web app \(such as icons, language, and URL entry point\) so that Windows 10 and other host platforms are able to provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="740a7-154">Web アプリマニフェストにサイトを関連付けると、Bing インデックスサービスを通じて[Microsoft ストアに自動的に含める][PwaEdgehtmlMicrosoftStoreImportingBing]ことができます。</span><span class="sxs-lookup"><span data-stu-id="740a7-154">Associating your site with a web app manifest makes it eligible for [automatic inclusion in the Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] through the Bing indexing service.</span></span>  

<span data-ttu-id="740a7-155">アプリには、次のような便利な PWA もあります。</span><span class="sxs-lookup"><span data-stu-id="740a7-155">To be a great PWA, your app also needs:</span></span>  

*   <span data-ttu-id="740a7-156">[X][ブラウザ間の互換性][MDNCrossBrowserTesting]。</span><span class="sxs-lookup"><span data-stu-id="740a7-156">[X] [Cross-browser compatibility][MDNCrossBrowserTesting].</span></span>  <span data-ttu-id="740a7-157">さまざまなブラウザーと環境で[テスト][MicrosoftDeveloperEdgeToolsRemote]して、PWA が動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="740a7-157">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  <span data-ttu-id="740a7-158">Windows 10 では、アプリを Microsoft Edge ブラウザーと完全な PWA 環境の両方でテストしてください。インストールされているスタンドアロン Windows 10 アプリ (EdgeHTML エンジン \) としてインストールします。</span><span class="sxs-lookup"><span data-stu-id="740a7-158">On Windows 10, be sure to test your app both in the Microsoft Edge browser and also in the full PWA experience: as an installed, standalone Windows 10 app \(powered by the EdgeHTML engine\).</span></span>  
  
*   <span data-ttu-id="740a7-159">[X][応答性][WikiResponsiveWebDesign]の高いデザイン。</span><span class="sxs-lookup"><span data-stu-id="740a7-159">[X] [Responsive design][WikiResponsiveWebDesign].</span></span>  <span data-ttu-id="740a7-160">柔軟なレイアウトと柔軟性の高い画像を CSS [grid][MDNCssGridLayout]や[flexbox][MDNCssFlexibleBoxLayout]、[メディアクエリ][MDNMediaQueries]、および [応答性の高い画像[MDNResponsiveImages]で使用して、ユーザーのデバイスに合わせて UX を調整します。</span><span class="sxs-lookup"><span data-stu-id="740a7-160">Employ fluid layouts and flexible images with CSS [grid][MDNCssGridLayout] and/or [flexbox][MDNCssFlexibleBoxLayout], [media queries][MDNMediaQueries], and [responsive images[MDNResponsiveImages] to adapt your UX to your user's device.</span></span>  <span data-ttu-id="740a7-161">ブラウザーのデバイス[エミュレーションツール][DevToolsGuide|::ref1::|]を使ってローカルでテストするか、[リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview]をセットアップしてターゲットデバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="740a7-161">Use device [emulation tools][DevToolsGuide|::ref1::|] from your browser to test locally, or set up a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>  <span data-ttu-id="740a7-162">Windows 10 では、PWAs \ (EdgeHTML) を、デスクトップ、スマートフォン、タブレット以外[のフォームファクターに合わせて調整][WindowsUWPDesignDevicesIndex]することができます。これには、 [Xbox とテレビ][WindowsUWPDesignDevicesDesigningTv]、 [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub]、 [Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality]デバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="740a7-162">On Windows 10, PWAs \(EdgeHTML\) are able to also be [tailored for form factors][WindowsUWPDesignDevicesIndex] beyond desktop, phone and tablet, including: [Xbox and TV][WindowsUWPDesignDevicesDesigningTv], [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub], and [Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality] devices.</span></span>  
  
*   <span data-ttu-id="740a7-163">[X][ディープリンク][WikiDeepLinking]。</span><span class="sxs-lookup"><span data-stu-id="740a7-163">[X] [Deep linking][WikiDeepLinking].</span></span>  <span data-ttu-id="740a7-164">サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="740a7-164">Route each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  

*   <span data-ttu-id="740a7-165">[X][ベストプラクティス][Webhint]。</span><span class="sxs-lookup"><span data-stu-id="740a7-165">[X] [Best practices][Webhint].</span></span>  <span data-ttu-id="740a7-166">アプリの効率、堅牢性、安全性、アクセシビリティを最適化するには、 [webhint][Webhint]のようなコード品質ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="740a7-166">Use code quality tools like the [webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  

<span data-ttu-id="740a7-167">プログレッシブ Web アプリを[Microsoft Store][MicrosoftDeveloperStore]に提出するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="740a7-167">To submit your Progressive Web App to the [Microsoft Store][MicrosoftDeveloperStore], you must have:</span></span>  

*   <span data-ttu-id="740a7-168">[X] [Microsoft 開発者アカウント][WindowsUWPPublishDeveloperAccount]</span><span class="sxs-lookup"><span data-stu-id="740a7-168">[X] A [Microsoft developer account][WindowsUWPPublishDeveloperAccount]</span></span>  
*   <span data-ttu-id="740a7-169">[X] [Windows アプリを発行するための][WindowsUWPPublishIndex]完了した手順</span><span class="sxs-lookup"><span data-stu-id="740a7-169">[X] Completed [steps for publishing a Windows app][WindowsUWPPublishIndex]</span></span>  

<span data-ttu-id="740a7-170">今後数ヶ月で、既存の PWAs が web 会議に[固有の条件][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]を満たしている場合は、Bing 検索エンジンによって、Microsoft Store に自動的にインデックスが作成されます (開発者は、Windows 10 の対象ユーザーに対してそれらを直接管理できます)。</span><span class="sxs-lookup"><span data-stu-id="740a7-170">In the coming months, existing PWAs on the web meeting [specific criteria][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] are auto-indexed by the Bing search engine into the Microsoft Store \(where developers are able to directly manage them for their Windows 10 audience\).</span></span>  

<span data-ttu-id="740a7-171">詳細については[、Microsoft ストアで Pwas (EdgeHTML)][PwaEdgehtmlMicrosoftStore]を確認してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-171">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] for further details.</span></span>  

## <span data-ttu-id="740a7-172">現在の可用性</span><span class="sxs-lookup"><span data-stu-id="740a7-172">Current availability</span></span>  

<span data-ttu-id="740a7-173">ブラウザエンジンのプログレッシブ Web アプリのさまざまな機能をサポートしています。多くのアーキテクチャコンポーネントに対応していますが、最も重要なのは[FETCH API][MDNFetchApi]の基礎となるネットワークインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="740a7-173">Browser engine support for Progressive Web Apps calls for a number of architectural components, the most significant being the networking infrastructure underlying the [Fetch API][MDNFetchApi].</span></span>  <span data-ttu-id="740a7-174">EdgeHTML エンジンでの PWA のサポートは、Windows 10 1809 リリースで完了しています。</span><span class="sxs-lookup"><span data-stu-id="740a7-174">PWA support in the EdgeHTML engine was completed in the Windows 10 1809 release.</span></span>  <span data-ttu-id="740a7-175">その時間が EdgeHTML エンジンに組み込まれていないため、web の標準をさらに改善するため、互換性テストを実行し、機能の検出を使用して、PWA の必要な機能が EdgeHTML プラットフォームでサポートされていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-175">Further improvements to web standards since that time will not be incorporated into the EdgeHTML engine so be sure to run compatibility tests and use feature detection to gracefully fallback should the feature your PWA needs be unsupported on the EdgeHTML platform.</span></span>  

<span data-ttu-id="740a7-176">今後の Microsoft Edge \ (Chromium \) リリースの2020では、ブラウザープラットフォームは、Chromium ブラウザーがサポートされているデバイス間で動作するこれらの機能を完全にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="740a7-176">For the upcoming Microsoft Edge \(Chromium\) release in 2020, the browser platform has full support for these features that work across devices where the Chromium browser is supported.</span></span>  

<span data-ttu-id="740a7-177">EdgeHTML と Windows では、標準ベースの PWA テクノロジの現在の状態は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="740a7-177">For EdgeHTML and Windows, here is the current status of standards-based PWA technologies:</span></span>  

| <span data-ttu-id="740a7-178">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="740a7-178">Technology</span></span> | <span data-ttu-id="740a7-179">目的</span><span class="sxs-lookup"><span data-stu-id="740a7-179">Purpose</span></span> | <span data-ttu-id="740a7-180">対象</span><span class="sxs-lookup"><span data-stu-id="740a7-180">Availability</span></span> | <span data-ttu-id="740a7-181">使用上の注意</span><span class="sxs-lookup"><span data-stu-id="740a7-181">Usage notes</span></span> |  
|:--- |:--- |:--- |:--- |  
| [<span data-ttu-id="740a7-182">Web アプリケーションマニフェスト</span><span class="sxs-lookup"><span data-stu-id="740a7-182">Web Application Manifest</span></span>][MDNWebAppManifest] | <span data-ttu-id="740a7-183">インストールとアプリストアのプロモーションを有効にするために、ホスト OS にアプリのメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="740a7-183">Provides app metadata to the host OS for enabling installation and app store promotion.</span></span>  <span data-ttu-id="740a7-184">Microsoft Store で PWAs が必要。</span><span class="sxs-lookup"><span data-stu-id="740a7-184">Required for PWAs in the Microsoft Store.</span></span>  | [<span data-ttu-id="740a7-185">開発中</span><span class="sxs-lookup"><span data-stu-id="740a7-185">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | <span data-ttu-id="740a7-186">現時点では、 [PWA ビルダー][|::ref2::|]を使用して、W3C に準拠した JSON マニフェストを生成し、さまざまな OS プラットフォーム用にアプリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="740a7-186">For now, you are able to use [PWA Builder][|::ref2::|] to generate a W3C-compliant JSON manifest and package your app for various OS platforms.</span></span>  <span data-ttu-id="740a7-187">Windows の場合、PWA ビルダーでは、JSON マニフェストが `.appxmanifest` windows 10 アプリで必要な \ (XML \) 形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="740a7-187">For Windows, PWA Builder translates your JSON manifest into the `.appxmanifest` \(XML\) format required by Windows 10 apps.</span></span>  |  
| [<span data-ttu-id="740a7-188">取得 API</span><span class="sxs-lookup"><span data-stu-id="740a7-188">Fetch API</span></span>][MDNFetchApi] | <span data-ttu-id="740a7-189">ページリソースの非同期ネットワーク \ (要求、返信) を提供します。</span><span class="sxs-lookup"><span data-stu-id="740a7-189">Provides asynchronous networking \(requests, responses\) for page resources</span></span> |<span data-ttu-id="740a7-190">[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /Build 14393 +</span><span class="sxs-lookup"><span data-stu-id="740a7-190">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="740a7-191">[サービスワーカー API][MDNServiceWorkerApi]構文は、フェッチベースのネットワーク api に基づいています。</span><span class="sxs-lookup"><span data-stu-id="740a7-191">The [Service Worker API][MDNServiceWorkerApi] syntax is based on Fetch-based networking APIs.</span></span>  <span data-ttu-id="740a7-192">さらに、 [FETCH API][MDNFetchApi]をもっと一般的な新しい方法として使うこともでき `XMLHttpRequest` ます。</span><span class="sxs-lookup"><span data-stu-id="740a7-192">You are able to also use [Fetch API][MDNFetchApi] more generally as a modern alternative to `XMLHttpRequest`.</span></span>  |  
| [<span data-ttu-id="740a7-193">Service Worker API</span><span class="sxs-lookup"><span data-stu-id="740a7-193">Service Worker API</span></span>][MDNServiceWorkerApi] | <span data-ttu-id="740a7-194">Web ページに依存しないイベント駆動型のスクリプトを実行する、オフライン対応の web アプリモデル/ネットワークプロキシを提供します。</span><span class="sxs-lookup"><span data-stu-id="740a7-194">Provides an offline-capable web app model / network proxy, where event-driven scripts run independent of web pages</span></span>  | <span data-ttu-id="740a7-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 +</span><span class="sxs-lookup"><span data-stu-id="740a7-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="740a7-196">`Enable Service Workers`EdgeHTML 16 には、実験的サポート \ (裏に旗) が同梱されています。</span><span class="sxs-lookup"><span data-stu-id="740a7-196">Experimental support \(behind `Enable Service Workers` flag\) shipped in EdgeHTML 16.</span></span>  <span data-ttu-id="740a7-197">EdgeHTML 17 + ビルドでは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="740a7-197">On by default in EdgeHTML 17+ builds.</span></span>  |  
| [<span data-ttu-id="740a7-198">キャッシュ API</span><span class="sxs-lookup"><span data-stu-id="740a7-198">Cache API</span></span>][MDNCache] | <span data-ttu-id="740a7-199">ネットワーク要求と応答のペアのストレージメカニズムを提供します</span><span class="sxs-lookup"><span data-stu-id="740a7-199">Provides a storage mechanism for network request/response pairs</span></span> | <span data-ttu-id="740a7-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 +</span><span class="sxs-lookup"><span data-stu-id="740a7-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="740a7-201">上の「 [Service WORKER API][MDNServiceWorkerApi]のメモ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-201">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  |  
| [<span data-ttu-id="740a7-202">プッシュ API</span><span class="sxs-lookup"><span data-stu-id="740a7-202">Push API</span></span>][MDNPushApi] | <span data-ttu-id="740a7-203">サービスワーカーがプッシュ通知をサブスクライブできるようにします。</span><span class="sxs-lookup"><span data-stu-id="740a7-203">Enables a service worker to subscribe to push notifications</span></span> |<span data-ttu-id="740a7-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 +</span><span class="sxs-lookup"><span data-stu-id="740a7-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span>| <span data-ttu-id="740a7-205">上の「 [Service WORKER API][MDNServiceWorkerApi]のメモ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-205">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  <span data-ttu-id="740a7-206">Windows 10 アプリ \ (PWAs を含む) では、W3C[プッシュ API][MDNPushApi]をサポートするプッシュ通知を実行するために、 [Windows プッシュ通知サービス \ (WNS)][WindowsUWPControlsPatternTilesNotificationsWns]が必要です。</span><span class="sxs-lookup"><span data-stu-id="740a7-206">Windows 10 apps \(including PWAs\) require the [Windows Push Notification Service \(WNS\)][WindowsUWPControlsPatternTilesNotificationsWns] to deliver push notifications, which supports the W3C [Push API][MDNPushApi].</span></span>  |  
| [<span data-ttu-id="740a7-207">通知 API</span><span class="sxs-lookup"><span data-stu-id="740a7-207">Notifications API</span></span>][MDNNotificationsApi] | <span data-ttu-id="740a7-208">サービスワーカーが、プッシュメッセージ時にシステム通知をユーザーに表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="740a7-208">Enables a service worker to display a system notification to the user upon push message</span></span> | <span data-ttu-id="740a7-209">[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /Build 14393 +</span><span class="sxs-lookup"><span data-stu-id="740a7-209">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="740a7-210">EdgeHTML の Web 通知は、ユーザーがアプリの通知を管理し、[非表示時間][MicrosoftSupportWindowsFocusAssist]を設定できる Windows 10[アクションセンター][MicrosoftSupportWindowsNotificationSettings]と完全に統合されています。</span><span class="sxs-lookup"><span data-stu-id="740a7-210">Web Notifications in EdgeHTML are fully integrated with the Windows 10 [Action Center][MicrosoftSupportWindowsNotificationSettings], where users are able to manage app notifications and set [Quiet Hours][MicrosoftSupportWindowsFocusAssist].</span></span>  |  
| [<span data-ttu-id="740a7-211">バックグラウンド同期 API</span><span class="sxs-lookup"><span data-stu-id="740a7-211">Background Sync API</span></span>][MDNSyncManager] | <span data-ttu-id="740a7-212">ユーザーがオンラインに戻ったことをサービスワーカーに通知するための API を提供します。また、定期的なイベントのスケジュールを設定して、ローカルデータをサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="740a7-212">Provides an API for notifying a service worker that the user has come back online and for scheduling periodic events to synchronize local data with the server</span></span> | [<span data-ttu-id="740a7-213">開発中</span><span class="sxs-lookup"><span data-stu-id="740a7-213">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | <span data-ttu-id="740a7-214">現時点では、ネイティブの[WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks]を使って、Windows 10 アプリとして実行されたときに PWA のバックグラウンドタスクを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="740a7-214">For now, you are able to use the native [WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] to implement background tasks for your PWA when it runs as a Windows 10 app.</span></span>  |  

<span data-ttu-id="740a7-215">Windows 10 での Microsoft ストアサポートの現在の状態は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="740a7-215">Here is the current status of Microsoft Store support for PWAs on Windows 10:</span></span>  

| <span data-ttu-id="740a7-216">ストアへの申請の方法</span><span class="sxs-lookup"><span data-stu-id="740a7-216">Store submission method</span></span> | <span data-ttu-id="740a7-217">ステータス</span><span class="sxs-lookup"><span data-stu-id="740a7-217">Status</span></span> | <span data-ttu-id="740a7-218">詳細</span><span class="sxs-lookup"><span data-stu-id="740a7-218">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="740a7-219">手動 \ (開発者によって開始されました)</span><span class="sxs-lookup"><span data-stu-id="740a7-219">Manual \(developer initiated\)</span></span> | <span data-ttu-id="740a7-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="740a7-220">Available</span></span> | <span data-ttu-id="740a7-221">開始するには[、Microsoft Store で Pwas (EdgeHTML)][PwaEdgehtmlMicrosoftStore]を確認してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-221">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] to get started.</span></span>  |  
| <span data-ttu-id="740a7-222">自動 \ (Bing \) での自動インデックス作成</span><span class="sxs-lookup"><span data-stu-id="740a7-222">Automatic \(auto-indexed with Bing\)</span></span> | <span data-ttu-id="740a7-223">近日提供予定</span><span class="sxs-lookup"><span data-stu-id="740a7-223">Coming soon</span></span> | <span data-ttu-id="740a7-224">現時点では、アプリパートナーの限定されたサブセットで PWA のオンボードプロセスを[試験][WindowsBlogsWelcomingPWAsEdgeWindows]的に行っています。</span><span class="sxs-lookup"><span data-stu-id="740a7-224">We are [currently piloting][WindowsBlogsWelcomingPWAsEdgeWindows] the PWA onboarding process with a limited subset of app partners.</span></span>  <span data-ttu-id="740a7-225">今後数ヶ月で、Microsoft はメインストリーム web 上で Microsoft ストアに配信されました。</span><span class="sxs-lookup"><span data-stu-id="740a7-225">In the coming months Microsoft welcomes PWAs across the mainstream web to the Microsoft Store.</span></span>  <span data-ttu-id="740a7-226">自動生成された PWA リストの Microsoft ストアの要件の詳細については、「 [Bing を使用した自動][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]生成される pwa のインポートの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="740a7-226">Check out [Automatic PWA importing with Bing][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] to learn more about Microsoft Store requirements for auto-generated PWA listings.</span></span>  |  

<!-- image links -->  

[ImageISearch]: media/i_search.png  
[ImageIPackage]: media/i_package.png  
[ImageIPushNotification]: media/i_push-notification.png  
[ImageIOffline]: media/i_offline.png  
[ImageIProgressive]: media/i_progressive.png  
[ImageISecurity]: media/i_security.png  
[ImageIResponsive]: media/i_responsive.png  
[ImageILink]: media/i_link.png  

<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools のプレビュー-DevTools プロトコルクライアント"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "エミュレーション"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 の新機能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 の新機能"  
[PwaChromiumIndex]: ../progressive-web-apps-chromium/index.md "Windows のプログレッシブ Web アプリ (Chromium)"  
[PwaEdgehtmlGetStarted]: ../progressive-web-apps-edgehtml/get-started.md "プログレッシブ Web アプリ (EdgeHTML) の使用を開始する"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store のプログレッシブ Web アプリ"
[PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Microsoft Store での自動送信 Web アプリの条件"  
[PwaEdgehtmlMicrosoftStoreImportingBing]: microsoft-store.md#automatic-pwa-importing-with-bing "Microsoft Store の Bing プログレッシブ Web アプリ (EdgeHTML) を使用した自動 PWA インポート"  


[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows プッシュ通知サービス \ (WNS \) の概要"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox およびテレビ向け設計"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンドタスクによるアプリのサポート"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "Windows アプリとゲームを公開する"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開く"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "Microsoft Edge および Windows 10 へのプログレッシブ Web アプリの歓迎-Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API-Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリケーションマニフェスト-Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即座のテスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向けの Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "Windows 10 でフォーカスアシストのオンとオフを切り替える"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "Windows 10 の通知設定を変更する"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "プログレッシブエンハンスメントについて-リストとの分離"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "アプリ |MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "クロスブラウザーテスト |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS の柔軟なボックスレイアウト |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッドレイアウト |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "メディアクエリ |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "見つけやすい web アプリの利点"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "インストール可能なプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "Linkable プログレッシブ web アプリの利点"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "ネットワークに依存しないプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "プログレッシブプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "Engageable-プログレッシブ web アプリの利点"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "応答性の高いプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "安全なプログレッシブ web アプリの利点"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "応答性の高い画像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "web ヒント"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープリンク-Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "応答性の高い web デザイン-Wikipedia"  
