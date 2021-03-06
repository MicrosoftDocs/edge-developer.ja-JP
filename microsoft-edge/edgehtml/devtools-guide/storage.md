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
# <a name="storage"></a>Storage

[記憶域] **パネルを** 使用して、次を含むさまざまなローカル キャッシュ データを検査および管理します。  

*   [Web ストレージ](#local-and-session-storage-managers) \(Local と Session storage\) のキー/値のペア  
*   [インデックス付き DB](#indexeddb-manager) 構造化データ  
*   [ドメイン](#cookies-list) の Cookie  
*   [サービス](#cache-manager) ワーカーデバッグ用のキャッシュ \(request/response pairs\)  

これらのカテゴリを展開し、子エントリをクリックしてリソース マネージャー タブを開きます。  

## <a name="local-and-session-storage-managers"></a>ローカル ストレージ マネージャーとセッション ストレージ マネージャー  

ローカル ストレージ マネージャーとセッション ストレージ マネージャーを使用して、ページの Web ストレージを検査および管理します。  

[**記憶域] パネル****の [リソース] ピ**ッカー内のローカル 記憶域フォルダーとセッション 記憶域[フォルダーには](./debugger.md#resource-picker)、ページの原点の一覧が表示されます。  これらのフレームのいずれかを選択すると [、Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) または [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)を介して設定された現在のキー/値ペアの編集可能なテーブルが開きます。\(および/または DevTools [Storage](#storage-list)リスト \から直接設定)。  

![DevTools ストレージ マネージャー](./media/storage_web_storage.png)  

[ローカル ストレージ] タブと [セッション ストレージ] タブでは、次の方法を実行できます。  

*   **\(** `Ctrl+F5` \)[](#cookies-list)を更新して、指定されたドメインのキー/値ペアの現在のセットを表示します。  \(リストはスクリプトの更新時に自動更新されません。\)  
*   Microsoft Edge **Web ストレージのストレージ制限に**達するシミュレーションを行います。  各ドメインとサブドメインには独自の記憶域があります。ただし、次の制限が組み合わされています。  
    *   **サブドメイン**: 最大 5 つの領域  
    *   **ドメイン**: 最大 10 MB の領域  
    *   **すべてのドメインの合計**: 最大 50 の容量  

   セッション ストレージは、その原点を参照する最後のブラウザー タブが閉じ次第クリアされます。  ローカル ストレージ エントリは、ページによってプログラムによってクリアされるまで、またはユーザーが手動でクリアするまで、無期限に保持されます。  

   **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイトのデータ**  

![[Microsoft Edge の設定] パネルから閲覧データを消去する](./media/settings_clear_browsing_data.png)  

### <a name="storage-list"></a>記憶域リスト  

記憶域リスト テーブルから、次の方法を実行できます。  

*   **テーブルの列名** `key/value` をクリックして、ペアを調べ、並べ替えを行います。  
*   **セル** を `Key` クリック `Value` して、既存のエントリを編集します。  
*   **右** クリックのコンテキスト メニュー オプションの [アイテムの削除] から `Del` \( \) エントリ **を削除します**。  
*   **テーブル** の下部 `key/value` にある空の行をクリックして、新しいペアを追加します。  

### <a name="shortcuts"></a>ショートカット

| 操作 | ショートカット |  
|:--- |:--- |  
| Refresh | `Ctrl`+`F5` |  
| 項目の削除 | `Del` |  
| 選択したアイテムをコピーする | `Ctrl`+`C` |  
| すべて選択 | `Ctrl`+`A` |  

## <a name="indexeddb-manager"></a>IndexedDB マネージャー  

**[IndexedDB] タブを**使用して、クライアント コンピューターにローカルに格納されている構造化データを検査および管理します。  具体的には、オブジェクト ストアとインデックスを検査/並べ替え、更新したり、個々のキー値エントリを削除することができます。  

> [!TIP]
> オーディオ ミキサーのデモ [を使用して](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 、Microsoft Edge DevTools で *IndexedDB マネージャー* をテスト ドライブできます。  

Microsoft Edge の現在のユーザーに保存されている IndexedDB データを削除するには、[Microsoft Edge の設定] メニューを **使用** します。  

**...** > **設定**  > **閲覧データのクリア**  > **Cookie と保存された Web サイトのデータ**  

デバッガーの Resource ピッカー内のフォルダーには、ページによって読み込まれたリソースの発生元 `IndexedDB` の一覧が表示されます。 [](./debugger.md#resource-picker)  IndexedDB \(IDB\) データベースは、オブジェクト ストアと共に原点の下に一覧表示されます。  

![DevTools IndexedDB マネージャー](./media/storage_indexeddb.png)  

### <a name="indexeddb-toolbar"></a>IndexedDB ツールバー  

IndexedDB ツールバーでは、次のコマンドを実行できます。  

*   **\(** `Ctrl` + `F5` \) を更新して、データベースのオブジェクト ストアまたはインデックス内の現在のエントリを表示します。  データベースに変更を加えた場合、IndexedDB マネージャーは自動更新されません。  

### <a name="object-store-entries-list"></a>オブジェクト ストアエントリの一覧  

オブジェクト ストアまたはインデックス テーブルから、次の方法を実行できます。  

*   **テーブル内の任意** の列名をクリックして、キーと値のペアを調べ、並べ替える。  
*   **Refresh** \( `Ctrl` + `F5` \)  
*   **アイテム \(** \) を削除して、オブジェクト ストアまたはインデックスで選択 `Del` したエントリを削除します。  これを行うには、右クリックのコンテキスト メニュー オプションの [アイテム [の](#context-menu) 削除] **から行います**。  
*   **選択したアイテム**をコピー \( `Ctrl` + `C` \) して、選択したアイテムをクリップボードにコピーします。  この操作は、右クリックのコンテキスト メニュー[](#context-menu)オプションの [選択したアイテムのコピー **] から実行することもできます**。  
*   **すべての \(** `Ctrl` + `A` \) を選択して、オブジェクト ストアまたはインデックス内のすべてのエントリを選択します。  これを行うには、右クリックのコンテキスト メニュー[](#context-menu)オプションの [すべて選択]**から行います**。  

オブジェクト ストアまたはインデックス テーブルの列は並べ替え可能です。  

| 列 | 説明 |  
|:--- |:--- |  
| キー | オブジェクト ストアを反復するときにキーと値のペア \( **主**キー \と同じ) の名前。インデックスを反復する場合のインデックス キー \(cursor の現在のキー\) の名前 |  
| 主キー | キーと値のペアの名前 **\(IDB** キーの詳細については MDN Web [ドキュメントを参照](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)\) |  
| 設定値 | キーと値のペアの値 |  

IndexedDB *の概念と* 使用方法の詳細については [、MDN Web ドキュメントを参照してください](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。  

### <a name="context-menu"></a>ショートカット メニュー  

[ *IndexedDB*](#indexeddb-toolbar)ツールバーに加えて、右クリックのコンテキスト メニューやキーボード ショートカットからオブジェクト ストアまたはインデックス内の**** データを[管理することもできます](#shortcuts)。  

### <a name="shortcuts"></a>ショートカット

| 操作 | ショートカット |  
|:--- |:--- |  
| Refresh | `Ctrl`+`F5` |  
| キーと値のペアを削除する | `Del` |  
| 選択したアイテムをコピーする | `Ctrl`+`C` |  
| すべて選択 | `Ctrl +`A' |  

## <a name="cookies-manager"></a>Cookie マネージャー  

Cookie マネージャーを使用して、特定のドメインの Cookie を検査および管理します。  

デバッガーの Resource ピッカー内のフォルダーには、ページによって読み込まれたリソースの発生元 `Cookies` の一覧が表示されます。 [](./debugger.md#resource-picker)  これらのフレームのいずれかを選択すると [、HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) ヘッダーまたは Document.cookie を使用したスクリプトによって設定されている現在の Cookie を表す [テーブルが開きます](https://developer.mozilla.org/docs/Web/API/Document/cookie)。  

![DevTools Cookie マネージャー](./media/storage_cookies.png)  

[Cookie] タブ ツールバーから、次の機能を実行できます。  

*   **\(** `Ctrl` + `F5` \) Cookie リスト[を更新して](#cookies-list)、指定されたドメインの現在の Cookie セットを表示します。  \(リストは自動更新されません。\)  
*   **現在のページの**パス `Ctrl` + `Shift` + `Del` のすべての Cookie \( \) \(session and permanent\) を削除します。  
*   **現在のページのパス**のすべてのセッション `Ctrl` + `Del` Cookie \( \) を削除します。  

Cookie リストを完全にクリアするには、[ネットワーク]**** パネル のツール バーからドメインのすべての Cookie をクリア[する必要があります](./network.md#toolbar)。  

### <a name="cookies-list"></a>Cookie リスト  

Cookie リスト テーブルから、次の機能を実行できます。  

*   **テーブル内の任意** の列名をクリックして、Cookie を調べ、並べ替える。  
*   **セル** を `Name` クリック `Value` して、既存の Cookie を編集します。  
*   **右** クリックの `Del` コンテキスト メニュー オプションから \( \) cookie [を削除](#context-menu) します `Delete cookie` 。  
*   **表** の下部にある空の行をクリックして、指定したセッションの新しい Cookie `Domain/Path` を追加します。  これはセッション Cookie でのみ機能します。永続的な Cookie \(特定の有効期限\を持つ) は、従来のメソッドで設定する必要があります。  ページ `Domain` の `Path` 場所に応じて、値と値が自動的に入力されます。  

Cookie リストの列は並べ替え可能です。

| 列 | 説明 |  
| :--- | :--- |  
| Name (名前) | Cookie の名前 |  
| 設定値 | Cookie の値 |  
| ドメイン | Cookie のホスト名 \(空の場合があります\) |  
| パス | Cookie の URL パス \(空の場合があります\) |  
| 有効期限 | HTTP 日付タイムスタンプとしての Cookie の最大有効期間。  いいえまたは `Expires` 設定 `Max-Age` されている場合、エントリはセッション Cookie と見なされます。  |  
| HTTP のみ | Cookie がディレクティブと一緒に設定されたかどうかを示し、JavaScript からアクセスできない `HttpOnly` ことを示します。 |  
| セキュリテイ保護 | Cookie がディレクティブと一緒に設定されたかどうかを示し、SSL と HTTPS プロトコルを使用した要求からのみサーバー `Secure` に送信されます。  |  

Cookie プロパティ**の詳細については、MDN Web ドキュメント**[の Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)リファレンスを参照してください。  

### <a name="context-menu"></a>ショートカット メニュー  

[Cookie] タブ ツールバー[に加えて](#cookies-manager)、右クリックのコンテキスト メニューやキーボード**** ショートカットから Cookie を[管理することもできます](#shortcuts)。  

### <a name="shortcuts"></a>ショートカット  

| 操作 | ショートカット |  
|:--- |:--- |  
| Refresh | `Ctrl`+`F5` |  
| Cookie の削除 | `Del` |  
| すべての Cookie を削除する | `Ctrl`+`Shift`+`Del` |  
| すべてのセッション Cookie を削除する | `Ctrl`+`Del` |  
| 選択したアイテムをコピーする | `Ctrl`+`C` |  
| すべて選択 | `Ctrl`+`A` |  

### <a name="cache-manager"></a>キャッシュ マネージャー  

特定のキャッシュ エントリをクリックすると、サービス ワーカー**** のキャッシュ マネージャーが開き、キャッシュ エントリ \( とキー/値のペア\) を検査して必要に応じて `Request` `Response` 削除できます。  

![キャッシュ マネージャー](./media/storage_cache.png)  

### <a name="shortcuts"></a>ショートカット  

#### <a name="cache-manager"></a>キャッシュ マネージャー  

| 操作 | ショートカット |  
|:--- |:--- |  
| Refresh | `Ctrl`+`F5` |  
| 項目の削除 | `Del` |  
| 選択したアイテムをコピーする | `Ctrl`+`C` |  
| すべて選択 | `Ctrl`+`A` |  
