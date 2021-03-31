---
description: WebView2 for WinForms アプリの入門ガイド
title: WebView2 for WinForms アプリの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2, webview2, WebView, webview, winforms アプリ, winforms, edge, CoreWebView2, ブラウザー管理, edge html, getting started, Getting Started, .NET, windows フォーム
ms.openlocfilehash: 45a3b59733a57975e373df2e21258198645be2d4
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306167"
---
# <span data-ttu-id="c7a37-104">Windows フォームでの WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="c7a37-104">Getting started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="c7a37-105">この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="c7a37-106">個々の API の詳細については、API リファレンスに [移動してください][DotnetApiMicrosoftWebWebview2Winforms]。</span><span class="sxs-lookup"><span data-stu-id="c7a37-106">For more information on individual APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2Winforms].</span></span>  

## <span data-ttu-id="c7a37-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c7a37-107">Prerequisites</span></span>  

<span data-ttu-id="c7a37-108">先に進む前に、前提条件の次の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="c7a37-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="c7a37-109">サポートされている OS \(現在は Windows 10、Windows 8.1、Windows 7\) にインストールされている[、WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]ランタイムまたは[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]非安定チャネル。</span><span class="sxs-lookup"><span data-stu-id="c7a37-109">[WebView2 Runtime][MicrosoftDeveloperMicrosoftEdgeWebview2] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c7a37-110">WebView チームは Canary チャネルの使用をお勧めします。最小要件バージョンは 82.0.488.0 です。</span><span class="sxs-lookup"><span data-stu-id="c7a37-110">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="c7a37-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 以降。</span><span class="sxs-lookup"><span data-stu-id="c7a37-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 or later.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="c7a37-112">現時点では、WebView2 は .NET 5 および .NET のコア デザイナーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c7a37-112">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>

## <span data-ttu-id="c7a37-113">手順 1 - シングル ウィンドウ アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="c7a37-113">Step 1 - Create a single-window app</span></span>

<span data-ttu-id="c7a37-114">1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-114">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="c7a37-115">In Visual Studio, choose **Windows Forms .NET Framework App**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="c7a37-115">In Visual Studio, choose **Windows Forms .NET Framework App** > **Next**.</span></span>
    
    :::image type="complex" source="./media/winforms-newproject.png" alt-text="新しいプロジェクト" lightbox="./media/winforms-newproject.png":::
       <span data-ttu-id="c7a37-117">新しいプロジェクト</span><span class="sxs-lookup"><span data-stu-id="c7a37-117">New project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="c7a37-118">**プロジェクト名**と**場所**の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="c7a37-119">**.NET Framework 4.6.2 以降を**選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-119">Choose **.NET Framework 4.6.2** or later.</span></span>  
    
    :::image type="complex" source="./media/winforms-startproj.png" alt-text="プロジェクトを開始する" lightbox="./media/winforms-startproj.png":::
       <span data-ttu-id="c7a37-121">プロジェクトを開始する</span><span class="sxs-lookup"><span data-stu-id="c7a37-121">Start project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="c7a37-122">プロジェクトを作成するには、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7a37-122">To create your project, choose **Create**.</span></span>
    
## <span data-ttu-id="c7a37-123">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="c7a37-123">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="c7a37-124">NuGet を使用して、WebView2 SDK をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-124">Use NuGet to add the WebView2 SDK to the project.</span></span>  

