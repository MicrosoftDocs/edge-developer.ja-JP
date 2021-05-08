---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 01cd67897f7041bca0cedcee2cc3242f3ebcc962
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536036"
---
# <a name="get-started-debugging-webview2-apps"></a>WebView2 アプリのデバッグを開始する  

Microsoft Edge WebView2 コントロールの目的は、Web アプリ開発機能とネイティブ アプリ開発機能とツールの両方を組み合わせることです。  WebView2 アプリを開発する場合は、アプリをデバッグする必要があります。  この記事では、WebView2 アプリで Web コードとネイティブ コードの両方をデバッグするために使用するさまざまなツールの概要を説明します。  

## [<a name="microsoft-edge-devtools"></a>Microsoft Edge DevTools](#tab/devtools)  

[Microsoft Edge (クロム)][DevtoolsGuideChromiumMain]開発者ツールを使用して、WebView2 コントロールに表示される Web コンテンツを、Microsoft Edge に表示される別の Web ページでデバッグするのと同じ方法でデバッグします。  DevTools を開く場合は、WebView コントロールにフォーカスを設定し、次のいずれかのアクションを使用します。  

*   `F12` を選択します。  
*   を選択します `Ctrl` + `Shift` + `I` 。  
*   コンテキスト メニュー \(右クリック\) を開き、 を選択します `Inspect` 。  
    
詳細については [、「DevTools の概要」に移動します][DevtoolsGuideChromiumMain]。  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   DevTools のデバッグ  
:::image-end:::    

## [<a name="visual-studio"></a>Visual Studio](#tab/visualstudio)  

Visual Studio WebView2 アプリでは、Web およびネイティブ コード用のさまざまなデバッグ ツールが提供されます。  [Visual Studio] セクションでは、主に WebView コントロールのデバッグを行います。ただし、WebView コントロールのデバッグ方法Visual Studio通常どおり使用できます。  Win32 アプリまたはアドインでのみ Web およびネイティブ コードをデバッグするには、次Officeを使用します。  

> [!IMPORTANT]
> ネイティブ デバッガーが接続されたVisual Studioでアプリをデバッグすると、開発者ツールの代わりにネイティブ デバッガーが `F12` トリガーされる場合があります。  状況 `Ctrl` + `Shift` + `I` を回避するには、コンテキスト メニュー \(右クリック\) を選択するか、または使用します。  

開始する前に、次の要件を満たしていることを確認してください。  

*   スクリプトをデバッグするには、アプリをアプリ内から起動するVisual Studio。  
*   実行中の WebView2 プロセスにデバッガーを接続することはできません。  
*   2019 Visual Studio 16.4 プレビュー 2 以降をインストールします。  
    
スクリプト デバッガー ツールをインストールし、スクリプト デバッガー ツールをVisual Studio。  

1.  C++ によるデスクトップ開発で **JavaScript 診断** コンポーネントをインストールするには、 **次のアクションを実行します**。  
    1.  Windows エクスプローラー バーに「 」 と入力 `Visual Studio Installer` します。  
    1.  [インストーラー **Visual Studio開く** ] を選択します。  
    1.  [インストーラー] Visual Studioインストールされているバージョンで、[その他] ボタン**** を選択し、[変更] を**選択します**。  
    1.  [Visual Studio] の **[ワークロード] で****、[C++ のデスクトップ開発] 設定を選択**します。  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studioワークロードの変更画面" lightbox="./media/workloads.png":::
            Visual Studioワークロードの変更画面
        :::image-end:::  
        
    1.  [個別 **のコンポーネント] を選択します**。  
    1.  検索ボックスに「 」 と入力 `JavaScript diagnostics` します。  
    1.  **[JavaScript 診断] 設定を選択**します。  
    1.  [変更 **] を選択します**。 
        
        :::image type="complex" source="./media/indiv-comp.png" alt-text="Visual Studio個々のコンポーネントの変更] タブ" lightbox="./media/indiv-comp.png":::
           Visual Studio個々のコンポーネントの変更] タブ  
        :::image-end:::  
        
