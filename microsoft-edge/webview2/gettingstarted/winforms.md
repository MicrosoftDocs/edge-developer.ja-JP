---
description: WebView2 for WinForms アプリの入門ガイド
title: WebView2 for WinForms アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, winforms アプリ, winforms, edge, CoreWebView2, ブラウザー管理, edge html, getting started, Getting Started, .NET, windows フォーム
ms.openlocfilehash: f4768c38f293d1931e625136ea7068a61176541e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182389"
---
# <span data-ttu-id="59a66-104">Windows フォームでの WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="59a66-104">Getting started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="59a66-105">この記事では、[WebView2](/microsoft-edge/webview2/index)の主な機能について説明して、初めて WebView2 アプリの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="59a66-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2](/microsoft-edge/webview2/index).</span></span>  <span data-ttu-id="59a66-106">個々の API について詳しくは、「[API リファレンス](/dotnet/api/microsoft.web.webview2.winforms)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59a66-106">For more information on individual APIs, see [API reference](/dotnet/api/microsoft.web.webview2.winforms).</span></span>  

## <span data-ttu-id="59a66-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="59a66-107">Prerequisites</span></span>  

<span data-ttu-id="59a66-108">続行する前に、次の前提条件の一覧をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="59a66-109">[WebView2 Runtime][Webview2Installer] または Windows 10、Windows 8.1、または Windows 7 にインストールされている [非安定型 Microsoft Edge (Chromium) カナリア チャネル](https://www.microsoftedgeinsider.com/download)のいずれか 。</span><span class="sxs-lookup"><span data-stu-id="59a66-109">[WebView2 Runtime][Webview2Installer] or any [non-stable Microsoft Edge (Chromium) Canary channel](https://www.microsoftedgeinsider.com/download) installed on Windows 10, Windows 8.1, or Windows 7.</span></span> 
* <span data-ttu-id="59a66-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="59a66-110">[Visual Studio](https://visualstudio.microsoft.com) 2017 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="59a66-111">現時点では、WebView2 は .NET 5 および .NET のコア デザイナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="59a66-111">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>

## <span data-ttu-id="59a66-112">手順 1-1 つのウィンドウ アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="59a66-112">Step 1 - Create a single window application</span></span>

<span data-ttu-id="59a66-113">1 つのメイン ウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="59a66-113">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="59a66-114">\*\*Visual Studio \*\*を開きます。</span><span class="sxs-lookup"><span data-stu-id="59a66-114">Open **Visual Studio.**</span></span>

1. <span data-ttu-id="59a66-115">[**Windows Forms .Net Framework アプリ**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="59a66-115">Choose **Windows Forms .NET Framework App** and then choose **Next**.</span></span>

    ![newproject](./media/winforms-newproject.png)

1. <span data-ttu-id="59a66-117">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="59a66-117">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="59a66-118">[**.Net Framework 4.6.2**] またはそれ以降を選択します。</span><span class="sxs-lookup"><span data-stu-id="59a66-118">Select **.NET Framework 4.6.2** or later.</span></span>  

    ![startproject](./media/winforms-startproj.png)

1. <span data-ttu-id="59a66-120">プロジェクトを作成するには、[**作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="59a66-120">Choose **Create** to create your project.</span></span>

## <span data-ttu-id="59a66-121">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="59a66-121">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="59a66-122">次に、NuGet を使ってプロジェクトに WebView2 SDK を追加します。</span><span class="sxs-lookup"><span data-stu-id="59a66-122">Next add the WebView2 SDK to the project using NuGet.</span></span>

1. <span data-ttu-id="59a66-123">プロジェクトのコンテキスト メニューを開き \(右クリック\)、[ **NuGet パッケージ...の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="59a66-123">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       <span data-ttu-id="59a66-125">NuGet パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="59a66-125">Manage NuGet Packages</span></span> :::image-end:::

1. <span data-ttu-id="59a66-126">検索バーに `Microsoft.Web.WebView2` を入力します。</span><span class="sxs-lookup"><span data-stu-id="59a66-126">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="59a66-127">検索結果から[**Microsoft.Web.WebView2**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="59a66-127">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  

    ![nuget](./media/installnuget.png)

<span data-ttu-id="59a66-129">WebView2 API を使ってアプリケーションの開発を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="59a66-129">You're all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="59a66-130">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-130">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="59a66-131">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a66-131">The running project displays an empty window.</span></span>  

![emptyApp](./media/winforms-emptyApp.png)

## <span data-ttu-id="59a66-133">手順 3-1 つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="59a66-133">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="59a66-134">次に、アプリケーションに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="59a66-134">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="59a66-135">**Windows フォーム デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="59a66-135">Open the **Windows Forms Designer**.</span></span>  
1. <span data-ttu-id="59a66-136">**ツールボックス**で**WebView2**を検索します。</span><span class="sxs-lookup"><span data-stu-id="59a66-136">Search for **WebView2** in the **Toolbox**.</span></span> <span data-ttu-id="59a66-137">**WebView2**コントロールを Windows フォーム アプリにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="59a66-137">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       <span data-ttu-id="59a66-139">WebView2 が表示されたツールボックス</span><span class="sxs-lookup"><span data-stu-id="59a66-139">Toolbox displaying WebView2</span></span> :::image-end:::  

1. <span data-ttu-id="59a66-140">`Name` プロパティを `webView` に変更します。</span><span class="sxs-lookup"><span data-stu-id="59a66-140">Change the `Name` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       <span data-ttu-id="59a66-142">WebView2 コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="59a66-142">Properties of the WebView2 control</span></span> :::image-end:::

1. <span data-ttu-id="59a66-143">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="59a66-143">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span> <span data-ttu-id="59a66-144">Source プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="59a66-144">Set the Source property to</span></span> <https://www.microsoft.com>
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       <span data-ttu-id="59a66-146">WebView2 コントロールの Source プロパティ</span><span class="sxs-lookup"><span data-stu-id="59a66-146">The Source property of the WebView2 control</span></span> :::image-end:::

<span data-ttu-id="59a66-147">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-147">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="59a66-148">WebView2 コントロールが表示されていることを確認します[https://www.microsoft.com](https://www.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="59a66-148">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>

![hellowebview](./media/winforms-hellowebview.png)

> [!NOTE]
> <span data-ttu-id="59a66-150">高 DPI モニターで作業している場合は、 [高 DPI サポートのために Windows フォーム アプリを構成](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="59a66-150">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support](/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support).</span></span>

## <span data-ttu-id="59a66-151">手順 4-ウィンドウのサイズ変更イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="59a66-151">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="59a66-152">ツールボックスからさらにいくつかのコントロールを Windows フォームに追加し、ウィンドウのサイズ変更イベントを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="59a66-152">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1. <span data-ttu-id="59a66-153">**Windows フォーム デザイナー**で、**ツールボックス**を開きます。</span><span class="sxs-lookup"><span data-stu-id="59a66-153">In the **Windows Forms Designer**, open the **Toolbox**</span></span>
1. <span data-ttu-id="59a66-154">**TextBox**を Windows フォーム アプリにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="59a66-154">Drag and Drop a **TextBox** into the Windows Forms App.</span></span> <span data-ttu-id="59a66-155">**プロパティ タブ**で、**TextBox** `addressBar`に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="59a66-155">Name the **TextBox** `addressBar` in the **Properties Tab**.</span></span>
1. <span data-ttu-id="59a66-156">**ボタン**を、Windows フォーム アプリにドラッグアンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="59a66-156">Drag and Drop a **Button** into the Windows Forms App.</span></span> <span data-ttu-id="59a66-157">**ボタン**のテキストを `Go!` に変更して**プロパティ タブ**で、**ボタン** `goButton`に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="59a66-157">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

    <span data-ttu-id="59a66-158">このアプリは、デザイナー上で次の画像のように見えます。</span><span class="sxs-lookup"><span data-stu-id="59a66-158">The app should look like the following image in the designer.</span></span>
    
    ![デザイナー](./media/winforms-designer.png)

1. <span data-ttu-id="59a66-160">**Form1.cs**で、アプリのウィンドウのサイズが変更されたときに、`Form_Resize` を定義してコントロールを配置したままにします。</span><span class="sxs-lookup"><span data-stu-id="59a66-160">In **Form1.cs** define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

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

<span data-ttu-id="59a66-161">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-161">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="59a66-162">アプリが次のスクリーンショットのように表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-162">Confirm that the app displays similar to the following screenshot.</span></span>

![アプリ](./media/winforms-app.png)

## <span data-ttu-id="59a66-164">ステップ 5-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="59a66-164">Step 5 - Navigation</span></span>

<span data-ttu-id="59a66-165">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="59a66-165">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="59a66-166">`Form1.cs` で `CoreWebView2` namespace を追加するには、`Form1.cs` の先頭に、次のコード スニペットを挿入します。</span><span class="sxs-lookup"><span data-stu-id="59a66-166">In `Form1.cs` add the `CoreWebView2` namespace by inserting the following code snippet at the top of `Form1.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1. <span data-ttu-id="59a66-167">**Windows Forms Designer**で、`Go!` ボタンをダブルクリックして `Form1.cs` に `goButton_Click` メソッドを作成 します。</span><span class="sxs-lookup"><span data-stu-id="59a66-167">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in `Form1.cs`.</span></span> <span data-ttu-id="59a66-168">関数内で次のスニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="59a66-168">Copy and paste the following snippet inside the function.</span></span> <span data-ttu-id="59a66-169">これで、この関数は、 `goButton_Click` アドレス バーに入力された URL に WebView を移動します。</span><span class="sxs-lookup"><span data-stu-id="59a66-169">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="59a66-170">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-170">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="59a66-171">アドレス バーに新しい URL を入力し [**実行**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="59a66-171">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="59a66-172">たとえば、`https://www.bing.com` と入力します。</span><span class="sxs-lookup"><span data-stu-id="59a66-172">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="59a66-173">WebView2 コントロールが URL に移動することを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-173">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="59a66-174">アドレス バーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-174">Ensure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="59a66-175">URL が `http://` または以下で開始する場合は、`ArgumentException`がスローされます。</span><span class="sxs-lookup"><span data-stu-id="59a66-175">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

![bing.](./media/winforms-bing.png)

## <span data-ttu-id="59a66-177">ステップ 6-ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="59a66-177">Step 6 - Navigation events</span></span>  

<span data-ttu-id="59a66-178">Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="59a66-178">During webpage navigation, the WebView2 control raises events.</span></span> <span data-ttu-id="59a66-179">WebView2 コントロールをホストするアプリケーションは、次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="59a66-179">The application that hosts WebView2 controls listens for the following events.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="59a66-180">詳細については、「[ナビゲーション イベント](../concepts/navigation-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a66-180">For more information, see [Navigation Events](../concepts/navigation-events.md).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   <span data-ttu-id="59a66-182">ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="59a66-182">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="59a66-183">エラーが発生した場合、次のイベントが発生し、エラー ページへ移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="59a66-183">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="59a66-184">HTTP リダイレクトがある場合は、複数の`NavigationStarting`イベントがあり ます。</span><span class="sxs-lookup"><span data-stu-id="59a66-184">When there's an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="59a66-185">これらのイベントの使い方を示すには、HTTPS を使用しない要求をキャンセルするための `NavigationStarting` 用ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="59a66-185">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="59a66-186">`Form1.cs` で、次に示すようにコンストラクターを変更し、 `EnsureHttps` 関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="59a66-186">In `Form1.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="59a66-187">コンストラクターでは、EnsureHttps が、WebView2 コントロールの`NavigationStarting` イベントのイベント ハンドラーとして登録されています。</span><span class="sxs-lookup"><span data-stu-id="59a66-187">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="59a66-188">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-188">Select `F5` to build and run your project.</span></span> <span data-ttu-id="59a66-189">HTTP サイトに移動するときに、WebView が変化しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-189">Confirm that when navigating to an HTTP site, the WebView remains unchanged.</span></span> <span data-ttu-id="59a66-190">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="59a66-190">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="59a66-191">手順 7-スクリプト</span><span class="sxs-lookup"><span data-stu-id="59a66-191">Step 7 - Scripting</span></span>  

<span data-ttu-id="59a66-192">ホスト アプリケーションを使って、実行時に WebView2 コントロールに JavaScript コードを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="59a66-192">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="59a66-193">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップレベル ドキュメントと任意の子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="59a66-193">The injected JavaScript applies to all new top-level documents and any child frames, until the JavaScript is removed.</span></span>  <span data-ttu-id="59a66-194">挿入された JavaScript は、グローバル オブジェクトの作成の後、および HTML ドキュメントに含まれるスクリプトの前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="59a66-194">The injected JavaScript is run after creation of the global object, and before any scripts included in the HTML document.</span></span>  

<span data-ttu-id="59a66-195">スクリプトを使用して、HTTPS 以外のサイトに移動したときにユーザーに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="59a66-195">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="59a66-196">[ExecuteScriptAsync]()メソッドを使って、スクリプトがWeb コンテンツに挿入されるように `EnsureHttps` 関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="59a66-196">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync]() method.</span></span>  

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

<span data-ttu-id="59a66-197">`F5` を選択して、プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-197">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="59a66-198">HTTPS を使用していないサイトにユーザーが移動したときに、アプリケーションにアラートが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-198">Confirm that the application displays an alert when you navigate to a site that doesn't use HTTPS.</span></span>  

![https](./media/winforms-https.png)

## <span data-ttu-id="59a66-200">手順 8-ホストと Web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="59a66-200">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="59a66-201">ホストと Web コンテンツは、`postMessage` を使用して次の方法で相互に通信でき ます。</span><span class="sxs-lookup"><span data-stu-id="59a66-201">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="59a66-202">WebView2 コントロールの Web コンテンツは、`window.chrome.webview.postMessage` を使ってホストにメッセージを投稿できます。</span><span class="sxs-lookup"><span data-stu-id="59a66-202">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="59a66-203">ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="59a66-203">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="59a66-204">ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="59a66-204">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="59a66-205">これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="59a66-205">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="59a66-206">この通信メカニズムにより、Web コンテンツはネイティブ機能を使ってホストにメッセージを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="59a66-206">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="59a66-207">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="59a66-207">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="59a66-208">**Form1.cs**で、 次のコード スニペットに示すように、コンストラクターを更新し、`InitializeAsync` 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="59a66-208">In **Form1.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="59a66-209">`CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async]() を待機します。</span><span class="sxs-lookup"><span data-stu-id="59a66-209">The `InitializeAsync` function awaits [EnsureCoreWebView2Async]() because the initialization of `CoreWebView2` is asynchronous.</span></span>  

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

1. <span data-ttu-id="59a66-210">**CoreWebView2** が初期化されたら、イベント ハンドラーを登録して `WebMessageReceived` に応答 します。</span><span class="sxs-lookup"><span data-stu-id="59a66-210">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="59a66-211">`Form1.cs` で `InitializeAsync` を更新して、次のコード スニペットを使用して、`UpdateAddressBar` を追加します。</span><span class="sxs-lookup"><span data-stu-id="59a66-211">In `Form1.cs`, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

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

1. <span data-ttu-id="59a66-212">WebView がWeb メッセージを送信して応答するためには、`CoreWebView2` が初期化された後、ホストが Web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="59a66-212">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1. <span data-ttu-id="59a66-213">そして、`postMessage` を使って、ホストに URL を送信し ます。</span><span class="sxs-lookup"><span data-stu-id="59a66-213">Send the URL to the host using `postMessage`.</span></span>
    1. <span data-ttu-id="59a66-214">イベント ハンドラーを登録して、ホストから送信されたメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="59a66-214">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="59a66-215">次のコード スニペットに示すように、`Form1.cs` で `InitializeAsync` を更新します。</span><span class="sxs-lookup"><span data-stu-id="59a66-215">In `Form1.cs`, update `InitializeAsync` as shown in the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="59a66-216">`F5` を選択して、アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="59a66-216">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="59a66-217">アドレス バーに、WebView に表示されているサイトの URL が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59a66-217">Confirm that the address bar displays the URL of the site displayed in the WebView.</span></span> <span data-ttu-id="59a66-218">また、新しい URL に正常に移動すると、WebView に表示された URL について、WebView はアラートをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="59a66-218">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

![finalapp](./media/winforms-finalapp.png)

<span data-ttu-id="59a66-220">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="59a66-220">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="59a66-221">次のステップ</span><span class="sxs-lookup"><span data-stu-id="59a66-221">Next steps</span></span> 

<span data-ttu-id="59a66-222">WebView2 の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a66-222">To continue learning more about WebView2, navigate to the following resources.</span></span>

* <span data-ttu-id="59a66-223">[WebView2Samples リポジトリ](https://github.com/MicrosoftEdge/WebView2Samples)には、WebView2's 機能の包括的な例があります。</span><span class="sxs-lookup"><span data-stu-id="59a66-223">The [WebView2Samples repo](https://github.com/MicrosoftEdge/WebView2Samples) has a comprehensive example of WebView2's capabilities.</span></span>
* <span data-ttu-id="59a66-224">[API リファレンス](/dotnet/api/microsoft.web.webview2.winforms.webview2) API の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a66-224">The [API reference](/dotnet/api/microsoft.web.webview2.winforms.webview2) for more detailed information about our APIs.</span></span>
* <span data-ttu-id="59a66-225">[WebView2 リソース](../index.md#next-steps)。</span><span class="sxs-lookup"><span data-stu-id="59a66-225">[WebView2 Resources](../index.md#next-steps).</span></span>


## <span data-ttu-id="59a66-226">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="59a66-226">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  


<!-- links -->  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー" 