1.  <span data-ttu-id="c7a37-125">プロジェクトにマウス ポインターを移動し、コンテキスト メニュー \(右クリック\) を開き、[NuGet パッケージの管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7a37-125">Hover on the project, open the contextual menu \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="NuGet パッケージを管理する":::
       <span data-ttu-id="c7a37-127">NuGet パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="c7a37-127">Manage NuGet Packages</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="c7a37-128">検索バーに `Microsoft.Web.WebView2` **「microsoft.Web.WebView2 >」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="c7a37-128">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
    
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       <span data-ttu-id="c7a37-130">NuGet</span><span class="sxs-lookup"><span data-stu-id="c7a37-130">NuGet</span></span>  
    :::image-end:::
    
    <span data-ttu-id="c7a37-131">WebView2 API を使用してアプリの開発を開始します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-131">Start developing apps using the WebView2 API.</span></span>  <span data-ttu-id="c7a37-132">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-132">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="c7a37-133">実行中のプロジェクトに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-133">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空のアプリ" lightbox="./media/winforms-emptyapp.png":::
       <span data-ttu-id="c7a37-135">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="c7a37-135">Empty app</span></span>  
    :::image-end:::
    
## <span data-ttu-id="c7a37-136">手順 3-1 つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="c7a37-136">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="c7a37-137">WebView をアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-137">Add a WebView to your app.</span></span>  

1.  <span data-ttu-id="c7a37-138">**Windows フォーム デザイナー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-138">Open the **Windows Forms Designer**.</span></span>  
1.  <span data-ttu-id="c7a37-139">**ツールボックス**で**WebView2**を検索します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-139">Search for **WebView2** in the **Toolbox**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c7a37-140">Visual Studio 2017 を使用している場合、既定では **、WebView2** がツールボックスに表示 **されない可能性があります**。</span><span class="sxs-lookup"><span data-stu-id="c7a37-140">If you are using Visual Studio 2017, by default **WebView2** may not display in the **Toolbox**.</span></span>  <span data-ttu-id="c7a37-141">この動作を有効にするには、[ ツール オプション全般] を選択し>自動的にツールボックスにデータを設定します  >    >   `True` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-141">To enable the behavior, choose **Tools** > **Options** > **General** > set the **Automatically Populate Toolbox** setting to `True`.</span></span>  
    
    <span data-ttu-id="c7a37-142">**WebView2**コントロールを Windows フォーム アプリにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="c7a37-142">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="WebView2 が表示されたツールボックス":::
       <span data-ttu-id="c7a37-144">WebView2 が表示されたツールボックス</span><span class="sxs-lookup"><span data-stu-id="c7a37-144">Toolbox displaying WebView2</span></span>
    :::image-end:::  

1.  <span data-ttu-id="c7a37-145">プロパティを `(Name)` 次に設定します `webView` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-145">Set the `(Name)` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 コントロールのプロパティ":::
       <span data-ttu-id="c7a37-147">WebView2 コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a37-147">Properties of the WebView2 control</span></span>
    :::image-end:::

1.  <span data-ttu-id="c7a37-148">この `Source` プロパティは、WebView2 コントロールに表示される初期 URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  <span data-ttu-id="c7a37-149">プロパティを `Source` 次の値に設定します `https://www.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-149">Set the `Source` property to `https://www.microsoft.com`.</span></span>  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 コントロールの Source プロパティ":::
       <span data-ttu-id="c7a37-151">**WebView2**コントロールの Source プロパティ</span><span class="sxs-lookup"><span data-stu-id="c7a37-151">The **Source** property of the WebView2 control</span></span>
    :::image-end:::  

<span data-ttu-id="c7a37-152">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-152">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="c7a37-153">WebView2 コントロールが表示されます [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-153">Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>

:::image type="complex" source="./media/winforms-hellowebview.png" alt-text="hello webview" lightbox="./media/winforms-hellowebview.png":::
   <span data-ttu-id="c7a37-155">hello webview</span><span class="sxs-lookup"><span data-stu-id="c7a37-155">hello webview</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c7a37-156">高 DPI モニターで作業している場合は、 [高 DPI サポートのために Windows フォーム アプリを構成][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7a37-156">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport].</span></span>  

