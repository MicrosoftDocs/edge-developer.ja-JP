---
description: WPF アプリ用 WebView2 の概要ガイド
title: WPF アプリ用 WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, wpf apps, wpf, edge, CoreWebView2, ブラウザー コントロール, edge html, 概要, 概要, .NET
ms.openlocfilehash: de67b8a2da8cda0339b5e8d0b96cf4c3df260ec6
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306146"
---
# <span data-ttu-id="66aa1-104">WPF での WebView2 の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="66aa1-104">Getting started with WebView2 in WPF</span></span>

<span data-ttu-id="66aa1-105">この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="66aa1-106">個々の API の詳細については、API リファレンスに [移動してください][DotnetApiMicrosoftWebWebview2Wpf]。</span><span class="sxs-lookup"><span data-stu-id="66aa1-106">For more information on individual APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2Wpf].</span></span>  

## <span data-ttu-id="66aa1-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="66aa1-107">Prerequisites</span></span>  

<span data-ttu-id="66aa1-108">先に進む前に、前提条件の次の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="66aa1-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="66aa1-109">サポートされている OS \(現在は Windows 10、Windows 8.1、および Windows 7\ にインストールされている[、WebView2][Webview2Installer]ランタイムまたは[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]非安定チャネル。</span><span class="sxs-lookup"><span data-stu-id="66aa1-109">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
*   <span data-ttu-id="66aa1-110">[Visual Studio][MicrosoftVisualstudioMain] 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="66aa1-110">[Visual Studio][MicrosoftVisualstudioMain] 2017 or later.</span></span>  
    
## <span data-ttu-id="66aa1-111">手順 1 - シングル ウィンドウ アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="66aa1-111">Step 1 - Create a single-window app</span></span>  

