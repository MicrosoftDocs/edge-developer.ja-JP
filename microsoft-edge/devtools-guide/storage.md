---
description: '[記憶域] パネルを使用して、web ストレージ、IndexedDB、cookies、要求/応答キャッシュを検査する'
title: DevTools-ストレージ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、web storage、ローカルストレージ、セッションストレージ、indexeddb、cookie、service worker、キャッシュ
ms.custom: seodec18
ms.openlocfilehash: 8de6e1f90f86fa09b116646918c6be1d8cfb0a72
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569655"
---
# <span data-ttu-id="8870c-104">記憶域</span><span class="sxs-lookup"><span data-stu-id="8870c-104">Storage</span></span>

<span data-ttu-id="8870c-105">[**記憶域**] パネルを使用して、ローカルでキャッシュされているさまざまなデータを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="8870c-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>

 - <span data-ttu-id="8870c-106">[Web ストレージ](#local-and-session-storage-managers)(*ローカル*と*セッション*の記憶域) のキーと値のペア</span><span class="sxs-lookup"><span data-stu-id="8870c-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span></span>
 - <span data-ttu-id="8870c-107">[インデックス付きのデータベース](#indexeddb-manager)構造化データ</span><span class="sxs-lookup"><span data-stu-id="8870c-107">[Indexed DB](#indexeddb-manager) structured data</span></span>
 - <span data-ttu-id="8870c-108">ドメインの[cookie](#cookies-list)</span><span class="sxs-lookup"><span data-stu-id="8870c-108">[Cookies](#cookies-list) for the domain</span></span>
 - <span data-ttu-id="8870c-109">Service worker のデバッグの[キャッシュ](#cache-manager)(要求/応答のペア)</span><span class="sxs-lookup"><span data-stu-id="8870c-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span></span>

<span data-ttu-id="8870c-110">いずれかのカテゴリを展開し、子エントリをクリックして、[リソースマネージャー] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="8870c-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>

## <span data-ttu-id="8870c-111">ローカルとセッションのストレージマネージャー</span><span class="sxs-lookup"><span data-stu-id="8870c-111">Local and Session storage managers</span></span>

<span data-ttu-id="8870c-112">*ローカルストレージマネージャー*と*セッションストレージマネージャー*を使用して、ページの web ストレージを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="8870c-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span></span> 

<span data-ttu-id="8870c-113">ストレージパネルの[*リソースピッカー*](./debugger.md#resource-picker)内の**ローカルストレージ**と**セッションストレージ**フォルダーには、ページの原点の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span></span> <span data-ttu-id="8870c-114">これらのフレームのいずれかを選択すると、 [windows](https://developer.mozilla.org/docs/Web/API/Window/localStorage)によって設定された現在のキーと値のペアの編集可能なテーブルが開きます (または、「Devtools ストレージ[」](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)[リスト](#storage-list)から直接設定されています)。</span><span class="sxs-lookup"><span data-stu-id="8870c-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span></span>

![DevTools Cookies マネージャー](./media/storage_web_storage.png)

<span data-ttu-id="8870c-116">[*ローカルストレージ*] タブと [*セッションストレージ*] タブから、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8870c-116">From the *Local Storage* and *Session Storage* tabs you can:</span></span>

 - <span data-ttu-id="8870c-117">**Refresh** [ `Ctrl+F5` [記憶域] の一覧](#cookies-list)を更新して、指定したドメインの現在のキーと値のペアのセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="8870c-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span> <span data-ttu-id="8870c-118">(一覧は、スクリプトの更新時には自動更新されません)。</span><span class="sxs-lookup"><span data-stu-id="8870c-118">(The list does not auto-refresh upon script updates.)</span></span>
 - <span data-ttu-id="8870c-119">Microsoft Edge web storage の**記憶域の上限に達した**ことをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="8870c-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span></span> <span data-ttu-id="8870c-120">各ドメインとサブドメインには専用のストレージ領域がありますが、次のように、結合された制限があります。</span><span class="sxs-lookup"><span data-stu-id="8870c-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>
    - <span data-ttu-id="8870c-121">サブ**ドメイン:** 最大 5 mb のスペース</span><span class="sxs-lookup"><span data-stu-id="8870c-121">**Subdomains:** up to 5 MBs of space</span></span>
    - <span data-ttu-id="8870c-122">**ドメイン:** 最大 10 mb のスペース</span><span class="sxs-lookup"><span data-stu-id="8870c-122">**Domains:** up to 10 MBs of space</span></span>
    - <span data-ttu-id="8870c-123">**すべてのドメインの合計:** 最大 50 mb のスペース</span><span class="sxs-lookup"><span data-stu-id="8870c-123">**Total for all domains:** up to 50 MBs of space</span></span>

   <span data-ttu-id="8870c-124">セッションストレージは、その原点を参照している最後のブラウザータブが閉じられるとすぐに消去されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span> <span data-ttu-id="8870c-125">ローカル記憶域エントリは、ページによってプログラムによって、またはユーザーによって手動で削除されるまで無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>

   <span data-ttu-id="8870c-126">**設定**  > **閲覧データ**  >  をクリアする**Cookie と保存済みの web サイトデータ**</span><span class="sxs-lookup"><span data-stu-id="8870c-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

![Microsoft Edge の [設定] パネルで閲覧データをクリアする](./media/settings_clear_browsing_data.png)

### <span data-ttu-id="8870c-128">ストレージリスト</span><span class="sxs-lookup"><span data-stu-id="8870c-128">Storage list</span></span>

<span data-ttu-id="8870c-129">*ストレージリスト*テーブルからは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-129">From the *Storage list* table you can:</span></span>

 - <span data-ttu-id="8870c-130">テーブルのいずれかの列名をクリックして、キーと値のペアを**検査して並べ替え**ます。</span><span class="sxs-lookup"><span data-stu-id="8870c-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span></span>
 - <span data-ttu-id="8870c-131">セルをクリックして、既存のエントリの*キー*と*値*を**編集**します。</span><span class="sxs-lookup"><span data-stu-id="8870c-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span></span>
 - <span data-ttu-id="8870c-132">**Delete** `Del` 右クリックのコンテキストメニューオプションから [削除] を選び、[*アイテムの削除*] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8870c-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span></span>
 - <span data-ttu-id="8870c-133">表の下部にある空の行をクリックして、新しいキーと値のペアを**追加**します。</span><span class="sxs-lookup"><span data-stu-id="8870c-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span></span>


### <span data-ttu-id="8870c-134">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8870c-134">Shortcuts</span></span>

| <span data-ttu-id="8870c-135">操作</span><span class="sxs-lookup"><span data-stu-id="8870c-135">Action</span></span>              | <span data-ttu-id="8870c-136">キー</span><span class="sxs-lookup"><span data-stu-id="8870c-136">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="8870c-137">Refresh</span><span class="sxs-lookup"><span data-stu-id="8870c-137">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="8870c-138">項目の削除</span><span class="sxs-lookup"><span data-stu-id="8870c-138">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="8870c-139">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="8870c-139">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="8870c-140">すべて選択</span><span class="sxs-lookup"><span data-stu-id="8870c-140">Select all</span></span>          | `Ctrl` + `A`  |


## <span data-ttu-id="8870c-141">IndexedDB マネージャー</span><span class="sxs-lookup"><span data-stu-id="8870c-141">IndexedDB manager</span></span>

<span data-ttu-id="8870c-142">[ **Indexeddb** ] タブを使用して、クライアントコンピューターにローカルに保存されている構造化データを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="8870c-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span> <span data-ttu-id="8870c-143">具体的には、オブジェクトストアとインデックスを検査/並べ替え、更新することができます。また、個々のキーと値のエントリを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="8870c-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>

> [!TIP]
> <span data-ttu-id="8870c-144">[オーディオミキサー](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/)のデモを使用して、Microsoft Edge Devtools の*indexeddb manager*のドライブをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>

<span data-ttu-id="8870c-145">Microsoft Edge で現在のユーザー用に保存されているすべての IndexedDB データを削除するには、Microsoft Edge の [*設定*] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="8870c-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span></span>

<span data-ttu-id="8870c-146">**...** > **設定**  > **閲覧データ**  >  をクリアする**Cookie と保存済みの web サイトデータ**</span><span class="sxs-lookup"><span data-stu-id="8870c-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

<span data-ttu-id="8870c-147">デバッガーの[*リソースピッカー*](./debugger.md#resource-picker)内の**indexeddb**フォルダーには、ページによって読み込まれたリソースから元のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="8870c-148">任意の IndexedDB (.IDB) データベースは、そのオブジェクトストアと共に、元のリストに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span></span> 

![DevTools IndexedDB manager](./media/storage_indexeddb.png)

### <span data-ttu-id="8870c-150">IndexedDB ツールバー</span><span class="sxs-lookup"><span data-stu-id="8870c-150">IndexedDB Toolbar</span></span>

<span data-ttu-id="8870c-151">[ *Indexeddb* ] ツールバーから次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-151">From the *IndexedDB* toolbar you can:</span></span>

 - <span data-ttu-id="8870c-152">[**更新**] ( `Ctrl+F5` ) を選び、データベースのオブジェクトストアまたはインデックスの現在のエントリを表示します。</span><span class="sxs-lookup"><span data-stu-id="8870c-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span></span> <span data-ttu-id="8870c-153">データベースに変更が加えられても、IndexedDB manager は自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="8870c-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>

### <span data-ttu-id="8870c-154">オブジェクトストアのエントリの一覧</span><span class="sxs-lookup"><span data-stu-id="8870c-154">Object store entries list</span></span>

<span data-ttu-id="8870c-155">*オブジェクトストア*または*インデックス*テーブルから、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8870c-155">From the *Object store* or *Index* table you can:</span></span>

 - <span data-ttu-id="8870c-156">テーブル内の任意の列名をクリックして、キーと値のペアを**検査して並べ替え**ます。</span><span class="sxs-lookup"><span data-stu-id="8870c-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="8870c-157">**Refresh** ( `Ctrl+F5` )</span><span class="sxs-lookup"><span data-stu-id="8870c-157">**Refresh** (`Ctrl+F5`)</span></span>
 - <span data-ttu-id="8870c-158">[**アイテムの削除**] ( `Del` ) オブジェクトストアまたはインデックスで選んだエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="8870c-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span></span> <span data-ttu-id="8870c-159">この操作は、右クリックの[コンテキストメニュー](#context-menu)オプションの [アイテムの*削除*] でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="8870c-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span></span>
 - <span data-ttu-id="8870c-160">選択した**アイテムをコピー**する () 選択したアイテムを `Ctrl+C` クリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8870c-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span></span> <span data-ttu-id="8870c-161">また、右クリックの[コンテキストメニュー](#context-menu)オプションで、*選択したアイテムをコピー*することもできます。</span><span class="sxs-lookup"><span data-stu-id="8870c-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span></span>
 - <span data-ttu-id="8870c-162">**[すべて]** () を選択し `Ctrl+A` て、オブジェクトストアまたはインデックス内のすべてのエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="8870c-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span></span> <span data-ttu-id="8870c-163">また、右クリックの[コンテキストメニュー](#context-menu)オプションで *[すべて] を選択*することもできます。</span><span class="sxs-lookup"><span data-stu-id="8870c-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span></span>

<span data-ttu-id="8870c-164">*オブジェクトストア*または*インデックス*テーブルの列は、並べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="8870c-164">The columns of the *Object store* or *Index* table are sortable:</span></span>

<span data-ttu-id="8870c-165">列</span><span class="sxs-lookup"><span data-stu-id="8870c-165">Column</span></span> | <span data-ttu-id="8870c-166">説明</span><span class="sxs-lookup"><span data-stu-id="8870c-166">Description</span></span>
:------------ | :-------------
<span data-ttu-id="8870c-167">Key</span><span class="sxs-lookup"><span data-stu-id="8870c-167">Key</span></span> | <span data-ttu-id="8870c-168">オブジェクトストアを反復処理するときのキーと値のペアの名前 (*主キー*と同じ)。インデックスを反復処理するときのインデックスキー (カーソルの現在のキー) の名前</span><span class="sxs-lookup"><span data-stu-id="8870c-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span></span>
<span data-ttu-id="8870c-169">主キー</span><span class="sxs-lookup"><span data-stu-id="8870c-169">Primary Key</span></span> | <span data-ttu-id="8870c-170">キーと値のペアの名前 (「MDN[キー](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)の詳細については、「 *MDN web ドキュメント*」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="8870c-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span></span>
<span data-ttu-id="8870c-171">値</span><span class="sxs-lookup"><span data-stu-id="8870c-171">Value</span></span> | <span data-ttu-id="8870c-172">キーと値のペアの値</span><span class="sxs-lookup"><span data-stu-id="8870c-172">Value of the key-value pair</span></span>

<span data-ttu-id="8870c-173">[Indexeddb の概念と使い方](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)について詳しくは、 *「MDN web ドキュメント*」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8870c-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>

### <span data-ttu-id="8870c-174">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="8870c-174">Context menu</span></span>

<span data-ttu-id="8870c-175">[ [ *Indexeddb* ] ツールバー](#indexeddb-toolbar)に加えて、右クリックの**コンテキストメニュー**やキーボード[ショートカット](#shortcuts)から、オブジェクトストアまたはインデックスのデータを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8870c-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="8870c-176">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8870c-176">Shortcuts</span></span>

<span data-ttu-id="8870c-177">操作</span><span class="sxs-lookup"><span data-stu-id="8870c-177">Action</span></span> | <span data-ttu-id="8870c-178">キー</span><span class="sxs-lookup"><span data-stu-id="8870c-178">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="8870c-179">Refresh</span><span class="sxs-lookup"><span data-stu-id="8870c-179">Refresh</span></span> | `Ctrl` + `F5`
<span data-ttu-id="8870c-180">キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="8870c-180">Delete key-value pair</span></span> | `Del`
<span data-ttu-id="8870c-181">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="8870c-181">Copy selected items</span></span> | `Ctrl` + `C`
<span data-ttu-id="8870c-182">すべて選択</span><span class="sxs-lookup"><span data-stu-id="8870c-182">Select all</span></span> | `Ctrl` + `A`

## <span data-ttu-id="8870c-183">Cookies マネージャー</span><span class="sxs-lookup"><span data-stu-id="8870c-183">Cookies manager</span></span>

<span data-ttu-id="8870c-184">*Cookie マネージャー*を使用して、指定したドメインの cookie を検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="8870c-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span></span> 

<span data-ttu-id="8870c-185">デバッガーの[*リソースピッカー*](./debugger.md#resource-picker)内の**Cookies**フォルダーには、ページによって読み込まれたリソースからの元のリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="8870c-186">これらのフレームのいずれかを選択すると、 [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)ヘッダーで設定された現在の cookie、または script を使用して、指定したスクリプトを含む表が表示さ[れます。](https://developer.mozilla.org/docs/Web/API/Document/cookie)</span><span class="sxs-lookup"><span data-stu-id="8870c-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>

![DevTools Cookies マネージャー](./media/storage_cookies.png)

<span data-ttu-id="8870c-188">[ *Cookie* ] タブのツールバーから次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-188">From the *Cookies* tab toolbar you can:</span></span>

 - <span data-ttu-id="8870c-189">**Refresh**指定した `Ctrl+F5` ドメインの現在の cookie のセットを表示するには、[ [cookie] の一覧](#cookies-list)を更新します。</span><span class="sxs-lookup"><span data-stu-id="8870c-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span> <span data-ttu-id="8870c-190">(リストは自動更新されません)。</span><span class="sxs-lookup"><span data-stu-id="8870c-190">(The list does not auto-refresh.)</span></span>
 - <span data-ttu-id="8870c-191">**Delete all cookies** `Ctrl+Shift+Del` 現在のページのパスについて、すべての cookie () (セッションと永続的) を削除します。</span><span class="sxs-lookup"><span data-stu-id="8870c-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span></span>
 - <span data-ttu-id="8870c-192">現在のページのパスの**セッション cookie** ( `Ctrl+Del` ) をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="8870c-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span></span>

<span data-ttu-id="8870c-193">*Cookie リスト*を完全に消去するには、[**ネットワーク**](./network.md#toolbar)パネルのツールバーから**ドメインのすべての cookie をクリア**する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8870c-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span></span>

### <span data-ttu-id="8870c-194">Cookies リスト</span><span class="sxs-lookup"><span data-stu-id="8870c-194">Cookies list</span></span>

<span data-ttu-id="8870c-195">*Cookie リスト*テーブルからは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-195">From the *Cookies list* table you can:</span></span>

 - <span data-ttu-id="8870c-196">表の任意の列名をクリックして、cookie を**検査して並べ替え**ます。</span><span class="sxs-lookup"><span data-stu-id="8870c-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="8870c-197">セルをクリックして、既存の cookie の*名前*と*値*を**編集**します。</span><span class="sxs-lookup"><span data-stu-id="8870c-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span></span>
 - <span data-ttu-id="8870c-198">**Delete** `Del` 右クリックの[コンテキストメニュー](#context-menu)オプションから cookie を削除して、 *cookie を削除*します。</span><span class="sxs-lookup"><span data-stu-id="8870c-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span></span>
 - <span data-ttu-id="8870c-199">表の下部にある空の行をクリックして、指定した*ドメイン/パス*の新しいセッション Cookie を**追加**します。</span><span class="sxs-lookup"><span data-stu-id="8870c-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span></span> <span data-ttu-id="8870c-200">これは、セッション cookie に対してのみ有効です。永続的な cookie (特定の有効期限を含む) は、従来の方法で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8870c-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span></span> <span data-ttu-id="8870c-201">[*ドメイン*] と [ *Path* ] の値は、ページの場所に応じて自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="8870c-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span></span>

<span data-ttu-id="8870c-202">*Cookie リスト*の列は、並べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="8870c-202">The columns of the *Cookies list* are sortable:</span></span>

<span data-ttu-id="8870c-203">列</span><span class="sxs-lookup"><span data-stu-id="8870c-203">Column</span></span> | <span data-ttu-id="8870c-204">説明</span><span class="sxs-lookup"><span data-stu-id="8870c-204">Description</span></span>
:------------ | :-------------
<span data-ttu-id="8870c-205">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="8870c-205">Name</span></span> | <span data-ttu-id="8870c-206">Cookie の名前</span><span class="sxs-lookup"><span data-stu-id="8870c-206">Name of the cookie</span></span>
<span data-ttu-id="8870c-207">値</span><span class="sxs-lookup"><span data-stu-id="8870c-207">Value</span></span> | <span data-ttu-id="8870c-208">Cookie の値</span><span class="sxs-lookup"><span data-stu-id="8870c-208">Value of the cookie</span></span>
<span data-ttu-id="8870c-209">ドメイン</span><span class="sxs-lookup"><span data-stu-id="8870c-209">Domain</span></span> | <span data-ttu-id="8870c-210">Cookie のホスト名 (空の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="8870c-210">Host name of the cookie (may be empty)</span></span>
<span data-ttu-id="8870c-211">パス</span><span class="sxs-lookup"><span data-stu-id="8870c-211">Path</span></span> | <span data-ttu-id="8870c-212">Cookie の URL パス (空の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="8870c-212">URL path for the cookie (may be empty)</span></span>
<span data-ttu-id="8870c-213">有効期限</span><span class="sxs-lookup"><span data-stu-id="8870c-213">Expires</span></span> | <span data-ttu-id="8870c-214">HTTP 日付のタイムスタンプとしての cookie の最長有効期間。</span><span class="sxs-lookup"><span data-stu-id="8870c-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span> <span data-ttu-id="8870c-215">指定しなかった場合、 `Expires` または `Max-Age` 設定されていない場合、エントリは*セッション*cookie と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8870c-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span></span>
<span data-ttu-id="8870c-216">HTTP のみ</span><span class="sxs-lookup"><span data-stu-id="8870c-216">HTTP only</span></span> | <span data-ttu-id="8870c-217">Cookie がディレクティブで設定されたかどうかを示します。 `HttpOnly` これは JavaScript からアクセスできないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8870c-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span>
<span data-ttu-id="8870c-218">セキュリテイ保護</span><span class="sxs-lookup"><span data-stu-id="8870c-218">Secure</span></span> | <span data-ttu-id="8870c-219">Cookie がディレクティブで設定されたかどうかを示し `Secure` ます。これは、SSL と HTTPS プロトコルを使って要求された場合にのみサーバーに送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8870c-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>

<span data-ttu-id="8870c-220">Cookie のプロパティについて詳しくは、「 **MDN web ドキュメント**[セット-cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンス」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8870c-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>

### <span data-ttu-id="8870c-221">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="8870c-221">Context menu</span></span>

<span data-ttu-id="8870c-222">[ *Cookie* ] タブ[ツールバー](#cookies-manager)に加えて、右クリックの**コンテキストメニュー**やキーボード[ショートカット](#shortcuts)からも cookie を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8870c-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="8870c-223">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8870c-223">Shortcuts</span></span>

| <span data-ttu-id="8870c-224">操作</span><span class="sxs-lookup"><span data-stu-id="8870c-224">Action</span></span>                     | <span data-ttu-id="8870c-225">キー</span><span class="sxs-lookup"><span data-stu-id="8870c-225">Shortcut</span></span>                 |
|:---------------------------|:-------------------------|
| <span data-ttu-id="8870c-226">Refresh</span><span class="sxs-lookup"><span data-stu-id="8870c-226">Refresh</span></span>                    | `Ctrl` + `F5`            |
| <span data-ttu-id="8870c-227">Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="8870c-227">Delete cookie</span></span>              | `Del`                    |
| <span data-ttu-id="8870c-228">すべての cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="8870c-228">Delete all cookies</span></span>         | `Ctrl` + `Shift` + `Del` |
| <span data-ttu-id="8870c-229">すべてのセッション cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="8870c-229">Delete all session cookies</span></span> | `Ctrl` + `Del`           |
| <span data-ttu-id="8870c-230">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="8870c-230">Copy selected items</span></span>        | `Ctrl` + `C`             |
| <span data-ttu-id="8870c-231">すべて選択</span><span class="sxs-lookup"><span data-stu-id="8870c-231">Select all</span></span>                 | `Ctrl` + `A`             |

### <span data-ttu-id="8870c-232">キャッシュマネージャー</span><span class="sxs-lookup"><span data-stu-id="8870c-232">Cache manager</span></span>

<span data-ttu-id="8870c-233">特定のキャッシュエントリをクリックすると、service worker**キャッシュ**マネージャーが開きます。ここでは、キャッシュエントリ (*要求*と*応答*のキー/値のペア) を検査したり、必要に応じて削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="8870c-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span></span>

![キャッシュマネージャー](./media/storage_cache.png)

### <span data-ttu-id="8870c-235">ショートカット</span><span class="sxs-lookup"><span data-stu-id="8870c-235">Shortcuts</span></span>

#### <span data-ttu-id="8870c-236">キャッシュマネージャー</span><span class="sxs-lookup"><span data-stu-id="8870c-236">Cache manager</span></span>

| <span data-ttu-id="8870c-237">操作</span><span class="sxs-lookup"><span data-stu-id="8870c-237">Action</span></span>              | <span data-ttu-id="8870c-238">キー</span><span class="sxs-lookup"><span data-stu-id="8870c-238">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="8870c-239">Refresh</span><span class="sxs-lookup"><span data-stu-id="8870c-239">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="8870c-240">項目の削除</span><span class="sxs-lookup"><span data-stu-id="8870c-240">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="8870c-241">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="8870c-241">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="8870c-242">すべて選択</span><span class="sxs-lookup"><span data-stu-id="8870c-242">Select all</span></span>          | `Ctrl` + `A`  |
