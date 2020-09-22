---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/21/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 78c0fb982de8ccce71a8df2b59447b55f64fdc2f
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052154"
---
# WebView2 アプリケーションのデバッグを開始する  

Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの両方の開発機能とツールの両方を組み合わせることです。  WebView2 アプリケーションを開発するときは、アプリケーションをデバッグする必要があります。  この記事では、WebView2 アプリケーションで web とネイティブコードの両方をデバッグするために使用するさまざまなツールについて説明します。  

## [Microsoft Edge DevTools](#tab/devtools)  

Microsoft edge [(Chromium) 開発者ツール][DevtoolsGuideChromiumMain] を使用して、microsoft edge に表示されている別の web ページをデバッグする場合と同じ方法で、WebView2 コントロールに表示される web コンテンツをデバッグします。  DevTools を開くには、WebView コントロールにフォーカスを設定し、次のいずれかの操作を実行します。  

*   を選択し `F12` ます。  
*   を選択し `Ctrl` + `Shift` + `I` ます。  
*   コンテキストメニューを開き (\ を右クリックし)、[] を選び `Inspect` ます。  

詳細については、「 [Devtools の概要][DevtoolsGuideChromiumMain]」を参照してください。  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   DevTools のデバッグ  
:::image-end:::  

## [Visual Studio](#tab/visualstudio)  

Visual Studio には、WebView2 アプリケーションの web とネイティブコード向けのさまざまなデバッグツールが用意されています。  Visual Studio セクションでは、主にフォーカスが WebView コントロールのデバッグを行っていますが、Visual Studio でのデバッグ方法は通常どおり利用できます。  Win32 アプリケーションまたは Office アドインでのみ、web とネイティブコードをデバッグするには、次のプロセスを使用します。  

> [!IMPORTANT]
> ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。  `Ctrl` + `Shift` + `I` または、コンテキストメニュー \ (右クリック \) を使用して、この状況を回避します。  

作業を始める前に、次の要件が満たされていることを確認します。  

*   スクリプトをデバッグするには、Visual Studio 内からアプリを起動する必要があります。  
*   実行中の WebView2 プロセスにデバッガーをアタッチすることはできません。  
*   Visual Studio 2019 バージョン 16.4 Preview 2 以降をインストールします。  

Visual Studio でスクリプトデバッガーツールをインストールしてセットアップします。  

1.  **C++ でデスクトップ開発**に**JavaScript 診断**コンポーネントをインストールするには、次の操作を実行します。  

    1. Windows エクスプローラーバーに「」と入力 `Visual Studio Installer` します。  
    1. [ **Visual Studio インストーラー** ] を選択して開きます。  
    1. Visual Studio インストーラーのインストールされているバージョンで、[ **その他** ] ボタンを選択し、[ **変更**] を選択します。  
    1. Visual Studio の [ **ワークロード**] で、[ **デスクトップ開発** ] の [C++] の設定を選択します。  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio のワークロードの変更画面" lightbox="./media/workloads.png":::
            Visual Studio のワークロードの変更画面 :::image-end:::  
        
    1.  **個々のコンポーネント**を選択します。  
    1.  検索ボックスに「」と入力し `JavaScript diagnostics` ます。  
    1.  **JavaScript 診断**設定を選択します。  
    1.  [ **Modify**] を選びます。 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio による個々のコンポーネントの変更のタブ" lightbox="./media/indivcomp.png":::
           Visual Studio による個々のコンポーネントの変更のタブ  
        :::image-end:::  
        
1.  WebView2 アプリケーションのスクリプトのデバッグを有効にします。  
    1.  WebView2 プロジェクトで、コンテキストメニュー \ を右クリックし、[ **プロパティ**] を選びます。  
    1.  [ **構成プロパティ**] で、[ **デバッグ**] を選びます。  
    1.  [ **デバッガーの種類**] で、[ **JavaScript (WebView2)**] を選びます。  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio のデバッグ構成プロパティ" lightbox="./media/enbjs.png":::
           Visual Studio の **デバッグ** 構成プロパティ  
        :::image-end:::  
        
WebView2 アプリケーションをデバッグするには、次の操作を実行します。  

1.  ソースコードにブレークポイントを設定するには、行番号の左側にカーソルを置いて、[ブレークポイントの設定] を選択します。  JS/TS デバッグアダプターはソースパスマッピングを実行しません。  WebView2 に関連付けられているのとまったく同じパスを開く必要があります。  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio のブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       Visual Studio のブレークポイントの追加  
    :::image-end:::  
    
1.  デバッガーを実行するには、プラットフォームのビットサイズを選択し、[ **ローカル Windows デバッガー**] の横にある緑色の [再生] ボタンを選択します。  アプリケーションが実行され、作成された最初の WebView2 プロセスにデバッガーが接続されます。  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio のローカル Windows デバッガー" lightbox="./media/run.png"::: 
       Visual Studio の **ローカル Windows デバッガー**  
    :::image-end:::  
    
1.  **デバッグコンソール**でデバッガーからの出力を見つけます。  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio のデバッグコンソール" lightbox="./media/console.png"::: 
       Visual Studio の **デバッグコンソール**  
    :::image-end:::  
    
## [Visual Studio Code](#tab/visualstudiocode)  

Microsoft Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグします。  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

Visual Studio コードで、次の操作を実行してコードをデバッグします。 

