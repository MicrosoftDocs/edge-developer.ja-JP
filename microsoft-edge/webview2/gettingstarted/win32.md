---
description: Win32 アプリ用 WebView2 の使い始めガイド
title: WebView2 for Win32 アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 47f24b160797ce0ab7a7cb6a656c4f6b4e5696ac
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536609"
---
# <a name="getting-started-with-webview2"></a>WebView2 の使用を開始する  

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ReferenceWin32]。  

## <a name="prerequisites"></a>前提条件  

先に進む前に、次の前提条件の一覧をインストールしてください。  

*   サポートされている OS \(現在は Windows 10、Windows 8.1、および Windows 7\ にインストールされている、[WebView2 ランタイム][Webview2Installer]または [Microsoft Edge (Chromium) 非安定チャネル][MicrosoftedgeinsiderDownload]。  
    
    > [!NOTE]
    > WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] C++ サポートがインストールされている 2015 以降。  
    
## <a name="step-1---create-a-single-window-app"></a>手順 1 - シングル ウィンドウ アプリを作成する  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

> [!IMPORTANT]
> チュートリアルのフォーカスを向上するには、「チュートリアル Windows: 従来のデスクトップ アプリケーション[(C++)][CppWindowsWalkthroughCreatingDesktopApplication]を作成する」の変更されたサンプル コードを使用します。  変更したサンプルをダウンロードして開始するには [、[WebView2 サンプル] に移動します][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]。  

1.  [Visual Studio] を開きます `WebView2GettingStarted.sln` 。  
    以前のバージョンの Visual Studio を使用する場合は **、WebView2GettingStarted**プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を選択**します**。  [**構成プロパティ全般**  >  **]** で **、Windows SDK** **** バージョンとプラットフォーム ツールセットを変更して、使用できる Win10 SDK Visual Studioツールセットを使用します。  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールのバージョン" lightbox="../media/tool-version.png":::
   ツールのバージョン  
:::image-end:::  

