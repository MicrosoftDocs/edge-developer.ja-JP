---
description: WinUI アプリ用 WebView2 の概要ガイド
title: WinUI アプリの WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、winui apps、winui、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: df6ee7a7391337635a63a961f62317e5b8a67334
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119095"
---
# WinUI3 での WebView2 の概要 (プレビュー)  

この記事では、WinUI3 で初めて WebView2 アプリを作成する方法について説明します。 [Microsoft Edge WebView2 (Preview) の概要][Webview2Index]の主な機能について説明します。  個々の Api について詳しくは、 [api リファレンス][GithubMicrosoftUiXamlSpecsWebview2]をご覧ください。  

## 前提条件  

次の記事を始める前に、次の前提条件の一覧をインストールしてください。  

*   Windows 10 バージョン 1803 \ (ビルド 17134 \) 以降。  詳細については、「 [Windows Update: FAQ][MicrosoftSupport12373]」を参照してください。  
*   [Microsoft Edge (Chromium) カナリア Channel][MicrosoftedgeinsiderDownload] windows 10、windows 8.1、または windows 7。  
*   Visual Studio 2019、バージョン 16.7 Preview 1。  詳細については、 [WINDOWS UI ライブラリ3プレビュー 2 (2020 年7月)][WindowsAppsWinui3ConfigureYourDevEnvironment]を参照してください。  
*   [X64][WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]と[x86][WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]の両方のバージョンの .net 5 Preview 4。  
*   [WinUI 3][VisualstudioMarketplaceWinUiprojecttemplates] Visual Studio 2019 用のプロジェクトテンプレートの拡張機能  
すべての Visual Studio 機能に確実にアクセスできるように、 [開発者モードを有効][WindowsUwpGetStartedEnableYourDeviceForDevelopment] にしていることを確認します。  

## 手順 1-プロジェクトを作成する  

1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。  

1.  Visual Studio で、[ **新しいプロジェクトの作成**] を選択します。  
1.  [プロジェクト] ドロップダウンで、[ **C#**]、[ **Windows**]、[ **WinUI** ] の順に選択します。  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-selections.png":::
       WinUI の Visual studio プロジェクト作成ダイアログ  
    :::image-end:::  
    
1.  [ **空のアプリ]、[パッケージ] (デスクトップの WinUI)** の順に選び、[ **次へ**] を選びます。  
1.  プロジェクト名を入力し、必要に応じてその他のオプションを選択して、[ **作成**] を選択します。  
1.  **新しいユニバーサル Windows プラットフォームプロジェクト**で、次の値を選択し、[ **OK]** を選択します。  
    *   ターゲットバージョン: **Windows 10、バージョン 1903 (ビルド 18362)** 以降。  
    *   最小バージョン: **Windows 10、バージョン 1803 (ビルド 17134)**。  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-projecttype.png":::
       [ターゲットバージョン] と [最小バージョン] の値が選択された新しいユニバーサル Windows プラットフォームプロジェクトダイアログ。
    :::image-end:::  
    
1.  ソリューションエクスプローラーで、2つのプロジェクトが生成されます。  
    *   **プロジェクト名 (デスクトップ)** このプロジェクトには、アプリのコードが含まれています。  **App.xaml.cs** は、 `Application` アプリインスタンスを表すクラスを定義します。 **MainWindow.xaml.cs** は、 `MainWindow` アプリインスタンスによって表示されるメインウィンドウを表すクラスを定義します。  これらのクラスは、 `Microsoft.UI.Xaml` WinUI の名前空間の型から派生します。  
    
    *   **プロジェクト名 (パッケージ)**。  このプロジェクトは、アプリを展開用の MSIX パッケージにビルドするように構成されている、Windows アプリケーションパッケージプロジェクトです。  プロジェクトには、アプリの thepackage manifestfor 含まれており、既定では、ソリューションのスタートアッププロジェクトになります。 詳細については、「 [Windows 10 のパッケージマニフェストスキーマリファレンス][UwpSchemasAppxpackageUapmanifestRoot]」の「 [msix パッケージ用にデスクトップアプリケーションをセットアップ][WindowsMsixDesktopToUwpPackagingDotNet]する」を参照してください。
    
1.  ソリューションエクスプローラーで **MainWindow** を開いて、コードを表示します。  プロジェクトを実行し、 `F5` ボタンを含むウィンドウを表示するには、を選択します。  
    
## 手順 2-WebView2 コントロールをプロジェクトに追加する  

次に、WebView2 コントロールをプロジェクトに追加します。  

1.  [開く] `MainWindow.xaml` を選びます。  タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    次のコードスニペットのように、コードが次のようになっていることを確認 `MainWindow.xaml` します。  
    
    ```xml
    <Window
          x:Class="WinUI_Sample.MainWindow"
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:local="using:WinUI_Sample"
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
          mc:Ignorable="d"
          xmlns:controls="using:Microsoft.UI.Xaml.Controls"
          >
        
          <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" VerticalAlignment="Center">
            <Button x:Name="myButton" Click="myButton_Click">Click Me</Button>
          </StackPanel>
    
    </Window>
    ```  
    
1.  WebView2 コントロールを追加するには、 `<StackPanel>` 次のコードスニペットでタグを置き換えます。  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  
    
    ```xml  
    <Grid>

        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="Auto" />
        </Grid.ColumnDefinitions>
        
        <controls:WebView2 x:Name="MyWebView"  Grid.Row="1" Grid.ColumnSpan="2" 
            Source="https://www.microsoft.com" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" />
    
    </Grid>
    ```  
    
1.  `MainWindow.xaml.cs`次の行を開いてコメントアウトします。
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  `F5`プロジェクトをビルドして実行する場合に選択します。  WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com][|::ref1::|Main] します。  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-part3.png":::
       Microsoft.com サイトを表示する WebView2 コントロール。  
    :::image-end:::  
    
