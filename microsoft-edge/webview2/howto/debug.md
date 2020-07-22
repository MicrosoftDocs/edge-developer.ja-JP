---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 232104abc360cfa660d567ffb66535213fcb3ae0
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888582"
---
# WebView2 を使用してデバッグする方法  

Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。  次のページでは、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて、その概要を示します。  

## Microsoft Edge DevTools  

Microsoft edge [(Chromium) 開発者ツール][DevtoolsMain]を使用して、microsoft edge を使用している場合と同じように、WebView2 コントロールに表示される web コンテンツをデバッグします。  DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかの操作を実行します。  

*   を選択し `F12` ます。  
*   を選択し `Ctrl` + `Shift` + `I` ます。  
*   コンテキストメニューを開き (\ を右クリックし)、を選択し `Inspect` ます。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools" lightbox="../media/f12.png":::
   Microsoft Edge DevTools  
:::image-end:::  

> [!IMPORTANT]
> ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。  この `Ctrl` + `Shift` + `I` 問題を回避するには、コンテキストメニュー \ (右クリック \) を使用します。  

## Visual Studio  

Visual Studio を使って、アプリケーションコードを開発したり、スクリプトをデバッグしたりすることができます。  

次の点にご注意ください。  

*   Visual Studio では、アプリが Visual Studio 内から起動された場合にのみデバッグスクリプトをサポートします。  \ (デバッグの実行プロセスをアタッチすることはサポートされていません)。  
*   ターゲット WebView のデバッグシナリオはサポートされていません。  

Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。  

デバッガーを設定します。  

*   C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。  
    
    1.  Windows の [**アプリ & 機能**の設定] に移動します。  Windows タスクバーを使って検索します。  
    1.  [ **Modify**] を選びます。  
    1.  [ **C++** ] チェックボックスがオンになっていることを**確認します**。  
        
        :::image type="complex" source="../media/appsandfeatures.png" alt-text="アプリと機能" lightbox="../media/appsandfeatures.png":::
           アプリと機能  
        :::image-end:::  
        
*   WebView2 スクリプトのデバッグを有効にします。  
    1.  プロジェクトにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[**プロパティ**] を選びます。  
    1.  [**構成プロパティ**] で、[**デバッグ**] を選択します。  
    1.  [**デバッガーの種類**] プロパティで、オプションの一覧を検索し、[ **JavaScript (WebView2)**] を選びます。  
        
        :::image type="complex" source="../media/enbjs.png" alt-text="Visual Studio JavaScript デバッガー" lightbox="../media/enbjs.png":::
           Visual Studio JavaScript デバッガー  
        :::image-end:::  
        
<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

すべての設定が完了し、デバッグする準備ができました。  

デバッグするには、次の操作を実行します。  

1.  ブレークポイントを設定する  
    *   スクリプトファイルを開き、目的の場所にブレークポイントを設定します。  
        
        > [!NOTE]
        > JS/TS デバッグアダプターはソースパスマッピングを行っていません。WebView2 に関連付けられているのとまったく同じパスを開く必要があります。  
        
1.  コードを実行する  
    *   適切なビルドのフレーバーとランタイム環境を選び、ローカル windows デバッガーを起動します。  
1.  デバッグコンソールの表示  
    *   アプリケーションが実行され、最初の webview2 を作成した後でデバッガーが接続されます。保留中のデバッグ出力が表示されます。  
        
        > [!NOTE]
        > このデバッグ方法は、現在、Win32 アプリケーションと Office アドインに制限されています。  
        
## Visual Studio Code  

Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。  詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]」を参照してください。  

<!--todo:  add See also heading  -->  

## Microsoft Edge WebView チームと連絡を取り合う  

フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。  [フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]にアクセスして、機能リクエストまたはバグレポートを送信します。  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-VS コード-Microsoft Edge 用デバッガー |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
