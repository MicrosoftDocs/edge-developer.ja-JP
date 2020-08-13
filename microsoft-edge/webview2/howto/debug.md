---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/10/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6b2cc65e5cb368c29efec2eb3638f0c1772000d9
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926478"
---
# WebView2 を使用してデバッグする方法  

Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。  次のページでは、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて、その概要を示します。  

## Microsoft Edge DevTools  

Microsoft edge [(Chromium) 開発者ツール][DevtoolsGuideChromiumMain]を使用して、microsoft edge と同じ方法で、WebView2 コントロールに表示される web コンテンツをデバッグします。  DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかの操作を実行します。  
*   を選択し `F12` ます。  
*   を選択し `Ctrl` + `Shift` + `I` ます。  
*   コンテキストメニューを開く (\ 右クリック \) > 選択] をクリック `Inspect` します。  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools" lightbox="../media/f12.png":::
   Microsoft Edge DevTools  
:::image-end:::  

> [!NOTE]
> ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグするときに、を押すと、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされることがあります。  `Ctrl` + `Shift` + `I` または、コンテキストメニュー \ (右クリック \) を使用して、この問題を回避します。  

> [!NOTE]
> WebView を初めて `--auto-open-devtools-for-tabs` 作成するときに、コマンドライン引数を使って新しい DevTools ウィンドウを開くことができます。  <!--See `CreateCoreWebView2Controller` documentation for how to provide additional command-line arguments to the browser process.  See `LoaderOverride` registry key to examine different builds of WebView2 without modifying your application in the `CreateCoreWebView2Controller` documentation.  -->  

## Visual Studio  

Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。  C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 診断ツール":::
   Visual Studio JavaScript 診断ツール  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

WebView2 スクリプトのデバッグを有効にするには、プロジェクトのコンテキストメニュー \ (右クリック \) を開いて、[**プロパティ**] > 選びます。  

*   [**構成プロパティ**] で、[**デバッグ**] を選択します。  
*   [**デバッガーの種類**] プロパティで、オプションの一覧から [ **JavaScript (WebView2)** ] を選びます。 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript デバッガー":::
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

Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。  詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]」を参照してください。  

<!--todo:  add See also heading  -->  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!--## Debugging  

Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`. You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView. See CreateCoreWebView2Controller documentation for how to provide additional command line arguments to the browser process. Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateCoreWebView2Controller documentation.  -->  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-VS コード-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
