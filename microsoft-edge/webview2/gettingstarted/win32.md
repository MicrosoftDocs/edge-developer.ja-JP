---
description: Win32 アプリ用 WebView2 の使用を開始するガイド
title: Win32 アプリ用 WebView2 の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 19bc0c5600ebd072ad9a6aa61d2a965e999865ce
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306160"
---
# WebView2 の使用を開始する  

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の WebView2 API の詳細については、API リファレンスに [移動してください][Webview2ReferenceWin32]。  

## 前提条件  

先に進む前に、前提条件の次の一覧をインストールしてください。  

*   サポートされている OS \(現在は Windows 10、Windows 8.1、Windows 7\) にインストールされている[、WebView2][Webview2Installer]ランタイムまたは[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]非安定チャネル。  
    
    > [!NOTE]
    > WebView チームでは、Canary チャネルの使用をお勧めします。必要な最小バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] C++ サポートがインストールされている 2015 以降。  
    
## 手順 1 - シングル ウィンドウ アプリを作成する  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

> [!IMPORTANT]
> チュートリアルに焦点を当てるには、「チュートリアル: サンプル アプリ用の従来の Windows デスクトップ アプリケーション [(C++)][CppWindowsWalkthroughCreatingDesktopApplication] を作成する」の変更されたサンプル コードを使用します。  変更したサンプルをダウンロードして開始するには [、WebView2 Samples に移動します][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]。  

1.  In Visual Studio, open `WebView2GettingStarted.sln` .  
    以前のバージョンの Visual Studio を使用している場合は **、WebView2GettingStarted** プロジェクトをポイントし、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を選択 **します**。  [**構成プロパティ全般**] で、Windows SDK バージョンとプラットフォーム ツールセットを変更して Win10 SDK を使用し、使用可能Visual Studioツールセット  >  **** を使用します。 **** ****  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールのバージョン" lightbox="../media/tool-version.png":::
   ツールのバージョン  
:::image-end:::  

