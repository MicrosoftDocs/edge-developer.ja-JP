---
description: Microsoft Edge (Chromium) 開発者ツールについて
title: Microsoft Edge (Chromium) 開発者ツール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 29ded7376ab1788998acf059c6677916a52d5d15
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408277"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a><span data-ttu-id="35c82-104">Microsoft Edge (クロム) 開発者ツールの概要</span><span class="sxs-lookup"><span data-stu-id="35c82-104">Microsoft Edge (Chromium) Developer Tools overview</span></span>  

<span data-ttu-id="35c82-105">Microsoft Edge は、クロム オープンソース プロジェクトを採用しています。</span><span class="sxs-lookup"><span data-stu-id="35c82-105">Microsoft Edge has adopted the Chromium open-source project.</span></span>  <span data-ttu-id="35c82-106">新しい Microsoft Edge ブラウザーを使用すると、Web の互換性が向上し、さまざまな Web プラットフォームの断片化が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="35c82-106">The new Microsoft Edge browser creates better web compatibility and reduces the fragmentation of different web platforms.</span></span>  <span data-ttu-id="35c82-107">この変更により、Microsoft Edge で Web ページのビルドとテストが容易になります。</span><span class="sxs-lookup"><span data-stu-id="35c82-107">The change should make it easier for you to build and test your webpages in Microsoft Edge.</span></span>  <span data-ttu-id="35c82-108">新しい Microsoft Edge は、他のクロム ベースのブラウザーで開いた場合、Web ページが期待通り動作するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35c82-108">The new Microsoft Edge should help your webpages work as expected when opened in other Chromium-based browsers.</span></span>  <span data-ttu-id="35c82-109">クロムベースのブラウザーには、Google Chrome、Vivaldi、Opera、Brave、新しい Microsoft Edge が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35c82-109">Chromium-based browsers include Google Chrome, Vivaldi, Opera, Brave, and the new Microsoft Edge.</span></span>  

<span data-ttu-id="35c82-110">Web は、デバイスの種類が増え続け、さまざまな種類のデバイスで使い方が増え続け始めていました。</span><span class="sxs-lookup"><span data-stu-id="35c82-110">The web has grown in usage across an ever-widening array of device types.</span></span>  <span data-ttu-id="35c82-111">Web ページのテストに伴う複雑性とオーバーヘッドは急速に増加しています。</span><span class="sxs-lookup"><span data-stu-id="35c82-111">The complexity and overhead involved in testing webpages has rapidly grown.</span></span>  <span data-ttu-id="35c82-112">このような Web 開発者は、さまざまなシステムに対してテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-112">Web developers like you need to test against many different systems.</span></span>  <span data-ttu-id="35c82-113">すべてのデバイスの種類とブラウザーで Web ページが適切に機能するために、特に小規模な会社で働く場合は、ほとんど不可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-113">To ensure your webpages work well on all device types and browsers, you may find it nearly impossible, particularly if you work at a small company.</span></span>  <span data-ttu-id="35c82-114">新しい Microsoft Edge は、クロムに基づくものに変更しました。</span><span class="sxs-lookup"><span data-stu-id="35c82-114">The new Microsoft Edge is now based on Chromium.</span></span>  <span data-ttu-id="35c82-115">Microsoft Edge チームは、Microsoft Edge Web プラットフォームを他のクロム ベースのブラウザーに合わせて配置することで、マトリックスを簡略化しました。</span><span class="sxs-lookup"><span data-stu-id="35c82-115">The Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers.</span></span>  <span data-ttu-id="35c82-116">新しい Microsoft Edge は、クラス最高の開発エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="35c82-116">The new Microsoft Edge provides a best-in-class development experience.</span></span>  <span data-ttu-id="35c82-117">このエクスペリエンスは、ブラウザー内や、日常使用する他の開発者ツール (コードなど) とVisual Studioされます。</span><span class="sxs-lookup"><span data-stu-id="35c82-117">The experience is accomplished inside the browser and along with the other developer tools you use everyday, such as Visual Studio Code.</span></span>  

