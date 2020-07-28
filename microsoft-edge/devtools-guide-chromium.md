---
description: Microsoft Edge (Chromium) 開発者ツールについて理解する
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b565f441ea6e6b3f2ae01ab251d7b9cae1aa815b
ms.sourcegitcommit: ad5eb43172280974b8c063867c2097f7c5c0e77d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "10898222"
---
# <span data-ttu-id="915a3-104">Microsoft Edge (Chromium) 開発者ツール</span><span class="sxs-lookup"><span data-stu-id="915a3-104">Microsoft Edge (Chromium) Developer Tools</span></span>  

<span data-ttu-id="915a3-105">Microsoft Edge では、Chromium open source プロジェクトを採用して、より良い web 互換性と、さまざまな基盤 web プラットフォームの断片化の少ない機能を作成しました。</span><span class="sxs-lookup"><span data-stu-id="915a3-105">Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.</span></span>  <span data-ttu-id="915a3-106">この変更により、Microsoft Edge で web サイトを作成してテストして、それぞれが Chromium ベースのブラウザーで表示されていても期待どおりに動作するようになります (Google Chrome、Vivaldi、Opera、Brave など)。</span><span class="sxs-lookup"><span data-stu-id="915a3-106">This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).</span></span>  

<span data-ttu-id="915a3-107">Web はさまざまな種類のデバイスにわたって使用されていますが、web サイトのテストに関わる複雑さとオーバーヘッドが増大しています。</span><span class="sxs-lookup"><span data-stu-id="915a3-107">As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded.</span></span> <span data-ttu-id="915a3-108">Web 開発者 (特に小規模企業向けのもの) では、さまざまなシステムをテストする必要があるため、サイトがすべてのデバイスの種類とすべてのブラウザーで適切に動作することを確認することは不可能です。</span><span class="sxs-lookup"><span data-stu-id="915a3-108">Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.</span></span>  <span data-ttu-id="915a3-109">Microsoft edge が Chromium をベースとしているため、microsoft edge チームは、Microsoft Edge web platform を他の Chromium ベースのブラウザーと連携させることで、優れた開発者ツールエクスペリエンスを、ブラウザー内と、毎日 (Visual Studio コードなど) で使用している他の開発者ツールで提供しています。</span><span class="sxs-lookup"><span data-stu-id="915a3-109">Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).</span></span>  

