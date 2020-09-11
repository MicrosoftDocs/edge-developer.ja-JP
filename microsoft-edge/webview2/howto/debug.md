---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/13/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 15171147b847b1d41cd603efed1b8ee42185dc29
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010699"
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

Visual Studio には、WebView2 アプリケーションの web とネイティブコード向けのさまざまなデバッグツールが用意されています。  Visual Studio のセクションでは、主に WebView コントロールのデバッグがフォーカスされますが、Visual Studio でのデバッグの他の方法は通常どおり利用できます。  Win32 アプリケーションまたは Office アドインでのみ、web とネイティブコードをデバッグするには、次のプロセスを使用します。  

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
