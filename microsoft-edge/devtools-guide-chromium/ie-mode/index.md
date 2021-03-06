---
description: IE モードと Microsoft Edge (クロム) DevTools
title: Internet Explorerと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, ie11, internet explorer 11, ie mode
ms.openlocfilehash: e65869cd88b449dcde0aec25c77df27f99b78f8d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398603"
---
# <a name="internet-explorer-mode-and-the-devtools"></a><span data-ttu-id="6f8ea-104">Internet Explorerと DevTools</span><span class="sxs-lookup"><span data-stu-id="6f8ea-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="6f8ea-105">この記事では、Internet Explorer \(IE モード\) を Microsoft Edge \(Chromium\) DevTools と統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <a name="understanding-ie-mode"></a><span data-ttu-id="6f8ea-106">IE モードについて</span><span class="sxs-lookup"><span data-stu-id="6f8ea-106">Understanding IE mode</span></span>  

<span data-ttu-id="6f8ea-107">IE モードを使用すると、企業は 11 でしか動作しない web サイトのInternet Explorerできます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="6f8ea-108">Microsoft Edge \(Chromium\) のこれらの Web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、サイトがタブに表示されます。 この機能により、企業は現在最新の Web ブラウザーと互換性がないテクノロジとの互換性を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="6f8ea-109">IE モードでは、次のテクノロジのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="6f8ea-110">IE ドキュメント モード</span><span class="sxs-lookup"><span data-stu-id="6f8ea-110">IE document modes</span></span>  
*   <span data-ttu-id="6f8ea-111">ActiveX コントロール</span><span class="sxs-lookup"><span data-stu-id="6f8ea-111">ActiveX controls</span></span>  
*   <span data-ttu-id="6f8ea-112">その他の従来のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="6f8ea-112">other legacy components</span></span>  

<span data-ttu-id="6f8ea-113">IE モードでは、レンダリング プロセスは 11 のInternet Explorerされます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="6f8ea-114">Microsoft Edge \(Chromium\) プロセス マネージャーは、レンダリング プロセスの有効期間を処理します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="6f8ea-115">特定のサイト \(または app\) のタブの有効期間に制限されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="6f8ea-116">タブが IE モードでレンダリングされる場合、特定のタブのアドレス バーにバッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="アドレス バーの IE モード バッジ" lightbox="../media/ie-mode-badge.msft.png":::
   <span data-ttu-id="6f8ea-118">アドレス バーの IE モード バッジ</span><span class="sxs-lookup"><span data-stu-id="6f8ea-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="6f8ea-119">IE モードは現在、Windows 10 Version 1903 \(May 2019 Update\) で使用できますが、サポートされているすべての Windows プラットフォームで近日公開予定です。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <a name="launching-the-devtools-on-a-tab-in-ie-mode"></a><span data-ttu-id="6f8ea-120">IE モードでタブで DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="6f8ea-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="6f8ea-121">IE モードで Web サイトのドキュメント モードを表示する場合は、アドレス バーでバッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モード バッジを使用してドキュメント モードを表示する" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="6f8ea-123">IE モード バッジを使用してドキュメント モードを表示する</span><span class="sxs-lookup"><span data-stu-id="6f8ea-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="6f8ea-124">タブが IE モードを使用している場合、DevTools は動作し、次の条件が発生します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="6f8ea-125">選択または選択 `F12` すると `Ctrl` + `Shift` + `I` 、Microsoft Edge \(Chromium\) DevTools の空のインスタンスが起動すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="6f8ea-126">コンテキスト メニュー \(右クリック\) を開き、[ソースの表示] を選択 **すると、メモ**帳が起動します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="6f8ea-127">コンテキスト メニュー \(右クリック\) を開いた場合 **、Inspect 要素は** 表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="6f8ea-128">DevTools \(Network **and** \**Performance tools\** など) 内の多くのツールが機能しない理由は、レンダリング エンジンが IE モードでクロムから Internet Explorer Internet Explorer 11 に切り替わるからです。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="6f8ea-129">フィードバックを提供するには [、[Microsoft Edge DevTools](#getting-in-touch-with-the-microsoft-edge-devtools-team)チームと連絡を取る] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="IE モードで起動された DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="6f8ea-131">IE モードで起動された DevTools</span><span class="sxs-lookup"><span data-stu-id="6f8ea-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="6f8ea-132">11 Internet Explorer 11 および IE モードで 11 ベースの web サイト \(または app\) をInternet Explorerするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="6f8ea-133">11 Internet Explorer開きます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="6f8ea-134">Windows 10 で、11 のショートカットをInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="6f8ea-135">**[スタート] メニュー**  > **Windows アクセサリ**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="6f8ea-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="6f8ea-136">Windows 7 で、[11] をInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="6f8ea-137">**[スタート] メニュー**  > **Internet Explorer 11**.</span><span class="sxs-lookup"><span data-stu-id="6f8ea-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="6f8ea-138">[Internet Explorer 11] で、同じ Web ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="6f8ea-139">DevTools Internet Explorer起動します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="6f8ea-140">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="6f8ea-141">任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[Inspect 要素] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="6f8ea-142">これらのツールの使用方法の詳細については、「F12 開発者ツールを使用する [」に移動します][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <a name="remote-debugging-and-ie-mode"></a><span data-ttu-id="6f8ea-143">リモート デバッグと IE モード</span><span class="sxs-lookup"><span data-stu-id="6f8ea-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="6f8ea-144">コマンド ライン インターフェイスからリモート デバッグを有効にした状態で Microsoft Edge \(Chromium\) を起動します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="6f8ea-145">Microsoft Visual Studio、Microsoft Visual Studioコード、その他の開発ツールは、通常、コマンドを実行して Microsoft Edge を起動します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-145">Microsoft Visual Studio, Microsoft Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="6f8ea-146">次のコマンドは、リモート デバッグ ポートがに設定された Microsoft Edge を起動します `9222` 。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="6f8ea-147">コマンド ライン引数を使用して Microsoft Edge \(Chromium\) を起動すると、IE モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="6f8ea-148">IE モードで表示される Web サイト \(または apps\) に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-148">You may still navigate to websites \(or apps\) that are otherwise displayed in IE mode.</span></span>  <span data-ttu-id="6f8ea-149">Web サイト \(または app\) コンテンツは、11 ではなく、クロムをInternet Explorerします。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="6f8ea-150">IE11 に依存する web ページの部分 (ActiveXなど) が正しく表示されないと予想します。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-150">Expect the parts of the webpages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="6f8ea-151">IE モード バッジはアドレス バーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="6f8ea-152">Microsoft Edge \(Chromium\) を完全に閉じて再起動するまで、IE モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6f8ea-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6f8ea-153">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6f8ea-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用|Microsoft Docs"  