## <span data-ttu-id="c7a37-157">手順 4-ウィンドウのサイズ変更イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="c7a37-157">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="c7a37-158">ツールボックスからさらにいくつかのコントロールを Windows フォームに追加し、ウィンドウのサイズ変更イベントを適切に処理します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-158">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1.  <span data-ttu-id="c7a37-159">**Windows フォーム デザイナー**で、**ツールボックス**を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-159">In the **Windows Forms Designer**, open the **Toolbox**</span></span>
1.  <span data-ttu-id="c7a37-160">Windows Forms アプリ **に TextBox** をドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="c7a37-160">Drag and drop a **TextBox** into the Windows Forms App.</span></span>  <span data-ttu-id="c7a37-161">[プロパティ **] タブで、** テキスト ボックスの名前 **を指定します** `addressBar` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-161">In the **Properties Tab**, name the **TextBox** `addressBar` .</span></span>
1.  <span data-ttu-id="c7a37-162">Windows フォーム アプリ **にボタンを** ドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="c7a37-162">Drag and drop a **Button** into the Windows Forms App.</span></span>  <span data-ttu-id="c7a37-163">**ボタン**のテキストを `Go!` に変更して**プロパティ タブ**で、**ボタン** `goButton`に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-163">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

    <span data-ttu-id="c7a37-164">このアプリは、デザイナー上で次の画像のように見えます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-164">The app should look like the following image in the designer.</span></span>
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="デザイナー" lightbox="./media/winforms-designer.png":::
       <span data-ttu-id="c7a37-166">デザイナー</span><span class="sxs-lookup"><span data-stu-id="c7a37-166">designer</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="c7a37-167">ファイル内 `Form1.cs` で、アプリ ウィンドウのサイズが変更された場合にコントロール `Form_Resize` が配置された状態を維持する定義をします。</span><span class="sxs-lookup"><span data-stu-id="c7a37-167">In the `Form1.cs` file, define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

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

<span data-ttu-id="c7a37-168">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-168">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="c7a37-169">アプリが次のスクリーンショットと同様に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-169">Ensure the app displays similar to the following screenshot.</span></span>

:::image type="complex" source="./media/winforms-app.png" alt-text="アプリ" lightbox="./media/winforms-app.png":::
   <span data-ttu-id="c7a37-171">アプリ</span><span class="sxs-lookup"><span data-stu-id="c7a37-171">App</span></span>  
:::image-end:::

## <span data-ttu-id="c7a37-172">ステップ 5-ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="c7a37-172">Step 5 - Navigation</span></span>

