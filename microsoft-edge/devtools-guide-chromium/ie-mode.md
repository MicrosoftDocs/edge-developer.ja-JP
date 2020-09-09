---
description: IE モードと Microsoft Edge (Chromium) DevTools
title: Internet Explorer モードと DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、ie11、internet explorer 11、ie モード
ms.openlocfilehash: b059cae3ff48a45fe92cbf69e37ad692e329b200
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003971"
---
# <span data-ttu-id="d925a-104">Internet Explorer モードと DevTools</span><span class="sxs-lookup"><span data-stu-id="d925a-104">Internet Explorer mode and the DevTools</span></span>  

<span data-ttu-id="d925a-105">この記事では、Internet Explorer モード \ (IE モード \) と Microsoft Edge \ (Chromium \) DevTools との統合方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d925a-105">This article describes how Internet Explorer mode \(IE mode\) integrates with the Microsoft Edge \(Chromium\) DevTools.</span></span>  

## <span data-ttu-id="d925a-106">IE モードについて</span><span class="sxs-lookup"><span data-stu-id="d925a-106">Understanding IE mode</span></span>  

<span data-ttu-id="d925a-107">IE モードでは、組織は、Internet Explorer 11 でのみ機能する web サイトのリストを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d925a-107">IE mode allows enterprises to specify a list of web sites that only work in Internet Explorer 11.</span></span>  <span data-ttu-id="d925a-108">Microsoft Edge \ (Chromium \) でこれらの web サイトに移動すると、Internet Explorer 11 のインスタンスが実行され、タブに表示されます。 この機能により、エンタープライズは最新の web ブラウザーと互換性のないテクノロジとの互換性を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d925a-108">When you navigate to these web sites in Microsoft Edge \(Chromium\), an instance of Internet Explorer 11 runs and renders the site in a tab.  The functionality allows enterprises to manage compatibility with technologies that are currently not compatible with any modern web browsers.</span></span>  <span data-ttu-id="d925a-109">次のテクノロジのサポートは、IE モードに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d925a-109">Support for the following technologies is included in IE mode.</span></span>  

*   <span data-ttu-id="d925a-110">IE ドキュメントモード</span><span class="sxs-lookup"><span data-stu-id="d925a-110">IE document modes</span></span>  
*   <span data-ttu-id="d925a-111">ActiveX コントロール</span><span class="sxs-lookup"><span data-stu-id="d925a-111">ActiveX controls</span></span>  
*   <span data-ttu-id="d925a-112">その他のレガシコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d925a-112">other legacy components</span></span>  

<span data-ttu-id="d925a-113">IE モードでは、レンダリングプロセスは Internet Explorer 11 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d925a-113">In IE mode, the rendering process is based on Internet Explorer 11.</span></span>  <span data-ttu-id="d925a-114">Microsoft Edge \ (Chromium \) プロセスマネージャーは、レンダリング処理の有効期間を処理します。</span><span class="sxs-lookup"><span data-stu-id="d925a-114">The Microsoft Edge \(Chromium\) process manager handles the lifetime of the rendering process.</span></span>  <span data-ttu-id="d925a-115">特定のサイト \ (またはアプリ \) のタブの有効期間に制限されています。</span><span class="sxs-lookup"><span data-stu-id="d925a-115">It is constrained to the lifetime of the tab for a specific site \(or app\).</span></span>  <span data-ttu-id="d925a-116">タブが IE モードでレンダリングされると、特定のタブのアドレスバーにバッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d925a-116">When a tab renders in IE mode, a badge appears in the address bar for the specific tab.</span></span>  

:::image type="complex" source="./media/ie-mode-badge.msft.png" alt-text="アドレスバーの IE モードバッジ" lightbox="./media/ie-mode-badge.msft.png":::
   <span data-ttu-id="d925a-118">アドレスバーの IE モードバッジ</span><span class="sxs-lookup"><span data-stu-id="d925a-118">IE mode badge in the address bar</span></span>  
:::image-end:::  

<span data-ttu-id="d925a-119">IE モードは現在、Windows 10 バージョン 1903 (2019 の更新プログラム \) で使用できますが、サポートされているすべての Windows プラットフォームに近い将来利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d925a-119">IE mode is currently available on Windows 10 Version 1903 \(May 2019 Update\), but is coming soon to all supported Windows platforms.</span></span>  

