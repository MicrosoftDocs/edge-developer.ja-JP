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
# <span data-ttu-id="c0e14-104">WinUI3 での WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c0e14-104">Getting started with WebView2 in WinUI3 (Preview)</span></span>  

<span data-ttu-id="c0e14-105">この記事では、WinUI3 で初めて WebView2 アプリを作成する方法について説明します。 [Microsoft Edge WebView2 (Preview) の概要][Webview2Index]の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-105">In this article, get started creating your first WebView2 app with WinUI3 and learn about the main features of [Introduction to Microsoft Edge WebView2 (Preview)][Webview2Index].</span></span>  <span data-ttu-id="c0e14-106">個々の Api について詳しくは、 [api リファレンス][GithubMicrosoftUiXamlSpecsWebview2]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-106">For more information on individual APIs, see [API reference][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

## <span data-ttu-id="c0e14-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c0e14-107">Prerequisites</span></span>  

<span data-ttu-id="c0e14-108">次の記事を始める前に、次の前提条件の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-108">Ensure you install the following list of pre-requisites before proceeding with the following article.</span></span>  

*   <span data-ttu-id="c0e14-109">Windows 10 バージョン 1803 \ (ビルド 17134 \) 以降。</span><span class="sxs-lookup"><span data-stu-id="c0e14-109">Windows 10 version 1803 \(build 17134\) or later.</span></span>  <span data-ttu-id="c0e14-110">詳細については、「 [Windows Update: FAQ][MicrosoftSupport12373]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-110">For more information, see [Windows Update: FAQ][MicrosoftSupport12373].</span></span>  
*   <span data-ttu-id="c0e14-111">[Microsoft Edge (Chromium) カナリア Channel][MicrosoftedgeinsiderDownload] windows 10、windows 8.1、または windows 7。</span><span class="sxs-lookup"><span data-stu-id="c0e14-111">[Microsoft Edge (Chromium) Canary channel][MicrosoftedgeinsiderDownload] on Windows 10, Windows 8.1, or Windows 7.</span></span>  
*   <span data-ttu-id="c0e14-112">Visual Studio 2019、バージョン 16.7 Preview 1。</span><span class="sxs-lookup"><span data-stu-id="c0e14-112">Visual Studio 2019, version 16.7 Preview 1.</span></span>  <span data-ttu-id="c0e14-113">詳細については、 [WINDOWS UI ライブラリ3プレビュー 2 (2020 年7月)][WindowsAppsWinui3ConfigureYourDevEnvironment]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-113">For more information, see [Windows UI Library 3 Preview 2 (July 2020)][WindowsAppsWinui3ConfigureYourDevEnvironment].</span></span>  
*   <span data-ttu-id="c0e14-114">[X64][WindowsDotnetcliBlobCoreSdk50100Preview4202681X64]と[x86][WindowsDotnetcliBlobCoreSdk50100Preview4202681X86]の両方のバージョンの .net 5 Preview 4。</span><span class="sxs-lookup"><span data-stu-id="c0e14-114">Both the [x64][WindowsDotnetcliBlobCoreSdk50100Preview4202681X64] and [x86][WindowsDotnetcliBlobCoreSdk50100Preview4202681X86] versions of .NET 5 Preview 4.</span></span>  
*   <span data-ttu-id="c0e14-115">[WinUI 3][VisualstudioMarketplaceWinUiprojecttemplates] Visual Studio 2019 用のプロジェクトテンプレートの拡張機能</span><span class="sxs-lookup"><span data-stu-id="c0e14-115">[WinUI 3 Project Templates][VisualstudioMarketplaceWinUiprojecttemplates] extension for Visual Studio 2019.</span></span>  
<span data-ttu-id="c0e14-116">すべての Visual Studio 機能に確実にアクセスできるように、 [開発者モードを有効][WindowsUwpGetStartedEnableYourDeviceForDevelopment] にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-116">Ensure you [Enable Developer Mode][WindowsUwpGetStartedEnableYourDeviceForDevelopment] to ensure you have access to all Visual Studio features.</span></span>  

## <span data-ttu-id="c0e14-117">手順 1-プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c0e14-117">Step 1 - Create Project</span></span>  

<span data-ttu-id="c0e14-118">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-118">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="c0e14-119">Visual Studio で、[ **新しいプロジェクトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-119">In Visual Studio, select **Create a new project**.</span></span>  
1.  <span data-ttu-id="c0e14-120">[プロジェクト] ドロップダウンで、[ **C#**]、[ **Windows**]、[ **WinUI** ] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-120">In the project drop-down, select **C#**, **Windows**, and **WinUI** respectively.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-selections.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-selections.png":::
       <span data-ttu-id="c0e14-122">WinUI の Visual studio プロジェクト作成ダイアログ</span><span class="sxs-lookup"><span data-stu-id="c0e14-122">Visual studio project creation dialog for WinUI</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c0e14-123">[ **空のアプリ]、[パッケージ] (デスクトップの WinUI)** の順に選び、[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-123">Choose **Blank App, Packaged (WinUI in Desktop)**, and then choose **Next**.</span></span>  
1.  <span data-ttu-id="c0e14-124">プロジェクト名を入力し、必要に応じてその他のオプションを選択して、[ **作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-124">Enter a project name, choose other options as needed, and then select **Create**.</span></span>  
1.  <span data-ttu-id="c0e14-125">**新しいユニバーサル Windows プラットフォームプロジェクト**で、次の値を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-125">In **New Universal Windows Platform Project**, select the following values, and then choose **OK**:</span></span>  
    *   <span data-ttu-id="c0e14-126">ターゲットバージョン: **Windows 10、バージョン 1903 (ビルド 18362)** 以降。</span><span class="sxs-lookup"><span data-stu-id="c0e14-126">Target version: **Windows 10, version 1903 (build 18362)** or later.</span></span>  
    *   <span data-ttu-id="c0e14-127">最小バージョン: **Windows 10、バージョン 1803 (ビルド 17134)**。</span><span class="sxs-lookup"><span data-stu-id="c0e14-127">Minimum version: **Windows 10, version 1803 (build 17134)**.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-projecttype.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-projecttype.png":::
       <span data-ttu-id="c0e14-129">[ターゲットバージョン] と [最小バージョン] の値が選択された新しいユニバーサル Windows プラットフォームプロジェクトダイアログ。</span><span class="sxs-lookup"><span data-stu-id="c0e14-129">The New Universal Windows Platform Project dialog with selected values for Target version and Minimum version.</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="c0e14-130">ソリューションエクスプローラーで、2つのプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-130">In the Solution Explorer, two projects are generated.</span></span>  
    *   <span data-ttu-id="c0e14-131">**プロジェクト名 (デスクトップ)**</span><span class="sxs-lookup"><span data-stu-id="c0e14-131">**Your project name(Desktop)**.</span></span> <span data-ttu-id="c0e14-132">このプロジェクトには、アプリのコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0e14-132">This project contains the code for your app.</span></span>  <span data-ttu-id="c0e14-133">**App.xaml.cs** は、 `Application` アプリインスタンスを表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-133">**App.xaml.cs** defines an`Application`class that represents your app instance.</span></span> <span data-ttu-id="c0e14-134">**MainWindow.xaml.cs** は、 `MainWindow` アプリインスタンスによって表示されるメインウィンドウを表すクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-134">**MainWindow.xaml.cs** defines a`MainWindow`class that represents the main window displayed by your app instance.</span></span>  <span data-ttu-id="c0e14-135">これらのクラスは、 `Microsoft.UI.Xaml` WinUI の名前空間の型から派生します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-135">These classes derive from types in the`Microsoft.UI.Xaml`namespace of WinUI.</span></span>  
    
    *   <span data-ttu-id="c0e14-136">**プロジェクト名 (パッケージ)**。</span><span class="sxs-lookup"><span data-stu-id="c0e14-136">**Your project name(Package)**.</span></span>  <span data-ttu-id="c0e14-137">このプロジェクトは、アプリを展開用の MSIX パッケージにビルドするように構成されている、Windows アプリケーションパッケージプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c0e14-137">This project is aWindows Application Packaging Projectthat is configured to build the app into an MSIX package for deployment.</span></span>  <span data-ttu-id="c0e14-138">プロジェクトには、アプリの thepackage manifestfor 含まれており、既定では、ソリューションのスタートアッププロジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="c0e14-138">The project contains thepackage manifestfor your app, and it is the startup project for your solution by default.</span></span> <span data-ttu-id="c0e14-139">詳細については、「 [Windows 10 のパッケージマニフェストスキーマリファレンス][UwpSchemasAppxpackageUapmanifestRoot]」の「 [msix パッケージ用にデスクトップアプリケーションをセットアップ][WindowsMsixDesktopToUwpPackagingDotNet]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-139">For more information, see [Set up your desktop application for MSIX packaging in Visual Studio][WindowsMsixDesktopToUwpPackagingDotNet] and [Package manifest schema reference for Windows 10][UwpSchemasAppxpackageUapmanifestRoot].</span></span>
    
1.  <span data-ttu-id="c0e14-140">ソリューションエクスプローラーで **MainWindow** を開いて、コードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-140">In the Solution Explorer, open **MainWindow.xaml** to display the code.</span></span>  <span data-ttu-id="c0e14-141">プロジェクトを実行し、 `F5` ボタンを含むウィンドウを表示するには、を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-141">Select `F5` to run your project and show a window with a button.</span></span>  
    
## <span data-ttu-id="c0e14-142">手順 2-WebView2 コントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="c0e14-142">Step 2 - Add a WebView2 control to your project</span></span>  

<span data-ttu-id="c0e14-143">次に、WebView2 コントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-143">Next add a WebView2 control to your project.</span></span>  

1.  <span data-ttu-id="c0e14-144">[開く] `MainWindow.xaml` を選びます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-144">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="c0e14-145">タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-145">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:controls="using:Microsoft.UI.Xaml.Controls"
    ```  
    
    <span data-ttu-id="c0e14-146">次のコードスニペットのように、コードが次のようになっていることを確認 `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-146">Confirm that your code in `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="c0e14-147">WebView2 コントロールを追加するには、 `<StackPanel>` 次のコードスニペットでタグを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-147">To add the WebView2 control, replace the `<StackPanel>` tags with the following code snippet.</span></span>  <span data-ttu-id="c0e14-148">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
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
    
1.  <span data-ttu-id="c0e14-149">`MainWindow.xaml.cs`次の行を開いてコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="c0e14-149">Open `MainWindow.xaml.cs` and comment out the following line.</span></span>
    
    ```xml
        // myButton.Content = "Clicked";     
    ```  
    
1.  <span data-ttu-id="c0e14-150">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-150">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="c0e14-151">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com][|::ref1::|Main] します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-151">Confirm that your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-part3.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-part3.png":::
       <span data-ttu-id="c0e14-153">Microsoft.com サイトを表示する WebView2 コントロール。</span><span class="sxs-lookup"><span data-stu-id="c0e14-153">A WebView2 control displaying the microsoft.com site.</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c0e14-154">手順 3-ナビゲーションコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="c0e14-154">Step 3 - Add navigation controls</span></span>  

<span data-ttu-id="c0e14-155">WebView2 コントロールに表示される web ページをアプリに追加することにより、ユーザーがそのページをコントロールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c0e14-155">Allow users to control the web page that is displayed in your WebView2 control by adding an address bar to your app.</span></span> 

1.  <span data-ttu-id="c0e14-156">**MainWindow**で、次のコードスニペットを、要素を含む要素内にコピーして貼り付け `Grid` `WebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-156">In **MainWindow.xaml**, copy and paste the following code snippet inside the `Grid` element that contains the `WebView2` element.</span></span>  
    
    ```xml
        <TextBox Name="addressBar" Grid.Column="0"/>
        <Button x:Name="myButton" Grid.Column="1" Click="myButton_Click">Go</Button>
    ```  
    
    <span data-ttu-id="c0e14-157">要素が次のコードスニペットのようになっていることを確認 `Grid` `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-157">Confirm that your `Grid` element of `MainWindow.xaml` is similar to the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="c0e14-158">**MainWindow.xaml.cs**で、次のコードスニペットをコピーして `myButton_Click` 、WebView2 コントロールをアドレスバーに入力した URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-158">In **MainWindow.xaml.cs**, copy the following code snippet to `myButton_Click`, which navigates the WebView2 control to the URL entered in the address bar.</span></span>  
    
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
    
    <span data-ttu-id="c0e14-159">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-159">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="c0e14-160">アドレスバーに新しい URL を入力し、[ **移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-160">Enter a new URL in the address bar, and then select **Go**.</span></span>  <span data-ttu-id="c0e14-161">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-161">For example, enter `https://www.bing.com`.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c0e14-162">アドレスバーに完全な Url を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-162">Ensure you use complete URLs in the address bar.</span></span> `ArgumentException` <span data-ttu-id="c0e14-163">URL が、またはで始まらない場合は、例外がスローされ `http://` `https://` ます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-163">exceptions are thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/winui-gettingstarted-bing.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-bing.png":::
       <span data-ttu-id="c0e14-165">Bing.com</span><span class="sxs-lookup"><span data-stu-id="c0e14-165">Bing.com</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c0e14-166">ステップ 4-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="c0e14-166">Step 4 - Navigation events</span></span>  

<span data-ttu-id="c0e14-167">WebView2 コントロールをホストするアプリケーションは、web ページのナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="c0e14-167">Applications that host WebView2 controls listen for the following events that are raised by WebView2 controls during web page navigation.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

> [!NOTE]
> <span data-ttu-id="c0e14-168">HTTP のリダイレクトでは `NavigationStarting` 、複数のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-168">HTTP redirects raise multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="c0e14-169">詳細については、「 [ナビゲーションイベント][Webviews2ConceptsNavigationEvents]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-169">For more information, see [Navigation Events][Webviews2ConceptsNavigationEvents].</span></span>  

<span data-ttu-id="c0e14-170">エラーが発生すると、次のイベントが発生し、エラーページに移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0e14-170">When errors occur, the following events are raised and may navigate to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
     
<span data-ttu-id="c0e14-171">イベントの使い方の例として、 `NavigationStarting` HTTPS を使っていない要求をすべてキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-171">As an example of how to use the events, register a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span> <span data-ttu-id="c0e14-172">で `MainWindow.xaml.cs` 、登録するコンストラクターを変更 `EnsureHttps` し、 `EnsureHttps` 次のコードスニペットと一致するように関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-172">In `MainWindow.xaml.cs`, modify the constructor to register `EnsureHttps`, and add the `EnsureHttps` function so that it matches the following code snippet.</span></span>  

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

<span data-ttu-id="c0e14-173">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-173">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="c0e14-174">HTTP サイトへのナビゲーションがブロックされ、HTTPS サイトで許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-174">Confirm that navigation is blocked to HTTP sites, and allowed for HTTPS sites.</span></span>  

## <span data-ttu-id="c0e14-175">手順 5-スクリプト</span><span class="sxs-lookup"><span data-stu-id="c0e14-175">Step 5 - Scripting</span></span>  

<span data-ttu-id="c0e14-176">ホストアプリケーションは、実行時に WebView2 コントロールに JavaScript コードを挿入することがあります。</span><span class="sxs-lookup"><span data-stu-id="c0e14-176">Host applications may inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="c0e14-177">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しい最上位レベルのドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-177">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="c0e14-178">挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c0e14-178">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="c0e14-179">例として、ユーザーが HTTPS 以外のサイトに移動したときにアラートが送信されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c0e14-179">As an example, add scripts send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="c0e14-180">この関数を変更し `EnsureHttps` て、 [executesを][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync]使って web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-180">Modify the `EnsureHttps` function to inject a script into the web content using [ExecuteScriptAsync][Webviews2ReferenceWpfMicrosoftWebExecutescriptasync].</span></span>  

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

<span data-ttu-id="c0e14-181">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-181">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="c0e14-182">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0e14-182">Confirm that your application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/winui-gettingstarted-script.png" alt-text="WinUI の Visual studio プロジェクト作成ダイアログ" lightbox="./media/winui-gettingstarted-script.png":::
   <span data-ttu-id="c0e14-184">通知ダイアログを表示する WebView2 コントロール</span><span class="sxs-lookup"><span data-stu-id="c0e14-184">WebView2 control showing an alert dialog</span></span>
:::image-end:::  

<span data-ttu-id="c0e14-185">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="c0e14-185">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="c0e14-186">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c0e14-186">Next Steps</span></span>  

<span data-ttu-id="c0e14-187">現在、チームは WebView2 の Api を構築しています。</span><span class="sxs-lookup"><span data-stu-id="c0e14-187">Our team is currently building more WebView2 APIs.</span></span>  <span data-ttu-id="c0e14-188">WebView2 Api の現在の状態について詳しくは、「 [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-188">For more information on the current state of WebView2 APIs, see the [WebView2 spec][GithubMicrosoftUiXamlSpecsWebview2].</span></span>  

> [!NOTE]
> <span data-ttu-id="c0e14-189">WebView2 Api が出荷されている時点で、WinRT CoreWebView2 オブジェクトが利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0e14-189">The WinRT CoreWebView2 object may not be available at the time the WebView2 APIs ship.</span></span> <span data-ttu-id="c0e14-190">WebView2 コントロールで利用できる Api を理解するには、利用可能な Api の一覧については、 [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-190">To understand which APIs are available to WebView2 controls, see [WebView2 Spec][GithubMicrosoftUiXamlSpecsWebview2] for a list of the APIs that are available.</span></span> 

<span data-ttu-id="c0e14-191">WebView2 機能の詳細については、「 [WebView2 の概念と How-To ガイド][Webview2IndexNextSteps]」および [WebView2 サンプルのリポジトリ][GithubMicrosoftedgeWebview2samplesMain]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e14-191">For more information about WebView2 capabilities, see [WebView2 Concepts and How-To guides][Webview2IndexNextSteps], and the [WebView2 samples repo][GithubMicrosoftedgeWebview2samplesMain].</span></span>  

## <span data-ttu-id="c0e14-192">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="c0e14-192">Getting in touch with the Microsoft Edge WebView team</span></span>  

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