1.  WebView2 アプリのスクリプト デバッグを有効にする。  
    1.  WebView2 プロジェクトで、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を **選択します**。  
    1.  [構成プロパティ **] で、[** デバッグ] **を選択します**。  
    1.  [デバッガーの**種類] で****、[JavaScript (WebView2) ] を選択します**。  
        
        :::image type="complex" source="./media/enb-js.png" alt-text="Visual Studioデバッグ構成プロパティ" lightbox="./media/enb-js.png":::
           Visual Studio **デバッグ構成** プロパティ  
        :::image-end:::  
        
WebView2 アプリをデバッグするには、次のアクションを実行します。  

1.  ソース コードでブレークポイントを設定するには、行番号の左側にマウス ポインターを置き、ブレークポイントを設定します。  JS/TS デバッグ アダプターは、ソース パスマッピングを実行しない。  WebView2 に関連付けられたまったく同じパスを開く必要があります。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studioブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       Visual Studioブレークポイントの追加  
    :::image-end:::  
    
1.  デバッガーを実行するには、プラットフォームのビット サイズを選択し、[ローカル Windows デバッガー] の横にある緑色の再生ボタン **を選択します**。  アプリが実行され、デバッガーは作成された最初の WebView2 プロセスに接続します。  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio Windows デバッガー" lightbox="./media/run.png"::: 
       Visual Studio Windows **デバッガー**  
    :::image-end:::  
    
1.  デバッグ コンソール **で、** デバッガーからの出力を見つける。  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio デバッグ コンソール" lightbox="./media/console.png"::: 
       Visual Studio デバッグ **コンソール**  
    :::image-end:::  
    
## [<a name="visual-studio-code"></a>Visual Studio Code](#tab/visualstudiocode)  

Microsoft Visual Studioコードを使用して、WebView2 コントロールで実行されるスクリプトをデバッグします。  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

[Visual Studioコード] で、次のアクションを実行してコードをデバッグします。 