## <span data-ttu-id="d925a-120">IE モードのタブで DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="d925a-120">Launching the DevTools on a tab in IE mode</span></span>  

<span data-ttu-id="d925a-121">IE モードで web サイトのドキュメントモードを表示しようとしている場合は、アドレスバーでバッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="d925a-121">If you are trying to view the document mode of a web site in IE mode, choose the badge in the address bar.</span></span>  

:::image type="complex" source="./media/ie-mode-badge-doc-mode.msft.png" alt-text="IE モードバッジを使用したドキュメントモードの表示" lightbox="./media/ie-mode-badge-doc-mode.msft.png":::
   <span data-ttu-id="d925a-123">IE モードバッジを使用したドキュメントモードの表示</span><span class="sxs-lookup"><span data-stu-id="d925a-123">View document mode using IE mode badge</span></span>  
:::image-end:::  

<span data-ttu-id="d925a-124">タブが IE モードを使っている場合、DevTools は動作せず、次の条件が満たされます。</span><span class="sxs-lookup"><span data-stu-id="d925a-124">If a tab is using IE mode, the DevTools do not work and the following conditions occur.</span></span>

*   <span data-ttu-id="d925a-125">選択 `F12` または選択すると `Ctrl` + `Shift` + `I` 、Microsoft Edge \ (Chromium \) devtools の空のインスタンスが起動します。次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d925a-125">If you select `F12` or select `Ctrl`+`Shift`+`I`, a blank instance of the Microsoft Edge \(Chromium\) DevTools is launched displays the following message.</span></span>  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   <span data-ttu-id="d925a-126">コンテキストメニューを開くと (\ を右クリックし)、[ **ソースの表示**] を選択すると、メモ帳が起動します。</span><span class="sxs-lookup"><span data-stu-id="d925a-126">If you open a contextual menu \(right-click\) and choose **View Source**, Notepad is launched.</span></span>  
*   <span data-ttu-id="d925a-127">コンテキストメニューを開くと (右クリック \)、 **検査要素** は表示されません。</span><span class="sxs-lookup"><span data-stu-id="d925a-127">If you open a contextual menu \(right-click\), the **Inspect Element** is not visible.</span></span>  

