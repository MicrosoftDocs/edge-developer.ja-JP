---
description: Microsoft Edge WebView 2 コントロールを使用して、WPF アプリの web コンテンツをホストする
title: Microsoft Edge WebView 2 (WPF アプリ)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、wpf アプリ、wpf、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET
ms.openlocfilehash: 01d92322a85e38dab3c502e8dd76729fef8400b1
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654274"
---
# <span data-ttu-id="feb0f-104">WPF での WebView2 の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="feb0f-104">Getting Started with WebView2 in WPF (Preview)</span></span>  

<span data-ttu-id="feb0f-105">この記事では、初めての WebView2 アプリの作成を開始し、 [WebView2 (preview)](/microsoft-edge/hosting/webview2/index)の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2 (preview)](/microsoft-edge/hosting/webview2/index).</span></span>  <span data-ttu-id="feb0f-106">個々の Api について詳しくは、 [api リファレンス](../reference/dotnet/0-9-515-reference-webview2.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="feb0f-106">For more information on individual APIs, see [API reference](../reference/dotnet/0-9-515-reference-webview2.md).</span></span>  

## <span data-ttu-id="feb0f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="feb0f-107">Prerequisites</span></span>  

<span data-ttu-id="feb0f-108">続行する前に、次の前提条件の一覧をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="feb0f-109">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/)は、windows 10、windows 8.1、または windows 7 にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="feb0f-109">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  <span data-ttu-id="feb0f-110">Microsoft Edge WebView チームは、カナリアチャネルの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="feb0f-110">The Microsoft Edge WebView team recommends using the Canary channel.</span></span>  
* <span data-ttu-id="feb0f-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 以降。</span><span class="sxs-lookup"><span data-stu-id="feb0f-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 or later.</span></span>  

## <span data-ttu-id="feb0f-112">手順 1-1 つのウィンドウアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="feb0f-112">Step 1 - Create a single window application</span></span>

