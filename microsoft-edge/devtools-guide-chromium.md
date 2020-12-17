---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8f773db3d175f8b5128e1558809334c8f2de4bd7
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "11204006"
---
# <span data-ttu-id="5401e-104">Microsoft Edge (Chromium) 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="5401e-104">Microsoft Edge (Chromium) Developer Tools</span></span>  

<span data-ttu-id="5401e-105">Microsoft Edge では、Chromium オープン ソース プロジェクトを採用して、Web の互換性を向上し、異なる基盤となる Web プラットフォームの断片化を減らしています。</span><span class="sxs-lookup"><span data-stu-id="5401e-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span></span>  <span data-ttu-id="5401e-106">この変更により、Microsoft Edge で Web サイトを簡単に構築してテストし、それぞれが別の Chromium ベースのブラウザー \(Google Chrome、Vivaldi、Opera、または Brave\ など) で表示されている場合でも、それぞれにおいて期待通りに機能することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5401e-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span></span>  

<span data-ttu-id="5401e-107">デバイスの種類が拡大するにつれて、Web の利用も拡大し、Web サイトのテストに伴う複雑性とオーバーヘッドが大きく増加しました。</span><span class="sxs-lookup"><span data-stu-id="5401e-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span></span> <span data-ttu-id="5401e-108">Web 開発者 \(特に小規模企業の開発者\) は、非常に多くの異なるシステムに対してテストを行う必要があるため、サイトがすべてのデバイスの種類とすべてのブラウザーで適切に動作することを確認するのは、ほぼ不可能に近いことです。</span><span class="sxs-lookup"><span data-stu-id="5401e-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span></span>  <span data-ttu-id="5401e-109">Microsoft Edge が Chromium に基づいているので、Microsoft Edge チームは、Microsoft Edge Web プラットフォームを他の Chromium ベースのブラウザーと一致することでマトリックスを簡略化し、ブラウザー内と、毎日使用する他の開発者ツール (Visual Studio Code\ など) の両方で、クラス最高の開発者ツール エクスペリエンスを実現しました。</span><span class="sxs-lookup"><span data-stu-id="5401e-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span></span>  

<span data-ttu-id="5401e-110">Microsoft Edge をチェック アウトしており、主に Chromium ベースのブラウザーで開発を行っている場合は、自宅にいるような安心感を感じることでしょう。</span><span class="sxs-lookup"><span data-stu-id="5401e-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span>  <span data-ttu-id="5401e-111">Microsoft Edge \(Chromium\) 開発者ツール は、既に使用している開発者ツールと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="5401e-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span></span>  <span data-ttu-id="5401e-112">詳細については、[Microsoft Edge (Chromium) DevTools の新機能][DevtoolsGuideChromiumWhatsNewIndex]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5401e-112">For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./devtools-guide-chromium/media/devtools.png":::
   <span data-ttu-id="5401e-114">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="5401e-114">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="5401e-115">新しい Microsoft Edge をチェック アウトしていて、以前に Microsoft Edge \(EdgeHTML\) で開発している場合は、Microsoft Edge で Web サイトのビルドとテストをより簡単かつ迅速に行える新しいツールが利用できます。</span><span class="sxs-lookup"><span data-stu-id="5401e-115">If you are checking out the new Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!</span></span>  

## <span data-ttu-id="5401e-116">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="5401e-116">Open the DevTools</span></span>  

<span data-ttu-id="5401e-117">DevTools を使用したことがない方のために説明しますと、Microsoft Edge 開発者ツールは、Microsoft Edge ブラウザーに直接組み込まれているツール セットです。</span><span class="sxs-lookup"><span data-stu-id="5401e-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="5401e-118">これらの DevTools を使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5401e-118">With these DevTools, you are able to do the following.</span></span>  

*   <span data-ttu-id="5401e-119">HTML Web サイトを検査して変更する</span><span class="sxs-lookup"><span data-stu-id="5401e-119">Inspect and make changes to your HTML website</span></span>  
*   <span data-ttu-id="5401e-120">CSS を編集し、Web サイトのレンダリング方法のプレビューを即座に確認する</span><span class="sxs-lookup"><span data-stu-id="5401e-120">Edit CSS and instantly see preview how your website renders</span></span>  
*   <span data-ttu-id="5401e-121">フロントエンド JavaScript コードから、すべての `console.log()` ステートメントを参照する</span><span class="sxs-lookup"><span data-stu-id="5401e-121">See all the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="5401e-122">ブレークポイントを設定し、1 行ずつステップ実行してスクリプトをデバッグする</span><span class="sxs-lookup"><span data-stu-id="5401e-122">Debug your script by setting breakpoints and stepping through it line by line</span></span>  

