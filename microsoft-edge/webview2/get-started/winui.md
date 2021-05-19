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
# <a name="get-started-with-webview2-in-winui-3-preview"></a><span data-ttu-id="95415-104">WinUI 3 での WebView2 の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="95415-104">Get started with WebView2 in WinUI 3 (Preview)</span></span>  

<span data-ttu-id="95415-105">この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="95415-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="95415-106">最初の WebView2 アプリは WinUI3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95415-106">Your first WebView2 app uses WinUI3.</span></span>  <span data-ttu-id="95415-107">個々の API の詳細については、[API リファレンス][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動してください。</span><span class="sxs-lookup"><span data-stu-id="95415-107">For more information on individual APIs, navigate to [API reference][GithubMicrosoftMicrosoftUiXamlSpecsWebview2].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="95415-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="95415-108">Prerequisites</span></span>  

<span data-ttu-id="95415-109">先に進む前に、次の前提条件の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="95415-109">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="95415-110">[WebView2 ランタイム][Webview2Installer]または Microsoft Edge [(Chromium)][MicrosoftedgeinsiderDownload]バージョン 1803 \(ビルド 17134\) 以降にインストールされている任意の Windows 10 (Chromium) 非安定チャネル。</span><span class="sxs-lookup"><span data-stu-id="95415-110">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="95415-111">[更新プログラム] の詳細Windows 10、[更新プログラム[: FAQ] Windows移動します][MicrosoftSupport12373]。</span><span class="sxs-lookup"><span data-stu-id="95415-111">For more information about Windows 10, navigate to [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="95415-112">WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。</span><span class="sxs-lookup"><span data-stu-id="95415-112">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="95415-113">[Visual Studio][MicrosoftVisualstudioMain] 2019 バージョン 16.9 プレビュー。</span><span class="sxs-lookup"><span data-stu-id="95415-113">[Visual Studio][MicrosoftVisualstudioMain] 2019, version 16.9 Preview.</span></span>  <span data-ttu-id="95415-114">詳細については、「UI ライブラリ[3 プレビュー 3 Windows」に移動します][WindowsAppsWinui3ConfigureYourDevEnvironment]。</span><span class="sxs-lookup"><span data-stu-id="95415-114">For more information, navigate to [Windows UI Library 3 Preview 3][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
    *   <span data-ttu-id="95415-115">インストール時に次のワークロードを含Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="95415-115">Include the following workloads when you install Visual Studio.</span></span>  
        *   <span data-ttu-id="95415-116">.NET Desktop Development \(インストーラーは .NET 5\) もインストールします。</span><span class="sxs-lookup"><span data-stu-id="95415-116">.NET Desktop Development \(the installer also installs .NET 5\)</span></span>  
        *   <span data-ttu-id="95415-117">ユニバーサル Windows プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="95415-117">Universal Windows Platform development</span></span>  
    *   <span data-ttu-id="95415-118">C++ アプリをビルドするには、次のワークロードも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="95415-118">To build C++ apps, you must also include the following workloads.</span></span>  
        *   <span data-ttu-id="95415-119">C++ を使用したデスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="95415-119">Desktop development with C++</span></span>  
        *   <span data-ttu-id="95415-120">ユニバーサル プラットフォーム ワークロード用の C++ \(v142\) ユニバーサル Windows ツールオプション コンポーネントWindowsです。</span><span class="sxs-lookup"><span data-stu-id="95415-120">The C++ \(v142\) Universal Windows Platform tools optional component for the Universal Windows Platform workload.</span></span>  <span data-ttu-id="95415-121">詳細については、右側のウィンドウ**の**[ユニバーサル Windows プラットフォーム開発] セクション**の [** インストールの詳細] に移動します。</span><span class="sxs-lookup"><span data-stu-id="95415-121">For more information,  navigate to **Installation Details** under the **Universal Windows Platform development** section, on the right pane.</span></span>  
        
## <a name="step-0---visual-studio-settings"></a><span data-ttu-id="95415-122">手順 0 - Visual Studio設定</span><span class="sxs-lookup"><span data-stu-id="95415-122">Step 0 - Visual Studio settings</span></span>  

1.  <span data-ttu-id="95415-123">システムのパッケージ ソースがNuGet有効になっている[nuget.org。][NugetHome] 詳細については、「Common NuGet[構成」][NugetConsumePackagesConfiguringNugetBehavior]および「Windows Community Toolkit」[に移動します][WindowsCommunitytoolkit]。</span><span class="sxs-lookup"><span data-stu-id="95415-123">Ensure your system has a NuGet package source enabled for [nuget.org][NugetHome].  For more information, navigate to [Common NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit].</span></span>  
1.  <span data-ttu-id="95415-124">レユニオン VSIX パッケージProject[インストールします][VisualstudioMarketplaceProjectreunionMicrosoftprojectreunion]。</span><span class="sxs-lookup"><span data-stu-id="95415-124">Download and install the [Project Reunion VSIX package][VisualstudioMarketplaceProjectreunionMicrosoftprojectreunion].</span></span>  <span data-ttu-id="95415-125">インストーラーは、WinUI 3 プロジェクト テンプレートと、WinUI 3 ライブラリを含む NuGet パッケージの両方を 2019 年Visual Studioします。</span><span class="sxs-lookup"><span data-stu-id="95415-125">The installer adds both the WinUI 3 project templates and the NuGet package containing the WinUI 3 libraries to Visual Studio 2019.</span></span>  
    
    <span data-ttu-id="95415-126">パッケージをパッケージに追加する方法については、「Visual Studio拡張機能の検索と使用」 `VSIX` [にVisual Studioします][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]。</span><span class="sxs-lookup"><span data-stu-id="95415-126">For instructions on how to add the `VSIX` package to Visual Studio, navigate to [Finding and Using Visual Studio Extensions][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox].</span></span>
    
1.  <span data-ttu-id="95415-127">すべての開発者固有の機能にVisual Studioするには、[開発者モード][をオンにします][WindowsUwpGetStartedEnableYourDeviceForDevelopment]。</span><span class="sxs-lookup"><span data-stu-id="95415-127">To access all developer-specific Visual Studio features, turn on [Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment].</span></span>  
    
## <a name="step-1---create-project"></a><span data-ttu-id="95415-128">手順 1 - 作成Project</span><span class="sxs-lookup"><span data-stu-id="95415-128">Step 1 - Create Project</span></span>  

<span data-ttu-id="95415-129">1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。</span><span class="sxs-lookup"><span data-stu-id="95415-129">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="95415-130">[新Visual Studio] で、[新**しいプロジェクトの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95415-130">In Visual Studio, choose **Create a new project**.</span></span>  
1.  <span data-ttu-id="95415-131">[プロジェクト] ドロップダウンで、[プロジェクト **]**、[C#] **、Windows** **[WinUI]** をそれぞれ選択します。</span><span class="sxs-lookup"><span data-stu-id="95415-131">In the project drop-down, choose **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-getting-started-selections.png" alt-text="新しい WinUI プロジェクトを作成するには、次のVisual Studio" lightbox="./media/winui-getting-started-selections.png":::
        <span data-ttu-id="95415-133">新しい WinUI プロジェクトを作成するには、次のVisual Studio</span><span class="sxs-lookup"><span data-stu-id="95415-133">Create a new WinUI project using Visual Studio</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="95415-134">[**空のアプリ] を選択し、[パッケージ化] (デスクトップの WinUI) [次へ]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95415-134">Choose **Blank App, Packaged (WinUI in Desktop)** > **Next**.</span></span>  
1.  <span data-ttu-id="95415-135">プロジェクト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="95415-135">Enter a project name.</span></span>
1.  <span data-ttu-id="95415-136">必要に応じてオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95415-136">Choose options as needed.</span></span>  
1.  <span data-ttu-id="95415-137">[**Create (作成)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95415-137">Choose **Create**.</span></span>  
1.  <span data-ttu-id="95415-138">[**新しいユニバーサル Windows プラットフォーム Project] で、次**の値を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95415-138">In **New Universal Windows Platform Project**, choose the following values, and then choose **OK**.</span></span>  
    *   <span data-ttu-id="95415-139">**ターゲット バージョン**: **Windows 10 バージョン 1903 (ビルド 18362)** 以降</span><span class="sxs-lookup"><span data-stu-id="95415-139">**Target version**:  **Windows 10, version 1903 (build 18362)** or later</span></span>  
    *   <span data-ttu-id="95415-140">**最小バージョン**: Windows 10**バージョン 1803 (ビルド 17134)**</span><span class="sxs-lookup"><span data-stu-id="95415-140">**Minimum version**:  **Windows 10, version 1803 (build 17134)**</span></span>  
        
    :::image type="complex" source="./media/winui-getting-started-project-type.png" alt-text="[新しいユニバーサル Windows プラットフォーム] ダイアログProjectターゲット バージョンと最小バージョンの値を選択します。" lightbox="./media/winui-getting-started-project-type.png":::
       <span data-ttu-id="95415-142">[新しいユニバーサル Windows プラットフォーム] ダイアログProjectターゲット バージョンと最小バージョンの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="95415-142">The New Universal Windows Platform Project dialog with chosen values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="95415-143">ソリューション エクスプローラーでは、2 つのプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="95415-143">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="95415-144">**プロジェクト名 (デスクトップ)**</span><span class="sxs-lookup"><span data-stu-id="95415-144">**Your project name (Desktop)**.</span></span>  <span data-ttu-id="95415-145">デスクトップ プロジェクトには、アプリのコードが含まれている。</span><span class="sxs-lookup"><span data-stu-id="95415-145">The Desktop project contains the code for your app.</span></span>  <span data-ttu-id="95415-146">ファイル `App.xaml.cs` は、アプリ インスタンス `Application` を表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="95415-146">The `App.xaml.cs` file defines an `Application` class that represents your app instance.</span></span>  <span data-ttu-id="95415-147">ファイル `MainWindow.xaml.cs` は、アプリ インスタンス `MainWindow` によって表示されるメイン ウィンドウを表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="95415-147">The `MainWindow.xaml.cs` file defines a `MainWindow` class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="95415-148">クラスは、WinUI の名前空間内 `Microsoft.UI.Xaml` の型から派生します。</span><span class="sxs-lookup"><span data-stu-id="95415-148">The classes derive from types in the `Microsoft.UI.Xaml` namespace of WinUI.</span></span>  
    *   <span data-ttu-id="95415-149">**プロジェクト名 (パッケージ)**</span><span class="sxs-lookup"><span data-stu-id="95415-149">**Your project name (Package)**.</span></span>  <span data-ttu-id="95415-150">Package プロジェクトは、展開Windows MSIX Projectにアプリをビルドするように構成されたアプリケーション パッケージ パッケージです。</span><span class="sxs-lookup"><span data-stu-id="95415-150">The Package project is a Windows Application Packaging Project that is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="95415-151">プロジェクトには、アプリのパッケージ マニフェストが含まれています。既定では、ソリューションのスタートアップ プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="95415-151">The project contains the package manifest for your app, and is the startup project for your solution by default.</span></span>  <span data-ttu-id="95415-152">詳細については[、「MSIX][WindowsMsixDesktopToUwpPackagingDotNet]パッケージ用のデスクトップ アプリケーションをセットアップする」および「Visual Studio のパッケージ マニフェスト スキーマ参照」[に移動][UwpSchemasAppxpackageUapmanifestRoot]Windows 10。</span><span class="sxs-lookup"><span data-stu-id="95415-152">For more information, navigate to [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>  
1.  <span data-ttu-id="95415-153">ソリューション エクスプローラーで、コードを表示するには、ファイルを開 `MainWindow.xaml` きます。</span><span class="sxs-lookup"><span data-stu-id="95415-153">In the Solution Explorer, to display the code, open the `MainWindow.xaml` file.</span></span>  <span data-ttu-id="95415-154">プロジェクトを実行し、ボタンでウィンドウを表示するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="95415-154">To run your project and display a window with a button, select `F5`.</span></span>  
    
## <a name="step-2---add-a-webview2-control-to-your-project"></a><span data-ttu-id="95415-155">手順 2 - WebView2 コントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="95415-155">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="95415-156">WebView2 コントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="95415-156">Add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="95415-157">`MainWindow.xaml`ファイルで、WebView2 XAML 名前空間を追加するには、`<Window/>` タグ内に次の行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="95415-157">In the `MainWindow.xaml` file, to add the WebView2 XAML namespace, insert the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="95415-158">コードが次 `MainWindow.xaml` のコード スニペットに似ているか確認します。</span><span class="sxs-lookup"><span data-stu-id="95415-158">Ensure your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="95415-159">WebView2 コントロールを追加するには、タグを次の `<StackPanel>` コード スニペットに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="95415-159">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="95415-160">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="95415-160">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
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
    
1.  <span data-ttu-id="95415-161">ファイルで `MainWindow.xaml.cs` 、次の行をコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="95415-161">In the `MainWindow.xaml.cs` file, comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="95415-162">プロジェクトをビルドして実行するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="95415-162">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="95415-163">WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="95415-163">Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-getting-started-part-3.png" alt-text="WebView2 コントロールには、次の microsoft.com" lightbox="./media/winui-getting-started-part-3.png":::
       <span data-ttu-id="95415-165">WebView2 コントロールには、次の microsoft.com</span><span class="sxs-lookup"><span data-stu-id="95415-165">WebView2 control displays microsoft.com</span></span>  
    :::image-end:::  
    
## <a name="step-3---add-navigation-controls"></a><span data-ttu-id="95415-166">手順 3 - ナビゲーション コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="95415-166">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="95415-167">WebView2 コントロールに表示される Web ページをユーザーが制御するには、アプリにアドレス バーを追加します。</span><span class="sxs-lookup"><span data-stu-id="95415-167">To allow users to control the webpage that is displayed in your WebView2 control, add an address bar to your app.</span></span>  

1.  <span data-ttu-id="95415-168">ファイル内 `MainWindow.xaml` で、要素を含む要素内に次の `<Grid>` コード スニペットをコピーして貼り付 `WebView2` けます。</span><span class="sxs-lookup"><span data-stu-id="95415-168">In the `MainWindow.xaml` file, copy and paste the following code snippet inside the `<Grid>` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="95415-169">ファイル内 `<Grid>` の要素が `MainWindow.xaml` 次のコード スニペットに似ているか確認します。</span><span class="sxs-lookup"><span data-stu-id="95415-169">Ensure your `<Grid>` element in the `MainWindow.xaml` file is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="95415-170">ファイルで、次のコード スニペットをコピーして、WebView2 コントロールをアドレス バーに入力した `MainWindow.xaml.cs` `myButton_Click` URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="95415-170">In the `MainWindow.xaml.cs` file, copy the following code snippet into `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
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
    
    <span data-ttu-id="95415-171">プロジェクトをビルドして実行するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="95415-171">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="95415-172">アドレス バーに新しい URL を入力し、[移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="95415-172">Enter a new URL in the address bar, and then choose **Go**.</span></span>  <span data-ttu-id="95415-173">たとえば、`https://www.bing.com` と入力します。</span><span class="sxs-lookup"><span data-stu-id="95415-173">For example, enter `https://www.bing.com`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="95415-174">アドレス バーに完全な URL を入力してください。</span><span class="sxs-lookup"><span data-stu-id="95415-174">Ensure you enter complete URLs in the address bar.</span></span>  `ArgumentException` <span data-ttu-id="95415-175">URL がで始まるか、またはで始まる場合、例外が `http://` スローされます `https://` 。</span><span class="sxs-lookup"><span data-stu-id="95415-175">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-getting-started-bing.png" alt-text="bing.com" lightbox="./media/winui-getting-started-bing.png":::
       <span data-ttu-id="95415-177">bing.com</span><span class="sxs-lookup"><span data-stu-id="95415-177">bing.com</span></span>  
    :::image-end:::  
    
## <a name="step-4---navigation-events"></a><span data-ttu-id="95415-178">手順 4 - ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="95415-178">Step 4 - Navigation events</span></span>  

<span data-ttu-id="95415-179">WebView2 コントロールをホストするアプリは、Web ページ ナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="95415-179">Apps that host WebView2 controls listen for the following events that are raised by WebView2 controls during webpage navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  
    
> [!NOTE]
> <span data-ttu-id="95415-180">HTTP リダイレクトが発生した場合、1 行に複数の `NavigationStarting` イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="95415-180">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="95415-181">詳細については、[ナビゲーション イベント][Webviews2ConceptsNavigationEvents]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="95415-181">For more information, navigate to [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="95415-182">エラーが発生すると、次のイベントが発生し、エラー Web ページに移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="95415-182">When errors occur, the following events are raised and may navigate to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
    
<span data-ttu-id="95415-183">イベントを使用する方法の例として、HTTPS 以外の要求を取り消すハンドラー `NavigationStarting` を登録します。</span><span class="sxs-lookup"><span data-stu-id="95415-183">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any non-HTTPS requests.</span></span>  <span data-ttu-id="95415-184">で `MainWindow.xaml.cs` 、コンストラクターを変更して登録し、次のコード スニペットと一致する `EnsureHttps` `EnsureHttps` 関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="95415-184">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  

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

<span data-ttu-id="95415-185">プロジェクトをビルドして実行するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="95415-185">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="95415-186">HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95415-186">Ensure navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <a name="step-5---scripting"></a><span data-ttu-id="95415-187">手順 5 - スクリプト</span><span class="sxs-lookup"><span data-stu-id="95415-187">Step 5 - Scripting</span></span>  

<span data-ttu-id="95415-188">ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="95415-188">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="95415-189">任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。</span><span class="sxs-lookup"><span data-stu-id="95415-189">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="95415-190">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="95415-190">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="95415-191">挿入された JavaScript は、特定のタイミングで実行されます。</span><span class="sxs-lookup"><span data-stu-id="95415-191">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="95415-192">グローバル オブジェクトの作成後に実行します。</span><span class="sxs-lookup"><span data-stu-id="95415-192">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="95415-193">HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。</span><span class="sxs-lookup"><span data-stu-id="95415-193">Run it before any other script included in the HTML document is run.</span></span>  
    
<span data-ttu-id="95415-194">たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="95415-194">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="95415-195">`EnsureHttps` [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]を使用する Web コンテンツにスクリプトを挿入する関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="95415-195">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync].</span></span>  

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

<span data-ttu-id="95415-196">プロジェクトをビルドして実行するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="95415-196">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="95415-197">HTTPS 以外の Web サイトに移動すると、アプリに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95415-197">Ensure your app displays an alert when you navigate to any non-HTTPS websites.</span></span>  

:::image type="complex" source="./media/winui-getting-started-script.png" alt-text="WebView2 コントロールがアラート ダイアログを表示する" lightbox="./media/winui-getting-started-script.png":::
   <span data-ttu-id="95415-199">WebView2 コントロールがアラート ダイアログを表示する</span><span class="sxs-lookup"><span data-stu-id="95415-199">WebView2 control displays an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="95415-200">これで、最初の WebView2 アプリがビルドされました。</span><span class="sxs-lookup"><span data-stu-id="95415-200">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="95415-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="95415-201">Next steps</span></span>  

<span data-ttu-id="95415-202">WebView2 の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95415-202">To continue learning more about WebView2, navigate to the following resources.</span></span>  

*   <span data-ttu-id="95415-203">WebView2 アプリケーションの構築の詳細については [、「WebView2 開発のベスト プラクティス」に移動します][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="95415-203">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="95415-204">WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。</span><span class="sxs-lookup"><span data-stu-id="95415-204">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain].</span></span>  
*   <span data-ttu-id="95415-205">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="95415-205">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="95415-206">WebView2 API のリリースでは、WinRT CoreWebView2 オブジェクトを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="95415-206">The WinRT CoreWebView2 object may not be available with the release of the WebView2 API.</span></span>  <span data-ttu-id="95415-207">WebView2 コントロールで使用できる API を理解するには [、WebView2 Spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] に移動して、使用可能な API の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="95415-207">To understand which APIs are available to WebView2 controls, navigate to [WebView2 Spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span>  
    
*   <span data-ttu-id="95415-208">WebView2 API の詳細については [、WebView2 仕様に移動します][GithubMicrosoftMicrosoftUiXamlSpecsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="95415-208">For detailed information about the WebView2 API, navigate to [WebView2 spec][GithubMicrosoftMicrosoftUiXamlSpecsWebview2].</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="95415-209">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="95415-209">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<span data-ttu-id="95415-210">WinUI 固有の機能要求またはバグを送信するには、[問題 [- microsoft/microsoft-ui-xaml]][GithubMicrosoftMicrosoftUiXamlIssues] に移動し、[新しい問題] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95415-210">To send your WinUI-specific feature requests or bugs, navigate to [Issues - microsoft/microsoft-ui-xaml][GithubMicrosoftMicrosoftUiXamlIssues] and choose **New issue**.</span></span>  

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
