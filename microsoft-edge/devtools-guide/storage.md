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
# 記憶域

[**記憶域**] パネルを使用して、ローカルでキャッシュされているさまざまなデータを検査および管理します。

 - [Web ストレージ](#local-and-session-storage-managers)(*ローカル*と*セッション*の記憶域) のキーと値のペア
 - [インデックス付きのデータベース](#indexeddb-manager)構造化データ
 - ドメインの[cookie](#cookies-list)
 - Service worker のデバッグの[キャッシュ](#cache-manager)(要求/応答のペア)

いずれかのカテゴリを展開し、子エントリをクリックして、[リソースマネージャー] タブを開きます。

## ローカルとセッションのストレージマネージャー

*ローカルストレージマネージャー*と*セッションストレージマネージャー*を使用して、ページの web ストレージを検査および管理します。 

ストレージパネルの[*リソースピッカー*](./debugger.md#resource-picker)内の**ローカルストレージ**と**セッションストレージ**フォルダーには、ページの原点の一覧が表示されます。 これらのフレームのいずれかを選択すると、 [windows](https://developer.mozilla.org/docs/Web/API/Window/localStorage)によって設定された現在のキーと値のペアの編集可能なテーブルが開きます (または、「Devtools ストレージ[」](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)[リスト](#storage-list)から直接設定されています)。

![DevTools Cookies マネージャー](./media/storage_web_storage.png)

[*ローカルストレージ*] タブと [*セッションストレージ*] タブから、次の操作を実行できます。

 - **Refresh** [ `Ctrl+F5` [記憶域] の一覧](#cookies-list)を更新して、指定したドメインの現在のキーと値のペアのセットを表示します。 (一覧は、スクリプトの更新時には自動更新されません)。
 - Microsoft Edge web storage の**記憶域の上限に達した**ことをシミュレートします。 各ドメインとサブドメインには専用のストレージ領域がありますが、次のように、結合された制限があります。
    - サブ**ドメイン:** 最大 5 mb のスペース
    - **ドメイン:** 最大 10 mb のスペース
    - **すべてのドメインの合計:** 最大 50 mb のスペース

   セッションストレージは、その原点を参照している最後のブラウザータブが閉じられるとすぐに消去されます。 ローカル記憶域エントリは、ページによってプログラムによって、またはユーザーによって手動で削除されるまで無期限に保持されます。

   **設定**  > **閲覧データ**  >  をクリアする**Cookie と保存済みの web サイトデータ**

![Microsoft Edge の [設定] パネルで閲覧データをクリアする](./media/settings_clear_browsing_data.png)

### ストレージリスト

*ストレージリスト*テーブルからは、次のことができます。

 - テーブルのいずれかの列名をクリックして、キーと値のペアを**検査して並べ替え**ます。
 - セルをクリックして、既存のエントリの*キー*と*値*を**編集**します。
 - **Delete** `Del` 右クリックのコンテキストメニューオプションから [削除] を選び、[*アイテムの削除*] を選びます。
 - 表の下部にある空の行をクリックして、新しいキーと値のペアを**追加**します。


### ショートカット

| 操作              | キー      |
|:--------------------|:--------------|
| Refresh             | `Ctrl` + `F5` |
| 項目の削除         | `Del`         |
| 選択したアイテムをコピーする | `Ctrl` + `C`  |
| すべて選択          | `Ctrl` + `A`  |


## IndexedDB マネージャー

[ **Indexeddb** ] タブを使用して、クライアントコンピューターにローカルに保存されている構造化データを検査および管理します。 具体的には、オブジェクトストアとインデックスを検査/並べ替え、更新することができます。また、個々のキーと値のエントリを削除することもできます。

> [!TIP]
> [オーディオミキサー](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/)のデモを使用して、Microsoft Edge Devtools の*indexeddb manager*のドライブをテストすることができます。

Microsoft Edge で現在のユーザー用に保存されているすべての IndexedDB データを削除するには、Microsoft Edge の [*設定*] メニューを使用します。

**...** > **設定**  > **閲覧データ**  >  をクリアする**Cookie と保存済みの web サイトデータ**

デバッガーの[*リソースピッカー*](./debugger.md#resource-picker)内の**indexeddb**フォルダーには、ページによって読み込まれたリソースから元のリストが表示されます。 任意の IndexedDB (.IDB) データベースは、そのオブジェクトストアと共に、元のリストに一覧表示されます。 

![DevTools IndexedDB manager](./media/storage_indexeddb.png)

### IndexedDB ツールバー

[ *Indexeddb* ] ツールバーから次のことができます。

 - [**更新**] ( `Ctrl+F5` ) を選び、データベースのオブジェクトストアまたはインデックスの現在のエントリを表示します。 データベースに変更が加えられても、IndexedDB manager は自動更新されません。

### オブジェクトストアのエントリの一覧

*オブジェクトストア*または*インデックス*テーブルから、次の操作を実行できます。

 - テーブル内の任意の列名をクリックして、キーと値のペアを**検査して並べ替え**ます。
 - **Refresh** ( `Ctrl+F5` )
 - [**アイテムの削除**] ( `Del` ) オブジェクトストアまたはインデックスで選んだエントリを削除します。 この操作は、右クリックの[コンテキストメニュー](#context-menu)オプションの [アイテムの*削除*] でも実行できます。
 - 選択した**アイテムをコピー**する () 選択したアイテムを `Ctrl+C` クリップボードにコピーします。 また、右クリックの[コンテキストメニュー](#context-menu)オプションで、*選択したアイテムをコピー*することもできます。
 - **[すべて]** () を選択し `Ctrl+A` て、オブジェクトストアまたはインデックス内のすべてのエントリを選択します。 また、右クリックの[コンテキストメニュー](#context-menu)オプションで *[すべて] を選択*することもできます。

*オブジェクトストア*または*インデックス*テーブルの列は、並べ替え可能です。

列 | 説明
:------------ | :-------------
Key | オブジェクトストアを反復処理するときのキーと値のペアの名前 (*主キー*と同じ)。インデックスを反復処理するときのインデックスキー (カーソルの現在のキー) の名前
主キー | キーと値のペアの名前 (「MDN[キー](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)の詳細については、「 *MDN web ドキュメント*」をご覧ください)。
値 | キーと値のペアの値

[Indexeddb の概念と使い方](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)について詳しくは、 *「MDN web ドキュメント*」をご覧ください。

### ショートカット メニュー

[ [ *Indexeddb* ] ツールバー](#indexeddb-toolbar)に加えて、右クリックの**コンテキストメニュー**やキーボード[ショートカット](#shortcuts)から、オブジェクトストアまたはインデックスのデータを管理することもできます。

### ショートカット

操作 | キー
:------------ | :-------------
Refresh | `Ctrl` + `F5`
キーと値のペアを削除する | `Del`
選択したアイテムをコピーする | `Ctrl` + `C`
すべて選択 | `Ctrl` + `A`

## Cookies マネージャー

*Cookie マネージャー*を使用して、指定したドメインの cookie を検査および管理します。 

デバッガーの[*リソースピッカー*](./debugger.md#resource-picker)内の**Cookies**フォルダーには、ページによって読み込まれたリソースからの元のリストが表示されます。 これらのフレームのいずれかを選択すると、 [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)ヘッダーで設定された現在の cookie、または script を使用して、指定したスクリプトを含む表が表示さ[れます。](https://developer.mozilla.org/docs/Web/API/Document/cookie)

![DevTools Cookies マネージャー](./media/storage_cookies.png)

[ *Cookie* ] タブのツールバーから次のことができます。

 - **Refresh**指定した `Ctrl+F5` ドメインの現在の cookie のセットを表示するには、[ [cookie] の一覧](#cookies-list)を更新します。 (リストは自動更新されません)。
 - **Delete all cookies** `Ctrl+Shift+Del` 現在のページのパスについて、すべての cookie () (セッションと永続的) を削除します。
 - 現在のページのパスの**セッション cookie** ( `Ctrl+Del` ) をすべて削除します。

*Cookie リスト*を完全に消去するには、[**ネットワーク**](./network.md#toolbar)パネルのツールバーから**ドメインのすべての cookie をクリア**する必要がある場合があります。

### Cookies リスト

*Cookie リスト*テーブルからは、次のことができます。

 - 表の任意の列名をクリックして、cookie を**検査して並べ替え**ます。
 - セルをクリックして、既存の cookie の*名前*と*値*を**編集**します。
 - **Delete** `Del` 右クリックの[コンテキストメニュー](#context-menu)オプションから cookie を削除して、 *cookie を削除*します。
 - 表の下部にある空の行をクリックして、指定した*ドメイン/パス*の新しいセッション Cookie を**追加**します。 これは、セッション cookie に対してのみ有効です。永続的な cookie (特定の有効期限を含む) は、従来の方法で設定する必要があります。 [*ドメイン*] と [ *Path* ] の値は、ページの場所に応じて自動的に入力されます。

*Cookie リスト*の列は、並べ替え可能です。

列 | 説明
:------------ | :-------------
Name (名前) | Cookie の名前
値 | Cookie の値
ドメイン | Cookie のホスト名 (空の可能性があります)
パス | Cookie の URL パス (空の可能性があります)
有効期限 | HTTP 日付のタイムスタンプとしての cookie の最長有効期間。 指定しなかった場合、 `Expires` または `Max-Age` 設定されていない場合、エントリは*セッション*cookie と見なされます。
HTTP のみ | Cookie がディレクティブで設定されたかどうかを示します。 `HttpOnly` これは JavaScript からアクセスできないことを示します。
セキュリテイ保護 | Cookie がディレクティブで設定されたかどうかを示し `Secure` ます。これは、SSL と HTTPS プロトコルを使って要求された場合にのみサーバーに送信されることを意味します。

Cookie のプロパティについて詳しくは、「 **MDN web ドキュメント**[セット-cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンス」をご覧ください。

### ショートカット メニュー

[ *Cookie* ] タブ[ツールバー](#cookies-manager)に加えて、右クリックの**コンテキストメニュー**やキーボード[ショートカット](#shortcuts)からも cookie を管理することができます。

### ショートカット

| 操作                     | キー                 |
|:---------------------------|:-------------------------|
| Refresh                    | `Ctrl` + `F5`            |
| Cookie を削除する              | `Del`                    |
| すべての cookie を削除する         | `Ctrl` + `Shift` + `Del` |
| すべてのセッション cookie を削除する | `Ctrl` + `Del`           |
| 選択したアイテムをコピーする        | `Ctrl` + `C`             |
| すべて選択                 | `Ctrl` + `A`             |

### キャッシュマネージャー

特定のキャッシュエントリをクリックすると、service worker**キャッシュ**マネージャーが開きます。ここでは、キャッシュエントリ (*要求*と*応答*のキー/値のペア) を検査したり、必要に応じて削除したりできます。

![キャッシュマネージャー](./media/storage_cache.png)

### ショートカット

#### キャッシュマネージャー

| 操作              | キー      |
|:--------------------|:--------------|
| Refresh             | `Ctrl` + `F5` |
| 項目の削除         | `Del`         |
| 選択したアイテムをコピーする | `Ctrl` + `C`  |
| すべて選択          | `Ctrl` + `A`  |