<span data-ttu-id="5401e-123">すべてはブラウザー内で直接行います。</span><span class="sxs-lookup"><span data-stu-id="5401e-123">all directly within the browser.</span></span>  <span data-ttu-id="5401e-124">これらは、Microsoft Edge で Web サイトを簡単かつ迅速に構築およびテストするために、DevTools が提供する機能の一部の例です。</span><span class="sxs-lookup"><span data-stu-id="5401e-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span></span>  

<span data-ttu-id="5401e-125">DevTools を開く方法</span><span class="sxs-lookup"><span data-stu-id="5401e-125">To open the DevTools</span></span>  

*   <span data-ttu-id="5401e-126">押す</span><span class="sxs-lookup"><span data-stu-id="5401e-126">press</span></span> `F12` 
*   <span data-ttu-id="5401e-127">Windows/Linux の場合、`Ctrl` + `Shift` + `I` を押す \(macOS の場合、`Command` + `Option` + `I` を押す\)</span><span class="sxs-lookup"><span data-stu-id="5401e-127">press `Ctrl`+`Shift`+`I` on Windows/Linux \(`Command`+`Option`+`I` on macOS\)</span></span>  

<span data-ttu-id="5401e-128">サイト上の要素の HTML または CSS を表示する場合は、要素を右クリックし、[**検査**] を選択して [要素] パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="5401e-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span></span>  <span data-ttu-id="5401e-129">Windows/Linux の場合、`Ctrl` + `Shift` + `C` を押す \(macOS の場合、`Command` + `Option` + `C` を押す\) と、を押して**要素の検査モード**で DevTools を開くと、サイト上の要素を選択し、**[要素]** パネルに HTML と CSS を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5401e-129">You may also press `Ctrl`+`Shift`+`C` on Windows/Linux \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span></span>  

<span data-ttu-id="5401e-130">フロントエンドの JavaScript コードからログを表示する場合や、スクリプトをすばやく実行する場合は、Windows/Linux の場合`Ctrl` + `Shift` + `J`、macOS の場合 `Command` + `Option` + `J` を押して、DevTools のコンソール パネルを起動します。</span><span class="sxs-lookup"><span data-stu-id="5401e-130">If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows/Linux or `Command`+`Option`+`J` on macOS to launch the Console panel in the DevTools.</span></span>  

## <span data-ttu-id="5401e-131">コア ツール</span><span class="sxs-lookup"><span data-stu-id="5401e-131">Core tools</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コア ツール" lightbox="./devtools-guide-chromium/media/devtools-core-tools.png":::
   <span data-ttu-id="5401e-133">Microsoft Edge (Chromium) DevTools コア ツール</span><span class="sxs-lookup"><span data-stu-id="5401e-133">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="5401e-134">Microsoft Edge \(Chromium\) DevTools には、次のパネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5401e-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span></span>  

*   <span data-ttu-id="5401e-135">**要素** は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="5401e-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="5401e-136">**コンソール** は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="5401e-136">A **Console** to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="5401e-137">コードを開いてライブ編集し、ブレークポイントを設定し、コードをステップ実行して、一度に 1 行の JavaScript だけでWeb サイトの状態を確認する**ソース** パネル</span><span class="sxs-lookup"><span data-stu-id="5401e-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span></span>  
*   <span data-ttu-id="5401e-138">**ネットワーク** パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。</span><span class="sxs-lookup"><span data-stu-id="5401e-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="5401e-139">**パフォーマンス** パネルは、サイトに必要な時間とシステム リソースをプロファイルします。</span><span class="sxs-lookup"><span data-stu-id="5401e-139">A **Performance** panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="5401e-140">**メモリ** パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。</span><span class="sxs-lookup"><span data-stu-id="5401e-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="5401e-141">Web アプリ マニフェスト、サービス ワーカー、およびサービス ワーカーのキャッシュを検査、変更、デバッグする **[アプリケーション]** パネル。</span><span class="sxs-lookup"><span data-stu-id="5401e-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="5401e-142">**[アプリケーション]** パネルからストレージ、データベース、およびキャッシュを検査および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5401e-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span></span>  
*   <span data-ttu-id="5401e-143">セキュリティの問題をデバッグし、Web サイトに HTTPS を適切に実装した **[セキュリティ]** パネル。</span><span class="sxs-lookup"><span data-stu-id="5401e-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span></span>  <span data-ttu-id="5401e-144">HTTPS は、サイトとサイト上に個人情報を入力するユーザーの両方に対して、重要なセキュリティとデータの整合性を提供します。</span><span class="sxs-lookup"><span data-stu-id="5401e-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="5401e-145">Web サイトの監査を実行するために、**監査**パネル \(現在は **Lighthouse**\ という名前に変更されました)。</span><span class="sxs-lookup"><span data-stu-id="5401e-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span></span>  <span data-ttu-id="5401e-146">監査の結果は、次の方法でサイトの品質を向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5401e-146">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="5401e-147">Web サイトのアクセス性、セキュリティ、パフォーマンスの確保に関連する一般的なエラーを発見します。</span><span class="sxs-lookup"><span data-stu-id="5401e-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="5401e-148">各エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="5401e-148">Fix each error.</span></span>  
    *   <span data-ttu-id="5401e-149">PWA を構築します。</span><span class="sxs-lookup"><span data-stu-id="5401e-149">Build a PWA.</span></span>  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

