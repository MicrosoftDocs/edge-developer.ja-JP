---
description: 対話型デバッグとアドホック テストには、コンソール ツールを使用します。
title: DevTools - コンソール
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, コンソール
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472aafa9e6c6fd98ea952804f0e92ed0b774f59c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234612"
---
# <span data-ttu-id="f42a9-104">コンソール</span><span class="sxs-lookup"><span data-stu-id="f42a9-104">Console</span></span>

<span data-ttu-id="f42a9-105">Microsoft Edge のコンソール開発者ツールは、JavaScript、ネットワーク要求、セキュリティ エラーなど、Web ページに関連付けられている情報をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="f42a9-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span></span> <span data-ttu-id="f42a9-106">コンソールを使用して、対話型デバッグとアドホック テストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-106">You can use the Console for interactive debugging and ad hoc testing.</span></span> 

<span data-ttu-id="f42a9-107">Microsoft Edge でコンソール ツールを開く場合は、F12 キーを押して開発者ツール ウィンドウにアクセスします (または、ページを右クリックして[ **要素**の検査] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="f42a9-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span></span> <span data-ttu-id="f42a9-108">次に、ウィンドウ **の** 上部にある [コンソール] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f42a9-108">Then, select the **Console** tab at the top of the window.</span></span> 

<span data-ttu-id="f42a9-109">コンソール ツールを使用して、実行中の Web ページと通信することもできます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-109">You can also use the Console tool to communicate to and from a running webpage.</span></span> <span data-ttu-id="f42a9-110">コンソールを使用すると、次の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-110">You can use the Console to:</span></span>

- <span data-ttu-id="f42a9-111">コードの [実行中に、標準のエラー コード](./console/error-and-status-codes.md) と状態コード、および情報メッセージをポストします。</span><span class="sxs-lookup"><span data-stu-id="f42a9-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span></span>
- <span data-ttu-id="f42a9-112">コードに含めるコンソール [API 呼び出](./console/console-api.md) しからカスタム デバッグ ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="f42a9-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span></span>
- <span data-ttu-id="f42a9-113">主要な [変数と関数](./console/command-line.md) の現在の戻り値を検査するコマンド ラインと対話型のツリー ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="f42a9-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span></span>

## <span data-ttu-id="f42a9-114">本体のパーツ</span><span class="sxs-lookup"><span data-stu-id="f42a9-114">Parts of the Console</span></span>

<span data-ttu-id="f42a9-115">次の図は、コンソールの主要な部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="f42a9-115">The following image shows the key parts of the Console:</span></span>

![Microsoft Edge DevTools コンソール](./media/console.png)

1. <span data-ttu-id="f42a9-117">**エラー**  / **警告**  / **情報**  / **ログ**ボタン: コンソール出力を指定された種類でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f42a9-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span></span> <span data-ttu-id="f42a9-118">Ctrl キーを押しながらボタンを **複数選択できます** 。</span><span class="sxs-lookup"><span data-stu-id="f42a9-118">You can multi-select buttons by holding down the **Ctrl** key.</span></span> <span data-ttu-id="f42a9-119">[ **すべて] ボタン** は、すべてのフィルターをクリアします。</span><span class="sxs-lookup"><span data-stu-id="f42a9-119">The **All** button clears all filters.</span></span>

2. <span data-ttu-id="f42a9-120">**[クリア**] ボタン (**Ctrl + L**): [クリア] ボタンは、現在のコンソール表示をクリアします。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f42a9-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span></span>

3. <span data-ttu-id="f42a9-121">**[ログの**保持] チェック\*\*\*\* ボックス: [ログの保持] チェック ボックスをオンにすると、ページが更新され、DevTools を閉じて再度開く間、コンソール出力が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span></span> <span data-ttu-id="f42a9-122">本体の履歴は、タブが閉じている場合、または手動で本体をクリアした場合にのみ消去されます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-122">The Console history clears only when the tab is closed or you manually clear the Console.</span></span>

4. <span data-ttu-id="f42a9-123">**ターゲット**: [ **ターゲット]** ドロップダウン メニューを使用して、ページ内や実行中の拡張機能など、別の実行コンテキスト `<iframe>` に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span></span> <span data-ttu-id="f42a9-124">既定では、ページのトップ レベル フレームが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-124">By default, the top-level frame of your page is selected.</span></span> <span data-ttu-id="f42a9-125">選択したフレームにカーソルを合わせると、そのリソースの完全な URL を示すヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span></span>

5. <span data-ttu-id="f42a9-126">**コンソールの表示**  / **[コンソールの**非表示] ボタン (**Ctrl** ): コンソール パネルに加えて、[コンソールを非表示にする] ボタンを押すと、他の DevTools パネルの下部からコンソール +  **&grave;** \*\*\*\*  /  **を使用**できます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span></span> <span data-ttu-id="f42a9-127">DevTools がコンソール パネルを開いている場合、ボタンは効果がありません。</span><span class="sxs-lookup"><span data-stu-id="f42a9-127">The button has no effect when DevTools is open to the Console panel.</span></span>
 
6. <span data-ttu-id="f42a9-128">**フィルター ログ** (**Ctrl + F**) : 検索ボックスで特定のテキスト文字列を使用してログをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f42a9-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span></span>

7. <span data-ttu-id="f42a9-129">**デバッガー**: 青色のソース リンクを選択して、DevTools デバッガーをその特定のコード行に開き、さらに詳しい検査を行います。</span><span class="sxs-lookup"><span data-stu-id="f42a9-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span></span>

## <span data-ttu-id="f42a9-130">ショートカット</span><span class="sxs-lookup"><span data-stu-id="f42a9-130">Shortcuts</span></span>

<span data-ttu-id="f42a9-131">操作</span><span class="sxs-lookup"><span data-stu-id="f42a9-131">Action</span></span>                                            | <span data-ttu-id="f42a9-132">ショートカット</span><span class="sxs-lookup"><span data-stu-id="f42a9-132">Shortcut</span></span>               
:-------------------------------------------------| :----------------------
<span data-ttu-id="f42a9-133">コンソールにフォーカスがある DevTools を起動する</span><span class="sxs-lookup"><span data-stu-id="f42a9-133">Launch DevTools with Console in focus</span></span>             | <span data-ttu-id="f42a9-134">**Ctrl**  + **Shift**  + **J**</span><span class="sxs-lookup"><span data-stu-id="f42a9-134">**Ctrl** + **Shift** + **J**</span></span> 
<span data-ttu-id="f42a9-135">コンソールに切り替える</span><span class="sxs-lookup"><span data-stu-id="f42a9-135">Switch to the Console</span></span>                                 | <span data-ttu-id="f42a9-136">**Ctrl**  + **2**</span><span class="sxs-lookup"><span data-stu-id="f42a9-136">**Ctrl** + **2**</span></span>           
<span data-ttu-id="f42a9-137">別の DevTools タブで本体を表示/非表示にする</span><span class="sxs-lookup"><span data-stu-id="f42a9-137">Show/hide the Console from another DevTools tab</span></span>       | <span data-ttu-id="f42a9-138">\*\*\*\*  +  Ctrl **&grave;**(バック ティック)</span><span class="sxs-lookup"><span data-stu-id="f42a9-138">**Ctrl** + **&grave;** (back tick)</span></span>  
<span data-ttu-id="f42a9-139">実行 (単一行コマンド)</span><span class="sxs-lookup"><span data-stu-id="f42a9-139">Execute (single-line command)</span></span>                     | **<span data-ttu-id="f42a9-140">Enter</span><span class="sxs-lookup"><span data-stu-id="f42a9-140">Enter</span></span>**                
<span data-ttu-id="f42a9-141">実行せずに行を折り返す (複数行のコマンド)</span><span class="sxs-lookup"><span data-stu-id="f42a9-141">Line break without executing (multi-line command)</span></span> | <span data-ttu-id="f42a9-142">**Shift**  + **Enter キー**または**Ctrl キーを**  +  **押す**</span><span class="sxs-lookup"><span data-stu-id="f42a9-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span></span>      
<span data-ttu-id="f42a9-143">すべてのメッセージのコンソールをクリアする</span><span class="sxs-lookup"><span data-stu-id="f42a9-143">Clear the Console of all messages</span></span>                 | <span data-ttu-id="f42a9-144">**Ctrl**  + **L**</span><span class="sxs-lookup"><span data-stu-id="f42a9-144">**Ctrl** + **L**</span></span>           
<span data-ttu-id="f42a9-145">フィルター ログ (フォーカスを検索ボックスに設定)</span><span class="sxs-lookup"><span data-stu-id="f42a9-145">Filter logs (set focus to search box)</span></span>             | <span data-ttu-id="f42a9-146">**Ctrl**  + **F**</span><span class="sxs-lookup"><span data-stu-id="f42a9-146">**Ctrl** + **F**</span></span>           
<span data-ttu-id="f42a9-147">オートコンプリート候補を受け入れる (フォーカスがある場合)</span><span class="sxs-lookup"><span data-stu-id="f42a9-147">Accept auto-completion suggestion (when in focus)</span></span> | <span data-ttu-id="f42a9-148">**Enter** キーまたは **Tab キー**</span><span class="sxs-lookup"><span data-stu-id="f42a9-148">**Enter** or **Tab**</span></span>       
<span data-ttu-id="f42a9-149">前/次の自動完了候補</span><span class="sxs-lookup"><span data-stu-id="f42a9-149">Previous/next auto-completion suggestion</span></span>          | <span data-ttu-id="f42a9-150">**上方向キー** /**下方向キー**</span><span class="sxs-lookup"><span data-stu-id="f42a9-150">**Up arrow key**/**Down arrow key**</span></span>   
