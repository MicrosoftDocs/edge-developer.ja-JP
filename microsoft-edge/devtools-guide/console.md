---
description: 対話型のデバッグとアドホックテストには、コンソールツールを使います。
title: DevTools-本体
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、コンソール
ms.custom: seodec18
ms.openlocfilehash: f2733cac57ed5f2364747ee64e669fa83aae41f4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569713"
---
# <span data-ttu-id="0183e-104">Console</span><span class="sxs-lookup"><span data-stu-id="0183e-104">Console</span></span>

<span data-ttu-id="0183e-105">Microsoft Edge の本体開発者ツールは、JavaScript、ネットワーク要求、セキュリティエラーなどの web ページに関連付けられている情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="0183e-105">The Console developer tool in Microsoft Edge logs information that's associated with a webpage, such as JavaScript, network requests, and security errors.</span></span> <span data-ttu-id="0183e-106">この本体を使って対話型のデバッグとアドホックテストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0183e-106">You can use the Console for interactive debugging and ad hoc testing.</span></span> 

<span data-ttu-id="0183e-107">Microsoft Edge でコンソールツールを開くには、F12 キーを押して [開発者ツール] ウィンドウにアクセスします (またはページを右クリックして、[**要素の検査**] を選びます)。</span><span class="sxs-lookup"><span data-stu-id="0183e-107">To open the Console tool in Microsoft Edge, press the F12 key to access the developer tool window (or right-click on the page, and then select **Inspect Element**).</span></span> <span data-ttu-id="0183e-108">次に、ウィンドウの上部にある [**コンソール**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0183e-108">Then, select the **Console** tab at the top of the window.</span></span> 

<span data-ttu-id="0183e-109">また、コンソールツールを使って、実行中の web ページとの間で通信を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="0183e-109">You can also use the Console tool to communicate to and from a running webpage.</span></span> <span data-ttu-id="0183e-110">コンソールを使用して、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0183e-110">You can use the Console to:</span></span>

- <span data-ttu-id="0183e-111">コードの実行時に、標準の[エラー、状態コード](./console/error-and-status-codes.md)、情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0183e-111">Post standard [error and status codes](./console/error-and-status-codes.md) and informational messages as your code runs.</span></span>
- <span data-ttu-id="0183e-112">コードに含める[コンソール API](./console/console-api.md)呼び出しからカスタムデバッグログを生成します。</span><span class="sxs-lookup"><span data-stu-id="0183e-112">Generate custom debug logs from the [Console API](./console/console-api.md) calls you include in your code.</span></span>
- <span data-ttu-id="0183e-113">主要な変数と関数の現在の戻り値を検査するための[コマンドライン](./console/command-line.md)と対話型ツリービューを提供します。</span><span class="sxs-lookup"><span data-stu-id="0183e-113">Provide a [command line](./console/command-line.md) and interactive tree view for inspecting current return values of key variables and functions.</span></span>

## <span data-ttu-id="0183e-114">本体の一部</span><span class="sxs-lookup"><span data-stu-id="0183e-114">Parts of the Console</span></span>

<span data-ttu-id="0183e-115">次の図は、本体の主要な部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="0183e-115">The following image shows the key parts of the Console:</span></span>

![Microsoft Edge DevTools コンソール](./media/console.png)

1. <span data-ttu-id="0183e-117">**エラー**  / **警告**  / **情報**  / **ログ**ボタン: 指定した種類でコンソールの出力をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0183e-117">**Errors** / **Warnings** / **Info** / **Logs** buttons: Filter console output by the specified type.</span></span> <span data-ttu-id="0183e-118">**Ctrl**キーを押しながら複数のボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0183e-118">You can multi-select buttons by holding down the **Ctrl** key.</span></span> <span data-ttu-id="0183e-119">[**すべて**] ボタンをクリックすると、すべてのフィルターがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0183e-119">The **All** button clears all filters.</span></span>

2. <span data-ttu-id="0183e-120">**クリア**ボタン (**Ctrl + L**): [**クリア**] ボタンを押すと、現在のコンソールの表示がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0183e-120">**Clear** button (**Ctrl+L**): The **Clear** button clears the current console display.</span></span>

3. <span data-ttu-id="0183e-121">[**ログの保存**] チェックボックス: [ログの**保存**] チェックボックスをオンにすると、ページの更新後にコンソール出力が保持され、[devtools] を閉じて再び開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0183e-121">**Preserve Log** check box: Selecting the **Preserve Log** check box persists your console output across page refreshes and closing and reopening DevTools.</span></span> <span data-ttu-id="0183e-122">本体の履歴は、タブが閉じられたとき、またはコンソールを手動でクリアしたときにのみ消去されます。</span><span class="sxs-lookup"><span data-stu-id="0183e-122">The Console history clears only when the tab is closed or you manually clear the Console.</span></span>

4. <span data-ttu-id="0183e-123">[ **Target**]: [ **target** ] ドロップダウンメニューを使用して、 `<iframe>` ページ内の、または実行中の拡張機能など、別の実行コンテキストに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0183e-123">**Target**: Use the **Target** drop-down menu to switch to a different execution context, such as an `<iframe>` in your page or a running extension.</span></span> <span data-ttu-id="0183e-124">既定では、ページのトップレベルのフレームが選択されています。</span><span class="sxs-lookup"><span data-stu-id="0183e-124">By default, the top-level frame of your page is selected.</span></span> <span data-ttu-id="0183e-125">選択したフレームの上にマウスポインターを置くと、そのリソースの完全な URL を示すヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0183e-125">Hovering over a selected frame displays a tooltip that shows the full URL for that resource.</span></span>

5. <span data-ttu-id="0183e-126">**本体**  /  の表示[**コンソールを表示**しない] ボタン (**Ctrl** +  **&grave;** ): コンソールパネルに加えて、[**コンソールの**  /  **非表示**] ボタンを押して、その他の devtools パネルの下部にあるコンソールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0183e-126">**Show Console** / **Hide Console** button (**Ctrl**+ **&grave;** ): In addition to the Console panel, you can use the console from the bottom of any other DevTools panel by pressing the **Show Console** / **Hide Console** button.</span></span> <span data-ttu-id="0183e-127">このボタンは、DevTools がコンソールパネルで開いている場合は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="0183e-127">The button has no effect when DevTools is open to the Console panel.</span></span>
 
6. <span data-ttu-id="0183e-128">**フィルターログ**(**Ctrl + F**): 検索ボックス内の特定のテキスト文字列を使用してログをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="0183e-128">**Filter logs** (**Ctrl+F**) : You can also filter logs by using a specific text string in the search box.</span></span>

7. <span data-ttu-id="0183e-129">**デバッガー**: 青色のソースリンクを選択し、その特定のコード行に対して Devtools デバッガーを開いてさらに検査を行います。</span><span class="sxs-lookup"><span data-stu-id="0183e-129">**Debugger**: Select any blue source link to open the DevTools Debugger to that particular line of code for further inspection.</span></span>

## <span data-ttu-id="0183e-130">ショートカット</span><span class="sxs-lookup"><span data-stu-id="0183e-130">Shortcuts</span></span>

<span data-ttu-id="0183e-131">操作</span><span class="sxs-lookup"><span data-stu-id="0183e-131">Action</span></span>                                            | <span data-ttu-id="0183e-132">キー</span><span class="sxs-lookup"><span data-stu-id="0183e-132">Shortcut</span></span>               
:-------------------------------------------------| :----------------------
<span data-ttu-id="0183e-133">コンソールでフォーカスが置かれた DevTools の起動</span><span class="sxs-lookup"><span data-stu-id="0183e-133">Launch DevTools with Console in focus</span></span>             | <span data-ttu-id="0183e-134">**Ctrl キー**  + **Shift キー**  + **J**</span><span class="sxs-lookup"><span data-stu-id="0183e-134">**Ctrl** + **Shift** + **J**</span></span> 
<span data-ttu-id="0183e-135">コンソールに切り替える</span><span class="sxs-lookup"><span data-stu-id="0183e-135">Switch to the Console</span></span>                                 | <span data-ttu-id="0183e-136">**Ctrl キー**  + **2**</span><span class="sxs-lookup"><span data-stu-id="0183e-136">**Ctrl** + **2**</span></span>           
<span data-ttu-id="0183e-137">他の DevTools タブで本体の表示/非表示を切り替える</span><span class="sxs-lookup"><span data-stu-id="0183e-137">Show/hide the Console from another DevTools tab</span></span>       | <span data-ttu-id="0183e-138">**Ctrl キー**  +  **&grave;**(バックチック)</span><span class="sxs-lookup"><span data-stu-id="0183e-138">**Ctrl** + **&grave;** (back tick)</span></span>  
<span data-ttu-id="0183e-139">Execute (単一行コマンド)</span><span class="sxs-lookup"><span data-stu-id="0183e-139">Execute (single-line command)</span></span>                     | **<span data-ttu-id="0183e-140">Enter</span><span class="sxs-lookup"><span data-stu-id="0183e-140">Enter</span></span>**                
<span data-ttu-id="0183e-141">実行せずに改行する (複数行コマンド)</span><span class="sxs-lookup"><span data-stu-id="0183e-141">Line break without executing (multi-line command)</span></span> | <span data-ttu-id="0183e-142">**Shift キー**  + **Enter**キーまたは**Ctrl キー**  +  **を**押します。</span><span class="sxs-lookup"><span data-stu-id="0183e-142">**Shift** + **Enter** or **Ctrl** + **Enter**</span></span>      
<span data-ttu-id="0183e-143">すべてのメッセージの本体をクリアする</span><span class="sxs-lookup"><span data-stu-id="0183e-143">Clear the Console of all messages</span></span>                 | <span data-ttu-id="0183e-144">**Ctrl キー**  + **L**</span><span class="sxs-lookup"><span data-stu-id="0183e-144">**Ctrl** + **L**</span></span>           
<span data-ttu-id="0183e-145">フィルターログ (検索ボックスにフォーカスを設定)</span><span class="sxs-lookup"><span data-stu-id="0183e-145">Filter logs (set focus to search box)</span></span>             | <span data-ttu-id="0183e-146">**Ctrl キー**  + **F**</span><span class="sxs-lookup"><span data-stu-id="0183e-146">**Ctrl** + **F**</span></span>           
<span data-ttu-id="0183e-147">オートコンプリートの候補を承諾する (フォーカスが置かれているとき)</span><span class="sxs-lookup"><span data-stu-id="0183e-147">Accept auto-completion suggestion (when in focus)</span></span> | <span data-ttu-id="0183e-148">**Enter**または**Tab**</span><span class="sxs-lookup"><span data-stu-id="0183e-148">**Enter** or **Tab**</span></span>       
<span data-ttu-id="0183e-149">前と次のオートコンプリートの候補</span><span class="sxs-lookup"><span data-stu-id="0183e-149">Previous/next auto-completion suggestion</span></span>          | <span data-ttu-id="0183e-150">**上方向キー** /**下方向キー**</span><span class="sxs-lookup"><span data-stu-id="0183e-150">**Up arrow key**/**Down arrow key**</span></span>   


