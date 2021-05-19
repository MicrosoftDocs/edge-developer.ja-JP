---
description: WinUI アプリ向け WebView2 の使い始めガイド
title: WinUI アプリ用 WebView2 の使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Webview2、WebView、Webview、winui アプリ、winui、edge、CoreWebView2、ブラウザー コントロール、エッジ html、開始、はじめに、.NET
ms.openlocfilehash: e334e8e7aec5fff4c57700a99de5cde906242e4f
ms.sourcegitcommit: bbbf722067f1d255f59ab384e66798f8b77ef609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "11574583"
---
# <a name="get-started-with-webview2-in-winui-3-preview"></a>WinUI 3 での WebView2 の使用を開始する (プレビュー)  

この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。  最初の WebView2 アプリは WinUI3 を使用します。  個々の API の詳細については、[API リファレンス][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動してください。  

## <a name="prerequisites"></a>前提条件  

先に進む前に、次の前提条件の一覧をインストールしてください。  

*   [WebView2 ランタイム][Webview2Installer]または Microsoft Edge [(Chromium)][MicrosoftedgeinsiderDownload]バージョン 1803 \(ビルド 17134\) 以降にインストールされている任意の Windows 10 (Chromium) 非安定チャネル。  [更新プログラム] の詳細Windows 10、[更新プログラム[: FAQ] Windows移動します][MicrosoftSupport12373]。  
    
    > [!NOTE]
    > WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。  
    
*   [Visual Studio][MicrosoftVisualstudioMain] 2019 バージョン 16.9 プレビュー。  詳細については、「UI ライブラリ[3 プレビュー 3 Windows」に移動します][WindowsAppsWinui3ConfigureYourDevEnvironment]。  
    *   インストール時に次のワークロードを含Visual Studio。  
        *   .NET Desktop Development \(インストーラーは .NET 5\) もインストールします。  
        *   ユニバーサル Windows プラットフォーム開発  
    *   C++ アプリをビルドするには、次のワークロードも含める必要があります。  
        *   C++ を使用したデスクトップ開発  
        *   ユニバーサル プラットフォーム ワークロード用の C++ \(v142\) ユニバーサル Windows ツールオプション コンポーネントWindowsです。  詳細については、右側のウィンドウ**の**[ユニバーサル Windows プラットフォーム開発] セクション**の [** インストールの詳細] に移動します。  
        
## <a name="step-0---visual-studio-settings"></a>手順 0 - Visual Studio設定  

1.  システムのパッケージ ソースがNuGet有効になっている[nuget.org。][NugetHome] 詳細については、「Common NuGet[構成」][NugetConsumePackagesConfiguringNugetBehavior]および「Windows Community Toolkit」[に移動します][WindowsCommunitytoolkit]。  
1.  レユニオン VSIX パッケージProject[インストールします][VisualstudioMarketplaceProjectreunionMicrosoftprojectreunion]。  インストーラーは、WinUI 3 プロジェクト テンプレートと、WinUI 3 ライブラリを含む NuGet パッケージの両方を 2019 年Visual Studioします。  
    
    パッケージをパッケージに追加する方法については、「Visual Studio拡張機能の検索と使用」 `VSIX` [にVisual Studioします][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。
    
1.  すべての開発者固有の機能にVisual Studioするには、[開発者モード][をオンにします][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。  
    
## <a name="step-1---create-project"></a>手順 1 - 作成Project  

1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。  

1.  [新Visual Studio] で、[新**しいプロジェクトの作成] を選択します**。  
1.  [プロジェクト] ドロップダウンで、[プロジェクト **]**、[C#] **、Windows** **[WinUI]** をそれぞれ選択します。  
    
    :::image type="complex" source="./media/winui-getting-started-selections.png" alt-text="新しい WinUI プロジェクトを作成するには、次のVisual Studio" lightbox="./media/winui-getting-started-selections.png":::
        新しい WinUI プロジェクトを作成するには、次のVisual Studio
    :::image-end:::  
    
1.  [**空のアプリ] を選択し、[パッケージ化] (デスクトップの WinUI) [次へ]**  >  **を選択します**。  
1.  プロジェクト名を入力します。
1.  必要に応じてオプションを選択します。  
1.  [**Create (作成)**] を選択します。  
1.  [**新しいユニバーサル Windows プラットフォーム Project] で、次**の値を選択し **、[OK] を選択します**。  
    *   **ターゲット バージョン**: **Windows 10 バージョン 1903 (ビルド 18362)** 以降  
    *   **最小バージョン**: Windows 10**バージョン 1803 (ビルド 17134)**  
        
    :::image type="complex" source="./media/winui-getting-started-project-type.png" alt-text="[新しいユニバーサル Windows プラットフォーム] ダイアログProjectターゲット バージョンと最小バージョンの値を選択します。" lightbox="./media/winui-getting-started-project-type.png":::
       [新しいユニバーサル Windows プラットフォーム] ダイアログProjectターゲット バージョンと最小バージョンの値を選択します。
    :::image-end:::  
    
1.  ソリューション エクスプローラーでは、2 つのプロジェクトが生成されます。  
    *   **プロジェクト名 (デスクトップ)**  デスクトップ プロジェクトには、アプリのコードが含まれている。  ファイル `App.xaml.cs` は、アプリ インスタンス `Application` を表すクラスを定義します。  ファイル `MainWindow.xaml.cs` は、アプリ インスタンス `MainWindow` によって表示されるメイン ウィンドウを表すクラスを定義します。  クラスは、WinUI の名前空間内 `Microsoft.UI.Xaml` の型から派生します。  
    *   **プロジェクト名 (パッケージ)**  Package プロジェクトは、展開Windows MSIX Projectにアプリをビルドするように構成されたアプリケーション パッケージ パッケージです。  プロジェクトには、アプリのパッケージ マニフェストが含まれています。既定では、ソリューションのスタートアップ プロジェクトです。  詳細については[、「MSIX][WindowsMsixDesktopToUwpPackagingDotNet]パッケージ用のデスクトップ アプリケーションをセットアップする」および「Visual Studio のパッケージ マニフェスト スキーマ参照」[に移動][UwpSchemasAppxpackageUapmanifestRoot]Windows 10。  
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
    
    :::image type="complex" source="./media/winui-getting-started-part-3.png" alt-text="WebView2 コントロールには、次の microsoft.com" lightbox="./media/winui-getting-started-part-3.png":::
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
    
    :::image type="complex" source="./media/winui-getting-started-bing.png" alt-text="bing.com" lightbox="./media/winui-getting-started-bing.png":::
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

:::image type="complex" source="./media/winui-getting-started-script.png" alt-text="WebView2 コントロールがアラート ダイアログを表示する" lightbox="./media/winui-getting-started-script.png":::
   WebView2 コントロールがアラート ダイアログを表示する
:::image-end:::  

これで、最初の WebView2 アプリがビルドされました。  

## <a name="next-steps"></a>次の手順  

WebView2 の詳細については、次のリソースを参照してください。  

*   WebView2 アプリケーションの構築の詳細については [、「WebView2 開発のベスト プラクティス」に移動します][WV2BestPractices]。  
*   WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。  
    
    > [!NOTE]
    > WebView2 API のリリースでは、WinRT CoreWebView2 オブジェクトを使用できない場合があります。  WebView2 コントロールで使用できる API を理解するには [、WebView2 Spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動して、使用可能な API の一覧を確認します。  
    
*   WebView2 API の詳細については [、WebView2 仕様に移動します][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

WinUI 固有の機能要求またはバグを送信するには、[問題 [- microsoft/microsoft-ui-xaml]][GithubMicrosoftMicrosoftUiXamlIssues] に移動し、[新しい問題] **を選択します**。  

<!-- links -->  
[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 の開発のベスト プラクティス|Microsoft Docs"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  
[MicrosoftDeveloperMicrosoftEdgeWebview2]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  

[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExescriptAsync(String) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "一般的NuGet構成|Microsoft Docs"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "パッケージ マニフェスト スキーマ参照 (Windows 10 |Microsoft Docs"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "[拡張機能の管理] ダイアログ ボックスを使用せずにインストールする - 拡張機能の管理 Visual Studio |Microsoft Docs"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "開発環境を構成する - WINDOWS UI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows Community Toolkit ドキュメント |Microsoft Docs"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "MSIX パッケージ用にデスクトップ アプリケーションをセットアップVisual Studio |Microsoft Docs"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効|Microsoft Docs"  

[GithubMicrosoftMicrosoftUiXamlIssues]: https://github.com/microsoft/microsoft-ui-xaml/issues "問題 - microsoft/microsoft-ui-xaml |GitHub"  
[GithubMicrosoftMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 仕様 - microsoft/microsoft-ui-xaml-specs |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows更新プログラム: FAQ"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[NugetHome]: https://nuget.org "ホーム |NuGetギャラリー"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "ダウンロード dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceProjectreunionMicrosoftprojectreunion]: https://marketplace.visualstudio.com/items?itemName=ProjectReunion.MicrosoftProjectReunion "Projectレユニオン |Visual StudioMarketplace"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
