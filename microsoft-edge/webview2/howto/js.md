---
description: WebView2 アプリで複雑なシナリオで JavaScript を使用する方法について説明します。
title: WebView2 アプリで JavaScript を使う
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f6e59acb0c4bf8ad5357aba87e0359d3b103ed63
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119067"
---
# 拡張シナリオでの、WebView での JavaScript の使用  

WebView2 コントロールで JavaScript を使うと、要件に合わせてネイティブアプリをカスタマイズできます。  この記事では、WebView2 で JavaScript を使用する方法について説明し、advanced WebView2 の機能と機能を使用して開発する方法について説明します。  

## 始める前に  

この記事では、既に作業中のプロジェクトがあることを前提としています。  プロジェクトを持っておらず、フォローする必要がある場合は、 [WebView2 のファーストステップガイド][Webview2GettingstartedWpf]に移動します。  

## 基本的な WebView2 関数  

WebView アプリで JavaScript の埋め込みを開始するには、次の関数を使用します。  

| API  | 説明  |
|:--- |:--- |  
| [すべてのユーティリティ][Webview2ReferenceWpf09515MicrosoftWebExecutescriptasync] | WebView コントロールで JavaScript を実行します。 詳細については、「はじめに」チュートリアルを参照してください。 |
| [Ondocumentの使い方非同期][Webview2ReferenceWin3209538Icorewebview2Addscripttoexecuteondocumentcreated] | ドキュメントオブジェクトモデル \ (DOM \) を作成するときに実行されます。 |
      
## シナリオ: 専用スクリプトファイルを実行する  

このセクションでは、WebView2 コントロールから専用の JavaScript ファイルにアクセスします。  

> [!NOTE]
> Javascript インラインの書き込みは JavaScript のクイックコマンドでは効率的な場合がありますが、JavaScript の色のテーマと行の書式設定が失われるため、Visual Studio でコードの大部分を記述するのが困難になります。  

この問題を解決するには、コードで個別の JavaScript ファイルを作成し、パラメーターを使ってそのファイルへの参照を渡し `ExecuteScriptAsync` ます。  

1.  `.js`プロジェクトでファイルを作成し、実行する JavaScript コードを追加します。  たとえば、という名前のファイルを作成 `script.js` します。  
1.  JavaScript ファイルをに渡す文字列に変換し `ExecuteScriptAsync` ます。  
    1.  JavaScript ファイルを文字列に変換するには、次のコードスニペットをコピーします。  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  コードをに貼り付け `MainWindow.xaml.cs` ます。  
1.  を使用してテキスト変数を渡し `ExecuteScriptAsync` ます。  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## シナリオ: ドラッグアンドドロップ機能を削除する  

このセクションでは、JavaScript を使って WebView2 control からドラッグアンドドロップ機能を削除します。  

まず、現在のドラッグアンドドロップ機能について説明します。  

1.  ドラッグアンドドロップのためにファイルを作成し `.txt` ます。  たとえば、という名前のファイルを作成し、 `contoso.txt` そのファイルにテキストを追加します。  
1.  プロジェクトを実行します。  
1.  ファイルを WebView コントロールにドラッグアンドドロップし `contoso.txt` ます。  新しいウィンドウが開きます。これはサンプルプロジェクトのコードの結果です。  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="contoso.txt のドラッグアンドドロップの結果" lightbox="./media/dragtext.png":::
       contoso.txt のドラッグアンドドロップの結果  
    :::image-end:::  

次に、WebView2 コントロールからドラッグアンドドロップ機能を削除するコードを追加します。  

1.  次のコードスニペットを in にコピーして貼り付け `InitializeAsync()` `MainWindow.xaml.cs` ます。   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  プロジェクトを実行します。  
1.  ドラッグアンドドロップを試してみてください `contoso.txt` 。  ドラッグアンドドロップができないことを確認します。  

## シナリオ: コンテキストメニューの削除  

このセクションで、WebView2 コントロールから既定のコンテキストメニューを削除します。  

まず、現在のコンテキストメニュー機能について説明します。  

1.  プロジェクトを実行します。  
1.  WebView2 コントロールの任意の場所にマウスポインターを移動し、コンテキストメニューを開きます (\ を右クリックします)。  コンテキストメニューに既定の選択肢が表示されます。  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="contoso.txt のドラッグアンドドロップの結果" lightbox="./media/contextmenu.png":::
       既定の選択肢が表示されたコンテキストメニュー  
    :::image-end:::  
    
次に、WebView2 コントロールからコンテキストメニュー機能を削除するコードを追加します。  

1.  次のコードスニペットを in にコピーして貼り付け `InitializeAsync()` `MainWindow.xaml.cs` ます。    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  コードをもう一度実行します。  コンテキストメニューを開くことができないことを確認します (\ [\] を右クリックします)。  
   
## 関連項目  

*   WebView2 の使用を開始する方法の詳細については、 [WebView2 の概要ガイド][Webview2MainGettingStarted]を参照してください。  
*   WebView2 機能の包括的な例については、GitHub 上の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。  
*   WebView2 Api の詳細については、 [api リファレンス][Webview2ApiReference]に移動してください。  
*   WebView2 の詳細については、 [WebView2 のリソース][Webview2MainNextSteps]を参照してください。  

## Microsoft Edge WebView チームと連絡を取り合う  

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
