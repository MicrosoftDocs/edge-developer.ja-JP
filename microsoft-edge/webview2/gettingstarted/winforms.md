---
description: WebView2 for WinForms アプリの入門ガイド
title: WebView2 for WinForms アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, winforms アプリ, winforms, edge, CoreWebView2, ブラウザー管理, edge html, getting started, Getting Started, .NET, windows フォーム
ms.openlocfilehash: 45a3b59733a57975e373df2e21258198645be2d4
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306167"
---
# Windows フォームでの WebView2 の概要

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の API の詳細については、API リファレンスに [移動してください][DotnetApiMicrosoftWebWebview2Winforms]。  

## 前提条件  

先に進む前に、前提条件の次の一覧をインストールしてください。  

*   サポートされている OS \(現在は Windows 10、Windows 8.1、Windows 7\) にインストールされている[、WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]ランタイムまたは[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]非安定チャネル。  
    
    > [!NOTE]
    > WebView チームは Canary チャネルの使用をお勧めします。最小要件バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2017 以降。  
    
> [!NOTE]
> 現時点では、WebView2 は .NET 5 および .NET のコア デザイナーをサポートしていません。

## 手順 1 - シングル ウィンドウ アプリを作成する

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  In Visual Studio, choose **Windows Forms .NET Framework App**  >  **Next**.
    
    :::image type="complex" source="./media/winforms-newproject.png" alt-text="新しいプロジェクト" lightbox="./media/winforms-newproject.png":::
       新しいプロジェクト  
    :::image-end:::
    
1.  **プロジェクト名**と**場所**の値を入力します。  **.NET Framework 4.6.2 以降を**選択します。  
    
    :::image type="complex" source="./media/winforms-startproj.png" alt-text="プロジェクトを開始する" lightbox="./media/winforms-startproj.png":::
       プロジェクトを開始する  
    :::image-end:::
    
1.  プロジェクトを作成するには、[作成] を **選択します**。
    
## 手順 2-WebView2 SDK をインストールする

NuGet を使用して、WebView2 SDK をプロジェクトに追加します。  

1.  プロジェクトにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[NuGet パッケージの管理 **] を選択します**。  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       NuGet パッケージを管理する
    :::image-end:::
    
1.  検索バーに `Microsoft.Web.WebView2` **「microsoft.Web.WebView2 >」と入力します**。  
    
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       NuGet  
    :::image-end:::
    
    WebView2 API を使用してアプリの開発を開始します。  プロジェクトをビルドして実行するには、次を選択します `F5` 。  実行中のプロジェクトに空のウィンドウが表示されます。  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空のアプリ" lightbox="./media/winforms-emptyapp.png":::
       空のアプリ  
    :::image-end:::
    
## 手順 3-1 つの WebView を作成する  

WebView をアプリに追加します。  

1.  **Windows フォーム デザイナー**を開きます。  
1.  **ツールボックス**で**WebView2**を検索します。  
    
    > [!NOTE]
    > Visual Studio 2017 を使用している場合、既定では **、WebView2** がツールボックスに表示 **されない可能性があります**。  この動作を有効にするには、[**** ツール オプション全般] を選択し>自動的にツールボックスにデータを設定します  >  ****  >  ******** `True` 。  
    
    **WebView2**コントロールを Windows フォーム アプリにドラッグしてドロップします。
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       WebView2 が表示されたツールボックス
    :::image-end:::  

1.  プロパティを `(Name)` 次に設定します `webView` 。
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       WebView2 コントロールのプロパティ
    :::image-end:::

1.  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  プロパティを `Source` 次の値に設定します `https://www.microsoft.com` 。  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       **WebView2**コントロールの Source プロパティ
    :::image-end:::  

プロジェクトをビルドして実行するには、次を選択します `F5` 。  WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。

:::image type="complex" source="./media/winforms-hellowebview.png" alt-text="hello webview" lightbox="./media/winforms-hellowebview.png":::
   hello webview  
:::image-end:::  

> [!NOTE]
> 高 DPI モニターで作業している場合は、 [高 DPI サポートのために Windows フォーム アプリを構成][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]することが必要な場合があります。  

## 手順 4-ウィンドウのサイズ変更イベントを処理する

ツールボックスからさらにいくつかのコントロールを Windows フォームに追加し、ウィンドウのサイズ変更イベントを適切に処理します。

1.  **Windows フォーム デザイナー**で、**ツールボックス**を開きます。
1.  Windows Forms アプリ **に TextBox** をドラッグ アンド ドロップします。  [プロパティ **] タブで、** テキスト ボックスの名前 **を指定します** `addressBar` 。
1.  Windows フォーム アプリ **にボタンを** ドラッグ アンド ドロップします。  **ボタン**のテキストを `Go!` に変更して**プロパティ タブ**で、**ボタン** `goButton`に名前を指定します。

    このアプリは、デザイナー上で次の画像のように見えます。
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="デザイナー" lightbox="./media/winforms-designer.png":::
       デザイナー  
    :::image-end:::  

