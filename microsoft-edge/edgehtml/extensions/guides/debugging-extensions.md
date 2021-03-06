---
description: F12 Developer Tools では、拡張機能のバックグラウンド スクリプト、コンテンツ スクリプト、および拡張ページをデバッグする方法について説明します。
title: デバッグ|拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, javascript, developer, debug, debuging
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a23c7558080cca7671cdfc9790705a8d8c9ed705
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399366"
---
# <a name="debugging-extensions"></a><span data-ttu-id="e14ad-104">拡張機能のデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="e14ad-105">F12 Developer Tools を使用して、Microsoft Edge で拡張機能をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="e14ad-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>  

<span data-ttu-id="e14ad-106">次のビデオでは、バグのある Microsoft Edge 拡張機能を使用して、各デバッグ シナリオを実行し、途中で修正します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span>  <span data-ttu-id="e14ad-107">詳細については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e14ad-107">See the step-by-step instructions below for more info.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]  

> [!NOTE]
> <span data-ttu-id="e14ad-108">F12 で拡張機能のデバッグを利用するには、まず about:flags で開発者機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e14ad-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span>  <span data-ttu-id="e14ad-109">この [方法の詳細については、「拡張機能の追加](./adding-and-removing-extensions.md) と削除」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e14ad-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>  

## <a name="background-script-debugging"></a><span data-ttu-id="e14ad-110">バックグラウンド スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-110">Background script debugging</span></span>  

<span data-ttu-id="e14ad-111">拡張機能のバックグラウンド スクリプトのデバッグを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-111">To start debugging the background script of your extension:</span></span>  

1.  <span data-ttu-id="e14ad-112">[詳細 **] (...)** の後に [拡張機能] **をクリックして** 、拡張機能ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
    
    ![[その他] ボタン](../media/morebutton.png)  
    
1.  <span data-ttu-id="e14ad-114">デバッグする拡張機能をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e14ad-114">Click on the extension that you want to debug.</span></span>  
1.  <span data-ttu-id="e14ad-115">[背景] **ページリンクをクリック** して、バックグラウンド プロセスの F12 を表示します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
    
    ![[検査] リンクを含むオプションの選択された拡張機能ビュー](../media/debug-inspect.png)  
    
1.  <span data-ttu-id="e14ad-117">F12 **の [** デバッガー] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-117">Select the **Debugger** tab in F12.</span></span>  
1.  <span data-ttu-id="e14ad-118">拡張機能のバックグラウンド スクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-118">Navigate to and select your extension's background script.</span></span>  
1.  <span data-ttu-id="e14ad-119">ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
    
    ![f12 コンソールに、ブレーク ポイントを含むバックグラウンド スクリプトを表示する](../media/debug-f12-background.png)  
    
1.  <span data-ttu-id="e14ad-121">[コンソール] **タブを** 選択し、コマンドを `location.reload()` 実行します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-121">Select the **Console** tab and execute the `location.reload()` command.</span></span>  <span data-ttu-id="e14ad-122">これにより、バックグラウンド スクリプトが再び実行され、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e14ad-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
    
    ![location.reload が入力されたコンソール](../media/debug-f12-background-console.png)  
    
## <a name="content-script-debugging"></a><span data-ttu-id="e14ad-124">コンテンツ スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-124">Content script debugging</span></span>  

<span data-ttu-id="e14ad-125">拡張機能のコンテンツ スクリプトのデバッグを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-125">To start debugging the content script of your extension:</span></span>  

1.  <span data-ttu-id="e14ad-126">[詳細] **(....)** ボタンに移動し **、[F12 Developer Tools]** を選択するか、キーボードを押して F12 `F12` を起動します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-126">Launch F12 by either navigating to the **More (...)** button and selecting **F12 Developer Tools** or by pressing `F12` on your keyboard.</span></span>  
1.  <span data-ttu-id="e14ad-127">拡張機能のコンテンツ スクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-127">Navigate to and select your extension's content script.</span></span>  <span data-ttu-id="e14ad-128">現在実行されている拡張機能のコンテンツ スクリプトは、拡張機能ごとに異なるフォルダーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="e14ad-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e14ad-129">実行中のコンテンツ スクリプトだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e14ad-129">Only running content scripts will appear.</span></span>  
    
1.  <span data-ttu-id="e14ad-130">ソース コード行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
    
    ![コンテンツ スクリプトがデバッグされている f12](../media/debug-content-f12.png)  
    
1.  <span data-ttu-id="e14ad-132">ブラウザー タブを更新して、コードのステップ実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-132">Refresh the browser tab to begin stepping though your code.</span></span>  
    
## <a name="extension-page-debugging"></a><span data-ttu-id="e14ad-133">拡張ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-133">Extension page debugging</span></span>  

<span data-ttu-id="e14ad-134">拡張ページのソース コードにアクセスしてデバッグするために使用できる方法は 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="e14ad-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span>  <span data-ttu-id="e14ad-135">1 つのメソッドは、さまざまなページに適用されます。もう 1 つはポップアップ ページでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>  

### <a name="debugging-any-extension-page"></a><span data-ttu-id="e14ad-136">拡張ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-136">Debugging any extension page</span></span>  

<span data-ttu-id="e14ad-137">次のメソッドは、オプション ページやポップアップなど、すべての拡張ページで機能します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-137">The following method works for all extension pages like the options page and popups:</span></span>  

1.  <span data-ttu-id="e14ad-138">ページの背景を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e14ad-138">Right-click on the background of your page.</span></span>  
1.  <span data-ttu-id="e14ad-139">[ソース **の表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e14ad-139">Select **View source**.</span></span>  
    
    ![ポップアップ デバッグを f12 で開く](../media/debug-popup-select.png)  
    
1.  <span data-ttu-id="e14ad-141">F12 が開いたら、デバッグするファイル内にブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>  
    
    ![f12 を使用したポップアップ デバッグ](../media/debug-popup-f12.png)  
    
1.  <span data-ttu-id="e14ad-143">[コンソール] **タブを** 選択し、コマンドを実行します `location.reload()` 。</span><span class="sxs-lookup"><span data-stu-id="e14ad-143">Select the **Console** tab and execute the command `location.reload()`.</span></span>  <span data-ttu-id="e14ad-144">これにより、ページ スクリプトが再び実行され、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e14ad-144">This will re-execute the page script, allowing you to step through your code.</span></span>  
    
    ![location.reload が入力されたコンソール](../media/debug-f12-background-console.png)  
    
### <a name="debugging-a-popup-extension-page"></a><span data-ttu-id="e14ad-146">ポップアップ拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="e14ad-146">Debugging a popup extension page</span></span>  

<span data-ttu-id="e14ad-147">拡張ページのデバッグ方法は、ポップアップ拡張ページにも適用されます。次の手順では、ポップアップをデバッグする別の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e14ad-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>  

1.  <span data-ttu-id="e14ad-148">拡張機能のアイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e14ad-148">Right-click your extension's icon.</span></span>  
1.  <span data-ttu-id="e14ad-149">[ポップアップ **の検査] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e14ad-149">Select **Inspect popup**.</span></span>  
    
    ![ポップアップ デバッグの検査](../media/debug-popup-inspect.png)  
    
1.  <span data-ttu-id="e14ad-151">ブレークポイントを配置し、ポップアップを再読み込みするには、上記の手順 3 と 4 に従います。</span><span class="sxs-lookup"><span data-stu-id="e14ad-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>  
    