<span data-ttu-id="c7a37-173">WebView2 コントロールに表示される URL をユーザーが変更できるようにする機能を追加するには、アドレス バーをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-173">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="c7a37-174">ファイル内 `Form1.cs` で名前空間を追加するには、次のコード スニペットを上部 `CoreWebView2` に挿入します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-174">In the `Form1.cs`file, to add the `CoreWebView2` namespace, insert the following code snippet at the top.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1.  <span data-ttu-id="c7a37-175">Windows フォーム **デザイナーで、** ボタンをダブルクリックして、 `Go!` ファイル内に `goButton_Click` メソッドを作成 `Form1.cs` します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-175">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in the `Form1.cs` file.</span></span>  <span data-ttu-id="c7a37-176">関数内で次のスニペットをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-176">Copy and paste the following snippet inside the function.</span></span>  <span data-ttu-id="c7a37-177">これで、この関数は、 `goButton_Click` アドレス バーに入力された URL に WebView を移動します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-177">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="c7a37-178">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-178">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="c7a37-179">アドレス バーに新しい URL を入力し [**実行**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-179">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="c7a37-180">たとえば、`https://www.bing.com` と入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-180">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="c7a37-181">WebView2 コントロールが URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-181">Ensure the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="c7a37-182">アドレス バーに完全な URL が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-182">Ensure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="c7a37-183">URL が `http://` または以下で開始する場合は、`ArgumentException`がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-183">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   <span data-ttu-id="c7a37-185">bing.com</span><span class="sxs-lookup"><span data-stu-id="c7a37-185">bing.com</span></span>  
:::image-end:::

## <span data-ttu-id="c7a37-186">ステップ 6-ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="c7a37-186">Step 6 - Navigation events</span></span>  

<span data-ttu-id="c7a37-187">Web ページのナビゲーション中に、WebView2 コントロールはイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-187">During webpage navigation, the WebView2 control raises events.</span></span>  <span data-ttu-id="c7a37-188">WebView2 コントロールをホストするアプリは、次のイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="c7a37-188">The app that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="c7a37-189">詳細については、ナビゲーション イベントに [移動します][Webview2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="c7a37-189">For more information, navigate to [Navigation Events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント":::
   <span data-ttu-id="c7a37-191">ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="c7a37-191">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="c7a37-192">エラーが発生すると、次のイベントが発生し、エラー Web ページへのナビゲーションに依存する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7a37-192">When an error occurs, the following events are raised and may depend on navigation to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> <span data-ttu-id="c7a37-193">HTTP リダイレクトが発生した場合、1 行に `NavigationStarting` 複数のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="c7a37-193">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="c7a37-194">これらのイベントの使い方を示すには、HTTPS を使用しない要求をキャンセルするための `NavigationStarting` 用ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-194">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="c7a37-195">ファイルで `Form1.cs` 、次のコード スニペットに一致するコンストラクターを更新し、関数を追加 `EnsureHttps` します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-195">In the `Form1.cs` file, update the constructor to match the following code snippet and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="c7a37-196">コンストラクターでは、EnsureHttps が、WebView2 コントロールの`NavigationStarting` イベントのイベント ハンドラーとして登録されています。</span><span class="sxs-lookup"><span data-stu-id="c7a37-196">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="c7a37-197">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-197">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="c7a37-198">HTTP サイトに移動する場合、WebView は変更されません。</span><span class="sxs-lookup"><span data-stu-id="c7a37-198">Ensure when navigating to an HTTP site, the WebView remains unchanged.</span></span>  <span data-ttu-id="c7a37-199">ただし、WebView は HTTPS サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-199">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="c7a37-200">手順 7-スクリプト</span><span class="sxs-lookup"><span data-stu-id="c7a37-200">Step 7 - Scripting</span></span>  

<span data-ttu-id="c7a37-201">ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-201">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="c7a37-202">任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-202">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="c7a37-203">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-203">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="c7a37-204">挿入された JavaScript は、特定のタイミングで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-204">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="c7a37-205">グローバル オブジェクトの作成後に実行します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-205">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="c7a37-206">HTML ドキュメントに含まれる他のスクリプトを実行する前に実行します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-206">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="c7a37-207">たとえば、ユーザーが HTTPS 以外のサイトに移動するときに警告を送信するスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-207">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="c7a37-208">`EnsureHttps` [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]メソッドを使用する Web コンテンツにスクリプトを挿入する関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-208">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] method.</span></span>  

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

<span data-ttu-id="c7a37-209">プロジェクトをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-209">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="c7a37-210">HTTPS を使用しない Web サイトに移動すると、アプリに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-210">Ensure the app displays an alert when you navigate to a website that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   <span data-ttu-id="c7a37-212">https</span><span class="sxs-lookup"><span data-stu-id="c7a37-212">https</span></span>  
:::image-end:::

## <span data-ttu-id="c7a37-213">手順 8-ホストと Web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="c7a37-213">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="c7a37-214">ホストコンテンツと Web コンテンツは、次のように相互 `postMessage` に通信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-214">The host and web content may use `postMessage` to communicate with each other as follows:</span></span>  

*   <span data-ttu-id="c7a37-215">WebView2 コントロールの Web コンテンツは、ホストにメッセージを投稿 `window.chrome.webview.postMessage` するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-215">Web content in a WebView2 control may use `window.chrome.webview.postMessage` to post a message to the host.</span></span>  <span data-ttu-id="c7a37-216">ホストは、ホストに登録されている `WebMessageReceived` のいずれかを使ってメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-216">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="c7a37-217">ホストは`CoreWebView2.PostWebMessageAsString` または `CoreWebView2.PostWebMessageAsJSON` を使用して WebView2 コントロールの Web コンテンツにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-217">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="c7a37-218">これらのメッセージは、`window.chrome.webview.addEventListener` に追加されているハンドラーによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-218">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="c7a37-219">通信メカニズムは、ネイティブ機能を使用して、Web コンテンツからホストにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-219">The communication mechanism passes messages from web content to the host using native capabilities.</span></span>  

