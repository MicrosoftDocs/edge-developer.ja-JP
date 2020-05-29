---
description: F12 開発者ツールを使用して、拡張機能のバックグラウンドスクリプト、コンテンツスクリプト、および拡張ページをデバッグする方法について説明します。
title: 拡張機能-デバッグ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、javascript、開発者、デバッグ、デバッグ
ms.custom: seodec18
ms.openlocfilehash: 34488870cb4e4a92a9d57859509ce7d1176cf284
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569502"
---
# <span data-ttu-id="2864f-104">デバッグ用の拡張機能</span><span class="sxs-lookup"><span data-stu-id="2864f-104">Debugging extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="2864f-105">F12 開発者ツールを使用して、Microsoft Edge で拡張機能をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="2864f-105">You can debug your extensions in Microsoft Edge by using F12 Developer Tools.</span></span>

<span data-ttu-id="2864f-106">以下のビデオでは、バグのある Microsoft Edge 拡張機能について説明します。各デバッグシナリオについて説明し、その方法に合わせて修正します。</span><span class="sxs-lookup"><span data-stu-id="2864f-106">The following video goes through a buggy Microsoft Edge extension, walking though each debugging scenario and fixing it up along the way.</span></span> <span data-ttu-id="2864f-107">詳細については、以下のステップバイステップの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2864f-107">See the step-by-step instructions below for more info.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> <span data-ttu-id="2864f-108">F12 で拡張機能のデバッグ機能を利用するには、最初に "about: flags" の開発者向け機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2864f-108">In order to take advantage of extension debugging with F12, you must first turn on developer features in about:flags.</span></span> <span data-ttu-id="2864f-109">その方法について詳しくは[、「拡張機能の追加と削除](./adding-and-removing-extensions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2864f-109">See [Adding and removing extensions](./adding-and-removing-extensions.md) for details on how to do this.</span></span>


## <span data-ttu-id="2864f-110">バックグラウンドスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2864f-110">Background script debugging</span></span>
<span data-ttu-id="2864f-111">拡張機能のバックグラウンドスクリプトのデバッグを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2864f-111">To start debugging the background script of your extension:</span></span>

1. <span data-ttu-id="2864f-112">[**その他 (...)** ] をクリックし、[**拡張機能**] をクリックして、拡張ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="2864f-112">Click on **More (...)** followed by **Extensions** to go into the extension pane.</span></span>  
 ![[その他] ボタン](./../media/morebutton.png)
2. <span data-ttu-id="2864f-114">デバッグする拡張機能をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2864f-114">Click on the extension that you want to debug.</span></span>
3. <span data-ttu-id="2864f-115">バックグラウンド**ページ**のリンクをクリックして、バックグラウンドプロセスに対して F12 を起動します。</span><span class="sxs-lookup"><span data-stu-id="2864f-115">Click on the **Background page** link to bring up F12 for the background process.</span></span>  
 ![検査リンク付きのオプションの拡張表示が選択されました](./../media/debug-inspect.png)
4. <span data-ttu-id="2864f-117">F12 で [**デバッガー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2864f-117">Select the **Debugger** tab in F12.</span></span>
5. <span data-ttu-id="2864f-118">目的の拡張機能のバックグラウンドスクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="2864f-118">Navigate to and select your extension's background script.</span></span>
6. <span data-ttu-id="2864f-119">ソースコードの行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="2864f-119">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![ブレークポイントを使用したバックグラウンドスクリプトを示す f12 コンソール](./../media/debug-f12-background.png)
7. <span data-ttu-id="2864f-121">[**コンソール**] タブを選択し、コマンド "" を実行し `location.reload()` ます。</span><span class="sxs-lookup"><span data-stu-id="2864f-121">Select the **Console** tab and execute the command "`location.reload()`".</span></span> <span data-ttu-id="2864f-122">これにより、バックグラウンドスクリプトが再実行され、コードをステップ実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2864f-122">This will re-execute the background script, allowing you to step through your code.</span></span>  
 ![場所を指定した本体。再読み込みが入力されました](./../media/debug-f12-background-console.png)


## <span data-ttu-id="2864f-124">コンテンツスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2864f-124">Content script debugging</span></span>
<span data-ttu-id="2864f-125">拡張機能のコンテンツスクリプトのデバッグを開始するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2864f-125">To start debugging the content script of your extension:</span></span>

1. <span data-ttu-id="2864f-126">[**その他 (...)** ] ボタンに移動し、 **[F12 開発者ツール]** を選ぶか、キーボードの f12 キーを押して、f12 を起動します。</span><span class="sxs-lookup"><span data-stu-id="2864f-126">Launch F12 by either navigating to the **More (...)** button and selecting **"F12 Developer Tools"** or by pressing F12 on your keyboard.</span></span>
2. <span data-ttu-id="2864f-127">目的の拡張機能のコンテンツスクリプトに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="2864f-127">Navigate to and select your extension's content script.</span></span> <span data-ttu-id="2864f-128">現在実行されている拡張機能のコンテンツスクリプトは、拡張機能ごとに異なるフォルダーで表されます。</span><span class="sxs-lookup"><span data-stu-id="2864f-128">Content scripts for extensions currently running will be depicted by a different folder for each extension.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2864f-129">実行中のコンテンツスクリプトのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2864f-129">Only running content scripts will appear.</span></span>

3. <span data-ttu-id="2864f-130">ソースコードの行番号の左側をクリックして、デバッグ用のブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="2864f-130">Place breakpoints for debugging by clicking to the left of the source code line number.</span></span>  
 ![デバッグ中のコンテンツスクリプトを含む f12](./../media/debug-content-f12.png)
4. <span data-ttu-id="2864f-132">ブラウザーのタブを更新して、コードのステップ実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="2864f-132">Refresh the browser tab to begin stepping though your code.</span></span>




## <span data-ttu-id="2864f-133">拡張機能のページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2864f-133">Extension page debugging</span></span>

<span data-ttu-id="2864f-134">デバッグ用の拡張ページのソースコードにアクセスするために使用できるメソッドは2つあります。</span><span class="sxs-lookup"><span data-stu-id="2864f-134">There are two methods that can be used for accessing the source code of your extension page for debugging.</span></span> <span data-ttu-id="2864f-135">1つの方法がさまざまなページに適用されますが、それ以外の方法はポップアップページにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2864f-135">One method applies to a variety of pages while the other only works for popup pages.</span></span>

### <span data-ttu-id="2864f-136">拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2864f-136">Debugging any extension page</span></span>
<span data-ttu-id="2864f-137">次の方法は、[オプション] ページやポップアップなどのすべての拡張ページで動作します。</span><span class="sxs-lookup"><span data-stu-id="2864f-137">The following method works for all extension pages like the options page and popups:</span></span>


1. <span data-ttu-id="2864f-138">ページの背景を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="2864f-138">Right-click on the background of your page.</span></span>
2. <span data-ttu-id="2864f-139">**「ソースの表示」** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2864f-139">Select **"View source"**.</span></span>

   ![f12 でのポップアップのデバッグ](./../media/debug-popup-select.png)

3. <span data-ttu-id="2864f-141">F12 キーが表示されたら、デバッグするファイル内にブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="2864f-141">Once F12 opens, place breakpoints within the file you want to debug.</span></span>

   ![f12 でのポップアップのデバッグ](./../media/debug-popup-f12.png)
4. <span data-ttu-id="2864f-143">[**コンソール**] タブを選択し、コマンドを実行し `location.reload()` ます。</span><span class="sxs-lookup"><span data-stu-id="2864f-143">Select the **Console** tab and execute the command `location.reload()`.</span></span> <span data-ttu-id="2864f-144">これにより、ページスクリプトが再実行され、コードをステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="2864f-144">This will re-execute the page script, allowing you to step through your code.</span></span>  

   ![場所を指定した本体。再読み込みが入力されました](./../media/debug-f12-background-console.png)

### <span data-ttu-id="2864f-146">ポップアップ拡張機能ページのデバッグ</span><span class="sxs-lookup"><span data-stu-id="2864f-146">Debugging a popup extension page</span></span>
<span data-ttu-id="2864f-147">拡張ページのデバッグ方法は、ポップアップ拡張ページにも適用されますが、次の手順では、ポップアップをデバッグする別の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2864f-147">While the method for debugging extension pages also applies to popup extension pages, the following steps outline another way to debug your popup:</span></span>

1. <span data-ttu-id="2864f-148">拡張機能のアイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="2864f-148">Right-click your extension's icon.</span></span>
2. <span data-ttu-id="2864f-149">[**ポップアップ検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2864f-149">Select **"Inspect popup"**.</span></span>

   ![ポップアップのデバッグ検査](./../media/debug-popup-inspect.png)
3. <span data-ttu-id="2864f-151">次の手順3と4を実行してブレークポイントを配置し、ポップアップを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="2864f-151">Follow steps 3 and 4 above for placing breakpoints and reloading the popup.</span></span>
