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
# <span data-ttu-id="58e07-104">ユーザーデータフォルダーの管理</span><span class="sxs-lookup"><span data-stu-id="58e07-104">Managing the User Data Folder</span></span>  

<span data-ttu-id="58e07-105">WebView2 アプリケーションは、cookie、アクセス許可、キャッシュされたリソースなどのブラウザーデータを保存するために、ユーザーデータフォルダーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="58e07-105">WebView2 applications interact with user data folders to store browser data, such as cookies, permissions, and cached resources.</span></span>  <span data-ttu-id="58e07-106">WebView2 コントロールの各インスタンスは、ユーザーデータフォルダーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="58e07-106">Each instance of a WebView2 control is associated with a user data folder.</span></span>  <span data-ttu-id="58e07-107">各ユーザーデータフォルダーは、ユーザーに対して一意です。</span><span class="sxs-lookup"><span data-stu-id="58e07-107">Each user data folder is unique to a user.</span></span>  

## <span data-ttu-id="58e07-108">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="58e07-108">Best Practices</span></span>  

<span data-ttu-id="58e07-109">ユーザーデータフォルダーは、WebView2 によって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="58e07-109">User data folders are created automatically by WebView2.</span></span>  <span data-ttu-id="58e07-110">WebView2 の開発者は、ユーザーデータフォルダーの有効期間を制御します。</span><span class="sxs-lookup"><span data-stu-id="58e07-110">WebView2 developers control the lifetime of the user data folder.</span></span>  <span data-ttu-id="58e07-111">アプリケーションでアプリケーションセッションのユーザーデータを再利用する場合は、ユーザーデータフォルダーを保存することを検討してください。そうしないと、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="58e07-111">If your application re-uses user data from application sessions, consider saving the user data folders, otherwise you may delete them.</span></span>  <span data-ttu-id="58e07-112">ユーザーデータフォルダーを管理する方法を決定する際には、次のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="58e07-112">Consider the following scenarios when deciding how to manage your user data folders:</span></span>  

*   <span data-ttu-id="58e07-113">同じユーザーがアプリケーションを繰り返し使っていて、アプリケーションの web コンテンツがユーザーのデータに依存している場合は、ユーザーデータフォルダーを保存します。</span><span class="sxs-lookup"><span data-stu-id="58e07-113">If the same user uses your application repeatedly, and the web content of the application relies on the user's data, save the user data folder.</span></span>  <span data-ttu-id="58e07-114">複数のユーザーがアプリケーションを繰り返し使用している場合は、新しいユーザーごとに新しいユーザーデータフォルダーを作成し、各ユーザーのユーザーデータフォルダーを保存します。</span><span class="sxs-lookup"><span data-stu-id="58e07-114">If multiple users use your application repeatedly, create a new user data folder for each new user, and save the user data folder of each user.</span></span>
*   <span data-ttu-id="58e07-115">アプリケーションに繰り返しユーザーがない場合は、ユーザーごとに新しいユーザーデータフォルダーを作成し、以前のユーザーデータフォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="58e07-115">If your application does not have repeat users, create a new user data folder for each user, and delete the previous user data folder.</span></span>  

## <span data-ttu-id="58e07-116">ユーザーデータフォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="58e07-116">Create user data folders</span></span>  