<span data-ttu-id="c7a37-220">プロジェクトでは、WebView2 コントロールが URL に移動すると、アドレスバーに URL が表示され、WebView2 コントロールに表示される URLについて警告がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-220">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="c7a37-221">ファイル内 `Form1.cs` でコンストラクターを更新し、次のコード `InitializeAsync` スニペットに一致する関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-221">In the `Form1.cs` file, update your constructor and create an `InitializeAsync` function to match the following code snippet.</span></span>  <span data-ttu-id="c7a37-222">`CoreWebView2` の初期化は非同期であるため、`InitializeAsync` の関数は[EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] を待機します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-222">The `InitializeAsync` function awaits [EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] because the initialization of `CoreWebView2` is asynchronous.</span></span>  

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

1.  <span data-ttu-id="c7a37-223">初期化 `CoreWebView2` された後、応答するイベント ハンドラーを登録します `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-223">After `CoreWebView2` is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="c7a37-224">ファイルで `Form1.cs` 、次の `InitializeAsync` コード スニペットを `UpdateAddressBar` 使用して更新して追加します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-224">In the `Form1.cs` file, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

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

1.  <span data-ttu-id="c7a37-225">WebView がWeb メッセージを送信して応答するためには、`CoreWebView2` が初期化された後、ホストが Web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-225">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1.  <span data-ttu-id="c7a37-226">そして、`postMessage` を使って、ホストに URL を送信し ます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-226">Send the URL to the host using `postMessage`.</span></span>
    1.  <span data-ttu-id="c7a37-227">イベント ハンドラーを登録して、ホストから送信されたメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-227">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="c7a37-228">ファイル内 `Form1.cs` で、次の `InitializeAsync` コード スニペットに一致する更新を行います。</span><span class="sxs-lookup"><span data-stu-id="c7a37-228">In the `Form1.cs` file, update `InitializeAsync` to match the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="c7a37-229">アプリをビルドして実行するには、次を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c7a37-229">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="c7a37-230">これで、アドレス バーに WebView2 コントロールの URI が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a37-230">Now, the address bar displays the URI in the WebView2 control.</span></span>  <span data-ttu-id="c7a37-231">また、新しい URL に正常に移動すると、WebView に表示された URL について、WebView はアラートをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c7a37-231">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

:::image type="complex" source="./media/winforms-finalapp.png" alt-text="最終的なアプリ" lightbox="./media/winforms-finalapp.png":::
   <span data-ttu-id="c7a37-233">最終的なアプリ</span><span class="sxs-lookup"><span data-stu-id="c7a37-233">Final app</span></span>  
:::image-end:::

<span data-ttu-id="c7a37-234">これで、最初の WebView2 アプリがビルドされました。</span><span class="sxs-lookup"><span data-stu-id="c7a37-234">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="c7a37-235">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c7a37-235">Next steps</span></span>  

<span data-ttu-id="c7a37-236">WebView2 の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7a37-236">To continue learning more about WebView2, navigate to the following resources.</span></span>  

### <span data-ttu-id="c7a37-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7a37-237">See also</span></span>  

*   <span data-ttu-id="c7a37-238">WebView2 機能の包括的な例については [、WebView2Samples に移動します][GithubMicrosoftedgeWebview2samplesMain]。</span><span class="sxs-lookup"><span data-stu-id="c7a37-238">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain].</span></span>  
*   <span data-ttu-id="c7a37-239">WebView2 の詳細については [、「WebView2 リソース」に移動してください][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="c7a37-239">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  
*   <span data-ttu-id="c7a37-240">WebView2 API の詳細については、API リファレンスに [移動してください][DotnetApiMicrosoftWebWebview2WinformsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="c7a37-240">For detailed information about the WebView2 API, navigate to [API reference][DotnetApiMicrosoftWebWebview2WinformsWebview2].</span></span>  

## <span data-ttu-id="c7a37-241">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="c7a37-241">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async(CoreWebView2Environment) メソッド |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync(String) メソッド |Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "高 DPI サポート向け Windows Forms アプリの構成 - Windows Forms | での高 DPI サポートMicrosoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 開発者"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  