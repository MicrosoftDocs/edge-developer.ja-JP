---
description: WebView2 for WinForms アプリの入門ガイド
title: WebView2 for WinForms アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, winforms アプリ, winforms, edge, CoreWebView2, ブラウザー管理, edge html, getting started, Getting Started, .NET, windows フォーム
ms.openlocfilehash: f4768c38f293d1931e625136ea7068a61176541e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182389"
---
# Windows フォームでの WebView2 の概要

この記事では、[WebView2](/microsoft-edge/webview2/index)の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の API について詳しくは、「[API リファレンス](/dotnet/api/microsoft.web.webview2.winforms)」 をご覧ください。  

## 前提条件  

続行する前に、次の前提条件の一覧をインストールしていることを確認します。  

* [WebView2 Runtime][Webview2Installer] または Windows 10、Windows 8.1、または Windows 7 にインストールされている [非安定型 Microsoft Edge (Chromium) カナリア チャネル](https://www.microsoftedgeinsider.com/download)のいずれか 。 
* [Visual Studio](https://visualstudio.microsoft.com) 2017 以降。

> [!NOTE]
> 現時点では、WebView2 は .NET 5 および .NET のコア デザイナーをサポートしていません。

## 手順 1-1 つのウィンドウ アプリケーションを作成する

1 つのメイン ウィンドウを含む基本的なデスクトッププロジェクトから始めます。  

1. **Visual Studio **を開きます。

1. [**Windows Forms .Net Framework アプリ**] を選び、[**次へ**] を選びます。

    ![newproject](./media/winforms-newproject.png)

1. **プロジェクト名**と**場所**の値を入力します。  [**.Net Framework 4.6.2**] またはそれ以降を選択します。  

    ![startproject](./media/winforms-startproj.png)

1. プロジェクトを作成するには、[**作成**] を選びます。

## 手順 2-WebView2 SDK をインストールする

次に、NuGet を使ってプロジェクトに WebView2 SDK を追加します。

1. プロジェクトのコンテキスト メニューを開き \(右クリック\)、[ **NuGet パッケージ...の管理**] を選択します。  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       NuGet パッケージを管理する :::image-end:::

1. 検索バーに `Microsoft.Web.WebView2` を入力します。  検索結果から[**Microsoft.Web.WebView2**] を選びます。  

    ![nuget](./media/installnuget.png)

WebView2 API を使ってアプリケーションの開発を開始する準備が整いました。  `F5` を選択して、プロジェクトをビルドして実行します。  実行中のプロジェクトに空のウィンドウが表示されます。  

![emptyApp](./media/winforms-emptyApp.png)

## 手順 3-1 つの WebView を作成する  

次に、アプリケーションに WebView を追加します。  

1. **Windows フォーム デザイナー**を開きます。  
1. **ツールボックス**で**WebView2**を検索します。 **WebView2**コントロールを Windows フォーム アプリにドラッグしてドロップします。
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       WebView2 が表示されたツールボックス :::image-end:::  

1. `Name` プロパティを `webView` に変更します。
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       WebView2 コントロールのプロパティ :::image-end:::

1. この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。 Source プロパティを設定します。 <https://www.microsoft.com>
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       WebView2 コントロールの Source プロパティ :::image-end:::

`F5` を選択して、プロジェクトをビルドして実行します。  WebView2 コントロールが表示されていることを確認します[https://www.microsoft.com](https://www.microsoft.com)。

![hellowebview](./media/winforms-hellowebview.png)

> [!NOTE]
> 高 DPI モニターで作業している場合は、 [高 DPI サポートのために Windows フォーム アプリを構成](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)することが必要な場合があります。

## 手順 4-ウィンドウのサイズ変更イベントを処理する

ツールボックスからさらにいくつかのコントロールを Windows フォームに追加し、ウィンドウのサイズ変更イベントを適切に処理します。

1. **Windows フォーム デザイナー**で、**ツールボックス**を開きます。
1. **TextBox**を Windows フォーム アプリにドラッグ アンド ドロップします。 **プロパティ タブ**で、**TextBox** `addressBar`に名前を指定します。
1. **ボタン**を、Windows フォーム アプリにドラッグアンド ドロップします。 **ボタン**のテキストを `Go!` に変更して**プロパティ タブ**で、**ボタン** `goButton`に名前を指定します。

    このアプリは、デザイナー上で次の画像のように見えます。
    
    ![デザイナー](./media/winforms-designer.png)

1. **Form1.cs**で、アプリのウィンドウのサイズが変更されたときに、`Form_Resize` を定義してコントロールを配置したままにします。

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

`F5` を選択して、プロジェクトをビルドして実行します。  アプリが次のスクリーンショットのように表示されることを確認します。

![アプリ](./media/winforms-app.png)

## ステップ 5-ナビゲーション

WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。

1. `Form1.cs` で `CoreWebView2` namespace を追加するには、`Form1.cs` の先頭に、次のコード スニペットを挿入します。  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1. **Windows Forms Designer**で、`Go!` ボタンをダブルクリックして `Form1.cs` に `goButton_Click` メソッドを作成 します。 関数内で次のスニペットをコピーして貼り付けます。 これで、この関数は、 `goButton_Click` アドレス バーに入力された URL に WebView を移動します。

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

`F5` を選択して、プロジェクトをビルドして実行します。  アドレス バーに新しい URL を入力し [**実行**]を選択します。  たとえば、`https://www.bing.com` と入力します。  WebView2 コントロールが URL に移動することを確認します。  

> [!NOTE]
> アドレス バーに完全な URL が入力されていることを確認します。 URL が `http://` または以下で開始する場合は、`ArgumentException`がスローされます。 `https://`

![bing.](./media/winforms-bing.png)

## ステップ 6-ナビゲーション イベント  

Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。 WebView2 コントロールをホストするアプリケーションは、次のイベントをリッスンします。  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

詳細については、「[ナビゲーション イベント](../concepts/navigation-events.md)」を参照してください。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   ナビゲーション イベント
:::image-end:::

エラーが発生した場合、次のイベントが発生し、エラー ページへ移動することがあります。  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

HTTP リダイレクトがある場合は、複数の`NavigationStarting`イベントがあり ます。  

これらのイベントの使い方を示すには、HTTPS を使用しない要求をキャンセルするための `NavigationStarting` 用ハンドラーを登録します。  

`Form1.cs` で、次に示すようにコンストラクターを変更し、 `EnsureHttps` 関数を追加します。  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

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

コンストラクターでは、EnsureHttps が、WebView2 コントロールの`NavigationStarting` イベントのイベント ハンドラーとして登録されています。  

`F5` を選択して、プロジェクトをビルドして実行します。 HTTP サイトに移動するときに、WebView が変化しないことを確認します。 ただし、WebView は HTTPS サイトに移動します。

## 手順 7-スクリプト  

ホスト アプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベル ドキュメントと任意の子フレームに適用されます。  挿入された JavaScript は、グローバル オブジェクトの作成の後、および HTML ドキュメントに含まれるスクリプトの前に実行されます。  

スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。  [ExecuteScriptAsync]()メソッドを使って、スクリプトがWeb コンテンツに挿入されるように `EnsureHttps` 関数を変更します。  

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

`F5` を選択して、プロジェクトをビルドして実行します。  HTTPS を使用していないサイトにユーザーが移動したときに、アプリケーションにアラートが表示されることを確認します。  

![https](./media/winforms-https.png)

## 手順 8-ホストと Web コンテンツ間の通信  

ホストと Web コンテンツは、`postMessage` を使用して次の方法で相互に通信でき ます。  

* WebView2 コントロールの Web コンテンツは、`window.chrome.webview.postMessage` を使ってホストにメッセージを投稿できます。  ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。  
* ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。  これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。  

この通信メカニズムにより、Web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。  

プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。  

1. **Form1.cs**で、 次のコード スニペットに示すように、コンストラクターを更新し、`InitializeAsync` 関数を作成します。  `CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async]() を待機します。  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

1. **CoreWebView2** が初期化されたら、イベント ハンドラーを登録して `WebMessageReceived` に応答 します。  `Form1.cs` で `InitializeAsync` を更新して、次のコード スニペットを使用して、`UpdateAddressBar` を追加します。  

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

1. WebView がWeb メッセージを送信して応答するためには、`CoreWebView2` が初期化された後、ホストが Web コンテンツにスクリプトを挿入します。  

    1. そして、`postMessage` を使って、ホストに URL を送信し ます。
    1. イベント ハンドラーを登録して、ホストから送信されたメッセージを出力します。  

次のコード スニペットに示すように、`Form1.cs` で `InitializeAsync` を更新します。  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

`F5` を選択して、アプリをビルドして実行します。  アドレス バーに、WebView に表示されているサイトの URL が表示されていることを確認します。 また、新しい URL に正常に移動すると、WebView に表示された URL について、WebView はアラートをユーザーに通知します。  

![finalapp](./media/winforms-finalapp.png)

おめでとうございます。最初の WebView2 アプリを作成しました。  

## 次のステップ 

WebView2 の詳細については、次のリソースを参照してください。

* [WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples)には、WebView2's 機能の包括的な例があります。
* [API リファレンス](/dotnet/api/microsoft.web.webview2.winforms.webview2) API の詳細については、こちらを参照してください。
* [WebView2 リソース](../index.md#next-steps)。


## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
