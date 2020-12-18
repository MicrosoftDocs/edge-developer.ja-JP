---
description: ストレージ パネルを使用して、Web ストレージ、IndexedDB、Cookie、要求/応答キャッシュを検査する
title: DevTools - ストレージ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, Web ストレージ, ローカル ストレージ, セッション ストレージ, indexeddb, Cookie, サービス ワーカー, キャッシュ
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 90a2e2fdb0f329c3d83f52beb9eba169bdd48520
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234441"
---
# <span data-ttu-id="a41e5-104">記憶域</span><span class="sxs-lookup"><span data-stu-id="a41e5-104">Storage</span></span>

<span data-ttu-id="a41e5-105">記憶域パネル **を使用** して、ローカルにキャッシュされたさまざまなデータ (以下を含む) を検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>

 - <span data-ttu-id="a41e5-106">[Web ストレージ](#local-and-session-storage-managers)(*ローカルストレージ\*\*とセッション*ストレージ) のキー/値のペア</span><span class="sxs-lookup"><span data-stu-id="a41e5-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span></span>
 - <span data-ttu-id="a41e5-107">[インデックス付き DB](#indexeddb-manager) 構造化データ</span><span class="sxs-lookup"><span data-stu-id="a41e5-107">[Indexed DB](#indexeddb-manager) structured data</span></span>
 - <span data-ttu-id="a41e5-108">[ドメイン](#cookies-list) の Cookie</span><span class="sxs-lookup"><span data-stu-id="a41e5-108">[Cookies](#cookies-list) for the domain</span></span>
 - <span data-ttu-id="a41e5-109">[サービス](#cache-manager) ワーカー デバッグ用のキャッシュ (要求と応答のペア)</span><span class="sxs-lookup"><span data-stu-id="a41e5-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span></span>

<span data-ttu-id="a41e5-110">これらのカテゴリを展開し、子エントリをクリックしてリソース マネージャー タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>

## <span data-ttu-id="a41e5-111">ローカルおよびセッション の記憶域マネージャー</span><span class="sxs-lookup"><span data-stu-id="a41e5-111">Local and Session storage managers</span></span>

<span data-ttu-id="a41e5-112">ローカル ストレージ *マネージャーと* セッション ストレージ マネージャー *を使用して、* ページの Web ストレージを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span></span> 

<span data-ttu-id="a41e5-113">記憶域**パネルの**リソース**ピッカー内**のローカル ストレージ[\*\*](./debugger.md#resource-picker)フォルダーとセッション ストレージ フォルダーには、ページの作成元の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span></span> <span data-ttu-id="a41e5-114">これらのフレームのいずれかを選択すると [、Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) または [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)を介して設定された現在のキー/値ペアの編集可能なテーブルが開きます (また、DevTools [Storage](#storage-list)リストから直接設定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="a41e5-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span></span>

![DevTools ローカル ストレージ マネージャー](./media/storage_web_storage.png)

<span data-ttu-id="a41e5-116">[ *ローカル ストレージ] タブと [* セッション *ストレージ] タブから、* 次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-116">From the *Local Storage* and *Session Storage* tabs you can:</span></span>

 - <span data-ttu-id="a41e5-117">**指定** した `Ctrl+F5` ドメインの [キーと](#cookies-list) 値のペアの現在のセットを表示するには、ストレージ リストを更新 () します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span> <span data-ttu-id="a41e5-118">(この一覧は、スクリプトの更新時に自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="a41e5-118">(The list does not auto-refresh upon script updates.)</span></span>
 - <span data-ttu-id="a41e5-119">Microsoft Edge **Web ストレージの記憶域制限**に達するシミュレーション。</span><span class="sxs-lookup"><span data-stu-id="a41e5-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span></span> <span data-ttu-id="a41e5-120">各ドメインとサブドメインには独自の記憶域が用意されています。ただし、次の制限を組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>
    - <span data-ttu-id="a41e5-121">**サブドメイン:** 最大 5 つの領域</span><span class="sxs-lookup"><span data-stu-id="a41e5-121">**Subdomains:** up to 5 MBs of space</span></span>
    - <span data-ttu-id="a41e5-122">**ドメイン:** 最大 10 の領域</span><span class="sxs-lookup"><span data-stu-id="a41e5-122">**Domains:** up to 10 MBs of space</span></span>
    - <span data-ttu-id="a41e5-123">**すべてのドメインの合計:** 最大 50 の領域</span><span class="sxs-lookup"><span data-stu-id="a41e5-123">**Total for all domains:** up to 50 MBs of space</span></span>

   <span data-ttu-id="a41e5-124">セッション ストレージは、その原点を参照する最後のブラウザー タブが閉じたらすぐにクリアされます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span> <span data-ttu-id="a41e5-125">ローカル ストレージ エントリは、ページによってプログラムによってクリアされるまで、またはユーザーが手動でクリアするまで、無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>

   <span data-ttu-id="a41e5-126">**設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイト データ**</span><span class="sxs-lookup"><span data-stu-id="a41e5-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

![Microsoft Edge の [設定] パネルから閲覧データをクリアする](./media/settings_clear_browsing_data.png)

### <span data-ttu-id="a41e5-128">記憶域リスト</span><span class="sxs-lookup"><span data-stu-id="a41e5-128">Storage list</span></span>

<span data-ttu-id="a41e5-129">記憶域の *一覧の表から* 、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-129">From the *Storage list* table you can:</span></span>

 - <span data-ttu-id="a41e5-130">**テーブルの列名** をクリックして、キーと値のペアを調べ、並べ替える。</span><span class="sxs-lookup"><span data-stu-id="a41e5-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span></span>
 - <span data-ttu-id="a41e5-131">**セル** を *クリック* して *、* 既存のエントリのキーと値を編集します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span></span>
 - <span data-ttu-id="a41e5-132">**Delete** ( `Del` ) an entry from the right-click context menu option, Delete *item*.</span><span class="sxs-lookup"><span data-stu-id="a41e5-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span></span>
 - <span data-ttu-id="a41e5-133">**表** の下部にある空の行をクリックして、新しいキーと値のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span></span>


### <span data-ttu-id="a41e5-134">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-134">Shortcuts</span></span>

| <span data-ttu-id="a41e5-135">操作</span><span class="sxs-lookup"><span data-stu-id="a41e5-135">Action</span></span>              | <span data-ttu-id="a41e5-136">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-136">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="a41e5-137">Refresh</span><span class="sxs-lookup"><span data-stu-id="a41e5-137">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="a41e5-138">項目の削除</span><span class="sxs-lookup"><span data-stu-id="a41e5-138">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="a41e5-139">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="a41e5-139">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="a41e5-140">すべて選択</span><span class="sxs-lookup"><span data-stu-id="a41e5-140">Select all</span></span>          | `Ctrl` + `A`  |


## <span data-ttu-id="a41e5-141">IndexedDB マネージャー</span><span class="sxs-lookup"><span data-stu-id="a41e5-141">IndexedDB manager</span></span>

<span data-ttu-id="a41e5-142">**[IndexedDB] タブを使用**して、クライアント コンピューターにローカルに格納されている構造化データを検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span> <span data-ttu-id="a41e5-143">具体的には、オブジェクト ストアとインデックスを検査/並べ替え、更新したり、個々のキー値エントリを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>

> [!TIP]
> <span data-ttu-id="a41e5-144">Audio Mixer デモを [使って](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 、Microsoft Edge DevTools で *IndexedDB マネージャー* をテストできます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>

<span data-ttu-id="a41e5-145">Microsoft Edge で現在のユーザーに保存されている IndexedDB データを削除するには、[Microsoft Edge の設定] メニューを *使用* します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span></span>

<span data-ttu-id="a41e5-146">**...** > **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイト データ**</span><span class="sxs-lookup"><span data-stu-id="a41e5-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

<span data-ttu-id="a41e5-147">デバッガーのリソース ピッカー内の**IndexedDB**フォルダーには、ページによって読み込まれたリソースからのオリジンの一覧が表示されます。 [\*\*](./debugger.md#resource-picker)</span><span class="sxs-lookup"><span data-stu-id="a41e5-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="a41e5-148">IndexedDB (IDB) データベースは、そのオブジェクト ストアと共に、作成元の下に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span></span> 

![DevTools IndexedDB マネージャー](./media/storage_indexeddb.png)

### <span data-ttu-id="a41e5-150">IndexedDB ツール バー</span><span class="sxs-lookup"><span data-stu-id="a41e5-150">IndexedDB Toolbar</span></span>

<span data-ttu-id="a41e5-151">*IndexedDB ツール バーから、* 次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-151">From the *IndexedDB* toolbar you can:</span></span>

 - <span data-ttu-id="a41e5-152">**データベース** のオブジェクト ストアまたはインデックスの現在のエントリを表示するには `Ctrl+F5` 、() を更新します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span></span> <span data-ttu-id="a41e5-153">データベースに変更を加えた場合、IndexedDB マネージャーは自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="a41e5-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>

### <span data-ttu-id="a41e5-154">オブジェクト ストアエントリリスト</span><span class="sxs-lookup"><span data-stu-id="a41e5-154">Object store entries list</span></span>

<span data-ttu-id="a41e5-155">オブジェクト ストア*またはインデックス テーブル\*\*から*、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-155">From the *Object store* or *Index* table you can:</span></span>

 - <span data-ttu-id="a41e5-156">**テーブル内の任意** の列名をクリックして、キーと値のペアを調べ、並べ替える。</span><span class="sxs-lookup"><span data-stu-id="a41e5-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="a41e5-157">**Refresh** ( `Ctrl+F5` )</span><span class="sxs-lookup"><span data-stu-id="a41e5-157">**Refresh** (`Ctrl+F5`)</span></span>
 - <span data-ttu-id="a41e5-158">**アイテム** ( `Del` ) を削除して、オブジェクト ストアまたはインデックスで選択されているエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span></span> <span data-ttu-id="a41e5-159">これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [アイテムの削除]*をクリックします*。</span><span class="sxs-lookup"><span data-stu-id="a41e5-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span></span>
 - <span data-ttu-id="a41e5-160">**選択した項目** ( `Ctrl+C` ) をコピーして、選択した項目をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a41e5-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span></span> <span data-ttu-id="a41e5-161">これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [選択した項目をコピー*する] をクリックします*。</span><span class="sxs-lookup"><span data-stu-id="a41e5-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span></span>
 - <span data-ttu-id="a41e5-162">**オブジェクト ストア** またはインデックス内のすべてのエントリを選択するには、[すべて] `Ctrl+A` () を選択します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span></span> <span data-ttu-id="a41e5-163">これを行うには、右クリックのコンテキスト メニュー オプションの [すべて [選択](#context-menu) ] *をクリックします*。</span><span class="sxs-lookup"><span data-stu-id="a41e5-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span></span>

<span data-ttu-id="a41e5-164">オブジェクト ストアまたは*インデックス テーブルの列\*\*は*並べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="a41e5-164">The columns of the *Object store* or *Index* table are sortable:</span></span>

<span data-ttu-id="a41e5-165">列</span><span class="sxs-lookup"><span data-stu-id="a41e5-165">Column</span></span> | <span data-ttu-id="a41e5-166">説明</span><span class="sxs-lookup"><span data-stu-id="a41e5-166">Description</span></span>
:------------ | :-------------
<span data-ttu-id="a41e5-167">キー</span><span class="sxs-lookup"><span data-stu-id="a41e5-167">Key</span></span> | <span data-ttu-id="a41e5-168">オブジェクト ストアを反復する場合のキーと\*\* 値のペアの名前 (主キーと同じ)インデックスを反復する場合のインデックス キーの名前 (カーソルの現在のキー)</span><span class="sxs-lookup"><span data-stu-id="a41e5-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span></span>
<span data-ttu-id="a41e5-169">主キー</span><span class="sxs-lookup"><span data-stu-id="a41e5-169">Primary Key</span></span> | <span data-ttu-id="a41e5-170">キーと値のペアの名前 *(IDB*キーの詳細については MDN Web ドキュメントを参照[)](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)</span><span class="sxs-lookup"><span data-stu-id="a41e5-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span></span>
<span data-ttu-id="a41e5-171">設定値</span><span class="sxs-lookup"><span data-stu-id="a41e5-171">Value</span></span> | <span data-ttu-id="a41e5-172">キーと値のペアの値</span><span class="sxs-lookup"><span data-stu-id="a41e5-172">Value of the key-value pair</span></span>

<span data-ttu-id="a41e5-173">IndexedDB *の概念と* 使用方法について詳しくは、MDN の Web [ドキュメントをご覧ください](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。</span><span class="sxs-lookup"><span data-stu-id="a41e5-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>

### <span data-ttu-id="a41e5-174">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="a41e5-174">Context menu</span></span>

<span data-ttu-id="a41e5-175">[ *IndexedDB*](#indexeddb-toolbar)ツール バーに加えて、右クリックのコンテキスト メニューやキーボード ショートカットからオブジェクト ストアまたはインデックス\*\*\*\* 内のデータを[管理することもできます](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="a41e5-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="a41e5-176">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-176">Shortcuts</span></span>

<span data-ttu-id="a41e5-177">操作</span><span class="sxs-lookup"><span data-stu-id="a41e5-177">Action</span></span> | <span data-ttu-id="a41e5-178">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-178">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="a41e5-179">Refresh</span><span class="sxs-lookup"><span data-stu-id="a41e5-179">Refresh</span></span> | `Ctrl` + `F5`
<span data-ttu-id="a41e5-180">キーと値のペアを削除する</span><span class="sxs-lookup"><span data-stu-id="a41e5-180">Delete key-value pair</span></span> | `Del`
<span data-ttu-id="a41e5-181">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="a41e5-181">Copy selected items</span></span> | `Ctrl` + `C`
<span data-ttu-id="a41e5-182">すべて選択</span><span class="sxs-lookup"><span data-stu-id="a41e5-182">Select all</span></span> | `Ctrl` + `A`

## <span data-ttu-id="a41e5-183">Cookie マネージャー</span><span class="sxs-lookup"><span data-stu-id="a41e5-183">Cookies manager</span></span>

<span data-ttu-id="a41e5-184">Cookie マネージャー *を使用して* 、特定のドメインの Cookie を検査および管理します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span></span> 

<span data-ttu-id="a41e5-185">デバッガー **の** リソース ピッカー内の Cookie フォルダーには [*、ページによって*](./debugger.md#resource-picker) 読み込まれたリソースからのオリジンの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="a41e5-186">これらのフレームのいずれかを選択すると [、HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) ヘッダーまたは Document.cookie を使用したスクリプトによって設定された現在の Cookie を表すテーブル [が開きます](https://developer.mozilla.org/docs/Web/API/Document/cookie)。</span><span class="sxs-lookup"><span data-stu-id="a41e5-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>

![DevTools Cookie マネージャー](./media/storage_cookies.png)

<span data-ttu-id="a41e5-188">*[Cookie] タブの*ツール バーから、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-188">From the *Cookies* tab toolbar you can:</span></span>

 - <span data-ttu-id="a41e5-189">**Cookie**リスト `Ctrl+F5` を[](#cookies-list)更新 () して、特定のドメインの Cookie の現在のセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span> <span data-ttu-id="a41e5-190">(リストは自動更新されません。</span><span class="sxs-lookup"><span data-stu-id="a41e5-190">(The list does not auto-refresh.)</span></span>
 - <span data-ttu-id="a41e5-191">**現在のページの** パスのすべての Cookie `Ctrl+Shift+Del` ( ) (セッションおよび永続) を削除します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span></span>
 - <span data-ttu-id="a41e5-192">**現在のページのパス** のすべてのセッション Cookie ( `Ctrl+Del` ) を削除します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span></span>

<span data-ttu-id="a41e5-193">Cookie リストを完全に*クリアするには*、[ネットワーク パネル\*\*\*\*] ツール バーからドメインのすべての Cookie をクリアする必要[**がある**](./network.md#toolbar)場合があります。</span><span class="sxs-lookup"><span data-stu-id="a41e5-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span></span>

### <span data-ttu-id="a41e5-194">Cookie リスト</span><span class="sxs-lookup"><span data-stu-id="a41e5-194">Cookies list</span></span>

<span data-ttu-id="a41e5-195">Cookie リスト *の表から、* 次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-195">From the *Cookies list* table you can:</span></span>

 - <span data-ttu-id="a41e5-196">**テーブル内の任意** の列名をクリックして、Cookie を検査して並べ替える。</span><span class="sxs-lookup"><span data-stu-id="a41e5-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="a41e5-197">**セル** を *クリック* して *、* 既存の Cookie の名前と値を編集します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span></span>
 - <span data-ttu-id="a41e5-198">**右**クリック `Del` のコンテキスト メニュー オプションから[](#context-menu)Cookie を削除 () します。Cookie*を削除します*。</span><span class="sxs-lookup"><span data-stu-id="a41e5-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span></span>
 - <span data-ttu-id="a41e5-199">**表** の下部にある空の行をクリックして、指定したドメイン */* パスの新しいセッション Cookie を追加します。</span><span class="sxs-lookup"><span data-stu-id="a41e5-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span></span> <span data-ttu-id="a41e5-200">これはセッション Cookie でのみ機能します。永続的な Cookie (特定の有効期限がある場合) は、従来の方法で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a41e5-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span></span> <span data-ttu-id="a41e5-201">Domain *と* *Path の値* は、ページの場所に従って自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span></span>

<span data-ttu-id="a41e5-202">Cookie リストの列 *は並* べ替え可能です。</span><span class="sxs-lookup"><span data-stu-id="a41e5-202">The columns of the *Cookies list* are sortable:</span></span>

<span data-ttu-id="a41e5-203">列</span><span class="sxs-lookup"><span data-stu-id="a41e5-203">Column</span></span> | <span data-ttu-id="a41e5-204">説明</span><span class="sxs-lookup"><span data-stu-id="a41e5-204">Description</span></span>
:------------ | :-------------
<span data-ttu-id="a41e5-205">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="a41e5-205">Name</span></span> | <span data-ttu-id="a41e5-206">Cookie の名前</span><span class="sxs-lookup"><span data-stu-id="a41e5-206">Name of the cookie</span></span>
<span data-ttu-id="a41e5-207">設定値</span><span class="sxs-lookup"><span data-stu-id="a41e5-207">Value</span></span> | <span data-ttu-id="a41e5-208">Cookie の値</span><span class="sxs-lookup"><span data-stu-id="a41e5-208">Value of the cookie</span></span>
<span data-ttu-id="a41e5-209">ドメイン</span><span class="sxs-lookup"><span data-stu-id="a41e5-209">Domain</span></span> | <span data-ttu-id="a41e5-210">Cookie のホスト名 (空の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="a41e5-210">Host name of the cookie (may be empty)</span></span>
<span data-ttu-id="a41e5-211">パス</span><span class="sxs-lookup"><span data-stu-id="a41e5-211">Path</span></span> | <span data-ttu-id="a41e5-212">Cookie の URL パス (空の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="a41e5-212">URL path for the cookie (may be empty)</span></span>
<span data-ttu-id="a41e5-213">有効期限</span><span class="sxs-lookup"><span data-stu-id="a41e5-213">Expires</span></span> | <span data-ttu-id="a41e5-214">HTTP 日付タイムスタンプとしての Cookie の最大有効期間。</span><span class="sxs-lookup"><span data-stu-id="a41e5-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span> <span data-ttu-id="a41e5-215">指定がない `Expires` 場合 `Max-Age` 、または設定されている場合、エントリはセッション Cookie *と見な* されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span></span>
<span data-ttu-id="a41e5-216">HTTP のみ</span><span class="sxs-lookup"><span data-stu-id="a41e5-216">HTTP only</span></span> | <span data-ttu-id="a41e5-217">Cookie がディレクティブで設定されたかどうかを示します `HttpOnly` 。JavaScript からアクセスできないかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="a41e5-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span>
<span data-ttu-id="a41e5-218">セキュリテイ保護</span><span class="sxs-lookup"><span data-stu-id="a41e5-218">Secure</span></span> | <span data-ttu-id="a41e5-219">Cookie がディレクティブと一緒に設定されたかどうかを示します。これは、SSL と HTTPS プロトコルを使用した要求からのみサーバー `Secure` に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>

<span data-ttu-id="a41e5-220">Cookie プロパティ**の詳細については、MDN Web ドキュメント**[の Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41e5-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>

### <span data-ttu-id="a41e5-221">ショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="a41e5-221">Context menu</span></span>

<span data-ttu-id="a41e5-222">[Cookie] タブ*の*[ツール](#cookies-manager)バーに加えて、右クリックのコンテキスト メニュー\*\*\*\* やキーボード ショートカットから Cookie を[管理することもできます](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="a41e5-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="a41e5-223">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-223">Shortcuts</span></span>

| <span data-ttu-id="a41e5-224">操作</span><span class="sxs-lookup"><span data-stu-id="a41e5-224">Action</span></span>                     | <span data-ttu-id="a41e5-225">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-225">Shortcut</span></span>                 |
|:---------------------------|:-------------------------|
| <span data-ttu-id="a41e5-226">Refresh</span><span class="sxs-lookup"><span data-stu-id="a41e5-226">Refresh</span></span>                    | `Ctrl` + `F5`            |
| <span data-ttu-id="a41e5-227">Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="a41e5-227">Delete cookie</span></span>              | `Del`                    |
| <span data-ttu-id="a41e5-228">すべての Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="a41e5-228">Delete all cookies</span></span>         | `Ctrl` + `Shift` + `Del` |
| <span data-ttu-id="a41e5-229">すべてのセッション Cookie を削除する</span><span class="sxs-lookup"><span data-stu-id="a41e5-229">Delete all session cookies</span></span> | `Ctrl` + `Del`           |
| <span data-ttu-id="a41e5-230">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="a41e5-230">Copy selected items</span></span>        | `Ctrl` + `C`             |
| <span data-ttu-id="a41e5-231">すべて選択</span><span class="sxs-lookup"><span data-stu-id="a41e5-231">Select all</span></span>                 | `Ctrl` + `A`             |

### <span data-ttu-id="a41e5-232">キャッシュ マネージャー</span><span class="sxs-lookup"><span data-stu-id="a41e5-232">Cache manager</span></span>

<span data-ttu-id="a41e5-233">特定のキャッシュ エントリをクリックすると、サービス ワーカー\*\*\*\* キャッシュ マネージャーが開き、必要に応じてキャッシュ エントリ *(* 要求\*\* と応答のキー/値のペア) を検査および削除できます。</span><span class="sxs-lookup"><span data-stu-id="a41e5-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span></span>

![キャッシュ マネージャー](./media/storage_cache.png)

### <span data-ttu-id="a41e5-235">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-235">Shortcuts</span></span>

#### <span data-ttu-id="a41e5-236">キャッシュ マネージャー</span><span class="sxs-lookup"><span data-stu-id="a41e5-236">Cache manager</span></span>

| <span data-ttu-id="a41e5-237">操作</span><span class="sxs-lookup"><span data-stu-id="a41e5-237">Action</span></span>              | <span data-ttu-id="a41e5-238">ショートカット</span><span class="sxs-lookup"><span data-stu-id="a41e5-238">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="a41e5-239">Refresh</span><span class="sxs-lookup"><span data-stu-id="a41e5-239">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="a41e5-240">項目の削除</span><span class="sxs-lookup"><span data-stu-id="a41e5-240">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="a41e5-241">選択したアイテムをコピーする</span><span class="sxs-lookup"><span data-stu-id="a41e5-241">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="a41e5-242">すべて選択</span><span class="sxs-lookup"><span data-stu-id="a41e5-242">Select all</span></span>          | `Ctrl` + `A`  |
