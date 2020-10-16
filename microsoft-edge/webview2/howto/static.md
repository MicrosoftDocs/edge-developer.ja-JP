---
description: WebView2 loader ライブラリを静的にリンクする方法について説明します。
title: WebView2 loader ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/15/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a25bd85c8a6b17bdf8712c954eb7b7cc28738eb2
ms.sourcegitcommit: 442de63da52d00c6dc27fa08ccdb736534127566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120074"
---
# WebView2 loader ライブラリを静的にリンクする方法  

## コンテキスト  

WebView2Loader.dll とは何ですか?  

*   WebView2 SDK には、ヘッダーファイルとファイルが含まれてい `WebView2Loader.dll.` `IDL` ます。 `WebView2Loader.dll` は、アプリがデバイス上の WebView2 Runtime (または非永続的な Microsoft Edge チャネル) を見つけるのに役立ちます。  

1つのランタイムを備えたアプリについては、次の手順を `WebView2Loader.dll` 実行し**Procedure**ます。  

## 手順  

1.  `.vcxproj`Visual Studio コードなどのテキストエディターでアプリのプロジェクトファイルを開きます。  
    
    > [!NOTE]
    > `.vcproj`プロジェクトファイルは非表示のファイルである可能性があります。これは Visual Studio では表示されません。  コマンドラインを使用して、非表示のファイルを検索します。  
    
1.  WebView2 NuGet パッケージターゲットファイルが含まれているコードのセクションを見つけます。  次の図では、コード内の場所が強調表示されています。  
    
    :::image type="complex" source="./media/inserthere.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/inserthere.png"::: 
       プロジェクトファイルのコードスニペット  
    :::image-end:::  
    
1.  次のコードスニペットをコピーして、が含まれている場所に貼り付け `Microsoft.Web.WebView2.targets` ます。  

    > [!NOTE]
    > たとえば、次のコードブロックの後に追加します。  
    > 
    > ```csharp
    > <Import Project="..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets" Condition="Exists('..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets')" />
    > ```  
    
    ```csharp
    <PropertyGroup> <WebView2LoaderPreference>Static</WebView2LoaderPreference> </PropertyGroup>
    ```
    
    :::image type="complex" source="./media/staticlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/staticlib.png"::: 
       挿入されたコードスニペット  
    :::image-end:::  
    
1.  アプリのビルド構成のその他の依存関係を編集します。  まず、すべてのタグを確認し `<AdditionalDependencies>` ます。  
1.  `version.lib`アプリのファイル内のすべてのビルド構成に、追加の依存関係として追加し `.vcxproj` ます。  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/versionlib.png"::: 
       追加 `version.lib` 先 `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > WebView2 チームは、今後のリリースで追加の依存関係の手順を自動化することを目的としています。  
    
アプリをコンパイルして展開します。  正しい.  

## 関連項目  

*   WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]に移動します。  
*   WebView2 機能の包括的な例については、GitHub on [WebView2Samples][GithubMicrosoftedgeWebview2samples] を参照してください。
*   WebView2 Api の詳細については、 [api リファレンス][Webview2ApiReference]に移動してください。
*   WebView2 の詳細については、 [WebView2 リソース][Webview2MainNextSteps]を参照してください。

## WebView2 チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能-Visual Studio コードの JavaScript デバッガー-microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-Visual Studio Code-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
