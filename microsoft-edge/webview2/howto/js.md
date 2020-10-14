---
description: WebView2 アプリで複雑なシナリオで JavaScript を使用する方法について説明します。
title: WebView2 アプリで JavaScript を使う
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/12/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 5312cf6209e81a1bbcfa33f324e9b8e7ef099cec
ms.sourcegitcommit: aec8d3482465dfb9a4f5f61c5eded1ff6f66d71d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117706"
---
# <span data-ttu-id="206ad-104">拡張シナリオでの、WebView での JavaScript の使用</span><span class="sxs-lookup"><span data-stu-id="206ad-104">Use JavaScript in WebView for extended scenarios</span></span>  

<span data-ttu-id="206ad-105">WebView2 コントロールで JavaScript を使うと、要件に合わせてネイティブアプリをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="206ad-105">Using JavaScript in WebView2 controls allows you to customize native apps to meet your requirements.</span></span>  <span data-ttu-id="206ad-106">この記事では、WebView2 で JavaScript を使用する方法について説明し、advanced WebView2 の機能と機能を使用して開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="206ad-106">This article explores how to use JavaScript in WebView2, and reviews how to develop using advanced WebView2 features and functionality.</span></span>  

## <span data-ttu-id="206ad-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="206ad-107">Before you begin</span></span>  

<span data-ttu-id="206ad-108">この記事では、既に作業中のプロジェクトがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="206ad-108">This article assumes that you already have a working project.</span></span>  <span data-ttu-id="206ad-109">プロジェクトを持っておらず、フォローする必要がある場合は、 [WebView2 のファーストステップガイド][Webview2GettingstartedWpf]に移動します。</span><span class="sxs-lookup"><span data-stu-id="206ad-109">If you do not have a project and want to follow along, navigate to the [WebView2 Getting Started Guide][Webview2GettingstartedWpf].</span></span>  

## <span data-ttu-id="206ad-110">基本的な WebView2 関数</span><span class="sxs-lookup"><span data-stu-id="206ad-110">Basic WebView2 Functions</span></span>  

<span data-ttu-id="206ad-111">WebView アプリで JavaScript の埋め込みを開始するには、次の関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="206ad-111">Use the following functions to begin embedding JavaScript in your WebView app.</span></span>  

| <span data-ttu-id="206ad-112">API</span><span class="sxs-lookup"><span data-stu-id="206ad-112">API</span></span>  | <span data-ttu-id="206ad-113">説明</span><span class="sxs-lookup"><span data-stu-id="206ad-113">Description</span></span>  |
|:--- |:--- |  
| [<span data-ttu-id="206ad-114">すべてのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="206ad-114">ExecuteScriptAsync</span></span>][Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync] | <span data-ttu-id="206ad-115">WebView コントロールで JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="206ad-115">Run JavaScript in a WebView control.</span></span> <span data-ttu-id="206ad-116">詳細については、「はじめに」チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="206ad-116">For more information, navigate to the Getting Started tutorial.</span></span> |
| [<span data-ttu-id="206ad-117">Ondocumentの使い方非同期</span><span class="sxs-lookup"><span data-stu-id="206ad-117">OnDocumentCreatedAsync</span></span>][Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated] | <span data-ttu-id="206ad-118">ドキュメントオブジェクトモデル \ (DOM \) を作成するときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="206ad-118">Runs when the Document Object Model \(DOM\) is created.</span></span> |
      
## <span data-ttu-id="206ad-119">シナリオ: 専用スクリプトファイルを実行する</span><span class="sxs-lookup"><span data-stu-id="206ad-119">Scenario:  Running a dedicated script file</span></span>  

<span data-ttu-id="206ad-120">このセクションでは、WebView2 コントロールから専用の JavaScript ファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="206ad-120">In this section, access a dedicated JavaScript file from your WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="206ad-121">Javascript インラインの書き込みは JavaScript のクイックコマンドでは効率的な場合がありますが、JavaScript の色のテーマと行の書式設定が失われるため、Visual Studio でコードの大部分を記述するのが困難になります。</span><span class="sxs-lookup"><span data-stu-id="206ad-121">Although writing JavaScript inline may be efficient for quick JavaScript commands, you lose JavaScript color themes and line formatting that makes it difficult to write large sections of code in Visual Studio.</span></span>  

