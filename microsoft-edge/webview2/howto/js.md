---
description: WebView2 アプリの複雑なシナリオで JavaScript を使用する方法について説明します。
title: WebView2 アプリで JavaScript を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: da04d1e24b95dfa7ea477bbd228fd46b64727ec3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230937"
---
# <span data-ttu-id="bc099-104">拡張シナリオで WebView で JavaScript を使用する</span><span class="sxs-lookup"><span data-stu-id="bc099-104">Use JavaScript in WebView for extended scenarios</span></span>  

<span data-ttu-id="bc099-105">WebView2 コントロールで JavaScript を使用すると、要件を満たしたネイティブ アプリをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bc099-105">Using JavaScript in WebView2 controls allows you to customize native apps to meet your requirements.</span></span>  <span data-ttu-id="bc099-106">この記事では、WebView2 で JavaScript を使用する方法について説明し、高度な WebView2 の機能を使用して開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc099-106">This article explores how to use JavaScript in WebView2, and reviews how to develop using advanced WebView2 features and functionality.</span></span>  

## <span data-ttu-id="bc099-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="bc099-107">Before you begin</span></span>  

<span data-ttu-id="bc099-108">この記事では、作業プロジェクトが既に存在すると想定しています。</span><span class="sxs-lookup"><span data-stu-id="bc099-108">This article assumes that you already have a working project.</span></span>  <span data-ttu-id="bc099-109">プロジェクトを持ってない場合は [、WebView2][Webview2GettingstartedWpf]の開始ガイドに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc099-109">If you do not have a project and want to follow along, navigate to the [WebView2 Getting Started Guide][Webview2GettingstartedWpf].</span></span>  

## <span data-ttu-id="bc099-110">基本的な WebView2 関数</span><span class="sxs-lookup"><span data-stu-id="bc099-110">Basic WebView2 Functions</span></span>  

<span data-ttu-id="bc099-111">次の関数を使用して、WebView アプリへの JavaScript の埋め込みを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc099-111">Use the following functions to begin embedding JavaScript in your WebView app.</span></span>  

| <span data-ttu-id="bc099-112">API</span><span class="sxs-lookup"><span data-stu-id="bc099-112">API</span></span>  | <span data-ttu-id="bc099-113">説明</span><span class="sxs-lookup"><span data-stu-id="bc099-113">Description</span></span>  |
|:--- |:--- |  
| [<span data-ttu-id="bc099-114">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="bc099-114">ExecuteScriptAsync</span></span>][Webview2ReferenceWpfMicrosoftWebExecutescriptasync] | <span data-ttu-id="bc099-115">WebView コントロールで JavaScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc099-115">Run JavaScript in a WebView control.</span></span> <span data-ttu-id="bc099-116">詳細については、「使い始める」チュートリアルに移動してください。</span><span class="sxs-lookup"><span data-stu-id="bc099-116">For more information, navigate to the Getting Started tutorial.</span></span> |
| [<span data-ttu-id="bc099-117">OnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="bc099-117">OnDocumentCreatedAsync</span></span>][Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated] | <span data-ttu-id="bc099-118">ドキュメント オブジェクト モデル \(DOM\) が作成されると実行されます。</span><span class="sxs-lookup"><span data-stu-id="bc099-118">Runs when the Document Object Model \(DOM\) is created.</span></span> |
      
## <span data-ttu-id="bc099-119">シナリオ: 専用のスクリプト ファイルを実行する</span><span class="sxs-lookup"><span data-stu-id="bc099-119">Scenario:  Running a dedicated script file</span></span>  

<span data-ttu-id="bc099-120">このセクションでは、WebView2 コントロールから専用の JavaScript ファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bc099-120">In this section, access a dedicated JavaScript file from your WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="bc099-121">JavaScript をインラインで記述することは、JavaScript コマンドを簡単に記述する方が効率的ですが、JavaScript の色のテーマと線の書式設定が失われるので、Visual Studio でコードの大きなセクションを記述するのが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="bc099-121">Although writing JavaScript inline may be efficient for quick JavaScript commands, you lose JavaScript color themes and line formatting that makes it difficult to write large sections of code in Visual Studio.</span></span>  

