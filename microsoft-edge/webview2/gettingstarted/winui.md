---
description: WinUI アプリ用 WebView2 の概要ガイド
title: WinUI アプリの WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/20/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、winui apps、winui、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: a1ccffe332f71ee9d53ff267e8cca6bdbda81703
ms.sourcegitcommit: 02c602379537ab3b9d0a355cea7fcf96fdbd8870
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "11182722"
---
# <span data-ttu-id="a814c-104">WinUI 3 での WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a814c-104">Getting started with WebView2 in WinUI 3 (Preview)</span></span>  

<span data-ttu-id="a814c-105">この記事では、初めての WebView2 アプリを作成する方法と、 [Microsoft Edge WebView2 (Preview) の概要][Webview2Index]の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a814c-105">In this article, learn how to create your first WebView2 app and about the main features of [Introduction to Microsoft Edge WebView2 (Preview)][Webview2Index].</span></span>  <span data-ttu-id="a814c-106">初めての WebView2 アプリでは、WinUI3 が使われます。</span><span class="sxs-lookup"><span data-stu-id="a814c-106">Your first WebView2 app uses WinUI3.</span></span>  <span data-ttu-id="a814c-107">個々の Api について詳しくは、「 [api リファレンス][GithubMicrosoftUiXamlSpecsWebview2]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a814c-107">For more information on individual APIs, navigate to [API reference][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

## <span data-ttu-id="a814c-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="a814c-108">Prerequisites</span></span>  

<span data-ttu-id="a814c-109">次の記事を始める前に、次の前提条件の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="a814c-109">Ensure you install the following list of pre-requisites before proceeding with the following article.</span></span>  

1.  <span data-ttu-id="a814c-110">Windows 10 バージョン 1803 \ (ビルド 17134 \) 以降。</span><span class="sxs-lookup"><span data-stu-id="a814c-110">Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="a814c-111">詳細については、「 [Windows Update: よく寄せ][MicrosoftSupport12373]られる質問 (FAQ)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-111">For more information, navigate to [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
1.  <span data-ttu-id="a814c-112">[Microsoft Edge (Chromium) カナリア Channel][MicrosoftedgeinsiderDownload] windows 10、windows 8.1、または windows 7。</span><span class="sxs-lookup"><span data-stu-id="a814c-112">[Microsoft Edge (Chromium) Canary channel][MicrosoftedgeinsiderDownload] on Windows 10, Windows 8.1, or Windows 7.</span></span>  
1.  <span data-ttu-id="a814c-113">Visual Studio 2019、バージョン 16.9 Preview。</span><span class="sxs-lookup"><span data-stu-id="a814c-113">Visual Studio 2019, version 16.9 Preview.</span></span>  <span data-ttu-id="a814c-114">詳細については、「 [WINDOWS UI ライブラリ3プレビュー 3][WindowsAppsWinui3ConfigureYourDevEnvironment]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-114">For more information, navigate to [Windows UI Library 3 Preview 3][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
    
    <span data-ttu-id="a814c-115">Visual Studio をインストールする場合は、次のワークロードを含めます。</span><span class="sxs-lookup"><span data-stu-id="a814c-115">Include the following workloads when you install Visual Studio.</span></span>  
    
    *   <span data-ttu-id="a814c-116">.NET デスクトップ開発 \ (インストーラーでも .NET 5 がインストールされます)</span><span class="sxs-lookup"><span data-stu-id="a814c-116">.NET Desktop Development \(the installer also installs .NET 5\)</span></span>  
    *   <span data-ttu-id="a814c-117">ユニバーサル Windows プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="a814c-117">Universal Windows Platform development</span></span>  
        
    <span data-ttu-id="a814c-118">C++ アプリをビルドするには、次のワークロードも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a814c-118">To build C++ apps, you must also include the following workloads.</span></span>  
    
    *   <span data-ttu-id="a814c-119">C++ でのデスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="a814c-119">Desktop development with C++</span></span>  
    *   <span data-ttu-id="a814c-120">ユニバーサル Windows プラットフォームのワークロードの C++ (v142) ユニバーサル Windows プラットフォームツールのオプションコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a814c-120">The C++ (v142) Universal Windows Platform tools optional component for the Universal Windows Platform workload.</span></span>  <span data-ttu-id="a814c-121">詳細については、右側のウィンドウで [ユニバーサル Windows プラットフォーム開発] セクションの [インストールの詳細] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-121">For more information,  navigate to Installation Details under the Universal Windows Platform development section, on the right pane.</span></span>  
        
1.  <span data-ttu-id="a814c-122">[Nuget.org][NugetHome]に対して有効になっている NuGet パッケージソースがシステムにあることを確認します。 詳細については、「[共通の NuGet 構成][NugetConsumePackagesConfiguringNugetBehavior]と[Windows コミュニティツールキット][WindowsCommunitytoolkit]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-122">Make sure your system has a NuGet package source enabled for [nuget.org][NugetHome].  For more information, navigate to [Common NuGet configurations][NugetConsumePackagesConfiguringNugetBehavior] and [Windows Community Toolkit][WindowsCommunitytoolkit].</span></span>  
1.  <span data-ttu-id="a814c-123">[WinUI 3 Preview 3 VSIX パッケージ][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="a814c-123">Download and install the [WinUI 3 Preview 3 VSIX package][VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates].</span></span>  <span data-ttu-id="a814c-124">インストーラーは、winui 3 プロジェクトテンプレートと、WinUI 3 ライブラリを含む NuGet パッケージを Visual Studio 2019 に追加します。</span><span class="sxs-lookup"><span data-stu-id="a814c-124">The installer adds both the WinUI 3 project templates and the NuGet package containing the WinUI 3 libraries to Visual Studio 2019.</span></span>  
    
    <span data-ttu-id="a814c-125">VSIX パッケージを Visual Studio に追加する方法については、「 [Visual Studio 拡張機能の検索と使用][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-125">For instructions on how to add the VSIX package to Visual Studio, navigate to [Finding and Using Visual Studio Extensions][VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox].</span></span>
    
1.  <span data-ttu-id="a814c-126">開発 [者モード][WindowsUwpGetStartedEnableYourDeviceForDevelopment] を有効にして、開発者固有の Visual Studio のすべての機能に確実にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a814c-126">Enable [Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment] to ensure you have access to all developer-specific Visual Studio features.</span></span>  
    
## <span data-ttu-id="a814c-127">手順 1-プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a814c-127">Step 1 - Create Project</span></span>  

<span data-ttu-id="a814c-128">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="a814c-128">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="a814c-129">Visual Studio で、[ **新しいプロジェクトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-129">In Visual Studio, choose **Create a new project**.</span></span>  
1.  <span data-ttu-id="a814c-130">[プロジェクト] ドロップダウンで、[ **C#**]、[ **Windows**]、[ **WinUI** ] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-130">In the project drop-down, choose **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="Visual Studio を使って新しい WinUI プロジェクトを作成する" lightbox="./media/winui-gettingstarted-selections.png":::
        <span data-ttu-id="a814c-132">Visual Studio を使って新しい WinUI プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a814c-132">Create a new WinUI project using Visual Studio</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="a814c-133">[ **空のアプリ]、[パッケージ] (デスクトップの WinUI)** の順に選び、[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a814c-133">Choose **Blank App, Packaged (WinUI in Desktop)**, and then choose **Next**.</span></span>  
1.  <span data-ttu-id="a814c-134">プロジェクト名を入力し、必要に応じてその他のオプションを選択して、[ **作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-134">Enter a project name, choose other options as needed, and then choose **Create**.</span></span>  
1.  <span data-ttu-id="a814c-135">**新しいユニバーサル Windows プラットフォームプロジェクト**で、次の値を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-135">In **New Universal Windows Platform Project**, choose the following values, and then choose **OK**.</span></span>  
    *   <span data-ttu-id="a814c-136">**ターゲットバージョン**:  **Windows 10、バージョン 1903 (ビルド 18362)** 以降</span><span class="sxs-lookup"><span data-stu-id="a814c-136">**Target version**:  **Windows 10, version 1903 (build 18362)** or later</span></span>  
    *   <span data-ttu-id="a814c-137">**最小バージョン**:  **Windows 10、バージョン 1803 (ビルド 17134)**</span><span class="sxs-lookup"><span data-stu-id="a814c-137">**Minimum version**:  **Windows 10, version 1803 (build 17134)**</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="[ターゲットバージョン] と [最小バージョン] の値が選択された新しいユニバーサル Windows プラットフォームプロジェクトダイアログ。" lightbox="./media/winui-gettingstarted-projecttype.png":::
       <span data-ttu-id="a814c-139">[ターゲットバージョン] と [最小バージョン] の値が選択された新しいユニバーサル Windows プラットフォームプロジェクトダイアログ。</span><span class="sxs-lookup"><span data-stu-id="a814c-139">The New Universal Windows Platform Project dialog with chosen values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="a814c-140">ソリューションエクスプローラーで、2つのプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a814c-140">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="a814c-141">**プロジェクト名 (デスクトップ)**</span><span class="sxs-lookup"><span data-stu-id="a814c-141">**Your project name (Desktop)**.</span></span>  <span data-ttu-id="a814c-142">このプロジェクトには、アプリのコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a814c-142">This project contains the code for your app.</span></span>  <span data-ttu-id="a814c-143">**App.xaml.cs** は、 `Application` アプリインスタンスを表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="a814c-143">**App.xaml.cs** defines an `Application` class that represents your app instance.</span></span>  <span data-ttu-id="a814c-144">**MainWindow.xaml.cs** は、 `MainWindow` アプリインスタンスによって表示されるメインウィンドウを表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="a814c-144">**MainWindow.xaml.cs** defines a `MainWindow` class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="a814c-145">これらのクラスは、 `Microsoft.UI.Xaml` WinUI の名前空間の型から派生します。</span><span class="sxs-lookup"><span data-stu-id="a814c-145">These classes derive from types in the `Microsoft.UI.Xaml` namespace of WinUI.</span></span>  
    
    *   <span data-ttu-id="a814c-146">**プロジェクト名 (パッケージ)**。</span><span class="sxs-lookup"><span data-stu-id="a814c-146">**Your project name (Package)**.</span></span>  <span data-ttu-id="a814c-147">このプロジェクトは、アプリを展開用の MSIX パッケージにビルドするように構成された Windows アプリケーションパッケージプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a814c-147">This project is a Windows Application Packaging Project that is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="a814c-148">プロジェクトには、アプリのパッケージマニフェストが含まれており、既定では、ソリューションのスタートアッププロジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="a814c-148">The project contains the package manifest for your app, and it is the startup project for your solution by default.</span></span>  <span data-ttu-id="a814c-149">詳細については、「 [Windows 10 のパッケージマニフェストスキーマリファレンス][UwpSchemasAppxpackageUapmanifestRoot]」の「 [msix パッケージ用にデスクトップアプリケーションをセットアップする」][WindowsMsixDesktopToUwpPackagingDotNet]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-149">For more information, navigate to [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>
    
1.  <span data-ttu-id="a814c-150">ソリューションエクスプローラーで、コードを表示するには、[ファイル] を開き `MainWindow.xaml` ます。</span><span class="sxs-lookup"><span data-stu-id="a814c-150">In the Solution Explorer, to display the code, open `MainWindow.xaml` file.</span></span>  <span data-ttu-id="a814c-151">プロジェクトを実行し、 `F5` ボタンを含むウィンドウを表示するには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-151">Select `F5` to run your project and show a window with a button.</span></span>  
    
## <span data-ttu-id="a814c-152">手順 2-WebView2 コントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="a814c-152">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="a814c-153">次に、WebView2 コントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a814c-153">Next add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="a814c-154">[開く] `MainWindow.xaml` を選びます。</span><span class="sxs-lookup"><span data-stu-id="a814c-154">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="a814c-155">タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。</span><span class="sxs-lookup"><span data-stu-id="a814c-155">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="a814c-156">次のコードスニペットのように、コードが次のようになっていることを確認 `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="a814c-156">Confirm that your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="a814c-157">WebView2 コントロールを追加するには、 `<StackPanel>` 次のコードスニペットでタグを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a814c-157">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="a814c-158">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="a814c-158">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
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
    
1.  <span data-ttu-id="a814c-159">`MainWindow.xaml.cs`次の行を開いてコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="a814c-159">Open `MainWindow.xaml.cs` and comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="a814c-160">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-160">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="a814c-161">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com][|::ref1::|Main] します。</span><span class="sxs-lookup"><span data-stu-id="a814c-161">Confirm that your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="Microsoft.com サイトを表示する WebView2 コントロール" lightbox="./media/winui-gettingstarted-part3.png":::
       <span data-ttu-id="a814c-163">Microsoft.com サイトを表示する WebView2 コントロール。</span><span class="sxs-lookup"><span data-stu-id="a814c-163">A WebView2 control displaying the microsoft.com site.</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a814c-164">手順 3-ナビゲーションコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a814c-164">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="a814c-165">WebView2 コントロールに表示される web ページをアプリに追加することにより、ユーザーがそのページをコントロールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a814c-165">Allow users to control the web page that is displayed in your WebView2 control by adding an address bar to your app.</span></span>  

1.  <span data-ttu-id="a814c-166">で `MainWindow.xaml` 、次のコードスニペットを、要素を含む要素内にコピーして貼り付け `Grid` `WebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="a814c-166">In `MainWindow.xaml`, copy and paste the following code snippet inside the `Grid` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="a814c-167">要素が次のコードスニペットのようになっていることを確認 `Grid` `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="a814c-167">Confirm that your `Grid` element of `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="a814c-168">で、 `MainWindow.xaml.cs` 次のコードスニペットをコピーして `myButton_Click` 、WebView2 コントロールをアドレスバーに入力した URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="a814c-168">In `MainWindow.xaml.cs`, copy the following code snippet to `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
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
    
    <span data-ttu-id="a814c-169">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-169">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="a814c-170">アドレスバーに新しい URL を入力して、[ **Go**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a814c-170">Enter a new URL in the address bar, and then choose **Go**.</span></span>  <span data-ttu-id="a814c-171">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="a814c-171">For example, enter `https://www.bing.com`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a814c-172">アドレスバーに完全な Url を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a814c-172">Ensure you use complete URLs in the address bar.</span></span>  `ArgumentException` <span data-ttu-id="a814c-173">URL が、またはで始まらない場合は、例外がスローされ `http://` `https://` ます。</span><span class="sxs-lookup"><span data-stu-id="a814c-173">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="Bing.com" lightbox="./media/winui-gettingstarted-bing.png":::
       <span data-ttu-id="a814c-175">Bing.com</span><span class="sxs-lookup"><span data-stu-id="a814c-175">Bing.com</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a814c-176">ステップ 4-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="a814c-176">Step 4 - Navigation events</span></span>  

<span data-ttu-id="a814c-177">WebView2 コントロールをホストするアプリケーションは、web ページのナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="a814c-177">Applications that host WebView2 controls listen for the following events that are raised by WebView2 controls during web page navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> <span data-ttu-id="a814c-178">HTTP のリダイレクトでは `NavigationStarting` 、複数のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="a814c-178">HTTP redirects raise multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="a814c-179">詳細については、「 [ナビゲーションイベント][Webviews2ConceptsNavigationEvents]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-179">For more information, navigate to [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="a814c-180">エラーが発生すると、次のイベントが発生し、エラーページに移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a814c-180">When errors occur, the following events are raised and may navigate to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
<span data-ttu-id="a814c-181">イベントの使い方の例として、 `NavigationStarting` HTTPS を使わない要求をキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="a814c-181">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any request that does not use HTTPS.</span></span>  <span data-ttu-id="a814c-182">で `MainWindow.xaml.cs` 、登録するコンストラクターを変更 `EnsureHttps` し、 `EnsureHttps` 次のコードスニペットと一致するように関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="a814c-182">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  

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

<span data-ttu-id="a814c-183">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-183">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="a814c-184">HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a814c-184">Confirm that navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <span data-ttu-id="a814c-185">手順 5-スクリプト</span><span class="sxs-lookup"><span data-stu-id="a814c-185">Step 5 - Scripting</span></span>  

<span data-ttu-id="a814c-186">ホストアプリケーションは、実行時に WebView2 コントロールに JavaScript コードを挿入することがあります。</span><span class="sxs-lookup"><span data-stu-id="a814c-186">Host applications may inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="a814c-187">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベルドキュメントと任意の子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a814c-187">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="a814c-188">挿入された JavaScript は、特定のタイミングで実行されます。</span><span class="sxs-lookup"><span data-stu-id="a814c-188">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="a814c-189">グローバルオブジェクトの作成後に実行します。</span><span class="sxs-lookup"><span data-stu-id="a814c-189">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="a814c-190">HTML ドキュメントに含まれている他のスクリプトが実行される前に実行します。</span><span class="sxs-lookup"><span data-stu-id="a814c-190">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="a814c-191">例として、ユーザーが HTTPS 以外のサイトに移動したときにアラートが送信されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a814c-191">As an example, add scripts send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="a814c-192">`EnsureHttps` [Executesサブスクリプション][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]を使っている web コンテンツにスクリプトを挿入するように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="a814c-192">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync].</span></span>  

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

<span data-ttu-id="a814c-193">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a814c-193">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="a814c-194">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a814c-194">Confirm that your application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="通知ダイアログを表示する WebView2 コントロール" lightbox="./media/winui-gettingstarted-script.png":::
   <span data-ttu-id="a814c-196">通知ダイアログを表示する WebView2 コントロール</span><span class="sxs-lookup"><span data-stu-id="a814c-196">WebView2 control showing an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="a814c-197">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a814c-197">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="a814c-198">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a814c-198">Next Steps</span></span>  

<span data-ttu-id="a814c-199">現在、チームは WebView2 の Api を構築しています。</span><span class="sxs-lookup"><span data-stu-id="a814c-199">Our team is currently building more WebView2 APIs.</span></span>  <span data-ttu-id="a814c-200">WebView2 Api の現在の状態について詳しくは、 [WebView2 仕様][GithubMicrosoftUiXamlSpecsWebview2]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-200">For more information on the current state of WebView2 APIs, navigate to the [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

> [!NOTE]
> <span data-ttu-id="a814c-201">WebView2 Api が出荷されている時点で、WinRT CoreWebView2 オブジェクトが利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a814c-201">The WinRT CoreWebView2 object may not be available at the time the WebView2 APIs ship.</span></span>  <span data-ttu-id="a814c-202">WebView2 コントロールで利用できる Api を理解するには、[ [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] ] に移動して、利用可能な api の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a814c-202">To understand which APIs are available to WebView2 controls, navigate to [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span>  

<span data-ttu-id="a814c-203">WebView2 機能の詳細については、 [WebView2 の概念と How-To ガイド][Webview2IndexNextSteps] 、 [WebView2 サンプルのリポジトリ][GithubMicrosoftedgeWebview2samplesMain]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="a814c-203">For more information about WebView2 capabilities, navigate to [WebView2 Concepts and How-To guides][Webview2IndexNextSteps] and the [WebView2 samples repo][GithubMicrosoftedgeWebview2samplesMain].</span></span>  

## <span data-ttu-id="a814c-204">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="a814c-204">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webviews2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーションイベント |Microsoft ドキュメント"  
[Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.Exe(文字列) メソッド (WebView2) | cuteScriptAsync) |Microsoft ドキュメント"  

[NugetConsumePackagesConfiguringNugetBehavior]: /nuget/consume-packages/configuring-nuget-behavior "一般的な NuGet 構成 |Microsoft ドキュメント"  

[UwpSchemasAppxpackageUapmanifestRoot]: /uwp/schemas/appxpackage/uapmanifestschema/schema-root "Windows 10 のパッケージマニフェストスキーマリファレンス |Microsoft ドキュメント"  

[VisualstudioIdeFindingUsingVisualStudioExtensionsInstallWithoutUsing-ManageExtensionsDialogBox]: /visualstudio/ide/finding-and-using-visual-studio-extensions#install-without-using-the-manage-extensions-dialog-box "[拡張機能の管理] ダイアログボックスを使用せずにインストールする-Visual Studio の拡張機能を管理する |Microsoft ドキュメント"  

[WindowsAppsWinui3ConfigureYourDevEnvironment]: /windows/apps/winui/winui3#configure-your-dev-environment "開発環境の構成-Windows UI Library 3.0 Preview 1 (2020 年5月) |Microsoft ドキュメント"  
[WindowsCommunitytoolkit]: /windows/communitytoolkit "Windows コミュニティツールキットドキュメント |Microsoft ドキュメント"  
[WindowsMsixDesktopToUwpPackagingDotNet]: /windows/msix/desktop/desktop-to-uwp-packaging-dot-net "Visual Studio の MSIX パッケージ用にデスクトップアプリケーションをセットアップする |Microsoft ドキュメント"  
[WindowsUwpGetStartedEnableYourDeviceForDevelopment]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効にする |Microsoft ドキュメント"  

[GithubMicrosoftUiXamlSpecsWebview2]: https://github.com/microsoft/microsoft-ui-xaml-specs/blob/master/active/WebView2/WebView2_spec.md "WebView2 spec-microsoft/microsoft-ui-xaml-定義 |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftMain]: https://www.microsoft.com "Publisher"  

[MicrosoftSupport12373]: https://support.microsoft.com/help/12373 "Windows Update: よく寄せられる質問 (FAQ)"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetHome]: https://nuget.org "ホーム |NuGet ギャラリー"  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exe "dotnet-sdk-5.0.100-preview.4.20268.1-win-x86.exeをダウンロードする "  

[WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]: https://dotnetcli.blob.core.windows.net/dotnet/Sdk/5.0.100-preview.4.20268.1/dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe " dotnet-sdk-5.0.100-preview.4.20268.1-win-x64.exe"  

[VisualstudioMarketplaceMicrosoftWinuiWinuiprojecttemplates]: https://marketplace.visualstudio.com/items?itemName=Microsoft-WinUI.WinUIProjectTemplates "WinUI 3 プロジェクトテンプレート |Visual Studio Marketplace"  
