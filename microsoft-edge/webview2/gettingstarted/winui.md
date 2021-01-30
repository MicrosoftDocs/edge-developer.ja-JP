---
description: WinUI アプリ用 WebView2 の使用を開始するガイド
title: WinUI アプリ用 WebView2 の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winui アプリ、winui、edge、CoreWebView2、ブラウザー コントロール、エッジ HTML、開始、開始、.NET
ms.openlocfilehash: 5188a735eaf635c3b3bc0eead6f4ee4f3a83f1c4
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306153"
---
# WinUI 3 での WebView2 の使用を開始する (プレビュー)  

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  最初の WebView2 アプリは WinUI3 を使用します。  個々の API の詳細については、API リファレンスに [移動してください][GithubMicrosoftUiXamlSpecsWebview2]。  

## 前提条件  

先に進む前に、前提条件の次の一覧をインストールしてください。  

*   Windows 10 バージョン 1803 \(ビルド 17134\) 以降にインストールされている[WebView2][Webview2Installer]ランタイムまたは[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]非安定チャネル。  Windows 10 について詳しくは、「Windows [Update: FAQ」をご覧ください][MicrosoftSupport12373]。  
    
    > [!NOTE]
    > WebView チームでは、Canary チャネルの使用をお勧めします。必要な最小バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2019 バージョン 16.9 プレビュー。  詳しくは [、Windows UI ライブラリ 3 プレビュー 3 に移動してください][WindowsAppsWinui3ConfigureYourDevEnvironment]。  
    
    *   インストール時に次のワークロードを含Visual Studio。  
        *   .NET Desktop Development \(インストーラーは .NET 5\ もインストールします)  
        *   ユニバーサル Windows プラットフォーム開発  
    *   C++ アプリをビルドするには、次のワークロードも含める必要があります。  
        *   C++ を使用したデスクトップ開発  
        *   C++ \(v142\) ユニバーサル Windows プラットフォーム ツール (ユニバーサル Windows プラットフォーム ワークロード用のオプション コンポーネント)。  詳細については、右側のウィンドウの [**ユニバーサル Windows**プラットフォーム**開発]** セクションの [インストールの詳細] に移動します。  
        
## 手順 0 - Visual Studio設定  

