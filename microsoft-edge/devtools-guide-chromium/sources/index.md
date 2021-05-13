---
description: '[ソース] ツールを使用して、サーバーから返される JavaScript を表示、変更、およびデバッグし、現在の Web ページを構成するリソースを検査します。  Sources ツールを開発環境として使用するには、ワークスペースにソース ファイルを追加します。'
title: ソース ツールの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d3ef49bf986d8827216bd0bc183e45806aa0a2c3
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564715"
---
# <a name="sources-tool-overview"></a><span data-ttu-id="49708-105">ソース ツールの概要</span><span class="sxs-lookup"><span data-stu-id="49708-105">Sources tool overview</span></span>  

<span data-ttu-id="49708-106">ソース ツール **を使用して** 、フロントエンド JavaScript コードを表示、変更、デバッグし、現在の Web ページを構成するリソースを検査します。</span><span class="sxs-lookup"><span data-stu-id="49708-106">Use the **Sources** tool to view, modify, and debug front-end JavaScript code, and to inspect the resources that make up the current webpage.</span></span>  <span data-ttu-id="49708-107">ソース **ツールには、** 次の 3 つのウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="49708-107">The **Sources** tool has three panes:</span></span>  

| <span data-ttu-id="49708-108">ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-108">Pane</span></span> | <span data-ttu-id="49708-109">アクション</span><span class="sxs-lookup"><span data-stu-id="49708-109">Actions</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="49708-110">**[ナビゲーター** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-110">**Navigator** pane</span></span> | <span data-ttu-id="49708-111">サーバーから返されるリソース間を移動して、現在の Web ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="49708-111">Navigate among the resources that are returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="49708-112">ファイル、画像、その他のリソースを選択し、そのパスを表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-112">Select files, images, and other resources, and view their paths.</span></span>  <span data-ttu-id="49708-113">必要に応じて、ローカル ワークスペースをセットアップして、変更をソース ファイルに直接保存します。</span><span class="sxs-lookup"><span data-stu-id="49708-113">Optionally, set up a local Workspace to save changes directly to source files.</span></span>  |  
| <span data-ttu-id="49708-114">**エディター** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-114">**Editor** pane</span></span> | <span data-ttu-id="49708-115">サーバーから返される JavaScript、HTML、CSS、その他のファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-115">View JavaScript, HTML, CSS, and other files that are returned from the server.</span></span>  <span data-ttu-id="49708-116">JavaScript または CSS を実験的に編集します。</span><span class="sxs-lookup"><span data-stu-id="49708-116">Make experimental edits to JavaScript or CSS.</span></span>  <span data-ttu-id="49708-117">変更は、ページを更新するまで保持され、Workspaces を使用してローカル ファイルに保存した場合はページ更新後も保持されます。</span><span class="sxs-lookup"><span data-stu-id="49708-117">Your changes are preserved until you refresh the page, or are preserved after page refresh if you save to a local file with Workspaces.</span></span>  <span data-ttu-id="49708-118">Workspaces または Overrides を使用する場合は、HTML ファイルも編集できます。</span><span class="sxs-lookup"><span data-stu-id="49708-118">When you use Workspaces or Overrides, you can edit HTML files as well.</span></span>  |  
| <span data-ttu-id="49708-119">**デバッガー ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="49708-119">**Debugger** pane</span></span> | <span data-ttu-id="49708-120">JavaScript デバッガーを使用してブレークポイントを設定し、JavaScript の実行を一時停止し、指定した JavaScript 式を確認しながら、行った編集内容を含むコードをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-120">Use the JavaScript Debugger to set breakpoints, pause running JavaScript, and step through the code, including any edits you have made, while watching any JavaScript expressions you specify.</span></span>  <span data-ttu-id="49708-121">現在のコード行のスコープ内にある変数の値を監視し、手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="49708-121">Watch and manually change the values of variables that are in-scope for the current line of code.</span></span>  |  

<span data-ttu-id="49708-122">次の図は、DevTools の左上隅に赤いボックスで強調表示されたナビゲーター ウィンドウ、右上\*\*\*\* で強調表示されているエディター ウィンドウ、および下部で強調表示された**デバッガー**ウィンドウを示しています。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="49708-122">The following figure shows the **Navigator** pane highlighted with a red box in the upper left corner of DevTools, the **Editor** pane highlighted in the upper right, and the **Debugger** pane highlighted on the bottom.</span></span>  <span data-ttu-id="49708-123">左側はブラウザー ウィンドウのメイン部分で、デバッガーがブレークポイントで一時停止している場合に、レンダリングされた Web ページが灰色表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-123">On the far left side is the main part of the browser window, showing the rendered webpage grayed-out because the debugger is paused on a breakpoint:</span></span>

:::image type="complex" source="../media/sources-panes-narrow-layout.msft.png" alt-text="狭いレイアウトの [ソース] ツールのウィンドウ" lightbox="../media/sources-panes-narrow-layout.msft.png":::
   <span data-ttu-id="49708-125">狭いレイアウトの [ソース] ツールのウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-125">The panes of the Sources tool, in narrow layout</span></span>  
:::image-end:::  

<span data-ttu-id="49708-126">DevTools が広い場合\*\*\*\*、デバッガー ウィンドウは右側に配置され **、Scope**と Watch が含**まれます**。</span><span class="sxs-lookup"><span data-stu-id="49708-126">When DevTools is wide, the **Debugger** pane is placed on the right, and includes **Scope** and **Watch**:</span></span>  

:::image type="complex" source="../media/sources-panes-wide-layout.msft.png" alt-text="サーバーから返される JavaScript の移動、表示、編集、デバッグ" lightbox="../media/sources-panes-wide-layout.msft.png":::
   <span data-ttu-id="49708-128">サーバーから返される JavaScript の移動、表示、編集、デバッグ</span><span class="sxs-lookup"><span data-stu-id="49708-128">Navigate, view, edit, and debug JavaScript returned by the server</span></span>  
:::image-end:::  