Visual Studio WebView2 ヘッダー ファイルが存在しないので、エラーが表示される場合があります。  エラーは手順 2 の後 [で修正する必要があります](#step-2---install-webview2-sdk)。  

## 手順 2-WebView2 SDK をインストールする  

WebView2 SDK をプロジェクトに追加します。  NuGet を使用して Win32 SDK をインストールします。  

1.  プロジェクトにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[NuGet パッケージの管理 **] を選択します**。  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="NuGet パッケージの管理" lightbox="../media/manage-nuget-packages.png":::
       NuGet パッケージの管理  
    :::image-end:::  
    
1.  Windows 実装ライブラリをインストールします。  
    1.  検索バーに `Microsoft.Windows.ImplementationLibrary` **「microsoft.Windows.ImplementationLibrary >」と入力します**。  
    1.  右側のウィンドウで、[インストール] を選択 **します**。  NuGet は、ライブラリをコンピューターにダウンロードします。  
        
        > [!NOTE]
        > Windows [実装ライブラリと][GithubMicrosoftWilMain] [Windows ランタイム C++ テンプレート ライブラリ][CppCxWrlTemplateLibraryVS2019] はオプションであり、この例では COM を簡単に操作できます。  
        
        :::image type="complex" source="../media/wil.png" alt-text="Windows 実装ライブラリ" lightbox="../media/wil.png":::
           Windows 実装ライブラリ  
        :::image-end:::  
        
1.  WebView2 SDK をインストールします。  
    1.  検索バーに `Microsoft.Web.WebView2` **「microsoft.Web.WebView2 >」と入力します**。  
    1.  右側のウィンドウで、[インストール] を選択 **します**。  NuGet は SDK をコンピューターにダウンロードします。  
        
        :::image type="complex" source="../media/nuget.png" alt-text="NuGet パッケージ マネージャー" lightbox="../media/nuget.png":::
           NuGet パッケージ マネージャー
        :::image-end:::  
        
1.  WebView2 ヘッダーをプロジェクトに追加します。  
    :::row:::
       :::column span="1":::
          ファイル内 `HelloWebView.cpp` で、次のコード スニペットをコピーし、最後の行の後に貼り付 `#include` けます。  
          
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
    
WebView2 API に対して使用およびビルドする準備が整いました。  

### 空のサンプル アプリをビルドする  

サンプル アプリをビルドして実行するには、次を選択します `F5` 。  アプリに空のウィンドウが表示されます。  

:::image type="complex" source="../media/empty-app.png" alt-text="空のアプリ" lightbox="../media/empty-app.png":::
   空のアプリ  
:::image-end:::  

## 手順 3 - 親ウィンドウ内に 1 つの WebView を作成する  

WebView をメイン ウィンドウに追加します。  

 このメソッドを使用して、環境をセットアップし、コントロールの電源を入れた `CreateCoreWebView2Environment` Microsoft Edge \(Chromium\) ブラウザーを探します。  また、既定の設定を使用する代わりに、ブラウザーの場所、ユーザー フォルダー、ブラウザー フラグを指定する場合にも、このメソッド `CreateCoreWebView2EnvironmentWithOptions` を使用できます。  メソッドが完了すると、コールバック内でメソッドを実行し、メソッドを実行して関連付 `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` けられた `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` `ICoreWebView2Controller::get_CoreWebView2` WebView を取得します。  

コールバックで、さらにいくつかの設定を設定し、WebView のサイズを変更して親ウィンドウの 100% を占め、Bing に移動します。  

次のコード スニペットをコピーし、コメントの後 `HelloWebView.cpp` とコメントの `// <-- WebView2 sample code starts here -->` 前に貼り付 `// <-- WebView2 sample code ends here -->` けます。  

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

### Bing サンプル アプリをビルドする  

アプリをビルドして実行するには、次を選択します `F5` 。  これで、Bing ページを表示する WebView ウィンドウが表示されます。  

:::image type="complex" source="../media/bing-window.png" alt-text="Bing ウィンドウ" lightbox="../media/bing-window.png":::
   Bing ウィンドウ  
:::image-end:::  

## 手順 4 - ナビゲーション イベント  

WebView チームでは、前の手順のメソッドを使用した URL への `ICoreWebView2::Navigate` 移動について既に説明しました。  ナビゲーション中、WebView はホストがリッスンする可能性がある一連のイベントを発生します。  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

詳細については、ナビゲーション イベントに [移動します][Webview2ConceptsNavigationEvents]。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント" lightbox="../media/navigation-events.png":::
   ナビゲーション イベント  
:::image-end:::  

エラーの場合、ナビゲーションがエラー Web ページに続いているかどうかに応じて、次の 1 つ以上のイベントが発生することがあります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に `NavigationStarting` 複数のイベントがあります。  

イベントを使用する例として、https 以外の要求をキャンセル `NavigationStarting` するイベントのハンドラーを登録します。  次のコード スニペットをコピーし、貼り付けます `HelloWebView.cpp` 。  

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

これで、アプリは https 以外のサイトには移動しなくなっています。  ナビゲーションを独自のドメイン内に制限するなどの他のタスクを実行するには、同様のメカニズムを使用できます。  

## 手順 5 - スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行します。  

次のコード スニペットをコピーし、貼り付けます `HelloWebView.cpp` 。  

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

ここで、WebView は常にオブジェクトを `Object` 固定し、ページ ドキュメントを 1 回返す必要があります。  

> [!NOTE] 
> スクリプト インジェクション API \(および他の WebView2 API\) は非同期です。コードを特定の順序で実行する必要がある場合は、コールバックを使用する必要があります。  

## 手順 6 - ホストコンテンツと Web コンテンツ間の通信  

ホストと Web コンテンツは、メソッドを介して相互に通信 `postMessage` する場合があります。  WebView 内で実行されている Web コンテンツは、メソッドを介してホストに投稿できます。メッセージは、ホストに登録されているイベント ハンドラー `window.chrome.webview.postMessage` `ICoreWebView2WebMessageReceivedEventHandler` によって処理されます。  同様に、ホストは、リスナーから追加されたハンドラーによってキャッチされるメソッドを介して Web コンテンツ `ICoreWebView2::PostWebMessageAsString` `ICoreWebView2::PostWebMessageAsJSON` にメッセージを送信 `window.chrome.webview.addEventListener` できます。  通信メカニズムを使用すると、ホストにネイティブ API の実行を求めるメッセージを渡して、Web コンテンツでネイティブ機能を使用できます。  

メカニズムを理解するための例として、WebView でドキュメント URL を出力しようとするときに、次の手順が実行されます。  

1.  ホストは、受信したメッセージを Web コンテンツに返すハンドラーを登録します。  
1.  ホストは、ホストからメッセージを印刷するハンドラーを登録するスクリプトを Web コンテンツに挿入します。  
1.  ホストは、URL をホストに投稿するスクリプトを Web コンテンツに挿入します。  
1.  ホストのハンドラーがトリガーされ、メッセージ \(URL\) が Web コンテンツに返されます。  
1.  Web コンテンツのハンドラーがトリガーされ、ホスト \(URL\) からメッセージが出力されます。  

次のコード スニペットをコピーし、貼り付けます `HelloWebView.cpp` 。  

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

### 表示 URL サンプル アプリを作成する  

アプリをビルドして実行するには、次を選択します `F5` 。  WEB ページに移動する前に、URL がポップアップ ウィンドウに表示されます。  

:::image type="complex" source="../media/show-url.png" alt-text="表示 URL" lightbox="../media/show-url.png":::
   表示 URL  
:::image-end:::  

これで、最初の WebView2 アプリがビルドされました。  

## 次のステップ  

WebView2 の機能の多くは、この記事では説明していないので、次のセクションではさらに多くのリソースを提供します。  

### 関連項目  

*   WebView2 機能の包括的な例については [、WebView2 API サンプルに移動してください][GithubMicrosoftedgeWebview2samplesApisample]。  
*   WebView2 を使用してビルドされたサンプル アプリの場合は [、WebView2Browser に移動します][GithubMicrosoftedgeWebview2browser]。  
*   WebView2 API の詳細については、API リファレンスに [移動してください][Webview2ReferenceWin32]。  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 開発者"  

[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows ランタイム C++ テンプレート ライブラリ (WRL) |Microsoft Docs"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "Walkthrough: Create a traditional Windows Desktop application (C++) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser - MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 実装ライブラリ (WIL) - microsoft/wil |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー"  
