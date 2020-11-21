---
description: WebView2 for WPF アプリの概要ガイド
title: WebView2 for WPF アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、wpf アプリ、wpf、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: e928dae0aa63f15ca5fa21860c83fa5529e905df
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182375"
---
# WPF での WebView2 の概要

この記事では、初めての WebView2 アプリの作成を開始し、 [WebView2](../index.md)の主な機能について説明します。  個々の Api について詳しくは、 [api リファレンス](/dotnet/api/microsoft.web.webview2.wpf)をご覧ください。  

## 前提条件  

続行する前に、次の前提条件の一覧をインストールしていることを確認します。  

* [WebView2 Runtime][Webview2Installer] または windows 10、windows 8.1、または windows 7 にインストールされている [非安定した Microsoft Edge (Chromium) カナリアチャネル](https://www.microsoftedgeinsider.com/download) 。  
* [Visual Studio](https://visualstudio.microsoft.com) 2017 以降。  

## 手順 1-1 つのウィンドウアプリケーションを作成する  

1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。  

1.  **Visual Studio**を開きます。  
1.  [ **Wpf .Net Core app** ] または [ **wpf .Net Framework] アプリ**を選択し、[ **次へ**] を選択します。  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF core":::
             WPF core :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF フレームワーク":::
             WPF フレームワーク :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  **プロジェクト名**と**場所**の値を入力します。  .NET Framework 4.6.2 以降、または .NET Core 3.0 以降を選択します。  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアの作成":::
                 コアの作成 :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークの作成":::
                 フレームワークの作成 :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  プロジェクトを作成するには、[ **作成** ] を選択します。  
    
## 手順 2-WebView2 SDK をインストールする  

次に、NuGet を使ってプロジェクトに WebView2 SDK を追加します。  

1.  プロジェクトのコンテキストメニューを開き (\ [\] を右クリックし)、[ **NuGet パッケージの管理**] を選択します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       Nuget.exe
    :::image-end:::
    
1.  `Microsoft.Web.WebView2`検索バーに入力します。  検索結果から [ **WebView2** ] を選びます。  
   
     ![nuget.exe](./media/installnuget.PNG)
    
    WebView2 API を使ってアプリケーションの開発を開始する準備が整いました。  `F5`プロジェクトをビルドして実行する場合に選択します。  実行中のプロジェクトに空のウィンドウが表示されます。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空のアプリ":::
       空のアプリ
    :::image-end:::  
    
## 手順 3-MainWindow で1つの WebView を作成する  

次に、アプリケーションに WebView を追加します。  

1.  [開く] `MainWindow.xaml` を選びます。  タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    コードが `MainWindow.xaml` 次のコードスニペットのようになっていることを確認します。  
    
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
    
1.  次のコードスニペットを使って、タグを置き換えて WebView2 コントロールを追加し `<Grid>` ます。  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  を押して `F5` 、プロジェクトをビルドして実行します。  WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com](https://www.microsoft.com) します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       Microsoft.com
    :::image-end:::  
    
## ステップ 4-ナビゲーション  

WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレスバーをアプリに追加します。

1.  **MainWindow**で、WebView を含む DockPanel 内に次のコードスニペットをコピーして貼り付けて、アドレスバーを追加します。  
    
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
    
    次のコードスニペットのように、セクションが次のようになっていることを確認 `DockPanel` `MainWindow.xaml` します。  
    
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
    
1.  `MainWindow.xaml.cs`Visual Studio で開きます。  `CoreWebView2`次のコードスニペットを先頭に挿入して、名前空間を追加し `MainWindow.xaml.cs` ます。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  **MainWindow.xaml.cs**で、次のコードスニペットをコピーして、 `ButtonGo_Click` アドレスバーに入力された URL に WebView を移動するメソッドを作成します。  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    を押して `F5` 、プロジェクトをビルドして実行します。  アドレスバーに新しい URL を入力し **、[設定] を選択し**ます。  たとえば、と入力 `https://www.bing.com` します。  WebView2 コントロールが URL に移動することを確認します。  
    
    > [!NOTE]
    > アドレスバーに完全な URL が入力されていることを確認します。  `ArgumentException`URL がまたはで始まらない場合は、がスローされ `http://` `https://` ます。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
       Bing
    :::image-end:::
    
## ステップ 5-ナビゲーションイベント  

Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。 WebView2 コントロールをホストするアプリケーションは、次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

詳細については、「 [ナビゲーションイベント](../concepts/navigation-events.md)」を参照してください。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   ナビゲーションイベント
:::image-end:::  

エラーが発生した場合、次のイベントが発生し、エラーページへの移動に依存することがあります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

HTTP リダイレクトがある場合は、複数のイベントがあり `NavigationStarting` ます。  

これらのイベントの使い方を示すには、HTTPS を使って `NavigationStarting` いない要求をキャンセルするためのハンドラーを登録します。  

で `MainWindow.xaml.cs` 、次に示すようにコンストラクターを変更し、関数を追加し `EnsureHttps` ます。  

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

コンストラクターでは、EnsureHttps は、WebView2 コントロールのイベントのイベントハンドラーとして登録され `NavigationStarting` ます。  

を押して `F5` 、プロジェクトをビルドして実行します。  HTTP サイトに移動するときに、WebView の表示が **変わら**ないことを確認します。  ただし、WebView は HTTPS サイトに移動します。  

## ステップ 6-スクリプト  

ホストアプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベルドキュメントと任意の子フレームに適用されます。  挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれるスクリプトの前に実行されます。  

スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。  `EnsureHttps` [Executesの](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync)メソッドを使って、スクリプトが web コンテンツに挿入されるように関数を変更します。  

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

を押して `F5` 、プロジェクトをビルドして実行します。  HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   HTTPS
:::image-end:::  

## 手順 7-ホストと web コンテンツ間の通信  

ホストと web コンテンツは、次の方法で相互に通信でき `postMessage` ます。  

*   WebView2 コントロールの Web コンテンツは、を使ってホストにメッセージを投稿でき `window.chrome.webview.postMessage` ます。  ホストは、ホストに登録されているメッセージを処理し `WebMessageReceived` ます。  
*   ホストは、またはを使用して WebView2 コントロールの web コンテンツにメッセージを投稿し `CoreWebView2.PostWebMessageAsString` `CoreWebView2.PostWebMessageAsJSON` ます。  これらのメッセージは、ハンドラーが追加されることによって検出され `window.chrome.webview.addEventListener` ます。  

この通信メカニズムにより、web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。  

プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URL のユーザーに警告が表示されます。  

1.  **MainWindow.xaml.cs**で、 `InitializeAsync` 次のコードスニペットに示すように、コンストラクターを更新し、関数を作成します。  `InitializeAsync`の初期化は非同期であるため、この関数は[EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async)を待機し `CoreWebView2` ます。  
    
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
    
1.  **CoreWebView2**が初期化されたら、イベントハンドラーを登録して応答 `WebMessageReceived` します。  **MainWindow.xaml.cs**で、 `InitializeAsync` `UpdateAddressBar` 次のコードスニペットを使用して、更新して追加します。  
    
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
    
1.  WebView が web メッセージを送信して応答するためには、が初期化された後、次のようになり `CoreWebView2` ます。  
    
    1.  ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツに、スクリプトを挿入します。  
    1.  ホストに URL をポストする web コンテンツにスクリプトを挿入します。  
    
    では `MainWindow.xaml.cs` 、 `InitializeAsync` 次のように更新します。  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    を押して `F5` アプリをビルドして実行します。  これで、アドレスバーに WebView2 コントロールの URI が表示されます。 新しい URI に正常に移動すると、WebView2 コントロールは、WebView2 コントロールに表示される URI をユーザーに通知します。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="アドレスバー":::
       アドレスバー
    :::image-end:::

おめでとうございます。最初の WebView2 アプリを作成しました。  

## 次のステップ  

*   WebView2 機能の包括的な例については、「GitHub の [WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples) 」を参照してください。  
*   WebView2 Api について詳しくは、 [api リファレンス](/dotnet/api/microsoft.web.webview2.wpf.webview2)をご覧ください。  
*   WebView2 の詳細については、「 [WebView2 のリソース](../index.md#next-steps)」を参照してください。  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer" 
