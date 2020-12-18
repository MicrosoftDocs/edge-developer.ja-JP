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
# 記憶域

記憶域パネル **を使用** して、ローカルにキャッシュされたさまざまなデータ (以下を含む) を検査および管理します。

 - [Web ストレージ](#local-and-session-storage-managers)(*ローカルストレージ**とセッション*ストレージ) のキー/値のペア
 - [インデックス付き DB](#indexeddb-manager) 構造化データ
 - [ドメイン](#cookies-list) の Cookie
 - [サービス](#cache-manager) ワーカー デバッグ用のキャッシュ (要求と応答のペア)

これらのカテゴリを展開し、子エントリをクリックしてリソース マネージャー タブを開きます。

## ローカルおよびセッション の記憶域マネージャー

ローカル ストレージ *マネージャーと* セッション ストレージ マネージャー *を使用して、* ページの Web ストレージを検査および管理します。 

記憶域**パネルの**リソース**ピッカー内**のローカル ストレージ[**](./debugger.md#resource-picker)フォルダーとセッション ストレージ フォルダーには、ページの作成元の一覧が表示されます。 これらのフレームのいずれかを選択すると [、Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) または [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)を介して設定された現在のキー/値ペアの編集可能なテーブルが開きます (また、DevTools [Storage](#storage-list)リストから直接設定することもできます)。

![DevTools ローカル ストレージ マネージャー](./media/storage_web_storage.png)

[ *ローカル ストレージ] タブと [* セッション *ストレージ] タブから、* 次の方法を実行できます。

 - **指定** した `Ctrl+F5` ドメインの [キーと](#cookies-list) 値のペアの現在のセットを表示するには、ストレージ リストを更新 () します。 (この一覧は、スクリプトの更新時に自動更新されません。
 - Microsoft Edge **Web ストレージの記憶域制限**に達するシミュレーション。 各ドメインとサブドメインには独自の記憶域が用意されています。ただし、次の制限を組み合わせて使用できます。
    - **サブドメイン:** 最大 5 つの領域
    - **ドメイン:** 最大 10 の領域
    - **すべてのドメインの合計:** 最大 50 の領域

   セッション ストレージは、その原点を参照する最後のブラウザー タブが閉じたらすぐにクリアされます。 ローカル ストレージ エントリは、ページによってプログラムによってクリアされるまで、またはユーザーが手動でクリアするまで、無期限に保持されます。

   **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイト データ**

![Microsoft Edge の [設定] パネルから閲覧データをクリアする](./media/settings_clear_browsing_data.png)

### 記憶域リスト

記憶域の *一覧の表から* 、次の方法を実行できます。

 - **テーブルの列名** をクリックして、キーと値のペアを調べ、並べ替える。
 - **セル** を *クリック* して *、* 既存のエントリのキーと値を編集します。
 - **Delete** ( `Del` ) an entry from the right-click context menu option, Delete *item*.
 - **表** の下部にある空の行をクリックして、新しいキーと値のペアを追加します。


### ショートカット

| 操作              | ショートカット      |
|:--------------------|:--------------|
| Refresh             | `Ctrl` + `F5` |
| 項目の削除         | `Del`         |
| 選択したアイテムをコピーする | `Ctrl` + `C`  |
| すべて選択          | `Ctrl` + `A`  |


## IndexedDB マネージャー

**[IndexedDB] タブを使用**して、クライアント コンピューターにローカルに格納されている構造化データを検査および管理します。 具体的には、オブジェクト ストアとインデックスを検査/並べ替え、更新したり、個々のキー値エントリを削除することができます。

> [!TIP]
> Audio Mixer デモを [使って](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 、Microsoft Edge DevTools で *IndexedDB マネージャー* をテストできます。

Microsoft Edge で現在のユーザーに保存されている IndexedDB データを削除するには、[Microsoft Edge の設定] メニューを *使用* します。

**...** > **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイト データ**

デバッガーのリソース ピッカー内の**IndexedDB**フォルダーには、ページによって読み込まれたリソースからのオリジンの一覧が表示されます。 [**](./debugger.md#resource-picker) IndexedDB (IDB) データベースは、そのオブジェクト ストアと共に、作成元の下に一覧表示されます。 

![DevTools IndexedDB マネージャー](./media/storage_indexeddb.png)

### IndexedDB ツール バー

*IndexedDB ツール バーから、* 次の方法を実行できます。

 - **データベース** のオブジェクト ストアまたはインデックスの現在のエントリを表示するには `Ctrl+F5` 、() を更新します。 データベースに変更を加えた場合、IndexedDB マネージャーは自動更新されません。

### オブジェクト ストアエントリリスト

オブジェクト ストア*またはインデックス テーブル**から*、次の方法を実行できます。

 - **テーブル内の任意** の列名をクリックして、キーと値のペアを調べ、並べ替える。
 - **Refresh** ( `Ctrl+F5` )
 - **アイテム** ( `Del` ) を削除して、オブジェクト ストアまたはインデックスで選択されているエントリを削除します。 これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [アイテムの削除]*をクリックします*。
 - **選択した項目** ( `Ctrl+C` ) をコピーして、選択した項目をクリップボードにコピーします。 これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [選択した項目をコピー*する] をクリックします*。
 - **オブジェクト ストア** またはインデックス内のすべてのエントリを選択するには、[すべて] `Ctrl+A` () を選択します。 これを行うには、右クリックのコンテキスト メニュー オプションの [すべて [選択](#context-menu) ] *をクリックします*。

オブジェクト ストアまたは*インデックス テーブルの列**は*並べ替え可能です。

列 | 説明
:------------ | :-------------
キー | オブジェクト ストアを反復する場合のキーと** 値のペアの名前 (主キーと同じ)インデックスを反復する場合のインデックス キーの名前 (カーソルの現在のキー)
主キー | キーと値のペアの名前 *(IDB*キーの詳細については MDN Web ドキュメントを参照[)](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)
設定値 | キーと値のペアの値

IndexedDB *の概念と* 使用方法について詳しくは、MDN の Web [ドキュメントをご覧ください](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。

### ショートカット メニュー

[ *IndexedDB*](#indexeddb-toolbar)ツール バーに加えて、右クリックのコンテキスト メニューやキーボード ショートカットからオブジェクト ストアまたはインデックス**** 内のデータを[管理することもできます](#shortcuts)。

### ショートカット

操作 | ショートカット
:------------ | :-------------
Refresh | `Ctrl` + `F5`
キーと値のペアを削除する | `Del`
選択したアイテムをコピーする | `Ctrl` + `C`
すべて選択 | `Ctrl` + `A`

## Cookie マネージャー

Cookie マネージャー *を使用して* 、特定のドメインの Cookie を検査および管理します。 

デバッガー **の** リソース ピッカー内の Cookie フォルダーには [*、ページによって*](./debugger.md#resource-picker) 読み込まれたリソースからのオリジンの一覧が表示されます。 これらのフレームのいずれかを選択すると [、HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) ヘッダーまたは Document.cookie を使用したスクリプトによって設定された現在の Cookie を表すテーブル [が開きます](https://developer.mozilla.org/docs/Web/API/Document/cookie)。

![DevTools Cookie マネージャー](./media/storage_cookies.png)

*[Cookie] タブの*ツール バーから、次の方法を実行できます。

 - **Cookie**リスト `Ctrl+F5` を[](#cookies-list)更新 () して、特定のドメインの Cookie の現在のセットを表示します。 (リストは自動更新されません。
 - **現在のページの** パスのすべての Cookie `Ctrl+Shift+Del` ( ) (セッションおよび永続) を削除します。
 - **現在のページのパス** のすべてのセッション Cookie ( `Ctrl+Del` ) を削除します。

Cookie リストを完全に*クリアするには*、[ネットワーク パネル****] ツール バーからドメインのすべての Cookie をクリアする必要[**がある**](./network.md#toolbar)場合があります。

### Cookie リスト

Cookie リスト *の表から、* 次の方法を実行できます。

 - **テーブル内の任意** の列名をクリックして、Cookie を検査して並べ替える。
 - **セル** を *クリック* して *、* 既存の Cookie の名前と値を編集します。
 - **右**クリック `Del` のコンテキスト メニュー オプションから[](#context-menu)Cookie を削除 () します。Cookie*を削除します*。
 - **表** の下部にある空の行をクリックして、指定したドメイン */* パスの新しいセッション Cookie を追加します。 これはセッション Cookie でのみ機能します。永続的な Cookie (特定の有効期限がある場合) は、従来の方法で設定する必要があります。 Domain *と* *Path の値* は、ページの場所に従って自動的に入力されます。

Cookie リストの列 *は並* べ替え可能です。

列 | 説明
:------------ | :-------------
Name (名前) | Cookie の名前
設定値 | Cookie の値
ドメイン | Cookie のホスト名 (空の可能性があります)
パス | Cookie の URL パス (空の可能性があります)
有効期限 | HTTP 日付タイムスタンプとしての Cookie の最大有効期間。 指定がない `Expires` 場合 `Max-Age` 、または設定されている場合、エントリはセッション Cookie *と見な* されます。
HTTP のみ | Cookie がディレクティブで設定されたかどうかを示します `HttpOnly` 。JavaScript からアクセスできないかどうかを示します
セキュリテイ保護 | Cookie がディレクティブと一緒に設定されたかどうかを示します。これは、SSL と HTTPS プロトコルを使用した要求からのみサーバー `Secure` に送信されます。

Cookie プロパティ**の詳細については、MDN Web ドキュメント**[の Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンスを参照してください。

### ショートカット メニュー

[Cookie] タブ*の*[ツール](#cookies-manager)バーに加えて、右クリックのコンテキスト メニュー**** やキーボード ショートカットから Cookie を[管理することもできます](#shortcuts)。

### ショートカット

| 操作                     | ショートカット                 |
|:---------------------------|:-------------------------|
| Refresh                    | `Ctrl` + `F5`            |
| Cookie を削除する              | `Del`                    |
| すべての Cookie を削除する         | `Ctrl` + `Shift` + `Del` |
| すべてのセッション Cookie を削除する | `Ctrl` + `Del`           |
| 選択したアイテムをコピーする        | `Ctrl` + `C`             |
| すべて選択                 | `Ctrl` + `A`             |

### キャッシュ マネージャー

特定のキャッシュ エントリをクリックすると、サービス ワーカー**** キャッシュ マネージャーが開き、必要に応じてキャッシュ エントリ *(* 要求** と応答のキー/値のペア) を検査および削除できます。

![キャッシュ マネージャー](./media/storage_cache.png)

### ショートカット

#### キャッシュ マネージャー

| 操作              | ショートカット      |
|:--------------------|:--------------|
| Refresh             | `Ctrl` + `F5` |
| 項目の削除         | `Del`         |
| 選択したアイテムをコピーする | `Ctrl` + `C`  |
| すべて選択          | `Ctrl` + `A`  |