<span data-ttu-id="d925a-128">DevTools \ ( **Network** や **Performance** tools など) 内の多数のツールが動作しない理由は、Chromium から INTERNET Explorer 11 に IE モードで切り替えたときです。</span><span class="sxs-lookup"><span data-stu-id="d925a-128">The reason that a number of the tools within the DevTools \(like the **Network** and **Performance** tools\) do not work is the rendering engine switches from Chromium to Internet Explorer 11 in IE mode.</span></span>  <span data-ttu-id="d925a-129">フィードバックを提供するには、「 [Microsoft Edge DevTools チームに連絡する」](#getting-in-touch-with-the-microsoft-edge-devtools-team)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d925a-129">To provide feedback, navigate to [Getting in touch with the Microsoft Edge DevTools team](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

:::image type="complex" source="./media/ie-mode-devtools.msft.png" alt-text="IE モードで起動した DevTools" lightbox="./media/ie-mode-devtools.msft.png":::
   <span data-ttu-id="d925a-131">IE モードで起動した DevTools</span><span class="sxs-lookup"><span data-stu-id="d925a-131">DevTools launched in IE mode</span></span>  
:::image-end:::  

<span data-ttu-id="d925a-132">Internet explorer 11 ベースの web サイト \ (またはアプリ \) を Internet Explorer 11 と IE モードでテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d925a-132">To test your Internet Explorer 11-based website \(or app\) in Internet Explorer 11 and IE mode, perform the following steps.</span></span>  

1.  <span data-ttu-id="d925a-133">Internet Explorer 11 を開きます。</span><span class="sxs-lookup"><span data-stu-id="d925a-133">Open Internet Explorer 11.</span></span>  
    *   <span data-ttu-id="d925a-134">Windows 10 では、Internet Explorer 11 のショートカットを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d925a-134">On Windows 10, locate the shortcut for Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="d925a-135">**[スタート] メニュー**  > **Windows アクセサリ**  > **Internet Explorer 11**。</span><span class="sxs-lookup"><span data-stu-id="d925a-135">**Start Menu** > **Windows Accessories** > **Internet Explorer 11**.</span></span>  
    *   <span data-ttu-id="d925a-136">Windows 7 の場合は、Internet Explorer 11 を探します。</span><span class="sxs-lookup"><span data-stu-id="d925a-136">On Windows 7, locate Internet Explorer 11.</span></span>
        1.  <span data-ttu-id="d925a-137">**[スタート] メニュー**  > **Internet Explorer 11**。</span><span class="sxs-lookup"><span data-stu-id="d925a-137">**Start Menu** > **Internet Explorer 11**.</span></span>  
1.  <span data-ttu-id="d925a-138">Internet Explorer 11 で、同じ web ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d925a-138">In Internet Explorer 11, open the same webpage.</span></span>  
1.  <span data-ttu-id="d925a-139">Internet Explorer DevTools を起動します。</span><span class="sxs-lookup"><span data-stu-id="d925a-139">Launch the Internet Explorer DevTools.</span></span>  
    *   <span data-ttu-id="d925a-140">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="d925a-140">Select `F12`.</span></span>  
    *   <span data-ttu-id="d925a-141">任意の場所にマウスポインターを置いてコンテキストメニューを開き (\ を右クリックし)、[ **要素の検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d925a-141">Hover anywhere, open a contextual menu \(right-click\), and choose **Inspect element**.</span></span>  <span data-ttu-id="d925a-142">これらのツールの使用方法の詳細については、「 [F12 開発者ツール][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d925a-142">For more information about how to use those tools, navigate to [Using the F12 developer tools][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326].</span></span>  

## <span data-ttu-id="d925a-143">リモートデバッグと IE モード</span><span class="sxs-lookup"><span data-stu-id="d925a-143">Remote debugging and IE mode</span></span>  

<span data-ttu-id="d925a-144">コマンドラインインターフェイスからリモートデバッグを有効にして、Microsoft Edge \ (Chromium \) を起動します。</span><span class="sxs-lookup"><span data-stu-id="d925a-144">Launch Microsoft Edge \(Chromium\) with remote debugging turned on from the command-line interface.</span></span>  <span data-ttu-id="d925a-145">通常、visual Studio、Visual Studio コード、および他の開発ツールは、Microsoft Edge を起動するためのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d925a-145">Visual Studio, Visual Studio Code, and other development tools typically run a command to launch Microsoft Edge.</span></span>  <span data-ttu-id="d925a-146">次のコマンドは、リモートデバッグポートがに設定された Microsoft Edge を起動し `9222` ます。</span><span class="sxs-lookup"><span data-stu-id="d925a-146">The following command launches Microsoft Edge with the remote debugging port set to `9222`.</span></span>  

```shell
start msedge --remote-debugging-port=9222
```  

<span data-ttu-id="d925a-147">コマンドライン引数を使用して Microsoft Edge \ (Chromium \) を起動した後、IE モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d925a-147">After you launch Microsoft Edge \(Chromium\) using a command-line argument, IE mode is unavailable.</span></span>  <span data-ttu-id="d925a-148">ただし、他の方法で表示される IE モードの web サイトに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="d925a-148">You may still navigate to websites \(or apps\) that would otherwise display in IE mode.</span></span> <span data-ttu-id="d925a-149">Web サイト \ (またはアプリ \) コンテンツは、Internet Explorer 11 ではなく Chromium を使用してレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d925a-149">The website \(or app\) content renders using Chromium, not Internet Explorer 11.</span></span>  <span data-ttu-id="d925a-150">ActiveX コントロールなど、IE11 に依存しているページの一部が正しく表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d925a-150">Expect the parts of the pages that rely on IE11, such as ActiveX controls, to not render correctly.</span></span>  <span data-ttu-id="d925a-151">IE モードのバッジはアドレスバーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d925a-151">The IE mode badge does not appear in the address bar.</span></span>  

<span data-ttu-id="d925a-152">IE モードは、Microsoft Edge \ (Chromium \) を完全に閉じて再起動するまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="d925a-152">IE mode remains unavailable until you completely close and restart Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="d925a-153">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d925a-153">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "F12 開発者ツールを使用する |Microsoft ドキュメント"  