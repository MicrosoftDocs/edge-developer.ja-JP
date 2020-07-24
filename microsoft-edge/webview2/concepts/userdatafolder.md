---
description: WebView2 アプリケーションでユーザーデータフォルダーを管理する方法について説明します。
title: WebView2 アプリケーションでユーザーデータフォルダーを管理します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、ユーザーデータフォルダー
ms.openlocfilehash: 4e10f589bc7866cd06e007d70c0dff941afc35cb
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895505"
---
# ユーザーデータフォルダーの管理  

WebView2 アプリケーションは、cookie、アクセス許可、キャッシュされたリソースなどのブラウザーデータを保存するために、ユーザーデータフォルダーとやり取りします。  WebView2 コントロールの各インスタンスは、ユーザーデータフォルダーに関連付けられます。  各ユーザーデータフォルダーは、ユーザーに対して一意です。  

## ベスト プラクティス  

ユーザーデータフォルダーは、WebView2 によって自動的に作成されます。  WebView2 の開発者は、ユーザーデータフォルダーの有効期間を制御します。  アプリケーションでアプリケーションセッションのユーザーデータを再利用する場合は、ユーザーデータフォルダーを保存することを検討してください。そうしないと、削除することができます。  ユーザーデータフォルダーを管理する方法を決定する際には、次のシナリオを検討してください。  

*   同じユーザーがアプリケーションを繰り返し使っていて、アプリケーションの web コンテンツがユーザーのデータに依存している場合は、ユーザーデータフォルダーを保存します。  複数のユーザーがアプリケーションを繰り返し使用している場合は、新しいユーザーごとに新しいユーザーデータフォルダーを作成し、各ユーザーのユーザーデータフォルダーを保存します。
*   アプリケーションに繰り返しユーザーがない場合は、ユーザーごとに新しいユーザーデータフォルダーを作成し、以前のユーザーデータフォルダーを削除します。  

## ユーザーデータフォルダーを作成する  

ユーザーデータフォルダーの場所を指定するに `userDataFolder` は、 [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \ (Win32 \) または[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \ (.net \) を呼び出すときにパラメーターを含めます。  作成後、WebView2 コントロールからのブラウザーデータは、のサブフォルダーに保存され `userDataFolder` ます。  `userDataFolder`指定しない場合、WebView2 は次のように既定の場所にユーザーデータフォルダーを作成します。  

*   パッケージ化された Windows ストアアプリの場合、既定のユーザーフォルダーは `ApplicationData\LocalFolder` パッケージのフォルダー内のサブフォルダーです。  
*   既存のデスクトップアプリの場合、既定のユーザーデータフォルダーは、アプリケーションの exe パスになり `.WebView2` ます。  既定の代わりに、ユーザーデータフォルダーを指定して、他のすべてのアプリデータが保存されているフォルダーと同じフォルダーに作成することをお勧めします。  

## ユーザーデータフォルダーを削除する  

アプリケーションでユーザーデータフォルダーを削除する必要がある場合があります。  

*   アプリをアンインストールする場合。  パッケージ化された Windows ストアアプリをアンインストールする場合、Windows はユーザーデータフォルダーを自動的に削除します。  
*   を選び、すべての閲覧データ履歴をクリーンアップします。  
*   データの破損を回復します。  
*   以前のセッションデータを削除します。  

> [!NOTE]
> ユーザーデータフォルダー内のファイルは、WebView2 アプリケーションが終了した後も引き続き使用されている可能性があります。  この場合は、ブラウザーのプロセスとすべての子プロセスが終了するのを待ってから、フォルダーを削除します。  WebView2 のプロパティを使用して、ブラウザープロセスのプロセス id を取得でき `BrowserProcessId` ます。  

## ユーザーデータフォルダーを共有する  

WebView2 コントロールでは、同じユーザーデータフォルダーを共有することができます。  

*   1つのブラウザープロセスで実行して、[システムリソースを最適化](../concepts/process-model.md)します。  
*   ブラウザー履歴とキャッシュリソースを共有します。  

ユーザーデータフォルダーを共有する場合は、次の点を考慮してください。  

1.  WebView2 コントロールを再作成して、ブラウザーのバージョンを更新するには、 [add_NewBrowserVersionAvailable](../reference/win32/0-9-538/icorewebview2environment.md#add_newbrowserversionavailable) \ (Win32 \) または[NewexitserverWebView2 available](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) \ (.net \) のイベントを使用します。  ブラウザープロセスのプロセス id を取得するには、 `BrowserProcessId` WebView2 コントロールのプロパティを使います。  

2.  同じユーザーデータフォルダーを共有する WebView2 コントロールでは、 [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \ (Win32 \) または[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \ (.net \) に同じオプションを使用する必要があります。  満たされていない場合、WebView2 の作成は失敗 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` します。  

アプリケーションのさまざまな部分を分離したり、WebView2 コントロール間でデータを共有したりする必要がない場合は、別のユーザーデータフォルダーを使用することができます。  たとえば、アプリケーションは2つの WebView2 コントロールで構成されています。1つはアドバタイズを表示し、もう一方はアプリケーションのコンテンツを表示することです。  このシナリオでは、開発者は、WebView2 コントロールごとに異なるユーザーデータフォルダーを使うことができます。  

> [!NOTE]
> WebView2 browser の各プロセスでは、追加のメモリとディスク領域が消費されます。  そのため、同時に複数のユーザーデータフォルダーを使用する WebView2s は実行しないことをお勧めします。  