<span data-ttu-id="35c82-118">クロムベースのブラウザー開発者として、新しい Microsoft Edge ブラウザーに快適に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-118">As a Chromium-based browser developer, you should feel comfortable with the new Microsoft Edge browser.</span></span>  <span data-ttu-id="35c82-119">Microsoft Edge \(Chromium\) DevTools は、既に知っている開発者ツールと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="35c82-119">The Microsoft Edge \(Chromium\) DevTools work just like the developer tools you already know and use.</span></span>  <span data-ttu-id="35c82-120">Microsoft Edge \(Chromium\) 開発者ツールは、Microsoft Edge \(Chromium\) DevTools または DevTools と呼ばれることが多い。</span><span class="sxs-lookup"><span data-stu-id="35c82-120">The Microsoft Edge \(Chromium\) Developer Tools are often called the Microsoft Edge \(Chromium\) DevTools or DevTools.</span></span>  <span data-ttu-id="35c82-121">詳細については、「Microsoft Edge [(クロム) DevTools の新機能」に移動します][DevtoolsGuideChromiumWhatsNewIndex]。</span><span class="sxs-lookup"><span data-stu-id="35c82-121">For more information, navigate to [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].</span></span>  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   <span data-ttu-id="35c82-123">Microsoft Edge (Chromium) DevTools</span><span class="sxs-lookup"><span data-stu-id="35c82-123">Microsoft Edge (Chromium) DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="35c82-124">以前に Microsoft Edge \(EdgeHTML\) 用に開発し、新しい Microsoft Edge を評価している場合は、Web ページをより簡単かつ迅速に構築およびテストするための優れた新しいツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="35c82-124">If you previously developed for Microsoft Edge \(EdgeHTML\) and are evaluating the new Microsoft Edge, it now provides great new tools for you to build and test your webpages easier and faster.</span></span>  

## <a name="open-the-devtools"></a><span data-ttu-id="35c82-125">DevTools を開く</span><span class="sxs-lookup"><span data-stu-id="35c82-125">Open the DevTools</span></span>  

<span data-ttu-id="35c82-126">Microsoft Edge DevTools は、Microsoft Edge ブラウザーに直接組み込む一連のツールです。</span><span class="sxs-lookup"><span data-stu-id="35c82-126">The Microsoft Edge DevTools are a set of tools built directly into the Microsoft Edge browser.</span></span>  <span data-ttu-id="35c82-127">DevTools を使用すると、ブラウザー内で以下のタスクを直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="35c82-127">The DevTools allows you to do the following tasks all directly within the browser.</span></span>  

*   <span data-ttu-id="35c82-128">HTML Web ページの検査と変更</span><span class="sxs-lookup"><span data-stu-id="35c82-128">Inspect and make changes to your HTML webpage</span></span>  
*   <span data-ttu-id="35c82-129">CSS を編集し、Web ページのレンダリング方法をプレビューする</span><span class="sxs-lookup"><span data-stu-id="35c82-129">Edit CSS and instantly see preview how your webpage renders</span></span>  
*   <span data-ttu-id="35c82-130">フロントエンド `console.log()` JavaScript コードのすべてのステートメントを確認する</span><span class="sxs-lookup"><span data-stu-id="35c82-130">Review all of the `console.log()` statements from your front-end JavaScript code</span></span>  
*   <span data-ttu-id="35c82-131">スクリプトをデバッグし、ブレークポイントを設定し、コードを 1 行に 1 行にステップ実行する</span><span class="sxs-lookup"><span data-stu-id="35c82-131">Debug your script, set breakpoints, and step through your code line by line</span></span>  
    
<span data-ttu-id="35c82-132">DevTools が提供する機能のその他の例を使用すると、Microsoft Edge で Web ページを簡単かつ迅速に構築およびテストできます。</span><span class="sxs-lookup"><span data-stu-id="35c82-132">More examples of the features that DevTools provide to make it easier and faster for you to build and test your webpage in Microsoft Edge.</span></span>  