<span data-ttu-id="66aa1-112">1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-112">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="66aa1-113">In Visual Studio, choose **WPF .NET Core App** \(or **WPF .NET Framework App**\) > **Next**.</span><span class="sxs-lookup"><span data-stu-id="66aa1-113">In Visual Studio, choose **WPF .NET Core App** \(or **WPF .NET Framework App**\) > **Next**.</span></span>  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF コア":::
             <span data-ttu-id="66aa1-115">WPF コア</span><span class="sxs-lookup"><span data-stu-id="66aa1-115">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF フレームワーク":::
             <span data-ttu-id="66aa1-117">WPF フレームワーク</span><span class="sxs-lookup"><span data-stu-id="66aa1-117">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="66aa1-118">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="66aa1-119">**.NET Framework 4.6.2**以降 \(または **.NET Core 3.0**以降\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-119">Choose **.NET Framework 4.6.2** or later \(or **.NET Core 3.0** or later\).</span></span>  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアを作成する":::
                 <span data-ttu-id="66aa1-121">コアを作成する</span><span class="sxs-lookup"><span data-stu-id="66aa1-121">Create core</span></span> :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークを作成する":::
                 <span data-ttu-id="66aa1-123">フレームワークを作成する</span><span class="sxs-lookup"><span data-stu-id="66aa1-123">Create Framework</span></span> :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  <span data-ttu-id="66aa1-124">プロジェクトを作成するには、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="66aa1-124">To create your project, choose **Create**.</span></span>  
    
## <span data-ttu-id="66aa1-125">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="66aa1-125">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="66aa1-126">NuGet を使用して、WebView2 SDK をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-126">Use NuGet to add the WebView2 SDK to the project.</span></span>  

1.  <span data-ttu-id="66aa1-127">プロジェクトにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[NuGet パッケージの管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="66aa1-127">Hover on the projecty, open the contextual menu \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージの管理":::
       <span data-ttu-id="66aa1-129">NuGet パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="66aa1-129">Manage NuGet packages</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="66aa1-130">検索バーに `Microsoft.Web.WebView2` **「microsoft.Web.WebView2 >」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="66aa1-130">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
   
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       <span data-ttu-id="66aa1-132">NuGet</span><span class="sxs-lookup"><span data-stu-id="66aa1-132">NuGet</span></span>  
    :::image-end:::
    
    <span data-ttu-id="66aa1-133">WebView2 API を使用してアプリの開発を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="66aa1-133">Ready to start developing apps using the WebView2 API.</span></span>  <span data-ttu-id="66aa1-134">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-134">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="66aa1-135">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-135">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空のアプリ":::
       <span data-ttu-id="66aa1-137">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="66aa1-137">Empty app</span></span>
    :::image-end:::  
    
## <span data-ttu-id="66aa1-138">手順 3 - MainWindow.xaml で単一の WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="66aa1-138">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="66aa1-139">次に、WebView をアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-139">Next add a WebView to your app.</span></span>  

1.  <span data-ttu-id="66aa1-140">ファイルで `MainWindow.xaml` 、WebView2 XAML 名前空間を追加するには、タグ内に次の行を挿入 `<Window/>` します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-140">In the `MainWindow.xaml` file, to add the WebView2 XAML namespace, insert the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    <span data-ttu-id="66aa1-141">コードが次 `MainWindow.xaml` のコード スニペットのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-141">Ensure the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
    ```xml
    <Window x:Class="WPF_Getting_Started.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:{YOUR PROJECT NAME}"
            xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
            mc:Ignorable="d"
            Title="MainWindow"
            Height="450"
            Width="800"
    >
        <Grid>
        
        </Grid>
    </Window>
    ```  
    
1.  <span data-ttu-id="66aa1-142">WebView2 コントロールを追加するには、タグを次の `<Grid>` コード スニペットに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-142">To add the WebView2 control, replace the `<Grid>` tags with the following code snippet.</span></span>  <span data-ttu-id="66aa1-143">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-143">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="66aa1-144">プロジェクトをビルドして実行するには `F5`  、[WebView2 コントロールが表示されるのを確認する] を選択します [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-144">To build and run the project, select `F5`  Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="66aa1-146">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="66aa1-146">Microsoft.com</span></span>
    :::image-end:::  
    
## <span data-ttu-id="66aa1-147">手順 4 - ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="66aa1-147">Step 4 - Navigation</span></span>  

<span data-ttu-id="66aa1-148">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-148">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="66aa1-149">ファイル内で、WebView を含む内部に次のコード スニペットをコピーして貼り付け、アドレス `MainWindow.xaml` `<DockPanel>` バーを追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-149">In the `MainWindow.xaml` file, add an address bar by copying and pasting the following code snippet inside the `<DockPanel>` that contains the WebView.</span></span>  
    
    ```xml
    <DockPanel DockPanel.Dock="Top">
        <Button x:Name="ButtonGo"
                DockPanel.Dock="Right"
                Click="ButtonGo_Click"
                Content="Go"
        />
        <TextBox Name="addressBar"/>
    </DockPanel>
    ```  
    
    <span data-ttu-id="66aa1-150">ファイルの `<DockPanel>` セクションが次 `MainWindow.xaml` のコード スニペットと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aa1-150">Ensure the `<DockPanel>` section of the `MainWindow.xaml` file matches the following code snippet.</span></span>  
    
    ```xml
    <DockPanel>
        <DockPanel DockPanel.Dock="Top">
            <Button x:Name="ButtonGo" DockPanel.Dock="Right" Click="ButtonGo_Click" Content="Go"/>
            <TextBox Name = "addressBar"/>
        </DockPanel>
        <wv2:WebView2 Name = "webView"
                      Source = "https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="66aa1-151">ファイルVisual Studio名前空間を追加するには、次のコード スニペットを上部 `MainWindow.xaml.cs` `CoreWebView2` に挿入します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-151">In Visual Studio, in the `MainWindow.xaml.cs` file, to add the `CoreWebView2` namespace, insert the following code snippet at the top.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="66aa1-152">ファイル内で、次のコード スニペットをコピーしてメソッドを作成します。このメソッドは、WebView をアドレス バーに入力された `MainWindow.xaml.cs` `ButtonGo_Click` URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-152">In the `MainWindow.xaml.cs`file, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    <span data-ttu-id="66aa1-153">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-153">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="66aa1-154">アドレス バーに新しい URL を入力し、[移動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="66aa1-154">Type a new URL in the address bar and choose **Go**.</span></span>  <span data-ttu-id="66aa1-155">たとえば、「`https://www.bing.com`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-155">For example, type `https://www.bing.com`.</span></span>  <span data-ttu-id="66aa1-156">WebView2 コントロールが URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-156">Ensure the WebView2 control navigates to the URL.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="66aa1-157">アドレス バーに完全な URL が入力されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aa1-157">Make sure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="66aa1-158">URL `ArgumentException` が次で始まるか、または次の形式で始まる場合は、An が `http://` スローされます `https://` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-158">An `ArgumentException` is thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
       <span data-ttu-id="66aa1-160">bing.com</span><span class="sxs-lookup"><span data-stu-id="66aa1-160">bing.com</span></span>
    :::image-end:::
    
## <span data-ttu-id="66aa1-161">手順 5 - ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="66aa1-161">Step 5 - Navigation events</span></span>  

<span data-ttu-id="66aa1-162">Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-162">During webpage navigation, the WebView2 control raises events.</span></span>  <span data-ttu-id="66aa1-163">WebView2 コントロールをホストするアプリは、次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="66aa1-163">The app that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="66aa1-164">詳細については、ナビゲーション イベントに [移動します][Webview2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="66aa1-164">For more information, navigate to [Navigation Events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   <span data-ttu-id="66aa1-166">ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="66aa1-166">Navigation events</span></span>
:::image-end:::  

<span data-ttu-id="66aa1-167">エラーが発生すると、次のイベントが発生し、エラー Web ページへのナビゲーションに依存する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66aa1-167">When an error occurs, the following events are raised and may depend on navigation to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> <span data-ttu-id="66aa1-168">HTTP リダイレクトが発生した場合、1 行に `NavigationStarting` 複数のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="66aa1-168">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="66aa1-169">イベントの使い方を示す場合は、HTTPS 以外の要求をキャンセルするハンドラー `NavigationStarting` を登録します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-169">To demonstrate how to use the events, register a handler for `NavigationStarting` that cancels any non-HTTPS requests.</span></span>  

<span data-ttu-id="66aa1-170">ファイルで `MainWindow.xaml.cs` 、次のコード スニペットに一致するコンストラクターを変更し、関数を追加 `EnsureHttps` します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-170">In the `MainWindow.xaml.cs` file, modify the constructor to match the following code snippet and add the `EnsureHttps` function.</span></span>  

```csharp
public MainWindow()
{
    InitializeComponent();
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

<span data-ttu-id="66aa1-171">コンストラクターでは、EnsureHttps が、WebView2 コントロールの`NavigationStarting` イベントのイベント ハンドラーとして登録されています。</span><span class="sxs-lookup"><span data-stu-id="66aa1-171">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="66aa1-172">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-172">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="66aa1-173">HTTP サイトに移動する場合、WebView は変更されません。</span><span class="sxs-lookup"><span data-stu-id="66aa1-173">Ensure when navigating to an HTTP site, the WebView remains unchanged.</span></span>  <span data-ttu-id="66aa1-174">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-174">However, the WebView navigates to HTTPS sites.</span></span>  

## <span data-ttu-id="66aa1-175">手順 6 - スクリプト</span><span class="sxs-lookup"><span data-stu-id="66aa1-175">Step 6 - Scripting</span></span>  

<span data-ttu-id="66aa1-176">ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-176">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="66aa1-177">任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-177">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="66aa1-178">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-178">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="66aa1-179">挿入された JavaScript は、特定のタイミングで実行されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-179">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="66aa1-180">グローバル オブジェクトの作成後に実行します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-180">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="66aa1-181">HTML ドキュメントに含まれる他のスクリプトを実行する前に実行します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-181">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="66aa1-182">たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-182">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="66aa1-183">`EnsureHttps` [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync)メソッドを使用する Web コンテンツにスクリプトを挿入する関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-183">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) method.</span></span>  

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

<span data-ttu-id="66aa1-184">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-184">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="66aa1-185">HTTPS を使用しない Web サイトに移動すると、アプリに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-185">Ensure the app displays an alert when you navigate to a website that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="66aa1-187">HTTPS</span><span class="sxs-lookup"><span data-stu-id="66aa1-187">HTTPS</span></span>
:::image-end:::  

## <span data-ttu-id="66aa1-188">手順 7 - ホストコンテンツと Web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="66aa1-188">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="66aa1-189">ホストと Web コンテンツは、`postMessage` を使用して次の方法で相互に通信でき ます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-189">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

*   <span data-ttu-id="66aa1-190">WebView2 コントロールの Web コンテンツは、`window.chrome.webview.postMessage` を使ってホストにメッセージを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-190">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="66aa1-191">ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-191">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="66aa1-192">ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-192">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="66aa1-193">これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-193">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="66aa1-194">通信メカニズムは、ネイティブ機能を使用して、Web コンテンツからホストにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-194">The communication mechanism passes messages from web content to the host using native capabilities.</span></span>  

<span data-ttu-id="66aa1-195">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-195">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="66aa1-196">ファイル内 `MainWindow.xaml.cs` でコンストラクターを更新し、次の `InitializeAsync` コード スニペットに一致する関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-196">In the `MainWindow.xaml.cs` file, update your constructor and create an `InitializeAsync` function to match the following code snippet.</span></span>  <span data-ttu-id="66aa1-197">`CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) を待機します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-197">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }
    
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  
    
1.  <span data-ttu-id="66aa1-198">**CoreWebView2** が初期化されたら、イベント ハンドラーを登録して `WebMessageReceived` に応答 します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-198">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="66aa1-199">`MainWindow.xaml.cs` で `InitializeAsync` を更新して、次のコード スニペットを使用して、`UpdateAddressBar` を追加します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-199">In `MainWindow.xaml.cs`, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="66aa1-200">WebView が Web メッセージを送信して応答するために、初期化された後、ホスト `CoreWebView2` は次のようにします。</span><span class="sxs-lookup"><span data-stu-id="66aa1-200">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  
    1.  <span data-ttu-id="66aa1-201">ホストからメッセージを印刷するハンドラーを登録するスクリプトを Web コンテンツに挿入します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-201">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    1.  <span data-ttu-id="66aa1-202">URL をホストに投稿するスクリプトを Web コンテンツに挿入します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-202">Injects a script to the web content that posts the URL to the host.</span></span>  
        
    <span data-ttu-id="66aa1-203">ファイル内 `MainWindow.xaml.cs` で、次の `InitializeAsync` コード スニペットに一致する更新を行います。</span><span class="sxs-lookup"><span data-stu-id="66aa1-203">In the `MainWindow.xaml.cs` file, update `InitializeAsync` to match the following code snippet.</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    <span data-ttu-id="66aa1-204">アプリをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="66aa1-204">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="66aa1-205">これで、アドレス バーに WebView2 コントロールの URI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66aa1-205">Now, the address bar displays the URI in the WebView2 control.</span></span>  <span data-ttu-id="66aa1-206">新しい URI に正常に移動すると、WebView2 コントロールは WebView2 コントロールに表示される URI をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-206">When you successfully navigate to a new URI, the WebView2 control alerts the user of the URI that's displayed in the WebView2 control.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="addressBar":::
       <span data-ttu-id="66aa1-208">addressBar</span><span class="sxs-lookup"><span data-stu-id="66aa1-208">addressBar</span></span>
    :::image-end:::

<span data-ttu-id="66aa1-209">これで、最初の WebView2 アプリがビルドされました。</span><span class="sxs-lookup"><span data-stu-id="66aa1-209">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="66aa1-210">次のステップ</span><span class="sxs-lookup"><span data-stu-id="66aa1-210">Next steps</span></span>  

<span data-ttu-id="66aa1-211">WebView2 の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66aa1-211">To continue learning more about WebView2, navigate to the following resources.</span></span>  

### <span data-ttu-id="66aa1-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="66aa1-212">See also</span></span>  

*   <span data-ttu-id="66aa1-213">WebView2 機能の包括的な例については、GitHub の [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samplesMain] に移動します。</span><span class="sxs-lookup"><span data-stu-id="66aa1-213">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samplesMain] on GitHub.</span></span>  
*   <span data-ttu-id="66aa1-214">WebView2 API の詳細については、API リファレンスに [移動してください](/dotnet/api/microsoft.web.webview2.wpf.webview2)。</span><span class="sxs-lookup"><span data-stu-id="66aa1-214">For more detailed information about WebView2 API, navigate to [API reference](/dotnet/api/microsoft.web.webview2.wpf.webview2).</span></span>  
*   <span data-ttu-id="66aa1-215">WebView2 の詳細については [、「WebView2 リソース」に移動してください](../index.md#next-steps)。</span><span class="sxs-lookup"><span data-stu-id="66aa1-215">For more information about  WebView2, navigate to [WebView2 Resources](../index.md#next-steps).</span></span>  

## <span data-ttu-id="66aa1-216">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="66aa1-216">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  
 
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async(CoreWebView2Environment) メソッド |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 開発者"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualStudioMain]: https://visualstudio.microsoft.com "Microsoft Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 