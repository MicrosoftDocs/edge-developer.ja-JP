---
description: WebView2 for WPF アプリの概要ガイド
title: WebView2 for WPF アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、wpf アプリ、wpf、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: e928dae0aa63f15ca5fa21860c83fa5529e905df
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182375"
---
# <span data-ttu-id="4d172-104">WPF での WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="4d172-104">Getting started with WebView2 in WPF</span></span>

<span data-ttu-id="4d172-105">この記事では、初めての WebView2 アプリの作成を開始し、 [WebView2](../index.md)の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d172-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2](../index.md).</span></span>  <span data-ttu-id="4d172-106">個々の Api について詳しくは、 [api リファレンス](/dotnet/api/microsoft.web.webview2.wpf)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4d172-106">For more information on individual APIs, see [API reference](/dotnet/api/microsoft.web.webview2.wpf).</span></span>  

## <span data-ttu-id="4d172-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="4d172-107">Prerequisites</span></span>  

<span data-ttu-id="4d172-108">続行する前に、次の前提条件の一覧をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="4d172-109">[WebView2 Runtime][Webview2Installer] または windows 10、windows 8.1、または windows 7 にインストールされている [非安定した Microsoft Edge (Chromium) カナリアチャネル](https://www.microsoftedgeinsider.com/download) 。</span><span class="sxs-lookup"><span data-stu-id="4d172-109">[WebView2 Runtime][Webview2Installer] or any [non-stable Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  
* <span data-ttu-id="4d172-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="4d172-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 or later.</span></span>  

## <span data-ttu-id="4d172-111">手順 1-1 つのウィンドウアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="4d172-111">Step 1 - Create a single window application</span></span>  

<span data-ttu-id="4d172-112">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="4d172-112">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="4d172-113">**Visual Studio**を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d172-113">Open **Visual Studio**.</span></span>  
1.  <span data-ttu-id="4d172-114">[ **Wpf .Net Core app** ] または [ **wpf .Net Framework] アプリ**を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d172-114">Select **WPF .NET Core App** or **WPF .NET Framework App**, and then select **Next**.</span></span>  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF core":::
             <span data-ttu-id="4d172-116">WPF core</span><span class="sxs-lookup"><span data-stu-id="4d172-116">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF フレームワーク":::
             <span data-ttu-id="4d172-118">WPF フレームワーク</span><span class="sxs-lookup"><span data-stu-id="4d172-118">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="4d172-119">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4d172-119">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="4d172-120">.NET Framework 4.6.2 以降、または .NET Core 3.0 以降を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d172-120">Select .NET Framework 4.6.2 or later, or .NET Core 3.0 or later.</span></span>  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアの作成":::
                 <span data-ttu-id="4d172-122">コアの作成</span><span class="sxs-lookup"><span data-stu-id="4d172-122">Create core</span></span> :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークの作成":::
                 <span data-ttu-id="4d172-124">フレームワークの作成</span><span class="sxs-lookup"><span data-stu-id="4d172-124">Create Framework</span></span> :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  <span data-ttu-id="4d172-125">プロジェクトを作成するには、[ **作成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d172-125">Select **Create** to create your project.</span></span>  
    
## <span data-ttu-id="4d172-126">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="4d172-126">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="4d172-127">次に、NuGet を使ってプロジェクトに WebView2 SDK を追加します。</span><span class="sxs-lookup"><span data-stu-id="4d172-127">Next add the WebView2 SDK to the project using NuGet.</span></span>  

1.  <span data-ttu-id="4d172-128">プロジェクトのコンテキストメニューを開き (\ [\] を右クリックし)、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d172-128">Open the context menu on the project \(right-click\), and select **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       <span data-ttu-id="4d172-130">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="4d172-130">NuGet</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="4d172-131">`Microsoft.Web.WebView2`検索バーに入力します。</span><span class="sxs-lookup"><span data-stu-id="4d172-131">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="4d172-132">検索結果から [ **WebView2** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4d172-132">Select **Microsoft.Web.WebView2** from the search results.</span></span>  
   
     ![nuget.exe](./media/installnuget.PNG)
    
    <span data-ttu-id="4d172-134">WebView2 API を使ってアプリケーションの開発を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="4d172-134">You're all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="4d172-135">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4d172-135">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="4d172-136">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d172-136">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空のアプリ":::
       <span data-ttu-id="4d172-138">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="4d172-138">Empty app</span></span>
    :::image-end:::  
    
## <span data-ttu-id="4d172-139">手順 3-MainWindow で1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="4d172-139">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="4d172-140">次に、アプリケーションに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="4d172-140">Next add a WebView to your application.</span></span>  

1.  <span data-ttu-id="4d172-141">[開く] `MainWindow.xaml` を選びます。</span><span class="sxs-lookup"><span data-stu-id="4d172-141">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="4d172-142">タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-142">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    <span data-ttu-id="4d172-143">コードが `MainWindow.xaml` 次のコードスニペットのようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-143">Confirm that the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="4d172-144">次のコードスニペットを使って、タグを置き換えて WebView2 コントロールを追加し `<Grid>` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-144">Add the WebView2 control by replacing the `<Grid>` tags, with the following code snippet.</span></span>  <span data-ttu-id="4d172-145">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d172-145">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="4d172-146">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="4d172-146">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="4d172-147">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com](https://www.microsoft.com) します。</span><span class="sxs-lookup"><span data-stu-id="4d172-147">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="4d172-149">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4d172-149">Microsoft.com</span></span>
    :::image-end:::  
    
## <span data-ttu-id="4d172-150">ステップ 4-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="4d172-150">Step 4 - Navigation</span></span>  

<span data-ttu-id="4d172-151">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレスバーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="4d172-151">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="4d172-152">**MainWindow**で、WebView を含む DockPanel 内に次のコードスニペットをコピーして貼り付けて、アドレスバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d172-152">In **MainWindow.xaml**, add an address bar by copying and pasting the following code snippet inside the DockPanel that contains the WebView.</span></span>  
    
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
    
    <span data-ttu-id="4d172-153">次のコードスニペットのように、セクションが次のようになっていることを確認 `DockPanel` `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="4d172-153">Confirm that the `DockPanel` section of `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="4d172-154">`MainWindow.xaml.cs`Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="4d172-154">Open `MainWindow.xaml.cs` in Visual Studio.</span></span>  <span data-ttu-id="4d172-155">`CoreWebView2`次のコードスニペットを先頭に挿入して、名前空間を追加し `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-155">Add the `CoreWebView2` namespace by inserting the following code snippet at the top of `MainWindow.xaml.cs`.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="4d172-156">**MainWindow.xaml.cs**で、次のコードスニペットをコピーして、 `ButtonGo_Click` アドレスバーに入力された URL に WebView を移動するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d172-156">In **MainWindow.xaml.cs**, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    <span data-ttu-id="4d172-157">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="4d172-157">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="4d172-158">アドレスバーに新しい URL を入力し **、[設定] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-158">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="4d172-159">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="4d172-159">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="4d172-160">WebView2 コントロールが URL に移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-160">Confirm that the WebView2 control navigates to the URL.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="4d172-161">アドレスバーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-161">Make sure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="4d172-162">`ArgumentException`URL がまたはで始まらない場合は、がスローされ `http://` `https://` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-162">An `ArgumentException` is thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
       <span data-ttu-id="4d172-164">Bing</span><span class="sxs-lookup"><span data-stu-id="4d172-164">Bing</span></span>
    :::image-end:::
    
## <span data-ttu-id="4d172-165">ステップ 5-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="4d172-165">Step 5 - Navigation events</span></span>  

<span data-ttu-id="4d172-166">Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="4d172-166">During webpage navigation, the WebView2 control raises events.</span></span> <span data-ttu-id="4d172-167">WebView2 コントロールをホストするアプリケーションは、次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="4d172-167">The application that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="4d172-168">詳細については、「 [ナビゲーションイベント](../concepts/navigation-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d172-168">For more information, see [Navigation Events](../concepts/navigation-events.md).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   <span data-ttu-id="4d172-170">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="4d172-170">Navigation events</span></span>
:::image-end:::  

<span data-ttu-id="4d172-171">エラーが発生した場合、次のイベントが発生し、エラーページへの移動に依存することがあります。</span><span class="sxs-lookup"><span data-stu-id="4d172-171">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

<span data-ttu-id="4d172-172">HTTP リダイレクトがある場合は、複数のイベントがあり `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-172">When there's an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="4d172-173">これらのイベントの使い方を示すには、HTTPS を使って `NavigationStarting` いない要求をキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="4d172-173">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="4d172-174">で `MainWindow.xaml.cs` 、次に示すようにコンストラクターを変更し、関数を追加し `EnsureHttps` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-174">In `MainWindow.xaml.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="4d172-175">コンストラクターでは、EnsureHttps は、WebView2 コントロールのイベントのイベントハンドラーとして登録され `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-175">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="4d172-176">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="4d172-176">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="4d172-177">HTTP サイトに移動するときに、WebView の表示が **変わら**ないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-177">Confirm that when navigating to an HTTP site, the WebView **remains unchanged**.</span></span>  <span data-ttu-id="4d172-178">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d172-178">However, the WebView navigates to HTTPS sites.</span></span>  

## <span data-ttu-id="4d172-179">ステップ 6-スクリプト</span><span class="sxs-lookup"><span data-stu-id="4d172-179">Step 6 - Scripting</span></span>  

<span data-ttu-id="4d172-180">ホストアプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="4d172-180">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="4d172-181">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベルドキュメントと任意の子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d172-181">The injected JavaScript applies to all new top-level documents and any child frames, until the JavaScript is removed.</span></span>  <span data-ttu-id="4d172-182">挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれるスクリプトの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4d172-182">The injected JavaScript is run after creation of the global object, and before any scripts included in the HTML document.</span></span>  

<span data-ttu-id="4d172-183">スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="4d172-183">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="4d172-184">`EnsureHttps` [Executesの](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync)メソッドを使って、スクリプトが web コンテンツに挿入されるように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="4d172-184">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync](/dotnet/api/microsoft.web.webview2.wpf.webview2.executescriptasync) method.</span></span>  

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

<span data-ttu-id="4d172-185">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="4d172-185">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="4d172-186">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d172-186">Confirm that the application displays an alert when you navigate to a site that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="4d172-188">HTTPS</span><span class="sxs-lookup"><span data-stu-id="4d172-188">HTTPS</span></span>
:::image-end:::  

## <span data-ttu-id="4d172-189">手順 7-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="4d172-189">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="4d172-190">ホストと web コンテンツは、次の方法で相互に通信でき `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-190">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

*   <span data-ttu-id="4d172-191">WebView2 コントロールの Web コンテンツは、を使ってホストにメッセージを投稿でき `window.chrome.webview.postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-191">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="4d172-192">ホストは、ホストに登録されているメッセージを処理し `WebMessageReceived` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-192">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="4d172-193">ホストは、またはを使用して WebView2 コントロールの web コンテンツにメッセージを投稿し `CoreWebView2.PostWebMessageAsString` `CoreWebView2.PostWebMessageAsJSON` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-193">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="4d172-194">これらのメッセージは、ハンドラーが追加されることによって検出され `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-194">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="4d172-195">この通信メカニズムにより、web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d172-195">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="4d172-196">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URL のユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d172-196">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="4d172-197">**MainWindow.xaml.cs**で、 `InitializeAsync` 次のコードスニペットに示すように、コンストラクターを更新し、関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="4d172-197">In **MainWindow.xaml.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="4d172-198">`InitializeAsync`の初期化は非同期であるため、この関数は[EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async)を待機し `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-198">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](/dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
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
    
1.  <span data-ttu-id="4d172-199">**CoreWebView2**が初期化されたら、イベントハンドラーを登録して応答 `WebMessageReceived` します。</span><span class="sxs-lookup"><span data-stu-id="4d172-199">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="4d172-200">**MainWindow.xaml.cs**で、 `InitializeAsync` `UpdateAddressBar` 次のコードスニペットを使用して、更新して追加します。</span><span class="sxs-lookup"><span data-stu-id="4d172-200">In **MainWindow.xaml.cs**, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="4d172-201">WebView が web メッセージを送信して応答するためには、が初期化された後、次のようになり `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="4d172-201">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  
    
    1.  <span data-ttu-id="4d172-202">ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツに、スクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="4d172-202">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    1.  <span data-ttu-id="4d172-203">ホストに URL をポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="4d172-203">Injects a script to the web content that posts the URL to the host.</span></span>  
    
    <span data-ttu-id="4d172-204">では `MainWindow.xaml.cs` 、 `InitializeAsync` 次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="4d172-204">In `MainWindow.xaml.cs`, update `InitializeAsync` as follows:</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    <span data-ttu-id="4d172-205">を押して `F5` アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="4d172-205">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="4d172-206">これで、アドレスバーに WebView2 コントロールの URI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d172-206">Now, the address bar displays the URI in the WebView2 control.</span></span> <span data-ttu-id="4d172-207">新しい URI に正常に移動すると、WebView2 コントロールは、WebView2 コントロールに表示される URI をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4d172-207">When you successfully navigate to a new URI, the WebView2 control alerts the user of the URI that's displayed in the WebView2 control.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="アドレスバー":::
       <span data-ttu-id="4d172-209">アドレスバー</span><span class="sxs-lookup"><span data-stu-id="4d172-209">addressBar</span></span>
    :::image-end:::

<span data-ttu-id="4d172-210">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="4d172-210">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="4d172-211">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4d172-211">Next steps</span></span>  

*   <span data-ttu-id="4d172-212">WebView2 機能の包括的な例については、「GitHub の [WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d172-212">For a comprehensive example of WebView2 capabilities, see [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) on GitHub.</span></span>  
*   <span data-ttu-id="4d172-213">WebView2 Api について詳しくは、 [api リファレンス](/dotnet/api/microsoft.web.webview2.wpf.webview2)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4d172-213">For more detailed information about WebView2 APIs, see [API reference](/dotnet/api/microsoft.web.webview2.wpf.webview2).</span></span>  
*   <span data-ttu-id="4d172-214">WebView2 の詳細については、「 [WebView2 のリソース](../index.md#next-steps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d172-214">For more information about  WebView2, see [WebView2 Resources](../index.md#next-steps).</span></span>  

## <span data-ttu-id="4d172-215">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="4d172-215">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer" 