<span data-ttu-id="49708-129">Sources ツールのサイズを最大化するには、DevTools を別のウィンドウにドッキング解除し、必要に応じて DevTools ウィンドウを別のモニターに移動します。</span><span class="sxs-lookup"><span data-stu-id="49708-129">To maximize the size of the Sources tool, undock DevTools into a separate window, and optionally move the DevTools window to a separate monitor.</span></span>  <span data-ttu-id="49708-130">「Change [Microsoft Edge DevTools プレースメント (Undock、Dock to bottom、Dock to left)」を参照してください][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="49708-130">See [Change Microsoft Edge DevTools placement (Undock, Dock to bottom, Dock to left)][DevToolsCustomizePlacement].</span></span>

<span data-ttu-id="49708-131">上記のデバッグ デモ Web ページを読み込むには、以下の「デバッガーを使用 [する基本的な方法」を](#the-basic-approach-to-using-a-debugger)参照してください。</span><span class="sxs-lookup"><span data-stu-id="49708-131">To load the debugging demo webpage that's shown above, see [The basic approach to using a debugger](#the-basic-approach-to-using-a-debugger), below.</span></span>

## <a name="using-the-navigator-pane-to-select-files"></a><span data-ttu-id="49708-132">[ナビゲーター] ウィンドウを使用してファイルを選択する</span><span class="sxs-lookup"><span data-stu-id="49708-132">Using the Navigator pane to select files</span></span>

<span data-ttu-id="49708-133">サーバーから **返** されるリソース間を移動して現在の Web ページを作成するには、ナビゲーター ウィンドウ \(左側\) を使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-133">Use the **Navigator** pane \(on the left\) to navigate among the resources that are returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="49708-134">ファイル、画像、その他のリソースを選択し、そのパスを表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-134">Select files, images, and other resources, and view their paths.</span></span>  

:::image type="complex" source="../media/navigator-pane.msft.png" alt-text="[ナビゲーター] ウィンドウ" lightbox="../media/navigator-pane.msft.png":::
   <span data-ttu-id="49708-136">[ **ナビゲーター]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-136">The **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="49708-137">ナビゲーター ウィンドウの非表示のタブにアクセスするには、[その他の ![ タブ ](../media/more-tabs-icon.msft.png) ] \( [**その他のタブ**] \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-137">To access any hidden tabs of the Navigator pane, select ![More tabs](../media/more-tabs-icon.msft.png) \(**More tabs**\).</span></span>

<span data-ttu-id="49708-138">次のサブセクションでは、ナビゲーター ウィンドウについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49708-138">The following subsections cover the Navigator pane:</span></span>  

*   [<span data-ttu-id="49708-139">[ページ] タブを使用して、現在の Web ページを作成するリソースを確認する</span><span class="sxs-lookup"><span data-stu-id="49708-139">Using the Page tab to explore resources that construct the current webpage</span></span>](#using-the-page-tab-to-explore-resources-that-construct-the-current-webpage)  
*   [<span data-ttu-id="49708-140">[ファイルシステム] タブを使用してローカル ワークスペースを定義する</span><span class="sxs-lookup"><span data-stu-id="49708-140">Using the Filesystem tab to define a local Workspace</span></span>](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [<span data-ttu-id="49708-141">[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする</span><span class="sxs-lookup"><span data-stu-id="49708-141">Using the Overrides tab to override server files with local files</span></span>](#using-the-overrides-tab-to-override-server-files-with-local-files)  
*   [<span data-ttu-id="49708-142">拡張機能の [コンテンツ スクリプト] タブMicrosoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="49708-142">Using the Content scripts tab for Microsoft Edge extensions</span></span>](#using-the-content-scripts-tab-for-microsoft-edge-extensions)  
*   [<span data-ttu-id="49708-143">[スニペット] タブを使用して任意のページで JavaScript コード スニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="49708-143">Using the Snippets tab to run JavaScript code snippets on any page</span></span>](#using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage)  
*   [<span data-ttu-id="49708-144">コマンド メニューを使用してファイルを開く</span><span class="sxs-lookup"><span data-stu-id="49708-144">Using the Command Menu to open files</span></span>](#using-the-command-menu-to-open-files)  
    
### <a name="using-the-page-tab-to-explore-resources-that-construct-the-current-webpage"></a><span data-ttu-id="49708-145">[ページ] タブを使用して、現在の Web ページを作成するリソースを確認する</span><span class="sxs-lookup"><span data-stu-id="49708-145">Using the Page tab to explore resources that construct the current webpage</span></span>

<span data-ttu-id="49708-146">[ナビゲーター] **ウィンドウの** [ **ページ** ] タブを使用して、サーバーから返されるファイル システムを探索して、現在の Web ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="49708-146">Use the **Page** tab of the **Navigator** pane to explore the file system that's returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="49708-147">JavaScript ファイルを選択して、表示、編集、およびデバッグします。</span><span class="sxs-lookup"><span data-stu-id="49708-147">Select a JavaScript file to view, edit, and debug it.</span></span>  <span data-ttu-id="49708-148">[ **ページ]** タブには、ページが読み込まれたすべてのリソースが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-148">The **Page** tab lists all of the resources that the page has loaded.</span></span>

:::image type="complex" source="../media/sources-page-tab.msft.png" alt-text="[ソース] ツールの [ナビゲーター] ウィンドウの [ページ] タブ" lightbox="../media/sources-page-tab.msft.png":::
   <span data-ttu-id="49708-150">[**ソース]** ツールの **[ナビゲーター** ] ウィンドウの **[ページ] タブ**</span><span class="sxs-lookup"><span data-stu-id="49708-150">The **Page** tab in the **Navigator** pane of the **Sources** tool</span></span>
:::image-end:::  

<span data-ttu-id="49708-151">[エディター] ウィンドウにファイル **を表示するには** 、[ページ] タブでファイル **を選択** します。 イメージの場合、イメージのプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-151">To display a file in the **Editor** pane, select a file in the **Page** tab.  For an image, a preview of the image is displayed.</span></span>  
<span data-ttu-id="49708-152">リソースの URL またはパスを表示するには、リソースの上にマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="49708-152">To display the URL or path for a resource, hover over the resource.</span></span>  
<span data-ttu-id="49708-153">ブラウザーの新しいタブにファイルを読み込む場合、または他のアクションを表示するには、ファイル名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="49708-153">To load a file into a new tab of the browser, or to display other actions, right-click on the file name.</span></span>  

#### <a name="icons-in-the-page-tab"></a><span data-ttu-id="49708-154">[ページ] タブのアイコン</span><span class="sxs-lookup"><span data-stu-id="49708-154">Icons in the Page tab</span></span>

<span data-ttu-id="49708-155">[ **ページ] タブ** には、次のアイコンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="49708-155">The **Page** tab uses the following icons:</span></span>  

*   <span data-ttu-id="49708-156">ウィンドウ **アイコン** とラベルは、HTML フレームであるメイン ドキュメント フレーム `top` を [表します][W3CHtml4Frames]。</span><span class="sxs-lookup"><span data-stu-id="49708-156">The **window** icon, along with the label `top`, represents the main document frame, which is an [HTML frame][W3CHtml4Frames].</span></span>  
*   <span data-ttu-id="49708-157">クラウド **アイコンは** 原点を [表します][WhatwgHtmlSpecMulitpageOriginHtmlOrigin]。</span><span class="sxs-lookup"><span data-stu-id="49708-157">The **cloud** icon represents an [origin][WhatwgHtmlSpecMulitpageOriginHtmlOrigin].</span></span>  
*   <span data-ttu-id="49708-158">フォルダー **アイコンは** 、ディレクトリを表します。</span><span class="sxs-lookup"><span data-stu-id="49708-158">The **folder** icon represents a directory.</span></span>  
*   <span data-ttu-id="49708-159">ページ **アイコンは** リソースを表します。</span><span class="sxs-lookup"><span data-stu-id="49708-159">The **page** icon represents a resource.</span></span>  
    
#### <a name="group-files-by-folder-or-as-a-flat-list"></a><span data-ttu-id="49708-160">フォルダーまたはフラット リストとしてファイルをグループ化する</span><span class="sxs-lookup"><span data-stu-id="49708-160">Group files by folder or as a flat list</span></span>

<span data-ttu-id="49708-161">[ **ページ]** タブには、サーバーとディレクトリ、またはフラット リストでグループ化されたファイルまたはリソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-161">The **Page** tab displays files or resources grouped by server and directory, or as a flat list.</span></span>

<span data-ttu-id="49708-162">リソースのグループ化方法を変更するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-162">To change how resources are grouped:</span></span>

1.  <span data-ttu-id="49708-163">[ナビゲーター] ウィンドウ \(左\) のタブの横にある **... \(** More options \) ボタン**を**選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-163">Next to the tabs on the Navigator pane \(on the left\), select the **...** \(**More options**\) button.</span></span>  <span data-ttu-id="49708-164">メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-164">A menu appears.</span></span>  
1.  <span data-ttu-id="49708-165">[フォルダー別にグループ化 **] オプションを選択またはオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="49708-165">Select or clear the **Group by folder** option.</span></span>  
    
### <a name="using-the-filesystem-tab-to-define-a-local-workspace"></a><span data-ttu-id="49708-166">[ファイルシステム] タブを使用してローカル ワークスペースを定義する</span><span class="sxs-lookup"><span data-stu-id="49708-166">Using the Filesystem tab to define a local Workspace</span></span>

<span data-ttu-id="49708-167">[ナビゲーター **] ウィンドウ** の [ **ファイルシステム** ] タブを使用して、ファイルをワークスペースに追加し、DevTools で行った変更をローカル ファイル システムに保存します。</span><span class="sxs-lookup"><span data-stu-id="49708-167">Use the **Filesystem** tab of the **Navigator** pane to add files to a Workspace, so that changes you make in DevTools get saved to your local file system.</span></span>  
<span data-ttu-id="49708-168">ワークスペース内のファイルは、DevTools 全体で、ファイル名の横に緑色のドットで示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-168">A file that's in a Workspace is indicated by a green dot next to the file name, throughout DevTools.</span></span>  

:::image type="complex" source="../media/sources-filesystem-tab.msft.png" alt-text="ワークスペースの [ファイル システム] タブ" lightbox="../media/sources-filesystem-tab.msft.png":::
   <span data-ttu-id="49708-170">ワークスペース **の** [ファイル システム] タブ</span><span class="sxs-lookup"><span data-stu-id="49708-170">The **Filesystem** tab, for a Workspace</span></span>
:::image-end:::  

<span data-ttu-id="49708-171">既定では、[ソース] ツールでファイルを\*\*\*\* 編集すると、Web ページを更新すると変更は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="49708-171">By default, when you edit a file in the **Sources** tool, your changes are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="49708-172">Sources **ツール** は、Web サーバーから返されるフロントエンド リソースのコピーを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-172">The **Sources** tool works with a copy of the front-end resources that are returned by the web server.</span></span>  <span data-ttu-id="49708-173">サーバーによって返されるこれらのフロントエンド ファイルを変更しても、ソース ファイルを変更しなかったため、変更は保持されません。</span><span class="sxs-lookup"><span data-stu-id="49708-173">When you modify these front-end files that are returned by the server, the changes don't persist, because you didn't change the source files.</span></span>  <span data-ttu-id="49708-174">また、実際のソース コードで編集内容を適用してから、サーバーに再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49708-174">You need to also apply your edits in your actual source code, and then re-deploy to the server.</span></span>  
<span data-ttu-id="49708-175">これに対し、Workspace を使用すると、Web ページを更新するときにフロントエンド コードに加えた変更は保持されます。</span><span class="sxs-lookup"><span data-stu-id="49708-175">In contrast, when you use a Workspace, changes that you make to your front-end code are preserved when you refresh the webpage.</span></span>  <span data-ttu-id="49708-176">Workspace では、サーバーから返されるフロントエンド コードを編集すると、ソース ツールによって編集内容がローカル ソース コードにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="49708-176">With a Workspace, when you edit the front-end code that's returned by the server, the Sources tool also applies your edits to your local source code.</span></span>  <span data-ttu-id="49708-177">その後、他のユーザーが変更を確認するには、変更されたソース ファイルのみをサーバーに再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49708-177">Then for other users to see your changes, you only need to redeploy your changed source files to the server.</span></span>  
<span data-ttu-id="49708-178">サーバーから返される JavaScript コードがローカルの JavaScript ソース コードと同じ場合、ワークスペースは適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="49708-178">Workspaces work well when the JavaScript code that's returned by the server is the same as your local JavaScript source code.</span></span>  <span data-ttu-id="49708-179">ワークスペースは、ワークフローがソース コードの変換 (minification や [TypeScript][TypescriptlangMain] のコンパイルなど) を伴う場合にも機能しません。</span><span class="sxs-lookup"><span data-stu-id="49708-179">Workspaces don't work as well when your workflow involves transformations on your source code, such as minification or [TypeScript][TypescriptlangMain] compilation.</span></span>  

<span data-ttu-id="49708-180">詳細については、「Workspaces を使用してファイル [を編集する」のチュートリアルを参照してください][DevtoolsGuideChromiumWorkspacesIndex]。</span><span class="sxs-lookup"><span data-stu-id="49708-180">For more information, see the tutorial [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex].</span></span>

### <a name="using-the-overrides-tab-to-override-server-files-with-local-files"></a><span data-ttu-id="49708-181">[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする</span><span class="sxs-lookup"><span data-stu-id="49708-181">Using the Overrides tab to override server files with local files</span></span>

<span data-ttu-id="49708-182">[ナビゲーター] **ウィンドウの** [上書 **き]** タブを使用して、ローカル フォルダーのファイルでページアセット \(images\など) を上書きします。</span><span class="sxs-lookup"><span data-stu-id="49708-182">Use the **Overrides** tab of the **Navigator** pane to override page assets \(such as images\) with files from a local folder.</span></span>  
<span data-ttu-id="49708-183">このタブのアイテムは、サーバーがアセットを送信した後でも、サーバーがブラウザーに送信する処理を上書きします。</span><span class="sxs-lookup"><span data-stu-id="49708-183">Items in this tab override what the server sends to the browser, even after the server has sent the assets.</span></span>  

:::image type="complex" source="../media/overrides-tab.msft.png" alt-text="ナビゲーター ウィンドウの [オーバーライド] タブ" lightbox="../media/overrides-tab.msft.png":::
   <span data-ttu-id="49708-185">ナビゲーター**ウィンドウの**[オーバーライド]**タブ**</span><span class="sxs-lookup"><span data-stu-id="49708-185">The **Overrides** tab of the **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="49708-186">オーバーライド **機能は** ワークスペースに似ています。</span><span class="sxs-lookup"><span data-stu-id="49708-186">The **Overrides** feature is similar to Workspaces.</span></span>  <span data-ttu-id="49708-187">Web ページの変更を試し、Web ページを更新した後も変更を保持する必要があるが、変更を Web ページのソース コードにマッピングする場合は、オーバーライドを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-187">Use Overrides when you want to experiment with changes to a webpage, and you need to keep the changes after you refresh the webpage, but you don't care about mapping your changes to the source code of the webpage.</span></span>  

<span data-ttu-id="49708-188">サーバーによって返されるファイルを上書きするファイルは、DevTools 全体で、ファイル名の横に紫色のドットで示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-188">A file that overrides a file that is returned by the server is indicated by a purple dot next to the file name, throughout DevTools.</span></span>

#### <a name="see-also"></a><span data-ttu-id="49708-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="49708-189">See also</span></span>

*   [<span data-ttu-id="49708-190">DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="49708-190">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>][DevtoolsJavascriptOverrides]  
*   [<span data-ttu-id="49708-191">前処理されたコードをソース コードにマップする</span><span class="sxs-lookup"><span data-stu-id="49708-191">Map preprocessed code to source code</span></span>][DevToolsJavaScriptSourceMaps]  
    
### <a name="using-the-content-scripts-tab-for-microsoft-edge-extensions"></a><span data-ttu-id="49708-192">拡張機能の [コンテンツ スクリプト] タブMicrosoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="49708-192">Using the Content scripts tab for Microsoft Edge extensions</span></span>

<span data-ttu-id="49708-193">ナビゲーター ウィンドウ**の [コンテンツ スクリプト**] タブを使用して、インストールした拡張機能によって読み込まれたMicrosoft Edgeを表示します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="49708-193">Use the **Content scripts** tab of the **Navigator** pane to view any content scripts that were loaded by a Microsoft Edge extension that you installed.</span></span>  

:::image type="complex" source="../media/content-scripts-tab.msft.png" alt-text="ナビゲーター ウィンドウの [コンテンツ スクリプト] タブ" lightbox="../media/content-scripts-tab.msft.png":::
   <span data-ttu-id="49708-195">ナビゲーター**ウィンドウの**[コンテンツ スクリプト **] タブ**</span><span class="sxs-lookup"><span data-stu-id="49708-195">The **Content scripts** tab of the **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="49708-196">デバッガーが認識しないコードにステップ インすると、そのコードをライブラリ コードとしてマークして、そのコードにステップ インしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="49708-196">When the debugger steps into code that you don't recognize, you might want to mark that code as Library code, to avoid stepping into that code.</span></span>  <span data-ttu-id="49708-197">「 [コンテンツ スクリプトをライブラリ コードとしてマークする」を参照してください][DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]。</span><span class="sxs-lookup"><span data-stu-id="49708-197">See [Mark content scripts as Library code][DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode].</span></span>

#### <a name="see-also"></a><span data-ttu-id="49708-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="49708-198">See also</span></span>

*   [<span data-ttu-id="49708-199">コンテンツ スクリプト</span><span class="sxs-lookup"><span data-stu-id="49708-199">Content scripts</span></span>][MdnAddOnsWebextensionsContentScripts]  
*   [<span data-ttu-id="49708-200">拡張機能のチュートリアルを作成する パート 2</span><span class="sxs-lookup"><span data-stu-id="49708-200">Create an extension tutorial Part 2</span></span>][ExtensionsChromiumGetstartPart2ContentScripts]  
    
### <a name="using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage"></a><span data-ttu-id="49708-201">[スニペット] タブを使用して任意の Web ページで JavaScript コード スニペットを実行する</span><span class="sxs-lookup"><span data-stu-id="49708-201">Using the Snippets tab to run JavaScript code snippets on any webpage</span></span>

<span data-ttu-id="49708-202">任意の **Web ページで** これらのスニペットを簡単に実行できるよう、 **ナビゲーター** ウィンドウの [スニペット] タブを使用して JavaScript コード スニペットを作成および保存します。</span><span class="sxs-lookup"><span data-stu-id="49708-202">Use the **Snippets** tab of the **Navigator** pane to create and save JavaScript code snippets, so that you can easily run these snippets on any webpage.</span></span>

:::image type="complex" source="../media/snippet.msft.png" alt-text="web ページに jQuery ライブラリを挿入するスニペット" lightbox="../media/snippet.msft.png":::
   <span data-ttu-id="49708-204">web ページに jQuery ライブラリを挿入するスニペット</span><span class="sxs-lookup"><span data-stu-id="49708-204">A Snippet that inserts the jQuery library into a webpage</span></span>  
:::image-end:::  

<span data-ttu-id="49708-205">たとえば、コンソールで次のコードを頻繁に入力して、jQuery ライブラリをページに挿入して、コンソールから jQuery コマンドを実行できると**します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="49708-205">For example, suppose you frequently enter the following code in the **Console**, to insert the jQuery library into a page so that you can run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="49708-206">代わりに、このコードをスニペットに保存し\*\*\*\*、必要なときにいつでも簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="49708-206">Instead, you can save this code in a **Snippet** and then easily run it whenever you need to.</span></span>  <span data-ttu-id="49708-207">`Ctrl` + `S` \(Windows/Linux\) または `Command` + `S` \(macOS\) を選択すると、DevTools\*\*\*\* はスニペットをファイル システムに保存します。</span><span class="sxs-lookup"><span data-stu-id="49708-207">When you select `Ctrl`+`S` \(Windows/Linux\) or `Command`+`S` \(macOS\), DevTools saves the **Snippet** to your file system.</span></span>  

<span data-ttu-id="49708-208">スニペットを実行する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="49708-208">There are multiple ways to run a Snippet:</span></span>  

*   <span data-ttu-id="49708-209">[ナビゲーター **] ウィンドウ** で、[スニペット] **タブを** 選択し、スニペット ファイルを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="49708-209">In the **Navigator** pane, select the **Snippets** tab, and then select the snippets file to open it.</span></span>  <span data-ttu-id="49708-210">次に、[エディター] ウィンドウの下部にある [ **実行** ] \( [実行] ![ ボタン \) を ](../media/run-snippet-icon.msft.png) 選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-210">Then at the bottom of the Editor pane, select **Run** \(![The Run button](../media/run-snippet-icon.msft.png)\).</span></span>  
*   <span data-ttu-id="49708-211">DevTools にフォーカスがある場合は `Ctrl` + `P` 、[\(Windows/Linux\) または `Command` + `P` [][DevToolsCommandMenuIndex]\(macOS\) `!` を選択してコマンド メニューを開き、 と入力します。</span><span class="sxs-lookup"><span data-stu-id="49708-211">When DevTools has focus, select `Ctrl`+`P` \(Windows/Linux\) or `Command`+`P` \(macOS\) to open the [Command Menu][DevToolsCommandMenuIndex], and then type `!`.</span></span>  
    
<span data-ttu-id="49708-212">スニペット は bookmarklets に似ています。</span><span class="sxs-lookup"><span data-stu-id="49708-212">Snippets are similar to bookmarklets.</span></span>

#### <a name="see-also"></a><span data-ttu-id="49708-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="49708-213">See also</span></span>

*   [<span data-ttu-id="49708-214">DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行する</span><span class="sxs-lookup"><span data-stu-id="49708-214">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>][DevtoolsGuideChromiumJavascriptSnippets]  
    
### <a name="using-the-command-menu-to-open-files"></a><span data-ttu-id="49708-215">コマンド メニューを使用してファイルを開く</span><span class="sxs-lookup"><span data-stu-id="49708-215">Using the Command Menu to open files</span></span>

<span data-ttu-id="49708-216">ファイルを開く場合は、[ソース]\*\*\*\* ツール内の\*\*\*\*[ナビゲーター] ウィンドウを使用する以外に、DevTools 内の任意の場所からコマンド メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49708-216">To open a file, in addition to using the **Navigator** pane within the **Sources** tool, you can use the Command Menu from anywhere within DevTools.</span></span>

*   <span data-ttu-id="49708-217">DevTools の任意の場所から、Windows/Linux または `Ctrl` + `P` `Command` + `P` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-217">From anywhere in DevTools, select `Ctrl`+`P` on Windows/Linux or `Command`+`P` on macOS.</span></span>  <span data-ttu-id="49708-218">[コマンド] メニューが表示され、[ソース] ツールの [ナビゲーター]\*\*\*\* ウィンドウのタブにあるすべてのリソース**が一覧表示**されます。</span><span class="sxs-lookup"><span data-stu-id="49708-218">The Command Menu appears, and lists all the resources that are in the tabs of the **Navigator** pane of the **Sources** tool.</span></span>  
*   <span data-ttu-id="49708-219">または、[ソース] ツールの\*\*\*\*[ナビゲーター]\*\*\*\* ウィンドウのタブの横にある **...** \(**More options**\) ボタンを選択し、[ファイルを開く]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-219">Or, next to the tabs of the **Navigator** pane in the **Sources** tool, select the **...** \(**More options**\) button, and then select **Open File**.</span></span>  

<span data-ttu-id="49708-220">すべてのファイルの一覧を表示して選択するには.jsを入力します `.js` 。</span><span class="sxs-lookup"><span data-stu-id="49708-220">To display and pick from a list of all .js files, type `.js`.</span></span>

:::image type="complex" source="../media/sources-command-menu-to-open-file.msft.png" alt-text="コマンド メニューを使用してファイルを開く" lightbox="../media/sources-command-menu-to-open-file.msft.png":::
   <span data-ttu-id="49708-222">コマンド メニューを使用してファイルを開く</span><span class="sxs-lookup"><span data-stu-id="49708-222">Opening a file by using the Command Menu</span></span>
:::image-end:::

<span data-ttu-id="49708-223">入力した場合、 `?` コマンド メニューには 、..を含むいくつかのコマンド **が表示されます。 ファイルを開きます**。</span><span class="sxs-lookup"><span data-stu-id="49708-223">If you type `?`, the Command Menu shows several commands, including **...  Open file**.</span></span>  <span data-ttu-id="49708-224">コマンド メニューを `Backspace` オフにした場合は、ファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-224">If you select `Backspace` to clear the Command Menu, a list of files is shown.</span></span>

<span data-ttu-id="49708-225">詳細については[、「DevTools コマンド メニューを使用してコマンドMicrosoft Edge実行する」を参照してください][DevToolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="49708-225">For more information, see [Run commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex].</span></span>

## <a name="using-the-editor-pane-to-view-or-edit-files"></a><span data-ttu-id="49708-226">[エディター] ウィンドウを使用してファイルを表示または編集する</span><span class="sxs-lookup"><span data-stu-id="49708-226">Using the Editor pane to view or edit files</span></span>

<span data-ttu-id="49708-227">[エディター **] ウィンドウ** を使用して、サーバーから返されるフロントエンド ファイルを表示して、JavaScript、HTML、CSS、イメージ ファイルなどの現在の Web ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="49708-227">Use the **Editor** pane to view the front-end files that are returned from the server to compose the current webpage, including JavaScript, HTML, CSS, and image files.</span></span>  <span data-ttu-id="49708-228">エディター ウィンドウでフロントエンド ファイルを編集すると\*\*\*\*、DevTools によって Web ページが更新され、変更されたコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="49708-228">When you edit the front-end files in the **Editor** pane, DevTools updates the webpage to run the modified code.</span></span>  

:::image type="complex" source="../media/editor-pane.msft.png" alt-text="[ソース] ツールの [エディター] ウィンドウ" lightbox="../media/editor-pane.msft.png":::
   <span data-ttu-id="49708-230">[ **ソース** ] ツールの **[エディター]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="49708-230">The **Editor** pane in the **Sources** tool</span></span>  
:::image-end:::

<span data-ttu-id="49708-231">[ **エディター]** ウィンドウには、さまざまな種類のファイルに対する次のレベルのサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="49708-231">The **Editor** pane has the following level of support for various file types:</span></span>  

| <span data-ttu-id="49708-232">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="49708-232">File Type</span></span> | <span data-ttu-id="49708-233">サポートされているアクション</span><span class="sxs-lookup"><span data-stu-id="49708-233">Supported Actions</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="49708-234">JavaScript</span><span class="sxs-lookup"><span data-stu-id="49708-234">JavaScript</span></span> | <span data-ttu-id="49708-235">表示、編集、デバッグを行います。</span><span class="sxs-lookup"><span data-stu-id="49708-235">View, edit, and debug.</span></span>  |  
| <span data-ttu-id="49708-236">CSS</span><span class="sxs-lookup"><span data-stu-id="49708-236">CSS</span></span> | <span data-ttu-id="49708-237">表示と編集。</span><span class="sxs-lookup"><span data-stu-id="49708-237">View and edit.</span></span>  |  
| <span data-ttu-id="49708-238">HTML</span><span class="sxs-lookup"><span data-stu-id="49708-238">HTML</span></span> | <span data-ttu-id="49708-239">表示と編集。</span><span class="sxs-lookup"><span data-stu-id="49708-239">View and edit.</span></span>  |  
| <span data-ttu-id="49708-240">画像</span><span class="sxs-lookup"><span data-stu-id="49708-240">Images</span></span> | <span data-ttu-id="49708-241">[表示] を選びます。</span><span class="sxs-lookup"><span data-stu-id="49708-241">View.</span></span>  |  

<span data-ttu-id="49708-242">既定では、Web ページを更新すると編集は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="49708-242">By default, edits are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="49708-243">変更をファイル システムに保存する方法については、上記の「Using the Filesystem tab to define a local [Workspace」を参照](#using-the-filesystem-tab-to-define-a-local-workspace)してください。</span><span class="sxs-lookup"><span data-stu-id="49708-243">For information about how to save the changes to your file system, see [Using the Filesystem tab to define a local Workspace](#using-the-filesystem-tab-to-define-a-local-workspace), above.</span></span>

<span data-ttu-id="49708-244">次のサブセクションでは、[エディター] ウィンドウについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49708-244">The following subsections cover the Editor pane:</span></span>  

*   [<span data-ttu-id="49708-245">JavaScript ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-245">Editing a JavaScript file</span></span>](#editing-a-javascript-file)  
*   [<span data-ttu-id="49708-246">美しい印刷を使用して、Minified JavaScript ファイルを再フォーマットする</span><span class="sxs-lookup"><span data-stu-id="49708-246">Reformatting a minified JavaScript file with pretty-print</span></span>](#reformatting-a-minified-javascript-file-with-pretty-print)  
*   [<span data-ttu-id="49708-247">読み取り可能なコードを表示するソース コードへのマイニング コードのマッピング</span><span class="sxs-lookup"><span data-stu-id="49708-247">Mapping minified code to your source code to show readable code</span></span>](#mapping-minified-code-to-your-source-code-to-show-readable-code)  
*   [<span data-ttu-id="49708-248">ソース コードからコンパイル済みのフロントエンド コードへの変換</span><span class="sxs-lookup"><span data-stu-id="49708-248">Transformations from source code to compiled front-end code</span></span>](#transformations-from-source-code-to-compiled-front-end-code)  
*   [<span data-ttu-id="49708-249">CSS ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-249">Editing a CSS file</span></span>](#editing-a-css-file)  
*   [<span data-ttu-id="49708-250">HTML ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-250">Editing an HTML file</span></span>](#editing-an-html-file)  
*   [<span data-ttu-id="49708-251">行番号または関数にアクセスする</span><span class="sxs-lookup"><span data-stu-id="49708-251">Going to a line number or function</span></span>](#going-to-a-line-number-or-function)  
*   [<span data-ttu-id="49708-252">別のツールを使用する場合のソース ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="49708-252">Displaying source files when using a different tool</span></span>](#displaying-source-files-when-using-a-different-tool)  
    
### <a name="editing-a-javascript-file"></a><span data-ttu-id="49708-253">JavaScript ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-253">Editing a JavaScript file</span></span>

<span data-ttu-id="49708-254">DevTools で JavaScript ファイルを編集するには、[ソース] ツール **内の [** エディター] **ウィンドウを使用** します。</span><span class="sxs-lookup"><span data-stu-id="49708-254">To edit a JavaScript file in DevTools, use the **Editor** pane, within the **Sources** tool.</span></span>

:::image type="complex" source="../media/editing-js-in-editor-pane.msft.png" alt-text="[エディター] ウィンドウでの JavaScript の編集" lightbox="../media/editing-js-in-editor-pane.msft.png":::
   <span data-ttu-id="49708-256">[ **エディター** ] ウィンドウでの JavaScript の編集</span><span class="sxs-lookup"><span data-stu-id="49708-256">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::

<span data-ttu-id="49708-257">ファイルをエディター ウィンドウに読み込むには\*\*\*\*、ナビゲーター ウィンドウ\*\*\*\* \(左側\) の [ページ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-257">To load a file into the Editor pane, use the **Page** tab in the **Navigator** pane \(on the left\).</span></span>  <span data-ttu-id="49708-258">または、 **次のようにコマンド**メニューを使用します。DevTools の右上隅で **、[DevTools** \( \) のカスタマイズと制御] を選択し、[ファイルを開く] を `...` **選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-258">Or use the **Command Menu**, as follows: in the upper right of DevTools, select **Customize and control DevTools** \(`...`\) and then select **Open File**.</span></span>

#### <a name="save-and-undo"></a><span data-ttu-id="49708-259">保存と元に戻す</span><span class="sxs-lookup"><span data-stu-id="49708-259">Save and Undo</span></span>

<span data-ttu-id="49708-260">JavaScript の変更を有効にするには`Ctrl`+`S` [\(Windows, Linux\)] または`Command`+`S` [\(macOS\)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-260">For JavaScript changes to take effect, select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\).</span></span>  

<span data-ttu-id="49708-261">ファイルを変更すると、ファイル名の横にアスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-261">If you change a file, an asterisk appears next to the file name.</span></span>  

*   <span data-ttu-id="49708-262">変更を保存するには、Windows/Linux または `Ctrl` + `S` `Command` + `S` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-262">To save changes, select `Ctrl`+`S` on Windows/Linux or `Command`+`S` on macOS.</span></span>  
*   <span data-ttu-id="49708-263">変更を元に戻すには、Windows/Linux または `Ctrl` + `Z` `Command` + `Z` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-263">To undo a change, select `Ctrl`+`Z` on Windows/Linux or `Command`+`Z` on macOS.</span></span>  
    
<span data-ttu-id="49708-264">既定では、Web ページを更新すると編集内容は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="49708-264">By default, your edits are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="49708-265">ローカル ファイル システムに変更を保存する方法の詳細については、「Workspaces を使用してファイルを編集する [」を参照してください][DevtoolsGuideChromiumWorkspacesIndex]。</span><span class="sxs-lookup"><span data-stu-id="49708-265">For more information about how to save the changes in your local file system, see [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex].</span></span>

#### <a name="find-and-replace"></a><span data-ttu-id="49708-266">検索と置換</span><span class="sxs-lookup"><span data-stu-id="49708-266">Find and Replace</span></span>

<span data-ttu-id="49708-267">現在のファイル内のテキストを検索するには、[\*\*\*\* エディター] ウィンドウを選択してフォーカスを設定し `Ctrl` + `F` 、Windows/Linux、 `Command` + `F` または macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-267">To find text in the current file, select the **Editor** pane to give it focus, and then select `Ctrl`+`F` on Windows/Linux, or `Command`+`F` on macOS.</span></span>  

:::image type="complex" source="../media/find-replace.msft.png" alt-text="検索と置換(Sources ツールのエディター ウィンドウ)" lightbox="../media/find-replace.msft.png":::
   <span data-ttu-id="49708-269">**検索**と**置換**、ソース ツール**の**エディター**ウィンドウで**</span><span class="sxs-lookup"><span data-stu-id="49708-269">**Find** and **Replace**, in the **Editor** pane of the **Sources** tool</span></span>
:::image-end:::

<span data-ttu-id="49708-270">テキストを検索して置き換える\*\*\*\* 場合は、[検索] テキスト ボックスの左側にある **[\( A-\>B**\) の置換] ボタン**を**選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-270">To find and replace text, select the **Replace** \(**A-\>B**\) button to the left of the **Find** textbox.</span></span>  <span data-ttu-id="49708-271">編集可能 **な** ファイルを表示**すると、[\( A-\>B**\) を置き換える] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-271">The **Replace** \(**A-\>B**\) button appears when viewing an editable file.</span></span>

#### <a name="showing-the-changes-you-made"></a><span data-ttu-id="49708-272">行った変更の表示</span><span class="sxs-lookup"><span data-stu-id="49708-272">Showing the changes you made</span></span>

<span data-ttu-id="49708-273">ファイルに加えた変更を確認するには、[エディター] ウィンドウで右\*\*\*\* クリックし、[ローカル変更]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-273">To review the changes you made to a file, right-click in the **Editor** pane and then select **Local Modifications**.</span></span>

<span data-ttu-id="49708-274">**DevTools**の下部にドロワーが開き、[変更] タブに変更が**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="49708-274">The **Drawer** opens at the bottom of DevTools, showing your changes within the **Changes** tab.</span></span>

:::image type="complex" source="../media/local-modifications.msft.png" alt-text="ドロワーの [変更] タブでローカル変更を表示する" lightbox="../media/local-modifications.msft.png":::
   <span data-ttu-id="49708-276">ドロワー **の [** 変更] タブ **で** 、ローカル変更を表示 **する**</span><span class="sxs-lookup"><span data-stu-id="49708-276">Showing **Local Modifications**, in the **Changes** tab of the **Drawer**</span></span>
:::image-end:::

#### <a name="changes-inside-a-function-take-effect"></a><span data-ttu-id="49708-277">関数内の変更が有効</span><span class="sxs-lookup"><span data-stu-id="49708-277">Changes inside a function take effect</span></span>

<span data-ttu-id="49708-278">DevTools はスクリプトを再実行しないので、有効な JavaScript の変更は、関数内で行う変更のみです。</span><span class="sxs-lookup"><span data-stu-id="49708-278">DevTools doesn't re-run a script, so the only JavaScript changes that take effect are changes that you make within functions.</span></span>  <span data-ttu-id="49708-279">たとえば、次の図では、サーバーによって返される JavaScript に次のコードを追加しました。</span><span class="sxs-lookup"><span data-stu-id="49708-279">For example, in the following figure, we added the following code to the JavaScript that is returned by the server:</span></span>  
*   <span data-ttu-id="49708-280">任意の関数の外部に `console.log('A')` ステートメントを追加しました。</span><span class="sxs-lookup"><span data-stu-id="49708-280">We added the statement `console.log('A')` outside of any function.</span></span>  
*   <span data-ttu-id="49708-281">関数内にステートメント `console.log('B')` を追加 `onClick` しました。</span><span class="sxs-lookup"><span data-stu-id="49708-281">We added the statement `console.log('B')` inside an `onClick` function.</span></span>  
<span data-ttu-id="49708-282">その後、変更を保存し、フォームに番号を入力し、フォームを送信するフォーム ボタンを選択しました。</span><span class="sxs-lookup"><span data-stu-id="49708-282">We then saved the changes, entered numbers into the form, and then selected the form button to send the form.</span></span>  

<span data-ttu-id="49708-283">グローバル スコープにあるフォームを送信した後は実行されませんが、関数内で実行され、コンソール `console.log('A')` `console.log('B')` `onClick` `B` に出力されます。</span><span class="sxs-lookup"><span data-stu-id="49708-283">After submitting the form, `console.log('A')`, which is at global scope, doesn't run, but `console.log('B')`, inside an `onClick` function, does run, outputting `B` to the Console:</span></span>

:::image type="complex" source="../media/edit-js.msft.png" alt-text="グローバル スコープの JavaScript が再実行されない" lightbox="../media/edit-js.msft.png":::
   <span data-ttu-id="49708-285">グローバル スコープの JavaScript が再実行されない</span><span class="sxs-lookup"><span data-stu-id="49708-285">Global-scope JavaScript is not re-run</span></span>  
:::image-end:::

### <a name="reformatting-a-minified-javascript-file-with-pretty-print"></a><span data-ttu-id="49708-286">美しい印刷を使用して、Minified JavaScript ファイルを再フォーマットする</span><span class="sxs-lookup"><span data-stu-id="49708-286">Reformatting a minified JavaScript file with pretty-print</span></span>

<span data-ttu-id="49708-287">ファイルを読み取り可能な形式に変更するには、[エディター] ウィンドウの\*\*\*\* 下部に中かっことして表示される [プリティ印刷] ボタン \( ![ Format \) を選択します。 ](../media/format-icon.msft.png)</span><span class="sxs-lookup"><span data-stu-id="49708-287">To use pretty-print to reformat a file to make it readable, select the **Pretty print** button \(![Format](../media/format-icon.msft.png)\), which is shown as braces, at the bottom of the Editor pane.</span></span>  <span data-ttu-id="49708-288">または、[エディター] **ウィンドウの** 上部に [印刷] ボタンが表示されている場合は、そのボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="49708-288">Or, if a **Pretty-print** button appears at the top of the Editor pane, you can select that button.</span></span>

:::image type="complex" source="../media/minified.msft.png" alt-text="[プリティ印刷] ボタン" lightbox="../media/minified.msft.png":::
   <span data-ttu-id="49708-290">[ **プリティ印刷]** ボタン</span><span class="sxs-lookup"><span data-stu-id="49708-290">The **Pretty print** button</span></span>  
:::image-end:::  

<span data-ttu-id="49708-291">再フォーマットされたファイルが新しいタブに表示され、ファイル `:formatted` 名に追加されます。</span><span class="sxs-lookup"><span data-stu-id="49708-291">The reformatted file appears in a new tab, with `:formatted` appended to the file name.</span></span>  <span data-ttu-id="49708-292">再フォーマットされたコードは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="49708-292">The reformatted code is read-only.</span></span>  

:::image type="complex" source="../media/pretty-printed.msft.png" alt-text="かなり印刷された (再フォーマットされた) JavaScript ファイル" lightbox="../media/pretty-printed.msft.png":::
   <span data-ttu-id="49708-294">かなり印刷された \(reformatted\) JavaScript ファイル</span><span class="sxs-lookup"><span data-stu-id="49708-294">A pretty-printed \(reformatted\) JavaScript file</span></span>  
:::image-end:::  

<span data-ttu-id="49708-295">再フォーマットされたファイルを、minified ファイルで選択したコードまでスクロールするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-295">To make the reformatted file scroll to the code that you select in the minified file:</span></span>  

1.  <span data-ttu-id="49708-296">[再フォーマットされたファイル] タブが開いている場合は、閉じます。</span><span class="sxs-lookup"><span data-stu-id="49708-296">If the reformatted file tab is open, close it.</span></span>  
1.  <span data-ttu-id="49708-297">[エディター] ウィンドウで、マイニング ファイル内のコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-297">Select some code in the minified file in the Editor pane.</span></span>
1.  <span data-ttu-id="49708-298">[きれいな印刷 **] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="49708-298">Select the **Pretty print** button.</span></span>  
     
<span data-ttu-id="49708-299">書式設定されたコードが新しいタブに表示され、選択したコードまでスクロールされます。</span><span class="sxs-lookup"><span data-stu-id="49708-299">The formatted code appears in a new tab, scrolled to the code that you selected.</span></span>

<span data-ttu-id="49708-300">詳細については、「美しい印刷 [を使用して、ミニマ化された JavaScript ファイルを再フォーマットする」を参照してください][DevToolsJavaScriptReferenceReformat]。</span><span class="sxs-lookup"><span data-stu-id="49708-300">For more information, see [Reformat a minified JavaScript file with pretty-print][DevToolsJavaScriptReferenceReformat].</span></span>  

### <a name="mapping-minified-code-to-your-source-code-to-show-readable-code"></a><span data-ttu-id="49708-301">読み取り可能なコードを表示するソース コードへのマイニング コードのマッピング</span><span class="sxs-lookup"><span data-stu-id="49708-301">Mapping minified code to your source code to show readable code</span></span>

<span data-ttu-id="49708-302">プリプロセッサからのソース マップを使用すると、DevTools は、サーバーによって返される、変換された、最小化された JavaScript ファイルに加えて、元の JavaScript ソース ファイルを読み込む原因になります。</span><span class="sxs-lookup"><span data-stu-id="49708-302">Source maps from preprocessors cause DevTools to load your original JavaScript source files in addition to your minified, transformed JavaScript files that are returned by the server.</span></span>  <span data-ttu-id="49708-303">次に、ブレークポイントを設定し、コードをステップ実行しながら、元のソース ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-303">You then view your original source files while you set breakpoints and step through code.</span></span>  <span data-ttu-id="49708-304">一方、Microsoft Edgeコードが実際に実行されています。</span><span class="sxs-lookup"><span data-stu-id="49708-304">Meanwhile, Microsoft Edge is actually running your minified code.</span></span>  

<span data-ttu-id="49708-305">[エディター **] ウィンドウ**で JavaScript ファイルを右クリックし、[ソース\*\*\*\* マップの追加] を選択すると、ポップアップ ボックスが表示され、[ソース マップ**URL]** テキスト ボックスと [追加] ボタンが**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="49708-305">In the **Editor** pane, if you right-click a JavaScript file and then select **Add source map**, a popup box appears, with a **Source map URL** textbox and an **Add** button.</span></span>

<span data-ttu-id="49708-306">ソース マッピングの方法では、結合、ミニファイ、またはコンパイルした後でも、フロントエンド コードを人間が読み取り、デバッグできます。</span><span class="sxs-lookup"><span data-stu-id="49708-306">The source-mapping approach keeps your front-end code human-readable and debuggable even after you combine, minify, or compile it.</span></span>
<span data-ttu-id="49708-307">詳細については、「前処理された [コードをソース コードにマップする」を参照してください][DevToolsJavaScriptSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="49708-307">For more information, see [Map preprocessed code to source code][DevToolsJavaScriptSourceMaps].</span></span>

### <a name="transformations-from-source-code-to-compiled-front-end-code"></a><span data-ttu-id="49708-308">ソース コードからコンパイル済みのフロントエンド コードへの変換</span><span class="sxs-lookup"><span data-stu-id="49708-308">Transformations from source code to compiled front-end code</span></span>

<span data-ttu-id="49708-309">javaScript ファイルを変換するフレームワーク (React など) を使用する場合、ローカル ソース JavaScript が、サーバーによって返されるフロントエンド JavaScript とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49708-309">If you use a framework that transforms your JavaScript files, such as React, your local source JavaScript might be different than the front-end JavaScript that's returned by the server.</span></span>  <span data-ttu-id="49708-310">このシナリオではワークスペースはサポートされていませんが、このシナリオではソース コードマッピングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49708-310">Workspaces aren't supported in this scenario, but source code mapping is supported in this scenario.</span></span>  

<span data-ttu-id="49708-311">開発環境では、サーバーにソース マップと、ユーザーの元のマップまたはファイルが含 `.ts` `.jsx` React。</span><span class="sxs-lookup"><span data-stu-id="49708-311">In a development environment, your server might include your source maps and your original `.ts` or `.jsx` files for React.</span></span>  <span data-ttu-id="49708-312">[ **ソース] ツール** は、これらのファイルを表示しますが、これらのファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="49708-312">The **Sources** tool displays these files, but doesn't allow you to edit these files.</span></span>  <span data-ttu-id="49708-313">ブレークポイントを設定してデバッガーを使用すると、DevTools は元のファイルまたはファイルを表示しますが、実際には JavaScript ファイルの最小バージョンを `.ts` `.jsx` ステップスルーします。</span><span class="sxs-lookup"><span data-stu-id="49708-313">When you set breakpoints and use the debugger, DevTools displays your original `.ts` or `.jsx` files, but actually steps-through the minified version of your JavaScript files.</span></span>

<span data-ttu-id="49708-314">このシナリオでは **、Sources** ツールは、サーバーから返される変換済みフロントエンド JavaScript の検査とステップスルーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49708-314">In this scenario, the **Sources** tool is useful for inspecting and stepping-through the transformed, front-end JavaScript that's returned from the server.</span></span>  <span data-ttu-id="49708-315">デバッガーを使用してウォッチ式を定義し、コンソールを使用して JavaScript 式を入力してスコープ内のデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="49708-315">Use the debugger to define Watch expressions, and use the Console to enter JavaScript expressions to manipulate data that's in-scope.</span></span>

### <a name="editing-a-css-file"></a><span data-ttu-id="49708-316">CSS ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-316">Editing a CSS file</span></span>

<span data-ttu-id="49708-317">DevTools で CSS を編集するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="49708-317">There are two ways to edit CSS in DevTools:</span></span>  

*   <span data-ttu-id="49708-318">要素ツール **では** 、ユーザー インターフェイス コントロールを使用して、一度に 1 つの CSS 設定を操作します。</span><span class="sxs-lookup"><span data-stu-id="49708-318">In the **Elements** tool, you work with one CSS setting at a time, through user interface controls.</span></span>  <span data-ttu-id="49708-319">ほとんどの場合、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49708-319">This approach is recommended in most cases.</span></span>  <span data-ttu-id="49708-320">詳細については、「スタイル」ウィンドウ [の「EDIT CSS フォント スタイルと設定」を参照してください][DevToolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="49708-320">For more information, see [Edit CSS font styles and settings in the Styles pane][DevToolsInspectStylesEditFonts].</span></span>  
*   <span data-ttu-id="49708-321">[ソース **] ツールでは** 、テキスト エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-321">In the **Sources** tool, you use a text editor.</span></span>  
    
<span data-ttu-id="49708-322">Sources ツールでは、CSS ファイルの直接編集がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49708-322">The Sources tool supports directly editing a CSS file.</span></span>  <span data-ttu-id="49708-323">たとえば、以下のスタイル ルールに一致するワークスペース[][DevtoolsGuideChromiumWorkspacesIndex]を使用してファイルを編集するチュートリアルから CSS ファイルを編集すると、レンダリングされた Web ページの左上にある要素が緑色 `H1` に変わります。</span><span class="sxs-lookup"><span data-stu-id="49708-323">For example, if you edit the CSS file from the tutorial [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to match the style rule below, the `H1` element in the upper left of the rendered webpage changes to green:</span></span>

```css
h1 {
  color: green;
}  
```  

:::image type="complex" source="../media/edit-css.msft.png" alt-text="[エディター] ウィンドウで CSS を編集して、H1 見出しのテキストの色を緑に変更する" lightbox="../media/edit-css.msft.png":::
   <span data-ttu-id="49708-325">[エディター] ウィンドウで CSS **を** 編集して、見出しのテキストの色を `H1` 緑に変更する</span><span class="sxs-lookup"><span data-stu-id="49708-325">Edit CSS in the **Editor** pane to change the text color of the `H1` heading to green</span></span>  
:::image-end:::  

<span data-ttu-id="49708-326">CSS の変更は直ちに有効になります。変更を手動で保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49708-326">CSS changes take effect immediately; you don't need to manually save the changes.</span></span>

#### <a name="see-also"></a><span data-ttu-id="49708-327">関連項目</span><span class="sxs-lookup"><span data-stu-id="49708-327">See also</span></span>  

*   [<span data-ttu-id="49708-328">[スタイル] ウィンドウで CSS フォントのスタイルと設定を編集する</span><span class="sxs-lookup"><span data-stu-id="49708-328">Edit CSS font styles and settings in the Styles pane</span></span>][DevToolsInspectStylesEditFonts]  
*   <span data-ttu-id="49708-329">[初級者向け DevTools: CSS の使用を開始][DevToolsBeginnersCss] する - チュートリアル</span><span class="sxs-lookup"><span data-stu-id="49708-329">[DevTools for beginners: Get started with CSS][DevToolsBeginnersCss] - tutorial</span></span>  
    
### <a name="editing-an-html-file"></a><span data-ttu-id="49708-330">HTML ファイルの編集</span><span class="sxs-lookup"><span data-stu-id="49708-330">Editing an HTML file</span></span>

<span data-ttu-id="49708-331">DevTools で HTML を編集するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="49708-331">There are two ways to edit HTML in DevTools:</span></span>  

*   <span data-ttu-id="49708-332">要素ツール **では** 、ユーザー インターフェイス コントロールを使用して、一度に 1 つの HTML 要素を操作します。</span><span class="sxs-lookup"><span data-stu-id="49708-332">In the **Elements** tool, you work with one HTML element at a time, through user interface controls.</span></span>  
*   <span data-ttu-id="49708-333">[ソース **] ツールでは** 、テキスト エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-333">In the **Sources** tool, you use a text editor.</span></span>  
    
:::image type="complex" source="../media/sources-html-editor.msft.png" alt-text="ソース ツールの HTML エディター" lightbox="../media/sources-html-editor.msft.png":::
   <span data-ttu-id="49708-335">ソース ツールの HTML**エディター**</span><span class="sxs-lookup"><span data-stu-id="49708-335">The HTML editor of the **Sources** tool</span></span>
:::image-end:::  

<span data-ttu-id="49708-336">JavaScript ファイルや CSS ファイルとは異なり、Web サーバーから返される HTML ファイルをソース ツールで直接編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="49708-336">Unlike a JavaScript or CSS file, an HTML file that is returned by the web server cannot be directly edited in the Sources tool.</span></span>  <span data-ttu-id="49708-337">ソース ツールのエディターを使用して HTML ファイルを編集するには、HTML ファイルがワークスペースまたは [上書き] タブ **にある必要** があります。 現在の記事の次のサブセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49708-337">To edit an HTML file using the Editor of the Sources tool, the HTML file must be in a Workspace or on the **Overrides** tab.  See these subsections of the current article:</span></span>  

*   [<span data-ttu-id="49708-338">[ファイルシステム] タブを使用してローカル ワークスペースを定義する</span><span class="sxs-lookup"><span data-stu-id="49708-338">Using the Filesystem tab to define a local Workspace</span></span>](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [<span data-ttu-id="49708-339">[上書き] タブを使用してサーバー ファイルをローカル ファイルで上書きする</span><span class="sxs-lookup"><span data-stu-id="49708-339">Using the Overrides tab to override server files with local files</span></span>](#using-the-overrides-tab-to-override-server-files-with-local-files)  
   
<span data-ttu-id="49708-340">変更を保存するには、Windows/Linux または `Ctrl` + `S` `Command` + `S` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-340">To save changes, select `Ctrl`+`S` on Windows/Linux or `Command`+`S` on macOS.</span></span>  <span data-ttu-id="49708-341">編集したファイルにはアスタリスクが付きます。</span><span class="sxs-lookup"><span data-stu-id="49708-341">An edited file is marked by an asterisk.</span></span>  
<span data-ttu-id="49708-342">テキストを見つけるには、Windows/Linux または `Ctrl` + `F` `Command` + `F` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-342">To find text, select `Ctrl`+`F` on Windows/Linux or `Command`+`F` on macOS.</span></span>  
<span data-ttu-id="49708-343">編集を元に戻すには、Windows/Linux または `Ctrl` + `Z` `Command` + `Z` macOS で選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-343">To undo an edit, select `Ctrl`+`Z` on Windows/Linux or `Command`+`Z` on macOS.</span></span>  
<span data-ttu-id="49708-344">HTML ファイルの編集中に他のコマンドを表示するには、[エディター] ウィンドウで HTML ファイルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="49708-344">To view other commands while editing an HTML file, in the Editor pane, right-click the HTML file.</span></span>  
<span data-ttu-id="49708-345">また、DevTools ではなく HTML エディターを使用して HTML を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="49708-345">You can also edit HTML by using an HTML editor, rather than DevTools.</span></span>  <span data-ttu-id="49708-346">たとえば、記事 [「DevTools for beginners: Get started][DevToolsBeginnersHtml] with HTML and THE DOM は Web ページ内で HTML 編集を可能にする Web サイトを使用します。</span><span class="sxs-lookup"><span data-stu-id="49708-346">For example, the article [DevTools for beginners: Get started with HTML and the DOM][DevToolsBeginnersHtml] uses a website that enables HTML editing within the webpage.</span></span>  

### <a name="going-to-a-line-number-or-function"></a><span data-ttu-id="49708-347">行番号または関数にアクセスする</span><span class="sxs-lookup"><span data-stu-id="49708-347">Going to a line number or function</span></span>

<span data-ttu-id="49708-348">エディター ウィンドウで開いているファイル内の行番号または記号 \(関数名\など) に移動するには、ファイルをスクロールするのではなく、コマンド メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49708-348">To go to a line number or symbol \(such as a function name\) in the file which is open in the Editor pane, you can use the Command Menu, rather than scrolling through the file.</span></span>

1.  <span data-ttu-id="49708-349">[ナビゲーター **] ウィンドウで**、省略記号 \( \) \( More options \) を選択し、[ファイルを開く `...` ]**を選択します**。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="49708-349">In the **Navigator** pane, select the ellipses \(`...`\) \(**More options**\), and then select **Open File**.</span></span>  <span data-ttu-id="49708-350">[コマンド] メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-350">The Command Menu appears.</span></span>  
1.  <span data-ttu-id="49708-351">次のいずれかの文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="49708-351">Type one of the following characters:</span></span>  
     
| <span data-ttu-id="49708-352">文字</span><span class="sxs-lookup"><span data-stu-id="49708-352">Character</span></span> | <span data-ttu-id="49708-353">コマンド名</span><span class="sxs-lookup"><span data-stu-id="49708-353">Command name</span></span> | <span data-ttu-id="49708-354">目的</span><span class="sxs-lookup"><span data-stu-id="49708-354">Purpose</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="49708-355">\:</span><span class="sxs-lookup"><span data-stu-id="49708-355">\:</span></span> | **<span data-ttu-id="49708-356">行に移動する</span><span class="sxs-lookup"><span data-stu-id="49708-356">Go to line</span></span>** | <span data-ttu-id="49708-357">行番号に移動します。</span><span class="sxs-lookup"><span data-stu-id="49708-357">Go to a line number.</span></span>  |  
| \@ | **<span data-ttu-id="49708-358">記号に移動する</span><span class="sxs-lookup"><span data-stu-id="49708-358">Go to symbol</span></span>** | <span data-ttu-id="49708-359">関数に移動します。</span><span class="sxs-lookup"><span data-stu-id="49708-359">Go to a function.</span></span>  <span data-ttu-id="49708-360">入力すると、[エディター] ウィンドウで開いている JavaScript ファイルにある関数がコマンド `@` メニューに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-360">When you type `@`, the Command Menu lists the functions that are found in the JavaScript file which is open in the Editor pane.</span></span>  |  
   
<span data-ttu-id="49708-361">詳細については[、「DevTools コマンド メニューを使用してコマンドMicrosoft Edge実行する」を参照してください][DevToolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="49708-361">For more information, see [Run commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex].</span></span>

### <a name="displaying-source-files-when-using-a-different-tool"></a><span data-ttu-id="49708-362">別のツールを使用する場合のソース ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="49708-362">Displaying source files when using a different tool</span></span>

<span data-ttu-id="49708-363">DevTools でソース ファイルを表示する主な場所は、ソース ツール **内** です。</span><span class="sxs-lookup"><span data-stu-id="49708-363">The main place to view source files in the DevTools is within the **Sources** tool.</span></span>  <span data-ttu-id="49708-364">ただし、ソース ファイルの表示または編集中に **、Elements** や **Console**などの他のツールにアクセスする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="49708-364">But sometimes you need to access other tools, such as **Elements** or **Console**, while viewing or editing your source files.</span></span>  <span data-ttu-id="49708-365">ドロワー **で [クイック ソース]** ツールを使用 [します][DevtoolsCustomizeIndexDrawer]。</span><span class="sxs-lookup"><span data-stu-id="49708-365">Use the **Quick Sources** tool in the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

1.  <span data-ttu-id="49708-366">[要素] ツールなど、[ソース] ツール **以外** のツール **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="49708-366">Select a tool other than the **Sources** tool, such as the **Elements** tool.</span></span>  
1.  <span data-ttu-id="49708-367">`Ctrl` + `Shift` + `P` \(Windows Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-367">Select `Ctrl`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="49708-368">[コマンド] メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="49708-368">The Command Menu opens.</span></span>  
1.  <span data-ttu-id="49708-369">を `Quick Source` 入力し、[クイック ソースの **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-369">Type `Quick Source`, and then select **Show Quick Source**.</span></span>  <span data-ttu-id="49708-370">DevTools ウィンドウの下部に、[クイック ソース] パネルが選択されたドロワー **が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-370">At the bottom of the DevTools window, the Drawer appears, with the **Quick Source** panel selected.</span></span>  <span data-ttu-id="49708-371">[**クイック ソース]** パネルには、ソース ツールで編集\*\*\*\* した最後のファイルが、コンパクト バージョンの DevTools コード エディター内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="49708-371">The **Quick Source** panel contains the last file you edited in the **Sources** tool, within a compact version of the DevTools code editor.</span></span>  
1.  <span data-ttu-id="49708-372">`Ctrl` + `P` \(Windows Linux\) または \(macOS\) を選択して、[ファイルを開く `Command` + `P` ]**ダイアログを開**きます。</span><span class="sxs-lookup"><span data-stu-id="49708-372">Select `Ctrl`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  
    
## <a name="using-the-debugger-pane-to-debug-javascript-code"></a><span data-ttu-id="49708-373">デバッガー ウィンドウを使用して JavaScript コードをデバッグする</span><span class="sxs-lookup"><span data-stu-id="49708-373">Using the Debugger pane to debug JavaScript code</span></span>

<span data-ttu-id="49708-374">JavaScript デバッガーを使用して、サーバーから返される JavaScript コードをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-374">Use the JavaScript debugger to step through the JavaScript code that's returned by the server.</span></span>  
<span data-ttu-id="49708-375">デバッガーには、 **デバッガー ウィンドウ** と、エディター ウィンドウのコード行に設定したブレークポイントが **含** まれます。</span><span class="sxs-lookup"><span data-stu-id="49708-375">The debugger includes the **Debugger** pane, along with breakpoints that you set on lines of code in the **Editor** pane.</span></span>

<span data-ttu-id="49708-376">デバッガーを使用して、指定した JavaScript 式を確認しながら、コードをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-376">With the debugger, you step through the code, while watching any JavaScript expressions you specify.</span></span>  <span data-ttu-id="49708-377">変数の値を監視して手動で変更し、現在のステートメントのスコープ内にある変数を自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-377">Watch and manually change variable values, and automatically show which variables are in-scope for the current statement.</span></span>

:::image type="complex" source="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png" alt-text="ソース ツールのデバッガー ウィンドウ  " lightbox="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png":::
   <span data-ttu-id="49708-379">ソース**ツール**のデバッガー**ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="49708-379">The **Debugger** pane of the **Sources** tool</span></span>  
:::image-end:::  

<span data-ttu-id="49708-380">デバッガーは、次のような標準的なデバッグ アクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49708-380">The debugger supports standard debugging actions, such as:</span></span>  

*   <span data-ttu-id="49708-381">ブレークポイントを設定し、コードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="49708-381">Setting breakpoints, to pause code.</span></span>  
*   <span data-ttu-id="49708-382">コードをステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-382">Stepping through code.</span></span>  
*   <span data-ttu-id="49708-383">プロパティと変数の表示と編集。</span><span class="sxs-lookup"><span data-stu-id="49708-383">Viewing and editing properties and variables.</span></span>  
*   <span data-ttu-id="49708-384">JavaScript 式の値を確認する。</span><span class="sxs-lookup"><span data-stu-id="49708-384">Watching the values of JavaScript expressions.</span></span>  
*   <span data-ttu-id="49708-385">呼び出し履歴\ (ここまでの関数呼び出しのシーケンス\) を表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-385">Viewing the call stack\ (the sequence of function calls so far\).</span></span>  
    
<span data-ttu-id="49708-386">DevTools のデバッガーは、デバッガーと同じ外観、外観、[][VisualStudioCodeDocsEditorDebugging]および動作をVisual Studio Codeのデバッガー[と][VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]同Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="49708-386">The debugger in DevTools is designed to look, feel, and work like [the debugger in Visual Studio Code][VisualStudioCodeDocsEditorDebugging] and [the debugger in Visual Studio][VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger].</span></span>

<span data-ttu-id="49708-387">次のサブセクションでは、デバッグについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49708-387">The following subsections cover debugging:</span></span>  

*   [<span data-ttu-id="49708-388">デバッガーを使用する基本的な方法</span><span class="sxs-lookup"><span data-stu-id="49708-388">The basic approach to using a debugger</span></span>](#the-basic-approach-to-using-a-debugger)  
*   [<span data-ttu-id="49708-389">デバッガーの Watch と Scope over console.log の利点</span><span class="sxs-lookup"><span data-stu-id="49708-389">Advantages of the debugger's Watch and Scope over console.log</span></span>](#advantages-of-the-debuggers-watch-and-scope-over-consolelog)  
*   [<span data-ttu-id="49708-390">直接Visual Studio Codeデバッグ</span><span class="sxs-lookup"><span data-stu-id="49708-390">Debug from Visual Studio Code directly</span></span>](#debug-from-visual-studio-code-directly)  
*   [<span data-ttu-id="49708-391">デバッグに関する記事</span><span class="sxs-lookup"><span data-stu-id="49708-391">Articles about debugging</span></span>](#articles-about-debugging)  
    
### <a name="the-basic-approach-to-using-a-debugger"></a><span data-ttu-id="49708-392">デバッガーを使用する基本的な方法</span><span class="sxs-lookup"><span data-stu-id="49708-392">The basic approach to using a debugger</span></span>

<span data-ttu-id="49708-393">JavaScript コードのトラブルシューティングを行う場合は、[エディター] ウィンドウ `console.log()` にステートメントを **挿入** します。</span><span class="sxs-lookup"><span data-stu-id="49708-393">To troubleshoot JavaScript code, you can insert `console.log()` statements in the **Editor** pane.</span></span>  <span data-ttu-id="49708-394">もう 1 つの強力な方法は、DevTools のデバッガー Microsoft Edgeです。</span><span class="sxs-lookup"><span data-stu-id="49708-394">Another, more powerful approach is to use the debugger of Microsoft Edge DevTools.</span></span>  <span data-ttu-id="49708-395">デバッガーの使用は、デバッガーのアプローチに慣れたら、より `console.log()` 簡単です。</span><span class="sxs-lookup"><span data-stu-id="49708-395">Using a debugger can actually be simpler than `console.log()`, once you're familiar with the debugger approach.</span></span>

<span data-ttu-id="49708-396">Web ページでデバッガーを使用するには、通常、ブレークポイントを設定し、次のように Web ページからフォームを送信します。</span><span class="sxs-lookup"><span data-stu-id="49708-396">To use a debugger on a webpage, you typically set a breakpoint and then send a form from the webpage, as follows:</span></span>

1.  <span data-ttu-id="49708-397">ブラウザーの新しいタブで Web ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="49708-397">Open the webpage in a new tab of the browser.</span></span>  <span data-ttu-id="49708-398">たとえば、このフォーム Web ページを新しいタブで開きます:Demo: はじめに デバッグ JavaScript with Microsoft Edge [(Chromium) DevTools][GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted].</span><span class="sxs-lookup"><span data-stu-id="49708-398">For example, open this form webpage in a new tab: [Demo: Get Started Debugging JavaScript with Microsoft Edge (Chromium) DevTools][GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted].</span></span>  
1.  <span data-ttu-id="49708-399">`F12` **[DevTools] ウィンドウを開き、[** ソース] タブ**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-399">Select `F12` to open the **DevTools** window, and then select the **Sources** tab.</span></span>  
1.  <span data-ttu-id="49708-400">[ナビゲーター **] ウィンドウ**\(左側\) で\*\*\*\*、[ページ] タブを選択し、 などの JavaScript ファイルを選択します `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="49708-400">In the **Navigator** pane \(on the left\), select the **Page** tab, and then select the JavaScript file, such as `get-started.js`.</span></span>  
1.  <span data-ttu-id="49708-401">[エディター **] ウィンドウ** で、疑わしいコード行の近くの行番号を選択して、その行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="49708-401">In the **Editor** pane, select a line number near a suspect line of code, to set a breakpoint on that line.</span></span>  <span data-ttu-id="49708-402">下の図では、ブレークポイントが行に設定されています `var sum = addend1 + addend2;` 。</span><span class="sxs-lookup"><span data-stu-id="49708-402">In the figure below, a breakpoint is set on the line `var sum = addend1 + addend2;`.</span></span>  
1.  <span data-ttu-id="49708-403">Web ページで値を入力し、フォームを送信します。</span><span class="sxs-lookup"><span data-stu-id="49708-403">In the webpage, enter values and submit the form.</span></span>  <span data-ttu-id="49708-404">たとえば、番号を入力し、[番号 1 の追加] ボタンと [番号 `5` `1` **2] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49708-404">For example, enter numbers, such as `5` and `1`, then select the button **Add Number 1 and Number 2**.</span></span>  
    
    <span data-ttu-id="49708-405">デバッガーは JavaScript コードを実行し、ブレークポイントで一時停止します。</span><span class="sxs-lookup"><span data-stu-id="49708-405">The debugger runs the JavaScript code and then pauses at the breakpoint.</span></span>  <span data-ttu-id="49708-406">デバッガーが一時停止モードに切り替わるので、スコープ内のプロパティの値を検査し、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="49708-406">The debugger is now in Paused mode, so you can inspect the values of the properties that are in-scope, and step through the code.</span></span>  
    
    :::image type="complex" source="../media/sources-paused-breakpoint-highlights.msft.png" alt-text="デバッガーの一時停止モードに入る" lightbox="../media/sources-paused-breakpoint-highlights.msft.png":::
        <span data-ttu-id="49708-408">デバッガーの一時停止モードに入る</span><span class="sxs-lookup"><span data-stu-id="49708-408">Entering Paused mode of the debugger</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="49708-409">上の図では、ウォッチ式と、ブレークポイントを越えた `sum` `typeof sum` 2 行のステップを追加しました。</span><span class="sxs-lookup"><span data-stu-id="49708-409">In the above figure, we added the Watch expressions `sum` and `typeof sum`, and stepped two lines past the breakpoint.</span></span>  
    
1.  <span data-ttu-id="49708-410">[スコープ] ウィンドウの **値を** 調べて、現在のブレークポイントのスコープ内のすべての変数またはプロパティとその値を表示します。</span><span class="sxs-lookup"><span data-stu-id="49708-410">Examine the values in the **Scope** pane, which shows all variables or properties that are in-scope for the current breakpoint, and their values.</span></span>  <span data-ttu-id="49708-411">または、[ウォッチ] ウィンドウに式 **を追加** します。</span><span class="sxs-lookup"><span data-stu-id="49708-411">Or, add expressions in the **Watch** pane.</span></span>  <span data-ttu-id="49708-412">これらの式は、コードをデバッグするためにステートメント内で記述する式 `console.log` と同じです。</span><span class="sxs-lookup"><span data-stu-id="49708-412">These expressions are the same expressions that you would write within a `console.log` statement to debug your code.</span></span>  <span data-ttu-id="49708-413">JavaScript コマンドを実行して現在のコンテキストでデータを操作するには、コンソール を使用 **します**。</span><span class="sxs-lookup"><span data-stu-id="49708-413">To run JavaScript commands to manipulate data in the current context, use the **Console**.</span></span>  <span data-ttu-id="49708-414">コンソールを開く場合は、 を選択します `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="49708-414">To open the console, select `Esc`.</span></span>  
1.  <span data-ttu-id="49708-415">デバッガー ウィンドウの上部にあるコントロール (Step \( \*\*\*\* \) など) を使用して、コード**を** `F9` ステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="49708-415">Step through the code by using the controls at the top of the **Debugger** pane, such as **Step** \(`F9`\).</span></span>
    
#### <a name="see-also"></a><span data-ttu-id="49708-416">関連項目</span><span class="sxs-lookup"><span data-stu-id="49708-416">See also</span></span>

*   <span data-ttu-id="49708-417">[JavaScript のデバッグの開始][DevtoolsGuideChromiumJavascriptIndex] - いくつかのフォーム コントロールを含む既存の単純な Web ページを使用したチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="49708-417">[Get started with debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] - a tutorial using an existing, simple webpage that contains a few form controls.</span></span>
    
### <a name="advantages-of-the-debuggers-watch-and-scope-over-consolelog"></a><span data-ttu-id="49708-418">デバッガー\'s Watch and Scope over console\.log の利点</span><span class="sxs-lookup"><span data-stu-id="49708-418">Advantages of the debugger\'s Watch and Scope over console\.log</span></span>  

<span data-ttu-id="49708-419">これら 3 つの方法は同等です。</span><span class="sxs-lookup"><span data-stu-id="49708-419">These three approaches are equivalent:</span></span>

*   <span data-ttu-id="49708-420">ステートメントを一時的に `console.log(sum)` 追加 `console.log(typeof sum)` し、スコープ内の `sum` コードに追加します。</span><span class="sxs-lookup"><span data-stu-id="49708-420">Temporarily adding the statements `console.log(sum)` and `console.log(typeof sum)` in the code, where `sum` is in-scope.</span></span>  
*   <span data-ttu-id="49708-421">デバッガーがスコープ内の場所で一時停止されている場合に、DevTools の [コンソール] ウィンドウでステートメント `sum` `console.log(typeof sum)` \*\*\*\* `sum` を発行します。</span><span class="sxs-lookup"><span data-stu-id="49708-421">Issuing the statements `sum` and `console.log(typeof sum)` in the **Console** pane of the DevTools, when the debugger is paused where `sum` is in-scope.</span></span>  
*   <span data-ttu-id="49708-422">[ウォッチ式 **]** と `sum` [ `typeof sum` デバッガー] ウィンドウ **を設定** します。</span><span class="sxs-lookup"><span data-stu-id="49708-422">Setting the **Watch** expressions `sum` and `typeof sum` in the **Debugger** pane.</span></span>  
    
<span data-ttu-id="49708-423">変数がスコープ内で、その値がデバッガー ウィンドウの [スコープ] セクションに自動的に表示され、計算される [エディター] ウィンドウにもオーバーレイ `sum` `sum` \*\*\*\*\*\*\*\* `sum` されます。</span><span class="sxs-lookup"><span data-stu-id="49708-423">When the variable `sum` is in-scope, `sum` and its value are automatically shown in the **Scope** section of the **Debugger** pane, and are also overlaid in the Editor pane where `sum` is calculated.</span></span>  <span data-ttu-id="49708-424">そのため、ウォッチ式を定義する必要はおそらくない `sum` でしょう。</span><span class="sxs-lookup"><span data-stu-id="49708-424">So you probably wouldn't need to define a Watch expression for `sum`.</span></span>

<span data-ttu-id="49708-425">デバッガーは、ステートメントよりもリッチで柔軟性の高い表示と環境を提供 `console.log` します。</span><span class="sxs-lookup"><span data-stu-id="49708-425">The debugger gives a richer, more flexible display and environment than a `console.log` statement.</span></span>  <span data-ttu-id="49708-426">たとえば、デバッガーでコードをステップ実行すると、現在定義されているプロパティと変数の値を表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="49708-426">For example, in the debugger, as you step through the code, you can display and change the values of all currently defined properties and variables.</span></span>  <span data-ttu-id="49708-427">スコープ内の配列の値を変更するなどの\*\*\*\* JavaScript ステートメントをコンソールで発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="49708-427">You can also issue JavaScript statements in the **Console**, such as to change values in an array that's in-scope.</span></span>  <span data-ttu-id="49708-428">\(コンソールを表示するには **、Esc**.\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="49708-428">\(To display the Console, select **Esc**.\)</span></span>

<span data-ttu-id="49708-429">ブレークポイントとウォッチ式は、Web ページを更新すると保持されます。</span><span class="sxs-lookup"><span data-stu-id="49708-429">Breakpoints and Watch expressions are preserved when you refresh the webpage.</span></span>

### <a name="debug-from-visual-studio-code-directly"></a><span data-ttu-id="49708-430">直接Visual Studio Codeデバッグ</span><span class="sxs-lookup"><span data-stu-id="49708-430">Debug from Visual Studio Code directly</span></span>

<span data-ttu-id="49708-431">DevTools デバッガーの代わりに Visual Studio Code のよりフル機能のデバッガーを使用するには、Microsoft Edge**ツールを**VS Code拡張機能Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="49708-431">To use the more full-featured debugger of Visual Studio Code instead of the DevTools debugger, use the **Microsoft Edge Tools for VS Code** extension for Visual Studio Code.</span></span>

:::image type="complex" source="../media/microsoft-edge-tools-for-vs-code-extension.msft.png" alt-text="[Microsoft Edge ツール] VS Codeの拡張機能Visual Studio Code" lightbox="../media/microsoft-edge-tools-for-vs-code-extension.msft.png":::
   <span data-ttu-id="49708-433">**[Microsoft Edgeツール] VS Code**の拡張機能Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49708-433">The **Microsoft Edge Tools for VS Code** extension for Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="49708-434">この拡張機能は、DevTools\*\*\*\* の要素とネットワーク ツールMicrosoft Edgeコード内からMicrosoft Visual Studioします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="49708-434">This extension provides access to the **Elements** and **Network** tools of Microsoft Edge DevTools, from within Microsoft Visual Studio Code.</span></span>  

<span data-ttu-id="49708-435">詳細については、「開発者向[け][VisualStudioCodeIndex]ツールVisual Studio Codeの概要」および「GitHub Readme」ページ[Microsoft Edgeを参照Visual Studio Code。][GithubMicrosoftVscodeEdgeDevtools]</span><span class="sxs-lookup"><span data-stu-id="49708-435">For more information, see [Visual Studio Code overview][VisualStudioCodeIndex] and the GitHub Readme page, [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools].</span></span>

### <a name="articles-about-debugging"></a><span data-ttu-id="49708-436">デバッグに関する記事</span><span class="sxs-lookup"><span data-stu-id="49708-436">Articles about debugging</span></span>

<span data-ttu-id="49708-437">次の記事では、デバッガー ウィンドウ **と** ブレークポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49708-437">The following articles cover the **Debugger** pane and breakpoints:</span></span>

*   <span data-ttu-id="49708-438">[DevTools での JavaScript][DevtoolsGuideChromiumJavascriptIndex]のデバッグMicrosoft Edge始める - 既存の単純なプロジェクトを使用したチュートリアル \(screen captures\を使用)。</span><span class="sxs-lookup"><span data-stu-id="49708-438">[Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsGuideChromiumJavascriptIndex] - A tutorial \(with screen captures\), using an existing, simple project.</span></span>  
*   <span data-ttu-id="49708-439">[デバッガー機能を使用][DevToolsJavaScriptReference] する - デバッガーを使用してブレークポイントの設定、コードのステップ実行、変数値の表示と変更、JavaScript 式の監視、通話履歴の表示を行う方法。</span><span class="sxs-lookup"><span data-stu-id="49708-439">[Use the debugger features][DevToolsJavaScriptReference] - How to use the debugger to set breakpoints, step through code, view and modify variable values, watch JavaScript expressions, and view the call stack.</span></span>  
*   <span data-ttu-id="49708-440">[ブレークポイントでコードを一時停止する][DevToolsJavaScriptBreakpoints] - デバッガーで基本的なブレークポイントと特殊なブレークポイントを設定する方法。</span><span class="sxs-lookup"><span data-stu-id="49708-440">[Pause your code with breakpoints][DevToolsJavaScriptBreakpoints] - How to set basic and specialized breakpoints in the debugger.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="49708-441">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="49708-441">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsBeginnersCss]: ../beginners/css.md "初級者向け DevTools: CSS の使用|Microsoft Docs"  
[DevToolsBeginnersHtml]: ../beginners/html.md "初級者向け DevTools: HTML と DOM の使用を|Microsoft Docs"  
[DevToolsCommandMenuIndex]: ../command-menu/index.md "Microsoft Edge DevTools コマンド メニュー を使用してコマンドを実行する | Microsoft Docs"   
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "ドロワー - Microsoft Edge DevTools をカスタマイズする | Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "DevTools Microsoft Edge配置を変更する (Undock、Dock to bottom、Dock to left) |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "DevTools アプリケーションの JavaScript のデバッグMicrosoft Edge開始|Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "DevTools を使用して任意の Web ページで JavaScript のスニペットMicrosoft Edge実行|Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "Workspaces を使用してファイルを編集|Microsoft Docs"  
[DevToolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "[スタイル] ウィンドウの [CSS フォントのスタイルと設定を編集|Microsoft Docs"  
[DevToolsJavaScriptBreakpoints]: ../javascript/breakpoints.md "ブレークポイントを使用してコードを一時停止|Microsoft Docs"  
[DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]: ../javascript/guides/mark-content-scripts-library-code.md "コンテンツ スクリプトをライブラリ コード としてマーク|Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ../javascript/overrides.md "DevTools を使用して Web ページ リソースをローカル コピー Microsoft Edgeオーバーライド|Microsoft Docs"  
[DevToolsJavaScriptReference]: ../javascript/reference.md "デバッガー機能を使用|Microsoft Docs"  
[DevToolsJavaScriptReferenceReformat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "簡易印刷を使用して、ミニマ化された JavaScript ファイルを再フォーマットする - デバッガー機能を使用|Microsoft Docs"  
[DevToolsJavaScriptSourceMaps]: ../javascript/source-maps.md "前処理されたコードをソース コード にマップ|Microsoft Docs"  
[VisualStudioCodeIndex]: ../../visual-studio-code/index.md "Visual Studio Code概要|Microsoft Docs"  
[ExtensionsChromiumGetstartPart2ContentScripts]: ../../extensions-chromium/getting-started/part2-content-scripts.md "拡張機能チュートリアルの作成 パート 2 |Microsoft Docs"  

[VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]: /visualstudio/debugger/navigating-through-code-with-the-debugger "デバッガー ウィンドウを使用してコードVisual Studio移動|Microsoft Docs"  

[VisualStudioCodeDocsEditorDebugging]: https://code.visualstudio.com/docs/editor/debugging "デバッグ|Visual Studio Code"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "Microsoft Edge開発者向けツール Visual Studio Code |GitHub"  

[GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "デモ: はじめに (Chromium) DevTools を使用Microsoft Edge JavaScript のデバッグ|Microsoft Docs"  

[WhatwgHtmlSpecMulitpageOriginHtmlOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "Origin |HTML 標準"  

[MdnAddOnsWebextensionsContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "コンテンツ スクリプト|MDN"  

[TypescriptlangMain]: https://www.typescriptlang.org "TypeScript"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "フレーム |W3C"  

> [!NOTE]
> <span data-ttu-id="49708-467">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="49708-467">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="49708-468">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/sources) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="49708-468">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="49708-470">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="49708-470">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  

<!--todo: needs an accessibility review to replace "view", "see", and "look" with "display", exception is "see also" headings -->  

<!--todo: need a consistency review to replace all UI interactions with "choose" and all keyboard interactions with "select" -->  
