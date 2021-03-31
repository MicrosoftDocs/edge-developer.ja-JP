---
description: '[記憶域] パネルを使用して、Web ストレージ、IndexedDB、Cookie、および要求/応答キャッシュを調べ'
title: 記憶域|DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, Web ストレージ, ローカル ストレージ, セッション ストレージ, indexeddb, cookie, Service worker, cache
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3e970ae0d8ca3a43a309eff7b77400aa3ced5b21
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398897"
---
# <a name="storage"></a><span data-ttu-id="1a98e-104">Storage</span><span class="sxs-lookup"><span data-stu-id="1a98e-104">Storage</span></span>

<span data-ttu-id="1a98e-105">[記憶域] **パネルを** 使用して、次を含むさまざまなローカル キャッシュ データを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>  

*   <span data-ttu-id="1a98e-106">[Web ストレージ](#local-and-session-storage-managers) \(Local と Session storage\) のキー/値のペア</span><span class="sxs-lookup"><span data-stu-id="1a98e-106">[Web storage](#local-and-session-storage-managers) \(Local and Session storage\) key/values pairs</span></span>  
*   <span data-ttu-id="1a98e-107">[インデックス付き DB](#indexeddb-manager) 構造化データ</span><span class="sxs-lookup"><span data-stu-id="1a98e-107">[Indexed DB](#indexeddb-manager) structured data</span></span>  
*   <span data-ttu-id="1a98e-108">[ドメイン](#cookies-list) の Cookie</span><span class="sxs-lookup"><span data-stu-id="1a98e-108">[Cookies](#cookies-list) for the domain</span></span>  
*   <span data-ttu-id="1a98e-109">[サービス](#cache-manager) ワーカーデバッグ用のキャッシュ \(request/response pairs\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-109">[Cache](#cache-manager) \(request/response pairs\) for service worker debugging</span></span>  

<span data-ttu-id="1a98e-110">これらのカテゴリを展開し、子エントリをクリックしてリソース マネージャー タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>  

## <a name="local-and-session-storage-managers"></a><span data-ttu-id="1a98e-111">ローカル ストレージ マネージャーとセッション ストレージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a98e-111">Local and Session storage managers</span></span>  

<span data-ttu-id="1a98e-112">ローカル ストレージ マネージャーとセッション ストレージ マネージャーを使用して、ページの Web ストレージを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-112">Use the Local Storage manager and Session Storage manager to inspect and manage the web storage for your page.</span></span>  

<span data-ttu-id="1a98e-113">[**記憶域] パネルの [リソース] ピ**ッカー内のローカル 記憶域フォルダーとセッション 記憶域[フォルダーには](./debugger.md#resource-picker)、ページの原点の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [Resource picker](./debugger.md#resource-picker) display a list of origins for the page.</span></span>  <span data-ttu-id="1a98e-114">これらのフレームのいずれかを選択すると [、Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) または [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)を介して設定された現在のキー/値ペアの編集可能なテーブルが開きます。\(および/または DevTools [Storage](#storage-list)リスト \から直接設定)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively \(and/or set directly from the  DevTools [Storage list](#storage-list)\).</span></span>  

![DevTools ストレージ マネージャー](./media/storage_web_storage.png)  

<span data-ttu-id="1a98e-116">[ローカル ストレージ] タブと [セッション ストレージ] タブでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-116">From the Local Storage and Session Storage tabs you can:</span></span>  

*   <span data-ttu-id="1a98e-117">**\(** `Ctrl+F5` \)[](#cookies-list)を更新して、指定されたドメインのキー/値ペアの現在のセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-117">**Refresh** \(`Ctrl+F5`\) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span>  <span data-ttu-id="1a98e-118">\(リストはスクリプトの更新時に自動更新されません。\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-118">\(The list does not auto-refresh upon script updates.\)</span></span>  
*   <span data-ttu-id="1a98e-119">Microsoft Edge **Web ストレージのストレージ制限に**達するシミュレーションを行います。</span><span class="sxs-lookup"><span data-stu-id="1a98e-119">**Simulate reaching the storage limit**  for Microsoft Edge web storage.</span></span>  <span data-ttu-id="1a98e-120">各ドメインとサブドメインには独自の記憶域があります。ただし、次の制限が組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="1a98e-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>  
    *   <span data-ttu-id="1a98e-121">**サブドメイン**: 最大 5 つの領域</span><span class="sxs-lookup"><span data-stu-id="1a98e-121">**Subdomains**:  up to 5 MBs of space</span></span>  
    *   <span data-ttu-id="1a98e-122">**ドメイン**: 最大 10 MB の領域</span><span class="sxs-lookup"><span data-stu-id="1a98e-122">**Domains**:  up to 10 MBs of space</span></span>  
    *   <span data-ttu-id="1a98e-123">**すべてのドメインの合計**: 最大 50 の容量</span><span class="sxs-lookup"><span data-stu-id="1a98e-123">**Total for all domains**:  up to 50 MBs of space</span></span>  

   <span data-ttu-id="1a98e-124">セッション ストレージは、その原点を参照する最後のブラウザー タブが閉じ次第クリアされます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span>  <span data-ttu-id="1a98e-125">ローカル ストレージ エントリは、ページによってプログラムによってクリアされるまで、またはユーザーが手動でクリアするまで、無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>  

   <span data-ttu-id="1a98e-126">**設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイトのデータ**</span><span class="sxs-lookup"><span data-stu-id="1a98e-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>  

![[Microsoft Edge の設定] パネルから閲覧データを消去する](./media/settings_clear_browsing_data.png)  

### <a name="storage-list"></a><span data-ttu-id="1a98e-128">記憶域リスト</span><span class="sxs-lookup"><span data-stu-id="1a98e-128">Storage list</span></span>  

<span data-ttu-id="1a98e-129">記憶域リスト テーブルから、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-129">From the Storage list table you can:</span></span>  

*   <span data-ttu-id="1a98e-130">**テーブルの列名** `key/value` をクリックして、ペアを調べ、並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="1a98e-130">**Inspect and sort** your `key/value` pairs by clicking on either column name in the table.</span></span>  
*   <span data-ttu-id="1a98e-131">**セル** を `Key` クリック `Value` して、既存のエントリを編集します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-131">**Edit** the `Key` and `Value` of an existing entry by clicking in the cell.</span></span>  
*   <span data-ttu-id="1a98e-132">**右** クリックのコンテキスト メニュー オプションの [アイテムの削除] から `Del` \( \) エントリ **を削除します**。</span><span class="sxs-lookup"><span data-stu-id="1a98e-132">**Delete** \(`Del`\) an entry from the right-click context menu option, **Delete item**.</span></span>  
*   <span data-ttu-id="1a98e-133">**テーブル** の下部 `key/value` にある空の行をクリックして、新しいペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-133">**Add** a new `key/value` pair by clicking on the empty row at the bottom of the table.</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="1a98e-134">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-134">Shortcuts</span></span>

| <span data-ttu-id="1a98e-135">操作</span><span class="sxs-lookup"><span data-stu-id="1a98e-135">Action</span></span> | <span data-ttu-id="1a98e-136">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-136">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1a98e-137">Refresh</span><span class="sxs-lookup"><span data-stu-id="1a98e-137">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="1a98e-138">項目の削除</span><span class="sxs-lookup"><span data-stu-id="1a98e-138">Delete item</span></span> | `Del` |  
| <span data-ttu-id="1a98e-139">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="1a98e-139">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="1a98e-140">すべて選択</span><span class="sxs-lookup"><span data-stu-id="1a98e-140">Select all</span></span> | `Ctrl`+`A` |  

## <a name="indexeddb-manager"></a><span data-ttu-id="1a98e-141">IndexedDB マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a98e-141">IndexedDB manager</span></span>  

<span data-ttu-id="1a98e-142">**[IndexedDB] タブを**使用して、クライアント コンピューターにローカルに格納されている構造化データを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span>  <span data-ttu-id="1a98e-143">具体的には、オブジェクト ストアとインデックスを検査/並べ替え、更新したり、個々のキー値エントリを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>  

> [!TIP]
> <span data-ttu-id="1a98e-144">オーディオ ミキサーのデモ [を使用して](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 、Microsoft Edge DevTools で *IndexedDB マネージャー* をテスト ドライブできます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="1a98e-145">Microsoft Edge の現在のユーザーに保存されている IndexedDB データを削除するには、[Microsoft Edge の設定] メニューを **使用** します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge **Settings** menu:</span></span>  

<span data-ttu-id="1a98e-146">**...** > **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイトのデータ**</span><span class="sxs-lookup"><span data-stu-id="1a98e-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>  

<span data-ttu-id="1a98e-147">デバッガーの Resource ピッカー内のフォルダーには、ページによって読み込まれたリソースの発生元 `IndexedDB` の一覧が表示されます。 [](./debugger.md#resource-picker)</span><span class="sxs-lookup"><span data-stu-id="1a98e-147">The `IndexedDB` folder inside the Debugger's [Resource picker](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span>  <span data-ttu-id="1a98e-148">IndexedDB \(IDB\) データベースは、オブジェクト ストアと共に原点の下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-148">Any IndexedDB \(IDB\) databases will be listed under the origin, along with their object stores.</span></span>  

![DevTools IndexedDB マネージャー](./media/storage_indexeddb.png)  

### <a name="indexeddb-toolbar"></a><span data-ttu-id="1a98e-150">IndexedDB ツールバー</span><span class="sxs-lookup"><span data-stu-id="1a98e-150">IndexedDB Toolbar</span></span>  

<span data-ttu-id="1a98e-151">IndexedDB ツールバーでは、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-151">From the IndexedDB toolbar you can:</span></span>  

*   <span data-ttu-id="1a98e-152">**\(** `Ctrl` + `F5` \) を更新して、データベースのオブジェクト ストアまたはインデックス内の現在のエントリを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-152">**Refresh** \(`Ctrl`+`F5`\) to see the current entries in the object store or index of your database.</span></span>  <span data-ttu-id="1a98e-153">データベースに変更を加えた場合、IndexedDB マネージャーは自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="1a98e-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>  

### <a name="object-store-entries-list"></a><span data-ttu-id="1a98e-154">オブジェクト ストアエントリの一覧</span><span class="sxs-lookup"><span data-stu-id="1a98e-154">Object store entries list</span></span>  

<span data-ttu-id="1a98e-155">オブジェクト ストアまたはインデックス テーブルから、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-155">From the Object store or Index table you can:</span></span>  

*   <span data-ttu-id="1a98e-156">**テーブル内の任意** の列名をクリックして、キーと値のペアを調べ、並べ替える。</span><span class="sxs-lookup"><span data-stu-id="1a98e-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>  
*   <span data-ttu-id="1a98e-157">**Refresh** \( `Ctrl` + `F5` \)</span><span class="sxs-lookup"><span data-stu-id="1a98e-157">**Refresh** \(`Ctrl`+`F5`\)</span></span>  
*   <span data-ttu-id="1a98e-158">**アイテム \(** \) を削除して、オブジェクト ストアまたはインデックスで選択 `Del` したエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-158">**Delete item** \(`Del`\) to remove the selected entry in your object store or index.</span></span>  <span data-ttu-id="1a98e-159">これを行うには、右クリックのコンテキスト メニュー オプションの [アイテム [の](#context-menu) 削除] **から行います**。</span><span class="sxs-lookup"><span data-stu-id="1a98e-159">You can also do this from the right-click [context menu](#context-menu) option, **Delete item**.</span></span>  
*   <span data-ttu-id="1a98e-160">**選択したアイテム**をコピー \( `Ctrl` + `C` \) して、選択したアイテムをクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1a98e-160">**Copy selected items** \(`Ctrl`+`C`\) to copy the selected item to your clipboard.</span></span>  <span data-ttu-id="1a98e-161">この操作は、右クリックのコンテキスト メニュー[](#context-menu)オプションの [選択したアイテムのコピー **] から実行することもできます**。</span><span class="sxs-lookup"><span data-stu-id="1a98e-161">You can also do this from the right-click [context menu](#context-menu) option, **Copy selected item**.</span></span>  
*   <span data-ttu-id="1a98e-162">**すべての \(** `Ctrl` + `A` \) を選択して、オブジェクト ストアまたはインデックス内のすべてのエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-162">**Select all** \(`Ctrl`+`A`\) to select all the entries in your object store or index.</span></span>  <span data-ttu-id="1a98e-163">これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [すべて選択]**から行います**。</span><span class="sxs-lookup"><span data-stu-id="1a98e-163">You can also do this from the right-click [context menu](#context-menu) option, **Select all**.</span></span>  

<span data-ttu-id="1a98e-164">オブジェクト ストアまたはインデックス テーブルの列は並べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="1a98e-164">The columns of the Object store or Index table are sortable:</span></span>  

| <span data-ttu-id="1a98e-165">列</span><span class="sxs-lookup"><span data-stu-id="1a98e-165">Column</span></span> | <span data-ttu-id="1a98e-166">説明</span><span class="sxs-lookup"><span data-stu-id="1a98e-166">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1a98e-167">キー</span><span class="sxs-lookup"><span data-stu-id="1a98e-167">Key</span></span> | <span data-ttu-id="1a98e-168">オブジェクト ストアを反復するときにキーと値のペア \( **主**キー \と同じ) の名前。インデックスを反復する場合のインデックス キー \(cursor の現在のキー\) の名前</span><span class="sxs-lookup"><span data-stu-id="1a98e-168">Name of the key-value pair \(same as **Primary Key**\) when iterating over an object store; Name of the index key \(cursor's current key\) when iterating over an index</span></span> |  
| <span data-ttu-id="1a98e-169">主キー</span><span class="sxs-lookup"><span data-stu-id="1a98e-169">Primary Key</span></span> | <span data-ttu-id="1a98e-170">キーと値のペアの名前 **\(IDB** キーの詳細については MDN Web [ドキュメントを参照](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-170">Name of the key-value pair \(see **MDN web docs** for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)\)</span></span> |  
| <span data-ttu-id="1a98e-171">設定値</span><span class="sxs-lookup"><span data-stu-id="1a98e-171">Value</span></span> | <span data-ttu-id="1a98e-172">キーと値のペアの値</span><span class="sxs-lookup"><span data-stu-id="1a98e-172">Value of the key-value pair</span></span> |  

<span data-ttu-id="1a98e-173">IndexedDB *の概念と* 使用方法の詳細については [、MDN Web ドキュメントを参照してください](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>  

### <a name="context-menu"></a><span data-ttu-id="1a98e-174">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="1a98e-174">Context menu</span></span>  

<span data-ttu-id="1a98e-175">[ *IndexedDB*](#indexeddb-toolbar)ツールバーに加えて、右クリックのコンテキスト メニューやキーボード ショートカットからオブジェクト ストアまたはインデックス内の データを[管理することもできます](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="1a98e-176">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-176">Shortcuts</span></span>

| <span data-ttu-id="1a98e-177">操作</span><span class="sxs-lookup"><span data-stu-id="1a98e-177">Action</span></span> | <span data-ttu-id="1a98e-178">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-178">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1a98e-179">Refresh</span><span class="sxs-lookup"><span data-stu-id="1a98e-179">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="1a98e-180">キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="1a98e-180">Delete key-value pair</span></span> | `Del` |  
| <span data-ttu-id="1a98e-181">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="1a98e-181">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="1a98e-182">すべて選択</span><span class="sxs-lookup"><span data-stu-id="1a98e-182">Select all</span></span> | `Ctrl +`<span data-ttu-id="1a98e-183">A'</span><span class="sxs-lookup"><span data-stu-id="1a98e-183">A\`</span></span> |  

## <a name="cookies-manager"></a><span data-ttu-id="1a98e-184">Cookie マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a98e-184">Cookies manager</span></span>  

<span data-ttu-id="1a98e-185">Cookie マネージャーを使用して、特定のドメインの Cookie を検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-185">Use the Cookies manager to inspect and manage the cookies for the given domain.</span></span>  

<span data-ttu-id="1a98e-186">デバッガーの Resource ピッカー内のフォルダーには、ページによって読み込まれたリソースの発生元 `Cookies` の一覧が表示されます。 [](./debugger.md#resource-picker)</span><span class="sxs-lookup"><span data-stu-id="1a98e-186">The `Cookies` folder inside the Debugger's [Resource picker](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span>  <span data-ttu-id="1a98e-187">これらのフレームのいずれかを選択すると [、HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) ヘッダーまたは Document.cookie を使用したスクリプトによって設定されている現在の Cookie を表す [テーブルが開きます](https://developer.mozilla.org/docs/Web/API/Document/cookie)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-187">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>  

![DevTools Cookie マネージャー](./media/storage_cookies.png)  

<span data-ttu-id="1a98e-189">[Cookie] タブ ツールバーから、次の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-189">From the Cookies tab toolbar you can:</span></span>  

*   <span data-ttu-id="1a98e-190">**\(** `Ctrl` + `F5` \) Cookie リスト[を更新して](#cookies-list)、指定されたドメインの現在の Cookie セットを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-190">**Refresh** \(`Ctrl`+`F5`\) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span>  <span data-ttu-id="1a98e-191">\(リストは自動更新されません。\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-191">\(The list does not auto-refresh.\)</span></span>  
*   <span data-ttu-id="1a98e-192">**現在のページの**パス `Ctrl` + `Shift` + `Del` のすべての Cookie \( \) \(session and permanent\) を削除します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-192">**Delete all cookies** \(`Ctrl`+`Shift`+`Del`\) \(session and permanent\) for the path of the current page.</span></span>  
*   <span data-ttu-id="1a98e-193">**現在のページのパス**のすべてのセッション `Ctrl` + `Del` Cookie \( \) を削除します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-193">**Delete all session cookies** \(`Ctrl`+`Del`\) for the path of the current page.</span></span>  

<span data-ttu-id="1a98e-194">Cookie リストを完全にクリアするには、[ネットワーク] パネル のツール バーからドメインのすべての Cookie をクリア[する必要があります](./network.md#toolbar)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-194">To completely clear your Cookies list, you might need to **Clear all cookies for the domain** from the [Network](./network.md#toolbar) panel toolbar.</span></span>  

### <a name="cookies-list"></a><span data-ttu-id="1a98e-195">Cookie リスト</span><span class="sxs-lookup"><span data-stu-id="1a98e-195">Cookies list</span></span>  

<span data-ttu-id="1a98e-196">Cookie リスト テーブルから、次の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-196">From the Cookies list table you can:</span></span>  

*   <span data-ttu-id="1a98e-197">**テーブル内の任意** の列名をクリックして、Cookie を調べ、並べ替える。</span><span class="sxs-lookup"><span data-stu-id="1a98e-197">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>  
*   <span data-ttu-id="1a98e-198">**セル** を `Name` クリック `Value` して、既存の Cookie を編集します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-198">**Edit** the `Name` and `Value` of an existing cookie by clicking in the cell.</span></span>  
*   <span data-ttu-id="1a98e-199">**右** クリックの `Del` コンテキスト メニュー オプションから \( \) cookie [を削除](#context-menu) します `Delete cookie` 。</span><span class="sxs-lookup"><span data-stu-id="1a98e-199">**Delete** \(`Del`\) a cookie from the right-click [context menu](#context-menu) option, `Delete cookie`.</span></span>  
*   <span data-ttu-id="1a98e-200">**表** の下部にある空の行をクリックして、指定したセッションの新しい Cookie `Domain/Path` を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-200">**Add** a new session cookie for the given `Domain/Path` by clicking on the empty row at the bottom of the table.</span></span>  <span data-ttu-id="1a98e-201">これはセッション Cookie でのみ機能します。永続的な Cookie \(特定の有効期限\を持つ) は、従来のメソッドで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a98e-201">This only works for session cookies; permanent cookies \(with specific expiry dates\) must be set with traditional methods.</span></span>  <span data-ttu-id="1a98e-202">ページ `Domain` の `Path` 場所に応じて、値と値が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-202">The `Domain` and `Path` values are auto-filled according to the location of the page.</span></span>  

<span data-ttu-id="1a98e-203">Cookie リストの列は並べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="1a98e-203">The columns of the Cookies list are sortable:</span></span>

| <span data-ttu-id="1a98e-204">列</span><span class="sxs-lookup"><span data-stu-id="1a98e-204">Column</span></span> | <span data-ttu-id="1a98e-205">説明</span><span class="sxs-lookup"><span data-stu-id="1a98e-205">Description</span></span> |  
| :--- | :--- |  
| <span data-ttu-id="1a98e-206">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="1a98e-206">Name</span></span> | <span data-ttu-id="1a98e-207">Cookie の名前</span><span class="sxs-lookup"><span data-stu-id="1a98e-207">Name of the cookie</span></span> |  
| <span data-ttu-id="1a98e-208">設定値</span><span class="sxs-lookup"><span data-stu-id="1a98e-208">Value</span></span> | <span data-ttu-id="1a98e-209">Cookie の値</span><span class="sxs-lookup"><span data-stu-id="1a98e-209">Value of the cookie</span></span> |  
| <span data-ttu-id="1a98e-210">ドメイン</span><span class="sxs-lookup"><span data-stu-id="1a98e-210">Domain</span></span> | <span data-ttu-id="1a98e-211">Cookie のホスト名 \(空の場合があります\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-211">Host name of the cookie \(may be empty\)</span></span> |  
| <span data-ttu-id="1a98e-212">パス</span><span class="sxs-lookup"><span data-stu-id="1a98e-212">Path</span></span> | <span data-ttu-id="1a98e-213">Cookie の URL パス \(空の場合があります\)</span><span class="sxs-lookup"><span data-stu-id="1a98e-213">URL path for the cookie \(may be empty\)</span></span> |  
| <span data-ttu-id="1a98e-214">有効期限</span><span class="sxs-lookup"><span data-stu-id="1a98e-214">Expires</span></span> | <span data-ttu-id="1a98e-215">HTTP 日付タイムスタンプとしての Cookie の最大有効期間。</span><span class="sxs-lookup"><span data-stu-id="1a98e-215">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span>  <span data-ttu-id="1a98e-216">いいえまたは `Expires` 設定 `Max-Age` されている場合、エントリはセッション Cookie と見なされます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-216">If no `Expires` or `Max-Age` was set, the entry is considered a Session cookie.</span></span>  |  
| <span data-ttu-id="1a98e-217">HTTP のみ</span><span class="sxs-lookup"><span data-stu-id="1a98e-217">HTTP only</span></span> | <span data-ttu-id="1a98e-218">Cookie がディレクティブと一緒に設定されたかどうかを示し、JavaScript からアクセスできない `HttpOnly` ことを示します。</span><span class="sxs-lookup"><span data-stu-id="1a98e-218">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span> |  
| <span data-ttu-id="1a98e-219">セキュリテイ保護</span><span class="sxs-lookup"><span data-stu-id="1a98e-219">Secure</span></span> | <span data-ttu-id="1a98e-220">Cookie がディレクティブと一緒に設定されたかどうかを示し、SSL と HTTPS プロトコルを使用した要求からのみサーバー `Secure` に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-220">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>  |  

<span data-ttu-id="1a98e-221">Cookie プロパティ**の詳細については、MDN Web ドキュメント**[の Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a98e-221">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>  

### <a name="context-menu"></a><span data-ttu-id="1a98e-222">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="1a98e-222">Context menu</span></span>  

<span data-ttu-id="1a98e-223">[Cookie] タブ ツールバー[に加えて](#cookies-manager)、右クリックのコンテキスト メニューやキーボード ショートカットから Cookie を[管理することもできます](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="1a98e-223">In addition to the Cookies tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="1a98e-224">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-224">Shortcuts</span></span>  

| <span data-ttu-id="1a98e-225">操作</span><span class="sxs-lookup"><span data-stu-id="1a98e-225">Action</span></span> | <span data-ttu-id="1a98e-226">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-226">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1a98e-227">Refresh</span><span class="sxs-lookup"><span data-stu-id="1a98e-227">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="1a98e-228">Cookie の削除</span><span class="sxs-lookup"><span data-stu-id="1a98e-228">Delete cookie</span></span> | `Del` |  
| <span data-ttu-id="1a98e-229">すべての Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="1a98e-229">Delete all cookies</span></span> | `Ctrl`+`Shift`+`Del` |  
| <span data-ttu-id="1a98e-230">すべてのセッション Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="1a98e-230">Delete all session cookies</span></span> | `Ctrl`+`Del` |  
| <span data-ttu-id="1a98e-231">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="1a98e-231">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="1a98e-232">すべて選択</span><span class="sxs-lookup"><span data-stu-id="1a98e-232">Select all</span></span> | `Ctrl`+`A` |  

### <a name="cache-manager"></a><span data-ttu-id="1a98e-233">キャッシュ マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a98e-233">Cache manager</span></span>  

<span data-ttu-id="1a98e-234">特定のキャッシュ エントリをクリックすると、サービス ワーカー のキャッシュ マネージャーが開き、キャッシュ エントリ \( とキー/値のペア\) を検査して必要に応じて `Request` `Response` 削除できます。</span><span class="sxs-lookup"><span data-stu-id="1a98e-234">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries \(`Request` and `Response` key/value pairs\):</span></span>  

![キャッシュ マネージャー](./media/storage_cache.png)  

### <a name="shortcuts"></a><span data-ttu-id="1a98e-236">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-236">Shortcuts</span></span>  

#### <a name="cache-manager"></a><span data-ttu-id="1a98e-237">キャッシュ マネージャー</span><span class="sxs-lookup"><span data-stu-id="1a98e-237">Cache manager</span></span>  

| <span data-ttu-id="1a98e-238">操作</span><span class="sxs-lookup"><span data-stu-id="1a98e-238">Action</span></span> | <span data-ttu-id="1a98e-239">ショートカット</span><span class="sxs-lookup"><span data-stu-id="1a98e-239">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1a98e-240">Refresh</span><span class="sxs-lookup"><span data-stu-id="1a98e-240">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="1a98e-241">項目の削除</span><span class="sxs-lookup"><span data-stu-id="1a98e-241">Delete item</span></span> | `Del` |  
| <span data-ttu-id="1a98e-242">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="1a98e-242">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="1a98e-243">すべて選択</span><span class="sxs-lookup"><span data-stu-id="1a98e-243">Select all</span></span> | `Ctrl`+`A` |  
