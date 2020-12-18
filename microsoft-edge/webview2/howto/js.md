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
# 拡張シナリオで WebView で JavaScript を使用する  

WebView2 コントロールで JavaScript を使用すると、要件を満たしたネイティブ アプリをカスタマイズできます。  この記事では、WebView2 で JavaScript を使用する方法について説明し、高度な WebView2 の機能を使用して開発する方法について説明します。  

## 始める前に  

この記事では、作業プロジェクトが既に存在すると想定しています。  プロジェクトを持ってない場合は [、WebView2][Webview2GettingstartedWpf]の開始ガイドに移動します。  

## 基本的な WebView2 関数  

次の関数を使用して、WebView アプリへの JavaScript の埋め込みを開始します。  

| API  | 説明  |
|:--- |:--- |  
| [ExecuteScriptAsync][Webview2ReferenceWpfMicrosoftWebExecutescriptasync] | WebView コントロールで JavaScript を実行します。 詳細については、「使い始める」チュートリアルに移動してください。 |
| [OnDocumentCreatedAsync][Webview2ReferenceWin32Icorewebview2Addscripttoexecuteondocumentcreated] | ドキュメント オブジェクト モデル \(DOM\) が作成されると実行されます。 |
      
## シナリオ: 専用のスクリプト ファイルを実行する  

このセクションでは、WebView2 コントロールから専用の JavaScript ファイルにアクセスします。  

> [!NOTE]
> JavaScript をインラインで記述することは、JavaScript コマンドを簡単に記述する方が効率的ですが、JavaScript の色のテーマと線の書式設定が失われるので、Visual Studio でコードの大きなセクションを記述するのが難しくなります。  

この問題を解決するには、コードを含む別の JavaScript ファイルを作成し、パラメーターを使用してそのファイルへの参照を渡 `ExecuteScriptAsync` します。  

1.  プロジェクトに `.js` ファイルを作成し、実行する JavaScript コードを追加します。  たとえば、ファイルを作成します `script.js` 。  
1.  JavaScript ファイルを、渡される文字列に変換します `ExecuteScriptAsync` 。  
    1.  JavaScript ファイルを文字列に変換するには、次のコード スニペットをコピーします。  
        
        ```csharp
        string text = System.IO.File.ReadAllText(@"C:\PATH_TO_YOUR_FILE\script.js");
        ```  
        
    1.  にコードを貼り付けます `MainWindow.xaml.cs` 。  
1.  を使用してテキスト変数を渡します `ExecuteScriptAsync` 。  
    
    ```csharp
    await webView.CoreWebView2.ExecuteScriptAsync(text);
    ```  

## シナリオ: ドラッグ アンド ドロップ機能を削除する  

このセクションでは、JavaScript を使用して、WebView2 コントロールからドラッグ アンド ドロップ機能を削除します。  

まず、現在のドラッグ アンド ドロップ機能について説明します。  

1.  ドラッグ アンド `.txt` ドロップでファイルを作成します。  たとえば、名前を付け、テキストを追加 `contoso.txt` するファイルを作成します。  
1.  プロジェクトを実行します。  
1.  ファイルを `contoso.txt` WebView コントロールにドラッグ アンド ドロップします。  新しいウィンドウが開きます。このウィンドウは、サンプル プロジェクトのコードの結果です。  
    
    :::image type="complex" source="./media/dragtext.png" alt-text="ドラッグ アンド ドロップの結果contoso.txt" lightbox="./media/dragtext.png":::
       ドラッグ アンド ドロップの結果contoso.txt  
    :::image-end:::  

次に、WebView2 コントロールからドラッグ アンド ドロップ機能を削除するコードを追加します。  

1.  次のコード スニペットをコピーして貼り付 `InitializeAsync()` けます `MainWindow.xaml.cs` 。   
            
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('dragover',function(e){e.preventDefault();},false);");
    
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('drop',function(e){" +
    "e.preventDefault();" +
    "console.log(e.dataTransfer);" +
    "console.log(e.dataTransfer.files[0])" +
    "}, false);");
    ```  
          
1.  プロジェクトを実行します。  
1.  ドラッグ アンド ドロップしてみてください `contoso.txt` 。  ドラッグ アンド ドロップができないのを確認します。  

## シナリオ: コンテキスト メニューの削除  

このセクションでは、WebView2 コントロールから既定のコンテキスト メニューを削除します。  

まず、現在のコンテキスト メニュー機能を確認します。  

1.  プロジェクトを実行します。  
1.  WebView2 コントロールの任意の場所にマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開きます。  コンテキスト メニューに既定の選択肢が表示されます。  
    
    :::image type="complex" source="./media/contextmenu.png" alt-text="既定の選択肢を示すコンテキスト メニュー" lightbox="./media/contextmenu.png":::
       既定の選択肢を示すコンテキスト メニュー  
    :::image-end:::  
    
次に、WebView2 コントロールからコンテキスト メニュー機能を削除するコードを追加します。  

1.  次のコード スニペットをコピーして貼り付 `InitializeAsync()` けます `MainWindow.xaml.cs` 。    
        
    ```csharp   
    await webView.CoreWebView2.ExecuteScriptAsync("window.addEventListener('contextmenu', window => {window.preventDefault();});");
    ```  

1.  コードを再度実行します。  コンテキスト メニュー \(右クリック\) を開くことができないか確認します。  
   
## 関連項目  

*   WebView2 の使用を開始する方法について詳しくは、「WebView2 の使い方ガイド [」をご覧ください][Webview2MainGettingStarted]。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリに移動します。  
*   WebView2 API の詳細については、API リファレンスに [移動してください][Webview2ApiReference]。  
*   WebView2 の詳細については [、WebView2 リソースに移動します][Webview2MainNextSteps]。  

## Microsoft Edge WebView チームと連絡を取り合う  

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
