---
description: Microsoft Edge WebView 2 コントロールを使用して、WPF アプリの web コンテンツをホストする
title: Microsoft Edge WebView 2 (WPF アプリ)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、wpf アプリ、wpf、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: 9ecb80050d52d1d3b888027a728456a881d8c5ad
ms.sourcegitcommit: 8f2badc98ea7b7d1861dabfaf0e4dd8677e89bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "10767017"
---
# <span data-ttu-id="13ba2-104">WPF での WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="13ba2-104">Getting started with WebView2 in WPF (Preview)</span></span>

<span data-ttu-id="13ba2-105">この記事では、初めての WebView2 アプリの作成を開始し、 [WebView2 (preview)](../index.md)の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2 (preview)](../index.md).</span></span>  <span data-ttu-id="13ba2-106">個々の Api について詳しくは、 [api リファレンス](../reference/dotnet/0-9-515-reference-webview2.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13ba2-106">For more information on individual APIs, see [API reference](../reference/dotnet/0-9-515-reference-webview2.md).</span></span>  

## <span data-ttu-id="13ba2-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="13ba2-107">Prerequisites</span></span>  

<span data-ttu-id="13ba2-108">続行する前に、次の前提条件の一覧をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="13ba2-109">[Microsoft Edge (Chromium) カナリアチャネル](https://www.microsoftedgeinsider.com/download)は、windows 10、windows 8.1、または windows 7 にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="13ba2-109">[Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  
* <span data-ttu-id="13ba2-110">[Visual Studio](https://visualstudio.microsoft.com/) 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="13ba2-110">[Visual Studio](https://visualstudio.microsoft.com/) 2017 or later.</span></span>  

## <span data-ttu-id="13ba2-111">手順 1-1 つのウィンドウアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="13ba2-111">Step 1 - Create a single window application</span></span>  

<span data-ttu-id="13ba2-112">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-112">Start with a basic desktop project containing a single main window.</span></span>  

1.  <span data-ttu-id="13ba2-113">**Visual Studio**を開きます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-113">Open **Visual Studio**.</span></span>  
1.  <span data-ttu-id="13ba2-114">[ **Wpf .Net Core app** ] または [ **wpf .Net Framework] アプリ**を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-114">Select **WPF .NET Core App** or **WPF .NET Framework App**, and then select **Next**.</span></span>  
    
    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF core":::
             <span data-ttu-id="13ba2-116">WPF core</span><span class="sxs-lookup"><span data-stu-id="13ba2-116">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF フレームワーク":::
             <span data-ttu-id="13ba2-118">WPF フレームワーク</span><span class="sxs-lookup"><span data-stu-id="13ba2-118">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="13ba2-119">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-119">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="13ba2-120">.NET Framework 4.6.2 以降、または .NET Core 3.0 以降を選択します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-120">Select .NET Framework 4.6.2 or later, or .NET Core 3.0 or later.</span></span>  
    
    :::row:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアの作成":::
                 <span data-ttu-id="13ba2-122">コアの作成</span><span class="sxs-lookup"><span data-stu-id="13ba2-122">Create core</span></span> :::image-end:::
           :::column-end:::
           :::column span="1":::
              :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークの作成":::
                 <span data-ttu-id="13ba2-124">フレームワークの作成</span><span class="sxs-lookup"><span data-stu-id="13ba2-124">Create Framework</span></span> :::image-end:::
           :::column-end:::
        :::row-end:::
    
1.  <span data-ttu-id="13ba2-125">プロジェクトを作成するには、[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-125">Select **Create** to create your project.</span></span>  
    
## <span data-ttu-id="13ba2-126">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="13ba2-126">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="13ba2-127">次に、WebView2 SDK をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-127">Next add the WebView2 SDK to the project.</span></span>  <span data-ttu-id="13ba2-128">プレビューでは、Nuget を使用して WebView2 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="13ba2-128">For the preview, install the WebView2 SDK using Nuget.</span></span>  

1.  <span data-ttu-id="13ba2-129">プロジェクトのコンテキストメニューを開き (\ [\] を右クリックし)、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-129">Open the context menu on the project \(right-click\), and select **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       <span data-ttu-id="13ba2-131">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="13ba2-131">Nuget</span></span>
    :::image-end:::
    
2.  <span data-ttu-id="13ba2-132">`Microsoft.Web.WebView2`検索バーに入力します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-132">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="13ba2-133">検索結果から [ **WebView2** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-133">Select **Microsoft.Web.WebView2** from the search results.</span></span>  

3. <span data-ttu-id="13ba2-134">[**プレリリースを含める**] をオンにし、**プレリリース**パッケージバージョンを選択して、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-134">Check **Include prerelease**, select a **prerelease** package version, and then choose **Install**.</span></span>  
  
     ![nuget.exe](./media/installnuget.PNG)
    
    <span data-ttu-id="13ba2-136">WebView2 API を使用したアプリケーションの開発を開始するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="13ba2-136">You are all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="13ba2-137">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-137">Press `F5` to build and run the project.</span></span>  <span data-ttu-id="13ba2-138">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-138">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空のアプリ":::
       <span data-ttu-id="13ba2-140">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="13ba2-140">Empty app</span></span> :::image-end:::  
    
## <span data-ttu-id="13ba2-141">手順 3-MainWindow で1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="13ba2-141">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="13ba2-142">次に、アプリケーションに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-142">Next add a WebView to your application.</span></span>  

1.  <span data-ttu-id="13ba2-143">[開く] `MainWindow.xaml` を選びます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-143">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="13ba2-144">タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-144">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  
    
    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  
    
    <span data-ttu-id="13ba2-145">コードが `MainWindow.xaml` 次のコードスニペットのようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-145">Confirm that the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="13ba2-146">次のコードスニペットを使って、タグを置き換えて WebView2 コントロールを追加し `<Grid>` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-146">Add the WebView2 control by replacing the `<Grid>` tags, with the following code snippet.</span></span>  <span data-ttu-id="13ba2-147">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-147">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  
    
    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  
    
1.  <span data-ttu-id="13ba2-148">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-148">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="13ba2-149">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com](https://www.microsoft.com) します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-149">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="13ba2-151">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="13ba2-151">Microsoft.com</span></span>
    :::image-end:::  
    
## <span data-ttu-id="13ba2-152">ステップ 4-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="13ba2-152">Step 4 - Navigation</span></span>  

<span data-ttu-id="13ba2-153">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレスバーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-153">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="13ba2-154">**MainWindow**で、WebView を含む DockPanel 内に次のコードスニペットをコピーして貼り付けて、アドレスバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-154">In **MainWindow.xaml**, add an address bar by copying and pasting the following code snippet inside the DockPanel that contains the WebView.</span></span>  
    
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
    
    <span data-ttu-id="13ba2-155">次のコードスニペットのように、セクションが次のようになっていることを確認 `DockPanel` `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-155">Confirm that the `DockPanel` section of `MainWindow.xaml` looks like the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="13ba2-156">`MainWindow.xaml.cs`Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-156">Open `MainWindow.xaml.cs` in Visual Studio.</span></span>  <span data-ttu-id="13ba2-157">`CoreWebView2`次のコードスニペットを先頭に挿入して、名前空間を追加し `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-157">Add the `CoreWebView2` namespace by inserting the following code snippet at the top of `MainWindow.xaml.cs`.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="13ba2-158">**MainWindow.xaml.cs**で、次のコードスニペットをコピーして、 `ButtonGo_Click` アドレスバーに入力された URL に WebView を移動するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-158">In **MainWindow.xaml.cs**, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  
    
    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
    <span data-ttu-id="13ba2-159">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-159">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="13ba2-160">アドレスバーに新しい URL を入力し **、[設定] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-160">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="13ba2-161">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-161">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="13ba2-162">WebView2 コントロールが URL に移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-162">Confirm that the WebView2 control navigates to the URL.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="13ba2-163">アドレスバーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-163">Make sure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="13ba2-164">`ArgumentException`URL がまたはで始まらない場合は、がスローされ `http://` `https://` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-164">An `ArgumentException` is thrown if the URL does not start with `http://` or `https://`.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
       <span data-ttu-id="13ba2-166">Bing</span><span class="sxs-lookup"><span data-stu-id="13ba2-166">Bing</span></span>
    :::image-end:::
    
## <span data-ttu-id="13ba2-167">ステップ 5-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="13ba2-167">Step 5 - Navigation events</span></span>  

<span data-ttu-id="13ba2-168">WebView2 コントロールをホストするアプリケーションは、web ページへのナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="13ba2-168">The application that hosts WebView2 controls listens to the following events that are raised by the WebView2 control during navigation to web pages.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="13ba2-169">詳細については、「[ナビゲーションイベント](../reference/win32/0-9-488/icorewebview2.md#navigation-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ba2-169">For more information, see [Navigation Events](../reference/win32/0-9-488/icorewebview2.md#navigation-events).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   <span data-ttu-id="13ba2-171">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="13ba2-171">Navigation events</span></span>
:::image-end:::  

<span data-ttu-id="13ba2-172">エラーが発生した場合、次のイベントが発生し、エラーページへの移動に依存することがあります。</span><span class="sxs-lookup"><span data-stu-id="13ba2-172">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

<span data-ttu-id="13ba2-173">HTTP リダイレクトがある場合は、複数のイベントがあり `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-173">When there is an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="13ba2-174">これらのイベントの使い方を示すには、HTTPS を使って `NavigationStarting` いない要求をキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-174">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that do not use HTTPS.</span></span>  

<span data-ttu-id="13ba2-175">で `MainWindow.xaml.cs` 、次に示すようにコンストラクターを変更し、関数を追加し `EnsureHttps` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-175">In `MainWindow.xaml.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="13ba2-176">コンストラクターでは、EnsureHttps は、WebView2 コントロールのイベントのイベントハンドラーとして登録され `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-176">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="13ba2-177">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-177">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="13ba2-178">HTTP サイトに移動するときに、WebView の表示が**変わら**ないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-178">Confirm that when navigating to an HTTP site, the WebView **remains unchanged**.</span></span>  <span data-ttu-id="13ba2-179">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-179">However, the WebView navigates to HTTPS sites.</span></span>  

## <span data-ttu-id="13ba2-180">ステップ 6-スクリプト</span><span class="sxs-lookup"><span data-stu-id="13ba2-180">Step 6 - Scripting</span></span>  

<span data-ttu-id="13ba2-181">ホストアプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-181">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="13ba2-182">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しい最上位レベルのドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-182">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="13ba2-183">挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-183">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="13ba2-184">スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-184">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="13ba2-185">`EnsureHttps` [Executesの](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync)メソッドを使って、スクリプトが web コンテンツに挿入されるように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-185">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync) method.</span></span>  

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

<span data-ttu-id="13ba2-186">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-186">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="13ba2-187">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-187">Confirm that the application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="13ba2-189">HTTPS</span><span class="sxs-lookup"><span data-stu-id="13ba2-189">HTTPS</span></span>
:::image-end:::  

## <span data-ttu-id="13ba2-190">手順 7-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="13ba2-190">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="13ba2-191">ホストと web コンテンツは、次の方法で相互に通信でき `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-191">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

*   <span data-ttu-id="13ba2-192">WebView2 コントロールの Web コンテンツは、を使ってホストにメッセージを投稿でき `window.chrome.webview.postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-192">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="13ba2-193">ホストは、ホストに登録されているメッセージを処理し `WebMessageReceived` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-193">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="13ba2-194">ホストは、またはを使用して WebView2 コントロールの web コンテンツにメッセージを投稿し `CoreWebView2.PostWebMessageAsString` `CoreWebView2.PostWebMessageAsJSON` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-194">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="13ba2-195">これらのメッセージは、ハンドラーが追加されることによって検出され `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-195">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="13ba2-196">この通信メカニズムにより、web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-196">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="13ba2-197">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URL のユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-197">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="13ba2-198">**MainWindow.xaml.cs**で、 `InitializeAsync` 次のコードスニペットに示すように、コンストラクターを更新し、関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-198">In **MainWindow.xaml.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="13ba2-199">`InitializeAsync`の初期化は非同期であるため、この関数は[EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async)を待機し `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-199">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
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
    
1.  <span data-ttu-id="13ba2-200">**CoreWebView2**が初期化されたら、イベントハンドラーを登録して応答 `WebMessageReceived` します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-200">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="13ba2-201">**MainWindow.xaml.cs** update で、 `InitializeAsync` `UpdateAddressBar` 次のコードスニペットを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-201">In **MainWindow.xaml.cs** update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="13ba2-202">WebView が web メッセージを送信して応答するためには、が初期化された後、次のようになり `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-202">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  
    
    1.  <span data-ttu-id="13ba2-203">ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツに、スクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-203">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    1.  <span data-ttu-id="13ba2-204">ホストに URL をポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-204">Injects a script to the web content that posts the URL to the host.</span></span>  
    
    <span data-ttu-id="13ba2-205">では `MainWindow.xaml.cs` 、 `InitializeAsync` 次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-205">In `MainWindow.xaml.cs`, update `InitializeAsync` as follows:</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
        
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
        await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
    }
    ```  
    
    <span data-ttu-id="13ba2-206">を押して `F5` アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-206">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="13ba2-207">アドレスバーに WebView の URI が表示されるようになり、新しい URI に正常に移動すると、webview に表示される URI のユーザーに対して WebView が通知されます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-207">Now the address bar displays the URI in the WebView and when you successfully navigate to a new URI, the WebView alerts the user of the URI displayed in the WebView.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="アドレスバー":::
       <span data-ttu-id="13ba2-209">アドレスバー</span><span class="sxs-lookup"><span data-stu-id="13ba2-209">addressBar</span></span>
    :::image-end:::

<span data-ttu-id="13ba2-210">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="13ba2-210">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="13ba2-211">次のステップ</span><span class="sxs-lookup"><span data-stu-id="13ba2-211">Next steps</span></span>  

*   <span data-ttu-id="13ba2-212">WebView2 機能の包括的な例については、「GitHub の[WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ba2-212">For a comprehensive example of WebView2 capabilities, see [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) on GitHub.</span></span>  
*   <span data-ttu-id="13ba2-213">WebView2 Api について詳しくは、 [api リファレンス](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13ba2-213">For more detailed information about WebView2 APIs, see [API reference](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md).</span></span>  
*   <span data-ttu-id="13ba2-214">WebView2 の詳細については、「 [WebView2 のリソース](../index.md#next-steps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ba2-214">For more information about  WebView2, see [WebView2 Resources](../index.md#next-steps).</span></span>  

## <span data-ttu-id="13ba2-215">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="13ba2-215">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="13ba2-216">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="13ba2-216">Help build a richer WebView2 experience by sharing your feedback!</span></span>  <span data-ttu-id="13ba2-217">Microsoft Edge WebView[フィードバックリポジトリ](https://github.com/MicrosoftEdge/WebViewFeedback)にアクセスして、機能要求またはバグレポートを送信するか、既知の問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="13ba2-217">Visit the Microsoft Edge WebView [feedback repo](https://github.com/MicrosoftEdge/WebViewFeedback) to submit feature requests or bug reports or search for known issues.</span></span>  