<span data-ttu-id="58e07-117">ユーザーデータフォルダーの場所を指定するに `userDataFolder` は、 [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \ (Win32 \) または[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \ (.net \) を呼び出すときにパラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="58e07-117">To specify the location of the user data folder, include the `userDataFolder` parameter when calling [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \(Win32\) or [CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \(.NET\).</span></span>  <span data-ttu-id="58e07-118">作成後、WebView2 コントロールからのブラウザーデータは、のサブフォルダーに保存され `userDataFolder` ます。</span><span class="sxs-lookup"><span data-stu-id="58e07-118">After creation, browser data from your WebView2 control is stored in a subfolder of `userDataFolder`.</span></span>  <span data-ttu-id="58e07-119">`userDataFolder`指定しない場合、WebView2 は次のように既定の場所にユーザーデータフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="58e07-119">When `userDataFolder` is not specified, WebView2 creates user data folders at default locations as follows:</span></span>  

*   <span data-ttu-id="58e07-120">パッケージ化された Windows ストアアプリの場合、既定のユーザーフォルダーは `ApplicationData\LocalFolder` パッケージのフォルダー内のサブフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="58e07-120">For packaged Windows Store apps, the default user folder is the `ApplicationData\LocalFolder` subfolder in the package's  folder.</span></span>  
*   <span data-ttu-id="58e07-121">既存のデスクトップアプリの場合、既定のユーザーデータフォルダーは、アプリケーションの exe パスになり `.WebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="58e07-121">For existing desktop apps, the default user data folder is the exe path of your application + `.WebView2`.</span></span>  <span data-ttu-id="58e07-122">既定の代わりに、ユーザーデータフォルダーを指定して、他のすべてのアプリデータが保存されているフォルダーと同じフォルダーに作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58e07-122">Instead of using the default, we recommend that you specify a user data folder, and that you create it in the same folder where all other app data is stored.</span></span>  

## <span data-ttu-id="58e07-123">ユーザーデータフォルダーを削除する</span><span class="sxs-lookup"><span data-stu-id="58e07-123">Delete user data folders</span></span>  

<span data-ttu-id="58e07-124">アプリケーションでユーザーデータフォルダーを削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="58e07-124">Your application may need to delete user data folders:</span></span>  

*   <span data-ttu-id="58e07-125">アプリをアンインストールする場合。</span><span class="sxs-lookup"><span data-stu-id="58e07-125">When uninstalling your app.</span></span>  <span data-ttu-id="58e07-126">パッケージ化された Windows ストアアプリをアンインストールする場合、Windows はユーザーデータフォルダーを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="58e07-126">If you are uninstalling packaged Windows Store apps, Windows deletes user data folders automatically.</span></span>  
*   <span data-ttu-id="58e07-127">を選び、すべての閲覧データ履歴をクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="58e07-127">To clean up all browsing data history.</span></span>  
*   <span data-ttu-id="58e07-128">データの破損を回復します。</span><span class="sxs-lookup"><span data-stu-id="58e07-128">To recover from data corruption.</span></span>  
*   <span data-ttu-id="58e07-129">以前のセッションデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="58e07-129">To remove previous session data.</span></span>  

> [!NOTE]
> <span data-ttu-id="58e07-130">ユーザーデータフォルダー内のファイルは、WebView2 アプリケーションが終了した後も引き続き使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58e07-130">Files in user data folders may still be in use after the WebView2 application is closed.</span></span>  <span data-ttu-id="58e07-131">この場合は、ブラウザーのプロセスとすべての子プロセスが終了するのを待ってから、フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="58e07-131">In this situation, wait for the browser process and all child processes to exit before deleting the folder.</span></span>  <span data-ttu-id="58e07-132">WebView2 のプロパティを使用して、ブラウザープロセスのプロセス id を取得でき `BrowserProcessId` ます。</span><span class="sxs-lookup"><span data-stu-id="58e07-132">You may retrieve the process id of the browser process using the `BrowserProcessId` property of the WebView2.</span></span>  

## <span data-ttu-id="58e07-133">ユーザーデータフォルダーを共有する</span><span class="sxs-lookup"><span data-stu-id="58e07-133">Share user data folders</span></span>  

<span data-ttu-id="58e07-134">WebView2 コントロールでは、同じユーザーデータフォルダーを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="58e07-134">WebView2 controls may share the same user data folders to:</span></span>  

*   <span data-ttu-id="58e07-135">1つのブラウザープロセスで実行して、[システムリソースを最適化](../concepts/process-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="58e07-135">[Optimize system resources](../concepts/process-model.md) by running in one browser process.</span></span>  
*   <span data-ttu-id="58e07-136">ブラウザー履歴とキャッシュリソースを共有します。</span><span class="sxs-lookup"><span data-stu-id="58e07-136">Share browser history and cached resources.</span></span>  

<span data-ttu-id="58e07-137">ユーザーデータフォルダーを共有する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="58e07-137">Consider the following when sharing user data folders:</span></span>  

1.  <span data-ttu-id="58e07-138">WebView2 コントロールを再作成して、ブラウザーのバージョンを更新するには、 [add_NewBrowserVersionAvailable](../reference/win32/0-9-538/icorewebview2environment.md#add_newbrowserversionavailable) \ (Win32 \) または[NewexitserverWebView2 available](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) \ (.net \) のイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="58e07-138">When re-creating WebView2 controls to update browser versions using [add_NewBrowserVersionAvailable](../reference/win32/0-9-538/icorewebview2environment.md#add_newbrowserversionavailable) \(Win32\) or [NewBrowserVersionAvailable](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) \(.NET\) events, ensure browser processes exit and close WebView2 controls that share the same user data folder.</span></span>  <span data-ttu-id="58e07-139">ブラウザープロセスのプロセス id を取得するには、 `BrowserProcessId` WebView2 コントロールのプロパティを使います。</span><span class="sxs-lookup"><span data-stu-id="58e07-139">To retrieve the process id of the browser process, use the `BrowserProcessId` property of the WebView2 control.</span></span>  

2.  <span data-ttu-id="58e07-140">同じユーザーデータフォルダーを共有する WebView2 コントロールでは、 [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \ (Win32 \) または[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \ (.net \) に同じオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58e07-140">WebView2 controls that share the same user data folder must use the same options for [ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) \(Win32\) or [CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) \(.NET\).</span></span>  <span data-ttu-id="58e07-141">満たされていない場合、WebView2 の作成は失敗 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` します。</span><span class="sxs-lookup"><span data-stu-id="58e07-141">If not, the WebView2 creation will fail with `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)`.</span></span>  

<span data-ttu-id="58e07-142">アプリケーションのさまざまな部分を分離したり、WebView2 コントロール間でデータを共有したりする必要がない場合は、別のユーザーデータフォルダーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="58e07-142">To isolate different parts of your application or when sharing data between WebView2 controls is not needed, you may choose to use different user data folders.</span></span>  <span data-ttu-id="58e07-143">たとえば、アプリケーションは2つの WebView2 コントロールで構成されています。1つはアドバタイズを表示し、もう一方はアプリケーションのコンテンツを表示することです。</span><span class="sxs-lookup"><span data-stu-id="58e07-143">For example, an application may consist of two WebView2 controls, one for displaying an advertisement and the other for displaying application content.</span></span>  <span data-ttu-id="58e07-144">このシナリオでは、開発者は、WebView2 コントロールごとに異なるユーザーデータフォルダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="58e07-144">In this scenario, developers may opt to use different user data folders for each WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="58e07-145">WebView2 browser の各プロセスでは、追加のメモリとディスク領域が消費されます。</span><span class="sxs-lookup"><span data-stu-id="58e07-145">Each WebView2 browser process consumes additional memory and disk space.</span></span>  <span data-ttu-id="58e07-146">そのため、同時に複数のユーザーデータフォルダーを使用する WebView2s は実行しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58e07-146">Therefore, we recommend not running WebView2s with too many different user data folders at the same time.</span></span>  
