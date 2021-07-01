---
description: WebView2 アプリケーションでユーザー データ フォルダーを管理する方法について説明します。
title: WebView2 アプリケーションでユーザー データ フォルダーを管理します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html、ユーザー データ フォルダー
ms.openlocfilehash: d3b3e8d81ddffec043f0988385a433eb7c817de7
ms.sourcegitcommit: 5ae09b1ad6cd576c9fec12538b23cd849861f2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "11627958"
---
# <a name="manage-the-user-data-folder"></a>ユーザー データ フォルダーの管理  

WebView2 アプリケーションは、ユーザー データ フォルダーを操作して、Cookie、アクセス許可、キャッシュされたリソースなどのブラウザー データを格納します。  WebView2 コントロールの各インスタンスは、ユーザー データ フォルダーに関連付けられる。  各ユーザー データ フォルダーは、ユーザーに固有です。  

## <a name="best-practices"></a>ベスト プラクティス  

ユーザー データ フォルダーは、WebView2 によって自動的に作成されます。  WebView2 開発者は、ユーザー データ フォルダーの有効期間を制御します。  アプリケーションがアプリケーション セッションからユーザー データを再使用する場合は、ユーザー データ フォルダーの保存を検討してください。それ以外の場合は削除できます。  ユーザー データ フォルダーを管理する方法を決定する場合は、次のシナリオを検討してください。  

*   同じユーザーがアプリケーションを繰り返し使用し、アプリケーションの Web コンテンツがユーザーのデータに依存している場合は、ユーザー データ フォルダーを保存します。  複数のユーザーがアプリケーションを繰り返し使用する場合は、新しいユーザーごとに新しいユーザー データ フォルダーを作成し、各ユーザーのユーザー データ フォルダーを保存します。
*   アプリケーションに繰り返しユーザーが存在しない場合は、ユーザーごとに新しいユーザー データ フォルダーを作成し、前のユーザー データ フォルダーを削除します。  
    
## <a name="create-user-data-folders"></a>ユーザー データ フォルダーの作成  

ユーザー データ フォルダーの場所を指定するには `userDataFolder` [、ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \(Win32\) または [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \(.NET\) を呼び出す際にパラメーターを含める必要があります。  作成後、WebView2 コントロールのブラウザー データは 、 のサブフォルダーに格納されます `userDataFolder` 。  指定しない場合、WebView2 は次のように既定の場所にユーザー `userDataFolder` データ フォルダーを作成します。  

*   パッケージ化されたWindowsストア アプリの場合、既定のユーザー フォルダーはパッケージのフォルダー `ApplicationData\LocalFolder` 内のサブフォルダーです。  
*   既存のデスクトップ アプリの場合、既定のユーザー データ フォルダーはアプリケーションの exe パス + です `.WebView2` 。  既定を使用する代わりに、ユーザー データ フォルダーを指定し、他のすべてのアプリ データが格納されている同じフォルダーに作成することをお勧めします。  
    
## <a name="delete-user-data-folders"></a>ユーザー データ フォルダーの削除  

アプリケーションでユーザー データ フォルダーを削除する必要がある場合があります。  

*   アプリをアンインストールする場合。  パッケージ化されたストア アプリをアンインストールするWindows、Windowsユーザー データ フォルダーが自動的に削除されます。  
*   すべての閲覧データ履歴をクリーンアップする。  
*   データの破損から回復する。  
*   以前のセッション データを削除するには。  
    
> [!NOTE]
> WebView2 アプリケーションを閉じた後も、ユーザー データ フォルダー内のファイルが使用されている可能性があります。  この状況では、フォルダーを削除する前に、ブラウザー プロセスとすべての子プロセスが終了するのを待ちます。  WebView2 のプロパティを使用して、ブラウザー プロセスの `BrowserProcessId` プロセス ID を取得できます。  

## <a name="share-user-data-folders"></a>ユーザー データ フォルダーの共有  

WebView2 コントロールは、次の場合に同じユーザー データ フォルダーを共有できます。  

*   [1 つのブラウザー プロセスで](../concepts/process-model.md) 実行することで、システム リソースを最適化します。  
*   ブラウザーの履歴とキャッシュされたリソースを共有します。  
    
ユーザー データ フォルダーを共有する場合は、次の点を考慮してください。  

1.  webView2 コントロールを再作成して [、add_NewBrowserVersionAvailable](/microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable) \(Win32\) イベントまたは [NewBrowserVersionAvailable](/dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable) \(.NET\) イベントを使用してブラウザー のバージョンを更新する場合は、ブラウザー プロセスが同じユーザー データ フォルダーを共有する WebView2 コントロールを終了して閉じる必要があります。  ブラウザー プロセスのプロセス ID を取得するには `BrowserProcessId` 、WebView2 コントロールのプロパティを使用します。  
1.  同じユーザー データ フォルダーを共有する WebView2 コントロールでは [、ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \(Win32\) または [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \(.NET\) に同じオプションを使用する必要があります。  指定しない場合、WebView2 の作成は失敗します `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` 。  
    
アプリケーションの異なる部分を分離したり、WebView2 コントロール間でデータを共有する必要が生じない場合は、別のユーザー データ フォルダーを使用することもできます。  たとえば、アプリケーションは 2 つの WebView2 コントロールで構成され、1 つは提供情報を表示し、もう 1 つはアプリケーション コンテンツを表示します。  このシナリオでは、開発者は WebView2 コントロールごとに異なるユーザー データ フォルダーを使用することを選択できます。  

> [!NOTE]
> 各 WebView2 ブラウザー プロセスでは、追加のメモリとディスク領域が消費されます。  したがって、同時に多数の異なるユーザー データ フォルダーを使用して WebView2s を実行することをお勧めします。  
