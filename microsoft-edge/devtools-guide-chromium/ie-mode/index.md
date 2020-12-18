---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorerモードと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: Microsoft Edge, Web 開発, f12 ツール, devtools, ie11, internet explorer 11, ie モード
ms.openlocfilehash: c88da78e073a75a664561aba899ca5c8ada78477
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234379"
---
# <span data-ttu-id="84d39-104">Internet Explorerモードと DevTools</span><span class="sxs-lookup"><span data-stu-id="84d39-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="84d39-105">この記事では、Internet Explorer \(IE mode\) を Microsoft Edge \(Chromium\) DevTools と統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84d39-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <span data-ttu-id="84d39-106">IE モードについて</span><span class="sxs-lookup"><span data-stu-id="84d39-106">Understanding IE mode</span></span>  

<span data-ttu-id="84d39-107">IE モードでは、企業は 11 か月 11 日にのみ動作する Web サイトのInternet Explorerできます。</span><span class="sxs-lookup"><span data-stu-id="84d39-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="84d39-108">Microsoft Edge \(Chromium\) でこれらの Web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、サイトがタブに表示されます。 この機能により、企業は現在、最新の Web ブラウザーと互換性がないテクノロジとの互換性を管理できます。</span><span class="sxs-lookup"><span data-stu-id="84d39-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="84d39-109">次のテクノロジのサポートは、IE モードに含まれています。</span><span class="sxs-lookup"><span data-stu-id="84d39-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="84d39-110">IE ドキュメント モード</span><span class="sxs-lookup"><span data-stu-id="84d39-110">IE document modes</span></span>  
*   <span data-ttu-id="84d39-111">ActiveX コントロール</span><span class="sxs-lookup"><span data-stu-id="84d39-111">ActiveX controls</span></span>  
*   <span data-ttu-id="84d39-112">その他のレガシ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="84d39-112">other legacy components</span></span>  

<span data-ttu-id="84d39-113">IE モードでは、レンダリング プロセスは 11 Internet Explorerされます。</span><span class="sxs-lookup"><span data-stu-id="84d39-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="84d39-114">Microsoft Edge \(Chromium\) プロセス マネージャーは、レンダリング プロセスの有効期間を処理します。</span><span class="sxs-lookup"><span data-stu-id="84d39-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="84d39-115">これは、特定のサイト \(または app\) のタブの有効期間に制限されます。</span><span class="sxs-lookup"><span data-stu-id="84d39-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="84d39-116">タブが IE モードでレンダリングされる場合、特定のタブのアドレス バーにバッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84d39-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="アドレス バーの IE モード バッジ" lightbox="../media/ie-mode-badge.msft.png":::
   <span data-ttu-id="84d39-118">アドレス バーの IE モード バッジ</span><span class="sxs-lookup"><span data-stu-id="84d39-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="84d39-119">IE モードは現在、Windows 10 バージョン 1903 \(May 2019 Update\) で利用できますが、サポートされている Windows プラットフォームはすべて近日公開される予定です。</span><span class="sxs-lookup"><span data-stu-id="84d39-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <span data-ttu-id="84d39-120">IE モードのタブで DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="84d39-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="84d39-121">WEB サイトのドキュメント モードを IE モードで表示する場合は、アドレス バーでバッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="84d39-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モード バッジを使ったドキュメント モードの表示" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="84d39-123">IE モード バッジを使ったドキュメント モードの表示</span><span class="sxs-lookup"><span data-stu-id="84d39-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="84d39-124">タブが IE モードを使用している場合、DevTools は動作しなく、次の条件が発生します。</span><span class="sxs-lookup"><span data-stu-id="84d39-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="84d39-125">選択または選択 `F12` すると `Ctrl` + `Shift` + `I` 、Microsoft Edge \(Chromium\) DevTools の空のインスタンスが起動すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84d39-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="84d39-126">コンテキスト メニュー \(右クリック\) を開き、[ソースの表示] を選択 **すると、メモ**帳が起動します。</span><span class="sxs-lookup"><span data-stu-id="84d39-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="84d39-127">コンテキスト メニュー \(右クリック\) を開いた場合 **、Inspect 要素** は表示されません。</span><span class="sxs-lookup"><span data-stu-id="84d39-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="84d39-128">DevTools \(Network **and** **Performance** tools\) 内の多くのツールが動作しない理由は、レンダリング エンジンが IE モードで Chromium から Internet Explorer 11 に切り替わるという点です。</span><span class="sxs-lookup"><span data-stu-id="84d39-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="84d39-129">フィードバックを提供するには [、Microsoft Edge DevTools](#getting-in-touch-with-the-microsoft-edge-devtools-team)チームと連絡を取る方法に移動します。</span><span class="sxs-lookup"><span data-stu-id="84d39-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="IE モードで起動された DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="84d39-131">IE モードで起動された DevTools</span><span class="sxs-lookup"><span data-stu-id="84d39-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="84d39-132">Internet Explorer 11 Internet Explorer IE モードで 11 ベースの Web サイト \(または app\) をテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84d39-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="84d39-133">Internet Explorer 11 を開きます。</span><span class="sxs-lookup"><span data-stu-id="84d39-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="84d39-134">Windows 10 で、Windows 11 のショートカットInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="84d39-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="84d39-135">**[スタート] メニュー**  > **Windows アクセサリ**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="84d39-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="84d39-136">Windows 7 で、11 をInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="84d39-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="84d39-137">**[スタート] メニュー**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="84d39-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="84d39-138">このInternet Explorer 11 で、同じ Web ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="84d39-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="84d39-139">DevTools Internet Explorer起動します。</span><span class="sxs-lookup"><span data-stu-id="84d39-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="84d39-140">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="84d39-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="84d39-141">任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き **、Inspect 要素を選択します**。</span><span class="sxs-lookup"><span data-stu-id="84d39-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="84d39-142">これらのツールの使い方について詳しくは [、「F12][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]開発者ツールの使用」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="84d39-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <span data-ttu-id="84d39-143">リモート デバッグと IE モード</span><span class="sxs-lookup"><span data-stu-id="84d39-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="84d39-144">コマンド ライン インターフェイスからリモート デバッグを有効にした状態で Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="84d39-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="84d39-145">Visual Studio、Visual Studio、および他の開発ツールは、通常、Microsoft Edge を起動するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="84d39-145">Visual Studio, Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="84d39-146">次のコマンドは、リモート デバッグ ポートを設定して Microsoft Edge を起動します `9222` 。</span><span class="sxs-lookup"><span data-stu-id="84d39-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="84d39-147">コマンド ライン引数を使って Microsoft Edge \(Chromium\) を起動すると、IE モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="84d39-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="84d39-148">IE モードで表示される Web サイト \(またはアプリ\) に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="84d39-148">You may still navigate to websites \(or apps\) that would otherwise display in IE mode.</span></span>  <span data-ttu-id="84d39-149">Web サイト \(または app\) コンテンツは、11 ではなく Chromium をInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="84d39-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="84d39-150">IE11 に依存する Web ページの部分 (ActiveXなど) が正しくレンダリングされない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84d39-150">Expect the parts of the webpages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="84d39-151">IE モード バッジがアドレス バーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="84d39-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="84d39-152">Microsoft Edge \(Chromium\) を完全に閉じて再起動するまで、IE モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="84d39-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="84d39-153">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="84d39-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用する |Microsoft Docs"  