<span data-ttu-id="915a3-110">Microsoft Edge をチェックしていて、Chromium ベースのブラウザーで主に開発している場合は、自宅で適切なことを考えてください。</span><span class="sxs-lookup"><span data-stu-id="915a3-110">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span>  <span data-ttu-id="915a3-111">Microsoft Edge \ (Chromium \) 開発者ツールは、既に知っていて使用している開発者ツールと同じ方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="915a3-111">The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.</span></span>  <span data-ttu-id="915a3-112">詳細については、「 [Microsoft Edge (Chromium) DevTools の新機能][DevtoolsGuideChromiumWhatsNewIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="915a3-112">For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   <span data-ttu-id="915a3-114">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="915a3-114">Microsoft Edge (Chromium) DevTools</span></span>
:::image-end:::

<span data-ttu-id="915a3-115">Microsoft edge の次のバージョンを確認していて、以前に Microsoft edge \ (EdgeHTML \) で開発したことがある場合は、Microsoft Edge で web サイトを簡単かつ迅速に構築およびテストするための新しいツールが追加されました。</span><span class="sxs-lookup"><span data-stu-id="915a3-115">If you are checking out the next version of Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!</span></span>  

## <span data-ttu-id="915a3-116">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="915a3-116">Open the DevTools</span></span>  

<span data-ttu-id="915a3-117">以前に DevTools を使ったことがない場合は、microsoft edge 開発者ツールは Microsoft Edge ブラウザーに直接組み込まれている一連のツールです。</span><span class="sxs-lookup"><span data-stu-id="915a3-117">If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="915a3-118">これらの DevTools を使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="915a3-118">With these DevTools, you are able to do the following.</span></span>  
*   <span data-ttu-id="915a3-119">HTML web サイトを検査して変更を加える</span><span class="sxs-lookup"><span data-stu-id="915a3-119">Inspect and make changes to your HTML website</span></span>  
*   <span data-ttu-id="915a3-120">CSS を編集し、web サイトの表示をプレビューで確認する</span><span class="sxs-lookup"><span data-stu-id="915a3-120">Edit CSS and instantly see preview how your website renders</span></span>  
*   <span data-ttu-id="915a3-121">`console.log()`フロントエンド JavaScript コードのすべてのステートメントを表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-121">See all the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="915a3-122">ブレークポイントを設定し、行ごとにステップスルーすることによってスクリプトをデバッグする</span><span class="sxs-lookup"><span data-stu-id="915a3-122">Debug your script by setting breakpoints and stepping through it line by line</span></span>  

<span data-ttu-id="915a3-123">ブラウザー内で直接。</span><span class="sxs-lookup"><span data-stu-id="915a3-123">all directly within the browser.</span></span>  <span data-ttu-id="915a3-124">ここでは、Microsoft Edge で web サイトを作成してテストするために、DevTools が提供するいくつかの機能の例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="915a3-124">These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.</span></span>  

<span data-ttu-id="915a3-125">DevTools を開くには</span><span class="sxs-lookup"><span data-stu-id="915a3-125">To open the DevTools</span></span>  
*   <span data-ttu-id="915a3-126">キーを押し</span><span class="sxs-lookup"><span data-stu-id="915a3-126">press</span></span> `F12` 
*   <span data-ttu-id="915a3-127">`Ctrl` + `Shift` + `I` Windows \ ( `Command` + `Option` + `I` macOS) を押します。</span><span class="sxs-lookup"><span data-stu-id="915a3-127">press `Ctrl`+`Shift`+`I` on Windows \(`Command`+`Option`+`I` on macOS\)</span></span>  

<span data-ttu-id="915a3-128">サイトの要素の HTML または CSS を表示する場合は、要素を右クリックして [**検査**] を選択し、[要素] パネルに移動します。</span><span class="sxs-lookup"><span data-stu-id="915a3-128">If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.</span></span>  <span data-ttu-id="915a3-129">また、 `Ctrl` + `Shift` + `C` Windows \ ( `Command` + `Option` + `C` macOS で) を押して、[**要素の検査] モード**で、サイトの要素を選択し、[**要素**] パネルで HTML と CSS を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="915a3-129">You may also press `Ctrl`+`Shift`+`C` on Windows \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.</span></span>  

<span data-ttu-id="915a3-130">フロントエンド JavaScript コードからログを表示したい場合、またはスクリプトをすばやく実行する場合は、 `Ctrl` + `Shift` + `J` Windows \ (macOS) を押して、 `Command` + `Option` + `J` devtools でコンソールパネルを起動します。</span><span class="sxs-lookup"><span data-stu-id="915a3-130">If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows \(`Command`+`Option`+`J` on macOS\) to launch the Console panel in the DevTools.</span></span>  

## <span data-ttu-id="915a3-131">コア ツール</span><span class="sxs-lookup"><span data-stu-id="915a3-131">Core tools</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コアツール":::
   <span data-ttu-id="915a3-133">Microsoft Edge (Chromium) DevTools コアツール</span><span class="sxs-lookup"><span data-stu-id="915a3-133">Microsoft Edge (Chromium) DevTools core tools</span></span>
:::image-end:::

<span data-ttu-id="915a3-134">Microsoft Edge \ (Chromium \) DevTools には、次のパネルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="915a3-134">The Microsoft Edge \(Chromium\) DevTools include the following panels.</span></span>  
*   <span data-ttu-id="915a3-135">**要素** は、パネルHTML および CSS の編集、アクセシビリティのプロパティの検査、イベント リスナーの表示、DOM 変異のブレークポイントの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="915a3-135">An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="915a3-136">**コンソール** は、ログ メッセージを表示およびフィルタリングし、JavaScript オブジェクトと DOM ノードを検査し、選択したウィンドウやフレームのコンテキストでの JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="915a3-136">A **Console** to view and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="915a3-137">コードのオープンとライブ編集、ブレークポイントの設定、コードのステップ実行、web サイトの1行の JavaScript の状態の表示を行うための**ソース**パネル</span><span class="sxs-lookup"><span data-stu-id="915a3-137">A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time</span></span>  
*   <span data-ttu-id="915a3-138">**ネットワーク** パネルは、ネットワークとブラウザーのキャッシュからの要求や応答を監視および検査します。</span><span class="sxs-lookup"><span data-stu-id="915a3-138">A **Network** panel to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="915a3-139">**パフォーマンス** パネルは、サイトに必要な時間とシステム リソースをプロファイルします。</span><span class="sxs-lookup"><span data-stu-id="915a3-139">A **Performance** panel to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="915a3-140">**メモリ** パネルは、メモリ リソースの使用状況を測定し、コード ランタイムの異なる状態でヒープ スナップショットを比較します。</span><span class="sxs-lookup"><span data-stu-id="915a3-140">A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="915a3-141">Web アプリマニフェスト、サービスワーカー、service worker キャッシュを検査、変更、デバッグする**アプリケーション**パネル。</span><span class="sxs-lookup"><span data-stu-id="915a3-141">An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="915a3-142">また、**アプリケーション**パネルからストレージ、データベース、キャッシュを調査し、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="915a3-142">You may also inspect and manage storage, databases, and caches from the **Application** panel.</span></span>  
*   <span data-ttu-id="915a3-143">セキュリティの問題をデバッグし、web サイトに HTTPS が適切に実装されていることを確認するための**セキュリティ**パネル。</span><span class="sxs-lookup"><span data-stu-id="915a3-143">A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.</span></span>  <span data-ttu-id="915a3-144">HTTPS は、サイトとユーザーの両方にとって重要なセキュリティとデータの整合性を提供します。これは、サイトでの個人情報の提供を目的としています。</span><span class="sxs-lookup"><span data-stu-id="915a3-144">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="915a3-145">監査\**パネル \** ( **Lighthouse**\ 名前を変更しました \) で web サイトの監査が実行されます。</span><span class="sxs-lookup"><span data-stu-id="915a3-145">An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.</span></span>  <span data-ttu-id="915a3-146">監査の結果は、次のような方法でサイトの品質を向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="915a3-146">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="915a3-147">Web サイトのアクセシビリティ、セキュリティ、パフォーマンスなどに関連する一般的なエラーを検出します。</span><span class="sxs-lookup"><span data-stu-id="915a3-147">Catch common errors related to making your website accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="915a3-148">各エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="915a3-148">Fix each error.</span></span>  
    *   <span data-ttu-id="915a3-149">PWA を構築します。</span><span class="sxs-lookup"><span data-stu-id="915a3-149">Build a PWA.</span></span>  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

<span data-ttu-id="915a3-150">[フィードバックと機能のリクエストを](#getting-in-touch-with-the-microsoft-edge-devtools-team)送信してください。</span><span class="sxs-lookup"><span data-stu-id="915a3-150">Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team)!</span></span>  

## <span data-ttu-id="915a3-151">拡張機能</span><span class="sxs-lookup"><span data-stu-id="915a3-151">Extensions</span></span>  

<span data-ttu-id="915a3-152">Web サイトやアプリの構築時に発生する問題の診断とデバッグを支援するために、DevTools の拡張機能を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="915a3-152">You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.</span></span>  <span data-ttu-id="915a3-153">Microsoft edge の[アドオン][MicrosoftEdgeAddonsExtensions]ページから microsoft edge の拡張機能を入手できます。</span><span class="sxs-lookup"><span data-stu-id="915a3-153">You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.</span></span>  <span data-ttu-id="915a3-154">[Microsoft Edge のアドオン][MicrosoftEdgeAddonsExtensions]ページから、**開発者ツール**のカテゴリからの devtools 拡張機能を参照したり、特定の拡張機能を検索したりできます。</span><span class="sxs-lookup"><span data-stu-id="915a3-154">From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="915a3-155">[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="915a3-155">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア":::
   <span data-ttu-id="915a3-157">Microsoft Edge の Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="915a3-157">Chrome Web Store in Microsoft Edge</span></span>
:::image-end:::

<span data-ttu-id="915a3-158">上部で、[**他のストアの拡張機能を許可する**] を選択し、表示されるダイアログボックスで [**許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="915a3-158">At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="915a3-159">Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="915a3-159">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="915a3-160">[ **Chrome に追加**] を選択して、Microsoft Edge に devtools 拡張機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="915a3-160">Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアから Microsoft Edge に拡張機能を追加する":::
   <span data-ttu-id="915a3-162">Chrome Web ストアから Microsoft Edge に拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="915a3-162">Adding extension from Chrome Web Store to Microsoft Edge</span></span>
:::image-end:::

## <span data-ttu-id="915a3-163">ショートカット</span><span class="sxs-lookup"><span data-stu-id="915a3-163">Shortcuts</span></span>  

<span data-ttu-id="915a3-164">これらのショートカットは、メインの [開発ツール] ウィンドウの制御、すべてのツールの操作、またはその両方を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="915a3-164">These shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="915a3-165">操作</span><span class="sxs-lookup"><span data-stu-id="915a3-165">Action</span></span> | <span data-ttu-id="915a3-166">Windows</span><span class="sxs-lookup"><span data-stu-id="915a3-166">Windows</span></span> | <span data-ttu-id="915a3-167">macOS</span><span class="sxs-lookup"><span data-stu-id="915a3-167">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="915a3-168">DevTools の表示/非表示 \ (最後に表示されたパネルに表示される \)</span><span class="sxs-lookup"><span data-stu-id="915a3-168">Show/Hide DevTools \(opens to last viewed panel\)</span></span> | `F12` <span data-ttu-id="915a3-169">/`Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="915a3-169">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="915a3-170">コンソールパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-170">Show the Console panel</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="915a3-171">サイト上の要素を選択して、[**要素**] パネルで HTML と CSS を表示できる [**要素の検査] モード**で devtools を表示します。</span><span class="sxs-lookup"><span data-stu-id="915a3-171">Show the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="915a3-172">設定を表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-172">Show Settings</span></span> | `?` <span data-ttu-id="915a3-173">/`Fn`+</span><span class="sxs-lookup"><span data-stu-id="915a3-173">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="915a3-174">/`Fn`+</span><span class="sxs-lookup"><span data-stu-id="915a3-174">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="915a3-175">次のパネルを表示</span><span class="sxs-lookup"><span data-stu-id="915a3-175">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="915a3-176">前のパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-176">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="915a3-177">使用されている最後の位置に DevTools をドッキングします。</span><span class="sxs-lookup"><span data-stu-id="915a3-177">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="915a3-178">DevTools がセッション全体の既定の位置に留まる場合は、このショートカットでは、DevTools を別のウィンドウにドッキング解除します。</span><span class="sxs-lookup"><span data-stu-id="915a3-178">If the DevTools remain in the default position for the entire session, this shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="915a3-179">**デバイスモード**の切り替え</span><span class="sxs-lookup"><span data-stu-id="915a3-179">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="915a3-180">[**要素の検査] モード**を切り替えて、サイトの要素を選択し、[**要素**] パネルで HTML と CSS を表示します。</span><span class="sxs-lookup"><span data-stu-id="915a3-180">Toggle **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="915a3-181">コマンドメニューを表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-181">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="915a3-182">ドロワーの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="915a3-182">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="915a3-183">非.</span><span class="sxs-lookup"><span data-stu-id="915a3-183">Refresh.</span></span>  <span data-ttu-id="915a3-184">キャッシュを使用してページが更新されます。</span><span class="sxs-lookup"><span data-stu-id="915a3-184">This refreshes the page using the cache.</span></span>  | `F5` <span data-ttu-id="915a3-185">/`Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="915a3-185">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="915a3-186">ハードリフレッシュ。</span><span class="sxs-lookup"><span data-stu-id="915a3-186">Hard Refresh.</span></span>  <span data-ttu-id="915a3-187">これにより、Microsoft Edge はリソースをもう一度ダウンロードして、再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="915a3-187">This forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="915a3-188">使用されているリソースがキャッシュバージョンから取得されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="915a3-188">It is possible that the used resources may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="915a3-189">+`F5`/`Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="915a3-189">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="915a3-190">現在のパネル内でテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="915a3-190">Search for text within the current panel.</span></span>  <span data-ttu-id="915a3-191">監査、アプリケーション、セキュリティの各パネルではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="915a3-191">Not supported in the Audits, Application, and Security panels</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="915a3-192">引き出しに検索パネルを表示します。これにより、読み込まれたすべてのリソースのテキストを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="915a3-192">Show the Search panel in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="915a3-193">[ソース] パネルでファイルを開く</span><span class="sxs-lookup"><span data-stu-id="915a3-193">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="915a3-194">+`O`/`Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="915a3-194">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="915a3-195">+`O`/`Command`+</span><span class="sxs-lookup"><span data-stu-id="915a3-195">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="915a3-196">拡大</span><span class="sxs-lookup"><span data-stu-id="915a3-196">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="915a3-197">縮小</span><span class="sxs-lookup"><span data-stu-id="915a3-197">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="915a3-198">既定のズームレベルに戻す</span><span class="sxs-lookup"><span data-stu-id="915a3-198">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="915a3-199">スニペットの実行</span><span class="sxs-lookup"><span data-stu-id="915a3-199">Run snippet</span></span> | `Ctrl`<span data-ttu-id="915a3-200">+`O`または、「」と入力し、その `Ctrl` + `P` `!` 後にスクリプトの名前を入力して、</span><span class="sxs-lookup"><span data-stu-id="915a3-200">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` | <span data-ttu-id="915a3-201">`Command` + `O` または、「」と入力して、 `Command` + `P` `!` 続けてスクリプトの名前を入力して、</span><span class="sxs-lookup"><span data-stu-id="915a3-201">Press `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then press</span></span> `Enter` |  
| <span data-ttu-id="915a3-202">編集不可の HTML ソースコードを新しいタブに表示する</span><span class="sxs-lookup"><span data-stu-id="915a3-202">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="915a3-203">該当せず</span><span class="sxs-lookup"><span data-stu-id="915a3-203">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="915a3-204">デバッグ中にブレークポイントで一時停止している場合は、[**更新**] ショートカットで最初にランタイムが再開されます。</span><span class="sxs-lookup"><span data-stu-id="915a3-204">If you are debugging and paused at a breakpoint, the **Refresh**shortcut resumes the runtime first.</span></span>  

## <span data-ttu-id="915a3-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="915a3-205">See also</span></span>  

*   [<span data-ttu-id="915a3-206">初心者向けの DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="915a3-206">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="915a3-207">Microsoft Edge (Chromium) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="915a3-207">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  

## <span data-ttu-id="915a3-208">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="915a3-208">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="915a3-209">フィードバックを送信してください。 Microsoft Edge チームは、Microsoft Edge DevTools の改善に進みます。</span><span class="sxs-lookup"><span data-stu-id="915a3-209">Please send your feedback, so the Microsoft Edge team continues improving the Microsoft Edge DevTools for you!</span></span>  <span data-ttu-id="915a3-210">Devtools の**フィードバック**アイコンを選択するか、または `Alt` + `Shift` + `I` (macOS の場合は) Windows を押して、 `Option` + `Shift` + `I` devtools のフィードバックまたは機能のリクエストを入力します。</span><span class="sxs-lookup"><span data-stu-id="915a3-210">Simply select the **Feedback** icon in the DevTools or press `Alt`+`Shift`+`I` on Windows \(`Option`+`Shift`+`I` on macOS\) and enter any feedback or feature requests you have for the DevTools.</span></span>  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge についてフィードバックを送信する":::
   <span data-ttu-id="915a3-212">Microsoft Edge についてフィードバックを送信する</span><span class="sxs-lookup"><span data-stu-id="915a3-212">Give feedback on Microsoft Edge</span></span>
:::image-end:::

<span data-ttu-id="915a3-213">[DevTools の最新機能][DevtoolsGuideChromiumWhatsNewIndex]をプレビューする場合は、夜間にビルドされた[Microsoft Edge カナリア][MicrosoftedgeinsiderDownload]をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="915a3-213">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- image links -->  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初心者向けの DevTools: HTML と DOM の使用を開始する |Microsoft ドキュメント"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools "Microsoft Edge (Chromium) DevTools の新機能 |Microsoft ドキュメント"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools Protocol |Microsoft ドキュメント"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張子 |Chrome Web ストア"  