Visual Studio WebView2 ヘッダー ファイルが存在しないので、エラーが表示される場合があります。  エラーは、手順 2 の後 [に修正する必要があります](#step-2---install-webview2-sdk)。  

## <a name="step-2---install-webview2-sdk"></a>手順 2-WebView2 SDK をインストールする  

WebView2 SDK をプロジェクトに追加します。  Win32 SDK NuGetインストールするには、次のコマンドを使用します。  

1.  プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[パッケージの管理] NuGet**します**。  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="NuGet パッケージの管理" lightbox="../media/manage-nuget-packages.png":::
       NuGet パッケージの管理  
    :::image-end:::  
    
1.  実装ライブラリWindowsインストールします。  
    1.  検索バーに `Microsoft.Windows.ImplementationLibrary` 「Microsoft.>」と入力**Windows。ImplementationLibrary**.  
    1.  右側のウィンドウで、[インストール] を **選択します**。  NuGetコンピューターにライブラリをダウンロードします。  
        
        > [!NOTE]
        > この[Windows実装ライブラリ][GithubMicrosoftWilMain]Windowsランタイム[C++ テンプレート][CppCxWrlTemplateLibraryVS2019]ライブラリはオプションであり、例では COM の操作を容易にします。  
        
        :::image type="complex" source="../media/wil.png" alt-text="Windows実装ライブラリ" lightbox="../media/wil.png":::
           Windows実装ライブラリ  
        :::image-end:::  
        
1.  WebView2 SDK をインストールします。  
    1.  検索バーに `Microsoft.Web.WebView2` と入力し、**[microsoft.Web.WebView2]** を選択します。  
    1.  右側のウィンドウで、[インストール] を **選択します**。  NuGet SDK をコンピューターにダウンロードします。  
        
        :::image type="complex" source="../media/nuget.png" alt-text="NuGet パッケージ マネージャー" lightbox="../media/nuget.png":::
           NuGet パッケージ マネージャー
        :::image-end:::  
        
1.  WebView2 ヘッダーをプロジェクトに追加します。  
    :::row:::
       :::column span="1":::
          ファイルで `HelloWebView.cpp` 、次のコード スニペットをコピーし、最後の行の後に貼り付 `#include` けます。  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          include セクションは、次のコード スニペットのようになります。  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
WebView2 API に対して使用してビルドする準備ができました。  

### <a name="build-your-empty-sample-app"></a>空のサンプル アプリをビルドする  

サンプル アプリをビルドして実行するには、 を選択します `F5` 。  アプリに空のウィンドウが表示されます。  

:::image type="complex" source="../media/empty-app.png" alt-text="空のアプリ" lightbox="../media/empty-app.png":::
   空のアプリ  
:::image-end:::  

## <a name="step-3---create-a-single-webview-within-the-parent-window"></a>手順 3 - 親ウィンドウ内に 1 つの WebView を作成する  

メイン ウィンドウに WebView を追加します。  

 このメソッド `CreateCoreWebView2Environment` を使用して、環境をセットアップし、コントロールMicrosoft Edge \(Chromium\) ブラウザーを探します。  既定の設定を使用する代わりに、ブラウザーの場所、ユーザー フォルダー、ブラウザー フラグを指定する場合にも、このメソッド `CreateCoreWebView2EnvironmentWithOptions` を使用できます。  メソッドが完了すると、コールバック内でメソッドを実行し、関連付けられた WebView を取得する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` `ICoreWebView2Controller::get_CoreWebView2` メソッドを実行します。  

コールバックで、もう少し設定を設定し、WebView のサイズを変更して親ウィンドウの 100% を占め、次のウィンドウBing。  

次のコード スニペットをコピーし、コメント `HelloWebView.cpp` の後とコメントの前 `// <-- WebView2 sample code starts here -->` に貼り付 `// <-- WebView2 sample code ends here -->` けます。  

```cpp
// Step 3 - Create a single WebView within the parent window
// Locate the browser and set up the environment for WebView
CreateCoreWebView2EnvironmentWithOptions(nullptr, nullptr, nullptr,
    Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
        [hWnd](HRESULT result, ICoreWebView2Environment* env) -> HRESULT {
        
            // Create a CoreWebView2Controller and get the associated CoreWebView2 whose parent is the main window hWnd
            env->CreateCoreWebView2Controller(hWnd, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                [hWnd](HRESULT result, ICoreWebView2Controller* controller) -> HRESULT {
                if (controller != nullptr) {
                    webviewController = controller;
                    webviewController->get_CoreWebView2(&webviewWindow);
                }
                
                // Add a few settings for the webview
                // The demo step is redundant since the values are the default settings
                ICoreWebView2Settings* Settings;
                webviewWindow->get_Settings(&Settings);
                Settings->put_IsScriptEnabled(TRUE);
                Settings->put_AreDefaultScriptDialogsEnabled(TRUE);
                Settings->put_IsWebMessageEnabled(TRUE);
                
                // Resize WebView to fit the bounds of the parent window
                RECT bounds;
                GetClientRect(hWnd, &bounds);
                webviewController->put_Bounds(bounds);
                
                // Schedule an async task to navigate to Bing
                webviewWindow->Navigate(L"https://www.bing.com/");
                
                // Step 4 - Navigation events
                
                // Step 5 - Scripting
                
                // Step 6 - Communication between host and web content
                
                return S_OK;
            }).Get());
        return S_OK;
    }).Get());
```  

### <a name="build-your-bing-sample-app"></a>サンプル アプリBing作成する  

アプリをビルドして実行するには、`F5` を選択します。  これで、WebView ウィンドウにページを表示Bingしました。  

:::image type="complex" source="../media/bing-window.png" alt-text="Bing ウィンドウ" lightbox="../media/bing-window.png":::
   Bing ウィンドウ  
:::image-end:::  

## <a name="step-4---navigation-events"></a>手順 4 - ナビゲーション イベント  

WebView チームは、最後の手順でメソッドを使用して URL への移動 `ICoreWebView2::Navigate` について既に説明しました。  ナビゲーション中に、WebView はホストがリッスンできる一連のイベントを発生します。  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

詳細については、「ナビゲーション イベント」 [に移動します][Webview2ConceptsNavigationEvents]。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント" lightbox="../media/navigation-events.png":::
   ナビゲーション イベント  
:::image-end:::  

エラーの場合、ナビゲーションがエラー Web ページに続いているかどうかに応じて、次の 1 つ以上のイベントが発生することがあります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に複数の `NavigationStarting` イベントがあります。  

イベントを使用する例として、イベントのハンドラーを登録して、https 以外の要求 `NavigationStarting` をキャンセルします。  次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。  

```cpp
// register an ICoreWebView2NavigationStartingEventHandler to cancel any non-https navigation
EventRegistrationToken token;
webviewWindow->add_NavigationStarting(Callback<ICoreWebView2NavigationStartingEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2NavigationStartingEventArgs * args) -> HRESULT {
        PWSTR uri;
        args->get_Uri(&uri);
        std::wstring source(uri);
        if (source.substr(0, 5) != L"https") {
            args->put_Cancel(true);
        }
        CoTaskMemFree(uri);
        return S_OK;
    }).Get(), &token);
```  

これで、アプリは https 以外のサイトには移動されません。  同様のメカニズムを使用して、独自のドメイン内へのナビゲーションの制限など、他のタスクを実行できます。  

## <a name="step-5---scripting"></a>手順 5 - スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。  

次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。  

```cpp
// Schedule an async task to add initialization script that freezes the Object object
webviewWindow->AddScriptToExecuteOnDocumentCreated(L"Object.freeze(Object);", nullptr);
// Schedule an async task to get the document URL
webviewWindow->ExecuteScript(L"window.document.URL;", Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
    [](HRESULT errorCode, LPCWSTR resultObjectAsJson) -> HRESULT {
        LPCWSTR URL = resultObjectAsJson;
        //doSomethingWithURL(URL);
        return S_OK;
    }).Get());
```  

これで、WebView は常にオブジェクトを `Object` フリーズし、ページ ドキュメントを 1 回返す必要があります。  

> [!NOTE] 
> スクリプトインジェクション API \(および他の WebView2 API\) は非同期です。コードを特定の順序で実行する必要がある場合は、コールバックを使用する必要があります。  

## <a name="step-6---communication-between-host-and-web-content"></a>手順 6 - ホストコンテンツと Web コンテンツ間の通信  

ホストと Web コンテンツは、メソッドを介して相互に通信 `postMessage` する場合があります。  WebView 内で実行されている Web コンテンツは、メソッドを介してホストに投稿され、メッセージはホストに登録されたイベント ハンドラー `window.chrome.webview.postMessage` `ICoreWebView2WebMessageReceivedEventHandler` によって処理されます。  同様に、ホストは、リスナーから追加されたハンドラーによってキャッチされる Web コンテンツまたはメソッドを通じて `ICoreWebView2::PostWebMessageAsString` `ICoreWebView2::PostWebMessageAsJSON` メッセージを送信 `window.chrome.webview.addEventListener` できます。  通信メカニズムにより、Web コンテンツはメッセージを渡してホストにネイティブ API の実行を求め、ネイティブ機能を使用できます。  

メカニズムを理解する例として、WebView でドキュメント URL を出力しようとするときに、次の手順が実行されます。  

1.  ホストは、受信したメッセージを Web コンテンツに戻すハンドラーを登録します。  
1.  ホストは、ホストからのメッセージを印刷するためのハンドラーを登録するスクリプトを Web コンテンツに挿入します。  
1.  ホストは、URL をホストに投稿する Web コンテンツにスクリプトを挿入します。  
1.  ホストのハンドラーがトリガーされ、メッセージ \(the URL\) を Web コンテンツに返します。  
1.  Web コンテンツのハンドラーがトリガーされ、ホスト \(the URL\) からメッセージが出力されます。  

次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。  

```cpp
// Set an event handler for the host to return received message back to the web content
webviewWindow->add_WebMessageReceived(Callback<ICoreWebView2WebMessageReceivedEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2WebMessageReceivedEventArgs * args) -> HRESULT {
        PWSTR message;
        args->TryGetWebMessageAsString(&message);
        // processMessage(&message);
        webview->PostWebMessageAsString(message);
        CoTaskMemFree(message);
        return S_OK;
    }).Get(), &token);

// Schedule an async task to add initialization script that
// 1) Add an listener to print message from the host
// 2) Post document URL to the host
webviewWindow->AddScriptToExecuteOnDocumentCreated(
    L"window.chrome.webview.addEventListener(\'message\', event => alert(event.data));" \
    L"window.chrome.webview.postMessage(window.document.URL);",
nullptr);
```  

### <a name="build-your-display-url-sample-app"></a>表示 URL サンプル アプリをビルドする  

アプリをビルドして実行するには、`F5` を選択します。  WEB ページに移動する前に、URL がポップアップ ウィンドウに表示されます。  

:::image type="complex" source="../media/show-url.png" alt-text="表示 URL" lightbox="../media/show-url.png":::
   表示 URL  
:::image-end:::  

これで、最初の WebView2 アプリがビルドされました。  

## <a name="next-steps"></a>次の手順  

この記事で説明されていない追加の WebView2 機能については、次のリソースを確認してください。  

*   WebView2 アプリケーションの構築の詳細については [、「WebView2 開発のベスト プラクティス」に移動します][WV2BestPractices]。  
*   WebView2 機能の包括的な例については [、「WebView2 API サンプル」に移動します][GithubMicrosoftedgeWebview2samplesApisample]。  
*   WebView2 を使用してビルドされたサンプル アプリの場合は [、WebView2Browser に移動します][GithubMicrosoftedgeWebview2browser]。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ReferenceWin32]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 の開発のベスト プラクティス|Microsoft Docs"  
[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 | Microsoft Edge 開発者"  

[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント | Microsoft Docs"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windowsランタイム C++ テンプレート ライブラリ (WRL) |Microsoft Docs"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "チュートリアル: 従来のデスクトップ Windows (C++) アプリケーションを作成|Microsoft Docs"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser - MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows実装ライブラリ (WIL) - microsoft/wil |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー"  
