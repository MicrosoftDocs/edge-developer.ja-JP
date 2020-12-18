---
description: WebView2 ローダー ライブラリを静的にリンクする方法について説明します。
title: WebView2 ローダー ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 397c226eb958d1e656fb0ecb6dd8f1e2fe300746
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230930"
---
# WebView2 ローダー ライブラリを静的にリンクする  

多数のファイルのパッケージではなく、1 つの実行可能ファイルを使用してアプリケーションを配布できます。 単一の実行可能ファイルを作成したり、パッケージのサイズを小さくしたりするには、WebView2Loader ファイルを静的にリンクする必要があります。 WebView2 SDK には、ヘッダー ファイルと `WebView2Loader.dll` ファイルが含 `IDL` まれています。 `WebView2Loader.dll` は、アプリがデバイス上で Microsoft Edge の WebView2 ランタイム (または安定しないチャネル) を見つけるのに役立つ小さなコンポーネントです。  

出荷しないアプリの場合は、 `WebView2Loader.dll` 次の手順を実行します。  

1.  アプリの `.vcxproj` プロジェクト ファイルを、コードなどのテキスト エディターでVisual Studioします。  
    
    > [!NOTE]
    > プロジェクト `.vcproj` ファイルは非表示のファイルである可能性があります。つまり、プロジェクト ファイルはVisual Studio。  コマンド ラインを使用して隠しファイルを検索します。  
    
1.  WebView2 NuGet パッケージ ターゲット ファイルを含めるコード内のセクションを探します。  次の図では、コード内の場所が強調表示されています。  

    :::image type="complex" source="./media/inserthere.png" alt-text="Project ファイルのコード スニペット" lightbox="./media/inserthere.png":::
       Project ファイルのコード スニペット   
    :::image-end:::  
  
1.  次のコード スニペットをコピーし、含まれている場所に `Microsoft.Web.WebView2.targets` 貼り付けます。  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="挿入されたコード スニペット" lightbox="./media/staticlib.png":::
       挿入されたコード スニペット  
    :::image-end:::  
    
1.  アプリのビルド構成の追加の依存関係を編集します。  まず、すべてのタグを検索 `<AdditionalDependencies>` します。 それぞれに対して、ファイル `version.lib` 内のすべての異なるビルド構成に追加の依存関係を追加 `.vcxproj` します。  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="ItemDefinitionGroups への version.lib の追加" lightbox="./media/versionlib.png":::
       次の `version.lib` 追加 `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > WebView2 チームは、今後のリリースで追加の依存関係の追加を自動化する予定です。  
    
1. アプリをコンパイルして実行します。

### WebView2 チームと連絡を取る  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### 関連項目  

*   WebView2 の使用を開始するには [、WebView2 の開始ガイドに移動します][Webview2MainGettingStarted]。  
*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] に移動します。
*   WebView2 API の詳細については、API リファレンスに [移動してください][Webview2ApiReference]。
*   WebView2 の詳細については [、「WebView2 リソース」に移動してください][Webview2MainNextSteps]。

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- Visual Studio コードの JavaScript デバッガー - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション - Visual Studio コード - Microsoft Edge のデバッガー - microsoft/vscode-edge-debug2 |GitHub"  
