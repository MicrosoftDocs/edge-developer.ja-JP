---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 4f94fe880f66f8aeb387d2db4a8bfaab20699466
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230699"
---
# WebView2 アプリケーションのデバッグを開始する  

Microsoft Edge WebView2 コントロールの目標は、Web とネイティブの両方のアプリケーション開発機能とツールを組み合わせることです。  WebView2 アプリケーションを開発する場合は、アプリケーションをデバッグする必要があります。  この記事では、WebView2 アプリケーションで Web とネイティブ コードの両方をデバッグするために使用するさまざまなツールの概要を説明します。  

## [Microsoft Edge DevTools](#tab/devtools)  

[Microsoft Edge (Chromium) 開発者][DevtoolsGuideChromiumMain]ツールを使用して、Microsoft Edge に表示される別の Web ページをデバッグするのと同じ方法で、WebView2 コントロールに表示される Web コンテンツをデバッグします。  DevTools を開く場合は、WebView コントロールにフォーカスを設定し、次のいずれかのアクションを使用します。  

*   `F12` を選択します。  
*   選択 `Ctrl` + `Shift` + `I` します。  
*   コンテキスト メニュー \(右クリック\) を開き、選択します `Inspect` 。  
    
詳しくは [、DevTools の概要に関するページをご覧ください][DevtoolsGuideChromiumMain]。  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   DevTools のデバッグ  
:::image-end:::  

## [Visual Studio](#tab/visualstudio)  

Visual Studioは、WebView2 アプリケーションで Web およびネイティブ コード用のさまざまなデバッグ ツールを提供します。  このセクションVisual Studio、主に WebView コントロールのデバッグに重点を置きますが、WebView コントロール内の他のデバッグ方法Visual Studio通常どおり使用できます。  Win32 アプリケーションで Web とネイティブ コードをデバッグしたり、アドインのみをOfficeするには、次のプロセスを使用します。  

> [!IMPORTANT]
> ネイティブ デバッガーがアタッチされた Visual Studio でアプリケーションをデバッグすると、選択すると、開発者ツールではなくネイティブ デバッガー `F12` がトリガーされる場合があります。  状況 `Ctrl` + `Shift` + `I` を回避するには、コンテキスト メニュー \(右クリック\) を選択するか、または使用します。  

開始する前に、次の要件を満たしていることを確認してください。  

*   スクリプトをデバッグするには、アプリをアプリ内から起動するVisual Studio。  
*   実行中の WebView2 プロセスにデバッガーをアタッチすることはできません。  
*   2019 Visual Studio 16.4 Preview 2 以降をインストールします。  
    
スクリプト デバッガー ツールをインストールしてセットアップVisual Studio。  

1.  C++ を使用したデスクトップ開発で **JavaScript 診断コンポーネント** をインストールするには、次 **の操作を実行します**。  
    
    1.  エクスプローラー バーに「.」と入力します `Visual Studio Installer` 。  
    1.  **[Visual Studioを選択して**開きます。  
    1.  新しいVisual Studioインストーラーのインストール済みバージョンで、[その他]**** ボタンを選択し、[変更] を**選択します**。  
    1.  [Visual Studioワークロード] で、[C++ でのデスクトップ開発]**設定を選択**します。 ****  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studioの変更画面" lightbox="./media/workloads.png":::
            Visual Studioの変更画面
        :::image-end:::  
        
    1.  個別の **コンポーネントを選択します**。  
    1.  検索ボックスに「.」と入力します `JavaScript diagnostics` 。  
    1.  **JavaScript 診断設定を選択**します。  
    1.  Choose **Modify**. 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studioの変更] タブ" lightbox="./media/indivcomp.png":::
           Visual Studioの変更] タブ  
        :::image-end:::  
        
1.  WebView2 アプリケーションのスクリプト デバッグを有効にする。  
    1.  WebView2 プロジェクトで、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を選択 **します**。  
    1.  [構成プロパティ **] で、[** デバッグ] **を選択します**。  
    1.  デバッガーの**種類で****、JavaScript (WebView2) を選択します**。  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studioデバッグ構成プロパティ" lightbox="./media/enbjs.png":::
           Visual Studio **デバッグ構成** プロパティ  
        :::image-end:::  
        
WebView2 アプリケーションをデバッグするには、次の操作を実行します。  

1.  ソース コードにブレークポイントを設定するには、行番号の左側にポイントし、ブレークポイントの設定を選択します。  JS/TS デバッグ アダプターはソース パス マッピングを実行します。  WebView2 に関連付けられているパスとまったく同じパスを開く必要があります。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studioブレークポイントを追加する" lightbox="./media/breakpoint.png"::: 
       Visual Studioブレークポイントを追加する  
    :::image-end:::  
    
1.  デバッガーを実行するには、プラットフォームのビット サイズを選択し、ローカル Windows デバッガーの横にある緑色の再生ボタン **を選択します**。  アプリケーションが実行され、デバッガーは作成された最初の WebView2 プロセスに接続します。  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio Windows デバッガーを使う" lightbox="./media/run.png"::: 
       Visual Studio Windows **デバッガーのインストール**  
    :::image-end:::  
    
1.  デバッグ コンソール **で、** デバッガーからの出力を見つける。  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio デバッグ コンソール" lightbox="./media/console.png"::: 
       Visual Studio **デバッグ コンソール**  
    :::image-end:::  
    
## [Visual Studio Code](#tab/visualstudiocode)  

Microsoft Visual Studio コードを使用して、WebView2 コントロールで実行されるスクリプトをデバッグします。  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