<span data-ttu-id="35c82-133">DevTools を開く方法</span><span class="sxs-lookup"><span data-stu-id="35c82-133">To open the DevTools</span></span>  

*   <span data-ttu-id="35c82-134">選択する</span><span class="sxs-lookup"><span data-stu-id="35c82-134">Select</span></span> `F12` 
*   <span data-ttu-id="35c82-135">`Ctrl` + `Shift` + `I` [\(Windows/Linux\) または `Command` + `Option` + `I` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c82-135">Select `Ctrl`+`Shift`+`I` \(Windows/Linux\) or `Command`+`Option`+`I` \(macOS\)</span></span>  
    
<span data-ttu-id="35c82-136">サイト上の要素の HTML または CSS を表示する場合は、要素を右クリックし\*\*\*\*、[検査] を選択して [要素] ツールに**移動**します。</span><span class="sxs-lookup"><span data-stu-id="35c82-136">If you want to see the HTML or CSS for an element on your site, right-click the element and choose **Inspect** to jump into the **Elements** tool.</span></span>  <span data-ttu-id="35c82-137">要素の検査モードで DevTools を開く**場合**は `Ctrl` + `Shift` + `C` 、[\(Windows/Linux\) または `Command` + `Option` + `C` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c82-137">To open the DevTools in **Inspect Element Mode**, select `Ctrl`+`Shift`+`C` \(Windows/Linux\)  or `Command`+`Option`+`C` \(macOS\).</span></span> <span data-ttu-id="35c82-138">要素 **の検査モードを** 使用すると、Web ページで要素を選択し、[要素] ツールに HTML と CSS を **表示** できます。</span><span class="sxs-lookup"><span data-stu-id="35c82-138">the **Inspect Element Mode** allows you to choose an element on the webpage and display the HTML and CSS in the **Elements** tool.</span></span>  

<span data-ttu-id="35c82-139">フロントエンド JavaScript コードからログを確認する場合や、スクリプトをすばやく実行する場合は、コンソール を開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="35c82-139">If you want to review logs from your front-end JavaScript code or quickly run some script, open the **Console**.</span></span>   <span data-ttu-id="35c82-140">DevTools で**コンソール**ツールを起動するには `Ctrl` + `Shift` + `J` 、[\(Windows/Linux\) または `Command` + `Option` + `J` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c82-140">To launch the **Console** tool in the DevTools, select `Ctrl`+`Shift`+`J` \(Windows/Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  

## <a name="core-tools"></a><span data-ttu-id="35c82-141">コア ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-141">Core tools</span></span>  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools コア ツール" lightbox="./media/devtools-core-tools.png":::
   <span data-ttu-id="35c82-143">Microsoft Edge (Chromium) DevTools コア ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-143">Microsoft Edge (Chromium) DevTools core tools</span></span>  
:::image-end::: 

<span data-ttu-id="35c82-144">Microsoft Edge \(Chromium\) DevTools には、次のツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="35c82-144">The Microsoft Edge \(Chromium\) DevTools include the following tools.</span></span>  

*   <span data-ttu-id="35c82-145">HTML **と** CSS の編集、アクセシビリティ プロパティの検査、イベント リスナーの表示、DOM ミューテーション ブレークポイントの設定を行う要素ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-145">An **Elements** tool to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints</span></span>  
*   <span data-ttu-id="35c82-146">ログ **メッセージの** 確認とフィルター処理、JavaScript オブジェクトと DOM ノードの検査、および選択したウィンドウまたはフレームのコンテキストでの JavaScript の実行を行うコンソール</span><span class="sxs-lookup"><span data-stu-id="35c82-146">A **Console** to review and filter log messages, inspect JavaScript objects and DOM nodes, and run JavaScript in the context of the selected window or frame</span></span>  
*   <span data-ttu-id="35c82-147">コード **を開** いて編集し、ブレークポイントを設定し、コードをステップ実行し、Web ページの状態を表示するソース ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-147">A **Sources** tool to open and edit your code, set breakpoints, step through code, and display the state of your webpage</span></span>
*   <span data-ttu-id="35c82-148">ネットワーク **キャッシュ** とブラウザー キャッシュからの要求と応答を監視および検査するネットワーク ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-148">A **Network** tool to monitor and inspect requests and responses from the network and browser cache</span></span>   
*   <span data-ttu-id="35c82-149">サイト **で** 必要な時間とシステム リソースをプロファイルするパフォーマンス ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-149">A **Performance** tool to profile the time and system resources required by your site</span></span>  
*   <span data-ttu-id="35c82-150">メモリ **リソース** の使用を測定し、異なる状態のコード ランタイムでヒープ スナップショットを比較するメモリ ツール</span><span class="sxs-lookup"><span data-stu-id="35c82-150">A **Memory** tool to measure your use of memory resources and compare heap snapshots at different states of code runtime</span></span>  
*   <span data-ttu-id="35c82-151">Web **アプリ** マニフェスト、サービス ワーカー、およびサービス ワーカー キャッシュを検査、変更、およびデバッグするアプリケーション ツール。</span><span class="sxs-lookup"><span data-stu-id="35c82-151">An **Application** tool to inspect, modify, and debug web app manifests, service workers, and service worker caches.</span></span>  <span data-ttu-id="35c82-152">また、アプリケーション ツールからストレージ、データベース、キャッシュを検査および **管理** することもできます。</span><span class="sxs-lookup"><span data-stu-id="35c82-152">You may also inspect and manage storage, databases, and caches from the **Application** tool.</span></span>  
*   <span data-ttu-id="35c82-153">セキュリティ **の** 問題をデバッグし、Web ページに HTTPS が適切に実装されていることを確認するためのセキュリティ ツール。</span><span class="sxs-lookup"><span data-stu-id="35c82-153">A **Security** tool to debug security issues and ensure that you have properly implemented HTTPS on your webpage.</span></span>  <span data-ttu-id="35c82-154">HTTPS は、サイトとサイト上に個人情報を入力するユーザーの両方に対して、重要なセキュリティとデータの整合性を提供します。</span><span class="sxs-lookup"><span data-stu-id="35c82-154">HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.</span></span>  
*   <span data-ttu-id="35c82-155">Web **ページの監査** を実行する監査ツール \( **名前が変更**されました。</span><span class="sxs-lookup"><span data-stu-id="35c82-155">An **Audits** tool \(now renamed **Lighthouse**\) to run an audit of your webpage.</span></span>  <span data-ttu-id="35c82-156">監査の結果は、次の方法でサイトの品質を向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35c82-156">The results of the audit help you improve the quality of your site in the following ways.</span></span>  
    *   <span data-ttu-id="35c82-157">Web ページへのアクセス、セキュリティ保護、パフォーマンスに関する一般的なエラーをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="35c82-157">Catch common errors related to making your webpage accessible, secure, performant, and so on.</span></span>  
    *   <span data-ttu-id="35c82-158">各エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="35c82-158">Fix each error.</span></span>  
    *   <span data-ttu-id="35c82-159">PWA を構築します。</span><span class="sxs-lookup"><span data-stu-id="35c82-159">Build a PWA.</span></span>  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

<span data-ttu-id="35c82-160">フィードバックと [機能要求を送信します](#getting-in-touch-with-the-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="35c82-160">Send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).</span></span>  

## <a name="extensions"></a><span data-ttu-id="35c82-161">拡張機能</span><span class="sxs-lookup"><span data-stu-id="35c82-161">Extensions</span></span>  

<span data-ttu-id="35c82-162">Web ページ \(または apps\) の構築中に問題を診断してデバッグすると、拡張機能を使用して DevTools にアクセスした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-162">You may have accessed DevTools using extensions when you diagnosed and debugged issues while you built your webpages \(or apps\).</span></span> <span data-ttu-id="35c82-163">Microsoft Edge 拡張機能は [、Microsoft Edge アドオンから取得されます][MicrosoftEdgeAddonsExtensions]。</span><span class="sxs-lookup"><span data-stu-id="35c82-163">Microsoft Edge extensions are acquired from [Microsoft Edge Add-ons][MicrosoftEdgeAddonsExtensions].</span></span>  <span data-ttu-id="35c82-164">[Microsoft Edge アドオンで][MicrosoftEdgeAddonsExtensions]、[開発者ツール] カテゴリから DevTools 拡張機能を参照するか、特定の拡張機能を検索します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="35c82-164">On [Microsoft Edge Add-ons][MicrosoftEdgeAddonsExtensions], browse DevTools extensions from the **Developer tools** category or search for a specific extension.</span></span>  

<span data-ttu-id="35c82-165">[Chrome Web ストア][GoogleChromeWebstoreExtensions]から拡張機能を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="35c82-165">You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].</span></span>  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge の Chrome Web ストア" lightbox="./media/allow-extensions-from-stores.png":::
   <span data-ttu-id="35c82-167">Microsoft Edge の Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="35c82-167">Chrome Web Store in Microsoft Edge</span></span>  
:::image-end:::  

<span data-ttu-id="35c82-168">上部の [他のストアからの拡張機能を許可する] を **選択** し、表示されるダイアログで [ **許可** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="35c82-168">At the top, choose **Allow extensions from other stores** and then choose **Allow** in the dialog that appears.</span></span>  

> [!NOTE]
> <span data-ttu-id="35c82-169">Microsoft Store 以外のソースからインストールされた拡張機能は未確認であり、ブラウザーのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-169">Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.</span></span>  

<span data-ttu-id="35c82-170">[Chrome **に追加] を** 選択して、DevTools 拡張機能を Microsoft Edge に追加します。</span><span class="sxs-lookup"><span data-stu-id="35c82-170">Choose **Add to Chrome** to add your DevTools extension to Microsoft Edge.</span></span>  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="Chrome Web ストアから Microsoft Edge に拡張機能を追加する" lightbox="./media/install-extension-from-chrome-store.png":::
   <span data-ttu-id="35c82-172">Chrome Web ストアから Microsoft Edge に拡張機能を追加する</span><span class="sxs-lookup"><span data-stu-id="35c82-172">Add extension from Chrome Web Store to Microsoft Edge</span></span>  
:::image-end:::  

## <a name="shortcuts"></a><span data-ttu-id="35c82-173">ショートカット</span><span class="sxs-lookup"><span data-stu-id="35c82-173">Shortcuts</span></span>  

<span data-ttu-id="35c82-174">次のショートカットは、メインの DevTools ウィンドウを制御します。すべてのツール間で動作するか、または両方を実行します。</span><span class="sxs-lookup"><span data-stu-id="35c82-174">The following shortcuts control the main DevTools window, work across all tools, or both.</span></span>  

| <span data-ttu-id="35c82-175">Action</span><span class="sxs-lookup"><span data-stu-id="35c82-175">Action</span></span> | <span data-ttu-id="35c82-176">Windows/Linux</span><span class="sxs-lookup"><span data-stu-id="35c82-176">Windows/Linux</span></span> | <span data-ttu-id="35c82-177">macOS</span><span class="sxs-lookup"><span data-stu-id="35c82-177">macOS</span></span> |  
|:--- |:--- | :--- |  
| <span data-ttu-id="35c82-178">DevTools \(開いて最後に表示されたツール\) を表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="35c82-178">Show/Hide DevTools \(opens to last viewed tool\)</span></span> | `F12` <span data-ttu-id="35c82-179">または `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="35c82-179">or `Ctrl`+`Shift`+</span></span>`I` | `Command`+`Option`+`I` |  
| <span data-ttu-id="35c82-180">コンソールの表示</span><span class="sxs-lookup"><span data-stu-id="35c82-180">Show the Console</span></span> | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| <span data-ttu-id="35c82-181">要素を選択して **要素ツールに** HTML と CSS を表示できる要素の検査モードで DevTools を **表示** する</span><span class="sxs-lookup"><span data-stu-id="35c82-181">Show the DevTools in **Inspect Element Mode** that allows you to choose an element and display the HTML and CSS in the **Elements** tool</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| <span data-ttu-id="35c82-182">設定の表示</span><span class="sxs-lookup"><span data-stu-id="35c82-182">Show Settings</span></span> | `?` <span data-ttu-id="35c82-183">または `Fn`+</span><span class="sxs-lookup"><span data-stu-id="35c82-183">or `Fn`+</span></span>`F1` | `?` <span data-ttu-id="35c82-184">または `Fn`+</span><span class="sxs-lookup"><span data-stu-id="35c82-184">or `Fn`+</span></span>`F1` |  
| <span data-ttu-id="35c82-185">次のパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="35c82-185">Show the next panel</span></span> | `Ctrl`+`]` | `Command`+`]` |  
| <span data-ttu-id="35c82-186">前のパネルを表示する</span><span class="sxs-lookup"><span data-stu-id="35c82-186">Show the previous panel</span></span> | `Ctrl`+`[` | `Command`+`[` |  
| <span data-ttu-id="35c82-187">DevTools を最後に使用した位置にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="35c82-187">Dock the DevTools in the last position used.</span></span>  <span data-ttu-id="35c82-188">DevTools がセッション全体の既定の位置に残っている場合、ショートカットは DevTools を別のウィンドウにドッキング解除します。</span><span class="sxs-lookup"><span data-stu-id="35c82-188">If the DevTools remain in the default position for the entire session, the shortcut undocks the DevTools into a separate window</span></span> | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| <span data-ttu-id="35c82-189">**デバイス モード**の切り替え</span><span class="sxs-lookup"><span data-stu-id="35c82-189">Toggle **Device Mode**</span></span> | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| <span data-ttu-id="35c82-190">要素 **を選択し** 、[要素] ツールで HTML と CSS を表示できる要素の検査モードの切り **替** え</span><span class="sxs-lookup"><span data-stu-id="35c82-190">Toggle **Inspect Element Mode** that allows to you to choose an element and display the HTML and CSS in the **Elements** tool</span></span> | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| <span data-ttu-id="35c82-191">コマンド メニューを表示する</span><span class="sxs-lookup"><span data-stu-id="35c82-191">Show the Command Menu</span></span> | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| <span data-ttu-id="35c82-192">ドロワーの表示/非表示</span><span class="sxs-lookup"><span data-stu-id="35c82-192">Show/Hide the Drawer</span></span> | `Esc` | `Esc` |  
| <span data-ttu-id="35c82-193">更新。</span><span class="sxs-lookup"><span data-stu-id="35c82-193">Refresh.</span></span>  <span data-ttu-id="35c82-194">キャッシュを使用して Web ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="35c82-194">Refreshes the webpage using the cache.</span></span>  | `F5` <span data-ttu-id="35c82-195">または `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="35c82-195">or `Ctrl`+</span></span>`R` | `Command`+`R` |  
| <span data-ttu-id="35c82-196">ハードの更新。</span><span class="sxs-lookup"><span data-stu-id="35c82-196">Hard Refresh.</span></span>  <span data-ttu-id="35c82-197">Microsoft Edge にリソースの再ダウンロードと再読み込みを強制的に行います。</span><span class="sxs-lookup"><span data-stu-id="35c82-197">Forces Microsoft Edge to download resources again and reload.</span></span>  <span data-ttu-id="35c82-198">使用されるリソースは、キャッシュされたバージョンから取得される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35c82-198">The resources that are used may come from a cached version</span></span> | `Ctrl`<span data-ttu-id="35c82-199">+`F5` または `Ctrl`+`Shift`+</span><span class="sxs-lookup"><span data-stu-id="35c82-199">+`F5` or `Ctrl`+`Shift`+</span></span>`R` | `Command`+`Shift`+`R` |  
| <span data-ttu-id="35c82-200">現在のパネル内のテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="35c82-200">Search for text within the current panel.</span></span>  <span data-ttu-id="35c82-201">監査、アプリケーション、およびセキュリティ ツールではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="35c82-201">Not supported in the Audits, Application, and Security tools</span></span> | `Ctrl`+`F` | `Command`+`F` |  
| <span data-ttu-id="35c82-202">ドロワーに検索ツールを表示し、読み込まれたすべてのリソースでテキストを検索できます</span><span class="sxs-lookup"><span data-stu-id="35c82-202">Show the Search tool in the Drawer, which lets you search for text across all loaded resources</span></span> | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| <span data-ttu-id="35c82-203">ソース パネルでファイルを開く</span><span class="sxs-lookup"><span data-stu-id="35c82-203">Open a file in the Sources panel</span></span> | `Ctrl`<span data-ttu-id="35c82-204">+`O` または `Ctrl`+</span><span class="sxs-lookup"><span data-stu-id="35c82-204">+`O` or `Ctrl`+</span></span>`P` | `Command`<span data-ttu-id="35c82-205">+`O` または `Command`+</span><span class="sxs-lookup"><span data-stu-id="35c82-205">+`O` or `Command`+</span></span>`P` |  
| <span data-ttu-id="35c82-206">拡大する</span><span class="sxs-lookup"><span data-stu-id="35c82-206">Zoom in</span></span> | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| <span data-ttu-id="35c82-207">縮小</span><span class="sxs-lookup"><span data-stu-id="35c82-207">Zoom out</span></span> | `Ctrl`+`-` | `Command`+`-` |  
| <span data-ttu-id="35c82-208">既定のズーム レベルを復元する</span><span class="sxs-lookup"><span data-stu-id="35c82-208">Restore default zoom level</span></span> | `Ctrl`+`0` | `Command`+`0` |  
| <span data-ttu-id="35c82-209">スニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="35c82-209">Run snippet</span></span> | `Ctrl`<span data-ttu-id="35c82-210">+`O``Ctrl` + `P` または、次 `!` にスクリプトの名前を入力してから、</span><span class="sxs-lookup"><span data-stu-id="35c82-210">+`O` or `Ctrl`+`P`, type `!` followed by the name of the script, then select</span></span> `Enter` | <span data-ttu-id="35c82-211">を `Command` + `O` 選択 `Command` + `P` するか、 `!` スクリプトの名前を入力してから、</span><span class="sxs-lookup"><span data-stu-id="35c82-211">Select `Command`+`O` or `Command`+`P`, type `!` followed by the name of the script, then select</span></span> `Enter` |  
| <span data-ttu-id="35c82-212">編集できない HTML ソース コードを新しいタブに表示する</span><span class="sxs-lookup"><span data-stu-id="35c82-212">Show non-editable HTML source code in a new tab</span></span> | `Ctrl`+`U` | <span data-ttu-id="35c82-213">該当せず</span><span class="sxs-lookup"><span data-stu-id="35c82-213">N/A</span></span> |  

> [!NOTE]
> <span data-ttu-id="35c82-214">デバッグ中にブレークポイントで一時停止している場合は、最初に**更新**ショートカットがランタイムを再開します。</span><span class="sxs-lookup"><span data-stu-id="35c82-214">If you are debugging and paused at a breakpoint, the **Refresh** shortcut resumes the runtime first.</span></span>  

## <a name="see-also"></a><span data-ttu-id="35c82-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="35c82-215">See also</span></span>  

*   [<span data-ttu-id="35c82-216">初級向け DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="35c82-216">DevTools for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideChromiumBeginnersHtml]  
*   [<span data-ttu-id="35c82-217">Microsoft Edge (Chromium) DevTools プロトコル</span><span class="sxs-lookup"><span data-stu-id="35c82-217">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolChromiumIndex]  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="35c82-218">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="35c82-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<span data-ttu-id="35c82-219">近々ある [DevTools][DevtoolsGuideChromiumWhatsNewIndex] の最新の機能をプレビューする場合は、毎晩ビルドされる [Microsoft Edge Canary][MicrosoftedgeinsiderDownload] をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="35c82-219">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideChromiumWhatsNewIndex], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2021/02/devtools "Microsoft Edge (Chromium) DevTools の新機能 | Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools プロトコル | Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge アドオン"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channelsをダウンロードする"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  