<span data-ttu-id="feb0f-113">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-113">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="feb0f-114">**Visual Studio を開きます。**</span><span class="sxs-lookup"><span data-stu-id="feb0f-114">Open **Visual Studio.**</span></span>
2. <span data-ttu-id="feb0f-115">[ **Wpf .Net Core app** ] または [ **Wpf .net Framework アプリ**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-115">Choose **WPF .NET Core App** or **WPF .NET Framework App**, and then choose **Next**.</span></span>  

    :::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpfcore.png" alt-text="WPF core":::
             <span data-ttu-id="feb0f-117">WPF core</span><span class="sxs-lookup"><span data-stu-id="feb0f-117">WPF core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-wpffw.png" alt-text="WPF フレームワーク":::
             <span data-ttu-id="feb0f-119">WPF フレームワーク</span><span class="sxs-lookup"><span data-stu-id="feb0f-119">WPF Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::

3. <span data-ttu-id="feb0f-120">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-120">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="feb0f-121">.NET Framework 4.6.2 以降、または .NET Core 3.0 以降を選択します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-121">Select .NET Framework 4.6.2 or later, or .NET Core 3.0 or later.</span></span>  

:::row:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-createcore.png" alt-text="コアの作成":::
             <span data-ttu-id="feb0f-123">コアの作成</span><span class="sxs-lookup"><span data-stu-id="feb0f-123">Create core</span></span> :::image-end:::
       :::column-end:::
       :::column span="1":::
          :::image type="complex" source="./media/wpf-gettingstarted-createfw.png" alt-text="フレームワークの作成":::
             <span data-ttu-id="feb0f-125">フレームワークの作成</span><span class="sxs-lookup"><span data-stu-id="feb0f-125">Create Framework</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::

4. <span data-ttu-id="feb0f-126">プロジェクトを作成するには、[**作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-126">Choose **Create** to create your project.</span></span>  

## <span data-ttu-id="feb0f-127">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="feb0f-127">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="feb0f-128">次に、WebView2 SDK をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-128">Next add the WebView2 SDK to the project.</span></span>  <span data-ttu-id="feb0f-129">プレビューでは、Nuget を使用して WebView2 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="feb0f-129">For the preview, install the WebView2 SDK using Nuget.</span></span>  

1. <span data-ttu-id="feb0f-130">プロジェクトのコンテキストメニューを開き (\ [\] を右クリックし)、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-130">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       <span data-ttu-id="feb0f-132">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="feb0f-132">Nuget</span></span> :::image-end:::

2. <span data-ttu-id="feb0f-133">`Microsoft.Web.WebView2`検索バーに入力します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-133">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="feb0f-134">検索結果から**WebView2**を選びます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-134">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  <span data-ttu-id="feb0f-135">パッケージバージョンを**プレリリース**に設定して、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-135">Set the package version to **pre-release**, and then choose **Install**.</span></span>  

     ![nuget.exe](./media/installnuget.PNG)

<span data-ttu-id="feb0f-137">WebView2 API を使用したアプリケーションの開発を開始するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="feb0f-137">You are all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="feb0f-138">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-138">Press `F5` to build and run the project.</span></span>  <span data-ttu-id="feb0f-139">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-139">The running project displays an empty window.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-blank.png" alt-text="空のアプリ":::
   <span data-ttu-id="feb0f-141">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="feb0f-141">Empty app</span></span>
:::image-end:::

## <span data-ttu-id="feb0f-142">手順 3-MainWindow で1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="feb0f-142">Step 3 - Create a single WebView in MainWindow.xaml</span></span>  

<span data-ttu-id="feb0f-143">次に、アプリケーションに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-143">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="feb0f-144">[開く] `MainWindow.xaml` を選びます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-144">Open `MainWindow.xaml`.</span></span>  <span data-ttu-id="feb0f-145">タグ内に次の行を挿入して、WebView2 XAML 名前空間を追加し `<Window/>` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-145">Add the WebView2 XAML namespace by inserting the following line inside the `<Window/>` tag.</span></span>  

    ```xml
    xmlns:wv2="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
    ```  

    <span data-ttu-id="feb0f-146">コードが `MainWindow.xaml` 次のコードスニペットのようになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-146">Confirm that the code in `MainWindow.xaml` looks like the following code snippet.</span></span>  

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
        />
        <Grid>

                </Grid>
    </Window>
    ```  

2. <span data-ttu-id="feb0f-147">次のコードスニペットを使って、タグを置き換えて WebView2 コントロールを追加し `<Grid>` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-147">Add the WebView2 control by replacing the `<Grid>` tags, with the following code snippet.</span></span>  <span data-ttu-id="feb0f-148">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  

    ```xml  
    <DockPanel>
        <wv2:WebView2 Name="webView"
                      Source="https://www.microsoft.com"
        />
    </DockPanel>
    ```  

3. <span data-ttu-id="feb0f-149">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-149">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="feb0f-150">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com](https://www.microsoft.com) します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-150">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-microsoft.png" alt-text="Microsoft.com":::
       <span data-ttu-id="feb0f-152">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="feb0f-152">Microsoft.com</span></span> :::image-end:::

## <span data-ttu-id="feb0f-153">ステップ 4-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="feb0f-153">Step 4 - Navigation</span></span>  

<span data-ttu-id="feb0f-154">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレスバーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-154">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="feb0f-155">**MainWindow**で、WebView を含む DockPanel 内に次のコードスニペットをコピーして貼り付けて、アドレスバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-155">In **MainWindow.xaml**, add an address bar by copying and pasting the following code snippet inside the DockPanel that contains the WebView.</span></span>  

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

<span data-ttu-id="feb0f-156">次のコードスニペットのように、セクションが次のようになっていることを確認 `DockPanel` `MainWindow.xaml` します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-156">Confirm that the `DockPanel` section of `MainWindow.xaml` looks like the following code snippet.</span></span>  

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

2. <span data-ttu-id="feb0f-157">`MainWindow.xaml.cs`Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-157">Open `MainWindow.xaml.cs` in Visual Studio.</span></span>  <span data-ttu-id="feb0f-158">`CoreWebView2`次のコードスニペットを先頭に挿入して、名前空間を追加し `MainWindow.xaml.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-158">Add the `CoreWebView2` namespace by inserting the following code snippet at the top of `MainWindow.xaml.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

3. <span data-ttu-id="feb0f-159">**MainWindow.xaml.cs**で、次のコードスニペットをコピーして、 `ButtonGo_Click` アドレスバーに入力された URL に WebView を移動するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-159">In **MainWindow.xaml.cs**, copy the following code snippet to create the `ButtonGo_Click` method, which navigates the WebView to the URL entered in the address bar.</span></span>  

    ```csharp
    private void ButtonGo_Click(object sender, RoutedEventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="feb0f-160">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-160">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="feb0f-161">アドレスバーに新しい URL を入力し、[設定]**をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-161">Enter a new URL in the address bar, and click **Go**.</span></span>  <span data-ttu-id="feb0f-162">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-162">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="feb0f-163">WebView2 コントロールが URL に移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-163">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="feb0f-164">アドレスバーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-164">Make sure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="feb0f-165">`ArgumentException`URL が先頭以外の場合、 `http://` または</span><span class="sxs-lookup"><span data-stu-id="feb0f-165">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

:::image type="complex" source="./media/wpf-gettingstarted-bing.png" alt-text="Bing":::
   <span data-ttu-id="feb0f-167">Bing</span><span class="sxs-lookup"><span data-stu-id="feb0f-167">Bing</span></span>
:::image-end:::

## <span data-ttu-id="feb0f-168">ステップ 5-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="feb0f-168">Step 5 - Navigation events</span></span>  

<span data-ttu-id="feb0f-169">WebView2 コントロールをホストするアプリケーションは、web ページへのナビゲーション中に WebView2 コントロールによって発生する次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="feb0f-169">The application that hosts WebView2 controls listens to the following events that are raised by the WebView2 control during navigation to web pages.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="feb0f-170">詳細については、「[ナビゲーションイベント](../reference/win32/0-9-488/icorewebview2.md#navigation-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb0f-170">For more information, see [Navigation Events](../reference/win32/0-9-488/icorewebview2.md#navigation-events).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   <span data-ttu-id="feb0f-172">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="feb0f-172">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="feb0f-173">エラーが発生した場合、次のイベントが発生し、エラーページへの移動に依存することがあります。</span><span class="sxs-lookup"><span data-stu-id="feb0f-173">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="feb0f-174">HTTP リダイレクトがある場合は、複数のイベントがあり `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-174">When there is an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="feb0f-175">これらのイベントの使い方を示すには、HTTPS を使って `NavigationStarting` いない要求をキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-175">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that do not use HTTPS.</span></span>  

<span data-ttu-id="feb0f-176">で `MainWindow.xaml.cs` 、次に示すようにコンストラクターを変更し、関数を追加し `EnsureHttps` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-176">In `MainWindow.xaml.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="feb0f-177">コンストラクターでは、EnsureHttps は、WebView2 コントロールのイベントのイベントハンドラーとして登録され `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-177">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="feb0f-178">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-178">Press `F5` to build and run your project.</span></span> <span data-ttu-id="feb0f-179">HTTP サイトに移動するときに、WebView の表示が**変わら**ないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-179">Confirm that when navigating to an HTTP site, the WebView **remains unchanged**.</span></span> <span data-ttu-id="feb0f-180">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-180">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="feb0f-181">ステップ 6-スクリプト</span><span class="sxs-lookup"><span data-stu-id="feb0f-181">Step 6 - Scripting</span></span>  

<span data-ttu-id="feb0f-182">ホストアプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-182">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="feb0f-183">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しい最上位レベルのドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-183">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="feb0f-184">挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-184">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="feb0f-185">スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-185">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="feb0f-186">`EnsureHttps` [Executesの](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync)メソッドを使って、スクリプトが web コンテンツに挿入されるように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-186">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#executescriptasync) method.</span></span>  

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

<span data-ttu-id="feb0f-187">を押して `F5` 、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-187">Press `F5` to build and run your project.</span></span>  <span data-ttu-id="feb0f-188">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-188">Confirm that the application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-https.png" alt-text="HTTPS":::
   <span data-ttu-id="feb0f-190">HTTPS</span><span class="sxs-lookup"><span data-stu-id="feb0f-190">HTTPS</span></span>
:::image-end:::

## <span data-ttu-id="feb0f-191">手順 7-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="feb0f-191">Step 7 - Communication between host and web content</span></span>  

<span data-ttu-id="feb0f-192">ホストと web コンテンツは、次の方法で相互に通信でき `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-192">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="feb0f-193">WebView2 コントロールの Web コンテンツは、を使ってホストにメッセージを投稿でき `window.chrome.webview.postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-193">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="feb0f-194">ホストは、ホストに登録されているメッセージを処理し `WebMessageReceived` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-194">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="feb0f-195">ホストは、またはを使用して WebView2 コントロールの web コンテンツにメッセージを投稿し `CoreWebView2.PostWebMessageAsString` `CoreWebView2.PostWebMessageAsJSON` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-195">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="feb0f-196">これらのメッセージは、ハンドラーが追加されることによって検出され `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-196">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="feb0f-197">この通信メカニズムにより、web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-197">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="feb0f-198">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URL のユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-198">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="feb0f-199">**MainWindow.xaml.cs**で、 `InitializeAsync` 次のコードスニペットに示すように、コンストラクターを更新し、関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-199">In **MainWindow.xaml.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="feb0f-200">`InitializeAsync`の初期化は非同期であるため、この関数は[EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async)を待機し `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-200">The `InitializeAsync` function awaits [EnsureCoreWebView2Async](../reference/wpf/0-9-515/microsoft-web-webview2-wpf-webview2.md#ensurecorewebview2async) because the initialization of `CoreWebView2` is asynchronous.</span></span>  

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

2. <span data-ttu-id="feb0f-201">**CoreWebView2**が初期化されたら、イベントハンドラーを登録して応答 `WebMessageReceived` します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-201">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="feb0f-202">**MainWindow.xaml.cs** update で、 `InitializeAsync` `UpdateAddressBar` 次のコードスニペットを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-202">In **MainWindow.xaml.cs** update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

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

3. <span data-ttu-id="feb0f-203">WebView が web メッセージを送信して応答するためには、が初期化された後、次のようになり `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-203">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host:</span></span>  

    1. <span data-ttu-id="feb0f-204">ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツに、スクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-204">Injects a script to the web content that registers a handler to print message from the host.</span></span>  
    2. <span data-ttu-id="feb0f-205">ホストに URL をポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-205">Injects a script to the web content that posts the URL to the host.</span></span>  

<span data-ttu-id="feb0f-206">では `MainWindow.xaml.cs` 、 `InitializeAsync` 次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-206">In `MainWindow.xaml.cs`, update `InitializeAsync` as follows:</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="feb0f-207">を押して `F5` アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-207">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="feb0f-208">アドレスバーに WebView の URI が表示されるようになり、新しい URI に正常に移動すると、webview に表示される URI のユーザーに対して WebView が通知されます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-208">Now the address bar displays the URI in the WebView and when you successfully navigate to a new URI, the WebView alerts the user of the URI displayed in the WebView.</span></span>  

:::image type="complex" source="./media/wpf-gettingstarted-searchbar.png" alt-text="アドレスバー":::
   <span data-ttu-id="feb0f-210">アドレスバー</span><span class="sxs-lookup"><span data-stu-id="feb0f-210">addressBar</span></span>
:::image-end:::

<span data-ttu-id="feb0f-211">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="feb0f-211">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="feb0f-212">次のステップ</span><span class="sxs-lookup"><span data-stu-id="feb0f-212">Next Steps</span></span>  

<span data-ttu-id="feb0f-213">このチュートリアルではカバーされていない WebView2 の機能が多数あります。</span><span class="sxs-lookup"><span data-stu-id="feb0f-213">There are plenty of WebView2 functionalities that are not covered in this walkthrough.</span></span>  

<span data-ttu-id="feb0f-214">詳細は次のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="feb0f-214">To learn more:</span></span>  

* <span data-ttu-id="feb0f-215">各 API の詳細については、 [api リファレンスを参照](../reference/dotnet/0-9-515-reference-webview2.md)してください。</span><span class="sxs-lookup"><span data-stu-id="feb0f-215">Please explore [API reference](../reference/dotnet/0-9-515-reference-webview2.md) for detailed information about each API.</span></span>  

## <span data-ttu-id="feb0f-216">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="feb0f-216">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="feb0f-217">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="feb0f-217">Help build a richer WebView2 experience by sharing your feedback!</span></span>  <span data-ttu-id="feb0f-218">Microsoft Edge WebView[フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能要求またはバグレポートを送信するか、既知の問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="feb0f-218">Visit the Microsoft Edge WebView [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports or search for known issues.</span></span>  