<span data-ttu-id="206ad-122">この問題を解決するには、コードで個別の JavaScript ファイルを作成し、パラメーターを使ってそのファイルへの参照を渡し `ExecuteScriptAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-122">To solve the problem, create a separate JavaScript file with your code, and then pass a reference to that file using the `ExecuteScriptAsync` parameters.</span></span>  

1.  <span data-ttu-id="206ad-123">`.js`プロジェクトでファイルを作成し、実行する JavaScript コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="206ad-123">Create a `.js` file in your project, and add the JavaScript code that you want to run.</span></span>  <span data-ttu-id="206ad-124">たとえば、という名前のファイルを作成 `script.js` します。</span><span class="sxs-lookup"><span data-stu-id="206ad-124">For example, create a file called `script.js`.</span></span>  
1.  <span data-ttu-id="206ad-125">JavaScript ファイルをに渡す文字列に変換し `ExecuteScriptAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-125">Convert the JavaScript file to a string that is passed to `ExecuteScriptAsync`.</span></span>  
    1.  <span data-ttu-id="206ad-126">JavaScript ファイルを文字列に変換するには、次のコードスニペットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="206ad-126">To convert your JavaScript file into a string, copy the following code snippet.</span></span>  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  <span data-ttu-id="206ad-127">コードをに貼り付け `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-127">Paste the code into `MainWindow.xaml.cs`.</span></span>  
1.  <span data-ttu-id="206ad-128">を使用してテキスト変数を渡し `ExecuteScriptAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-128">Pass your text variable using `ExecuteScriptAsync`.</span></span>  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## <span data-ttu-id="206ad-129">シナリオ: ドラッグアンドドロップ機能を削除する</span><span class="sxs-lookup"><span data-stu-id="206ad-129">Scenario:  Remove drag-and-drop functionality</span></span>  

<span data-ttu-id="206ad-130">このセクションでは、JavaScript を使って WebView2 control からドラッグアンドドロップ機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="206ad-130">In this section, use JavaScript to remove the drag-and-drop functionality from your WebView2 control.</span></span>  

<span data-ttu-id="206ad-131">まず、現在のドラッグアンドドロップ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="206ad-131">To begin, explore the current drag-and-drop functionality.</span></span>  

1.  <span data-ttu-id="206ad-132">ドラッグアンドドロップのためにファイルを作成し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-132">Create a `.txt` file in order to drag-and-drop.</span></span>  <span data-ttu-id="206ad-133">たとえば、という名前のファイルを作成し、 `contoso.txt` そのファイルにテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="206ad-133">For example, create a file named `contoso.txt` and add text to it.</span></span>  
1.  <span data-ttu-id="206ad-134">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="206ad-134">Run your project.</span></span>  
1.  <span data-ttu-id="206ad-135">ファイルを WebView コントロールにドラッグアンドドロップし `contoso.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-135">Drag-and-drop the `contoso.txt` file onto the WebView control.</span></span>  <span data-ttu-id="206ad-136">新しいウィンドウが開きます。これはサンプルプロジェクトのコードの結果です。</span><span class="sxs-lookup"><span data-stu-id="206ad-136">A new window opens, which is the result of the code in your sample project.</span></span>  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="contoso.txt のドラッグアンドドロップの結果" lightbox="./media/dragtext.png":::
       <span data-ttu-id="206ad-138">contoso.txt のドラッグアンドドロップの結果</span><span class="sxs-lookup"><span data-stu-id="206ad-138">Result of dragging and dropping contoso.txt</span></span>  
    :::image-end:::  

<span data-ttu-id="206ad-139">次に、WebView2 コントロールからドラッグアンドドロップ機能を削除するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="206ad-139">Now, add code to remove the drag-and-drop functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="206ad-140">次のコードスニペットを in にコピーして貼り付け `InitializeAsync()` `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-140">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  <span data-ttu-id="206ad-141">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="206ad-141">Run your project.</span></span>  
1.  <span data-ttu-id="206ad-142">ドラッグアンドドロップを試してみてください `contoso.txt` 。</span><span class="sxs-lookup"><span data-stu-id="206ad-142">Try to drag-and-drop `contoso.txt`.</span></span>  <span data-ttu-id="206ad-143">ドラッグアンドドロップができないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="206ad-143">Confirm that you are not able to drag-and-drop.</span></span>  