## 手順 3-ナビゲーションコントロールを追加する  

WebView2 コントロールに表示される web ページをアプリに追加することにより、ユーザーがそのページをコントロールできるようにします。 

1.  **MainWindow**で、次のコードスニペットを、要素を含む要素内にコピーして貼り付け `Grid` `WebView2` ます。  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    要素が次のコードスニペットのようになっていることを確認 `Grid` `MainWindow.xaml` します。  
    
    ```xml
    <Grid>
    
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="Auto" />
        </Grid.ColumnDefinitions>
    
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
        
        <WebView2 x:Name="MyWebView"  Grid.Row="1" Grid.ColumnSpan="2" 
            Source="https://www.microsoft.com" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" />
    
    </Grid>
    ```  
    
1.  **MainWindow.xaml.cs**で、次のコードスニペットをコピーして `myButton_Click` 、WebView2 コントロールをアドレスバーに入力した URL に移動します。  
    
    ```csharp
    private void myButton_Click(object sender, RoutedEventArgs e)
    {
        try
        {
            Uri targetUri = new Uri(addressBar.Text);
            MyWebView.Source = targetUri;
        }
        catch (FormatException ex)
        {
            // Incorrect address entered.
        }
    }
    ```  
    
    `F5`プロジェクトをビルドして実行する場合に選択します。  アドレスバーに新しい URL を入力し、[ **移動**] を選択します。  たとえば、と入力 `https://www.bing.com` します。 
    
    > [!NOTE]
    > アドレスバーに完全な Url を使用していることを確認します。 `ArgumentException` URL が、またはで始まらない場合は、例外がスローされ `http://` `https://` ます。  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-bing.png":::
       Bing.com  
    :::image-end:::  
    
## ステップ 4-ナビゲーションイベント  

WebView2 コントロールをホストするアプリケーションは、web ページのナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> HTTP のリダイレクトでは `NavigationStarting` 、複数のイベントが発生します。  

詳細については、「 [ナビゲーションイベント][Webviews2ConceptsNavigationEvents]」を参照してください。  

エラーが発生すると、次のイベントが発生し、エラーページに移動する可能性があります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
イベントの使い方の例として、 `NavigationStarting` HTTPS を使っていない要求をすべてキャンセルするためのハンドラーを登録します。 で `MainWindow.xaml.cs` 、登録するコンストラクターを変更 `EnsureHttps` し、 `EnsureHttps` 次のコードスニペットと一致するように関数を追加します。  

```csharp
public MainWindow()
{
    InitializeComponent();
    MyWebView.NavigationStarting += EnsureHttps;
}

private void EnsureHttps(WebView2 sender, WebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
    else
    {
        addressBar.Text = uri;
    }
}
```  

`F5`プロジェクトをビルドして実行する場合に選択します。  HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されていることを確認します。  

## 手順 5-スクリプト  

ホストアプリケーションは、実行時に WebView2 コントロールに JavaScript コードを挿入することがあります。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しい最上位レベルのドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。  

例として、ユーザーが HTTPS 以外のサイトに移動したときにアラートが送信されることがあります。  この関数を変更し `EnsureHttps` て、 [executesを][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]使って web コンテンツにスクリプトを挿入します。  

```csharp
private void EnsureHttps(WebView2 sender, WebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        MyWebView.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
    else
    {
        addressBar.Text = uri;
    }
}
```  

`F5`プロジェクトをビルドして実行する場合に選択します。  HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-script.png":::
   通知ダイアログを表示する WebView2 コントロール
:::image-end:::  

おめでとうございます。最初の WebView2 アプリを作成しました。  

## 次のステップ  

現在、チームは WebView2 の Api を構築しています。  WebView2 Api の現在の状態について詳しくは、「 [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2]」をご覧ください。  

> [!NOTE]
> WebView2 Api が出荷されている時点で、WinRT CoreWebView2 オブジェクトが利用できない場合があります。 WebView2 コントロールで利用できる Api を理解するには、利用可能な Api の一覧については、 [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] を参照してください。 

WebView2 機能の詳細については、「 [WebView2 の概念と How-To ガイド][Webview2IndexNextSteps]」および [WebView2 サンプルのリポジトリ][GithubMicrosoftedgeWebview2samplesMain]を参照してください。  

## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーションイベント |Microsoft ドキュメント"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.Exe(文字列) メソッド (WebView2) | cuteScriptAsync) |Microsoft ドキュメント"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "Windows 10 のパッケージマニフェストスキーマリファレンス |Microsoft ドキュメント"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "開発環境の構成-Windows UI Library 3.0 Preview 1 (2020 年5月) |Microsoft ドキュメント"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "Visual Studio の MSIX パッケージ用にデスクトップアプリケーションをセットアップする |Microsoft ドキュメント"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効にする |Microsoft ドキュメント"  

[GithubMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 spec-microsoft/microsoft-ui-xaml-定義 |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Publisher"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows Update: よく寄せられる質問 (FAQ)"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exeをダウンロードする "  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceWinUiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 プロジェクトテンプレート"  
