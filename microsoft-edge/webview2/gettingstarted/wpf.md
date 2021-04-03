---
description: WPF アプリ用 WebView2 の概要ガイド
title: WPF アプリ用 WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, wpf アプリ, wpf, edge, CoreWebView2, ブラウザー コントロール, edge html, 概要, 概要, .NET
ms.openlocfilehash: 14e6b64e36f6354554957d2c7953f789024d23c9
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470838"
---
# <a name="getting-started-with-webview2-in-wpf"></a>WPF での WebView2 の使用を開始する

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の API の詳細については、[API リファレンス][DotnetApiMicrosoftWebWebview2Wpf] に移動してください。  

## <a name="prerequisites"></a>前提条件  

先に進む前に、次の前提条件の一覧をインストールしてください。  

*   サポートされている OS \(現在は Windows 10、Windows 8.1、および Windows 7\ にインストールされている、[WebView2 ランタイム][Webview2Installer]または [Microsoft Edge (Chromium) 非安定チャネル][MicrosoftedgeinsiderDownload]。  
*   [Visual Studio][MicrosoftVisualstudioMain] 2017 以降。  
    
## <a name="step-1---create-a-single-window-app"></a>手順 1 - シングル ウィンドウ アプリを作成する  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  Visual Studio で, **WPF .NET Core App** \(または **WPF .NET Framework App**\) > **[次へ]** の順に選択します。  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF コア":::
             WPF コア :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF Framework":::
             WPF Framework :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  **[プロジェクト名]** と **[場所]** の値を入力します。  **.NET Framework 4.6.2**以降 \(または **.NET Core 3.0**以降\) を選択します。  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアを作成する":::
                 コアを作成する :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークを作成する":::
                 フレームワークを作成する :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  プロジェクトを作成するには、**[作成]** を 選択します。  
    
## <a name="step-2---install-webview2-sdk"></a>手順 2-WebView2 SDK をインストールする  

NuGet を使用して、WebView2 SDK をプロジェクトに追加します。  

1.  プロジェクトにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、**[NuGet パッケージの管理...]** を選択します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージの管理":::
       NuGet パッケージの管理
    :::image-end:::
    
1.  検索バーに `Microsoft.Web.WebView2` と入力し、**[microsoft.Web.WebView2]** を選択します。  
   
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       NuGet  
    :::image-end:::
    
    WebView2 API を使用してアプリの開発を開始する準備ができました。  プロジェクトをビルドして実行するには、`F5`を選択します。  実行中のプロジェクトに空のウィンドウが表示されます。  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空のアプリ" lightbox="./media/winforms-emptyapp.png":::
       空のアプリ  
    :::image-end:::  
    
## <a name="step-3---create-a-single-webview"></a>手順 3-1 つの WebView を作成する 

次に、WebView をアプリに追加します。  

1.  `MainWindow.xaml`ファイルで、WebView2 XAML 名前空間を追加するには、`<Window/>` タグ内に次の行を挿入します。  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    `MainWindow.xaml` コードが次のコード スニペットのように表示されます。  
    
    ```xml
    <Window x:Class="WPF_Getting_Started.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:{YOUR PROJECT NAME}"
            xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
            mc:Ignorable="d"
            Title="MainWindow"
            Height="450"
            Width="800"
    >
        <Grid>
        
        </Grid>
    </Window>
    ```  
    
1.  WebView2 コントロールを追加するには、タグを次の `<Grid>` コード スニペットに置き換えます。  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  プロジェクトをビルドして実行するには `F5` を選択して、WebView2 コントロールに [https://www.microsoft.com][|::ref1::|Main] が表示されていることを確認します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       Microsoft.com
    :::image-end:::  
    
## <a name="step-4---navigation"></a>手順 4 - ナビゲーション  

WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。

1.  `MainWindow.xaml` ファイル内で、`<DockPanel>` の　WebView を含む内部に次のコード スニペットをコピーして貼り付け、アドレス バーを追加します。  
    
    ```xml
    <DockPanel DockPanel.Dock="Top">
        <Button x:Name="ButtonGo"
                DockPanel.Dock="Right"
                Click="ButtonGo_Click"
                Content="Go"
        />
        <TextBox Name="addressBar"/>
    </DockPanel>
    ```  
    
    `MainWindow.xaml` ファイルの `<DockPanel>` セクションが次のコード スニペットと一致する必要があります。  
    
    ```xml
    <DockPanel>
        <DockPanel DockPanel.Dock="Top">
            <Button x:Name="ButtonGo" DockPanel.Dock="Right" Click="ButtonGo_Click" Content="Go"/>
            <TextBox Name = "addressBar"/>
        </DockPanel>
        <wv2:WebView2 Name = "webView"
                      Source = "https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  Visual Studio の `MainWindow.xaml.cs` ファイルで、`CoreWebView2` 名前空間を追加するには、次のコード スニペットを上部に挿入します。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  `MainWindow.xaml.cs` ファイルで、次のコード スニペットをコピーして `ButtonGo_Click` メソッドを作成します。このメソッドは、WebView をアドレス バーに入力された URL に移動します。  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    プロジェクトをビルドして実行するには、`F5`を選択します。  アドレス バーに新しい URL を入力し、**[移動]** を選択します。  たとえば、`https://www.bing.com` を入力します。  WebView2 コントロールが URL に移動することを確認します。  
    
    > [!NOTE]
    > アドレス バーに完全な URL が入力されている必要があります。  URL が `http://` または `https://` で始まらない場合、`ArgumentException` がスローされます。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
       bing.com
    :::image-end:::
    
## <a name="step-5---navigation-events"></a>手順 5 - ナビゲーション イベント  

Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。  WebView2 コントロールをホストするアプリは、次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

詳細については、[ナビゲーション イベント][Webview2ConceptsNavigationEvents]に移動してください。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   ナビゲーション イベント
:::image-end:::  

エラーが発生すると、次のイベントが発生し、エラー Web ページへのナビゲーションに依存する可能性があります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に複数の `NavigationStarting` イベントがあります。  

イベントの使い方を示す場合は、HTTPS 以外の要求をキャンセルする `NavigationStarting` のハンドラーを登録します。  

`MainWindow.xaml.cs` ファイルで、次のコード スニペットに一致するコンストラクターを変更し、`EnsureHttps` 関数を追加します。  

```csharp
public MainWindow()
{
    InitializeComponent();
    webView.NavigationStarting += EnsureHttps;
}

void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
}
```  

コンストラクターでは `EnsureHttps` 、WebView2 コントロール上のイベントの `NavigationStarting` イベント ハンドラーとして登録されます。  

プロジェクトをビルドして実行するには、`F5`を選択します。  HTTP サイトに移動する場合、WebView は変更されません。  ただし、WebView は HTTPS サイトに移動します。  

## <a name="step-6---scripting"></a>手順 6 - スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。  

たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。  [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync)メソッドを使用する Web コンテンツにスクリプトを挿入する `EnsureHttps` 関数を変更します。  

```csharp
void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        webView.CoreWebView2.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
}
```  

プロジェクトをビルドして実行するには、`F5`を選択します。  HTTPS を使用しない Web サイトに移動すると、アプリに警告が表示されます。  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   HTTPS
:::image-end:::  

## <a name="step-7---communication-between-host-and-web-content"></a>手順 7 - ホストコンテンツと Web コンテンツ間の通信  

ホストと Web コンテンツは、 を使用して次の方法で通信できます `postMessage` 。  

*   WebView2 コントロールの Web コンテンツは、`window.chrome.webview.postMessage` を使ってホストにメッセージを投稿できます。  ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。  
*   ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。  メッセージはに追加されたハンドラーによってキャッチされます `window.chrome.webview.addEventListener` 。  

通信メカニズムは、ネイティブ機能を使用して、Web コンテンツからホストにメッセージを渡します。  

プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。  

1.  `MainWindow.xaml.cs` ファイル内でコンストラクターを更新し、次のコードスニペットに一致する `InitializeAsync` 関数を作成します。  `CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) を待機します。  
    
    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }
    
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  
    
1.  **CoreWebView2** が初期化されたら、イベント ハンドラーを登録して `WebMessageReceived` に応答 します。  `MainWindow.xaml.cs` で `InitializeAsync` を更新して、次のコード スニペットを使用して、`UpdateAddressBar` を追加します。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
    }
    
    void UpdateAddressBar(object sender, CoreWebView2WebMessageReceivedEventArgs args)
    {
        String uri = args.TryGetWebMessageAsString();
        addressBar.Text = uri;
        webView.CoreWebView2.PostWebMessageAsString(uri);
    }
    ```  
    
1.  WebView が Web メッセージを送信して応答するために、`CoreWebView2` の初期化後にホストは次の処理を行います。  
    1.  ホストからメッセージを印刷するハンドラーを登録するスクリプトを Web コンテンツに挿入します。  
    1.  URL をホストに投稿するスクリプトを Web コンテンツに挿入します。  
        
    `MainWindow.xaml.cs` ファイル内で、次のコード スニペットに一致する `InitializeAsync` の更新を行います。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    アプリをビルドして実行するには、`F5` を選択します。  これで、アドレス バーに WebView2 コントロールの URI が表示されます。  新しい URI に正常に移動すると、WebView2 コントロールは WebView2 コントロールに表示される URI をユーザーに通知します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="addressBar":::
       addressBar
    :::image-end:::

これで、最初の WebView2 アプリがビルドされました。  

## <a name="next-steps"></a>次の手順  

WebView2 の詳細については、次のリソースを参照してください。  

### <a name="see-also"></a>関連項目  

*   WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samplesMain] に移動します。  
*   WebView2 API の詳細については、[API リファレンス](/dotnet/api/microsoft.web.webview2.wpf.webview2) に移動してください。  
*   WebView2 の詳細については、[WebView2 リソース](../index.md#next-steps) に移動してください。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  
 
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント | Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async(CoreWebView2Environment) メソッド | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド | Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 | Microsoft Edge 開発者"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualStudioMain]: https://visualstudio.microsoft.com "Microsoft Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
