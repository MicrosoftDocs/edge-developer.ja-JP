---
description: WebView2 for WinForms アプリの概要ガイド
title: WebView2 for WinForms アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、WebView、webview、winforms アプリ、winforms、edge、CoreWebView2、browser control、edge html、はじめに、作業の開始、.NET、windows フォーム
ms.openlocfilehash: f4768c38f293d1931e625136ea7068a61176541e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182389"
---
# <span data-ttu-id="d3325-104">Windows フォームでの WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="d3325-104">Getting started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="d3325-105">この記事では、初めての WebView2 アプリの作成を開始し、 [WebView2](/microsoft-edge/webview2/index)の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3325-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2](/microsoft-edge/webview2/index).</span></span>  <span data-ttu-id="d3325-106">個々の Api について詳しくは、 [api リファレンス](/dotnet/api/microsoft.web.webview2.winforms)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3325-106">For more information on individual APIs, see [API reference](/dotnet/api/microsoft.web.webview2.winforms).</span></span>  

## <span data-ttu-id="d3325-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d3325-107">Prerequisites</span></span>  

<span data-ttu-id="d3325-108">続行する前に、次の前提条件の一覧をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="d3325-109">[WebView2 Runtime][Webview2Installer] または windows 10、windows 8.1、または windows 7 にインストールされている [非安定した Microsoft Edge (Chromium) カナリアチャネル](https://www.microsoftedgeinsider.com/download) 。</span><span class="sxs-lookup"><span data-stu-id="d3325-109">[WebView2 Runtime][Webview2Installer] or any [non-stable Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span> 
* <span data-ttu-id="d3325-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="d3325-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="d3325-111">現時点では、WebView2 は .NET 5 および .NET のコアデザイナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d3325-111">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>

## <span data-ttu-id="d3325-112">手順 1-1 つのウィンドウアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="d3325-112">Step 1 - Create a single window application</span></span>

<span data-ttu-id="d3325-113">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="d3325-113">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="d3325-114">**Visual Studio を開きます。**</span><span class="sxs-lookup"><span data-stu-id="d3325-114">Open **Visual Studio.**</span></span>

1. <span data-ttu-id="d3325-115">[ **Windows Forms .Net Framework アプリ** ] を選び、[ **次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d3325-115">Choose **Windows Forms .NET Framework App** and then choose **Next**.</span></span>

    ![newproject](./media/winforms-newproject.png)

1. <span data-ttu-id="d3325-117">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3325-117">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="d3325-118">**.Net Framework 4.6.2**以降を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-118">Select **.NET Framework 4.6.2** or later.</span></span>  

    ![project の startproject](./media/winforms-startproj.png)

1. <span data-ttu-id="d3325-120">プロジェクトを作成するには、[ **作成** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d3325-120">Choose **Create** to create your project.</span></span>

## <span data-ttu-id="d3325-121">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="d3325-121">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="d3325-122">次に、NuGet を使ってプロジェクトに WebView2 SDK を追加します。</span><span class="sxs-lookup"><span data-stu-id="d3325-122">Next add the WebView2 SDK to the project using NuGet.</span></span>

1. <span data-ttu-id="d3325-123">プロジェクトのコンテキストメニューを開き (\ [\] を右クリックし)、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-123">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       <span data-ttu-id="d3325-125">NuGet パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="d3325-125">Manage NuGet Packages</span></span> :::image-end:::

1. <span data-ttu-id="d3325-126">`Microsoft.Web.WebView2`検索バーに入力します。</span><span class="sxs-lookup"><span data-stu-id="d3325-126">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="d3325-127">検索結果から **WebView2** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d3325-127">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  

    ![nuget.exe](./media/installnuget.png)

<span data-ttu-id="d3325-129">WebView2 API を使ってアプリケーションの開発を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="d3325-129">You're all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="d3325-130">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-130">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="d3325-131">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3325-131">The running project displays an empty window.</span></span>  

![emptyApp](./media/winforms-emptyApp.png)

## <span data-ttu-id="d3325-133">手順 3-1 つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="d3325-133">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="d3325-134">次に、アプリケーションに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="d3325-134">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="d3325-135">**Windows フォームデザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3325-135">Open the **Windows Forms Designer**.</span></span>  
1. <span data-ttu-id="d3325-136">**ツールボックス**で**WebView2**を検索します。</span><span class="sxs-lookup"><span data-stu-id="d3325-136">Search for **WebView2** in the **Toolbox**.</span></span> <span data-ttu-id="d3325-137">**WebView2**コントロールを Windows フォームアプリにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="d3325-137">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       <span data-ttu-id="d3325-139">WebView2 が表示されたツールボックス</span><span class="sxs-lookup"><span data-stu-id="d3325-139">Toolbox displaying WebView2</span></span> :::image-end:::  

1. <span data-ttu-id="d3325-140">`Name`プロパティをに変更 `webView` します。</span><span class="sxs-lookup"><span data-stu-id="d3325-140">Change the `Name` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       <span data-ttu-id="d3325-142">WebView2 コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="d3325-142">Properties of the WebView2 control</span></span> :::image-end:::

1. <span data-ttu-id="d3325-143">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="d3325-143">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span> <span data-ttu-id="d3325-144">Source プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="d3325-144">Set the Source property to</span></span> <https://www.microsoft.com>
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       <span data-ttu-id="d3325-146">WebView2 コントロールの Source プロパティ</span><span class="sxs-lookup"><span data-stu-id="d3325-146">The Source property of the WebView2 control</span></span> :::image-end:::

<span data-ttu-id="d3325-147">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-147">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d3325-148">WebView2 コントロールが表示されていることを確認 [https://www.microsoft.com](https://www.microsoft.com) します。</span><span class="sxs-lookup"><span data-stu-id="d3325-148">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>

![\ 低 ebビュー](./media/winforms-hellowebview.png)

> [!NOTE]
> <span data-ttu-id="d3325-150">高 DPI モニターで作業している場合は、 [高 dpi サポートのために Windows フォームアプリを構成](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3325-150">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support).</span></span>

## <span data-ttu-id="d3325-151">手順 4-ウィンドウのサイズ変更イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="d3325-151">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="d3325-152">ツールボックスからさらにいくつかのコントロールを追加し、ウィンドウのサイズ変更イベントを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="d3325-152">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1. <span data-ttu-id="d3325-153">**Windows フォームデザイナー**で、**ツールボックス**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3325-153">In the **Windows Forms Designer**, open the **Toolbox**</span></span>
1. <span data-ttu-id="d3325-154">**TextBox**を Windows フォームアプリにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="d3325-154">Drag and Drop a **TextBox** into the Windows Forms App.</span></span> <span data-ttu-id="d3325-155">[ **TextBox** `addressBar` **プロパティ] タブ**で、テキストボックスに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3325-155">Name the **TextBox** `addressBar` in the **Properties Tab**.</span></span>
1. <span data-ttu-id="d3325-156">**ボタン**をドラッグして、Windows フォームアプリにドロップします。</span><span class="sxs-lookup"><span data-stu-id="d3325-156">Drag and Drop a **Button** into the Windows Forms App.</span></span> <span data-ttu-id="d3325-157">[ **Button** `Go!` **Button** `goButton` **プロパティ] タブ**で、ボタンのテキストを変更し、ボタンに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3325-157">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

    <span data-ttu-id="d3325-158">このアプリは、デザイナーの次の画像のようになります。</span><span class="sxs-lookup"><span data-stu-id="d3325-158">The app should look like the following image in the designer.</span></span>
    
    ![デザイナー](./media/winforms-designer.png)

1. <span data-ttu-id="d3325-160">**Form1.cs**では、 `Form_Resize` アプリのウィンドウのサイズが変更されたときに、コントロールを配置したままにします。</span><span class="sxs-lookup"><span data-stu-id="d3325-160">In **Form1.cs** define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

<span data-ttu-id="d3325-161">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-161">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d3325-162">アプリが次のスクリーンショットのように表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-162">Confirm that the app displays similar to the following screenshot.</span></span>

![アプリ](./media/winforms-app.png)

## <span data-ttu-id="d3325-164">ステップ 5-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="d3325-164">Step 5 - Navigation</span></span>

<span data-ttu-id="d3325-165">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレスバーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="d3325-165">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="d3325-166">「 `Form1.cs` 名前空間を追加する」 `CoreWebView2` の先頭に、次のコードスニペットを挿入し `Form1.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-166">In `Form1.cs` add the `CoreWebView2` namespace by inserting the following code snippet at the top of `Form1.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1. <span data-ttu-id="d3325-167">**Windows Forms Designer**で、ボタンをダブルクリックして `Go!` メソッドを作成 `goButton_Click` `Form1.cs` します。</span><span class="sxs-lookup"><span data-stu-id="d3325-167">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in `Form1.cs`.</span></span> <span data-ttu-id="d3325-168">関数内で次のスニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d3325-168">Copy and paste the following snippet inside the function.</span></span> <span data-ttu-id="d3325-169">これで、この関数は、 `goButton_Click` アドレスバーに入力された URL に WebView を移動します。</span><span class="sxs-lookup"><span data-stu-id="d3325-169">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="d3325-170">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-170">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d3325-171">アドレスバーに新しい URL を入力し **、[設定] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-171">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="d3325-172">たとえば、と入力 `https://www.bing.com` します。</span><span class="sxs-lookup"><span data-stu-id="d3325-172">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="d3325-173">WebView2 コントロールが URL に移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-173">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="d3325-174">アドレスバーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-174">Ensure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="d3325-175">`ArgumentException`URL が先頭以外の場合、 `http://` または</span><span class="sxs-lookup"><span data-stu-id="d3325-175">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

![bing.](./media/winforms-bing.png)

## <span data-ttu-id="d3325-177">ステップ 6-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="d3325-177">Step 6 - Navigation events</span></span>  

<span data-ttu-id="d3325-178">Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="d3325-178">During webpage navigation, the WebView2 control raises events.</span></span> <span data-ttu-id="d3325-179">WebView2 コントロールをホストするアプリケーションは、次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d3325-179">The application that hosts WebView2 controls listens for the following events.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="d3325-180">詳細については、「 [ナビゲーションイベント](../concepts/navigation-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3325-180">For more information, see [Navigation Events](../concepts/navigation-events.md).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   <span data-ttu-id="d3325-182">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="d3325-182">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="d3325-183">エラーが発生した場合、次のイベントが発生し、エラーページへの移動に依存することがあります。</span><span class="sxs-lookup"><span data-stu-id="d3325-183">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="d3325-184">HTTP リダイレクトがある場合は、複数のイベントがあり `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-184">When there's an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="d3325-185">これらのイベントの使い方を示すには、HTTPS を使って `NavigationStarting` いない要求をキャンセルするためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="d3325-185">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="d3325-186">で `Form1.cs` 、次に示すようにコンストラクターを変更し、関数を追加し `EnsureHttps` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-186">In `Form1.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

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

<span data-ttu-id="d3325-187">コンストラクターでは、EnsureHttps は、WebView2 コントロールのイベントのイベントハンドラーとして登録され `NavigationStarting` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-187">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="d3325-188">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-188">Select `F5` to build and run your project.</span></span> <span data-ttu-id="d3325-189">HTTP サイトに移動するときに、WebView の表示が変わらないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-189">Confirm that when navigating to an HTTP site, the WebView remains unchanged.</span></span> <span data-ttu-id="d3325-190">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="d3325-190">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="d3325-191">手順 7-スクリプト</span><span class="sxs-lookup"><span data-stu-id="d3325-191">Step 7 - Scripting</span></span>  

<span data-ttu-id="d3325-192">ホストアプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="d3325-192">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="d3325-193">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベルドキュメントと任意の子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3325-193">The injected JavaScript applies to all new top-level documents and any child frames, until the JavaScript is removed.</span></span>  <span data-ttu-id="d3325-194">挿入された JavaScript は、グローバルオブジェクトの作成後、および HTML ドキュメントに含まれるスクリプトの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d3325-194">The injected JavaScript is run after creation of the global object, and before any scripts included in the HTML document.</span></span>  

<span data-ttu-id="d3325-195">スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="d3325-195">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="d3325-196">`EnsureHttps` [Executesの]()メソッドを使って、スクリプトが web コンテンツに挿入されるように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="d3325-196">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync]() method.</span></span>  

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

<span data-ttu-id="d3325-197">`F5`プロジェクトをビルドして実行する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-197">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="d3325-198">HTTPS を使用していないサイトに移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-198">Confirm that the application displays an alert when you navigate to a site that doesn't use HTTPS.</span></span>  

![https](./media/winforms-https.png)

## <span data-ttu-id="d3325-200">手順 8-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="d3325-200">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="d3325-201">ホストと web コンテンツは、次の方法で相互に通信でき `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-201">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="d3325-202">WebView2 コントロールの Web コンテンツは、を使ってホストにメッセージを投稿でき `window.chrome.webview.postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-202">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="d3325-203">ホストは、ホストに登録されているメッセージを処理し `WebMessageReceived` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-203">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="d3325-204">ホストは、またはを使用して WebView2 コントロールの web コンテンツにメッセージを投稿し `CoreWebView2.PostWebMessageAsString` `CoreWebView2.PostWebMessageAsJSON` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-204">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="d3325-205">これらのメッセージは、ハンドラーが追加されることによって検出され `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-205">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="d3325-206">この通信メカニズムにより、web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d3325-206">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="d3325-207">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URL のユーザーに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3325-207">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="d3325-208">**Form1.cs**で、 `InitializeAsync` 次のコードスニペットに示すように、コンストラクターを更新し、関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="d3325-208">In **Form1.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="d3325-209">`InitializeAsync`の初期化は非同期であるため、この関数は[EnsureCoreWebView2Async]()を待機し `CoreWebView2` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-209">The `InitializeAsync` function awaits [EnsureCoreWebView2Async]() because the initialization of `CoreWebView2` is asynchronous.</span></span>  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

1. <span data-ttu-id="d3325-210">**CoreWebView2**が初期化されたら、イベントハンドラーを登録して応答 `WebMessageReceived` します。</span><span class="sxs-lookup"><span data-stu-id="d3325-210">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="d3325-211">`Form1.cs` `InitializeAsync` 次の `UpdateAddressBar` コードスニペットを使用して、での更新と追加を行います。</span><span class="sxs-lookup"><span data-stu-id="d3325-211">In `Form1.cs`, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

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

1. <span data-ttu-id="d3325-212">WebView が web メッセージを送信して応答するためには、が初期化された後、 `CoreWebView2` 次のように、ホストが web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="d3325-212">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1. <span data-ttu-id="d3325-213">を使って、ホストに URL を送信し `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="d3325-213">Send the URL to the host using `postMessage`.</span></span>
    1. <span data-ttu-id="d3325-214">イベントハンドラーを登録して、ホストから送信されたメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="d3325-214">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="d3325-215">`Form1.cs` `InitializeAsync` 次のコードスニペットに示すように、を更新します。</span><span class="sxs-lookup"><span data-stu-id="d3325-215">In `Form1.cs`, update `InitializeAsync` as shown in the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="d3325-216">`F5`アプリをビルドして実行することを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3325-216">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="d3325-217">アドレスバーに、WebView に表示されているサイトの URL が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3325-217">Confirm that the address bar displays the URL of the site displayed in the WebView.</span></span> <span data-ttu-id="d3325-218">また、新しい URL に正常に移動すると、webview に表示された URL のユーザーに対して WebView が通知されます。</span><span class="sxs-lookup"><span data-stu-id="d3325-218">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

![finalapp](./media/winforms-finalapp.png)

<span data-ttu-id="d3325-220">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d3325-220">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="d3325-221">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d3325-221">Next steps</span></span> 

<span data-ttu-id="d3325-222">WebView2 の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3325-222">To continue learning more about WebView2, navigate to the following resources.</span></span>

* <span data-ttu-id="d3325-223">[WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples)には、WebView2's 機能の包括的な例があります。</span><span class="sxs-lookup"><span data-stu-id="d3325-223">The [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) has a comprehensive example of WebView2's capabilities.</span></span>
* <span data-ttu-id="d3325-224">Api [リファレンス](/dotnet/api/microsoft.web.webview2.winforms.webview2) 。 api の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3325-224">The [API reference](/dotnet/api/microsoft.web.webview2.winforms.webview2) for more detailed information about our APIs.</span></span>
* <span data-ttu-id="d3325-225">[WebView2 リソース](../index.md#next-steps)。</span><span class="sxs-lookup"><span data-stu-id="d3325-225">[WebView2 Resources](../index.md#next-steps).</span></span>


## <span data-ttu-id="d3325-226">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="d3325-226">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer" 