1.  プロジェクトにファイルが必要です `launch.json` 。  プロジェクトにファイルが含まれていない場合は `launch.json` 、次のコードスニペットをコピーして、新しいファイルを作成し `launch.json` ます。  
        
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
        
1.  ソースコードにブレークポイントを設定するには、その行にカーソルを合わせて、 `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="Visual Studio コードでブレークポイントが設定されている" lightbox="./media/breakpointvs.png":::
       Visual Studio コードでブレークポイントが設定されている  
    :::image-end:::
    
    > [!NOTE]
    > Visual Studio コードではソースマッピングが実行されないため、WebView2 で使用するのと同じファイルにブレークポイントを設定してください。  パスが一致しない場合、Visual Studio コードはブレークポイントで実行中のコードを一時停止しません。  
    
1.  コードを実行します。  
    1.  [ **実行** ] タブで、ドロップダウンメニューから [起動構成] を選びます。  
    1.  アプリケーションのデバッグを開始するには、[デバッグの開始] を選びます。これは、[起動構成] ドロップダウンの隣にある緑色の三角形です。  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studio コードの [実行] タブ" lightbox="./media/runvs.png":::
           Visual Studio コードの [実行] タブ  
        :::image-end:::  
        
1.  デバッグ **コンソール** を開いて、デバッグ出力とエラーを表示します。  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio コードデバッグコンソール" lightbox="./media/resultsvs.png":::
       Visual Studio コードデバッグコンソール  
    :::image-end:::  
    
**詳細設定**:  

*   ターゲット Webview のデバッグ。 

    一部の WebView2 アプリケーションでは、複数の WebView2 コントロールを使うことができます。 この状況でデバッグする WebView2 コントロールを選ぶには、ターゲット指定された WebView2 デバッグを使用できます。 
    
    `launch.json`ターゲット Webview のデバッグを使用するには、次の操作を開いて実行します。  
    
    1.  パラメーターがに設定されていることを確認 `useWebview` `true` します。  
    1.  パラメーターを追加 `urlFilter` します。  WebView2 コントロールが URL に移動すると、 `urlFilter` パラメーター値が使用され、url に表示される文字列が比較されます。  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    アプリケーションをデバッグするときに、レンダリング処理の最初からコードをステップ実行しなければならない場合があります。 Web ページをサイトにレンダリングしていて、ソースコードにアクセスできない場合、web ページでは認識されないパラメーターが無視されるため、このオプションを使うことができ `?=value`  ます。   
    
    > [!IMPORTANT]
    > URL で最初の一致が見つかった後、デバッガーは停止します。  CDP ポートはすべての WebView2 コントロールで共有され、1つのポート番号を使用するため、2つの WebView2 コントロールを同時にデバッグすることはできません。  
    
*   実行中のプロセスをデバッグする  
    
    WebView2 プロセスを実行するためにデバッガーをアタッチすることが必要な場合があります。 そのためには、で `launch.json` `request` パラメーターをに更新 `attach` します。
        
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
        
    WebView2 コントロールは、WebView2 コントロールのデバッグを許可するために、CDP ポートを開く必要があります。  デバッガーを開始する前に、コードをビルドして、1つの WebView2 コントロールのみに Chrome (Chrome) ポートを開いていることを確認する必要があります。  
    
*   デバッグトレースオプション  
    
    `trace`launch.jsのパラメーターを追加して、デバッグトレースを有効にします。  
    
    1.  `trace`パラメーターを追加します。  
        
 
        
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
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" デバッグ出力をログファイルに保存します。" lightbox="./media/tracelog.png":::
                 ログファイルへのデバッグ出力の保存  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細な出力" lightbox="./media/verbose.png":::
                 冗長トレースが有効になっている Visual Studio コードデバッグの出力  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   Office アドインをデバッグします。
    
    Office アドインをデバッグする場合は、アドインのソースコードを Visual Studio コードの別のインスタンスで開きます。  WebView2 アプリケーションで launch.jsを開き、次のコードスニペットを追加して、デバッガーを Office アドインにアタッチします。
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   デバッガーのトラブルシューティング  
    
    デバッガーの使用時には、次のシナリオが発生する可能性があります。  

    *   デバッガーはブレークポイントで停止せず、デバッグ出力があります。  この問題を解決するには、ブレークポイントを設定したファイルが WebView2 コントロールで使用されているファイルと同じであることを確認します。  デバッガーはソースパスマッピングを実行しません。  
    *   実行中のプロセスにアタッチできないため、タイムアウトエラーが発生します。  この問題を解決するには、WebView2 コントロールが CDP ポートを開いていることを確認します。  レジストリの  `additionalBrowserArguments`  値が正しいこと、またはオプションが正しいことを確認します。  詳細については、「[.net] [Webview2ReferenceDotnet09515MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] と [additionalBrowserArguments for Win32] [Webview2ReferenceWin3209538Webview2IdlParameters]」を参照してください。  
    
* * *  


* * *  

## 関連項目  

*   WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]を参照してください。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。
*   WebView2 Api について詳しくは、 [api リファレンス][Webview2ApiReference]をご覧ください。
*   WebView2 の詳細については、「 [WebView2 のリソース][Webview2MainNextSteps]」を参照してください。

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515 クラス | WebView2 クラスの場合 |Microsoft ドキュメント"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft ドキュメント"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能-Visual Studio コードの JavaScript デバッガー-microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-Visual Studio Code-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
