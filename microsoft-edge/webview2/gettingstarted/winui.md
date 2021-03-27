---
description: WinUI アプリ用 WebView2 の使い始めガイド
title: WinUI アプリ用 WebView2 の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Webview2、WebView、Webview、winui アプリ、winui、edge、CoreWebView2、ブラウザー コントロール、エッジ html、開始方法、開始方法、.NET
ms.openlocfilehash: 52d84afb6f9fe1e120f75525b2669a797309fdfe
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461207"
---
# <a name="getting-started-with-webview2-in-winui-3-preview"></a>WinUI 3 の WebView2 の使用を開始する (プレビュー)  

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  最初の WebView2 アプリは WinUI3 を使用します。  個々の API の詳細については、[API リファレンス][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動してください。  

## <a name="prerequisites"></a>前提条件  

先に進む前に、次の前提条件の一覧をインストールしてください。  

*   [WebView2 ランタイム][Webview2Installer] または Windows 10 バージョン 1803 \(ビルド 17134\) 以降にインストールされている Microsoft [Edge (クロム)][MicrosoftedgeinsiderDownload] 非安定チャネル。  Windows 10 の詳細については [、「Windows Update: FAQ」に移動します][MicrosoftSupport12373]。  
    
    > [!NOTE]
    > WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2019 バージョン 16.9 プレビュー。  詳細については [、「Windows UI ライブラリ 3 プレビュー 3」に移動します][WindowsAppsWinui3ConfigureYourDevEnvironment]。  
    *   インストール時に次のワークロードを含Visual Studio。  
        *   .NET Desktop Development \(インストーラーは .NET 5\) もインストールします。  
        *   ユニバーサル Windows プラットフォームの開発  
    *   C++ アプリをビルドするには、次のワークロードも含める必要があります。  
        *   C++ を使用したデスクトップ開発  
        *   ユニバーサル Windows プラットフォーム ワークロード用の C++ \(v142\) ユニバーサル Windows プラットフォーム ツールオプション コンポーネント。  詳細については、右側のウィンドウ**の [****ユニバーサル Windows プラットフォーム**開発] セクションの [インストールの詳細] に移動します。  
        
## <a name="step-0---visual-studio-settings"></a>手順 0 - Visual Studio設定  

1.  システムで NuGet パッケージ ソースが有効になっているか確認 [nuget.org。][NugetHome] 詳細については [、「Common NuGet 構成」][NugetConsumePackagesConfiguringNugetBehavior] および「Windows Community Toolkit」 [に移動します][WindowsCommunitytoolkit]。  
1.  [WinUI 3 Preview 3 VSIX パッケージをダウンロードしてインストールします][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]。  インストーラーは、WinUI 3 プロジェクト テンプレートと、WinUI 3 ライブラリを含む NuGet パッケージの両方を 2019 年Visual Studioします。  
    
    パッケージをパッケージに追加する方法については、「Visual Studio拡張機能の検索と使用」 `VSIX` [にVisual Studioします][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。
    
1.  すべての開発者固有の機能にVisual Studioするには、[開発者モード] [をオンにします][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。  
    
## <a name="step-1---create-project"></a>手順 1 - プロジェクトの作成  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  [新Visual Studio] で、[新 **しいプロジェクトの作成] を選択します**。  
1.  [プロジェクト] ドロップダウンで、[ウィンドウ] **、C#** **WinUI****をそれぞれ**選択します。  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="プロジェクトを使用して新しい WinUI プロジェクトをVisual Studio" lightbox="./media/winui-gettingstarted-selections.png":::
        プロジェクトを使用して新しい WinUI プロジェクトをVisual Studio
    :::image-end:::  
    
1.  [**空のアプリ] を選択し、[パッケージ化] (デスクトップの WinUI) [次へ]**  >  **を選択します**。  
1.  プロジェクト名を入力します。
1.  必要に応じてオプションを選択します。  
1.  [**Create (作成)**] を選択します。  
1.  [ **新しいユニバーサル Windows プラットフォーム プロジェクト] で**、次の値を選択し **、[OK] を選択します**。  
    *   **対象バージョン**:  **Windows 10 バージョン 1903 (ビルド 18362)** 以降  
    *   **最小バージョン**:  **Windows 10 バージョン 1803 (ビルド 17134)**  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="[ターゲット バージョン] と [最小バージョン] の値を選択した [新しいユニバーサル Windows プラットフォーム プロジェクト] ダイアログ。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       [ターゲット バージョン] と [最小バージョン] の値を選択した [新しいユニバーサル Windows プラットフォーム プロジェクト] ダイアログ。
    :::image-end:::  
    
1.  ソリューション エクスプローラーでは、2 つのプロジェクトが生成されます。  
    *   **プロジェクト名 (デスクトップ)**  デスクトップ プロジェクトには、アプリのコードが含まれている。  ファイル `App.xaml.cs` は、アプリ インスタンス `Application` を表すクラスを定義します。  ファイル `MainWindow.xaml.cs` は、アプリ インスタンス `MainWindow` によって表示されるメイン ウィンドウを表すクラスを定義します。  クラスは、WinUI の名前空間内 `Microsoft.UI.Xaml` の型から派生します。  
    *   **プロジェクト名 (パッケージ)**  パッケージ プロジェクトは、展開用に MSIX パッケージにアプリをビルドするように構成された Windows アプリケーション パッケージ プロジェクトです。  プロジェクトには、アプリのパッケージ マニフェストが含まれています。既定では、ソリューションのスタートアップ プロジェクトです。  詳細については、「Windows [10][UwpSchemasAppxpackageUapmanifestRoot]の[MSIX][WindowsMsixDesktopToUwpPackagingDotNet]パッケージのデスクトップ アプリケーションをセットアップする」および「Visual Studio マニフェスト スキーマリファレンス」に移動します。  
1.  ソリューション エクスプローラーで、コードを表示するには、ファイルを開 `MainWindow.xaml` きます。  プロジェクトを実行し、ボタンでウィンドウを表示するには、 を選択します `F5` 。  
    
## <a name="step-2---add-a-webview2-control-to-your-project"></a>手順 2 - WebView2 コントロールをプロジェクトに追加する  

WebView2 コントロールをプロジェクトに追加します。  

1.  `MainWindow.xaml`ファイルで、WebView2 XAML 名前空間を追加するには、`<Window/>` タグ内に次の行を挿入します。  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    コードが次 `MainWindow.xaml` のコード スニペットに似ているか確認します。  
    
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
    
1.  ファイルで `MainWindow.xaml.cs` 、次の行をコメントアウトします。
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  プロジェクトをビルドして実行するには、 を選択します `F5` 。  WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="WebView2 コントロールには、次の microsoft.com" lightbox="./media/winui-gettingstarted-part3.png":::
       WebView2 コントロールには、次の microsoft.com  
    :::image-end:::  
    
## <a name="step-3---add-navigation-controls"></a>手順 3 - ナビゲーション コントロールを追加する  

WebView2 コントロールに表示される Web ページをユーザーが制御するには、アプリにアドレス バーを追加します。  

1.  ファイル内 `MainWindow.xaml` で、要素を含む要素内に次の `<Grid>` コード スニペットをコピーして貼り付 `WebView2` けます。  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    ファイル内 `<Grid>` の要素が `MainWindow.xaml` 次のコード スニペットに似ているか確認します。  
    
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
    
1.  ファイルで、次のコード スニペットをコピーして、WebView2 コントロールをアドレス バーに入力した `MainWindow.xaml.cs` `myButton_Click` URL に移動します。  
    
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
    
    プロジェクトをビルドして実行するには、 を選択します `F5` 。  アドレス バーに新しい URL を入力し、[移動] を **選択します**。  たとえば、`https://www.bing.com` と入力します。  
    
    > [!NOTE]
    > アドレス バーに完全な URL を入力してください。  `ArgumentException` URL がで始まるか、またはで始まる場合、例外が `http://` スローされます `https://` 。  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       bing.com  
    :::image-end:::  
    
## <a name="step-4---navigation-events"></a>手順 4 - ナビゲーション イベント  

WebView2 コントロールをホストするアプリは、Web ページ ナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> HTTP リダイレクトが発生した場合、1 行に複数の `NavigationStarting` イベントがあります。  

詳細については、[ナビゲーション イベント][Webviews2ConceptsNavigationEvents]に移動してください。  

エラーが発生すると、次のイベントが発生し、エラー Web ページに移動することがあります。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
イベントを使用する方法の例として、HTTPS 以外の要求を取り消すハンドラー `NavigationStarting` を登録します。  で `MainWindow.xaml.cs` 、コンストラクターを変更して登録し、次のコード スニペットと一致する `EnsureHttps` `EnsureHttps` 関数を追加します。  

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

プロジェクトをビルドして実行するには、 を選択します `F5` 。  HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されている必要があります。  

## <a name="step-5---scripting"></a>手順 5 - スクリプト  

ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。  任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。  挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。  挿入された JavaScript は、特定のタイミングで実行されます。  

*   グローバル オブジェクトの作成後に実行します。  
*   HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。  

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

プロジェクトをビルドして実行するには、 を選択します `F5` 。  HTTPS 以外の Web サイトに移動すると、アプリに通知が表示されます。  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="WebView2 コントロールがアラート ダイアログを表示する" lightbox="./media/winui-gettingstarted-script.png":::
   WebView2 コントロールがアラート ダイアログを表示する
:::image-end:::  

これで、最初の WebView2 アプリがビルドされました。  

## <a name="next-steps"></a>次の手順  

WebView2 の詳細については、次のリソースを参照してください。  

### <a name="see-also"></a>関連項目  

*   WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  
    
    > [!NOTE]
    > WebView2 API のリリースでは、WinRT CoreWebView2 オブジェクトを使用できない場合があります。  WebView2 コントロールで使用できる API を理解するには [、WebView2 Spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動して、使用可能な API の一覧を確認します。  
    
*   WebView2 API の詳細については [、WebView2 仕様に移動します][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

WinUI 固有の機能要求またはバグを送信するには、[問題 [- microsoft/microsoft-ui-xaml]][GithubMicrosoftMicrosoftUiXamlIssues] に移動し、[新しい問題] **を選択します**。  

<!-- links -->  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: ../index.md "Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExescriptAsync(String) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "NuGet の一般的な構成|Microsoft Docs"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "Windows 10 のパッケージ マニフェスト スキーマ参照|Microsoft Docs"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "[拡張機能の管理] ダイアログ ボックスを使用せずにインストールする - 拡張機能の管理 Visual Studio |Microsoft Docs"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "開発環境を構成する - Windows UI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows コミュニティ Toolkit ドキュメント |Microsoft Docs"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "MSIX パッケージ用にデスクトップ アプリケーションをセットアップVisual Studio |Microsoft Docs"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効|Microsoft Docs"  

[GithubMicrosoftMicrosoftUiXamlIssues]: https://github.com/microsoft/microsoft-ui-xaml/issues "問題 - microsoft/microsoft-ui-xaml |GitHub"  
[GithubMicrosoftMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 仕様 - microsoft/microsoft-ui-xaml-specs |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows Update: FAQ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[NugetHome]: https://nuget.org "ホーム |NuGet ギャラリー"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "ダウンロード dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 Project Templates |Visual Studio Marketplace"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