<span data-ttu-id="bc099-122">この問題を解決するには、コードを含む別の JavaScript ファイルを作成し、パラメーターを使用してそのファイルへの参照を渡 `ExecuteScriptAsync` します。</span><span class="sxs-lookup"><span data-stu-id="bc099-122">To solve the problem, create a separate JavaScript file with your code, and then pass a reference to that file using the `ExecuteScriptAsync` parameters.</span></span>  

1.  <span data-ttu-id="bc099-123">プロジェクトに `.js` ファイルを作成し、実行する JavaScript コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc099-123">Create a `.js` file in your project, and add the JavaScript code that you want to run.</span></span>  <span data-ttu-id="bc099-124">たとえば、ファイルを作成します `script.js` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-124">For example, create a file called `script.js`.</span></span>  
1.  <span data-ttu-id="bc099-125">JavaScript ファイルを、渡される文字列に変換します `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-125">Convert the JavaScript file to a string that is passed to `ExecuteScriptAsync`.</span></span>  
    1.  <span data-ttu-id="bc099-126">JavaScript ファイルを文字列に変換するには、次のコード スニペットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bc099-126">To convert your JavaScript file into a string, copy the following code snippet.</span></span>  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  <span data-ttu-id="bc099-127">にコードを貼り付けます `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-127">Paste the code into `MainWindow.xaml.cs`.</span></span>  
1.  <span data-ttu-id="bc099-128">を使用してテキスト変数を渡します `ExecuteScriptAsync` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-128">Pass your text variable using `ExecuteScriptAsync`.</span></span>  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## <span data-ttu-id="bc099-129">シナリオ: ドラッグ アンド ドロップ機能を削除する</span><span class="sxs-lookup"><span data-stu-id="bc099-129">Scenario:  Remove drag-and-drop functionality</span></span>  

<span data-ttu-id="bc099-130">このセクションでは、JavaScript を使用して、WebView2 コントロールからドラッグ アンド ドロップ機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="bc099-130">In this section, use JavaScript to remove the drag-and-drop functionality from your WebView2 control.</span></span>  

<span data-ttu-id="bc099-131">まず、現在のドラッグ アンド ドロップ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc099-131">To begin, explore the current drag-and-drop functionality.</span></span>  

1.  <span data-ttu-id="bc099-132">ドラッグ アンド `.txt` ドロップでファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc099-132">Create a `.txt` file in order to drag-and-drop.</span></span>  <span data-ttu-id="bc099-133">たとえば、名前を付け、テキストを追加 `contoso.txt` するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc099-133">For example, create a file named `contoso.txt` and add text to it.</span></span>  
1.  <span data-ttu-id="bc099-134">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc099-134">Run your project.</span></span>  
1.  <span data-ttu-id="bc099-135">ファイルを `contoso.txt` WebView コントロールにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="bc099-135">Drag-and-drop the `contoso.txt` file onto the WebView control.</span></span>  <span data-ttu-id="bc099-136">新しいウィンドウが開きます。このウィンドウは、サンプル プロジェクトのコードの結果です。</span><span class="sxs-lookup"><span data-stu-id="bc099-136">A new window opens, which is the result of the code in your sample project.</span></span>  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="ドラッグ アンド ドロップの結果contoso.txt" lightbox="./media/dragtext.png":::
       <span data-ttu-id="bc099-138">ドラッグ アンド ドロップの結果contoso.txt</span><span class="sxs-lookup"><span data-stu-id="bc099-138">Result of dragging and dropping contoso.txt</span></span>  
    :::image-end:::  