1.  システムで NuGet パッケージ ソースが有効になっているか確認 [nuget.org。][NugetHome] 詳細については、一般的な [NuGet][NugetConsumePackagesConfiguringNugetBehavior] 構成と [Windows コミュニティ][WindowsCommunitytoolkit]に移動Toolkit。  
1.  [WinUI 3 Preview 3 VSIX パッケージをダウンロードしてインストールします][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。  インストーラーは、WinUI 3 プロジェクト テンプレートと、WinUI 3 ライブラリを含む NuGet パッケージの両方を 2019 Visual Studioします。  
    
    パッケージをパッケージに追加する方法についてはVisual Studio拡張機能の検索と `VSIX` [使用Visual Studioしてください][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。
    
1.  開発者固有のすべての機能にアクセスVisual Studio、開発者モードを [有効にします][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。  
    
## 手順 1 - プロジェクトを作成する  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  In Visual Studio, choose **Create a new project**.  
1.  プロジェクトのドロップダウンで **、C#、Windows、****および** **WinUI をそれぞれ**選択します。  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="次のコマンドを使用して新しい WinUI プロジェクトをVisual Studio" lightbox="./media/winui-gettingstarted-selections.png":::
        次のコマンドを使用して新しい WinUI プロジェクトをVisual Studio
    :::image-end:::  
    
1.  Choose **Blank App, Packaged (WinUI in Desktop)**  >  **Next**.  
1.  プロジェクト名を入力します。
1.  必要に応じてオプションを選択します。  
1.  [**Create (作成)**] を選択します。  
1.  [ **新しいユニバーサル Windows プラットフォーム プロジェクト] で**、次の値を選択し **、[OK]** を選択します。  
    *   **ターゲット バージョン**:  **Windows 10 バージョン 1903 (ビルド 18362)** 以降  
    *   **最小バージョン**:  **Windows 10 バージョン 1803 (ビルド 17134)**  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="[ターゲット バージョン] と [最小バージョン] の値が選択された [新しいユニバーサル Windows プラットフォーム プロジェクト] ダイアログ。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       [ターゲット バージョン] と [最小バージョン] の値が選択された [新しいユニバーサル Windows プラットフォーム プロジェクト] ダイアログ。
    :::image-end:::  
    
1.  ソリューション エクスプローラーでは、2 つのプロジェクトが生成されます。  
    *   **プロジェクト名 (デスクトップ)** です。  デスクトップ プロジェクトには、アプリのコードが含まれている。  この `App.xaml.cs` ファイルは、アプリ `Application` インスタンスを表すクラスを定義します。  この `MainWindow.xaml.cs` ファイルは、アプリ `MainWindow` インスタンスによって表示されるメイン ウィンドウを表すクラスを定義します。  これらのクラスは `Microsoft.UI.Xaml` 、WinUI の名前空間の型から派生します。  
    *   **プロジェクト名 (パッケージ)** です。  Package プロジェクトは、アプリを展開用の MSIX パッケージにビルドするように構成された Windows アプリケーション パッケージ プロジェクトです。  プロジェクトにはアプリのパッケージ マニフェストが含まれています。既定では、ソリューションのスタートアップ プロジェクトです。  詳しくは[、「Windows 10][UwpSchemasAppxpackageUapmanifestRoot]のパッケージ マニフェスト スキーマ リファレンス」の「Visual Studio [MSIX][WindowsMsixDesktopToUwpPackagingDotNet]パッケージ用のデスクトップ アプリケーションのセットアップ」をご覧ください。  
1.  ソリューション エクスプローラーでコードを表示するには、ファイルを開 `MainWindow.xaml` きます。  プロジェクトを実行し、ボタンのあるウィンドウを表示するには、次を選択します `F5` 。  
    
## 手順 2 - WebView2 コントロールをプロジェクトに追加する  

WebView2 コントロールをプロジェクトに追加します。  

1.  ファイルで `MainWindow.xaml` 、WebView2 XAML 名前空間を追加するには、タグ内に次の行を挿入 `<Window/>` します。  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    コードが次 `MainWindow.xaml` のコード スニペットと似ている必要があります。  
    
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
    
1.  WebView2 コントロールを追加するには、タグを次の `<StackPanel>` コード スニペットに置き換えます。  この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。  
    
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
    
1.  ファイル内 `MainWindow.xaml.cs` で、次の行をコメント アウトします。
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  プロジェクトをビルドして実行するには、次を選択します `F5` 。  WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="WebView2 コントロールには、次のmicrosoft.com" lightbox="./media/winui-gettingstarted-part3.png":::
       WebView2 コントロールは、コントロールを表示microsoft.com  
    :::image-end:::  
    
## 手順 3 - ナビゲーション コントロールを追加する  

WebView2 コントロールに表示される Web ページをユーザーが制御するには、アプリにアドレス バーを追加します。  

1.  ファイル内 `MainWindow.xaml` で、要素を含む要素内に次のコード `<Grid>` スニペットをコピーして貼り付 `WebView2` けます。  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    ファイル内 `<Grid>` の要素が `MainWindow.xaml` 次のコード スニペットと似ている必要があります。  
    
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
    
1.  ファイル内で、次のコード スニペットをコピーして、WebView2 コントロールをアドレス バーに入力された `MainWindow.xaml.cs` `myButton_Click` URL に移動します。  
    
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
    
    プロジェクトをビルドして実行するには、次を選択します `F5` 。  アドレス バーに新しい URL を入力し、[移動] を選択 **します**。  たとえば、`https://www.bing.com` と入力します。  
    
    > [!NOTE]
    > アドレス バーに完全な URL を入力してください。  `ArgumentException` URL が次の値で始まるか、または次の URL で始まる場合は例外が `http://` スローされます `https://` 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       bing.com  
    :::image-end:::  
    
## 手順 4 - ナビゲーション イベント  

WebView2 コントロールをホストするアプリは、WebView2 コントロールが Web ページのナビゲーション中に発生する次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に `NavigationStarting` 複数のイベントがあります。  

詳細については、ナビゲーション イベントに [移動します][Webviews2ConceptsNavigationEvents]。  

エラーが発生すると、次のイベントが発生し、エラー Web ページに移動する可能性があります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
イベントを使用する方法の例として、HTTPS 以外の要求をキャンセル `NavigationStarting` するハンドラーを登録します。  In, `MainWindow.xaml.cs` modify the constructor to `EnsureHttps` register, and add the function so that `EnsureHttps` it matches the following code snippet.  

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

プロジェクトをビルドして実行するには、次を選択します `F5` 。  HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されます。  

## 手順 5 - スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行します。  

たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。  `EnsureHttps` [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]を使用する Web コンテンツにスクリプトを挿入する関数を変更します。  

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

プロジェクトをビルドして実行するには、次を選択します `F5` 。  HTTPS 以外の Web サイトに移動するときに、アプリに警告が表示されます。  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="通知ダイアログを表示する WebView2 コントロール" lightbox="./media/winui-gettingstarted-script.png":::
   通知ダイアログを表示する WebView2 コントロール
:::image-end:::  

これで、最初の WebView2 アプリがビルドされました。  

## 次のステップ  

WebView2 の詳細については、次のリソースを参照してください。  

### 関連項目  

*   WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   WebView2 の詳細については [、「WebView2 リソース」に移動してください][Webview2IndexNextSteps]。  
    
    > [!NOTE]
    > WinRT CoreWebView2 オブジェクトは、WebView2 API のリリースでは使用できない場合があります。  WebView2 コントロールで使用できる API を理解するには [、WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] に移動して、使用可能な API の一覧を確認します。  
    
*   WebView2 API の詳細については [、WebView2 仕様に移動してください][GithubMicrosoftUiXamlSpecsWebview2]。  
    
## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: ../index.md "Microsoft Edge WebView2 (プレビュー) |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) |Microsoft Docs"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "NuGet の一般的な構成|Microsoft Docs"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "Windows 10 | のパッケージ マニフェスト スキーマ リファレンスMicrosoft Docs"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "[拡張機能の管理] ダイアログ ボックスを使用せずにインストールする - Visual Studio |Microsoft Docs"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "開発環境を構成する - Windows UI Library 3.0 Preview 1 (2020 年 5 月) |Microsoft Docs"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows Community Toolkit ドキュメント |Microsoft Docs"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "MSIX パッケージ用にデスクトップ アプリケーションをセットアップVisual Studio |Microsoft Docs"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効|Microsoft Docs"  

[GithubMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 仕様 - microsoft/microsoft-ui-xaml-specs |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows Update: FAQ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[NugetHome]: https://nuget.org "ホーム |NuGet ギャラリー"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "ダウンロードdotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 プロジェクト テンプレート |Visual Studio Marketplace"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
