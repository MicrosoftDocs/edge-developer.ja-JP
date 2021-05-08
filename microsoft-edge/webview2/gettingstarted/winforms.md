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
ms.openlocfilehash: 408d225c6c0abe54483226e7004a386d367d65ab
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536551"
---
# <a name="getting-started-with-webview2-in-windows-forms"></a>Windows フォームでの WebView2 の概要

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  個々の API の詳細については、[API リファレンス][DotnetApiMicrosoftWebWebview2Winforms] に移動してください。  

## <a name="prerequisites"></a>前提条件  

先に進む前に、次の前提条件の一覧をインストールしてください。  

*   サポートされている OS \(現在は Windows 10、Windows 8.1、および Windows 7\ にインストールされている、[WebView2 ランタイム][MicrosoftDeveloperMicrosoftEdgeWebview2]または [Microsoft Edge (Chromium) 非安定チャネル][MicrosoftedgeinsiderDownload]。  
    
    > [!NOTE]
    > WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2017 以降。  
    
> [!NOTE]
> 現時点では、WebView2 は .NET 5 および .NET のコア デザイナーをサポートしていません。  

## <a name="step-1---create-a-single-window-app"></a>手順 1 - シングル ウィンドウ アプリを作成する

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  [Visual Studio] で、[フォーム **] Windows [.NET Framework] を**  >  **選択します**。
    
    :::image type="complex" source="./media/winforms-newproject.png" alt-text="新しいプロジェクト" lightbox="./media/winforms-newproject.png":::
       新しいプロジェクト  
    :::image-end:::
    
1.  **[プロジェクト名]** と **[場所]** の値を入力します。  [.NET Framework **4.6.2 以降] を**選択します。  
    
    :::image type="complex" source="./media/winforms-startproj.png" alt-text="プロジェクトの開始" lightbox="./media/winforms-startproj.png":::
       プロジェクトの開始  
    :::image-end:::
    
1.  プロジェクトを作成するには、**[作成]** を 選択します。
    
## <a name="step-2---install-webview2-sdk"></a>手順 2-WebView2 SDK をインストールする

NuGet を使用して、WebView2 SDK をプロジェクトに追加します。  

1.  プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[パッケージの管理] をNuGet**します。。**  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       NuGet パッケージを管理する
    :::image-end:::
    
1.  検索バーに `Microsoft.Web.WebView2` と入力し、**[microsoft.Web.WebView2]** を選択します。  
    
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       NuGet  
    :::image-end:::
    
    WebView2 API を使用してアプリの開発を開始します。  プロジェクトをビルドして実行するには、`F5`を選択します。  実行中のプロジェクトに空のウィンドウが表示されます。  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空のアプリ" lightbox="./media/winforms-emptyapp.png":::
       空のアプリ  
    :::image-end:::
    
## <a name="step-3---create-a-single-webview"></a>手順 3-1 つの WebView を作成する  

アプリに WebView を追加します。  

1.  **Windows フォーム デザイナー**を開きます。  
1.  **ツールボックス**で**WebView2**を検索します。  
    
    > [!NOTE]
    > 2017 年 2017 Visual Studio使用している場合、既定では**WebView2**がツールボックスに表示**されない場合があります**。  動作を有効にするには、[ツール**オプション全般**] を選択>ツールボックスの自動設定  >  ****  >  ******設定**をに設定します `True` 。  
    
    **WebView2**コントロールを Windows フォーム アプリにドラッグしてドロップします。
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       WebView2 が表示されたツールボックス  
    :::image-end:::  

1.  プロパティを `(Name)` に設定します `webView` 。
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       WebView2 コントロールのプロパティ
    :::image-end:::

1.  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  プロパティを `Source` に設定します `https://www.microsoft.com` 。  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       **WebView2**コントロールの Source プロパティ
    :::image-end:::  

プロジェクトをビルドして実行するには、 を選択します `F5` 。  WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。

:::image type="complex" source="./media/winforms-hellowebview.png" alt-text="hello webview" lightbox="./media/winforms-hellowebview.png":::
   hello webview  
:::image-end:::  

> [!NOTE]
> 高 DPI モニターで作業している場合は、 [高 DPI サポートのために Windows フォーム アプリを構成][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]することが必要な場合があります。  

## <a name="step-4---handle-window-resize-events"></a>手順 4-ウィンドウのサイズ変更イベントを処理する  

ツールボックスからさらにいくつかのコントロールを Windows フォームに追加し、ウィンドウのサイズ変更イベントを適切に処理します。  

1.  [フォーム**デザイナー Windowsツールボックス**] を**開きます**。  
1.  **TextBox**を Windows フォーム アプリにドラッグ アンド ドロップします。  **プロパティ タブ**で、**TextBox** `addressBar`に名前を指定します。  
1.  **ボタン**を、Windows フォーム アプリにドラッグアンド ドロップします。  **ボタン**のテキストを `Go!` に変更して**プロパティ タブ**で、**ボタン** `goButton`に名前を指定します。  
    
    このアプリは、デザイナー上で次の画像のように見えます。  
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="WinForms デザイナー" lightbox="./media/winforms-designer.png":::
       WinForms デザイナー  
    :::image-end:::  

1.  ファイル内 `Form1.cs` で、App Window のサイズを変更するときに `Form_Resize` コントロールを保持する定義を行います。

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

プロジェクトをビルドして実行するには、 を選択します `F5` 。  アプリが次のスクリーンショットと同様に表示されるのを確認します。

:::image type="complex" source="./media/winforms-app.png" alt-text="アプリ" lightbox="./media/winforms-app.png":::
   アプリ  
:::image-end:::

## <a name="step-5---navigation"></a>ステップ 5-ナビゲーション

WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。  

1.  `F5` を選択して、プロジェクトをビルドして実行します。  アプリが次のスクリーンショットのように表示されることを確認します。  
    
    :::image type="complex" source="./media/winforms-app.png" alt-text="WinForms アプリ" lightbox="./media/winforms-app.png":::
       WinForms アプリ  
    :::image-end:::  
    
1.  ファイルに `Form1.cs` 名前空間を追加するには `CoreWebView2` 、次のコード スニペットを上部に挿入します。  

1.  `Form1.cs` で `CoreWebView2` namespace を追加するには、`Form1.cs` の先頭に、次のコード スニペットを挿入します。  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1.  [フォーム**Windowsで**、ボタンをダブルクリックして、 `Go!` ファイルに `goButton_Click` メソッドを作成 `Form1.cs` します。  関数内で次のスニペットをコピーして貼り付けます。  これで、この関数は、 `goButton_Click` アドレス バーに入力された URL に WebView を移動します。

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

プロジェクトをビルドして実行するには、 を選択します `F5` 。  アドレス バーに新しい URL を入力し [**実行**]を選択します。  たとえば、`https://www.bing.com` と入力します。  WebView2 コントロールが URL に移動することを確認します。  

> [!NOTE]
> アドレス バーに完全な URL が入力されていることを確認します。  URL が `http://` または以下で開始する場合は、`ArgumentException`がスローされます。 `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   bing.com  
:::image-end:::

## <a name="step-6---navigation-events"></a>ステップ 6-ナビゲーション イベント  

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

イベントを使用する方法を示す場合は、まず、HTTPS を使用しない要求をキャンセルするハンドラーを登録 `NavigationStarting` します。  

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

コンストラクターでは `EnsureHttps` 、WebView2 コントロール上のイベントの `NavigationStarting` イベント ハンドラーとして登録されます。  

プロジェクトをビルドして実行するには、 を選択します `F5` 。  HTTP サイトに移動する場合、WebView は変更されません。  ただし、WebView は HTTPS サイトに移動します。

## <a name="step-7---scripting"></a>手順 7-スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。  

たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。  [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]メソッドを使用する Web コンテンツにスクリプトを挿入する `EnsureHttps` 関数を変更します。  

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

プロジェクトをビルドして実行するには、 を選択します `F5` 。  HTTPS を使用しない Web サイトに移動すると、アプリに警告が表示されます。  

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   https  
:::image-end:::

## <a name="step-8---communication-between-host-and-web-content"></a>手順 8-ホストと Web コンテンツ間の通信  

ホストと Web コンテンツは、次のように相互 `postMessage` に通信するために使用できます。  

*   WebView2 コントロールの Web コンテンツは、ホスト `window.chrome.webview.postMessage` にメッセージを投稿するために使用できます。  ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。  
*   ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。  これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。  

通信メカニズムは、ネイティブ機能を使用して、Web コンテンツからホストにメッセージを渡します。  

プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。  

1.  `Form1.cs` ファイル内でコンストラクターを更新し、次のコードスニペットに一致する `InitializeAsync` 関数を作成します。  `CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] を待機します。  

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

1.  初期化 `CoreWebView2` 後、に応答するイベント ハンドラーを登録します `WebMessageReceived` 。  ファイルで `Form1.cs` 、次のコード `InitializeAsync` スニペット `UpdateAddressBar` を使用して更新して追加します。  

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

`Form1.cs` ファイル内で、次のコード スニペットに一致する `InitializeAsync` の更新を行います。  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

アプリをビルドして実行するには、`F5` を選択します。  これで、アドレス バーに WebView2 コントロールの URI が表示されます。  また、新しい URL に正常に移動すると、WebView に表示された URL について、WebView はアラートをユーザーに通知します。  

:::image type="complex" source="./media/winforms-finalapp.png" alt-text="最終アプリ" lightbox="./media/winforms-finalapp.png":::
   最終アプリ  
:::image-end:::

これで、最初の WebView2 アプリがビルドされました。  

## <a name="next-steps"></a>次の手順  

WebView2 の詳細については、次のリソースを参照してください。  

*   WebView2 アプリケーションの構築の詳細については [、「WebView2 開発のベスト プラクティス」に移動します][WV2BestPractices]。  
*   WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WinformsWebview2]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 の開発のベスト プラクティス|Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント | Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async(CoreWebView2Environment) メソッド | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド | Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "高 DPI サポート用Windowsフォーム アプリの構成 - 高 DPI サポートは、Windows フォーム |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 | Microsoft Edge 開発者"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  