1.  プロジェクトにファイルが必要 `launch.json` です。  プロジェクトにファイルが含されていない場合は、次のコード スニペットを `launch.json` コピーし、新しいファイルを作成 `launch.json` します。  
    
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",
        "env": {
            // Customize for your app location if needed
            "Path": "%path%;e:/path/to/your/app/location; "
        },
        "useWebView": true,
        // The following two lines setup source path mapping, where `url` is the start page of your app, and `webRoot` is the top level directory with all your code files.
        "url": "file:///${workspaceFolder}/path/to/your/toplevel/foo.html",
        "webRoot": "${workspaceFolder}/path/to/your/assets"
    ```  
    
    > [!NOTE]
    > Visual Studioコード ソース パスマッピングには URL が必要になります。そのため、アプリの起動時にコマンド ライン パラメーターが受信されます。  必要に応じて、パラメーター `url` を無視しても問題ない場合があります。  
    
1.  ソース コードでブレークポイントを設定するには、行にカーソルを合わせると、 `F9`
    
    :::image type="complex" source="./media/breakpoint-vs.png" alt-text="ブレークポイントはコードでVisual Studioされます" lightbox="./media/breakpoint-vs.png":::
       ブレークポイントはコードでVisual Studioされます  
    :::image-end:::
    
1.  コードを実行します。  
    1.  [実行 **] タブ** で、ドロップダウン メニューから起動構成を選択します。  
    1.  アプリのデバッグを開始するには、[デバッグの開始] を選択します。これは、起動構成ドロップダウンの横にある緑色の三角形です。  
        
        :::image type="complex" source="./media/run-vs.png" alt-text=" Visual Studio [コードの実行] タブ" lightbox="./media/run-vs.png":::
           Visual Studio [コードの実行] タブ  
        :::image-end:::  
        
1.  デバッグ **出力とエラー** を表示するには、[デバッグ コンソール] を開きます。  
    
    :::image type="complex" source="./media/results-vs.png" alt-text=" Visual Studio コード デバッグ コンソール" lightbox="./media/results-vs.png":::
       Visual Studio コード デバッグ コンソール  
    :::image-end:::  
    
**詳細設定**:  

*   ターゲット Webview のデバッグ。 
    
    一部の WebView2 アプリでは、複数の WebView2 コントロールを使用できます。 この状況でデバッグする WebView2 コントロールを選択するには、ターゲット Webview2 デバッグを使用できます。 
    
    ターゲット `launch.json` Webview デバッグを使用するには、次のアクションを開いて完了します。  
    
    1.  パラメーターが `useWebview` に設定されているを確認します `true` 。  
    1.  パラメーターを追加 `urlFilter` します。  WebView2 コントロールが URL に移動すると、URL に表示される文字列を比較するためにパラメーター値 `urlFilter` が使用されます。  
        
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    アプリをデバッグするときに、レンダリング プロセスの最初からコードをステップ実行する必要がある場合があります。 サイトで Web ページをレンダリングし、ソース コードにアクセスできない場合は、認識されていないパラメーターは Web ページで無視されますので、このオプション `?=value`  を使用できます。   
    
    > [!IMPORTANT]
    > URL で最初の一致が見つかったら、デバッガーは停止します。  CDP ポートは、すべての WebView2 コントロールで共有され、1 つのポート番号を使用するので、2 つの WebView2 コントロールを同時にデバッグすることはできません。  
    
*   実行中のプロセスのデバッグ  
    
    実行中の WebView2 プロセスにデバッガーを接続する必要がある場合があります。 これを行うには、 `launch.json` にパラメーターを `request` 更新します `attach` 。
    
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
    
    WebView2 コントロールは、WebView2 コントロールのデバッグを許可するために CDP ポートを開く必要があります。  デバッガーを開始する前に、1 つの WebView2 コントロールだけが Chrome Developer Protocol (CDP) ポートを開いているか確認するために、コードをビルドする必要があります。  
    
*   デバッグ トレース オプション  
    
    デバッグ トレース `trace` を有効にするには、launch.jsにパラメーターを追加します。  
    
    1.  パラメーターを `trace` 追加します。  
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/trace-log.png" alt-text=" デバッグ出力をログ ファイルに保存します。" lightbox="./media/trace-log.png":::
                 デバッグ出力をログ ファイルに保存する  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細出力" lightbox="./media/verbose.png":::
                 Visual Studioトレースを有効にしたコード デバッグ出力  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   アドインOfficeデバッグします。  
    
    アドインをデバッグする場合Officeコードの別のインスタンスでアドイン ソース コードをVisual Studioします。  WebView2 launch.jsでアプリを開き、次のコード スニペットを追加して、デバッガーをアドインにOfficeします。
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   デバッガーのトラブルシューティング  
    
    デバッガーを使用すると、次のシナリオが発生する場合があります。  
    
    *   デバッガーはブレークポイントで停止しないし、デバッグ出力があります。  この問題を解決するには、ブレークポイントを持つファイルが WebView2 コントロールで使用されるファイルと同じことを確認します。  デバッガーはソース パスマッピングを実行しない。  
    *   実行中のプロセスに接続できないので、タイムアウト エラーが発生します。  この問題を解決するには、WebView2 コントロールが CDP ポートを開いているか確認します。  レジストリ内  `additionalBrowserArguments`  の値が正しいか、オプションが正しいか確認します。  詳細については [、「additionalBrowserArguments for dotnet」][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] および [「additionalBrowserArguments for Win32」に移動します][Webview2ReferenceWin32Webview2IdlParameters]。  
        
* * *  

## <a name="see-also"></a>関連項目  

*   WebView2 の使用を開始するには [、[WebView2 スタートガイド] に移動します][Webview2MainGetStarted]。  
*   WebView2 機能の包括的な例については [、GitHub の WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリに移動します。
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments プロパティ (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