<span data-ttu-id="bc099-139">次に、WebView2 コントロールからドラッグ アンド ドロップ機能を削除するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc099-139">Now, add code to remove the drag-and-drop functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="bc099-140">次のコード スニペットをコピーして貼り付 `InitializeAsync()` けます `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-140">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  <span data-ttu-id="bc099-141">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc099-141">Run your project.</span></span>  
1.  <span data-ttu-id="bc099-142">ドラッグ アンド ドロップしてみてください `contoso.txt` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-142">Try to drag-and-drop `contoso.txt`.</span></span>  <span data-ttu-id="bc099-143">ドラッグ アンド ドロップができないのを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc099-143">Confirm that you are not able to drag-and-drop.</span></span>  

## <span data-ttu-id="bc099-144">シナリオ: コンテキスト メニューの削除</span><span class="sxs-lookup"><span data-stu-id="bc099-144">Scenario:  Removing the Context Menu</span></span>  

<span data-ttu-id="bc099-145">このセクションでは、WebView2 コントロールから既定のコンテキスト メニューを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc099-145">In this section, remove the default context menu from your WebView2 control.</span></span>  

<span data-ttu-id="bc099-146">まず、現在のコンテキスト メニュー機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="bc099-146">To begin, explore the current contextual menu functionality.</span></span>  

1.  <span data-ttu-id="bc099-147">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc099-147">Run your project.</span></span>  
1.  <span data-ttu-id="bc099-148">WebView2 コントロールの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc099-148">Hover anywhere on the WebView2 control and open the context menu \(right-click\).</span></span>  <span data-ttu-id="bc099-149">コンテキスト メニューに既定の選択肢が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc099-149">The context menu displays the default choices.</span></span>  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="既定の選択肢を示すコンテキスト メニュー" lightbox="./media/contextmenu.png":::
       <span data-ttu-id="bc099-151">既定の選択肢を示すコンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="bc099-151">The context menu showing the default choices</span></span>  
    :::image-end:::  
    
<span data-ttu-id="bc099-152">次に、WebView2 コントロールからコンテキスト メニュー機能を削除するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc099-152">Now add code to remove the contextual menu functionality from the WebView2 control.</span></span>  

1.  <span data-ttu-id="bc099-153">次のコード スニペットをコピーして貼り付 `InitializeAsync()` けます `MainWindow.xaml.cs` 。</span><span class="sxs-lookup"><span data-stu-id="bc099-153">Copy and paste the following code snippet into `InitializeAsync()` in `MainWindow.xaml.cs`.</span></span>    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  <span data-ttu-id="bc099-154">コードを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="bc099-154">Run the code again.</span></span>  <span data-ttu-id="bc099-155">コンテキスト メニュー \(右クリック\) を開くことができないか確認します。</span><span class="sxs-lookup"><span data-stu-id="bc099-155">Confirm that you're not able to open a context menu \(right-click\).</span></span>  
   
## <span data-ttu-id="bc099-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc099-156">See also</span></span>  

*   <span data-ttu-id="bc099-157">WebView2 の使用を開始する方法について詳しくは、「WebView2 の使い方ガイド [」をご覧ください][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="bc099-157">For more information on getting started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="bc099-158">WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc099-158">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>  
*   <span data-ttu-id="bc099-159">WebView2 API の詳細については、API リファレンスに [移動してください][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="bc099-159">For detailed information on WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>  
*   <span data-ttu-id="bc099-160">WebView2 の詳細については [、WebView2 リソースに移動します][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="bc099-160">For more information on WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>  

## <span data-ttu-id="bc099-161">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="bc099-161">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  


[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2GettingstartedWpf]: ../gettingstarted/wpf.md "WPF での WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated]: /microsoft-edge/webview2/reference/win32/icorewebview2#addscripttoexecuteondocumentcreated "AddScriptToExecuteOnDocumentCreated - 0.9.579 - interface ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