## <span data-ttu-id="206ad-144">シナリオ: コンテキストメニューの削除</span><span class="sxs-lookup"><span data-stu-id="206ad-144">Scenario:  Removing the Context Menu</span></span>  

<span data-ttu-id="206ad-145">このセクションで、WebView2 コントロールから既定のコンテキストメニューを削除します。</span><span class="sxs-lookup"><span data-stu-id="206ad-145">In this section, remove the default context menu from your WebView2 control.</span></span>  

<span data-ttu-id="206ad-146">まず、現在のコンテキストメニュー機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="206ad-146">To begin, explore the current contextual menu functionality.</span></span>  

1.  <span data-ttu-id="206ad-147">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="206ad-147">Run your project.</span></span>  
1.  <span data-ttu-id="206ad-148">WebView2 コントロールの任意の場所にマウスポインターを移動し、コンテキストメニューを開きます (\ を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="206ad-148">Hover anywhere on the WebView2 control and open the context menu \(right-click\).</span></span>  <span data-ttu-id="206ad-149">コンテキストメニューに既定の選択肢が表示されます。</span><span class="sxs-lookup"><span data-stu-id="206ad-149">The context menu displays the default choices.</span></span>  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="contoso.txt のドラッグアンドドロップの結果" lightbox="./media/contextmenu.png":::
       <span data-ttu-id="206ad-151">既定の選択肢が表示されたコンテキストメニュー</span><span class="sxs-lookup"><span data-stu-id="206ad-151">The context menu showing the default choices</span></span>  
    :::image-end:::  
    
<span data-ttu-id="206ad-152">次に、WebView2 コントロールからコンテキストメニュー機能を削除するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="206ad-152">Now add code to remove the contextual menu functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="206ad-153">次のコードスニペットを in にコピーして貼り付け `InitializeAsync()` `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="206ad-153">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  <span data-ttu-id="206ad-154">コードをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="206ad-154">Run the code again.</span></span>  <span data-ttu-id="206ad-155">コンテキストメニューを開くことができないことを確認します (\ [\] を右クリックします)。</span><span class="sxs-lookup"><span data-stu-id="206ad-155">Confirm that you're not able to open a context menu \(right-click\).</span></span>  
   
## <span data-ttu-id="206ad-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="206ad-156">See also</span></span>  

*   <span data-ttu-id="206ad-157">WebView2 の使用を開始する方法の詳細については、 [WebView2 の概要ガイド][Webview2MainGettingStarted]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="206ad-157">For more information on getting started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="206ad-158">WebView2 機能の包括的な例については、GitHub 上の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="206ad-158">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>  
*   <span data-ttu-id="206ad-159">WebView2 Api の詳細については、 [api リファレンス][Webview2ApiReference]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="206ad-159">For detailed information on WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>  
*   <span data-ttu-id="206ad-160">WebView2 の詳細については、 [WebView2 のリソース][Webview2MainNextSteps]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="206ad-160">For more information on WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>  

## <span data-ttu-id="206ad-161">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="206ad-161">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  


[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated]: ../reference/win32/0-9-538/icorewebview2.md#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated-0.9.579 ICoreWebView2 |Microsoft ドキュメント"  
[Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync]: ../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync "WebView2 クラス | WebView2 クラスの場合は、このサイトをお選びください。Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
