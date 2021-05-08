---
description: WebView2 ローダー ライブラリを静的にリンクする方法について説明します。
title: WebView2 ローダー ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 8f48a4fde9e2960de6156fc14db8c84f87a49868
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536031"
---
# <a name="statically-link-the-webview2-loader-library"></a>WebView2 ローダー ライブラリを静的にリンクする  

多くのファイルのパッケージではなく、1 つの実行可能ファイルでアプリケーションを配布できます。 単一の実行可能ファイルを作成したり、パッケージのサイズを小さくしたりするには、WebView2Loader ファイルを静的にリンクする必要があります。 WebView2 SDK には、ヘッダー ファイル、および `WebView2Loader.dll` ファイルが含 `IDL` まれています。 `WebView2Loader.dll` は、アプリがデバイス上の WebView2 ランタイム(または Microsoft Edge の安定しないチャネル)を見つけるのに役立つ小さなコンポーネントです。  

出荷しないアプリの場合は、 `WebView2Loader.dll` 次の手順を実行します。  

1.  アプリの `.vcxproj` プロジェクト ファイルをテキスト エディター (コードなど) でVisual Studioします。  
    
    > [!NOTE]
    > プロジェクト `.vcproj` ファイルは非表示のファイルである可能性があります。つまり、プロジェクト ファイルは非表示のファイルVisual Studio。  コマンド ラインを使用して、隠しファイルを検索します。  
    
1.  WebView2 NuGet パッケージ ターゲット ファイルを含めるコード内のセクションを探します。  コード内の場所は、次の図で強調表示されています。  
    
    :::image type="complex" source="./media/insert-here.png" alt-text="Project Files コード スニペット" lightbox="./media/insert-here.png":::
       Project Files コード スニペット   
    :::image-end:::  
    
1.  次のコード スニペットをコピーし、含まれる場所に `Microsoft.Web.WebView2.targets` 貼り付けます。  
    
    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```  
    
    :::image type="complex" source="./media/static-lib.png" alt-text="挿入されたコード スニペット" lightbox="./media/static-lib.png":::
       挿入されたコード スニペット  
    :::image-end:::  
    
1.  アプリのビルド構成の追加の依存関係を編集します。  まず、すべてのタグを検索 `<AdditionalDependencies>` します。 それぞれに対して、 `version.lib` ファイル内のすべての異なるビルド構成に追加の依存関係として追加 `.vcxproj` します。  
    
    :::image type="complex" source="./media/version-lib.png" alt-text="ItemDefinitionGroups への version.lib の追加" lightbox="./media/version-lib.png":::
       に追加 `version.lib` する `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > WebView2 チームは、今後のリリースで追加の依存関係の追加を自動化します。  
    
1.  アプリをコンパイルして実行します。  
    
## <a name="getting-in-touch-with-the-webview2-team"></a>WebView2 チームと連絡を取る  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

## <a name="see-also"></a>関連項目  

*   WebView2 の使用を開始するには [、[WebView2 スタートガイド] に移動します][Webview2MainGetStarted]。  
*   WebView2 機能の包括的な例については [、GitHub の WebView2Samples][GithubMicrosoftedgeWebview2samples] に移動します。
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。
    
<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- JavaScript デバッガー Visual Studioコード - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (クロム) WebView アプリケーション - Visual Studio コード - デバッガー for Microsoft Edge - microsoft/vscode-edge-debug2 |GitHub"  