コードVisual Studio、次のアクションを実行してコードをデバッグします。 

1.  プロジェクトにはファイルが必要 `launch.json` です。  プロジェクトにファイルが存在しない場合は、次のコード スニペットをコピーして `launch.json` 、新しいファイルを作成 `launch.json` します。  
    
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",
        "env": {
            // Customize for your application location if needed
            "Path": "%path%;e:/path/to/your/application/location; "
        },
        "useWebView": true,
    ```  
    
1.  ソース コードにブレークポイントを設定するには、行にカーソルを合わせると、 `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="ブレークポイントがコードでVisual Studioされている" lightbox="./media/breakpointvs.png":::
       ブレークポイントがコードでVisual Studioされている  
    :::image-end:::
    
    > [!NOTE]
    > コードVisual Studioソース マッピングを実行しないので、WebView2 が使用するファイルと同じファイルにブレークポイントを設定してください。  パスが一致しない場合、Visual Studioコードは実行中のコードをブレークポイントで一時停止しません。  
    
1.  コードを実行します。  
    1.  [実行 **] タブ** で、ドロップダウン メニューから起動構成を選択します。  
    1.  アプリケーションのデバッグを開始するには、[デバッグの開始] を選択します。これは、起動構成ドロップダウンの横にある緑色の三角形です。  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studioコードの実行] タブ" lightbox="./media/runvs.png":::
           Visual Studioコードの実行] タブ  
        :::image-end:::  
        
1.  デバッグ **コンソールを開** き、デバッグ出力とエラーを表示します。  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio コード デバッグ コンソール" lightbox="./media/resultsvs.png":::
       Visual Studio コード デバッグ コンソール  
    :::image-end:::  
    
**詳細設定**:  

*   対象となる Web ビューのデバッグ。 
    
    一部の WebView2 アプリケーションでは、複数の WebView2 コントロールを使用できます。 この状況でデバッグする WebView2 コントロールを選択するには、ターゲット Webview2 デバッグを使用できます。 
    
    次 `launch.json` の操作を開いて完了し、対象の Webview デバッグを使用します。  
    
    1.  パラメーターが `useWebview` 次に設定されているのを確認します `true` 。  
    1.  パラメーターを追加 `urlFilter` します。  WebView2 コントロールが URL に移動すると、URL に表示される文字列を比較するためにパラメーター値 `urlFilter` が使用されます。  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    アプリケーションをデバッグするときに、レンダリング プロセスの最初からコードをステップ実行する必要がある場合があります。 サイトで Web ページをレンダリングする場合にソース コードにアクセスできない場合は、このオプションを使用できます。Web ページは認識できないパラメーターを `?=value`  無視します。   
    
    > [!IMPORTANT]
    > URL で最初の一致が見つかると、デバッガーは停止します。  CDP ポートは、すべての WebView2 コントロールで共有され、1 つのポート番号を使用するために、2 つの WebView2 コントロールを同時にデバッグすることはできません。  
    
*   実行中のプロセスをデバッグする  
    
    実行中の WebView2 プロセスにデバッガーをアタッチする必要がある場合があります。 これを行うには、in `launch.json` パラメーターを `request` 次の値に更新します `attach` 。
    
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
    
    WebView2 コントロールは、Cdp ポートを開き、WebView2 コントロールのデバッグを可能にする必要があります。  デバッガーを起動する前に、Chrome Developer Protocol (CDP) ポートを開いている WebView2 コントロールが 1 つだけ確保するために、コードをビルドする必要があります。  
    
*   デバッグ トレース オプション  
    
    デバッグ トレース `trace` を有効にするにはlaunch.jsパラメーターを追加します。  
    
    1.  パラメーターを `trace` 追加します。  
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" デバッグ出力をログ ファイルに保存します。" lightbox="./media/tracelog.png":::
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
    
    アドインをデバッグするOffice、アドイン ソース コードをアドイン コードの別のインスタンスVisual Studioします。  WebView2 launch.jsでアプリケーションを開き、次のコード スニペットを追加して、デバッガーをアドインにアタッチOfficeします。
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   デバッガーのトラブルシューティング  
    
    デバッガーを使用する場合、次のシナリオが発生する場合があります。  
    
    *   デバッガーはブレークポイントで停止しないので、デバッグ出力があります。  この問題を解決するには、ブレークポイントが設定されたファイルが、WebView2 コントロールで使用されているファイルと同じファイルである必要があります。  デバッガーはソース パスマッピングを実行します。  
    *   実行中のプロセスにアタッチできないので、タイムアウト エラーが発生します。  この問題を解決するには、WebView2 コントロールが CDP ポートを開いているのを確認します。  レジストリの  `additionalBrowserArguments`  値が正しいか、オプションが正しいか確認します。  詳細については [、dotnet 用の additionalBrowserArguments][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] と [Win32 用の additionalBrowserArguments を参照してください][Webview2ReferenceWin32Webview2IdlParameters]。  
    
* * *  

## 関連項目  

*   WebView2 の使用を開始するには [、WebView2 の開始ガイドを参照してください][Webview2MainGettingStarted]。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。
*   WebView2 API の詳細については、API リファレンスを [参照してください][Webview2ApiReference]。
*   WebView2 の詳細については [、「WebView2 リソース」を参照してください][Webview2MainNextSteps]。
    
## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments プロパティ (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- Visual Studio コードの JavaScript デバッガー - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション - Visual Studio コード - Microsoft Edge のデバッガー - microsoft/vscode-edge-debug2 |GitHub"  