<span data-ttu-id="5401e-150">[フィードバックと機能のリクエスト](#getting-in-touch-with-the-microsoft-edge-devtools-team) を送信してください。</span><span class="sxs-lookup"><span data-stu-id="5401e-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <span data-ttu-id="5401e-151">拡張機能</span><span class="sxs-lookup"><span data-stu-id="5401e-151">Extensions</span></span>  

<span data-ttu-id="5401e-152">DevTools の拡張機能を使用して、Web サイトやアプリの構築時の問題を診断およびデバッグした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5401e-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span></span>  <span data-ttu-id="5401e-153">[Microsoft Edge アドオン][MicrosoftEdgeAddonsExtensions] ページから Microsoft Edge の拡張機能を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5401e-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span></span>  <span data-ttu-id="5401e-154">[Microsoft Edge アドオン ページ][MicrosoftEdgeAddonsExtensions]から、**開発者ツール** カテゴリの DevTools 拡張機能を参照するか、特定の拡張機能を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="5401e-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="5401e-155">[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5401e-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア" lightbox="./devtools-guide-chromium/media/allow-extensions-from-stores.png":::
   <span data-ttu-id="5401e-157">Microsoft Edge の Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="5401e-157">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="5401e-158">上部にある\*\* [他のストアからの拡張機能を許可する]\*\* を選択し、表示されるダイアログで **[許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5401e-158">At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="5401e-159">Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5401e-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="5401e-160">\*\*[Chrome に追加] \*\*を選択して、DevTools 拡張機能を Microsoft Edge に追加します。</span><span class="sxs-lookup"><span data-stu-id="5401e-160">Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアからの Microsoft Edge への拡張機能の追加" lightbox="./devtools-guide-chromium/media/install-extension-from-chrome-store.png":::
   <span data-ttu-id="5401e-162">Chrome Web ストアからの Microsoft Edge への拡張機能の追加</span><span class="sxs-lookup"><span data-stu-id="5401e-162">Adding extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <span data-ttu-id="5401e-163">ショートカット</span><span class="sxs-lookup"><span data-stu-id="5401e-163">Shortcuts</span></span>  

<span data-ttu-id="5401e-164">これらのショートカットは、DevTools のメイン ウィンドウを制御するか、すべてのツールで機能するか、または両方を実行します。</span><span class="sxs-lookup"><span data-stu-id="5401e-164">These shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="5401e-165">Action</span><span class="sxs-lookup"><span data-stu-id="5401e-165">Action</span></span> | <span data-ttu-id="5401e-166">Windows/Linux</span><span class="sxs-lookup"><span data-stu-id="5401e-166">Windows/Linux</span></span> | <span data-ttu-id="5401e-167">macOS</span><span class="sxs-lookup"><span data-stu-id="5401e-167">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="5401e-168">DevTools の表示/非表示 \(最後に表示されたパネルに表示される\)</span><span class="sxs-lookup"><span data-stu-id="5401e-168">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12` <span data-ttu-id="5401e-169">または `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="5401e-169">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="5401e-170">コンソール パネルを表示する</span><span class="sxs-lookup"><span data-stu-id="5401e-170">Show the Console panel</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="5401e-171">**要素の検査モード**でDevTools を表示します。これにより、サイトで要素を選択し、**[要素]** パネルに HTML と CSS を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5401e-171">Show the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="5401e-172">設定の表示</span><span class="sxs-lookup"><span data-stu-id="5401e-172">Show Settings</span></span> | `?` <span data-ttu-id="5401e-173">または `Fn`+</span><span class="sxs-lookup"><span data-stu-id="5401e-173">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="5401e-174">または `Fn`+</span><span class="sxs-lookup"><span data-stu-id="5401e-174">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="5401e-175">次のパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="5401e-175">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="5401e-176">前のパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="5401e-176">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="5401e-177">DevTools を最後に使用した位置にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="5401e-177">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="5401e-178">DevTools がセッション全体の既定の位置にとどまっている場合、このショートカットは DevTools を別のウィンドウにドッキングを解除します。</span><span class="sxs-lookup"><span data-stu-id="5401e-178">If the DevTools remain in the default position for the entire session, this shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="5401e-179">**デバイス モード**の切り替え</span><span class="sxs-lookup"><span data-stu-id="5401e-179">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="5401e-180">**[要素の検査モード] **に切り替えると、サイトで要素を選択し、**[要素]** パネルに HTML と CSS を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5401e-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="5401e-181">コマンド メニューを表示する</span><span class="sxs-lookup"><span data-stu-id="5401e-181">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="5401e-182">ドロワーの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="5401e-182">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="5401e-183">更新。</span><span class="sxs-lookup"><span data-stu-id="5401e-183">Refresh.</span></span>  <span data-ttu-id="5401e-184">これにより、キャッシュを使用してページが更新されます。</span><span class="sxs-lookup"><span data-stu-id="5401e-184">This refreshes the page using the cache.</span></span>  | `F5` <span data-ttu-id="5401e-185">または `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="5401e-185">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="5401e-186">ハードの更新。</span><span class="sxs-lookup"><span data-stu-id="5401e-186">Hard Refresh.</span></span>  <span data-ttu-id="5401e-187">これにより、Microsoft Edge はリソースを強制的に再度ダウンロードして、再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="5401e-187">This forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="5401e-188">使用されているリソースが、キャッシュされたバージョンから取得される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5401e-188">It is possible that the used resources may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="5401e-189">+`F5` または `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="5401e-189">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="5401e-190">現在のパネル内のテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="5401e-190">Search for text within the current panel.</span></span>  <span data-ttu-id="5401e-191">監査、アプリケーション、およびセキュリティ パネルではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="5401e-191">Not supported in the Audits, Application, and Security panels</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="5401e-192">ドロワーに検索パネルを表示すると、読み込まれたすべてのリソースでテキストを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5401e-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="5401e-193">ソース パネルでファイルを開く</span><span class="sxs-lookup"><span data-stu-id="5401e-193">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="5401e-194">+`O` または `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="5401e-194">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="5401e-195">+`O` または `Command`+</span><span class="sxs-lookup"><span data-stu-id="5401e-195">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="5401e-196">拡大する</span><span class="sxs-lookup"><span data-stu-id="5401e-196">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="5401e-197">縮小</span><span class="sxs-lookup"><span data-stu-id="5401e-197">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="5401e-198">既定のズーム レベルを復元する</span><span class="sxs-lookup"><span data-stu-id="5401e-198">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="5401e-199">スニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="5401e-199">Run snippet</span></span> | `Ctrl`<span data-ttu-id="5401e-200">+`O` または `Ctrl` + `P`、スクリプト名の後に`!` を入力し、その後押します</span><span class="sxs-lookup"><span data-stu-id="5401e-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` | <span data-ttu-id="5401e-201">`Command` + `O` または `Command` + `P` を押し、スクリプト名の後に `!` を入力し、その後押します</span><span class="sxs-lookup"><span data-stu-id="5401e-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` |  
| <span data-ttu-id="5401e-202">編集できない HTML ソース コードを新しいタブに表示する</span><span class="sxs-lookup"><span data-stu-id="5401e-202">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="5401e-203">該当せず</span><span class="sxs-lookup"><span data-stu-id="5401e-203">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="5401e-204">デバッグ中にブレークポイントで一時停止している場合は、最初に**更新**ショートカットがランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="5401e-204">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <span data-ttu-id="5401e-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="5401e-205">See also</span></span>  

*   [<span data-ttu-id="5401e-206">初級向け DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="5401e-206">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="5401e-207">Microsoft Edge (Chromium) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="5401e-207">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  

## <span data-ttu-id="5401e-208">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="5401e-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<span data-ttu-id="5401e-209">近々ある [DevTools][DevtoolsGuideChromiumWhatsNewIndex] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5401e-209">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (Chromium) DevTools の新機能 | Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools プロトコル | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
