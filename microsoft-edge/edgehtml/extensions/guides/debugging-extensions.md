---
description: F12 開発者ツールを使用して、拡張機能のバックグラウンド スクリプト、コンテンツ スクリプト、拡張機能ページをデバッグする方法について説明します。
title: 拡張機能 - デバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, javascript, 開発者, デバッグ, デバッグ
ms.custom: seodec18
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 17da1a2badd99dd57bb8b1e3de063fe045b34333
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234968"
---
# <span data-ttu-id="41f51-104">拡張機能のデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="41f51-105">F12 開発者ツールを使用して、Microsoft Edge で拡張機能をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="41f51-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>

<span data-ttu-id="41f51-106">次のビデオでは、Microsoft Edge の拡張機能を利用して、それぞれのデバッグ シナリオを説明し、途中で修正します。</span><span class="sxs-lookup"><span data-stu-id="41f51-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span> <span data-ttu-id="41f51-107">詳しくは、以下の詳しい手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41f51-107">See the step-by-step instructions below for more info.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> <span data-ttu-id="41f51-108">F12 で拡張機能のデバッグを利用するには、まず about:flags で開発者向け機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41f51-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span> <span data-ttu-id="41f51-109">この [方法の詳細については、「拡張機能の追加](./adding-and-removing-extensions.md) と削除」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41f51-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>


## <span data-ttu-id="41f51-110">バックグラウンド スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-110">Background script debugging</span></span>
<span data-ttu-id="41f51-111">拡張機能のバックグラウンド スクリプトのデバッグを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41f51-111">To start debugging the background script of your extension:</span></span>

1. <span data-ttu-id="41f51-112">[その他 **] (...)** の後に [拡張機能] を **クリックして、** 拡張機能ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="41f51-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
 ![[その他] ボタン](./../media/morebutton.png)
2. <span data-ttu-id="41f51-114">デバッグする拡張機能をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41f51-114">Click on the extension that you want to debug.</span></span>
3. <span data-ttu-id="41f51-115">[バックグラウンド] **ページのリンクをクリック** して、バックグラウンド プロセス用に F12 キーを表示します。</span><span class="sxs-lookup"><span data-stu-id="41f51-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
 ![[inspect] リンクを含むオプションの選択された拡張機能ビュー](./../media/debug-inspect.png)
4. <span data-ttu-id="41f51-117">F12 **の [デバッガー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="41f51-117">Select the **Debugger** tab in F12.</span></span>
5. <span data-ttu-id="41f51-118">拡張機能のバックグラウンド スクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="41f51-118">Navigate to and select your extension's background script.</span></span>
6. <span data-ttu-id="41f51-119">ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="41f51-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![ブレーク ポイントを含むバックグラウンド スクリプトを示す f12 コンソール](./../media/debug-f12-background.png)
7. <span data-ttu-id="41f51-121">[コンソール] **タブを** 選択し、コマンド " を実行します `location.reload()` 。</span><span class="sxs-lookup"><span data-stu-id="41f51-121">Select the **Console** tab and execute the command "`location.reload()`".</span></span> <span data-ttu-id="41f51-122">これにより、バックグラウンド スクリプトが再び実行され、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="41f51-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
 ![location.reload が入力されたコンソール](./../media/debug-f12-background-console.png)


## <span data-ttu-id="41f51-124">コンテンツ スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-124">Content script debugging</span></span>
<span data-ttu-id="41f51-125">拡張機能のコンテンツ スクリプトのデバッグを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41f51-125">To start debugging the content script of your extension:</span></span>

1. <span data-ttu-id="41f51-126">[その他] **(...)** ボタンに移動して **[F12 開発者** ツール] を選択するか、キーボードで F12 キーを押して、F12 を起動します。</span><span class="sxs-lookup"><span data-stu-id="41f51-126">Launch F12 by either navigating to the **More (...)** button and selecting **"F12 Developer Tools"** or by pressing F12 on your keyboard.</span></span>
2. <span data-ttu-id="41f51-127">拡張機能のコンテンツ スクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="41f51-127">Navigate to and select your extension's content script.</span></span> <span data-ttu-id="41f51-128">現在実行されている拡張機能のコンテンツ スクリプトは、拡張機能ごとに異なるフォルダーで示されます。</span><span class="sxs-lookup"><span data-stu-id="41f51-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41f51-129">実行中のコンテンツ スクリプトだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41f51-129">Only running content scripts will appear.</span></span>

3. <span data-ttu-id="41f51-130">ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="41f51-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![コンテンツ スクリプトがデバッグされている f12](./../media/debug-content-f12.png)
4. <span data-ttu-id="41f51-132">ブラウザーのタブを更新して、コードのステップ実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="41f51-132">Refresh the browser tab to begin stepping though your code.</span></span>




## <span data-ttu-id="41f51-133">拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-133">Extension page debugging</span></span>

<span data-ttu-id="41f51-134">デバッグのために拡張機能ページのソース コードにアクセスするために使用できるメソッドは 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="41f51-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span> <span data-ttu-id="41f51-135">1 つのメソッドはさまざまなページに適用されます。もう 1 つのメソッドはポップアップ ページでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="41f51-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>

### <span data-ttu-id="41f51-136">拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-136">Debugging any extension page</span></span>
<span data-ttu-id="41f51-137">次のメソッドは、オプション ページやポップアップなど、すべての拡張機能ページに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="41f51-137">The following method works for all extension pages like the options page and popups:</span></span>


1. <span data-ttu-id="41f51-138">ページの背景を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="41f51-138">Right-click on the background of your page.</span></span>
2. <span data-ttu-id="41f51-139">[ソース **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="41f51-139">Select **"View source"**.</span></span>

   ![f12 キーを使用したポップアップ デバッグ - 選択](./../media/debug-popup-select.png)

3. <span data-ttu-id="41f51-141">F12 キーが開いたら、デバッグするファイル内にブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="41f51-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>

   ![f12 キーを使用したポップアップ デバッグ](./../media/debug-popup-f12.png)
4. <span data-ttu-id="41f51-143">[コンソール] **タブを** 選択し、コマンドを実行します `location.reload()` 。</span><span class="sxs-lookup"><span data-stu-id="41f51-143">Select the **Console** tab and execute the command `location.reload()`.</span></span> <span data-ttu-id="41f51-144">これにより、ページ スクリプトが再び実行され、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="41f51-144">This will re-execute the page script, allowing you to step through your code.</span></span>  

   ![location.reload が入力されたコンソール](./../media/debug-f12-background-console.png)

### <span data-ttu-id="41f51-146">ポップアップ拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="41f51-146">Debugging a popup extension page</span></span>
<span data-ttu-id="41f51-147">拡張ページをデバッグする方法はポップアップ拡張ページにも適用されます。次の手順では、ポップアップをデバッグする別の方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="41f51-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>

1. <span data-ttu-id="41f51-148">拡張機能のアイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="41f51-148">Right-click your extension's icon.</span></span>
2. <span data-ttu-id="41f51-149">[ポップアップ **の検査] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="41f51-149">Select **"Inspect popup"**.</span></span>

   ![ポップアップ デバッグ検査](./../media/debug-popup-inspect.png)
3. <span data-ttu-id="41f51-151">ブレークポイントを配置してポップアップを再読み込みするには、上記の手順 3 と 4 に従います。</span><span class="sxs-lookup"><span data-stu-id="41f51-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>