1.  ファイル内 `Form1.cs` で、アプリ ウィンドウのサイズが変更された場合にコントロール `Form_Resize` が配置された状態を維持する定義をします。

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

プロジェクトをビルドして実行するには、次を選択します `F5` 。  アプリが次のスクリーンショットと同様に表示されます。

:::image type="complex" source="./media/winforms-app.png" alt-text="アプリ" lightbox="./media/winforms-app.png":::
   アプリ  
:::image-end:::

## ステップ 5-ナビゲーション

WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。

1.  ファイル内 `Form1.cs` で名前空間を追加するには、次のコード スニペットを上部 `CoreWebView2` に挿入します。  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1.  Windows フォーム **デザイナーで、** ボタンをダブルクリックして、 `Go!` ファイル内に `goButton_Click` メソッドを作成 `Form1.cs` します。  関数内で次のスニペットをコピーして貼り付けます。  これで、この関数は、 `goButton_Click` アドレス バーに入力された URL に WebView を移動します。

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

プロジェクトをビルドして実行するには、次を選択します `F5` 。  アドレス バーに新しい URL を入力し [**実行**]を選択します。  たとえば、`https://www.bing.com` と入力します。  WebView2 コントロールが URL に移動します。  

> [!NOTE]
> アドレス バーに完全な URL が入力されていることを確認します。  URL が `http://` または以下で開始する場合は、`ArgumentException`がスローされます。 `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   bing.com  
:::image-end:::

## ステップ 6-ナビゲーション イベント  

Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。  WebView2 コントロールをホストするアプリは、次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

詳細については、ナビゲーション イベントに [移動します][Webview2ConceptsNavigationEvents]。  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   ナビゲーション イベント
:::image-end:::

エラーが発生すると、次のイベントが発生し、エラー Web ページへのナビゲーションに依存する可能性があります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に `NavigationStarting` 複数のイベントがあります。  

これらのイベントの使い方を示すには、HTTPS を使用しない要求をキャンセルするための `NavigationStarting` 用ハンドラーを登録します。  

ファイルで `Form1.cs` 、次のコード スニペットに一致するコンストラクターを更新し、関数を追加 `EnsureHttps` します。  

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

プロジェクトをビルドして実行するには、次を選択します `F5` 。  HTTP サイトに移動する場合、WebView は変更されません。  ただし、WebView は HTTPS サイトに移動します。

## 手順 7-スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行します。  

たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。  `EnsureHttps` [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]メソッドを使用する Web コンテンツにスクリプトを挿入する関数を変更します。  

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

プロジェクトをビルドして実行するには、次を選択します `F5` 。  HTTPS を使用しない Web サイトに移動すると、アプリに警告が表示されます。  

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   https  
:::image-end:::

## 手順 8-ホストと Web コンテンツ間の通信  

ホストコンテンツと Web コンテンツは、次のように相互 `postMessage` に通信するために使用できます。  

*   WebView2 コントロールの Web コンテンツは、ホストにメッセージを投稿 `window.chrome.webview.postMessage` するために使用できます。  ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。  
*   ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。  これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。  

通信メカニズムは、ネイティブ機能を使用して、Web コンテンツからホストにメッセージを渡します。  

プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。  

1.  ファイル内 `Form1.cs` でコンストラクターを更新し、次のコード `InitializeAsync` スニペットに一致する関数を作成します。  `CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] を待機します。  

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

1.  初期化 `CoreWebView2` された後、応答するイベント ハンドラーを登録します `WebMessageReceived` 。  ファイルで `Form1.cs` 、次の `InitializeAsync` コード スニペットを `UpdateAddressBar` 使用して更新して追加します。  

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

1.  WebView がWeb メッセージを送信して応答するためには、`CoreWebView2` が初期化された後、ホストが Web コンテンツにスクリプトを挿入します。  

    1.  そして、`postMessage` を使って、ホストに URL を送信し ます。
    1.  イベント ハンドラーを登録して、ホストから送信されたメッセージを出力します。  

ファイル内 `Form1.cs` で、次の `InitializeAsync` コード スニペットに一致する更新を行います。  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

アプリをビルドして実行するには、次を選択します `F5` 。  これで、アドレス バーに WebView2 コントロールの URI が表示されます。  また、新しい URL に正常に移動すると、WebView に表示された URL について、WebView はアラートをユーザーに通知します。  

:::image type="complex" source="./media/winforms-finalapp.png" alt-text="最終的なアプリ" lightbox="./media/winforms-finalapp.png":::
   最終的なアプリ  
:::image-end:::

これで、最初の WebView2 アプリがビルドされました。  

## 次のステップ  

WebView2 の詳細については、次のリソースを参照してください。  

### 関連項目  

*   WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   WebView2 の詳細については [、「WebView2 リソース」に移動してください][Webview2IndexNextSteps]。  
*   WebView2 API の詳細については、API リファレンスに [移動してください][DotnetApiMicrosoftWebWebview2WinformsWebview2]。  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async(CoreWebView2Environment) メソッド |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド |Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "高 DPI サポート向け Windows Forms アプリの構成 - Windows Forms | での高 DPI サポートMicrosoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 開発者"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  