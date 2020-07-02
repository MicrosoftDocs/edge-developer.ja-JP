---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリケーションの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 370b5da2d42412a08a5c7f8a7401496fa70e3065
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844405"
---
# <span data-ttu-id="d03c3-104">WebView2 を使用したアプリケーションの配布</span><span class="sxs-lookup"><span data-stu-id="d03c3-104">Distribution of applications using WebView2</span></span>  

<span data-ttu-id="d03c3-105">WebView2 コントロールでは、Microsoft Edge \ (Chromium \) プラットフォームが利用されます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-105">The WebView2 control utilizes the Microsoft Edge \(Chromium\) platform.</span></span>  <span data-ttu-id="d03c3-106">アプリをパッケージ化して配布する場合は、アプリが起動される前にプラットフォームまたは WebView2 ランタイムのコピーが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-106">When packaging and distributing your app, make sure a copy of the platform or the WebView2 Runtime is present before the app starts.</span></span>  <span data-ttu-id="d03c3-107">次のページでは、お客様が WebView2 ランタイムをインストールして、WebView2 アプリケーション用に2つの配布モードを使用する方法について説明します。 [Evergreen](#evergreen-distribution-mode)と[修正バージョン](#fixed-version-distribution-mode)。</span><span class="sxs-lookup"><span data-stu-id="d03c3-107">The following page describes how you \(the developer\) are able to ensure that the WebView2 Runtime is installed and use of the two distribution modes for your WebView2 application:  [Evergreen](#evergreen-distribution-mode) and [Fixed version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="d03c3-108">Evergreen 配布モード</span><span class="sxs-lookup"><span data-stu-id="d03c3-108">Evergreen distribution mode</span></span>  

<span data-ttu-id="d03c3-109">Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-109">The evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="d03c3-110">Evergreen 配布モードには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-110">The evergreen distribution mode has the following characteristics.</span></span>  

*   <span data-ttu-id="d03c3-111">Web platform は、追加の作業を行わなくても自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-111">The web platform updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="d03c3-112">Evergreen 配布モードを利用するすべてのアプリケーションでは、プラットフォームのバイナリの共有コピーが使用されます。これにより、ディスク領域を節約できます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-112">All applications that leverage the evergreen distribution mode use a shared copy of the platform binaries, which saves disk space.</span></span>  

<span data-ttu-id="d03c3-113">アプリケーションが web プラットフォームとして使用できるチャネル WebView2 は複数あります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-113">There are multiple channels WebView2 that applications may use as the web platform.</span></span>  <span data-ttu-id="d03c3-114">既定では、WebView2 は、WebView2 SDK の最小バージョン要件を満たすデバイスで利用可能な最も安定したチャネルをターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="d03c3-114">By default, WebView2 targets the most stable channel available on the device that meets the minimum version requirement of the WebView2 SDK.</span></span>  <span data-ttu-id="d03c3-115">以下のチャネルは、安定していないチャネルの順に一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="d03c3-115">The following channels are listed in order from most to least stable channel.</span></span>  

1.  <span data-ttu-id="d03c3-116">WebView2 ランタイム \ (プレビュー \)</span><span class="sxs-lookup"><span data-stu-id="d03c3-116">WebView2 Runtime \(Preview\)</span></span>  
1.  <span data-ttu-id="d03c3-117">Microsoft Edge Beta チャネル</span><span class="sxs-lookup"><span data-stu-id="d03c3-117">Microsoft Edge Beta Channel</span></span>  
1.  <span data-ttu-id="d03c3-118">Microsoft Edge Dev チャネル</span><span class="sxs-lookup"><span data-stu-id="d03c3-118">Microsoft Edge Dev Channel</span></span>  
1.  <span data-ttu-id="d03c3-119">Microsoft Edge Canary チャネル</span><span class="sxs-lookup"><span data-stu-id="d03c3-119">Microsoft Edge Canary Channel</span></span>    

> [!NOTE]
> <span data-ttu-id="d03c3-120">ほとんどの開発者は、evergreen の配布モデルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d03c3-120">The evergreen distribution model is recommended for most developers.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d03c3-121">Microsoft Edge の安定したチャネルは、WebView2 の有効なターゲットではないため、この理由については後で説明します。</span><span class="sxs-lookup"><span data-stu-id="d03c3-121">Microsoft Edge Stable Channel is not a valid target for WebView2, and the reasons are described later.</span></span>  

<span data-ttu-id="d03c3-122">バージョン管理の詳細については、「[バージョン管理][ConceptsVersioning]と[グローバル][ReferenceWin3209538WebviewIdl]化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-122">For more information about versioning, see [Versioning][ConceptsVersioning] and [Globals][ReferenceWin3209538WebviewIdl].</span></span>  

### <span data-ttu-id="d03c3-123">WebView2 のランタイムとインストーラーについて (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d03c3-123">Understand the WebView2 Runtime and installer (Preview)</span></span>  

<span data-ttu-id="d03c3-124">アプリケーションが実行されているすべてのユーザーコンピューターに Microsoft Edge の厩舎チャネルがインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-124">Microsoft Edge Stable Channel may not be installed on all user machines where your application runs.</span></span>  <span data-ttu-id="d03c3-125">ユーザーが Microsoft Edge をインストールする必要がないように、アプリケーションでは Evergreen WebView2 Runtime および Installer \ (Preview \) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-125">Instead of requiring that users install Microsoft Edge, your application may use the Evergreen WebView2 Runtime and Installer \(Preview\).</span></span>  <span data-ttu-id="d03c3-126">WebView2 Runtime は、WebView2 アプリケーションを実行するために使用される Microsoft Edge バイナリのカスタマイズされたコピーです。</span><span class="sxs-lookup"><span data-stu-id="d03c3-126">The WebView2 Runtime is a customized copy of the Microsoft Edge binaries that is used to run your WebView2 applications.</span></span>  <span data-ttu-id="d03c3-127">WebView2 ランタイムがインストールされている場合、ユーザーは通常のブラウザーとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d03c3-127">When the WebView2 Runtime is installed, users are not able to use it as a normal browser.</span></span>  <span data-ttu-id="d03c3-128">たとえば、デスクトップショートカット、スタートメニューエントリがない場合、ユーザーはランタイムバイナリを使用してブラウザーウィンドウを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="d03c3-128">For example, there is no desktop shortcut, start menu entry, users are not able to open a browser window using the Runtime binaries, and so on.</span></span>  <span data-ttu-id="d03c3-129">デバイス上のすべての Evergreen WebView2 アプリケーションは、単一の Evergreen WebView2 ランタイムインストールを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-129">All Evergreen WebView2 applications on the device may use a single Evergreen WebView2 Runtime installation.</span></span>  

<span data-ttu-id="d03c3-130">現在、プレビュー中に、Evergreen WebView2 Runtime と Microsoft Edge Dev チャネルが同時に更新され、同じビルドが存在します。</span><span class="sxs-lookup"><span data-stu-id="d03c3-130">Today during the preview, the Evergreen WebView2 Runtime and Microsoft Edge Dev Channel are updated at the same time and have the same build.</span></span>  <span data-ttu-id="d03c3-131">プレビュー中に、WebView2 チームは WebView2 ランタイムを更新して、Microsoft Edge ベータチャネルと同じビルドを一致させます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-131">In the future during the Preview, the WebView2 Team plans to update the WebView2 Runtime and match the same build as the Microsoft Edge Beta Channel.</span></span>  <span data-ttu-id="d03c3-132">今後、WebView2 が一般的な可用性 \ (GA) に達すると、WebView2 チームは WebView2 ランタイムの更新を計画し、Microsoft Edge の厩舎チャネルと同じビルドを一致させます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-132">In the future when WebView2 reaches General Availability \(GA\), the WebView2 Team plans to update the WebView2 Runtime and match the same build as the Microsoft Edge Stable Channel.</span></span>  <span data-ttu-id="d03c3-133">GA 後、アプリケーションでは、WebView2 ランタイムを運用環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-133">After GA, applications should use the WebView2 Runtime in production.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d03c3-134">プレビュー中に WebView2 アプリケーションを運用環境に出荷しないでください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-134">Do not ship WebView2 applications in production during the preview.</span></span>  

<span data-ttu-id="d03c3-135">Evergreen WebView2 ランタイムが利用可能であることを確認するには、次のワークフローを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-135">Please use the following workflow to ensure the Evergreen WebView2 Runtime is available.</span></span>  

1.  <span data-ttu-id="d03c3-136">最新の[Evergreen WebView2 ランタイムインストーラー][Webview2Installer]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d03c3-136">Download the latest [Evergreen WebView2 Runtime Installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="d03c3-137">アプリケーションのインストーラーまたはアップデーターにインストーラーを含めます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-137">Include the installer in your application installer or updater.</span></span>  
1.  <span data-ttu-id="d03c3-138">アプリケーションのインストールまたは更新時に、ユーザーのコンピューターに Evergreen WebView2 ランタイムが既にインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d03c3-138">During your application installation or update, check if the Evergreen WebView2 Runtime is already installed on the user machine.</span></span>  <span data-ttu-id="d03c3-139">見つからない場合、アプリケーションはインストーラーを起動してランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d03c3-139">If not, the application invokes the installer to install the runtime.</span></span>  

<span data-ttu-id="d03c3-140">シナリオによっては、上記のワークフローを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-140">Depending on your scenario, you may need to change the above workflow.</span></span>  <span data-ttu-id="d03c3-141">たとえば、アプリケーションのインストーラーでは、アプリケーションパッケージに Evergreen WebView2 Runtime Installer を含める代わりに、インストーラーをダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-141">For example, your application installer may download the Evergreen WebView2 Runtime Installer instead of including it in your application package.</span></span>  

> [!NOTE]
> <span data-ttu-id="d03c3-142">WebView2 Runtime インストーラーと WebView2 Runtime インストーラーの両方がプレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="d03c3-142">Both the WebView2 Runtime and WebView2 Runtime installer are in preview.</span></span>  <span data-ttu-id="d03c3-143">プレビューには、初期スコープが限定されています。また、x64 の Windows 10 では、スタンドアロンのマシン単位インストールとしてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-143">The preview has a limited initial scope and is only available as a standalone, per-machine install on Windows 10 on x64.</span></span>  <span data-ttu-id="d03c3-144">将来的には、Windows 7、x86、および ARM64 のサポートが計画されています。</span><span class="sxs-lookup"><span data-stu-id="d03c3-144">In the future, support for Windows 7, x86, and ARM64 is planned.</span></span>  

### <span data-ttu-id="d03c3-145">WebView2 Runtime と非安定した Microsoft Edge チャネルを使用するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="d03c3-145">Best practices for using WebView2 Runtime and non-stable Microsoft Edge channels</span></span>  

<span data-ttu-id="d03c3-146">プレビュー時には、次の推奨事項について検討してください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-146">Consider the following recommendations during the preview.</span></span>  

*   <span data-ttu-id="d03c3-147">[Evergreen WebView2 Runtime と Installer][Webview2Installer]を使って、パッケージ化パイプラインと配布パイプラインを開発またはテストしてください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-147">Make sure to use the [Evergreen WebView2 Runtime and Installer][Webview2Installer] to develop or test your packaging and distribution pipeline.</span></span>  <span data-ttu-id="d03c3-148">今後は、運用アプリケーションにインストーラーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-148">In the future, your production application should include the installer.</span></span>  
*   <span data-ttu-id="d03c3-149">アプリケーションを開発するには、Evergreen WebView2 ランタイムを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-149">For developing your application, you may use the Evergreen WebView2 Runtime.</span></span>  <span data-ttu-id="d03c3-150">ただし、ランタイムは Dev チャネルからベータチャネルまたは安定したチャネルにシフトするため、ランタイムビルド番号は最新の preview WebView2 SDK 最小バージョン要件を満たしていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-150">However, as the runtime shifts from the Dev Channel to the Beta Channel or Stable Channel, the runtime build number may not meet the most recent preview WebView2 SDK minimum version requirements.</span></span>  <span data-ttu-id="d03c3-151">最新の SDK を使用する場合は、Microsoft Edge カナリアチャネルをインストールして、デバイスで互換性のあるビルドが利用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d03c3-151">If you wish to use the most recent SDK, install the Microsoft Edge Canary channel to ensure a compatible build is available on the device.</span></span>  <span data-ttu-id="d03c3-152">バージョン管理の詳細については、「[バージョン管理][ConceptsVersioning]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d03c3-152">For more information about versioning, see [Versioning][ConceptsVersioning].</span></span>  
*   <span data-ttu-id="d03c3-153">安定したチャネルで利用できないプラットフォームに対する変更と互換性のある web コンテンツをテストするには、必要に応じて、適切でない非安定チャネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d03c3-153">To test your web content for compatibility with changes to the platform not available in the Stable Channel, use the appropriate non-Stable Channel as required.</span></span>  

## <span data-ttu-id="d03c3-154">固定バージョンの配布モード</span><span class="sxs-lookup"><span data-stu-id="d03c3-154">Fixed version distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="d03c3-155">固定バージョンの配布モデルは現在利用できません。</span><span class="sxs-lookup"><span data-stu-id="d03c3-155">The fixed version distribution model is currently not available.</span></span>  

<span data-ttu-id="d03c3-156">制限された環境では、固定バージョン \ (以前は "独自の \" 配布モード) をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="d03c3-156">For constrained environments, there are plans to support a fixed version \(previously named bring-your-own\) distribution mode.</span></span>  <span data-ttu-id="d03c3-157">修正済みのバージョン配布モードでは、特定のバージョンの WebView2 ランタイムを選択してパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-157">The fixed version distribution mode allows you to select and package a specific version of the WebView2 Runtime.</span></span>  <span data-ttu-id="d03c3-158">修正されたバージョンの配布モードでは、どのバージョンの WebView2 ランタイムをアプリケーションで使うか、ユーザーコンピューターが更新されるタイミングを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="d03c3-158">The fixed version distribution mode allows you to control which version of the WebView2 Runtime is used by your application, and when user machines are updated.</span></span>  <span data-ttu-id="d03c3-159">修正済みのバージョン配布モードでは、自動更新は取得されません。また、手動で更新プログラムを適用することを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d03c3-159">The fixed version distribution mode does not receive any automatic updates, and you should plan to manually apply updates.</span></span>  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ReferenceWin3209538WebviewIdl]: ../reference/win32/0-9-538/webview2-idl.md  "Globals |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  
